# SqospStartJob

- ea: `0x140001380`
- end: `0x14000192c`
- name: `SqospStartJob`
- size: `1452`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400142c0`
- `0x140014950`

## callees

- `0x140001380`
- `0x140001940`
- `0x140002f90`
- `0x1400031a0`
- `0x140004610`
- `0x1400056e0`
- `0x140007238`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400013f2`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400013f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000156d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016df`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000156d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016df`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400013de`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400013de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000150a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000150a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016a8`
- `HAL!KeQueryPerformanceCounter` at `0x1400013a4`
- `HAL!KeQueryPerformanceCounter` at `0x1400013a4`
- `FLTMGR!FltReferenceContext` at `0x1400013b6`
- `FLTMGR!FltReferenceContext` at `0x1400013b6`

## pseudocode

```c
__int64 __fastcall SqospStartJob(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // rdi
  LARGE_INTEGER PerformanceCounter; // rsi
  __int64 v5; // rdx
  char v6; // al
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // r12
  __int64 v11; // rbp
  __int64 *v12; // rdx
  __int64 v13; // r14
  __int64 v14; // rdi
  unsigned __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  char v18; // dl
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // r14
  bool v23; // cf
  __int64 v24; // rax
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // rtt
  unsigned __int64 v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // edi
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // rcx
  _QWORD v36[2]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int64 v37; // [rsp+30h] [rbp-38h]
  __int16 v38; // [rsp+38h] [rbp-30h]
  char v39; // [rsp+3Ah] [rbp-2Eh]
  int v40; // [rsp+3Bh] [rbp-2Dh]
  char v41; // [rsp+3Fh] [rbp-29h]

  v1 = *(_QWORD *)(a1 + 32);
  v40 = 0;
  v41 = 0;
  v3 = *(void **)(v1 + 8);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  FltReferenceContext(v3);
  v36[0] = v3;
  v36[1] = &Object;
  v38 = 0;
  v39 = 0;
  if ( KeGetCurrentIrql() > 1u || KeAreAllApcsDisabled() )
    v37 = 0;
  else
    v37 = qword_14000D1D0 + ((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6);
  *(LARGE_INTEGER *)(a1 + 160) = PerformanceCounter;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  v5 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
  v6 = *(_BYTE *)(v5 + 4);
  if ( v6 == 4 )
  {
    *(_QWORD *)(a1 + 136) = *(_QWORD *)(v5 + 40);
    v7 = *(unsigned int *)(v5 + 24);
    goto LABEL_7;
  }
  if ( v6 == 3 )
  {
    *(_QWORD *)(a1 + 136) = *(_QWORD *)(v5 + 40);
    v7 = *(unsigned int *)(v5 + 24);
LABEL_7:
    *(_QWORD *)(a1 + 144) = v7;
    goto LABEL_8;
  }
  v7 = 0;
  if ( v6 == 13 )
  {
    if ( *(_DWORD *)(v5 + 40) == 623208 )
    {
      v33 = *(_QWORD *)(v5 + 48);
      *(_QWORD *)(a1 + 136) = *(_QWORD *)(v33 + 8);
      v7 = *(_QWORD *)(v33 + 16);
      *(_QWORD *)(a1 + 144) = v7;
    }
    if ( *(_DWORD *)(v5 + 40) == 622792 )
    {
      v34 = *(_QWORD **)(v5 + 48);
      *(_QWORD *)(a1 + 136) = *v34;
      v7 = v34[1] - *v34;
      goto LABEL_7;
    }
  }
LABEL_8:
  v8 = *(_QWORD **)(a1 + 40);
  if ( *(_BYTE *)(v8[1] + 126LL) && v7 && (v8[57] || v8[58]) && !(unsigned __int8)SqospLimiterStartJobInternal(a1, v36) )
  {
    v32 = 2;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))SqospProcessJobDispatcherContext)(
      v36,
      0,
      (LARGE_INTEGER)PerformanceCounter.QuadPart);
  }
  else
  {
    v9 = *(_QWORD *)(a1 + 40);
    v10 = *(_QWORD *)(a1 + 160);
    v11 = *(_QWORD *)v9;
    *(_BYTE *)(a1 + 128) = 1;
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 200));
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 4136));
    v12 = *(__int64 **)(a1 + 40);
    v13 = *(_QWORD *)(a1 + 144);
    v14 = *v12;
    if ( v13 )
    {
      v15 = (unsigned __int64)(v13 + 511) >> 9;
      v16 = a1;
      _InterlockedExchange64(
        v12 + 32,
        (*(_QWORD *)(a1 + 136) >> 9) - _InterlockedExchange64(v12 + 31, v15 + (*(_QWORD *)(a1 + 136) >> 9)));
      v17 = 127;
      v18 = 1;
    }
    else
    {
      v15 = 0;
      v18 = 0;
      v17 = a1;
      v16 = 127;
    }
    *(_BYTE *)(v16 + v17) = v18;
    *(_BYTE *)(v14 + 1096) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v14 + 1088));
    v19 = *(_QWORD *)(v14 + 1224);
    if ( v19 )
      v20 = *(_QWORD *)(v14 + 1120) + *(_QWORD *)(v14 + 1144) * *(_QWORD *)(v14 + 1248) / v19;
    else
      v20 = *(_QWORD *)(v14 + 1120);
    if ( *(_BYTE *)(a1 + 127) )
      v20 += *(_QWORD *)(v14 + 1128);
    v21 = v20 + *(_QWORD *)(v14 + 1136) * v15;
    KeReleaseSpinLock((PKSPIN_LOCK)(v14 + 1088), *(_BYTE *)(v14 + 1096));
    if ( v21 > 0 )
    {
      if ( (unsigned __int64)v21 > 0xEE6B2800 )
        v21 = 4000000000LL;
    }
    else
    {
      v21 = 1;
    }
    *(_QWORD *)(a1 + 152) = v21;
    if ( v10 >= qword_14000D2C0 + *(_QWORD *)(v11 + 3016)
      && !_interlockedbittestandset((volatile signed __int32 *)(v11 + 2936), 0) )
    {
      BalanceCollectThroughputSample(v11, v10, v11 + 3016);
      if ( v10 - *(_QWORD *)(v11 + 2944) >= qword_14000D320 )
      {
        v23 = *(_DWORD *)(v11 + 2932) < 0x14u;
        *(_QWORD *)(v11 + 2944) = v10;
        if ( !v23 && *(_DWORD *)(v11 + 4008) >= 0x14u )
        {
          v24 = *(_QWORD *)(v11 + 2976);
          if ( v24 )
            BalanceComputeThroughputFunction(
              v11 + 3016,
              v24 * (unsigned __int64)(unsigned int)dword_14000D2E4 / 0x64,
              *(_QWORD *)(v11 + 2960));
        }
        *(_BYTE *)(v11 + 1096) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 1088));
        if ( (unsigned __int8)SqospAreExternalDeviceCostEstimatesValid(v11) )
        {
          v25 = *(_QWORD *)(v11 + 960);
        }
        else if ( *(_QWORD *)(v11 + 4032) && *(_DWORD *)(v11 + 920) )
        {
          v35 = *(_QWORD *)(v11 + 1112);
          if ( !v35 )
            v35 = *(_QWORD *)(v11 + 960);
          v25 = (unsigned __int64)(v35 + *(_QWORD *)(v11 + 4032)) >> 1;
          *(_QWORD *)(v11 + 1112) = v25;
        }
        else
        {
          v25 = qword_14000D2D0;
          *(_QWORD *)(v11 + 1112) = qword_14000D2D0;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 1088), *(_BYTE *)(v11 + 1096));
        v26 = qword_14000D2D8;
        if ( v25 >= qword_14000D2D8 )
        {
          v26 = v25;
          if ( v25 > qword_14000D2D0 )
            v26 = qword_14000D2D0;
        }
        v27 = v26 >> 1;
        v28 = *(_QWORD *)(v11 + 4064) - *(_QWORD *)(v11 + 2992);
        *(_QWORD *)(v11 + 2992) = *(_QWORD *)(v11 + 4064);
        if ( v28 )
        {
          v29 = *(_QWORD *)(v11 + 4152) - *(_QWORD *)(v11 + 2984);
          *(_QWORD *)(v11 + 2984) = *(_QWORD *)(v11 + 4152);
          v30 = (qword_14000D298 * (v29 / v28)) >> 16;
        }
        else
        {
          v30 = 0;
        }
        if ( 100 * v30 <= v27 )
          _interlockedbittestandreset((volatile signed __int32 *)(v11 + 2936), 1u);
        else
          _interlockedbittestandset((volatile signed __int32 *)(v11 + 2936), 1u);
        if ( *(_DWORD *)(v11 + 924) )
        {
          *(_QWORD *)(v11 + 3000) = v27;
          *(_QWORD *)(v11 + 3008) = 100 * v30;
        }
      }
      _interlockedbittestandreset((volatile signed __int32 *)(v11 + 2936), 0);
    }
    if ( *(_DWORD *)(v11 + 1152) == 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 1152), 4, 3) == 3 )
      BalanceUpdateCostEstimatesInternal(v11, v10);
    if ( (*(_DWORD *)(v11 + 2936) & 2) == 0 )
    {
      *(LARGE_INTEGER *)(a1 + 168) = PerformanceCounter;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))SqospProcessJobDispatcherContext)(
        v36,
        0,
        (LARGE_INTEGER)PerformanceCounter.QuadPart);
      return 0;
    }
    v31 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SqospProcessJobDispatcherContext)(
            v36,
            a1,
            (LARGE_INTEGER)PerformanceCounter.QuadPart);
    v32 = 2;
    if ( a1 )
      return v31;
  }
  return v32;
}

```

