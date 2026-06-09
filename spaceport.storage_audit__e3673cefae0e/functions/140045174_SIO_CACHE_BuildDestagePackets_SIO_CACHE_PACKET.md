# SIO_CACHE::BuildDestagePackets(SIO_CACHE_PACKET *)

- ea: `0x140045174`
- end: `0x14004559e`
- name: `?BuildDestagePackets@SIO_CACHE@@IEAAJPEAVSIO_CACHE_PACKET@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SIO_CACHE_PACKET *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140044308`

## callees

- `0x1400057f0`
- `0x140005eb0`
- `0x14000aca0`
- `0x14000bd00`
- `0x14000e0f0`
- `0x14001a250`
- `0x14001e7e0`
- `0x140026130`
- `0x1400276d0`
- `0x14002a800`
- `0x140044138`
- `0x140045174`
- `0x1400466b4`
- `0x140046e5c`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400452b6`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004530d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004554d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400452b6`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004530d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004554d`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140045211`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400452ec`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140045525`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140045211`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400452ec`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140045525`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1400452d6`
- `ntoskrnl!RtlNumberOfSetBits` at `0x1400452d6`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::BuildDestagePackets(SIO_CACHE *this, struct SIO_CACHE_PACKET *a2)
{
  __int64 v3; // rcx
  char v4; // r12
  struct SIO_CACHE_PACKET *v5; // r13
  SIO_CACHE_PACKET *v6; // rbx
  _QWORD *v7; // rsi
  int v8; // r14d
  _QWORD **v9; // r12
  KIRQL v10; // al
  _QWORD *v11; // rbx
  KIRQL v12; // bp
  _QWORD *i; // r15
  ULONG v14; // r12d
  KIRQL v15; // bl
  SIO_CACHE_PACKET *v16; // rax
  SIO_CACHE_PACKET *v17; // rax
  SIO_CACHE_PACKET *v18; // rbp
  SIO_VDT *v19; // rcx
  unsigned __int8 IsValid; // bl
  SIO_RAID *v21; // rax
  int v22; // eax
  struct SIO_CACHE_LINE *v23; // rax
  bool v24; // cf
  KIRQL v25; // r15
  __int64 result; // rax
  unsigned int DestageQueueDepth; // [rsp+20h] [rbp-68h]
  struct SIO_CACHE_LINE *v28; // [rsp+28h] [rbp-60h] BYREF
  struct SIO_CACHE_LINE *v29; // [rsp+30h] [rbp-58h]
  __int64 v30; // [rsp+38h] [rbp-50h]
  char v31; // [rsp+90h] [rbp+8h]
  char v33; // [rsp+A0h] [rbp+18h]
  int v34; // [rsp+A8h] [rbp+20h]

  v3 = *((_QWORD *)this + 1);
  v4 = 0;
  v29 = 0;
  v5 = a2;
  v28 = 0;
  v6 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3);
  if ( !*((_BYTE *)this + 595) )
  {
    if ( SIO_CACHE::GetUsedPercentage(this) )
    {
      v33 = 0;
      DestageQueueDepth = SIO_CACHE::GetDestageQueueDepth(this);
      v34 = 0;
      if ( DestageQueueDepth )
      {
        v9 = (_QWORD **)((char *)this + 352);
        while ( 1 )
        {
          v10 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
          v11 = *v9;
          v12 = v10;
          for ( i = (_QWORD *)**v9; ; i = (_QWORD *)*i )
          {
            v7 = 0;
            if ( v11 == v9 )
              break;
            if ( (v11[8] & 4) == 0 && *((_WORD *)v11 + 33) != *((_WORD *)this + 296) )
            {
              v7 = v11;
              v33 = 1;
              if ( SIO_CACHE_STATE::MarkDestaging((SIO_CACHE_STATE *)(v11 + 6), *((_QWORD *)this + 70)) )
              {
                SIO_CACHE::QueueLine(this, (struct SIO_CACHE_LINE *)v11);
                goto LABEL_16;
              }
            }
            v11 = i;
          }
          if ( !v33
            && *((_BYTE *)this + 594)
            && *((SIO_CACHE **)this + 50) == (SIO_CACHE *)((char *)this + 400)
            && *((SIO_CACHE **)this + 46) == (SIO_CACHE *)((char *)this + 368) )
          {
            v8 = *((_DWORD *)this + 143);
            *((_BYTE *)this + 595) = 1;
          }
LABEL_16:
          if ( v7 )
            *((_WORD *)v7 + 33) = 0;
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, v12);
          if ( !v7 )
            break;
          _InterlockedIncrement((volatile signed __int32 *)this + 144);
          v14 = RtlNumberOfSetBits((PRTL_BITMAP)(v7 + 9));
          if ( v14 )
          {
            v16 = (SIO_CACHE_PACKET *)SC_PACKET::operator new(0x128u);
            if ( !v16 )
            {
              v6 = 0;
LABEL_51:
              v8 = -1073741670;
              goto LABEL_53;
            }
            v17 = SIO_CACHE_PACKET::SIO_CACHE_PACKET(v16);
            v18 = v17;
            v6 = v17;
            if ( !v17 )
              goto LABEL_51;
            v8 = SC_BUFFER::Initialize((__int64)v17 + 112, 3, 0, *((_DWORD *)this + 118));
            if ( v8 < 0 )
              goto LABEL_53;
            *((_QWORD *)v6 + 16) = v7;
            *((_QWORD *)v6 + 17) = v7[4];
            *((_DWORD *)v6 + 36) = *((_DWORD *)this + 118);
            *((_BYTE *)v6 + 168) = 3;
            *((_BYTE *)v6 + 170) = 22;
            v19 = *(SIO_VDT **)(*((_QWORD *)this + 1) + 128LL);
            if ( v19 )
              IsValid = SIO_VDT::IsValid(v19, v7[4], *((unsigned int *)this + 118));
            else
              IsValid = 1;
            v21 = (SIO_RAID *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v30 + 392) + 104LL))(
                                *(_QWORD *)(v30 + 392),
                                v7[4]);
            if ( !v21 && *(_QWORD *)(*((_QWORD *)this + 1) + 128LL) )
              IsValid = 0;
            *((_DWORD *)v18 + 72) = 1;
            if ( !IsValid )
              *((_DWORD *)v18 + 72) = 2;
            if ( v21 )
            {
              if ( *(_DWORD *)SIO_RAID::Resiliency(v21) == 3 && IsValid )
              {
                if ( v14 == *((_DWORD *)v7 + 18) )
                {
                  *((_DWORD *)v18 + 72) = 2;
                }
                else
                {
                  if ( *((_BYTE *)this + 608) )
                  {
                    v22 = 3;
                  }
                  else
                  {
                    if ( *(_BYTE *)(*((_QWORD *)this + 1) + 153LL) )
                    {
                      v8 = SIO_CACHE::AllocateParityLine(this, v7[4], &v28);
                      v6 = v18;
                      if ( v8 < 0 )
                        goto LABEL_53;
                      v23 = v28;
                      v29 = v28;
                    }
                    else
                    {
                      v23 = v29;
                    }
                    *((_QWORD *)v18 + 35) = v23;
                    v22 = 5;
                  }
                  *((_DWORD *)v18 + 72) = v22;
                }
              }
            }
            else
            {
              v31 = 1;
              *((_DWORD *)v18 + 45) = -1058602988;
            }
            SIO_CACHE_PACKET::AttachDestage(a2, v18);
          }
          else
          {
            v15 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
            SIO_CACHE::CompleteDestage(this, (struct SIO_CACHE_LINE *)v7, v8);
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, v15);
          }
          v6 = 0;
          v24 = ++v34 < DestageQueueDepth;
          v9 = (_QWORD **)((char *)this + 352);
          if ( !v24 )
          {
            v7 = 0;
            goto LABEL_53;
          }
        }
        v6 = 0;
