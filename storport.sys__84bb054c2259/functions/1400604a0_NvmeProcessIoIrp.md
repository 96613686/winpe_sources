# NvmeProcessIoIrp

- ea: `0x1400604a0`
- end: `0x140060e86`
- name: `NvmeProcessIoIrp`
- size: `2534`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140002110`

## callees

- `0x140042b60`
- `0x140043ca0`
- `0x140051870`
- `0x1400604a0`
- `0x140062190`
- `0x140062b20`
- `0x140066100`
- `0x140066260`
- `0x1400707a0`
- `0x14012f180`
- `0x1401404ac`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140060c40`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140060c40`
- `ntoskrnl!PoFxIdleComponent` at `0x140060dfd`
- `ntoskrnl!PoFxIdleComponent` at `0x140060e4c`
- `ntoskrnl!PoFxIdleComponent` at `0x140060dfd`
- `ntoskrnl!PoFxIdleComponent` at `0x140060e4c`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400604f7`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400604f7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060682`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060714`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060dd7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060682`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060714`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060dd7`
- `ntoskrnl!KeLowerIrql` at `0x140060bdd`
- `ntoskrnl!KeLowerIrql` at `0x140060bdd`
- `ntoskrnl!KfRaiseIrql` at `0x140060aff`
- `ntoskrnl!KfRaiseIrql` at `0x140060aff`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060763`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060e25`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060763`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060e25`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400604de`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400604de`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400608b2`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400608b2`
- `ntoskrnl!PoFxActivateComponent` at `0x14006063c`
- `ntoskrnl!PoFxActivateComponent` at `0x1400606da`
- `ntoskrnl!PoFxActivateComponent` at `0x140060736`
- `ntoskrnl!PoFxActivateComponent` at `0x14006063c`
- `ntoskrnl!PoFxActivateComponent` at `0x1400606da`
- `ntoskrnl!PoFxActivateComponent` at `0x140060736`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140060800`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140060800`
- `ntoskrnl!IoRecordIoAttribution` at `0x14006081f`
- `ntoskrnl!IoRecordIoAttribution` at `0x14006081f`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1400607ab`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x1400607ab`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400605ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400605ed`

## pseudocode