## disassembly

```asm
0x140001380  push    rbx
0x140001382  push    rsi
0x140001383  push    rdi
0x140001384  push    r13
0x140001386  sub     rsp, 48h
0x14000138a  mov     rax, [rcx+20h]
0x14000138e  mov     rbx, rcx
0x140001391  xor     r13d, r13d
0x140001394  xor     ecx, ecx; PerformanceFrequency
0x140001396  mov     [rsp+68h+var_2D], r13d
0x14000139b  mov     [rsp+68h+var_29], r13b
0x1400013a0  mov     rdi, [rax+8]
0x1400013a4  call    cs:__imp_KeQueryPerformanceCounter
0x1400013ab  nop     dword ptr [rax+rax+00h]
0x1400013b0  mov     rcx, rdi; Context
0x1400013b3  mov     rsi, rax
0x1400013b6  call    cs:__imp_FltReferenceContext
0x1400013bd  nop     dword ptr [rax+rax+00h]
0x1400013c2  lea     rax, Object
0x1400013c9  mov     [rsp+68h+var_48], rdi
0x1400013ce  mov     [rsp+68h+var_40], rax
0x1400013d3  mov     [rsp+68h+var_30], r13w
0x1400013d9  mov     [rsp+68h+var_2E], r13b
0x1400013de  call    cs:__imp_KeGetCurrentIrql
0x1400013e5  nop     dword ptr [rax+rax+00h]
0x1400013ea  cmp     al, 1
0x1400013ec  ja      loc_1400017C7
0x1400013f2  call    cs:__imp_KeAreAllApcsDisabled
0x1400013f9  nop     dword ptr [rax+rax+00h]
0x1400013fe  test    al, al
0x140001400  jnz     loc_1400017C7
0x140001406  mov     eax, gs:1A4h
0x14000140e  mov     ecx, eax
0x140001410  shl     rcx, 6
0x140001414  add     rcx, cs:qword_14000D1D0
0x14000141b  mov     [rsp+68h+var_38], rcx
0x140001420  mov     [rbx+0A0h], rsi
0x140001427  mov     [rbx+88h], r13
0x14000142e  mov     [rbx+90h], r13
0x140001435  mov     rax, [rbx]
0x140001438  mov     rdx, [rax+10h]
0x14000143c  movzx   eax, byte ptr [rdx+4]
0x140001440  cmp     al, 4
0x140001442  jz      loc_1400015FD
0x140001448  cmp     al, 3
0x14000144a  jnz     loc_1400017D1
0x140001450  mov     rax, [rdx+28h]
0x140001454  mov     [rbx+88h], rax
0x14000145b  mov     ecx, [rdx+18h]
0x14000145e  mov     [rbx+90h], rcx
0x140001465  mov     rdx, [rbx+28h]
0x140001469  mov     rax, [rdx+8]
0x14000146d  cmp     [rax+7Eh], r13b
0x140001471  jnz     loc_140001829
0x140001477  mov     rax, [rbx+28h]
0x14000147b  mov     [rsp+68h+arg_8], rbp
0x140001480  mov     [rsp+68h+arg_10], r12
0x140001488  mov     r12, [rbx+0A0h]
0x14000148f  mov     rbp, [rax]
0x140001492  mov     [rsp+68h+arg_18], r14
0x14000149a  mov     byte ptr [rbx+80h], 1
0x1400014a1  mov     [rsp+68h+var_28], r15
0x1400014a6  lock inc dword ptr [rax+0C8h]
0x1400014ad  lock inc dword ptr [rbp+1028h]
0x1400014b4  mov     rdx, [rbx+28h]
0x1400014b8  mov     r14, [rbx+90h]
0x1400014bf  mov     rdi, [rdx]
0x1400014c2  test    r14, r14
0x1400014c5  jz      loc_140001851
0x1400014cb  mov     rcx, [rbx+88h]
0x1400014d2  add     r14, 1FFh
0x1400014d9  shr     rcx, 9
0x1400014dd  shr     r14, 9
0x1400014e1  lea     rax, [r14+rcx]
0x1400014e5  xchg    rax, [rdx+0F8h]
0x1400014ec  sub     rcx, rax
0x1400014ef  mov     rax, rbx
0x1400014f2  xchg    rcx, [rdx+100h]
0x1400014f9  mov     ecx, 7Fh
0x1400014fe  mov     dl, 1
0x140001500  mov     [rax+rcx], dl
0x140001503  lea     rcx, [rdi+440h]; SpinLock
0x14000150a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001511  nop     dword ptr [rax+rax+00h]
0x140001516  mov     [rdi+448h], al
0x14000151c  mov     rcx, [rdi+4C8h]
0x140001523  mov     r8, [rdi+460h]
0x14000152a  test    rcx, rcx
0x14000152d  jz      loc_140001863
0x140001533  mov     rax, [rdi+4E0h]
0x14000153a  xor     edx, edx
0x14000153c  imul    rax, [rdi+478h]
0x140001544  div     rcx
0x140001547  add     rax, r8
0x14000154a  cmp     [rbx+7Fh], r13b
0x14000154e  jnz     loc_14000186B
0x140001554  imul    r14, [rdi+470h]
0x14000155c  movzx   edx, byte ptr [rdi+448h]; NewIrql
0x140001563  lea     rcx, [rdi+440h]; SpinLock
0x14000156a  add     r14, rax
0x14000156d  call    cs:__imp_KeReleaseSpinLock
0x140001574  nop     dword ptr [rax+rax+00h]
0x140001579  mov     r15, [rsp+68h+var_28]
0x14000157e  test    r14, r14
0x140001581  jg      loc_140001877
0x140001587  mov     r14d, 1
0x14000158d  mov     [rbx+98h], r14
0x140001594  mov     rcx, [rbp+0BC8h]
0x14000159b  add     rcx, cs:qword_14000D2C0
0x1400015a2  cmp     r12, rcx
0x1400015a5  jnb     short loc_140001610
0x1400015a7  mov     eax, [rbp+480h]
0x1400015ad  mov     r14, [rsp+68h+arg_18]
0x1400015b5  cmp     eax, 3
0x1400015b8  jz      loc_140001904
0x1400015be  mov     eax, [rbp+0B78h]
0x1400015c4  lea     rcx, [rsp+68h+var_48]
0x1400015c9  mov     r12, [rsp+68h+arg_10]
0x1400015d1  mov     r8, rsi
0x1400015d4  mov     rbp, [rsp+68h+arg_8]
0x1400015d9  test    al, 2
0x1400015db  jnz     loc_140001772
0x1400015e1  xor     edx, edx
0x1400015e3  mov     [rbx+0A8h], rsi
0x1400015ea  call    SqospProcessJobDispatcherContext
0x1400015ef  mov     eax, r13d
0x1400015f2  add     rsp, 48h
0x1400015f6  pop     r13
0x1400015f8  pop     rdi
0x1400015f9  pop     rsi
0x1400015fa  pop     rbx
0x1400015fb  retn
0x1400015fd  mov     rax, [rdx+28h]
0x140001601  mov     [rbx+88h], rax
0x140001608  mov     ecx, [rdx+18h]
0x14000160b  jmp     loc_14000145E
0x140001610  lock bts dword ptr [rbp+0B78h], 0
0x140001619  jb      short loc_1400015A7
0x14000161b  lea     r8, [rbp+0BC8h]
0x140001622  mov     rdx, r12
0x140001625  mov     rcx, rbp
0x140001628  call    BalanceCollectThroughputSample
0x14000162d  mov     rax, r12
0x140001630  sub     rax, [rbp+0B80h]
0x140001637  cmp     rax, cs:qword_14000D320
0x14000163e  jb      loc_140001764
0x140001644  cmp     dword ptr [rbp+0B74h], 14h
0x14000164b  mov     [rbp+0B80h], r12
0x140001652  jb      short loc_1400016A1
0x140001654  cmp     dword ptr [rbp+0FA8h], 14h
0x14000165b  jb      short loc_1400016A1
0x14000165d  mov     rax, [rbp+0BA0h]
0x140001664  test    rax, rax
0x140001667  jz      short loc_1400016A1
0x140001669  mov     r9d, cs:dword_14000D2E4
0x140001670  lea     rcx, [rbp+0BC8h]
0x140001677  mov     r8, [rbp+0B90h]
0x14000167e  imul    r9, rax
0x140001682  mov     rax, 47AE147AE147AE15h
0x14000168c  mul     r9
0x14000168f  sub     r9, rdx
0x140001692  shr     r9, 1
0x140001695  add     rdx, r9
0x140001698  shr     rdx, 6
0x14000169c  call    BalanceComputeThroughputFunction
0x1400016a1  lea     rcx, [rbp+440h]; SpinLock
0x1400016a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400016af  nop     dword ptr [rax+rax+00h]
0x1400016b4  mov     rcx, rbp
0x1400016b7  mov     [rbp+448h], al
0x1400016bd  call    SqospAreExternalDeviceCostEstimatesValid
0x1400016c2  test    al, al
0x1400016c4  jz      loc_140001888
0x1400016ca  mov     rdi, [rbp+3C0h]
0x1400016d1  movzx   edx, byte ptr [rbp+448h]; NewIrql
0x1400016d8  lea     rcx, [rbp+440h]; SpinLock
0x1400016df  call    cs:__imp_KeReleaseSpinLock
0x1400016e6  nop     dword ptr [rax+rax+00h]
0x1400016eb  mov     r8, cs:qword_14000D2D8
0x1400016f2  cmp     rdi, r8
0x1400016f5  jnb     loc_1400018DA
0x1400016fb  mov     rax, [rbp+0FE0h]
0x140001702  mov     r9, rax
0x140001705  shr     r8, 1
0x140001708  sub     r9, [rbp+0BB0h]
0x14000170f  mov     [rbp+0BB0h], rax
0x140001716  jz      loc_1400017B7
0x14000171c  mov     rcx, [rbp+1038h]
0x140001723  xor     edx, edx
0x140001725  mov     rax, rcx
0x140001728  sub     rax, [rbp+0BA8h]
0x14000172f  div     r9
0x140001732  mov     [rbp+0BA8h], rcx
0x140001739  imul    rax, cs:qword_14000D298
0x140001741  shr     rax, 10h
0x140001745  imul    rcx, rax, 64h ; 'd'
0x140001749  cmp     rcx, r8
0x14000174c  jbe     short loc_1400017BC
0x14000174e  lock bts dword ptr [rbp+0B78h], 1
0x140001757  cmp     [rbp+39Ch], r13d
0x14000175e  jnz     loc_1400018F1
0x140001764  lock btr dword ptr [rbp+0B78h], 0
0x14000176d  jmp     loc_1400015A7
0x140001772  mov     rdx, rbx
0x140001775  call    SqospProcessJobDispatcherContext
0x14000177a  test    rbx, rbx
0x14000177d  mov     edi, 2
0x140001782  cmovnz  edi, eax
0x140001785  jmp     short loc_1400017B0
0x140001787  lea     rdx, [rsp+68h+var_48]
0x14000178c  mov     rcx, rbx
0x14000178f  call    SqospLimiterStartJobInternal
0x140001794  test    al, al
0x140001796  jnz     loc_140001477
0x14000179c  mov     r8, rsi
0x14000179f  lea     rcx, [rsp+68h+var_48]
0x1400017a4  xor     edx, edx
0x1400017a6  mov     edi, 2
0x1400017ab  call    SqospProcessJobDispatcherContext
0x1400017b0  mov     eax, edi
0x1400017b2  jmp     loc_1400015F2
0x1400017b7  mov     rax, r13
0x1400017ba  jmp     short loc_140001745
0x1400017bc  lock btr dword ptr [rbp+0B78h], 1
0x1400017c5  jmp     short loc_140001757
0x1400017c7  mov     [rsp+68h+var_38], r13
0x1400017cc  jmp     loc_140001420
0x1400017d1  mov     rcx, r13
0x1400017d4  cmp     al, 0Dh
0x1400017d6  jnz     loc_140001465
0x1400017dc  cmp     dword ptr [rdx+28h], 98268h
0x1400017e3  jnz     short loc_1400017FF
0x1400017e5  mov     rcx, [rdx+30h]
0x1400017e9  mov     rax, [rcx+8]
0x1400017ed  mov     [rbx+88h], rax
0x1400017f4  mov     rcx, [rcx+10h]
0x1400017f8  mov     [rbx+90h], rcx
0x1400017ff  cmp     dword ptr [rdx+28h], 980C8h
0x140001806  jnz     loc_140001465
0x14000180c  mov     rcx, [rdx+30h]
0x140001810  mov     rax, [rcx]
0x140001813  mov     [rbx+88h], rax
0x14000181a  mov     rax, [rcx]
0x14000181d  mov     rcx, [rcx+8]
0x140001821  sub     rcx, rax
0x140001824  jmp     loc_14000145E
0x140001829  test    rcx, rcx
0x14000182c  jz      loc_140001477
0x140001832  cmp     [rdx+1C8h], r13
0x140001839  jnz     loc_140001787
0x14000183f  cmp     [rdx+1D0h], r13
0x140001846  jz      loc_140001477
0x14000184c  jmp     loc_140001787
0x140001851  mov     r14, r13
0x140001854  xor     dl, dl
0x140001856  mov     rcx, rbx
0x140001859  mov     eax, 7Fh
0x14000185e  jmp     loc_140001500
0x140001863  mov     rax, r8
0x140001866  jmp     loc_14000154A
0x14000186b  add     rax, [rdi+468h]
0x140001872  jmp     loc_140001554
0x140001877  mov     eax, 0EE6B2800h
0x14000187c  cmp     r14, rax
0x14000187f  cmova   r14, rax
0x140001883  jmp     loc_14000158D
0x140001888  cmp     [rbp+0FC0h], r13
0x14000188f  jz      short loc_1400018C7
0x140001891  mov     eax, [rbp+398h]
0x140001897  test    eax, eax
0x140001899  jz      short loc_1400018C7
0x14000189b  mov     rcx, [rbp+458h]
0x1400018a2  test    rcx, rcx
0x1400018a5  jnz     short loc_1400018AE
0x1400018a7  mov     rcx, [rbp+3C0h]
0x1400018ae  mov     rdi, [rbp+0FC0h]
0x1400018b5  add     rdi, rcx
0x1400018b8  shr     rdi, 1
0x1400018bb  mov     [rbp+458h], rdi
0x1400018c2  jmp     loc_1400016D1
0x1400018c7  mov     rdi, cs:qword_14000D2D0
0x1400018ce  mov     [rbp+458h], rdi
0x1400018d5  jmp     loc_1400016D1
0x1400018da  cmp     rdi, cs:qword_14000D2D0
0x1400018e1  mov     r8, rdi
0x1400018e4  cmova   r8, cs:qword_14000D2D0
0x1400018ec  jmp     loc_1400016FB
0x1400018f1  mov     [rbp+0BB8h], r8
0x1400018f8  mov     [rbp+0BC0h], rcx
0x1400018ff  jmp     loc_140001764
0x140001904  mov     ecx, 4
0x140001909  mov     eax, 3
0x14000190e  lock cmpxchg [rbp+480h], ecx
0x140001916  jnz     loc_1400015BE
0x14000191c  mov     rdx, r12
0x14000191f  mov     rcx, rbp
0x140001922  call    BalanceUpdateCostEstimatesInternal
0x140001927  jmp     loc_1400015BE
```
