# SIO_CACHE::BuildReplayPackets(SIO_CACHE_PACKET *)

- ea: `0x140045664`
- end: `0x1400458c8`
- name: `?BuildReplayPackets@SIO_CACHE@@IEAAJPEAVSIO_CACHE_PACKET@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SIO_CACHE_PACKET *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400443c8`

## callees

- `0x1400057f0`
- `0x140005eb0`
- `0x14000bd00`
- `0x14001a250`
- `0x14001a310`
- `0x140026130`
- `0x1400276d0`
- `0x14002a800`
- `0x140045664`
- `0x140046774`
- `0x1400467d0`
- `0x140046f1c`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004572d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140045881`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004572d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140045881`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400456b1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004585a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400456b1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14004585a`

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
0x140045664  mov     [rsp+arg_0], rbx
0x140045669  mov     [rsp+arg_8], rdx
0x14004566e  push    rbp
0x14004566f  push    rsi
0x140045670  push    rdi
0x140045671  push    r12
0x140045673  push    r13
0x140045675  push    r14
0x140045677  push    r15
0x140045679  sub     rsp, 30h
0x14004567d  xor     r15b, r15b
0x140045680  mov     rbx, rcx
0x140045683  mov     [rsp+68h+arg_10], r15b
0x14004568b  xor     edi, edi
0x14004568d  call    ?GetDestageQueueDepth@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetDestageQueueDepth(void)
0x140045692  mov     [rsp+68h+var_48], eax
0x140045696  lea     r12, [rbx+158h]
0x14004569d  xor     r13d, r13d
0x1400456a0  xor     esi, esi
0x1400456a2  xor     r14d, r14d
0x1400456a5  cmp     r13d, eax
0x1400456a8  jnb     loc_140045842
0x1400456ae  mov     rcx, r12; SpinLock
0x1400456b1  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400456b8  nop     dword ptr [rax+rax+00h]
0x1400456bd  lea     rbp, [rbx+1A0h]
0x1400456c4  mov     [rsp+68h+OldIrql], al
0x1400456cb  mov     rsi, [rbp+0]
0x1400456cf  mov     r15, [rsi]
0x1400456d2  xor     r14d, r14d
0x1400456d5  cmp     rsi, rbp
0x1400456d8  jz      short loc_140045723
0x1400456da  test    byte ptr [rsi+40h], 4
0x1400456de  jnz     short loc_140045704
0x1400456e0  movzx   eax, word ptr [rbx+250h]
0x1400456e7  cmp     [rsi+42h], ax
0x1400456eb  jz      short loc_140045704
0x1400456ed  mov     rdx, [rbx+230h]; __int64
0x1400456f4  lea     rcx, [rsi+30h]; this
0x1400456f8  mov     r14, rsi
0x1400456fb  call    ?MarkDestaging@SIO_CACHE_STATE@@QEAAE_J@Z; SIO_CACHE_STATE::MarkDestaging(__int64)
0x140045700  test    al, al
0x140045702  jnz     short loc_14004570C
0x140045704  mov     rsi, r15
0x140045707  mov     r15, [r15]
0x14004570a  jmp     short loc_1400456D2
0x14004570c  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x14004570f  mov     rcx, rbx; this
0x140045712  call    ?QueueLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLine(SIO_CACHE_LINE *)
0x140045717  dec     dword ptr [rbx+224h]
0x14004571d  xor     eax, eax
0x14004571f  mov     [rsi+42h], ax
0x140045723  mov     dl, [rsp+68h+OldIrql]; OldIrql
0x14004572a  mov     rcx, r12; SpinLock
0x14004572d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140045734  nop     dword ptr [rax+rax+00h]
0x140045739  test    r14, r14
0x14004573c  jz      loc_140045838
0x140045742  lock inc dword ptr [rbx+240h]
0x140045749  mov     rdx, [r14+20h]; unsigned __int64
0x14004574d  mov     r8b, 1; unsigned __int8
0x140045750  mov     rcx, rbx; this
0x140045753  call    ?GetLine@SIO_CACHE@@IEAAPEAVSIO_CACHE_LINE@@_KE@Z; SIO_CACHE::GetLine(unsigned __int64,uchar)
0x140045758  mov     ecx, 128h; NumberOfBytes
0x14004575d  mov     r15, rax
0x140045760  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x140045765  test    rax, rax
0x140045768  jz      loc_14004582F
0x14004576e  mov     rcx, rax; this
0x140045771  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x140045776  mov     rbp, rax
0x140045779  mov     rsi, rax
0x14004577c  test    rax, rax
0x14004577f  jz      loc_140045831
0x140045785  mov     r9d, [rbx+1D8h]
0x14004578c  lea     rcx, [rax+70h]
0x140045790  xor     r8d, r8d
0x140045793  lea     edx, [r8+3]
0x140045797  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004579c  mov     edi, eax
0x14004579e  test    eax, eax
0x1400457a0  js      loc_14004583A
0x1400457a6  mov     rcx, [rsp+68h+arg_8]; this
0x1400457ab  mov     rdx, rsi; struct SIO_CACHE_PACKET *
0x1400457ae  mov     [rsi+80h], r14
0x1400457b5  mov     rax, [r14+20h]
0x1400457b9  mov     [rsi+88h], rax
0x1400457c0  mov     eax, [rbx+1D8h]
0x1400457c6  mov     [rsi+90h], eax
0x1400457cc  mov     byte ptr [rsi+0A8h], 3
0x1400457d3  mov     byte ptr [rsi+0AAh], 16h
0x1400457da  mov     dword ptr [rsi+120h], 9
0x1400457e4  mov     [rsi+118h], r15
0x1400457eb  call    ?AttachDestage@SIO_CACHE_PACKET@@QEAAXPEAV1@@Z; SIO_CACHE_PACKET::AttachDestage(SIO_CACHE_PACKET *)
0x1400457f0  mov     rcx, [rsi+118h]
0x1400457f7  add     rcx, 30h ; '0'; this
0x1400457fb  call    ?IsDirty@SIO_CACHE_STATE@@QEAAEXZ; SIO_CACHE_STATE::IsDirty(void)
0x140045800  test    al, al
0x140045802  jz      short loc_14004581B
0x140045804  mov     r15b, 1
0x140045807  mov     dword ptr [rsi+0B4h], 0C0E70025h
0x140045811  mov     [rsp+68h+arg_10], r15b
0x140045819  jmp     short loc_140045823
0x14004581b  mov     r15b, [rsp+68h+arg_10]
0x140045823  mov     eax, [rsp+68h+var_48]
0x140045827  inc     r13d
0x14004582a  jmp     loc_1400456A0
0x14004582f  xor     esi, esi
0x140045831  mov     edi, 0C000009Ah
0x140045836  jmp     short loc_14004583A
0x140045838  xor     esi, esi
0x14004583a  mov     r15b, [rsp+68h+arg_10]
0x140045842  mov     r8d, edi
0x140045845  mov     edx, 9
0x14004584a  mov     rcx, rbx
0x14004584d  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x140045852  test    r14, r14
0x140045855  jz      short loc_14004588D
0x140045857  mov     rcx, r12; SpinLock
0x14004585a  call    cs:__imp_ExAcquireSpinLockExclusive
0x140045861  nop     dword ptr [rax+rax+00h]
0x140045866  mov     bpl, al
0x140045869  test    edi, edi
0x14004586b  jns     short loc_14004587B
0x14004586d  mov     r8d, edi; int
0x140045870  mov     rdx, r14; struct SIO_CACHE_LINE *
0x140045873  mov     rcx, rbx; this
0x140045876  call    ?CompleteDestage@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@J@Z; SIO_CACHE::CompleteDestage(SIO_CACHE_LINE *,long)
0x14004587b  mov     dl, bpl; OldIrql
0x14004587e  mov     rcx, r12; SpinLock
0x140045881  call    cs:__imp_ExReleaseSpinLockExclusive
0x140045888  nop     dword ptr [rax+rax+00h]
0x14004588d  test    rsi, rsi
0x140045890  jz      short loc_1400458A5
0x140045892  mov     r8, [rsi]
0x140045895  mov     edx, 1
0x14004589a  mov     rcx, rsi
0x14004589d  mov     rax, [r8]
0x1400458a0  call    _guard_dispatch_icall
0x1400458a5  mov     rbx, [rsp+68h+arg_0]
0x1400458aa  mov     eax, 0C0E70025h
0x1400458af  test    r15b, r15b
0x1400458b2  cmovnz  edi, eax
0x1400458b5  mov     eax, edi
0x1400458b7  add     rsp, 30h
0x1400458bb  pop     r15
0x1400458bd  pop     r14
0x1400458bf  pop     r13
0x1400458c1  pop     r12
0x1400458c3  pop     rdi
0x1400458c4  pop     rsi
0x1400458c5  pop     rbp
0x1400458c6  retn
```
