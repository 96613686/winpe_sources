# SIO_CACHE::BuildDestagePackets(SIO_CACHE_PACKET *)

- ea: `0x140045234`
- end: `0x14004565e`
- name: `?BuildDestagePackets@SIO_CACHE@@IEAAJPEAVSIO_CACHE_PACKET@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SIO_CACHE_PACKET *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400443c8`

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
- `0x1400441f8`
- `0x140045234`
- `0x140046774`
- `0x140046f1c`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140045376`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400453cd`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004560d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140045376`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400453cd`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004560d`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400452d1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400453ac`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400455e5`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400452d1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400453ac`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400455e5`
- `ntoskrnl!RtlNumberOfSetBits` at `0x140045396`
- `ntoskrnl!RtlNumberOfSetBits` at `0x140045396`

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
0x140045234  mov     [rsp+arg_8], rdx
0x140045239  push    rbx
0x14004523a  push    rbp
0x14004523b  push    rsi
0x14004523c  push    rdi
0x14004523d  push    r12
0x14004523f  push    r13
0x140045241  push    r14
0x140045243  push    r15
0x140045245  sub     rsp, 48h
0x140045249  xor     eax, eax
0x14004524b  mov     rdi, rcx
0x14004524e  mov     rcx, [rcx+8]
0x140045252  xor     r12b, r12b
0x140045255  mov     [rsp+88h+var_58], rax
0x14004525a  mov     r13, rdx
0x14004525d  mov     [rsp+88h+var_60], rax
0x140045262  xor     ebx, ebx
0x140045264  xor     esi, esi
0x140045266  mov     [rsp+88h+arg_0], r12b
0x14004526e  mov     rax, [rcx]
0x140045271  mov     rax, [rax+50h]
0x140045275  call    _guard_dispatch_icall
0x14004527a  xor     r14d, r14d
0x14004527d  mov     [rsp+88h+var_50], rax
0x140045282  cmp     [rdi+253h], bl
0x140045288  jnz     loc_1400455C6
0x14004528e  mov     rcx, rdi; this
0x140045291  call    ?GetUsedPercentage@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetUsedPercentage(void)
0x140045296  test    eax, eax
0x140045298  jz      loc_1400455C6
0x14004529e  mov     rcx, rdi; this
0x1400452a1  mov     [rsp+88h+arg_10], bl
0x1400452a8  call    ?GetDestageQueueDepth@SIO_CACHE@@QEAAKXZ; SIO_CACHE::GetDestageQueueDepth(void)
0x1400452ad  mov     [rsp+88h+var_68], eax
0x1400452b1  mov     [rsp+88h+arg_18], ebx
0x1400452b8  test    eax, eax
0x1400452ba  jz      loc_1400455C6
0x1400452c0  lea     r13, [rdi+158h]
0x1400452c7  lea     r12, [rdi+160h]
0x1400452ce  mov     rcx, r13; SpinLock
0x1400452d1  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400452d8  nop     dword ptr [rax+rax+00h]
0x1400452dd  mov     rbx, [r12]
0x1400452e1  mov     bpl, al
0x1400452e4  mov     r15, [rbx]
0x1400452e7  jmp     short loc_140045325
0x1400452e9  test    byte ptr [rbx+40h], 4
0x1400452ed  jnz     short loc_14004531F
0x1400452ef  movzx   eax, word ptr [rdi+250h]
0x1400452f6  cmp     [rbx+42h], ax
0x1400452fa  jz      short loc_14004531F
0x1400452fc  mov     rdx, [rdi+230h]; __int64
0x140045303  lea     rcx, [rbx+30h]; this
0x140045307  mov     rsi, rbx
0x14004530a  mov     [rsp+88h+arg_10], 1
0x140045312  call    ?MarkDestaging@SIO_CACHE_STATE@@QEAAE_J@Z; SIO_CACHE_STATE::MarkDestaging(__int64)
0x140045317  test    al, al
0x140045319  jnz     loc_1400453DE
0x14004531f  mov     rbx, r15
0x140045322  mov     r15, [r15]
0x140045325  xor     esi, esi
0x140045327  cmp     rbx, r12
0x14004532a  jnz     short loc_1400452E9
0x14004532c  cmp     [rsp+88h+arg_10], sil
0x140045334  jnz     short loc_140045365
0x140045336  cmp     [rdi+252h], sil
0x14004533d  jz      short loc_140045365
0x14004533f  lea     rax, [rdi+190h]
0x140045346  cmp     [rax], rax
0x140045349  jnz     short loc_140045365
0x14004534b  lea     rax, [rdi+170h]
0x140045352  cmp     [rax], rax
0x140045355  jnz     short loc_140045365
0x140045357  mov     r14d, [rdi+23Ch]
0x14004535e  mov     byte ptr [rdi+253h], 1
0x140045365  test    rsi, rsi
0x140045368  jz      short loc_140045370
0x14004536a  xor     eax, eax
0x14004536c  mov     [rsi+42h], ax
0x140045370  mov     dl, bpl; OldIrql
0x140045373  mov     rcx, r13; SpinLock
0x140045376  call    cs:__imp_ExReleaseSpinLockExclusive
0x14004537d  nop     dword ptr [rax+rax+00h]
0x140045382  test    rsi, rsi
0x140045385  jz      loc_1400455B4
0x14004538b  lock inc dword ptr [rdi+240h]
0x140045392  lea     rcx, [rsi+48h]; BitMapHeader
0x140045396  call    cs:__imp_RtlNumberOfSetBits
0x14004539d  nop     dword ptr [rax+rax+00h]
0x1400453a2  mov     r12d, eax
0x1400453a5  test    eax, eax
0x1400453a7  jnz     short loc_1400453EE
0x1400453a9  mov     rcx, r13; SpinLock
0x1400453ac  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400453b3  nop     dword ptr [rax+rax+00h]
0x1400453b8  mov     r8d, r14d; int
0x1400453bb  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x1400453be  mov     rcx, rdi; this
0x1400453c1  mov     bl, al
0x1400453c3  call    ?CompleteDestage@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@J@Z; SIO_CACHE::CompleteDestage(SIO_CACHE_LINE *,long)
0x1400453c8  mov     dl, bl; OldIrql
0x1400453ca  mov     rcx, r13; SpinLock
0x1400453cd  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400453d4  nop     dword ptr [rax+rax+00h]
0x1400453d9  jmp     loc_14004557F
0x1400453de  mov     rdx, rbx; struct SIO_CACHE_LINE *
0x1400453e1  mov     rcx, rdi; this
0x1400453e4  call    ?QueueLine@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::QueueLine(SIO_CACHE_LINE *)
0x1400453e9  jmp     loc_140045365
0x1400453ee  mov     ecx, 128h; NumberOfBytes
0x1400453f3  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x1400453f8  test    rax, rax
0x1400453fb  jz      loc_1400455AA
0x140045401  mov     rcx, rax; this
0x140045404  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x140045409  mov     rbp, rax
0x14004540c  mov     rbx, rax
0x14004540f  test    rax, rax
0x140045412  jz      loc_1400455AC
0x140045418  mov     r9d, [rdi+1D8h]
0x14004541f  lea     rcx, [rax+70h]
0x140045423  xor     r8d, r8d
0x140045426  lea     edx, [r8+3]
0x14004542a  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004542f  mov     r14d, eax
0x140045432  test    eax, eax
0x140045434  js      loc_1400455B6
0x14004543a  mov     [rbx+80h], rsi
0x140045441  mov     rcx, [rsi+20h]
0x140045445  mov     [rbx+88h], rcx
0x14004544c  mov     ecx, [rdi+1D8h]
0x140045452  mov     [rbx+90h], ecx
0x140045458  mov     byte ptr [rbx+0A8h], 3
0x14004545f  mov     byte ptr [rbx+0AAh], 16h
0x140045466  mov     rcx, [rdi+8]
0x14004546a  mov     rcx, [rcx+80h]; this
0x140045471  test    rcx, rcx
0x140045474  jz      short loc_14004548A
0x140045476  mov     r8d, [rdi+1D8h]; unsigned __int64
0x14004547d  mov     rdx, [rsi+20h]; unsigned __int64
0x140045481  call    ?IsValid@SIO_VDT@@QEAAE_K0@Z; SIO_VDT::IsValid(unsigned __int64,unsigned __int64)
0x140045486  mov     bl, al
0x140045488  jmp     short loc_14004548C
0x14004548a  mov     bl, 1
0x14004548c  mov     rax, [rsp+88h+var_50]
0x140045491  mov     rdx, [rsi+20h]
0x140045495  mov     rcx, [rax+188h]
0x14004549c  mov     rax, [rcx]
0x14004549f  mov     rax, [rax+68h]
0x1400454a3  call    _guard_dispatch_icall
0x1400454a8  test    rax, rax
0x1400454ab  jnz     short loc_1400454C0
0x1400454ad  mov     rdx, [rdi+8]
0x1400454b1  xor     ecx, ecx
0x1400454b3  movzx   ebx, bl
0x1400454b6  cmp     [rdx+80h], rcx
0x1400454bd  cmovnz  ebx, ecx
0x1400454c0  mov     dword ptr [rbp+120h], 1
0x1400454ca  test    bl, bl
0x1400454cc  jnz     short loc_1400454D8
0x1400454ce  mov     dword ptr [rbp+120h], 2
0x1400454d8  test    rax, rax
0x1400454db  jnz     short loc_1400454F1
0x1400454dd  mov     [rsp+88h+arg_0], 1
0x1400454e5  mov     dword ptr [rbp+0B4h], 0C0E70014h
0x1400454ef  jmp     short loc_14004556F
0x1400454f1  mov     rcx, rax; this
0x1400454f4  call    ?Resiliency@SIO_RAID@@UEAAPEAVSP_RESILIENCY_INFO@@XZ; SIO_RAID::Resiliency(void)
0x1400454f9  cmp     dword ptr [rax], 3
0x1400454fc  jnz     short loc_14004556F
0x1400454fe  test    bl, bl
0x140045500  jz      short loc_14004556F
0x140045502  cmp     r12d, [rsi+48h]
0x140045506  jz      short loc_140045565
0x140045508  cmp     byte ptr [rdi+260h], 0
0x14004550f  jz      short loc_140045518
0x140045511  mov     eax, 3
0x140045516  jmp     short loc_14004555D
0x140045518  mov     rax, [rdi+8]
0x14004551c  cmp     byte ptr [rax+99h], 0
0x140045523  jz      short loc_14004554C
0x140045525  mov     rdx, [rsi+20h]; unsigned __int64
0x140045529  lea     r8, [rsp+88h+var_60]; struct SIO_CACHE_LINE **
0x14004552e  mov     rcx, rdi; this
0x140045531  call    ?AllocateParityLine@SIO_CACHE@@IEAAJ_KPEAPEAVSIO_CACHE_LINE@@@Z; SIO_CACHE::AllocateParityLine(unsigned __int64,SIO_CACHE_LINE * *)
0x140045536  mov     r14d, eax
0x140045539  mov     rbx, rbp
0x14004553c  test    eax, eax
0x14004553e  js      short loc_1400455B6
0x140045540  mov     rax, [rsp+88h+var_60]
0x140045545  mov     [rsp+88h+var_58], rax
0x14004554a  jmp     short loc_140045551
0x14004554c  mov     rax, [rsp+88h+var_58]
0x140045551  mov     [rbp+118h], rax
0x140045558  mov     eax, 5
0x14004555d  mov     [rbp+120h], eax
0x140045563  jmp     short loc_14004556F
0x140045565  mov     dword ptr [rbp+120h], 2
0x14004556f  mov     rcx, [rsp+88h+arg_8]; this
0x140045577  mov     rdx, rbp; struct SIO_CACHE_PACKET *
0x14004557a  call    ?AttachDestage@SIO_CACHE_PACKET@@QEAAXPEAV1@@Z; SIO_CACHE_PACKET::AttachDestage(SIO_CACHE_PACKET *)
0x14004557f  mov     r12d, [rsp+88h+arg_18]
0x140045587  xor     ebx, ebx
0x140045589  inc     r12d
0x14004558c  cmp     r12d, [rsp+88h+var_68]
0x140045591  mov     [rsp+88h+arg_18], r12d
0x140045599  lea     r12, [rdi+160h]
0x1400455a0  jb      loc_1400452CE
0x1400455a6  mov     esi, ebx
0x1400455a8  jmp     short loc_1400455B6
0x1400455aa  xor     ebx, ebx
0x1400455ac  mov     r14d, 0C000009Ah
0x1400455b2  jmp     short loc_1400455B6
0x1400455b4  xor     ebx, ebx
0x1400455b6  mov     r12b, [rsp+88h+arg_0]
0x1400455be  mov     r13, [rsp+88h+arg_8]
0x1400455c6  mov     r8d, r14d
0x1400455c9  mov     edx, 8
0x1400455ce  mov     rcx, rdi
0x1400455d1  call    ?LogStatus@SIO_CACHE@@IEAAXW4SIO_CACHE_OPERATION@@J@Z; SIO_CACHE::LogStatus(SIO_CACHE_OPERATION,long)
0x1400455d6  test    rsi, rsi
0x1400455d9  jz      short loc_140045619
0x1400455db  lea     rbp, [rdi+158h]
0x1400455e2  mov     rcx, rbp; SpinLock
0x1400455e5  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400455ec  nop     dword ptr [rax+rax+00h]
0x1400455f1  mov     r15b, al
0x1400455f4  test    r14d, r14d
0x1400455f7  jns     short loc_140045607
0x1400455f9  mov     r8d, r14d; int
0x1400455fc  mov     rdx, rsi; struct SIO_CACHE_LINE *
0x1400455ff  mov     rcx, rdi; this
0x140045602  call    ?CompleteDestage@SIO_CACHE@@IEAAXPEAVSIO_CACHE_LINE@@J@Z; SIO_CACHE::CompleteDestage(SIO_CACHE_LINE *,long)
0x140045607  mov     dl, r15b; OldIrql
0x14004560a  mov     rcx, rbp; SpinLock
0x14004560d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140045614  nop     dword ptr [rax+rax+00h]
0x140045619  test    rbx, rbx
0x14004561c  jz      short loc_140045631
0x14004561e  mov     rax, [rbx]
0x140045621  mov     edx, 1
0x140045626  mov     rcx, rbx
0x140045629  mov     rax, [rax]
0x14004562c  call    _guard_dispatch_icall
0x140045631  xor     eax, eax
0x140045633  lea     rcx, [r13+108h]
0x14004563a  cmp     [rcx], rcx
0x14004563d  mov     ecx, 0C0E70014h
0x140045642  cmovz   eax, r14d
0x140045646  test    r12b, r12b
0x140045649  cmovnz  eax, ecx
0x14004564c  add     rsp, 48h
0x140045650  pop     r15
0x140045652  pop     r14
0x140045654  pop     r13
0x140045656  pop     r12
0x140045658  pop     rdi
0x140045659  pop     rsi
0x14004565a  pop     rbp
0x14004565b  pop     rbx
0x14004565c  retn
```
