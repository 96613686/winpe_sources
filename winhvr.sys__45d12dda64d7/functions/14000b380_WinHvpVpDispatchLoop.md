# WinHvpVpDispatchLoop

- ea: `0x14000b380`
- end: `0x14000bcc0`
- name: `WinHvpVpDispatchLoop`
- size: `2368`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000b0f0`

## callees

- `0x140003910`
- `0x140004118`
- `0x140009c50`
- `0x140009c90`
- `0x14000b380`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000b43d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bbf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b43d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ba2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bbf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b412`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b456`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b412`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b456`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9f7`
- `ntoskrnl!HvlInvokeFastExtendedHypercall` at `0x14000b741`
- `ntoskrnl!HvlInvokeFastExtendedHypercall` at `0x14000b741`
- `ntoskrnl!KfRaiseIrql` at `0x14000b590`
- `ntoskrnl!KfRaiseIrql` at `0x14000b788`
- `ntoskrnl!KfRaiseIrql` at `0x14000b590`
- `ntoskrnl!KfRaiseIrql` at `0x14000b788`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ba3f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bc0e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ba3f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bc0e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000baad`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000baad`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000bae1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000bae1`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000b829`
- `ntoskrnl!KeQueryPriorityThread` at `0x14000b829`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000b489`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000ba1a`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000b489`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000ba1a`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000b5bc`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000b7f9`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000b5bc`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14000b7f9`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14000b3f2`
- `ntoskrnl!ExTryAcquirePushLockExclusiveEx` at `0x14000b3f2`
- `ntoskrnl!ZwYieldExecution` at `0x14000b941`
- `ntoskrnl!ZwYieldExecution` at `0x14000bb8c`
- `ntoskrnl!ZwYieldExecution` at `0x14000b941`
- `ntoskrnl!ZwYieldExecution` at `0x14000bb8c`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000bba8`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000bba8`
- `ntoskrnl!KeQueryTotalCycleTimeThread` at `0x14000b64c`
- `ntoskrnl!KeQueryTotalCycleTimeThread` at `0x14000b7a3`
- `ntoskrnl!KeQueryTotalCycleTimeThread` at `0x14000b64c`
- `ntoskrnl!KeQueryTotalCycleTimeThread` at `0x14000b7a3`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000b532`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000b532`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000b550`
- `ntoskrnl!PsIsThreadTerminating` at `0x14000b550`
- `ntoskrnl!KePrepareToDispatchVirtualProcessor` at `0x14000b6a5`
- `ntoskrnl!KePrepareToDispatchVirtualProcessor` at `0x14000b6a5`
- `ntoskrnl!KeLowerIrql` at `0x14000b660`
- `ntoskrnl!KeLowerIrql` at `0x14000b8a0`
- `ntoskrnl!KeLowerIrql` at `0x14000b660`
- `ntoskrnl!KeLowerIrql` at `0x14000b8a0`
- `ntoskrnl!__imp_KeYieldExecution` at `0x14000b90e`
- `ntoskrnl!__imp_KeYieldExecution` at `0x14000b90e`

## pseudocode