```c
__int64 __fastcall NvmeProcessIoIrp(ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter2)
{
  unsigned int v4; // edi
  __int64 CurrentProcessorNumber; // r13
  __int64 *v6; // r15
  unsigned int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rcx
  char v10; // r14
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // r12
  __int64 v14; // rax
  bool v15; // bl
  __int64 v16; // rcx
  __int64 v17; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v22; // rcx
  __int64 v23; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v24; // rcx
  __int64 v25; // rax
  unsigned __int8 *v26; // rax
  __int64 v27; // rbx
  _DWORD *v28; // rax
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // r14
  bool v31; // bl
  unsigned __int64 v32; // rdi
  unsigned __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // r10
  __int64 v36; // r9
  unsigned int v37; // edx
  char v38; // al
  __int64 v39; // r11
  unsigned int v40; // edx
  unsigned int v41; // eax
  __int64 NVMeSGLBufferContext; // rax
  __int64 v43; // r13
  __int64 v44; // rdx
  char v45; // al
  __int64 v46; // rax
  int v47; // ebx
  __int64 v48; // rdi
  __int64 v49; // r8
  int v50; // r9d
  __int64 v51; // rbx
  PSLIST_ENTRY v52; // rax
  __int64 NewNVMePrpListBufferEntry; // rax
  __int64 v54; // r10
  __int64 v55; // r8
  __int64 v56; // rbx
  __int64 v57; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v58; // rcx
  __int64 v59; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v60; // rcx
  __int64 v61; // rcx
  int v63; // [rsp+38h] [rbp-C0h]
  char v64; // [rsp+60h] [rbp-98h]
  char v65; // [rsp+60h] [rbp-98h]
  KIRQL v66; // [rsp+61h] [rbp-97h]
  __int64 v67; // [rsp+68h] [rbp-90h] BYREF
  unsigned __int64 v68; // [rsp+70h] [rbp-88h]
  __int64 v69; // [rsp+78h] [rbp-80h]
  __int64 v70; // [rsp+80h] [rbp-78h]
  unsigned __int64 v71; // [rsp+88h] [rbp-70h]
  __int128 v72; // [rsp+90h] [rbp-68h] BYREF
  __int128 v73; // [rsp+A0h] [rbp-58h] BYREF

  v69 = *(_QWORD *)(BugCheckParameter2 + 184);
  v4 = 259;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v6 = (__int64 *)(BugCheckParameter3 + 128);
  if ( IoGetIoPriorityHint((PIRP)BugCheckParameter2) > IoPriorityLow )
  {
    v10 = 0;
    v12 = CurrentProcessorNumber;
    *(_BYTE *)(BugCheckParameter2 + 151) |= 1u;
    v14 = *(_QWORD *)(BugCheckParameter3 + 696);
    v67 = CurrentProcessorNumber;
    _InterlockedIncrement(*(volatile signed __int32 **)(v14 + 8 * CurrentProcessorNumber));
    v13 = (__int64 *)(BugCheckParameter3 + 16);
    goto LABEL_15;
  }
  v8 = *(_QWORD *)(*v6 + 8);
  if ( v8 && !*(_BYTE *)(v8 + 64) )
    goto LABEL_12;
  v9 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 16) + 128LL) + 168LL) + 8LL);
  if ( v9 )
  {
    if ( !*(_BYTE *)(v9 + 64) )
      goto LABEL_12;
  }
  if ( !*(_DWORD *)(*(_QWORD *)(BugCheckParameter3 + 264) + 40LL) )
  {
    v7 = *((_DWORD *)g_CpuInfo + 3);
    if ( v7 )
    {
      v11 = 0;
      while ( !**(_DWORD **)(*(_QWORD *)(BugCheckParameter3 + 696) + 8 * v11) )
      {
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= v7 )
          goto LABEL_12;
      }
      goto LABEL_7;
    }
LABEL_12:
    v10 = 0;
    goto LABEL_13;
  }
LABEL_7:
  v10 = 1;
LABEL_13:
  v12 = CurrentProcessorNumber;
  v67 = CurrentProcessorNumber;
  v13 = (__int64 *)(BugCheckParameter3 + 16);
LABEL_15:
  if ( *(_BYTE *)*v6 || _InterlockedIncrement(*(volatile signed __int32 **)(*(_QWORD *)(*v6 + 24) + 8 * v12)) != 1 )
    goto LABEL_41;
  if ( KeGetCurrentIrql() >= 2u || (*(_DWORD *)(*v6 + 80) & 6) != 0 )
  {
    v15 = 1;
    v68 = *(_QWORD *)(*v13 + 128);
    v20 = *(_QWORD *)(v68 + 168);
    if ( *(_BYTE *)v20 == 1 )
    {
      PoFxActivateComponent(**(_QWORD **)(v20 + 8), 0, 2);
      v15 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v68 + 168) + 8LL) + 64LL) == 1;
    }
    v21 = *v6;
    if ( *v6 )
    {
      if ( *(_QWORD *)(v21 + 8) )
      {
        v22 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v21 + 40);
        if ( v22 )
        {
          if ( ExAcquireRundownProtectionCacheAware(v22) )
          {
            v19 = 2;
LABEL_35:
            PoFxActivateComponent(**(_QWORD **)(*v6 + 8), 0, v19);
            v23 = *(_QWORD *)(*v6 + 8);
            v15 = *(_BYTE *)(v23 + 64) == 1;
            if ( *v6 )
            {
              if ( v23 )
              {
                v24 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(*v6 + 40);
                if ( v24 )
                  ExReleaseRundownProtectionCacheAware(v24);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v15 = 1;
    v68 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 16) + 128LL);
    v16 = *(_QWORD *)(v68 + 168);
    if ( *(_BYTE *)v16 == 1 )
    {
      PoFxActivateComponent(**(_QWORD **)(v16 + 8), 0, 1);
      v15 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v68 + 168) + 8LL) + 64LL) == 1;
    }
    v17 = *v6;
    if ( *v6 )
    {
      if ( *(_QWORD *)(v17 + 8) )
      {
        v18 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v17 + 40);
        if ( v18 )
        {
          if ( ExAcquireRundownProtectionCacheAware(v18) )
          {
            v19 = 5;
            if ( !*(_DWORD *)(BugCheckParameter3 + 272) )
              v19 = 1;
            goto LABEL_35;
          }
        }
      }
    }
  }
  if ( !v15 )
  {
    NvmeNamespaceProcessIoForDeviceIdle(BugCheckParameter3);
    return v4;
  }
LABEL_41:
  if ( v10 )
  {
    v25 = *(_QWORD *)(BugCheckParameter2 + 184);
    v67 = 0;
    *(_BYTE *)(v25 + 3) |= 1u;
    if ( (int)IoGetIoAttributionHandle(BugCheckParameter2, &v67) >= 0 )
    {
      v26 = *(unsigned __int8 **)(BugCheckParameter2 + 184);
      v27 = v67;
      v72 = 0;
      LODWORD(v72) = 1;
      v73 = 0;
      DWORD1(v72) = *v26 | 0x300;
      *((_QWORD *)&v73 + 1) = KeQueryUnbiasedInterruptTimePrecise((PULONG64)&v73 + 1);
      IoRecordIoAttribution(v27, &v72);
    }
    StorPushRequestToDeviceQueue(
      *(_QWORD *)(BugCheckParameter3 + 264),
      (unsigned int)CurrentProcessorNumber,
      BugCheckParameter2);
    v28 = *(_DWORD **)(*v13 + 1312);
    if ( v28 && *v28 || *(_DWORD *)(*v13 + 948) )
    {
      _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(BugCheckParameter3 + 264) + 40LL), 0, 1);
    }
    else if ( _InterlockedCompareExchange(
                (volatile signed __int32 *)(*(_QWORD *)(BugCheckParameter3 + 264) + 40LL),
                1,
                0) != 1 )
    {
      KeSetCoalescableTimer(
        *(PKTIMER *)(*(_QWORD *)(BugCheckParameter3 + 264) + 32LL),
        (LARGE_INTEGER)-120000LL,
        0,
        0xAu,
        *(PKDPC *)(*(_QWORD *)(BugCheckParameter3 + 264) + 24LL));
    }
    return v4;
  }
  LOBYTE(v7) = 1;
  if ( (unsigned __int8)StorAttemptInsertDeviceQueue(
                          *(_QWORD *)(BugCheckParameter3 + 256),
                          BugCheckParameter2,
                          v7,
                          CurrentProcessorNumber,
                          *v13) )
    return v4;
  v29 = *(unsigned int *)(BugCheckParameter3 + 64);
  v30 = *(unsigned int *)(v69 + 8);
  v31 = *(_BYTE *)v69 == 3;
  v64 = v31;
  if ( *(_DWORD *)(v69 + 8) % (unsigned int)v29
    || (v32 = *(_QWORD *)(v69 + 24), v68 = v32 / v29, v32 % v29)
    || (v33 = *(_QWORD *)(BugCheckParameter3 + 432), v32 / v29 >= v33)
    || (v71 = (unsigned int)v30 / (unsigned int)v29, v33 - v68 < v71) )
  {
    v4 = -1073741811;
    goto LABEL_89;
  }
  v34 = *(_QWORD *)(*(_QWORD *)(*v13 + 128) + 1336LL);
  if ( v34 && *(_DWORD *)(v34 + 28) )
    DlrmProcessReadWriteRequest(*(_QWORD *)(*(_QWORD *)(*v13 + 128) + 1336LL), (unsigned int)v30, v29, v68);
  v35 = *v13;
  v36 = *(unsigned int *)(*(_QWORD *)(*v13 + 128) + 208LL);
  LODWORD(v70) = v36;
  if ( (unsigned int)v30 > (unsigned int)v36 )
    goto LABEL_82;
  v37 = *(_DWORD *)(BugCheckParameter3 + 428);
  if ( v37 )
  {
    if ( (unsigned int)v30 > v37
      || ((v38 = *(_BYTE *)(BugCheckParameter3 + 427), v39 = v37, !v38)
        ? (v29 = v30 / v37, v41 = v29 + (v30 % v37 + v37 + v32 % v37 - 1) / v37)
        : (v40 = v37 - 1,
           v36 = (unsigned int)v70,
           v29 = ((unsigned int)v30 & v40) - 1LL,
           v41 = (v30 >> v38) + ((v29 + v39 + ((unsigned int)v32 & v40)) >> v38)),
          v41 > 1) )
    {
LABEL_82:
      v4 = NvmeSplitIoParallel(BugCheckParameter3, BugCheckParameter2, v32, v36, CurrentProcessorNumber, 0, 0, 0);
LABEL_83:
      v51 = v67;
      goto LABEL_84;
    }
  }
  if ( _bittest64((const signed __int64 *)(v35 + 136), 0x20u) )
  {
    v50 = 0;
    v51 = CurrentProcessorNumber;
    if ( ((v30
         + 4095
         + ((*(_DWORD *)(*(_QWORD *)(BugCheckParameter2 + 8) + 32LL)
           + *(_DWORD *)(*(_QWORD *)(BugCheckParameter2 + 8) + 44LL))
          & 0xFFF))
        & 0xFFFFFFFFFFFFF000uLL) <= 0x2000
      || (v52 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v35 + 880) + 8 * CurrentProcessorNumber)),
          v50 = (int)v52,
          v52)
      || (NewNVMePrpListBufferEntry = AllocateNewNVMePrpListBufferEntry(
                                        *(_QWORD *)(BugCheckParameter3 + 16),
                                        (unsigned int)CurrentProcessorNumber),
          v50 = NewNVMePrpListBufferEntry,
          NewNVMePrpListBufferEntry) )
    {
      v54 = *v13;
      if ( (*(_BYTE *)(*v13 + 136) & 2) != 0 )
        v55 = *(_QWORD *)(v54 + 728) + 192 * CurrentProcessorNumber;
      else
        LODWORD(v55) = 192 * *(unsigned __int16 *)(*(_QWORD *)(v54 + 872) + 2 * CurrentProcessorNumber)
                     + *(_DWORD *)(v54 + 728)
                     - 192;
      v4 = NvmeSubmitIoToSQ(
             BugCheckParameter3,
             BugCheckParameter2,
             v55,
             v50,
             CurrentProcessorNumber,
             0,
             v30,
             v32,
             v68,
             v71,
             v64,
             0);
    }
    else
    {
      NvmeNamespaceQueueIo(BugCheckParameter3, BugCheckParameter2, (unsigned int)CurrentProcessorNumber);
      v4 = -2147483631;
    }
LABEL_84:
    if ( v4 != -2147483631 )
    {
      if ( v4 == 259 )
        return v4;
      goto LABEL_90;
    }
    return 259;
  }
  NVMeSGLBufferContext = GetNVMeSGLBufferContext(v35, (unsigned int)CurrentProcessorNumber, v29, v36);
  v43 = NVMeSGLBufferContext;
  if ( NVMeSGLBufferContext )
  {
    v44 = v69;
    *(_QWORD *)(NVMeSGLBufferContext + 40) = BugCheckParameter2;
    v45 = *(_BYTE *)(NVMeSGLBufferContext + 126) & 0xFE;
    *(_QWORD *)(v43 + 96) = v32;
    *(_QWORD *)(v43 + 32) = BugCheckParameter3;
    *(_BYTE *)(v43 + 126) = v31 | v45;
    *(_QWORD *)(v43 + 104) = v68;
    *(_DWORD *)(v43 + 112) = v71;
    *(_QWORD *)(v43 + 64) = 0;
    *(_QWORD *)(v43 + 72) = 0;
    *(_DWORD *)(v43 + 116) = v30;
    *(_QWORD *)(v43 + 56) = *(_QWORD *)(v44 + 24);
    v46 = *(_QWORD *)(v44 + 8);
    *(_QWORD *)(v44 + 24) = v43;
    *(_QWORD *)(v43 + 48) = v46;
    *(_QWORD *)(v43 + 80) = *(_QWORD *)(*(_QWORD *)(BugCheckParameter2 + 8) + 32LL)
                          + *(unsigned int *)(*(_QWORD *)(BugCheckParameter2 + 8) + 44LL);
    *(_QWORD *)(v44 + 8) = 0xFEDCBA9000000000uLL;
    v47 = *(unsigned __int16 *)(v43 + 124);
    v48 = *(_QWORD *)(v43 + 16);
    v68 = *(_QWORD *)(BugCheckParameter2 + 8);
    v70 = *(_QWORD *)(v43 + 80);
    v69 = *v13;
    v66 = KfRaiseIrql(2u);
    v65 = v64 ^ 1;
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, _DWORD, __int64 (__fastcall *)(), __int64, char, __int64, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v69 + 128) + 1160LL) + 8LL) + 112LL))(
           *(_QWORD *)(*(_QWORD *)(v69 + 128) + 1160LL),
           *(_QWORD *)(*(_QWORD *)(v69 + 128) + 8LL),
           v68,
           v70,
           v30,
           NvmeContinueScatterGatherProcessIO,
           v43,
           v65,
           v48,
           v47);
    if ( v4 == -1073741789 )
    {
      LOBYTE(v63) = v65;
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, _DWORD, __int64 (__fastcall *)(), __int64, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v69 + 128) + 1160LL) + 8LL) + 88LL))(
             *(_QWORD *)(*(_QWORD *)(v69 + 128) + 1160LL),
             *(_QWORD *)(*(_QWORD *)(v69 + 128) + 8LL),
             v68,
             v70,
             v30,
             NvmeContinueScatterGatherProcessIO,
             v43,
             v63);
    }
    if ( v66 < 2u )
      KeLowerIrql(v66);
    if ( (v4 & 0x80000000) == 0 )
      return 259;
    LOBYTE(v49) = 1;
    FreeNVMeSGLBufferContext(*v13, v43, v49);
    goto LABEL_83;
  }
  v4 = -1073741670;
LABEL_89:
  v51 = v67;
LABEL_90:
  if ( (*(_BYTE *)(BugCheckParameter2 + 151) & 1) != 0 )
    _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(BugCheckParameter3 + 696) + 8 * v51));
  if ( !*(_BYTE *)*v6
    && _InterlockedExchangeAdd(*(volatile signed __int32 **)(*(_QWORD *)(*v6 + 24) + 8 * v51), 0xFFFFFFFF) == 1 )
  {
    v56 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter3 + 16) + 128LL);
    v57 = *(_QWORD *)(BugCheckParameter3 + 128);
    if ( v57 )
    {
      if ( *(_QWORD *)(v57 + 8) )
      {
        v58 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v57 + 40);
        if ( v58 )
        {
          if ( ExAcquireRundownProtectionCacheAware(v58) )
          {
            PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(BugCheckParameter3 + 128) + 8LL), 0, 2);
            v59 = *(_QWORD *)(BugCheckParameter3 + 128);
            if ( v59 )
            {
              if ( *(_QWORD *)(v59 + 8) )
              {
                v60 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v59 + 40);
                if ( v60 )
                  ExReleaseRundownProtectionCacheAware(v60);
              }
            }
          }
        }
      }
    }
    v61 = *(_QWORD *)(v56 + 168);
    if ( *(_BYTE *)v61 == 1 )
      PoFxIdleComponent(**(_QWORD **)(v61 + 8), 0, 2);
  }
  return v4;
}

```

