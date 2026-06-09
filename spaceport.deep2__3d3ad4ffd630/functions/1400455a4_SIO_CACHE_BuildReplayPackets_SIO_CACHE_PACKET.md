# SIO_CACHE::BuildReplayPackets(SIO_CACHE_PACKET *)

- ea: `0x1400455a4`
- end: `0x140045808`
- name: `?BuildReplayPackets@SIO_CACHE@@IEAAJPEAVSIO_CACHE_PACKET@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SIO_CACHE_PACKET *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140044308`

## callees

- `0x1400057f0`
- `0x140005eb0`
- `0x14000bd00`
- `0x14001a250`
- `0x14001a310`
- `0x140026130`
- `0x1400276d0`
- `0x14002a800`
- `0x1400455a4`
- `0x1400466b4`
- `0x140046710`
- `0x140046e5c`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004566d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400457c1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004566d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400457c1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400455f1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004579a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400455f1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004579a`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::BuildReplayPackets(SIO_CACHE *this, struct SIO_CACHE_PACKET *a2)
{
  char v2; // r15
  int v4; // edi
  unsigned int DestageQueueDepth; // eax
  unsigned int i; // r13d
  SIO_CACHE_PACKET *v7; // rsi
  unsigned __int64 *v8; // r14
  unsigned __int64 *v9; // rsi
  unsigned __int64 *j; // r15
  struct SIO_CACHE_LINE *Line; // r15
  SIO_CACHE_PACKET *v12; // rax
  SIO_CACHE_PACKET *v13; // rax
  KIRQL v14; // bp
  unsigned int v16; // [rsp+20h] [rbp-48h]
  char v18; // [rsp+80h] [rbp+18h]
  KIRQL OldIrql; // [rsp+88h] [rbp+20h]

  v2 = 0;
  v18 = 0;
  v4 = 0;
  DestageQueueDepth = SIO_CACHE::GetDestageQueueDepth(this);
  v16 = DestageQueueDepth;
  for ( i = 0; ; ++i )
  {
    v7 = 0;
    v8 = 0;
    if ( i >= DestageQueueDepth )
      break;
    OldIrql = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
    v9 = (unsigned __int64 *)*((_QWORD *)this + 52);
    for ( j = (unsigned __int64 *)*v9; ; j = (unsigned __int64 *)*j )
    {
      v8 = 0;
      if ( v9 == (unsigned __int64 *)((char *)this + 416) )
        break;
      if ( (v9[8] & 4) == 0 && *((_WORD *)v9 + 33) != *((_WORD *)this + 296) )
      {
        v8 = v9;
        if ( SIO_CACHE_STATE::MarkDestaging((SIO_CACHE_STATE *)(v9 + 6), *((_QWORD *)this + 70)) )
        {
          SIO_CACHE::QueueLine(this, (struct SIO_CACHE_LINE *)v9);
          --*((_DWORD *)this + 137);
          *((_WORD *)v9 + 33) = 0;
          break;
        }
      }
      v9 = j;
    }
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, OldIrql);
    if ( !v8 )
    {
      v7 = 0;
      goto LABEL_21;
    }
    _InterlockedIncrement((volatile signed __int32 *)this + 144);
    Line = SIO_CACHE::GetLine(this, v8[4], 1u);
    v12 = (SIO_CACHE_PACKET *)SC_PACKET::operator new(0x128u);
    if ( !v12 )
    {
      v7 = 0;
LABEL_19:
      v4 = -1073741670;
LABEL_21:
      v2 = v18;
      break;
    }
    v13 = SIO_CACHE_PACKET::SIO_CACHE_PACKET(v12);
    v7 = v13;
    if ( !v13 )
      goto LABEL_19;
    v4 = SC_BUFFER::Initialize((__int64)v13 + 112, 3, 0, *((_DWORD *)this + 118));
    if ( v4 < 0 )
      goto LABEL_21;
    *((_QWORD *)v7 + 16) = v8;
    *((_QWORD *)v7 + 17) = v8[4];
    *((_DWORD *)v7 + 36) = *((_DWORD *)this + 118);
    *((_BYTE *)v7 + 168) = 3;
    *((_BYTE *)v7 + 170) = 22;
    *((_DWORD *)v7 + 72) = 9;
    *((_QWORD *)v7 + 35) = Line;
    SIO_CACHE_PACKET::AttachDestage(a2, v7);
    if ( SIO_CACHE_STATE::IsDirty((SIO_CACHE_STATE *)(*((_QWORD *)v7 + 35) + 48LL)) )
    {
      v2 = 1;
      *((_DWORD *)v7 + 45) = -1058602971;
      v18 = 1;
    }
    else
    {
      v2 = v18;
    }
    DestageQueueDepth = v16;
  }
  SIO_CACHE::LogStatus(this, 9);
  if ( v8 )
  {
    v14 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
    if ( v4 < 0 )
      SIO_CACHE::CompleteDestage(this, (struct SIO_CACHE_LINE *)v8, v4);
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, v14);
  }
  if ( v7 )
    (**(void (__fastcall ***)(SIO_CACHE_PACKET *, __int64))v7)(v7, 1);
  if ( v2 )
    return (unsigned int)-1058602971;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400455a4  mov     [rsp+arg_0], rbx
0x1400455a9  mov     [rsp+arg_8], rdx
0x1400455ae  push    rbp
0x1400455af  push    rsi
0x1400455b0  push    rdi
0x1400455b1  push    r12
0x1400455b3  push    r13
0x1400455b5  push    r14
0x1400455b7  push    r15
0x1400455b9  sub     rsp, 30h
0x1400455bd  xor     r15b, r15b
0x1400455c0  mov     rbx, rcx
0x1400455c3  mov     [rsp+68h+arg_10], r15b
0x1400455cb  xor     edi, edi
0x1400455cd  call    ?GetDestageQueueDepth@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetDestageQueueDepth(void)
0x1400455d2  mov     [rsp+68h+var_48], eax
0x1400455d6  lea     r12, [rbx+158h]
0x1400455dd  xor     r13d, r13d
0x1400455e0  xor     esi, esi
0x1400455e2  xor     r14d, r14d
0x1400455e5  cmp     r13d, eax
0x1400455e8  jnb     loc_140045782
0x1400455ee  mov     rcx, r12; SpinLock
0x1400455f1  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400455f8  nop     dword ptr [rax+rax+00h]
0x1400455fd  lea     rbp, [rbx+1A0h]
0x140045604  mov     [rsp+68h+OldIrql], al
0x14004560b  mov     rsi, [rbp+0]
0x14004560f  mov     r15, [rsi]
0x140045612  xor     r14d, r14d
0x140045615  cmp     rsi, rbp
0x140045618  jz      short loc_140045663
0x14004561a  test    byte ptr [rsi+40h], 4
0x14004561e  jnz     short loc_140045644
0x140045620  movzx   eax, word ptr [rbx+250h]
0x140045627  cmp     [rsi+42h], ax
0x14004562b  jz      short loc_140045644
0x14004562d  mov     rdx, [rbx+230h]; __int64
0x140045634  lea     rcx, [rsi+30h]; this
0x140045638  mov     r14, rsi
0x14004563b  call    ?MarkDestaging@SIO_CACHE_STATE@@QEAAE_J@Z; SIO_CACHE_STATE::MarkDestaging(__int64)
0x140045640  test    al, al
0x140045642  jnz     short loc_14004564C
0x140045644  mov     rsi, r15
0x140045647  mov     r15, [r15]
0x14004564a  jmp     short loc_140045612
0x14004564c  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x14004564f  mov     rcx, rbx; this
0x140045652  call    ?QueueLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLine(SIO_CACHE_LINE *)
0x140045657  dec     dword ptr [rbx+224h]
0x14004565d  xor     eax, eax
0x14004565f  mov     [rsi+42h], ax
0x140045663  mov     dl, [rsp+68h+OldIrql]; OldIrql
0x14004566a  mov     rcx, r12; SpinLock
0x14004566d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140045674  nop     dword ptr [rax+rax+00h]
0x140045679  test    r14, r14
0x14004567c  jz      loc_140045778
0x140045682  lock inc dword ptr [rbx+240h]
0x140045689  mov     rdx, [r14+20h]; unsigned __int64
0x14004568d  mov     r8b, 1; unsigned __int8
0x140045690  mov     rcx, rbx; this
0x140045693  call    ?GetLine@SIO_CACHE@@IEAAPEAVSIO_CACHE_LINE@@_KE@Z; SIO_CACHE::GetLine(unsigned __int64,uchar)
0x140045698  mov     ecx, 128h; NumberOfBytes
0x14004569d  mov     r15, rax
0x1400456a0  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x1400456a5  test    rax, rax
0x1400456a8  jz      loc_14004576F
0x1400456ae  mov     rcx, rax; this
0x1400456b1  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x1400456b6  mov     rbp, rax
0x1400456b9  mov     rsi, rax
0x1400456bc  test    rax, rax
0x1400456bf  jz      loc_140045771
0x1400456c5  mov     r9d, [rbx+1D8h]
0x1400456cc  lea     rcx, [rax+70h]
0x1400456d0  xor     r8d, r8d
0x1400456d3  lea     edx, [r8+3]
0x1400456d7  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x1400456dc  mov     edi, eax
0x1400456de  test    eax, eax
0x1400456e0  js      loc_14004577A
0x1400456e6  mov     rcx, [rsp+68h+arg_8]; this
0x1400456eb  mov     rdx, rsi; struct SIO_CACHE_PACKET *
0x1400456ee  mov     [rsi+80h], r14
0x1400456f5  mov     rax, [r14+20h]
0x1400456f9  mov     [rsi+88h], rax
0x140045700  mov     eax, [rbx+1D8h]
0x140045706  mov     [rsi+90h], eax
0x14004570c  mov     byte ptr [rsi+0A8h], 3
0x140045713  mov     byte ptr [rsi+0AAh], 16h
0x14004571a  mov     dword ptr [rsi+120h], 9
0x140045724  mov     [rsi+118h], r15
0x14004572b  call    ?AttachDestage@SIO_CACHE_PACKET@@QEAAXPEAV1@@Z; SIO_CACHE_PACKET::AttachDestage(SIO_CACHE_PACKET *)
0x140045730  mov     rcx, [rsi+118h]
0x140045737  add     rcx, 30h ; '0'; this
0x14004573b  call    ?IsDirty@SIO_CACHE_STATE@@QEAAEXZ; SIO_CACHE_STATE::IsDirty(void)
0x140045740  test    al, al
0x140045742  jz      short loc_14004575B
0x140045744  mov     r15b, 1
0x140045747  mov     dword ptr [rsi+0B4h], 0C0E70025h
0x140045751  mov     [rsp+68h+arg_10], r15b
0x140045759  jmp     short loc_140045763
0x14004575b  mov     r15b, [rsp+68h+arg_10]
0x140045763  mov     eax, [rsp+68h+var_48]
0x140045767  inc     r13d
0x14004576a  jmp     loc_1400455E0
0x14004576f  xor     esi, esi
0x140045771  mov     edi, 0C000009Ah
0x140045776  jmp     short loc_14004577A
0x140045778  xor     esi, esi
0x14004577a  mov     r15b, [rsp+68h+arg_10]
0x140045782  mov     r8d, edi
0x140045785  mov     edx, 9
0x14004578a  mov     rcx, rbx
0x14004578d  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x140045792  test    r14, r14
0x140045795  jz      short loc_1400457CD
0x140045797  mov     rcx, r12; SpinLock
0x14004579a  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400457a1  nop     dword ptr [rax+rax+00h]
0x1400457a6  mov     bpl, al
0x1400457a9  test    edi, edi
0x1400457ab  jns     short loc_1400457BB
0x1400457ad  mov     r8d, edi; int
0x1400457b0  mov     rdx, r14; struct SIO_CACHE_LINE *
0x1400457b3  mov     rcx, rbx; this
0x1400457b6  call    ?CompleteDestage@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@J@Z; SIO_CACHE::CompleteDestage(SIO_CACHE_LINE *,long)
0x1400457bb  mov     dl, bpl; OldIrql
0x1400457be  mov     rcx, r12; SpinLock
0x1400457c1  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400457c8  nop     dword ptr [rax+rax+00h]
0x1400457cd  test    rsi, rsi
0x1400457d0  jz      short loc_1400457E5
0x1400457d2  mov     r8, [rsi]
0x1400457d5  mov     edx, 1
0x1400457da  mov     rcx, rsi
0x1400457dd  mov     rax, [r8]
0x1400457e0  call    _guard_dispatch_icall
0x1400457e5  mov     rbx, [rsp+68h+arg_0]
0x1400457ea  mov     eax, 0C0E70025h
0x1400457ef  test    r15b, r15b
0x1400457f2  cmovnz  edi, eax
0x1400457f5  mov     eax, edi
0x1400457f7  add     rsp, 30h
0x1400457fb  pop     r15
0x1400457fd  pop     r14
0x1400457ff  pop     r13
0x140045801  pop     r12
0x140045803  pop     rdi
0x140045804  pop     rsi
0x140045805  pop     rbp
0x140045806  retn
```