```c
__int64 __fastcall WinHvpVpDispatchLoop(__int64 *a1, unsigned int a2, int *a3)
{
  __int64 *v3; // rbx
  unsigned int v4; // r15d
  __int64 *v5; // r12
  KIRQL v7; // al
  int v8; // ecx
  int v9; // ecx
  signed int v10; // r14d
  KIRQL v11; // si
  bool v12; // zf
  __int64 v13; // rdx
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v15; // r13
  KIRQL v16; // si
  _QWORD *v17; // rdi
  unsigned __int64 v18; // rax
  __int64 v19; // r10
  signed __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // edi
  __int64 v23; // rax
  __int64 v24; // rdi
  unsigned __int16 v25; // ax
  signed int v26; // eax
  KIRQL v27; // r12
  unsigned __int64 v28; // rax
  ULONG64 v29; // rtt
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // r14
  _QWORD *v33; // r13
  __int64 v34; // r8
  signed __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rax
  int *v38; // r13
  int v39; // edi
  KIRQL v40; // al
  int v41; // ecx
  KIRQL v42; // al
  KIRQL v43; // di
  int v45; // ecx
  BOOLEAN v46; // al
  int v47; // edx
  __int64 v48; // rcx
  char v49; // [rsp+40h] [rbp-89h] BYREF
  char v50; // [rsp+41h] [rbp-88h] BYREF
  char v51; // [rsp+42h] [rbp-87h] BYREF
  char v52; // [rsp+43h] [rbp-86h] BYREF
  NTSTATUS v53; // [rsp+44h] [rbp-85h]
  __int64 v54; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v55; // [rsp+50h] [rbp-79h]
  int v56; // [rsp+54h] [rbp-75h] BYREF
  struct _KTHREAD *v57; // [rsp+58h] [rbp-71h]
  unsigned __int64 v58; // [rsp+60h] [rbp-69h] BYREF
  int *v59; // [rsp+68h] [rbp-61h]
  union _LARGE_INTEGER Interval; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v61; // [rsp+78h] [rbp-51h]
  __int64 v62; // [rsp+80h] [rbp-49h]
  __int64 v63; // [rsp+88h] [rbp-41h] BYREF
  PVOID Object[2]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v66; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-9h] BYREF
  int v68; // [rsp+C8h] [rbp-1h]
  int v69; // [rsp+CCh] [rbp+3h]
  __int64 v70; // [rsp+D0h] [rbp+7h]
  unsigned __int64 v71; // [rsp+D8h] [rbp+Fh]

  v55 = a2;
  v61 = a1;
  v3 = a1 + 3;
  v59 = a3;
  v4 = a2;
  Interval.QuadPart = 0;
  v5 = a1;
  v63 = 0;
  v56 = 0;
  v49 = 0;
  v51 = 0;
  *(_OWORD *)Object = 0;
  v52 = 0;
  v66 = 0;
  v50 = 0;
  v58 = 0;
  if ( !(unsigned __int8)ExTryAcquirePushLockExclusiveEx(a1 + 3, 0) )
    return 3224698901LL;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 2);
  v8 = *((_DWORD *)v3 + 2);
  if ( v8 != 2 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 2 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)v3 + 2, v7);
        ExReleasePushLockExclusiveEx(v3, 0);
        return 3224698901LL;
      }
    }
    else
    {
      *((_DWORD *)v3 + 2) = 2;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 2, v7);
  v10 = 0;
  if ( *((_BYTE *)v3 + 12) )
  {
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 11);
    v12 = v3[10] == -1;
    v3[5] = (__int64)KeGetCurrentThread();
    v13 = 1;
    if ( v12 )
      v13 = 15;
    *((_DWORD *)v3 + 24) = KeSetActualBasePriorityThread(v3[5], v13);
    KeReleaseSpinLock((PKSPIN_LOCK)v3 + 11, v11);
  }
  *a3 = 6;
  Object[0] = (PVOID)v3[16];
  Object[1] = v3 + 17;
  Interval.QuadPart = -50000;
  CurrentThread = KeGetCurrentThread();
  v12 = *((_BYTE *)v3 + 13) == 0;
  v15 = v3[23];
  v62 = v15;
  v57 = CurrentThread;
  if ( !v12 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v15 + 8));
    *((_BYTE *)v3 + 13) = 0;
  }
  while ( 1 )
  {
    if ( *((_DWORD *)v3 + 2) == 4 )
      goto LABEL_90;
    v12 = *((_DWORD *)v3 + 6) == 1;
    v53 = 0;
    if ( v12 )
    {
      v53 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 1u, 0, 0);
      if ( !v53 )
        *((_DWORD *)v3 + 6) = 2;
    }
    if ( PsIsThreadTerminating(CurrentThread) || *((_DWORD *)v3 + 2) == 3 )
      break;
    v10 = v53;
    if ( *((_DWORD *)v3 + 6) == 2 )
    {
      if ( *((_BYTE *)v3 + 12) )
      {
        v54 = 0;
        v16 = KfRaiseIrql(2u);
        v17 = (_QWORD *)(qword_140016198 + 368LL * HIDWORD(KeGetPcr()[1].LockArray));
        v18 = KeQueryInterruptTimePrecise(&v54);
        if ( !v3[7] )
        {
          if ( v17[2] <= v18 )
          {
            v19 = dword_140016188;
            v20 = v17[1] + ((__int64)dword_140016188 >> 3) - ((unsigned __int64)(v17[3] + 2LL * v17[1]) >> 3);
            if ( v20 < 500 )
            {
              v20 = 500;
            }
            else if ( v20 > dword_14001618C )
            {
              v20 = dword_14001618C;
            }
            v17[1] = v20;
            v17[2] = v19 + v18;
            v17[3] = 0;
          }
          v3[7] = v17[1];
          if ( v3[10] == -1 )
            v3[8] = v18;
        }
        v3[9] = KeQueryTotalCycleTimeThread(KeGetCurrentThread(), 0);
        KeLowerIrql(v16);
      }
      v21 = v4 >> 1;
      v58 = 0;
      LOBYTE(v21) = (v4 & 2) != 0;
      v22 = v4 & 1 | 2;
      KePrepareToDispatchVirtualProcessor(v21, &v50, &v51, &v52, &v49, &v58);
      if ( v50 )
        v22 = v4 & 1 | 0xA;
      if ( v51 )
        v22 |= 0x10u;
      if ( v52 )
        v22 |= 0x20u;
      if ( v49 )
        v22 |= 4u;
      v67 = *v5;
      v68 = *((_DWORD *)v5 + 2);
      v23 = v3[7];
      v69 = v22;
      v24 = v3[22];
      v70 = v23;
      v71 = v58;
      v54 = 65730;
      v65 = 0;
      if ( v24 )
        *(_BYTE *)(v24 + 65) = 1;
      v25 = HvlInvokeFastExtendedHypercall(v54, &v67, 32, &v65, 16);
      if ( v24 )
        *(_BYTE *)(v24 + 65) = 0;
      if ( v25 )
      {
        v10 = v25 | 0xC0350000;
        v53 = v10;
        if ( v49 )
          __writemsr(0x48u, v58);
        _enable();
        v26 = v25 | 0xC0350000;
      }
      else
      {
        v10 = 0;
        v3[3] = v65;
        v26 = 0;
        v53 = 0;
      }
      LODWORD(v54) = v26;
      if ( *((_BYTE *)v3 + 12) )
      {
        *(_QWORD *)&v65 = 0;
        v27 = KfRaiseIrql(2u);
        v29 = 10 * (KeQueryTotalCycleTimeThread(KeGetCurrentThread(), 0) - v3[9]);
        v28 = v29 / qword_140016180;
        v30 = v29 / qword_140016180;
        if ( (unsigned int)(*((_DWORD *)v3 + 7) - 7) <= 1 )
          goto LABEL_79;
        if ( !v28 )
          goto LABEL_47;
        v31 = v3[7];
        if ( v31 < v28 + 500 )
LABEL_79:
          v3[7] = 0;
        else
          v3[7] = v31 - v28;
LABEL_47:
        v32 = KeQueryInterruptTimePrecise(&v65);
        v33 = (_QWORD *)(qword_140016198 + 368LL * HIDWORD(KeGetPcr()[1].LockArray));
        if ( KeQueryPriorityThread(KeGetCurrentThread()) == 15 )
        {
          if ( v33[2] >= v32 )
          {
            v33[3] += v30;
            goto LABEL_50;
          }
LABEL_51:
          v34 = dword_140016188;
          v35 = ((__int64)dword_140016188 >> 3) - ((unsigned __int64)(v33[3] + 2LL * v33[1]) >> 3) + v33[1];
          if ( v35 < 500 )
          {
            v35 = 500;
          }
          else if ( v35 > dword_14001618C )
          {
            v35 = dword_14001618C;
          }
          v33[1] = v35;
          v33[2] = v34 + v32;
          v33[3] = v30;
        }
        else
        {
LABEL_50:
          v30 = 0;
          if ( v33[2] <= v32 )
            goto LABEL_51;
        }
        KeLowerIrql(v27);
        v26 = v54;
        v10 = v53;
        v4 = v55;
        v5 = v61;
        v15 = v62;
      }
      if ( v26 < 0 )
      {
        if ( v26 != -1070268409 )
          goto LABEL_90;
        *((_DWORD *)v3 + 6) = 2;
        *((_DWORD *)v3 + 7) = 5;
        if ( *((_BYTE *)v3 + 12) )
        {
          if ( v3[10] == -1 )
            WinHvpThrottleVpDispatchThreadNoCheck(v3);
          if ( v3[10] != -1 && ZwYieldExecution() < 0 )
            KeDelayExecutionThread(0, 0, &Interval);
        }
      }
      if ( !v3[7] && *((_BYTE *)v3 + 12) )
      {
        if ( v3[10] == -1 )
          WinHvpThrottleVpDispatchThreadNoCheck(v3);
        if ( v3[10] != -1 )
          ZwYieldExecution();
      }
      v36 = *((_DWORD *)v3 + 7);
      if ( v36 == 2 )
      {
        v37 = v3[22];
        if ( v37 && *(_DWORD *)(v37 + 20) )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
          *((_BYTE *)v3 + 13) = 1;
        }
        v38 = v59;
        *v59 = 4;
        goto LABEL_73;
      }
      v4 &= ~1u;
      v55 = v4;
      if ( v36 == 6 )
      {
        v46 = ExAcquireRundownProtection((PEX_RUNDOWN_REF)v3 + 20);
        CurrentThread = v57;
        if ( v46 )
        {
          ((void (__fastcall *)(_QWORD, __int64))qword_140016230)(0, v3[21]);
          ExReleaseRundownProtection((PEX_RUNDOWN_REF)v3 + 20);
        }
      }
      else
      {
        CurrentThread = v57;
        if ( !*((_BYTE *)v3 + 12) && v36 == 7 )
          KeYieldExecution(3 - (unsigned int)(*(_DWORD *)(v15 + 8) != 0));
      }
    }
  }
  if ( (v4 & 1) != 0 )
  {
    v47 = *((_DWORD *)v5 + 2);
    v48 = *v5;
    v56 = 1;
    *(_QWORD *)&v66 = 0;
    v10 = WinHvSetVpRegisters(v48, v47, 0, 1, (__int64)&v56, (__int64)&v66, (__int64)&v63);
    if ( v10 < 0 )
    {
LABEL_90:
      v38 = v59;
      goto LABEL_73;
    }
  }
  v38 = v59;
  v10 = 0;
  *v59 = 5;
LABEL_73:
  v39 = *v38;
  v40 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 2);
  v41 = *((_DWORD *)v3 + 2);
  if ( v41 == 2 )
  {
    if ( (unsigned int)(v39 - 4) <= 1 )
      goto LABEL_75;
    if ( v39 == 2 )
    {
      *((_DWORD *)v3 + 2) = 3;
      goto LABEL_76;
    }
    if ( v39 == 3 )
LABEL_111:
      *((_DWORD *)v3 + 2) = 4;
  }
  else
  {
    v45 = v41 - 1;
    if ( v45 )
    {
      if ( v45 == 2 )
      {
        if ( (unsigned int)(v39 - 4) <= 1 )
        {
LABEL_75:
          *((_DWORD *)v3 + 2) = 1;
          goto LABEL_76;
        }
        if ( v39 == 3 )
          goto LABEL_111;
      }
    }
    else if ( v39 == 1 )
    {
      *((_DWORD *)v3 + 2) = 2;
    }
    else
    {
      *((_DWORD *)v3 + 2) = (v39 != 2) + 3;
    }
  }
LABEL_76:
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 2, v40);
  if ( *((_BYTE *)v3 + 12) )
  {
    v42 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 11);
    v3[5] = 0;
    v43 = v42;
    KeSetActualBasePriorityThread(KeGetCurrentThread(), *((unsigned int *)v3 + 24));
    KeReleaseSpinLock((PKSPIN_LOCK)v3 + 11, v43);
  }
  ExReleasePushLockExclusiveEx(v3, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b380  push    rbp
0x14000b382  push    rbx
0x14000b383  push    rsi
0x14000b384  push    rdi
0x14000b385  push    r12
0x14000b387  push    r13
0x14000b389  push    r15
0x14000b38b  lea     rbp, [rsp-27h]
0x14000b390  sub     rsp, 0F0h
0x14000b397  mov     rax, cs:__security_cookie
0x14000b39e  xor     rax, rsp
0x14000b3a1  mov     [rbp+57h+var_40], rax
0x14000b3a5  xor     esi, esi
0x14000b3a7  mov     [rbp+57h+var_D0], edx
0x14000b3aa  xorps   xmm0, xmm0
0x14000b3ad  mov     [rbp+57h+var_A8], rcx
0x14000b3b1  lea     rbx, [rcx+18h]
0x14000b3b5  mov     [rbp+57h+var_B8], r8
0x14000b3b9  mov     r15d, edx
0x14000b3bc  mov     qword ptr [rbp+57h+Interval], rsi
0x14000b3c0  mov     r12, rcx
0x14000b3c3  mov     [rbp+57h+var_98], rsi
0x14000b3c7  mov     rcx, rbx
0x14000b3ca  mov     [rbp+57h+var_CC], esi
0x14000b3cd  xor     edx, edx
0x14000b3cf  mov     [rsp+120h+var_E0], sil
0x14000b3d4  mov     r13, r8
0x14000b3d7  mov     [rsp+120h+var_DE], sil
0x14000b3dc  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14000b3e0  mov     [rsp+120h+var_DD], sil
0x14000b3e5  movups  [rbp+57h+var_70], xmm0
0x14000b3e9  mov     [rsp+120h+var_DF], sil
0x14000b3ee  mov     [rbp+57h+var_C0], rsi
0x14000b3f2  call    cs:__imp_ExTryAcquirePushLockExclusiveEx
0x14000b3f9  nop     dword ptr [rax+rax+00h]
0x14000b3fe  test    al, al
0x14000b400  jz      loc_14000BCB6
0x14000b406  lea     rcx, [rbx+10h]; SpinLock
0x14000b40a  mov     [rsp+120h+arg_8], r14
0x14000b412  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b419  nop     dword ptr [rax+rax+00h]
0x14000b41e  mov     ecx, [rbx+8]
0x14000b421  movzx   edx, al; NewIrql
0x14000b424  cmp     ecx, 2
0x14000b427  jz      short loc_14000B439
0x14000b429  sub     ecx, 1
0x14000b42c  jnz     loc_14000BBE8
0x14000b432  mov     dword ptr [rbx+8], 2
0x14000b439  lea     rcx, [rbx+10h]; SpinLock
0x14000b43d  call    cs:__imp_KeReleaseSpinLock
0x14000b444  nop     dword ptr [rax+rax+00h]
0x14000b449  mov     r14d, esi
0x14000b44c  cmp     [rbx+0Ch], sil
0x14000b450  jz      short loc_14000B4AC
0x14000b452  lea     rcx, [rbx+58h]; SpinLock
0x14000b456  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b45d  nop     dword ptr [rax+rax+00h]
0x14000b462  mov     rcx, gs:188h
0x14000b46b  movzx   esi, al
0x14000b46e  mov     rdx, [rbx+50h]
0x14000b472  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14000b476  mov     [rbx+28h], rcx
0x14000b47a  mov     rcx, [rbx+28h]
0x14000b47e  mov     edx, 1
0x14000b483  jz      loc_14000BA7E
0x14000b489  call    cs:__imp_KeSetActualBasePriorityThread
0x14000b490  nop     dword ptr [rax+rax+00h]
0x14000b495  movzx   edx, sil; NewIrql
0x14000b499  lea     rcx, [rbx+58h]; SpinLock
0x14000b49d  mov     [rbx+60h], eax
0x14000b4a0  call    cs:__imp_KeReleaseSpinLock
0x14000b4a7  nop     dword ptr [rax+rax+00h]
0x14000b4ac  mov     dword ptr [r13+0], 6
0x14000b4b4  mov     rax, [rbx+80h]
0x14000b4bb  mov     [rbp+57h+Object], rax
0x14000b4bf  lea     rax, [rbx+88h]
0x14000b4c6  mov     [rbp+57h+Object+8], rax
0x14000b4ca  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFF3CB0h
0x14000b4d2  mov     rsi, gs:188h
0x14000b4db  cmp     byte ptr [rbx+0Dh], 0
0x14000b4df  mov     r13, [rbx+0B8h]
0x14000b4e6  mov     [rbp+57h+var_A0], r13
0x14000b4ea  mov     [rbp+57h+var_C8], rsi
0x14000b4ee  jnz     loc_14000BB15
0x14000b4f4  mov     eax, [rbx+8]
0x14000b4f7  cmp     eax, 4
0x14000b4fa  jz      loc_14000BB34
0x14000b500  xor     edi, edi
0x14000b502  cmp     dword ptr [rbx+18h], 1
0x14000b506  mov     [rsp+120h+var_DC], edi
0x14000b50a  jnz     short loc_14000B54D
0x14000b50c  mov     [rsp+120h+WaitBlockArray], rdi; WaitBlockArray
0x14000b511  lea     rdx, [rbp+57h+Object]; Object
0x14000b515  mov     [rsp+120h+Timeout], rdi; Timeout
0x14000b51a  xor     r9d, r9d; WaitReason
0x14000b51d  mov     [rsp+120h+Alertable], 1; Alertable
0x14000b522  mov     r8d, 1; WaitType
0x14000b528  mov     ecx, 2; Count
0x14000b52d  mov     [rsp+120h+WaitMode], dil; WaitMode
0x14000b532  call    cs:__imp_KeWaitForMultipleObjects
0x14000b539  nop     dword ptr [rax+rax+00h]
0x14000b53e  mov     [rsp+120h+var_DC], eax
0x14000b542  test    eax, eax
0x14000b544  jnz     short loc_14000B54D
0x14000b546  mov     dword ptr [rbx+18h], 2
0x14000b54d  mov     rcx, rsi; Thread
0x14000b550  call    cs:__imp_PsIsThreadTerminating
0x14000b557  nop     dword ptr [rax+rax+00h]
0x14000b55c  test    al, al
0x14000b55e  jnz     loc_14000BBB9
0x14000b564  mov     ecx, [rbx+8]
0x14000b567  cmp     ecx, 3
0x14000b56a  jz      loc_14000BBB9
0x14000b570  cmp     dword ptr [rbx+18h], 2
0x14000b574  mov     r14d, [rsp+120h+var_DC]
0x14000b579  jnz     loc_14000B4F4
0x14000b57f  cmp     [rbx+0Ch], dil
0x14000b583  jz      loc_14000B66C
0x14000b589  mov     cl, 2; NewIrql
0x14000b58b  mov     [rsp+120h+var_D8], rdi
0x14000b590  call    cs:__imp_KfRaiseIrql
0x14000b597  nop     dword ptr [rax+rax+00h]
0x14000b59c  mov     ecx, gs:1A4h
0x14000b5a4  movzx   esi, al
0x14000b5a7  mov     edx, ecx
0x14000b5a9  lea     rcx, [rsp+120h+var_D8]
0x14000b5ae  imul    rdi, rdx, 170h
0x14000b5b5  add     rdi, cs:qword_140016198
0x14000b5bc  call    cs:__imp_KeQueryInterruptTimePrecise
0x14000b5c3  nop     dword ptr [rax+rax+00h]
0x14000b5c8  cmp     qword ptr [rbx+38h], 0
0x14000b5cd  mov     r9, rax
0x14000b5d0  jnz     short loc_14000B641
0x14000b5d2  cmp     [rdi+10h], rax
0x14000b5d6  ja      short loc_14000B62B
0x14000b5d8  mov     r8, [rdi+8]
0x14000b5dc  mov     rcx, [rdi+18h]
0x14000b5e0  movsxd  r10, cs:dword_140016188
0x14000b5e7  lea     rdx, [rcx+r8*2]
0x14000b5eb  mov     rcx, r10
0x14000b5ee  sar     rcx, 3
0x14000b5f2  shr     rdx, 3
0x14000b5f6  sub     rcx, rdx
0x14000b5f9  add     rcx, r8
0x14000b5fc  cmp     rcx, 1F4h
0x14000b603  jl      loc_14000BB23
0x14000b609  movsxd  rax, cs:dword_14001618C
0x14000b610  cmp     rcx, rax
0x14000b613  cmovg   rcx, rax
0x14000b617  lea     rax, [r10+r9]
0x14000b61b  mov     [rdi+8], rcx
0x14000b61f  mov     [rdi+10h], rax
0x14000b623  mov     qword ptr [rdi+18h], 0
0x14000b62b  mov     rax, [rdi+8]
0x14000b62f  mov     [rbx+38h], rax
0x14000b633  mov     rax, [rbx+50h]
0x14000b637  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b63b  jnz     short loc_14000B641
0x14000b63d  mov     [rbx+40h], r9
0x14000b641  mov     rcx, gs:188h; Thread
0x14000b64a  xor     edx, edx; CycleTimeStamp
0x14000b64c  call    cs:__imp_KeQueryTotalCycleTimeThread
0x14000b653  nop     dword ptr [rax+rax+00h]
0x14000b658  movzx   ecx, sil; NewIrql
0x14000b65c  mov     [rbx+48h], rax
0x14000b660  call    cs:__imp_KeLowerIrql
0x14000b667  nop     dword ptr [rax+rax+00h]
0x14000b66c  mov     ecx, r15d
0x14000b66f  lea     rax, [rbp+57h+var_C0]
0x14000b673  mov     qword ptr [rsp+120h+Alertable], rax
0x14000b678  lea     r9, [rsp+120h+var_DD]
0x14000b67d  shr     ecx, 1
0x14000b67f  lea     rax, [rsp+120h+var_E0]
0x14000b684  mov     edi, r15d
0x14000b687  mov     qword ptr [rsp+120h+WaitMode], rax
0x14000b68c  xor     esi, esi
0x14000b68e  lea     r8, [rsp+120h+var_DE]
0x14000b693  and     edi, 1
0x14000b696  mov     [rbp+57h+var_C0], rsi
0x14000b69a  and     cl, 1
0x14000b69d  lea     rdx, [rsp+120h+var_DF]
0x14000b6a2  or      edi, 2
0x14000b6a5  call    cs:__imp_KePrepareToDispatchVirtualProcessor
0x14000b6ac  nop     dword ptr [rax+rax+00h]
0x14000b6b1  mov     eax, edi
0x14000b6b3  or      eax, 8
0x14000b6b6  cmp     [rsp+120h+var_DF], sil
0x14000b6bb  cmovnz  edi, eax
0x14000b6be  cmp     [rsp+120h+var_DE], sil
0x14000b6c3  jnz     loc_14000B95F
0x14000b6c9  cmp     [rsp+120h+var_DD], sil
0x14000b6ce  jnz     loc_14000B94F
0x14000b6d4  cmp     [rsp+120h+var_E0], sil
0x14000b6d9  jnz     loc_14000B957
0x14000b6df  mov     rax, [r12]
0x14000b6e3  xorps   xmm0, xmm0
0x14000b6e6  mov     [rbp+57h+var_60], rax
0x14000b6ea  mov     eax, [r12+8]
0x14000b6ef  mov     [rbp+57h+var_58], eax
0x14000b6f2  mov     rax, [rbx+38h]
0x14000b6f6  mov     [rbp+57h+var_54], edi
0x14000b6f9  mov     rdi, [rbx+0B0h]
0x14000b700  mov     [rbp+57h+var_50], rax
0x14000b704  mov     rax, [rbp+57h+var_C0]
0x14000b708  mov     [rsp+120h+var_D8], rsi
0x14000b70d  mov     [rbp+57h+var_48], rax
0x14000b711  mov     dword ptr [rsp+120h+var_D8], 100C2h
0x14000b719  movups  [rbp+57h+var_80], xmm0
0x14000b71d  test    rdi, rdi
0x14000b720  jz      short loc_14000B726
0x14000b722  mov     byte ptr [rdi+41h], 1
0x14000b726  mov     rcx, [rsp+120h+var_D8]
0x14000b72b  lea     r9, [rbp+57h+var_80]
0x14000b72f  mov     r8d, 20h ; ' '
0x14000b735  mov     dword ptr [rsp+120h+WaitMode], 10h
0x14000b73d  lea     rdx, [rbp+57h+var_60]
0x14000b741  call    cs:__imp_HvlInvokeFastExtendedHypercall
0x14000b748  nop     dword ptr [rax+rax+00h]
0x14000b74d  test    rdi, rdi
0x14000b750  jz      short loc_14000B756
0x14000b752  mov     [rdi+41h], sil
0x14000b756  test    ax, ax
0x14000b759  jnz     loc_14000B967
0x14000b75f  mov     eax, dword ptr [rbp+57h+var_80]
0x14000b762  mov     r14d, esi
0x14000b765  mov     [rbx+18h], eax
0x14000b768  mov     eax, dword ptr [rbp+57h+var_80+4]
0x14000b76b  mov     [rbx+1Ch], eax
0x14000b76e  mov     eax, esi
0x14000b770  mov     [rsp+120h+var_DC], esi
0x14000b774  mov     dword ptr [rsp+120h+var_D8], eax
0x14000b778  cmp     [rbx+0Ch], sil
0x14000b77c  jz      loc_14000B8C1
0x14000b782  mov     cl, 2; NewIrql
0x14000b784  mov     qword ptr [rbp+57h+var_80], rsi
0x14000b788  call    cs:__imp_KfRaiseIrql
0x14000b78f  nop     dword ptr [rax+rax+00h]
0x14000b794  mov     rcx, gs:188h; Thread
0x14000b79d  xor     edx, edx; CycleTimeStamp
0x14000b79f  movzx   r12d, al
0x14000b7a3  call    cs:__imp_KeQueryTotalCycleTimeThread
0x14000b7aa  nop     dword ptr [rax+rax+00h]
0x14000b7af  mov     ecx, [rbx+1Ch]
0x14000b7b2  xor     edx, edx
0x14000b7b4  sub     rax, [rbx+48h]
0x14000b7b8  sub     ecx, 7
0x14000b7bb  lea     rax, [rax+rax*4]
0x14000b7bf  add     rax, rax
0x14000b7c2  div     cs:qword_140016180
0x14000b7c9  mov     rdi, rax
0x14000b7cc  cmp     ecx, 1
0x14000b7cf  jbe     loc_14000BA75
0x14000b7d5  test    rax, rax
0x14000b7d8  jz      short loc_14000B7F5
0x14000b7da  mov     rdx, [rbx+38h]
0x14000b7de  lea     rcx, [rax+1F4h]
0x14000b7e5  cmp     rdx, rcx
0x14000b7e8  jb      loc_14000BA75
0x14000b7ee  sub     rdx, rax
0x14000b7f1  mov     [rbx+38h], rdx
0x14000b7f5  lea     rcx, [rbp+57h+var_80]
0x14000b7f9  call    cs:__imp_KeQueryInterruptTimePrecise
0x14000b800  nop     dword ptr [rax+rax+00h]
0x14000b805  mov     ecx, gs:1A4h
0x14000b80d  mov     r14, rax
0x14000b810  mov     edx, ecx
0x14000b812  mov     rcx, gs:188h; Thread
0x14000b81b  imul    r13, rdx, 170h
0x14000b822  add     r13, cs:qword_140016198
0x14000b829  call    cs:__imp_KeQueryPriorityThread
0x14000b830  nop     dword ptr [rax+rax+00h]
0x14000b835  cmp     eax, 0Fh
0x14000b838  jnz     short loc_14000B844
0x14000b83a  cmp     [r13+10h], r14
0x14000b83e  jb      short loc_14000B84C
0x14000b840  add     [r13+18h], rdi
0x14000b844  xor     edi, edi
0x14000b846  cmp     [r13+10h], r14
0x14000b84a  ja      short loc_14000B89C
0x14000b84c  mov     rdx, [r13+8]
0x14000b850  mov     rax, [r13+18h]
0x14000b854  movsxd  r8, cs:dword_140016188
0x14000b85b  lea     rcx, [rax+rdx*2]
0x14000b85f  mov     rax, r8
0x14000b862  shr     rcx, 3
0x14000b866  sar     rax, 3
0x14000b86a  sub     rax, rcx
0x14000b86d  lea     rcx, [rax+rdx]
0x14000b871  cmp     rcx, 1F4h
0x14000b878  jl      loc_14000BAF2
0x14000b87e  movsxd  rax, cs:dword_14001618C
0x14000b885  cmp     rcx, rax
0x14000b888  cmovg   rcx, rax
0x14000b88c  lea     rax, [r8+r14]
0x14000b890  mov     [r13+8], rcx
0x14000b894  mov     [r13+10h], rax
0x14000b898  mov     [r13+18h], rdi
0x14000b89c  movzx   ecx, r12b; NewIrql
0x14000b8a0  call    cs:__imp_KeLowerIrql
0x14000b8a7  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