LABEL_53:
        v4 = v31;
        v5 = a2;
      }
    }
  }
  SIO_CACHE::LogStatus(this, 8);
  if ( v7 )
  {
    v25 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 86);
    if ( v8 < 0 )
      SIO_CACHE::CompleteDestage(this, (struct SIO_CACHE_LINE *)v7, v8);
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 86, v25);
  }
  if ( v6 )
    (**(void (__fastcall ***)(SIO_CACHE_PACKET *, __int64))v6)(v6, 1);
  result = 0;
  if ( *((struct SIO_CACHE_PACKET **)v5 + 33) == (struct SIO_CACHE_PACKET *)((char *)v5 + 264) )
    result = (unsigned int)v8;
  if ( v4 )
    return 3236364308LL;
  return result;
}

```

## disassembly

```asm
0x140045174  mov     [rsp+arg_8], rdx
0x140045179  push    rbx
0x14004517a  push    rbp
0x14004517b  push    rsi
0x14004517c  push    rdi
0x14004517d  push    r12
0x14004517f  push    r13
0x140045181  push    r14
0x140045183  push    r15
0x140045185  sub     rsp, 48h
0x140045189  xor     eax, eax
0x14004518b  mov     rdi, rcx
0x14004518e  mov     rcx, [rcx+8]
0x140045192  xor     r12b, r12b
0x140045195  mov     [rsp+88h+var_58], rax
0x14004519a  mov     r13, rdx
0x14004519d  mov     [rsp+88h+var_60], rax
0x1400451a2  xor     ebx, ebx
0x1400451a4  xor     esi, esi
0x1400451a6  mov     [rsp+88h+arg_0], r12b
0x1400451ae  mov     rax, [rcx]
0x1400451b1  mov     rax, [rax+50h]
0x1400451b5  call    _guard_dispatch_icall
0x1400451ba  xor     r14d, r14d
0x1400451bd  mov     [rsp+88h+var_50], rax
0x1400451c2  cmp     [rdi+253h], bl
0x1400451c8  jnz     loc_140045506
0x1400451ce  mov     rcx, rdi; this
0x1400451d1  call    ?GetUsedPercentage@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetUsedPercentage(void)
0x1400451d6  test    eax, eax
0x1400451d8  jz      loc_140045506
0x1400451de  mov     rcx, rdi; this
0x1400451e1  mov     [rsp+88h+arg_10], bl
0x1400451e8  call    ?GetDestageQueueDepth@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetDestageQueueDepth(void)
0x1400451ed  mov     [rsp+88h+var_68], eax
0x1400451f1  mov     [rsp+88h+arg_18], ebx
0x1400451f8  test    eax, eax
0x1400451fa  jz      loc_140045506
0x140045200  lea     r13, [rdi+158h]
0x140045207  lea     r12, [rdi+160h]
0x14004520e  mov     rcx, r13; SpinLock
0x140045211  call    cs:__imp_ExAcquireSpinLockExclusive
0x140045218  nop     dword ptr [rax+rax+00h]
0x14004521d  mov     rbx, [r12]
0x140045221  mov     bpl, al
0x140045224  mov     r15, [rbx]
0x140045227  jmp     short loc_140045265
0x140045229  test    byte ptr [rbx+40h], 4
0x14004522d  jnz     short loc_14004525F
0x14004522f  movzx   eax, word ptr [rdi+250h]
0x140045236  cmp     [rbx+42h], ax
0x14004523a  jz      short loc_14004525F
0x14004523c  mov     rdx, [rdi+230h]; __int64
0x140045243  lea     rcx, [rbx+30h]; this
0x140045247  mov     rsi, rbx
0x14004524a  mov     [rsp+88h+arg_10], 1
0x140045252  call    ?MarkDestaging@SIO_CACHE_STATE@@QEAAE_J@Z; SIO_CACHE_STATE::MarkDestaging(__int64)
0x140045257  test    al, al
0x140045259  jnz     loc_14004531E
0x14004525f  mov     rbx, r15
0x140045262  mov     r15, [r15]
0x140045265  xor     esi, esi
0x140045267  cmp     rbx, r12
0x14004526a  jnz     short loc_140045229
0x14004526c  cmp     [rsp+88h+arg_10], sil
0x140045274  jnz     short loc_1400452A5
0x140045276  cmp     [rdi+252h], sil
0x14004527d  jz      short loc_1400452A5
0x14004527f  lea     rax, [rdi+190h]
0x140045286  cmp     [rax], rax
0x140045289  jnz     short loc_1400452A5
0x14004528b  lea     rax, [rdi+170h]
0x140045292  cmp     [rax], rax
0x140045295  jnz     short loc_1400452A5
0x140045297  mov     r14d, [rdi+23Ch]
0x14004529e  mov     byte ptr [rdi+253h], 1
0x1400452a5  test    rsi, rsi
0x1400452a8  jz      short loc_1400452B0
0x1400452aa  xor     eax, eax
0x1400452ac  mov     [rsi+42h], ax
0x1400452b0  mov     dl, bpl; OldIrql
0x1400452b3  mov     rcx, r13; SpinLock
0x1400452b6  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400452bd  nop     dword ptr [rax+rax+00h]
0x1400452c2  test    rsi, rsi
0x1400452c5  jz      loc_1400454F4
0x1400452cb  lock inc dword ptr [rdi+240h]
0x1400452d2  lea     rcx, [rsi+48h]; BitMapHeader
0x1400452d6  call    cs:__imp_RtlNumberOfSetBits
0x1400452dd  nop     dword ptr [rax+rax+00h]
0x1400452e2  mov     r12d, eax
0x1400452e5  test    eax, eax
0x1400452e7  jnz     short loc_14004532E
0x1400452e9  mov     rcx, r13; SpinLock
0x1400452ec  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400452f3  nop     dword ptr [rax+rax+00h]
0x1400452f8  mov     r8d, r14d; int
0x1400452fb  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x1400452fe  mov     rcx, rdi; this
0x140045301  mov     bl, al
0x140045303  call    ?CompleteDestage@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@J@Z; SIO_CACHE::CompleteDestage(SIO_CACHE_LINE *,long)
0x140045308  mov     dl, bl; OldIrql
0x14004530a  mov     rcx, r13; SpinLock
0x14004530d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140045314  nop     dword ptr [rax+rax+00h]
0x140045319  jmp     loc_1400454BF
0x14004531e  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x140045321  mov     rcx, rdi; this
0x140045324  call    ?QueueLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLine(SIO_CACHE_LINE *)
0x140045329  jmp     loc_1400452A5
0x14004532e  mov     ecx, 128h; NumberOfBytes
0x140045333  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x140045338  test    rax, rax
0x14004533b  jz      loc_1400454EA
0x140045341  mov     rcx, rax; this
0x140045344  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x140045349  mov     rbp, rax
0x14004534c  mov     rbx, rax
0x14004534f  test    rax, rax
0x140045352  jz      loc_1400454EC
0x140045358  mov     r9d, [rdi+1D8h]
0x14004535f  lea     rcx, [rax+70h]
0x140045363  xor     r8d, r8d
0x140045366  lea     edx, [r8+3]
0x14004536a  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004536f  mov     r14d, eax
0x140045372  test    eax, eax
0x140045374  js      loc_1400454F6
0x14004537a  mov     [rbx+80h], rsi
0x140045381  mov     rcx, [rsi+20h]
0x140045385  mov     [rbx+88h], rcx
0x14004538c  mov     ecx, [rdi+1D8h]
0x140045392  mov     [rbx+90h], ecx
0x140045398  mov     byte ptr [rbx+0A8h], 3
0x14004539f  mov     byte ptr [rbx+0AAh], 16h
0x1400453a6  mov     rcx, [rdi+8]
0x1400453aa  mov     rcx, [rcx+80h]; this
0x1400453b1  test    rcx, rcx
0x1400453b4  jz      short loc_1400453CA
0x1400453b6  mov     r8d, [rdi+1D8h]; unsigned __int64
0x1400453bd  mov     rdx, [rsi+20h]; unsigned __int64
0x1400453c1  call    ?IsValid@SIO_VDT@@QEAAE_K0@Z; SIO_VDT::IsValid(unsigned __int64,unsigned __int64)
0x1400453c6  mov     bl, al
0x1400453c8  jmp     short loc_1400453CC
0x1400453ca  mov     bl, 1
0x1400453cc  mov     rax, [rsp+88h+var_50]
0x1400453d1  mov     rdx, [rsi+20h]
0x1400453d5  mov     rcx, [rax+188h]
0x1400453dc  mov     rax, [rcx]
0x1400453df  mov     rax, [rax+68h]
0x1400453e3  call    _guard_dispatch_icall
0x1400453e8  test    rax, rax
0x1400453eb  jnz     short loc_140045400
0x1400453ed  mov     rdx, [rdi+8]
0x1400453f1  xor     ecx, ecx
0x1400453f3  movzx   ebx, bl
0x1400453f6  cmp     [rdx+80h], rcx
0x1400453fd  cmovnz  ebx, ecx
0x140045400  mov     dword ptr [rbp+120h], 1
0x14004540a  test    bl, bl
0x14004540c  jnz     short loc_140045418
0x14004540e  mov     dword ptr [rbp+120h], 2
0x140045418  test    rax, rax
0x14004541b  jnz     short loc_140045431
0x14004541d  mov     [rsp+88h+arg_0], 1
0x140045425  mov     dword ptr [rbp+0B4h], 0C0E70014h
0x14004542f  jmp     short loc_1400454AF
0x140045431  mov     rcx, rax; this
0x140045434  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x140045439  cmp     dword ptr [rax], 3
0x14004543c  jnz     short loc_1400454AF
0x14004543e  test    bl, bl
0x140045440  jz      short loc_1400454AF
0x140045442  cmp     r12d, [rsi+48h]
0x140045446  jz      short loc_1400454A5
0x140045448  cmp     byte ptr [rdi+260h], 0
0x14004544f  jz      short loc_140045458
0x140045451  mov     eax, 3
0x140045456  jmp     short loc_14004549D
0x140045458  mov     rax, [rdi+8]
0x14004545c  cmp     byte ptr [rax+99h], 0
0x140045463  jz      short loc_14004548C
0x140045465  mov     rdx, [rsi+20h]; unsigned __int64
0x140045469  lea     r8, [rsp+88h+var_60]; struct SIO_CACHE_LINE **
0x14004546e  mov     rcx, rdi; this
0x140045471  call    ?AllocateParityLine@SIO_CACHE@@IEAAJ_KPEAPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::AllocateParityLine(unsigned __int64,SIO_CACHE_LINE * *)
0x140045476  mov     r14d, eax
0x140045479  mov     rbx, rbp
0x14004547c  test    eax, eax
0x14004547e  js      short loc_1400454F6
0x140045480  mov     rax, [rsp+88h+var_60]
0x140045485  mov     [rsp+88h+var_58], rax
0x14004548a  jmp     short loc_140045491
0x14004548c  mov     rax, [rsp+88h+var_58]
0x140045491  mov     [rbp+118h], rax
0x140045498  mov     eax, 5
0x14004549d  mov     [rbp+120h], eax
0x1400454a3  jmp     short loc_1400454AF
0x1400454a5  mov     dword ptr [rbp+120h], 2
0x1400454af  mov     rcx, [rsp+88h+arg_8]; this
0x1400454b7  mov     rdx, rbp; struct SIO_CACHE_PACKET *
0x1400454ba  call    ?AttachDestage@SIO_CACHE_PACKET@@QEAAXPEAV1@@Z; SIO_CACHE_PACKET::AttachDestage(SIO_CACHE_PACKET *)
0x1400454bf  mov     r12d, [rsp+88h+arg_18]
0x1400454c7  xor     ebx, ebx
0x1400454c9  inc     r12d
0x1400454cc  cmp     r12d, [rsp+88h+var_68]
0x1400454d1  mov     [rsp+88h+arg_18], r12d
0x1400454d9  lea     r12, [rdi+160h]
0x1400454e0  jb      loc_14004520E
0x1400454e6  mov     esi, ebx
0x1400454e8  jmp     short loc_1400454F6
0x1400454ea  xor     ebx, ebx
0x1400454ec  mov     r14d, 0C000009Ah
0x1400454f2  jmp     short loc_1400454F6
0x1400454f4  xor     ebx, ebx
0x1400454f6  mov     r12b, [rsp+88h+arg_0]
0x1400454fe  mov     r13, [rsp+88h+arg_8]
0x140045506  mov     r8d, r14d
0x140045509  mov     edx, 8
0x14004550e  mov     rcx, rdi
0x140045511  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x140045516  test    rsi, rsi
0x140045519  jz      short loc_140045559
0x14004551b  lea     rbp, [rdi+158h]
0x140045522  mov     rcx, rbp; SpinLock
0x140045525  call    cs:__imp_ExAcquireSpinLockExclusive
0x14004552c  nop     dword ptr [rax+rax+00h]
0x140045531  mov     r15b, al
0x140045534  test    r14d, r14d
0x140045537  jns     short loc_140045547
0x140045539  mov     r8d, r14d; int
0x14004553c  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x14004553f  mov     rcx, rdi; this
0x140045542  call    ?CompleteDestage@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@J@Z; SIO_CACHE::CompleteDestage(SIO_CACHE_LINE *,long)
0x140045547  mov     dl, r15b; OldIrql
0x14004554a  mov     rcx, rbp; SpinLock
0x14004554d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140045554  nop     dword ptr [rax+rax+00h]
0x140045559  test    rbx, rbx
0x14004555c  jz      short loc_140045571
0x14004555e  mov     rax, [rbx]
0x140045561  mov     edx, 1
0x140045566  mov     rcx, rbx
0x140045569  mov     rax, [rax]
0x14004556c  call    _guard_dispatch_icall
0x140045571  xor     eax, eax
0x140045573  lea     rcx, [r13+108h]
0x14004557a  cmp     [rcx], rcx
0x14004557d  mov     ecx, 0C0E70014h
0x140045582  cmovz   eax, r14d
0x140045586  test    r12b, r12b
0x140045589  cmovnz  eax, ecx
0x14004558c  add     rsp, 48h
0x140045590  pop     r15
0x140045592  pop     r14
0x140045594  pop     r13
0x140045596  pop     r12
0x140045598  pop     rdi
0x140045599  pop     rsi
0x14004559a  pop     rbp
0x14004559b  pop     rbx
0x14004559c  retn
```