## disassembly

```asm
0x1400604a0  push    rbp
0x1400604a2  push    rsi
0x1400604a3  push    rdi
0x1400604a4  push    r12
0x1400604a6  push    r13
0x1400604a8  push    r14
0x1400604aa  push    r15
0x1400604ac  sub     rsp, 0C0h
0x1400604b3  mov     rax, cs:__security_cookie
0x1400604ba  xor     rax, rsp
0x1400604bd  mov     [rsp+0F8h+var_48], rax
0x1400604c5  mov     rax, [rdx+0B8h]
0x1400604cc  mov     rsi, rcx
0x1400604cf  xor     ecx, ecx; ProcNumber
0x1400604d1  mov     [rsp+0F8h+var_80], rax
0x1400604d6  mov     rbp, rdx
0x1400604d9  mov     edi, 103h
0x1400604de  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400604e5  nop     dword ptr [rax+rax+00h]
0x1400604ea  mov     rcx, rbp; Irp
0x1400604ed  mov     r13d, eax
0x1400604f0  lea     r15, [rsi+80h]
0x1400604f7  call    cs:__imp_IoGetIoPriorityHint
0x1400604fe  nop     dword ptr [rax+rax+00h]
0x140060503  cmp     eax, 1
0x140060506  jg      loc_140060599
0x14006050c  mov     rax, [r15]
0x14006050f  mov     rcx, [rax+8]
0x140060513  test    rcx, rcx
0x140060516  jz      short loc_14006051E
0x140060518  cmp     byte ptr [rcx+40h], 0
0x14006051c  jz      short loc_140060580
0x14006051e  mov     rax, [rsi+10h]
0x140060522  mov     rcx, [rax+80h]
0x140060529  mov     rax, [rcx+0A8h]
0x140060530  mov     rcx, [rax+8]
0x140060534  test    rcx, rcx
0x140060537  jz      short loc_14006053F
0x140060539  cmp     byte ptr [rcx+40h], 0
0x14006053d  jz      short loc_140060580
0x14006053f  mov     rax, [rsi+108h]
0x140060546  mov     ecx, [rax+28h]
0x140060549  test    ecx, ecx
0x14006054b  jz      short loc_140060552
0x14006054d  mov     r14b, 1
0x140060550  jmp     short loc_140060583
0x140060552  mov     rax, cs:g_CpuInfo
0x140060559  mov     r8d, [rax+0Ch]
0x14006055d  test    r8d, r8d
0x140060560  jz      short loc_140060580
0x140060562  mov     r9, [rsi+2B8h]
0x140060569  xor     edx, edx
0x14006056b  nop     dword ptr [rax+rax+00h]
0x140060570  mov     rcx, [r9+rdx*8]
0x140060574  cmp     dword ptr [rcx], 0
0x140060577  ja      short loc_14006054D
0x140060579  inc     edx
0x14006057b  cmp     edx, r8d
0x14006057e  jb      short loc_140060570
0x140060580  xor     r14b, r14b
0x140060583  mov     rcx, rsi
0x140060586  mov     eax, 10h
0x14006058b  mov     rdx, r13
0x14006058e  mov     [rsp+0F8h+var_90], rdx
0x140060593  lea     r12, [rcx+rax]
0x140060597  jmp     short loc_1400605BD
0x140060599  xor     r14b, r14b
0x14006059c  mov     rdx, r13
0x14006059f  or      byte ptr [rbp+97h], 1
0x1400605a6  mov     rax, [rsi+2B8h]
0x1400605ad  mov     [rsp+0F8h+var_90], rdx
0x1400605b2  mov     rcx, [rax+r13*8]
0x1400605b6  lock inc dword ptr [rcx]
0x1400605b9  lea     r12, [rsi+10h]
0x1400605bd  mov     rax, [r15]
0x1400605c0  mov     [rsp+0F8h+arg_10], rbx
0x1400605c8  cmp     byte ptr [rax], 0
0x1400605cb  jnz     loc_140060786
0x1400605d1  mov     rax, [rax+18h]
0x1400605d5  mov     rcx, [rax+rdx*8]
0x1400605d9  mov     eax, 1
0x1400605de  lock xadd [rcx], eax
0x1400605e2  inc     eax
0x1400605e4  cmp     eax, 1
0x1400605e7  jnz     loc_140060786
0x1400605ed  call    cs:__imp_KeGetCurrentIrql
0x1400605f4  nop     dword ptr [rax+rax+00h]
0x1400605f9  cmp     al, 2
0x1400605fb  jnb     loc_1400606AE
0x140060601  mov     rax, [r15]
0x140060604  mov     ecx, [rax+50h]
0x140060607  test    cl, 6
0x14006060a  jnz     loc_1400606AE
0x140060610  mov     rax, [rsi+10h]
0x140060614  mov     bl, 1
0x140060616  mov     rax, [rax+80h]
0x14006061d  mov     [rsp+0F8h+var_88], rax
0x140060622  mov     rcx, [rax+0A8h]
0x140060629  cmp     [rcx], bl
0x14006062b  jnz     short loc_14006065E
0x14006062d  mov     rcx, [rcx+8]
0x140060631  xor     edx, edx
0x140060633  mov     r8d, 1
0x140060639  mov     rcx, [rcx]
0x14006063c  call    cs:__imp_PoFxActivateComponent
0x140060643  nop     dword ptr [rax+rax+00h]
0x140060648  mov     rcx, [rsp+0F8h+var_88]
0x14006064d  mov     rax, [rcx+0A8h]
0x140060654  mov     rcx, [rax+8]
0x140060658  cmp     [rcx+40h], bl
0x14006065b  setz    bl
0x14006065e  mov     rax, [r15]
0x140060661  test    rax, rax
0x140060664  jz      loc_14006076F
0x14006066a  cmp     qword ptr [rax+8], 0
0x14006066f  jz      loc_14006076F
0x140060675  mov     rcx, [rax+28h]; RunRefCacheAware
0x140060679  test    rcx, rcx
0x14006067c  jz      loc_14006076F
0x140060682  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140060689  nop     dword ptr [rax+rax+00h]
0x14006068e  test    al, al
0x140060690  jz      loc_14006076F
0x140060696  cmp     dword ptr [rsi+110h], 0
0x14006069d  mov     r8d, 5
0x1400606a3  mov     eax, 1
0x1400606a8  cmovbe  r8d, eax
0x1400606ac  jmp     short loc_14006072A
0x1400606ae  mov     rax, [r12]
0x1400606b2  mov     bl, 1
0x1400606b4  mov     rax, [rax+80h]
0x1400606bb  mov     [rsp+0F8h+var_88], rax
0x1400606c0  mov     rcx, [rax+0A8h]
0x1400606c7  cmp     [rcx], bl
0x1400606c9  jnz     short loc_1400606FC
0x1400606cb  mov     rcx, [rcx+8]
0x1400606cf  xor     edx, edx
0x1400606d1  mov     r8d, 2
0x1400606d7  mov     rcx, [rcx]
0x1400606da  call    cs:__imp_PoFxActivateComponent
0x1400606e1  nop     dword ptr [rax+rax+00h]
0x1400606e6  mov     rcx, [rsp+0F8h+var_88]
0x1400606eb  mov     rax, [rcx+0A8h]
0x1400606f2  mov     rcx, [rax+8]
0x1400606f6  cmp     [rcx+40h], bl
0x1400606f9  setz    bl
0x1400606fc  mov     rax, [r15]
0x1400606ff  test    rax, rax
0x140060702  jz      short loc_14006076F
0x140060704  cmp     qword ptr [rax+8], 0
0x140060709  jz      short loc_14006076F
0x14006070b  mov     rcx, [rax+28h]; RunRefCacheAware
0x14006070f  test    rcx, rcx
0x140060712  jz      short loc_14006076F
0x140060714  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14006071b  nop     dword ptr [rax+rax+00h]
0x140060720  test    al, al
0x140060722  jz      short loc_14006076F
0x140060724  mov     r8d, 2
0x14006072a  mov     rax, [r15]
0x14006072d  xor     edx, edx
0x14006072f  mov     rcx, [rax+8]
0x140060733  mov     rcx, [rcx]
0x140060736  call    cs:__imp_PoFxActivateComponent
0x14006073d  nop     dword ptr [rax+rax+00h]
0x140060742  mov     rax, [r15]
0x140060745  mov     rcx, [rax+8]
0x140060749  cmp     byte ptr [rcx+40h], 1
0x14006074d  setz    bl
0x140060750  test    rax, rax
0x140060753  jz      short loc_14006076F
0x140060755  test    rcx, rcx
0x140060758  jz      short loc_14006076F
0x14006075a  mov     rcx, [rax+28h]; RunRefCacheAware
0x14006075e  test    rcx, rcx
0x140060761  jz      short loc_14006076F
0x140060763  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14006076a  nop     dword ptr [rax+rax+00h]
0x14006076f  test    bl, bl
0x140060771  jnz     short loc_140060786
0x140060773  mov     r8d, r13d
0x140060776  mov     rdx, rbp
0x140060779  mov     rcx, rsi; BugCheckParameter3
0x14006077c  call    NvmeNamespaceProcessIoForDeviceIdle
0x140060781  jmp     loc_140060E58
0x140060786  test    r14b, r14b
0x140060789  jz      loc_1400608C3
0x14006078f  mov     rax, [rbp+0B8h]
0x140060796  lea     rdx, [rsp+0F8h+var_90]
0x14006079b  mov     [rsp+0F8h+var_90], 0
0x1400607a4  mov     rcx, rbp
0x1400607a7  or      byte ptr [rax+3], 1
0x1400607ab  call    cs:__imp_IoGetIoAttributionHandle
0x1400607b2  nop     dword ptr [rax+rax+00h]
0x1400607b7  mov     r14d, 1
0x1400607bd  test    eax, eax
0x1400607bf  js      short loc_14006082B
0x1400607c1  mov     rax, [rbp+0B8h]
0x1400607c8  lea     rcx, [rsp+0F8h+QpcTimeStamp]; QpcTimeStamp
0x1400607d0  mov     rbx, [rsp+0F8h+var_90]
0x1400607d5  xorps   xmm0, xmm0
0x1400607d8  movups  [rsp+0F8h+var_68], xmm0
0x1400607e0  mov     dword ptr [rsp+0F8h+var_68], r14d
0x1400607e8  movups  xmmword ptr [rsp+0A0h], xmm0
0x1400607f0  movzx   edx, byte ptr [rax]
0x1400607f3  or      edx, 300h
0x1400607f9  mov     dword ptr [rsp+0F8h+var_68+4], edx
0x140060800  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140060807  nop     dword ptr [rax+rax+00h]
0x14006080c  lea     rdx, [rsp+0F8h+var_68]
0x140060814  mov     rcx, rbx
0x140060817  mov     [rsp+0F8h+QpcTimeStamp], rax
0x14006081f  call    cs:__imp_IoRecordIoAttribution
0x140060826  nop     dword ptr [rax+rax+00h]
0x14006082b  mov     rcx, [rsi+108h]
0x140060832  mov     r8, rbp
0x140060835  mov     edx, r13d
0x140060838  call    StorPushRequestToDeviceQueue
0x14006083d  mov     rax, [r12]
0x140060841  mov     rax, [rax+520h]
0x140060848  test    rax, rax
0x14006084b  jz      short loc_140060853
0x14006084d  mov     eax, [rax]
0x14006084f  test    eax, eax
0x140060851  jnz     short loc_140060860
0x140060853  mov     rax, [r12]
0x140060857  cmp     dword ptr [rax+3B4h], 0
0x14006085e  jz      short loc_140060876
0x140060860  mov     rdx, [rsi+108h]
0x140060867  xor     ecx, ecx
0x140060869  mov     eax, r14d
0x14006086c  lock cmpxchg [rdx+28h], ecx
0x140060871  jmp     loc_140060E58
0x140060876  mov     rcx, [rsi+108h]
0x14006087d  xor     eax, eax
0x14006087f  lock cmpxchg [rcx+28h], r14d
0x140060885  cmp     eax, 1
0x140060888  jz      loc_140060E58
0x14006088e  mov     rcx, [rsi+108h]
0x140060895  mov     r9d, 0Ah; TolerableDelay
0x14006089b  xor     r8d, r8d; Period
0x14006089e  mov     rdx, 0FFFFFFFFFFFE2B40h; DueTime
0x1400608a5  mov     rax, [rcx+18h]
0x1400608a9  mov     rcx, [rcx+20h]; Timer
0x1400608ad  mov     [rsp+0F8h+Dpc], rax; Dpc
0x1400608b2  call    cs:__imp_KeSetCoalescableTimer
0x1400608b9  nop     dword ptr [rax+rax+00h]
0x1400608be  jmp     loc_140060E58
0x1400608c3  mov     rax, [r12]
0x1400608c7  mov     r9d, r13d
0x1400608ca  mov     rcx, [rsi+100h]
0x1400608d1  mov     r8b, 1
0x1400608d4  mov     rdx, rbp
0x1400608d7  mov     [rsp+0F8h+Dpc], rax
0x1400608dc  call    StorAttemptInsertDeviceQueue
0x1400608e1  test    al, al
0x1400608e3  jnz     loc_140060E58
0x1400608e9  mov     rcx, [rsp+0F8h+var_80]
0x1400608ee  mov     r8d, [rsi+40h]
0x1400608f2  cmp     byte ptr [rcx], 3
0x1400608f5  mov     r14d, [rcx+8]
0x1400608f9  setz    bl
0x1400608fc  mov     eax, r14d
0x1400608ff  xor     edx, edx
0x140060901  mov     [rsp+0F8h+var_98], bl
0x140060905  div     r8d
0x140060908  test    edx, edx
0x14006090a  jnz     loc_140060D69
0x140060910  mov     rdi, [rcx+18h]
0x140060914  xor     edx, edx
0x140060916  mov     rax, rdi
0x140060919  div     r8
0x14006091c  mov     [rsp+0F8h+var_88], rax
0x140060921  mov     r9, rax
0x140060924  test    rdx, rdx
0x140060927  jnz     loc_140060D69
0x14006092d  mov     rcx, [rsi+1B0h]
0x140060934  cmp     rax, rcx
0x140060937  jnb     loc_140060D69
0x14006093d  mov     eax, r14d
0x140060940  sub     rcx, r9
0x140060943  div     r8d
0x140060946  mov     [rsp+0F8h+var_70], rax
0x14006094e  cmp     rcx, rax
0x140060951  jb      loc_140060D69
0x140060957  mov     rax, [r12]
0x14006095b  mov     rcx, [rax+80h]
0x140060962  mov     rax, [rcx+538h]
0x140060969  test    rax, rax
0x14006096c  jz      short loc_14006098F
0x14006096e  mov     eax, [rax+1Ch]
0x140060971  test    eax, eax
0x140060973  jz      short loc_14006098F
0x140060975  mov     rax, [r12]
0x140060979  mov     edx, r14d
0x14006097c  mov     rcx, [rax+80h]
0x140060983  mov     rcx, [rcx+538h]
0x14006098a  call    DlrmProcessReadWriteRequest
0x14006098f  mov     r10, [r12]
0x140060993  mov     rax, [r10+80h]
  ... truncated ...
```
