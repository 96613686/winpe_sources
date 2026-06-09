# NvmeProcessPendingIoInSpecifiedGroup

- ea: `0x140133400`
- end: `0x140134380`
- name: `NvmeProcessPendingIoInSpecifiedGroup`
- size: `3968`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14012f7a0`

## callees

- `0x14003ea90`
- `0x140042b60`
- `0x140043ca0`
- `0x140060e90`
- `0x140062190`
- `0x140065dc0`
- `0x140066260`
- `0x140124160`
- `0x14012f040`
- `0x14012f180`
- `0x140133400`
- `0x1401348c0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140133f20`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140133f20`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140133d33`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140133d7d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140133d33`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140133d7d`
- `ntoskrnl!PoFxIdleComponent` at `0x140134141`
- `ntoskrnl!PoFxIdleComponent` at `0x140134190`
- `ntoskrnl!PoFxIdleComponent` at `0x140134141`
- `ntoskrnl!PoFxIdleComponent` at `0x140134190`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14013411b`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14013411b`
- `ntoskrnl!KeSetEvent` at `0x1401336af`
- `ntoskrnl!KeSetEvent` at `0x1401336af`
- `ntoskrnl!KeLowerIrql` at `0x1401336e1`
- `ntoskrnl!KeLowerIrql` at `0x140133c60`
- `ntoskrnl!KeLowerIrql` at `0x140133cfb`
- `ntoskrnl!KeLowerIrql` at `0x1401341ff`
- `ntoskrnl!KeLowerIrql` at `0x1401336e1`
- `ntoskrnl!KeLowerIrql` at `0x140133c60`
- `ntoskrnl!KeLowerIrql` at `0x140133cfb`
- `ntoskrnl!KeLowerIrql` at `0x1401341ff`
- `ntoskrnl!KfRaiseIrql` at `0x1401335a0`
- `ntoskrnl!KfRaiseIrql` at `0x140133b8b`
- `ntoskrnl!KfRaiseIrql` at `0x140133cc2`
- `ntoskrnl!KfRaiseIrql` at `0x1401335a0`
- `ntoskrnl!KfRaiseIrql` at `0x140133b8b`
- `ntoskrnl!KfRaiseIrql` at `0x140133cc2`
- `ntoskrnl!IoQueueWorkItem` at `0x1401336d1`
- `ntoskrnl!IoQueueWorkItem` at `0x1401336d1`
- `ntoskrnl!IofCompleteRequest` at `0x1401340be`
- `ntoskrnl!IofCompleteRequest` at `0x1401340be`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140134169`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140134169`
- `ntoskrnl!ExQueryDepthSList` at `0x140133543`
- `ntoskrnl!ExQueryDepthSList` at `0x140133581`
- `ntoskrnl!ExQueryDepthSList` at `0x14013361e`
- `ntoskrnl!ExQueryDepthSList` at `0x140133543`
- `ntoskrnl!ExQueryDepthSList` at `0x140133581`
- `ntoskrnl!ExQueryDepthSList` at `0x14013361e`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1401342d5`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1401342d5`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140133753`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140133753`
- `ntoskrnl!IoRecordIoAttribution` at `0x14013376a`
- `ntoskrnl!IoRecordIoAttribution` at `0x14013376a`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140133718`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140133718`

## pseudocode

```c
char __fastcall NvmeProcessPendingIoInSpecifiedGroup(__int64 a1, unsigned int a2)
{
  bool v2; // zf
  __int64 v3; // rax
  int v4; // r12d
  unsigned int v5; // r15d
  __int64 v6; // r13
  union _SLIST_HEADER *v7; // r9
  unsigned int v8; // r14d
  unsigned int v9; // edx
  __int64 v10; // rbx
  unsigned int v11; // eax
  char v12; // si
  int v13; // ecx
  unsigned int v14; // edi
  __int64 v15; // rbx
  unsigned int v16; // edx
  unsigned int v17; // r8d
  unsigned int v18; // edx
  KIRQL v19; // di
  unsigned __int32 v20; // r9d
  signed __int32 v21; // ecx
  ULONG_PTR v22; // rsi
  unsigned int v23; // edx
  unsigned int v24; // r8d
  unsigned int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // r15d
  __int64 v32; // r9
  unsigned __int8 *v33; // rax
  __int64 v34; // rdi
  ULONG_PTR v35; // r14
  char *v36; // rdi
  PSLIST_ENTRY v37; // r13
  __int64 v38; // r11
  __int64 v39; // rbx
  unsigned int v40; // r12d
  unsigned __int64 v41; // r8
  __int16 v42; // di
  unsigned __int64 v43; // rbx
  unsigned __int64 v44; // r12
  __int16 v45; // r13
  signed __int32 v46; // eax
  int v47; // eax
  int v48; // r9d
  __int64 v49; // rax
  unsigned __int64 v50; // rbx
  unsigned int v51; // edi
  unsigned int v52; // r15d
  unsigned __int64 Next; // rdi
  unsigned __int64 v54; // r8
  unsigned __int64 v55; // rbx
  unsigned __int64 v56; // r9
  unsigned __int64 v57; // rcx
  unsigned int v58; // edx
  char v59; // al
  unsigned int v60; // edx
  unsigned int v61; // eax
  __int64 NVMeSGLBufferContext; // rax
  __int64 v63; // r15
  char v64; // al
  __int64 v65; // rax
  int v66; // ebx
  __int64 v67; // rdi
  KIRQL v68; // r13
  __int64 v69; // rbx
  __int64 v70; // rdx
  __int64 v71; // rdi
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r12
  unsigned __int8 v75; // di
  __int64 v76; // rbx
  KIRQL v77; // r13
  __int64 v78; // rdx
  __int64 v79; // rbx
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rax
  int v84; // eax
  unsigned __int64 v85; // r15
  unsigned __int64 v86; // rcx
  __int16 v87; // r12
  __int64 v88; // r11
  unsigned int v89; // edx
  char v90; // al
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // r9
  int v93; // r9d
  __int64 v94; // r13
  PSLIST_ENTRY v95; // rax
  __int64 NewNVMePrpListBufferEntry; // rax
  __int64 v97; // r10
  __int64 v98; // r8
  int v99; // eax
  int v100; // eax
  __int64 v101; // rax
  __int64 v102; // rbx
  __int64 v103; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v104; // rcx
  __int64 v105; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v106; // rcx
  __int64 v107; // rax
  char v108; // al
  __int64 v110; // rax
  __int64 v111; // rcx
  unsigned int v112; // eax
  __int64 v113; // rdx
  _DWORD *v114; // rax
  int v115; // [rsp+28h] [rbp-B1h]
  int v116; // [rsp+38h] [rbp-A1h]
  __int64 v117; // [rsp+40h] [rbp-99h]
  int v118; // [rsp+48h] [rbp-91h]
  unsigned __int8 v119; // [rsp+60h] [rbp-79h]
  char v120; // [rsp+62h] [rbp-77h]
  unsigned __int8 v121; // [rsp+62h] [rbp-77h]
  char v122; // [rsp+63h] [rbp-76h] BYREF
  unsigned __int8 v123; // [rsp+64h] [rbp-75h]
  int v124; // [rsp+68h] [rbp-71h]
  int v125; // [rsp+6Ch] [rbp-6Dh]
  PSLIST_ENTRY ListEntry; // [rsp+70h] [rbp-69h]
  int v127[2]; // [rsp+78h] [rbp-61h]
  unsigned __int64 v128; // [rsp+80h] [rbp-59h]
  __int64 v129; // [rsp+88h] [rbp-51h]
  unsigned __int64 v130; // [rsp+90h] [rbp-49h]
  __int16 v131[2]; // [rsp+98h] [rbp-41h] BYREF
  unsigned int v132; // [rsp+9Ch] [rbp-3Dh]
  int v133; // [rsp+A0h] [rbp-39h] BYREF
  int v134; // [rsp+A4h] [rbp-35h]
  __int64 v135; // [rsp+A8h] [rbp-31h] BYREF
  union _SLIST_HEADER *v136; // [rsp+B0h] [rbp-29h]
  __int64 v137; // [rsp+B8h] [rbp-21h]
  __int64 v138; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v139; // [rsp+C8h] [rbp-11h]
  __int64 v140; // [rsp+D0h] [rbp-9h]
  __int128 WatchdogInformation; // [rsp+D8h] [rbp-1h] BYREF
  __int128 WatchdogInformation_16; // [rsp+E8h] [rbp+Fh] BYREF

  v2 = (*(_BYTE *)(a1 + 136) & 2) == 0;
  v3 = *(_QWORD *)(a1 + 1112);
  v4 = *(_DWORD *)(a1 + 656);
  v5 = a2;
  v124 = a2;
  v137 = a1;
  v129 = a2;
  v6 = *(_QWORD *)(v3 + 8LL * a2);
  v140 = v6;
  v134 = v4;
  if ( v2 )
    v7 = (union _SLIST_HEADER *)(192LL * *(unsigned __int16 *)(*(_QWORD *)(a1 + 872) + 2LL * a2)
                               + *(_QWORD *)(a1 + 728)
                               - 192LL);
  else
    v7 = (union _SLIST_HEADER *)(*(_QWORD *)(a1 + 728) + 192LL * a2);
  v8 = *(_DWORD *)(v6 + 64);
  v132 = v8;
  v125 = v8;
  v136 = v7;
  while ( 2 )
  {
    v9 = v8;
    while ( 1 )
    {
      v10 = *(_QWORD *)(v6 + 8LL * v8 + 264);
      if ( v10 )
      {
        if ( **(_DWORD **)(v10 + 16) )
          return 0;
        if ( *(_DWORD *)v10 || *(_DWORD *)(v10 + 48) != *(_DWORD *)(v10 + 52) )
          break;
      }
      if ( v4 != 1 )
      {
        v11 = v8 + 1;
        v8 = 0;
        if ( v11 < *(_DWORD *)(v6 + 4) )
          v8 = v11;
        v132 = v8;
        if ( v9 != v8 )
          continue;
      }
      goto LABEL_14;
    }
    if ( !ExQueryDepthSList(v7 + 4) )
    {
      v12 = 1;
      goto LABEL_15;
    }
    v135 = 0;
    v19 = KfRaiseIrql(2u);
    do
    {
      v20 = *(_DWORD *)(v10 + 52);
      if ( v20 == *(_DWORD *)(v10 + 48) )
      {
        if ( _InterlockedCompareExchange((volatile signed __int32 *)v10, 0, 1) == 1 )
        {
          v107 = *(_QWORD *)(v10 + 24);
          if ( *(_BYTE *)(*(_QWORD *)(v10 + 16) + 20LL) == 1 )
            _InterlockedDecrement((volatile signed __int32 *)(v107 + 956));
          else
            _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v107 + 16) + 952LL));
        }
        KeLowerIrql(v19);
        goto LABEL_174;
      }
      v21 = 0;
      if ( v20 + 1 < *(_DWORD *)(*(_QWORD *)(v10 + 16) + 4LL) )
        v21 = v20 + 1;
    }
    while ( v20 != _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 52), v21, v20) );
    do
      v22 = _InterlockedExchange64((volatile __int64 *)(8LL * v20 + *(_QWORD *)(v10 + 56)), 0);
    while ( !v22 );
    if ( !*(_DWORD *)(*(_QWORD *)(v10 + 16) + 16LL)
      && (*(_DWORD *)v10 == 2
       || ExQueryDepthSList((PSLIST_HEADER)(*(_QWORD *)(v10 + 32) + 16LL * *(unsigned int *)(v10 + 8)))) )
    {
      if ( *(_DWORD *)(v10 + 48) == *(_DWORD *)(v10 + 52)
        || ((v23 = *(_DWORD *)(v10 + 48), v24 = *(_DWORD *)(v10 + 52), v23 != v24)
          ? (v23 <= v24
           ? ((v26 = *(_QWORD *)(v10 + 24), *(_BYTE *)(*(_QWORD *)(v10 + 16) + 20LL))
            ? (v27 = *(_QWORD *)(v26 + 1024))
            : (v27 = *(_QWORD *)(v26 + 256)),
              v25 = *(_DWORD *)(v27 + 4) - v24 + v23)
           : (v25 = v23 - v24))
          : (v25 = 0),
            v25 <= *(_DWORD *)(*(_QWORD *)(v10 + 16) + 8LL)) )
      {
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v10 + 16) + 16LL), 1, 0) )
        {
          v28 = *(_QWORD *)(v10 + 24);
          if ( *(_BYTE *)(*(_QWORD *)(v10 + 16) + 20LL) )
            IoQueueWorkItem(
              *(PIO_WORKITEM *)(v28 + 1032),
              NvmeControllerRefillShadowQueueRoutine,
              DelayedWorkQueue,
              *(PVOID *)(v10 + 24));
          else
            KeSetEvent((PRKEVENT)(v28 + 480), 0, 0);
        }
      }
    }
    KeLowerIrql(v19);
    if ( (*(_BYTE *)(v137 + 136) & 2) != 0 )
    {
      v31 = NvmeNamespaceProcessRequest(*(_QWORD *)(v10 + 24), v22, v5);
      goto LABEL_164;
    }
    if ( (int)IoGetIoAttributionHandle(v22, &v135) >= 0 )
    {
      v33 = *(unsigned __int8 **)(v22 + 184);
      v34 = v135;
      WatchdogInformation = 0;
      LODWORD(WatchdogInformation) = 1;
      WatchdogInformation_16 = 0;
      DWORD1(WatchdogInformation) = *v33 | 0x200;
      *((_QWORD *)&WatchdogInformation_16 + 1) = KeQueryUnbiasedInterruptTimePrecise((PULONG64)&WatchdogInformation_16 + 1);
      IoRecordIoAttribution(v34, &WatchdogInformation);
    }
    v35 = *(_QWORD *)(v10 + 24);
    v36 = *(char **)(v22 + 184);
    v37 = 0;
    v131[0] = 0;
    LOBYTE(v30) = 0;
    v138 = 0;
    LOBYTE(v32) = 0;
    v38 = *(_QWORD *)(v35 + 16);
    v133 = 0;
    v122 = 0;
    v39 = *((_QWORD *)v36 + 1);
    v40 = v39;
    v41 = HIDWORD(*(_QWORD *)(v38 + 136));
    LOBYTE(v41) = v41 & 1;
    ListEntry = 0;
    v130 = v41;
    v119 = 0;
    if ( v39 == 0x8765432100000003uLL )
    {
      v29 = *((_QWORD *)v36 + 3);
      v128 = v29;
    }
    else
    {
      v29 = 0;
      v128 = 0;
      if ( v39 == 0xFEDCBA9000000000uLL )
      {
        v37 = (PSLIST_ENTRY)*((_QWORD *)v36 + 3);
        ListEntry = v37;
      }
    }
    if ( (unsigned int)(*(_DWORD *)(v35 + 96) - 5) <= 1 )
    {
      v122 = 1;
      v31 = -1073741810;
      goto LABEL_80;
    }
    v123 = *v36;
    v30 = v123;
    v120 = v123 == 3;
    if ( !v29 )
    {
      v52 = *(_DWORD *)(*(_QWORD *)(v38 + 128) + 208LL);
      v127[0] = v52;
      if ( (_BYTE)v41 )
      {
        Next = *((_QWORD *)v36 + 3);
      }
      else
      {
        if ( !v37 )
        {
          v54 = *(unsigned int *)(v35 + 64);
          if ( (unsigned int)v39 % (unsigned int)v54
            || (v55 = *((_QWORD *)v36 + 3), v130 = v55 / v54, v56 = v55 / v54, v55 % v54)
            || (v57 = *(_QWORD *)(v35 + 432), v55 / v54 >= v57)
            || (*(_QWORD *)v127 = v40 / (unsigned int)v54, v57 - v130 < *(_QWORD *)v127) )
          {
            v31 = -1073741811;
            goto LABEL_149;
          }
          if ( v40 > v52
            || (v58 = *(_DWORD *)(v35 + 428)) != 0
            && (v40 > v58
             || ((v59 = *(_BYTE *)(v35 + 427), v56 = v58, !v59)
               ? (v54 = v40 / (unsigned __int64)v58, v61 = v40 / v58 + (v40 % v58 - 1LL + v58 + v55 % v58) / v58)
               : (v60 = v58 - 1,
                  v54 = v60 & (unsigned int)v55,
                  v61 = ((unsigned __int64)v40 >> v59) + (((v40 & v60) + v56 + v54 - 1) >> v59)),
                 v61 > 1)) )
          {
            v51 = v124;
            v84 = NvmeSplitIoParallel(v35, v22, v55, v52, v124, 0, 0, 0);
            v50 = v128;
            v31 = v84;
            goto LABEL_110;
          }
          NVMeSGLBufferContext = GetNVMeSGLBufferContext(v38, (unsigned int)v124, v54, v56);
          ListEntry = (PSLIST_ENTRY)NVMeSGLBufferContext;
          v63 = NVMeSGLBufferContext;
          if ( !NVMeSGLBufferContext )
          {
            v31 = -1073741670;
            goto LABEL_149;
          }
          v2 = v123 == 3;
          *(_QWORD *)(NVMeSGLBufferContext + 40) = v22;
          v64 = *(_BYTE *)(NVMeSGLBufferContext + 126) & 0xFE;
          *(_QWORD *)(v63 + 96) = v55;
          *(_QWORD *)(v63 + 32) = v35;
          *(_QWORD *)(v63 + 104) = v130;
          *(_DWORD *)(v63 + 112) = v127[0];
          *(_QWORD *)(v63 + 64) = 0;
          *(_QWORD *)(v63 + 72) = 0;
          *(_BYTE *)(v63 + 126) = v64 | v2;
          *(_DWORD *)(v63 + 116) = v40;
          *(_QWORD *)(v63 + 56) = *((_QWORD *)v36 + 3);
          v65 = *((_QWORD *)v36 + 1);
          *((_QWORD *)v36 + 3) = v63;
          *(_QWORD *)(v63 + 48) = v65;
          *((_QWORD *)v36 + 1) = 0xFEDCBA9000000000uLL;
          v66 = *(unsigned __int16 *)(v63 + 124);
          v67 = *(_QWORD *)(v63 + 16);
          *(_QWORD *)v127 = *(unsigned int *)(*(_QWORD *)(v22 + 8) + 44LL) + *(_QWORD *)(*(_QWORD *)(v22 + 8) + 32LL);
          *(_QWORD *)(v63 + 80) = *(_QWORD *)v127;
          v139 = *(_QWORD *)(v22 + 8);
          v130 = *(_QWORD *)(v35 + 16);
          v68 = KfRaiseIrql(2u);
          v118 = v66;
          v69 = *(_QWORD *)v127;
          v117 = v67;
          v70 = *(_QWORD *)(v130 + 128);
          v71 = v139;
          v72 = *(_QWORD *)(v70 + 1160);
          v73 = *(_QWORD *)(v70 + 8);
          v123 = v123 != 3;
          LOBYTE(v116) = v123;
          v31 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, unsigned int, __int64 (__fastcall *)(), __int64, int, __int64, int))(*(_QWORD *)(v72 + 8) + 112LL))(
                  v72,
                  v73,
                  v139,
                  *(_QWORD *)v127,
                  v40,
                  NvmeContinueScatterGatherProcessIO,
                  v63,
                  v116,
                  v117,
                  v118);
          if ( v31 == -1073741789 )
          {
            LOBYTE(v116) = v123;
            v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, unsigned int, __int64 (__fastcall *)(), PSLIST_ENTRY, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v130 + 128) + 1160LL) + 8LL) + 88LL))(
                    *(_QWORD *)(*(_QWORD *)(v130 + 128) + 1160LL),
                    *(_QWORD *)(*(_QWORD *)(v130 + 128) + 8LL),
                    v71,
                    v69,
                    v40,
                    NvmeContinueScatterGatherProcessIO,
                    ListEntry,
                    v116);
          }
          if ( v68 < 2u )
            KeLowerIrql(v68);
          v50 = v128;
          if ( v31 >= 0 )
            v31 = 259;
LABEL_109:
          v51 = v124;
          v37 = ListEntry;
          goto LABEL_110;
        }
        Next = (unsigned __int64)v37[6].Next;
        LODWORD(v39) = HIDWORD(v37[7].Next);
        v37[4].Next = 0;
        *((_QWORD *)&v37[4].Next + 1) = 0;
      }
      v41 = *(unsigned int *)(v35 + 64);
      v29 = (unsigned int)v39 % (unsigned int)v41;
      if ( (unsigned int)v39 % (unsigned int)v41
        || (v29 = Next % v41, v85 = Next / v41, Next % v41)
        || (v86 = *(_QWORD *)(v35 + 432), Next / v41 >= v86)
        || (LODWORD(v29) = (unsigned int)v39 % (unsigned int)v41,
            v87 = (unsigned int)v39 / (unsigned int)v41,
            v86 - v85 < (unsigned int)v39 / (unsigned int)v41) )
      {
        v31 = -1073741811;
        v30 = 0;
      }
      else
      {
        v88 = *(_QWORD *)(v35 + 16);
        if ( (unsigned int)v39 > *(_DWORD *)(*(_QWORD *)(v88 + 128) + 208LL)
          || (v89 = *(_DWORD *)(v35 + 428)) != 0
          && ((unsigned int)v39 > v89
           || ((v90 = *(_BYTE *)(v35 + 427)) == 0
             ? (LODWORD(v92) = (unsigned int)v39 / v89, v91 = ((unsigned int)v39 % v89 - 1LL + v89 + Next % v89) / v89)
             : (v91 = (((unsigned int)v39 & (v89 - 1)) + v89 + (unsigned __int64)((v89 - 1) & (unsigned int)Next) - 1) >> v90,
                v92 = (unsigned __int64)(unsigned int)v39 >> *(_BYTE *)(v35 + 427)),
               (unsigned int)(v92 + v91) > 1)) )
        {
          v100 = NvmeSplitIoParallel(v35, v22, Next, v127[0], v124, 0, 0, 0);
          v30 = 0;
          v31 = v100;
          v32 = 0;
        }
        else
        {
          v93 = 0;
          v94 = v129;
          if ( (((unsigned int)v39
               + ((*(_DWORD *)(*(_QWORD *)(v22 + 8) + 32LL) + *(_DWORD *)(*(_QWORD *)(v22 + 8) + 44LL)) & 0xFFF)
               + 4095LL)
              & 0xFFFFFFFFFFFFF000uLL) <= 0x2000
            || (v95 = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v88 + 880) + 8 * v129)),
                v93 = (int)v95,
                v95)
            || (NewNVMePrpListBufferEntry = AllocateNewNVMePrpListBufferEntry(*(_QWORD *)(v35 + 16), (unsigned int)v94),
                v93 = NewNVMePrpListBufferEntry,
                NewNVMePrpListBufferEntry) )
          {
            v97 = *(_QWORD *)(v35 + 16);
            if ( (*(_BYTE *)(v97 + 136) & 2) != 0 )
              v98 = *(_QWORD *)(v97 + 728) + 192 * v94;
            else
              LODWORD(v98) = 192 * *(unsigned __int16 *)(*(_QWORD *)(v97 + 872) + 2 * v94)
                           + *(_DWORD *)(v97 + 728)
                           - 192;
            LOBYTE(v115) = 0;
            v99 = NvmeSubmitIoToSQ(v35, v22, v98, v93, v124, v115, v39, Next, v85, v87, v120, 0);
            v30 = 0;
            v31 = v99;
            v32 = 0;
          }
          else
          {
            NvmeNamespaceQueueIo(v35, v22, (unsigned int)v94);
            v30 = 0;
            v31 = -2147483631;
            v32 = 0;
          }
        }
      }
      goto LABEL_80;
    }
    v31 = 0;
    LOBYTE(v30) = 0;
    v42 = 0;
    v121 = 0;
    v127[0] = 0;
    if ( !(_BYTE)v41 )
    {
      _InterlockedIncrement16((volatile signed __int16 *)(v29 + 120));
      v119 = 1;
    }
LABEL_58:
    v43 = v29;
    while ( 1 )
    {
      v44 = *(_QWORD *)(v43 + 96);
      v45 = *(_WORD *)(v43 + 34);
      v46 = _InterlockedCompareExchange((volatile signed __int32 *)(v43 + 104), 4, 3);
      if ( (_BYTE)v41 )
      {
        if ( v46 != 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v43 + 104), 4, 1) != 1 )
          goto LABEL_72;
      }
      else if ( v46 != 3 )
      {
        if ( *(_DWORD *)(v43 + 104) == 1 )
          ++v42;
        goto LABEL_72;
      }
      v47 = NvmeSendSplitIo(v43, v124, 0, 0, (__int64)&v122, (__int64)&v138, (__int64)&v133, (__int64)v131, v30);
      v31 = v47;
      if ( v47 != 259 )
        break;
      HIWORD(v48) = HIWORD(v127[0]);
      v49 = *(_QWORD *)(v35 + 16);
      LOWORD(v48) = LOWORD(v127[0]) + 1;
      v30 = (unsigned __int16)(LOWORD(v127[0]) + 1);
      v127[0] = v48;
      LOBYTE(v30) = (unsigned int)v30 % *(unsigned __int8 *)(v49 + 1730) == 0;
      v121 = v30;
LABEL_71:
      v41 = v130;
      v29 = v128;
LABEL_72:
      v43 = v44;
      if ( v42 && !v44 )
      {
        v42 = 0;
        goto LABEL_58;
      }
      if ( !v44 )
      {
        LOBYTE(v30) = 1;
        goto LABEL_79;
      }
    }
    if ( v47 != -2147483631 )
    {
      if ( !v45 )
      {
        v122 = 1;
LABEL_78:
        v30 = 0;
        goto LABEL_79;
      }
      if ( v122 )
        goto LABEL_78;
      v30 = v121;
      goto LABEL_71;
    }
    _InterlockedCompareExchange((volatile signed __int32 *)(v43 + 104), 3, 4);
    NvmeNamespaceQueueIo(v35, *(_QWORD *)(v43 + 24), (unsigned int)v124);
    LOBYTE(v30) = 1;
LABEL_79:
    v32 = v119;
LABEL_80:
    v50 = v128;
    if ( !(_BYTE)v130 && (_BYTE)v32 )
      _InterlockedDecrement16((volatile signed __int16 *)(v128 + 120));
    if ( (_BYTE)v30 )
      goto LABEL_109;
    v37 = ListEntry;
    v51 = v124;
    if ( v50 )
      _interlockedbittestandreset((volatile signed __int32 *)(v50 + 108), 0);
LABEL_110:
    if ( v31 != -2147483631 && v31 < 1 )
    {
      if ( v37 )
      {
        v74 = *((_QWORD *)&v37[1].Next + 1);
        if ( v74 )
        {
          v75 = *((_BYTE *)&v37[7].Next + 14) & 1;
          v76 = *(_QWORD *)(*(_QWORD *)(v35 + 16) + 128LL);
          v77 = KfRaiseIrql(2u);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(*(_QWORD *)(v76 + 1160) + 8LL) + 96LL))(
            *(_QWORD *)(v76 + 1160),
            v74,
            v75 ^ 1u);
          if ( v77 < 2u )
            KeLowerIrql(v77);
          v37 = ListEntry;
        }
        v78 = *((_QWORD *)&v37[5].Next + 1);
        v79 = v129;
        if ( v78 )
        {
          v80 = *(_QWORD *)(v35 + 16);
          *(_QWORD *)(v78 + 88) = 0;
          *(_DWORD *)(v78 + 108) = 0;
          *(_DWORD *)(v78 + 104) = 0;
          ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v80 + 888) + 8 * v79), (PSLIST_ENTRY)v78);
        }
        v81 = *(_QWORD *)(v35 + 16);
        v82 = *(_QWORD *)(*((_QWORD *)&v37[2].Next + 1) + 184LL);
        *(_QWORD *)(v82 + 8) = v37[3].Next;
        *(_QWORD *)(v82 + 24) = *((_QWORD *)&v37[3].Next + 1);
        v83 = *((unsigned int *)&v37[7].Next + 2);
        *((_QWORD *)&v37[1].Next + 1) = 0;
        *((_QWORD *)&v37[5].Next + 1) = 0;
        *((_BYTE *)&v37[7].Next + 14) = 0;
        ExpInterlockedPushEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)(v81 + 896) + 8 * v83), v37);
        if ( (*(_BYTE *)(v22 + 151) & 1) != 0 )
          _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v35 + 696) + 8 * v79));
        goto LABEL_151;
      }
      if ( v50 )
      {
        if ( v122 )
        {
          FreeAllSglAndContextInChainedSplitIoContext(*(_QWORD *)(v35 + 16), v50, v41, v32);
          FreeNVMeChainedIoSplitContext(*(_QWORD *)(v35 + 16), v51, v50, v22);
          goto LABEL_149;
        }
      }
      else
      {
LABEL_149:
        v79 = v129;
        if ( (*(_BYTE *)(v22 + 151) & 1) != 0 )
          _InterlockedDecrement(*(volatile signed __int32 **)(*(_QWORD *)(v35 + 696) + 8 * v129));
LABEL_151:
        *(_DWORD *)(v22 + 48) = v31;
        IofCompleteRequest((PIRP)v22, 0);
        v101 = *(_QWORD *)(v35 + 128);
        if ( !*(_BYTE *)v101 )
        {
          v30 = *(_QWORD *)(*(_QWORD *)(v101 + 24) + 8 * v79);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v30, 0xFFFFFFFF) == 1 )
          {
            v102 = *(_QWORD *)(*(_QWORD *)(v35 + 16) + 128LL);
            v103 = *(_QWORD *)(v35 + 128);
            if ( v103 )
            {
              if ( *(_QWORD *)(v103 + 8) )
              {
                v104 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v103 + 40);
                if ( v104 )
                {
                  if ( ExAcquireRundownProtectionCacheAware(v104) )
                  {
                    PoFxIdleComponent(**(_QWORD **)(*(_QWORD *)(v35 + 128) + 8LL), 0, 2);
                    v105 = *(_QWORD *)(v35 + 128);
                    if ( v105 )
                    {
                      if ( *(_QWORD *)(v105 + 8) )
                      {
                        v106 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v105 + 40);
                        if ( v106 )
                          ExReleaseRundownProtectionCacheAware(v106);
                      }
                    }
                  }
                }
              }
            }
            v30 = *(_QWORD *)(v102 + 168);
            if ( *(_BYTE *)v30 == 1 )
              PoFxIdleComponent(**(_QWORD **)(v30 + 8), 0, 2);
          }
        }
      }
    }
    v8 = v132;
    v6 = v140;
    v4 = v134;
LABEL_164:
    if ( v31 == 259 )
    {
LABEL_167:
      if ( v4 != 1 )
        goto LABEL_175;
LABEL_178:
      LOBYTE(v29) = 5;
      LOBYTE(v30) = 10;
      v108 = StorCheckDpcWatchdogTimerExpire(v30, v29);
      v5 = v124;
      v12 = 1;
      v7 = v136;
      if ( v108 )
        return v12;
      continue;
    }
    break;
  }
  if ( v31 != -2147483631 )
  {
    if ( v31 != -2147483622 )
      goto LABEL_167;
LABEL_174:
    if ( v4 != 1 )
    {
LABEL_175:
      v30 = ++v8;
      if ( v8 >= *(_DWORD *)(v6 + 4) )
        v8 = 0;
      v132 = v8;
      goto LABEL_178;
    }
  }
LABEL_14:
  v12 = 0;
LABEL_15:
  v13 = v125;
  v14 = v125;
  while ( 1 )
  {
    v15 = *(_QWORD *)(v6 + 8LL * v14 + 264);
    if ( v15 )
    {
      if ( *(_DWORD *)v15 == 2
        || ExQueryDepthSList((PSLIST_HEADER)(*(_QWORD *)(v15 + 32) + 16LL * *(unsigned int *)(v15 + 8))) )
      {
        if ( *(_DWORD *)(v15 + 48) == *(_DWORD *)(v15 + 52)
          || ((v16 = *(_DWORD *)(v15 + 48), v17 = *(_DWORD *)(v15 + 52), v16 != v17)
            ? (v16 <= v17
             ? ((v110 = *(_QWORD *)(v15 + 24), *(_BYTE *)(*(_QWORD *)(v15 + 16) + 20LL))
              ? (v111 = *(_QWORD *)(v110 + 1024))
              : (v111 = *(_QWORD *)(v110 + 256)),
                v18 = *(_DWORD *)(v111 + 4) - v17 + v16)
             : (v18 = v16 - v17))
            : (v18 = 0),
              v18 <= *(_DWORD *)(*(_QWORD *)(v15 + 16) + 8LL)) )
        {
          v12 = 1;
          if ( (unsigned int)StorRefillShadowQueue(*(_QWORD *)(v15 + 16), v14, 0) == 4 )
            return v12;
        }
      }
      v13 = v125;
    }
    if ( v4 == 1 )
      break;
    v112 = v14 + 1;
    v14 = 0;
    if ( v112 < *(_DWORD *)(v6 + 4) )
      v14 = v112;
    if ( v13 == v14 )
      break;
    WatchdogInformation = 0;
    LODWORD(WatchdogInformation_16) = 0;
    if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)&WatchdogInformation) >= 0
      && (DWORD2(WatchdogInformation)
       && 100 * (unsigned __int64)HIDWORD(WatchdogInformation) < 5 * (unsigned __int64)DWORD2(WatchdogInformation)
       || (_DWORD)WatchdogInformation
       && 100 * (unsigned __int64)DWORD1(WatchdogInformation) < 10 * (unsigned __int64)(unsigned int)WatchdogInformation) )
    {
      return 1;
    }
    v13 = v125;
  }
  if ( !v12 )
  {
    v113 = 0;
    if ( *(_DWORD *)(v6 + 4) )
    {
      while ( 1 )
      {
        v114 = *(_DWORD **)(v6 + 8 * v113 + 264);
        if ( v114 )
        {
          if ( *v114 || v114[12] != v114[13] )
            break;
        }
        v113 = (unsigned int)(v113 + 1);
        if ( (unsigned int)v113 >= *(_DWORD *)(v6 + 4) )
          return v12;
      }
      return 1;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140133400  mov     [rsp-8+arg_10], rbx
0x140133405  push    rbp
0x140133406  push    rsi
0x140133407  push    rdi
0x140133408  push    r12
0x14013340a  push    r13
0x14013340c  push    r14
0x14013340e  push    r15
0x140133410  lea     rbp, [rsp-27h]
0x140133415  sub     rsp, 100h
0x14013341c  mov     rax, cs:__security_cookie
0x140133423  xor     rax, rsp
0x140133426  mov     [rbp+57h+var_38], rax
0x14013342a  test    byte ptr [rcx+88h], 2
0x140133431  mov     r8, rcx
0x140133434  mov     rax, [rcx+458h]
0x14013343b  mov     r12d, [rcx+290h]
0x140133442  mov     r15d, edx
0x140133445  mov     [rbp+57h+var_C8], r15d
0x140133449  mov     [rbp+57h+var_78], rcx
0x14013344d  mov     [rbp+57h+var_A8], r15
0x140133451  mov     r13, [rax+r15*8]
0x140133455  mov     [rbp+57h+var_60], r13
0x140133459  mov     [rbp+57h+var_8C], r12d
0x14013345d  jz      short loc_140133470
0x14013345f  lea     r9, [r15+r15*2]
0x140133463  shl     r9, 6
0x140133467  add     r9, [rcx+2D8h]
0x14013346e  jmp     short loc_140133495
0x140133470  mov     rax, [rcx+368h]
0x140133477  mov     r9, [r8+2D8h]
0x14013347e  add     r9, 0FFFFFFFFFFFFFF40h
0x140133485  movzx   ecx, word ptr [rax+r15*2]
0x14013348a  lea     rdx, [rcx+rcx*2]
0x14013348e  shl     rdx, 6
0x140133492  add     r9, rdx
0x140133495  mov     r14d, [r13+40h]
0x140133499  mov     esi, 1
0x14013349e  mov     [rbp+57h+var_94], r14d
0x1401334a2  mov     [rbp+57h+var_C4], r14d
0x1401334a6  mov     [rbp+57h+var_80], r9
0x1401334aa  nop     word ptr [rax+rax+00h]
0x1401334b0  mov     edx, r14d
0x1401334b3  nop     dword ptr [rax+00h]
0x1401334b7  nop     word ptr [rax+rax+00000000h]
0x1401334c0  mov     ebx, r14d
0x1401334c3  mov     rbx, [r13+rbx*8+108h]
0x1401334cb  test    rbx, rbx
0x1401334ce  jz      short loc_1401334F4
0x1401334d0  mov     rax, [rbx+10h]
0x1401334d4  cmp     dword ptr [rax], 0
0x1401334d7  jnz     loc_140134255
0x1401334dd  cmp     dword ptr [rbx], 0
0x1401334e0  jnz     loc_14013357D
0x1401334e6  mov     ecx, [rbx+34h]
0x1401334e9  mov     eax, [rbx+30h]
0x1401334ec  cmp     eax, ecx
0x1401334ee  jnz     loc_14013357D
0x1401334f4  cmp     r12d, 1
0x1401334f8  jz      short loc_140133512
0x1401334fa  lea     eax, [r14+1]
0x1401334fe  xor     r14d, r14d
0x140133501  cmp     eax, [r13+4]
0x140133505  cmovb   r14d, eax
0x140133509  mov     [rbp+57h+var_94], r14d
0x14013350d  cmp     edx, r14d
0x140133510  jnz     short loc_1401334C0
0x140133512  xor     sil, sil
0x140133515  mov     ecx, [rbp+57h+var_C4]
0x140133518  mov     edi, ecx
0x14013351a  nop     word ptr [rax+rax+00h]
0x140133520  mov     eax, edi
0x140133522  mov     rbx, [r13+rax*8+108h]
0x14013352a  test    rbx, rbx
0x14013352d  jz      loc_1401342AF
0x140133533  cmp     dword ptr [rbx], 2
0x140133536  jz      short loc_140133558
0x140133538  mov     ecx, [rbx+8]
0x14013353b  shl     rcx, 4
0x14013353f  add     rcx, [rbx+20h]; SListHead
0x140133543  call    cs:__imp_ExQueryDepthSList
0x14013354a  nop     dword ptr [rax+rax+00h]
0x14013354f  test    ax, ax
0x140133552  jz      loc_1401342AC
0x140133558  mov     ecx, [rbx+34h]
0x14013355b  mov     eax, [rbx+30h]
0x14013355e  cmp     eax, ecx
0x140133560  jz      loc_140134292
0x140133566  mov     edx, [rbx+30h]
0x140133569  mov     r8d, [rbx+34h]
0x14013356d  cmp     edx, r8d
0x140133570  jnz     loc_14013425C
0x140133576  xor     edx, edx
0x140133578  jmp     loc_140134289
0x14013357d  lea     rcx, [r9+40h]; SListHead
0x140133581  call    cs:__imp_ExQueryDepthSList
0x140133588  nop     dword ptr [rax+rax+00h]
0x14013358d  test    ax, ax
0x140133590  jz      loc_14013424D
0x140133596  mov     cl, 2; NewIrql
0x140133598  mov     [rbp+57h+var_88], 0
0x1401335a0  call    cs:__imp_KfRaiseIrql
0x1401335a7  nop     dword ptr [rax+rax+00h]
0x1401335ac  movzx   edi, al
0x1401335af  nop
0x1401335b0  mov     r9d, [rbx+34h]
0x1401335b4  mov     ecx, [rbx+30h]
0x1401335b7  cmp     r9d, ecx
0x1401335ba  jz      loc_1401341CF
0x1401335c0  mov     rcx, [rbx+10h]
0x1401335c4  lea     r8d, [r9+1]
0x1401335c8  mov     eax, r9d
0x1401335cb  mov     edx, [rcx+4]
0x1401335ce  xor     ecx, ecx
0x1401335d0  cmp     r8d, edx
0x1401335d3  cmovb   ecx, r8d
0x1401335d7  lock cmpxchg [rbx+34h], ecx
0x1401335dc  jnz     short loc_1401335B0
0x1401335de  mov     ecx, r9d
0x1401335e1  shl     rcx, 3
0x1401335e5  nop     word ptr [rax+rax+00000000h]
0x1401335f0  mov     rax, [rbx+38h]
0x1401335f4  xor     esi, esi
0x1401335f6  xchg    rsi, [rcx+rax]
0x1401335fa  test    rsi, rsi
0x1401335fd  jz      short loc_1401335F0
0x1401335ff  mov     rax, [rbx+10h]
0x140133603  mov     ecx, [rax+10h]
0x140133606  test    ecx, ecx
0x140133608  jnz     loc_1401336DD
0x14013360e  cmp     dword ptr [rbx], 2
0x140133611  jz      short loc_140133633
0x140133613  mov     ecx, [rbx+8]
0x140133616  shl     rcx, 4
0x14013361a  add     rcx, [rbx+20h]; SListHead
0x14013361e  call    cs:__imp_ExQueryDepthSList
0x140133625  nop     dword ptr [rax+rax+00h]
0x14013362a  test    ax, ax
0x14013362d  jz      loc_1401336DD
0x140133633  mov     ecx, [rbx+34h]
0x140133636  mov     eax, [rbx+30h]
0x140133639  cmp     eax, ecx
0x14013363b  jz      short loc_140133683
0x14013363d  mov     edx, [rbx+30h]
0x140133640  mov     r8d, [rbx+34h]
0x140133644  cmp     edx, r8d
0x140133647  jnz     short loc_14013364D
0x140133649  xor     edx, edx
0x14013364b  jmp     short loc_14013367A
0x14013364d  jbe     short loc_140133654
0x14013364f  sub     edx, r8d
0x140133652  jmp     short loc_14013367A
0x140133654  mov     rax, [rbx+10h]
0x140133658  mov     rcx, [rbx+18h]
0x14013365c  cmp     byte ptr [rax+14h], 0
0x140133660  jnz     short loc_14013366B
0x140133662  mov     rax, [rcx+100h]
0x140133669  jmp     short loc_140133672
0x14013366b  mov     rax, [rcx+400h]
0x140133672  mov     ecx, [rax+4]
0x140133675  sub     ecx, r8d
0x140133678  add     edx, ecx
0x14013367a  mov     rax, [rbx+10h]
0x14013367e  cmp     edx, [rax+8]
0x140133681  ja      short loc_1401336DD
0x140133683  mov     rcx, [rbx+10h]
0x140133687  xor     eax, eax
0x140133689  mov     edx, 1
0x14013368e  lock cmpxchg [rcx+10h], edx
0x140133693  jnz     short loc_1401336DD
0x140133695  mov     rax, [rbx+10h]
0x140133699  mov     rcx, [rbx+18h]
0x14013369d  cmp     byte ptr [rax+14h], 0
0x1401336a1  jnz     short loc_1401336BD
0x1401336a3  add     rcx, 1E0h; Event
0x1401336aa  xor     r8d, r8d; Wait
0x1401336ad  xor     edx, edx; Increment
0x1401336af  call    cs:__imp_KeSetEvent
0x1401336b6  nop     dword ptr [rax+rax+00h]
0x1401336bb  jmp     short loc_1401336DD
0x1401336bd  mov     r9, rcx; Context
0x1401336c0  mov     r8d, edx; QueueType
0x1401336c3  mov     rcx, [rcx+408h]; IoWorkItem
0x1401336ca  lea     rdx, NvmeControllerRefillShadowQueueRoutine; WorkerRoutine
0x1401336d1  call    cs:__imp_IoQueueWorkItem
0x1401336d8  nop     dword ptr [rax+rax+00h]
0x1401336dd  movzx   ecx, dil; NewIrql
0x1401336e1  call    cs:__imp_KeLowerIrql
0x1401336e8  nop     dword ptr [rax+rax+00h]
0x1401336ed  mov     rcx, [rbp+57h+var_78]
0x1401336f1  test    byte ptr [rcx+88h], 2
0x1401336f8  jz      short loc_140133711
0x1401336fa  mov     rcx, [rbx+18h]
0x1401336fe  mov     r8d, r15d
0x140133701  mov     rdx, rsi
0x140133704  call    NvmeNamespaceProcessRequest
0x140133709  mov     r15d, eax
0x14013370c  jmp     loc_1401341A8
0x140133711  lea     rdx, [rbp+57h+var_88]
0x140133715  mov     rcx, rsi
0x140133718  call    cs:__imp_IoGetIoAttributionHandle
0x14013371f  nop     dword ptr [rax+rax+00h]
0x140133724  test    eax, eax
0x140133726  js      short loc_140133776
0x140133728  mov     rax, [rsi+0B8h]
0x14013372f  lea     rcx, [rbp+57h+QpcTimeStamp]; QpcTimeStamp
0x140133733  mov     rdi, [rbp+57h+var_88]
0x140133737  xorps   xmm0, xmm0
0x14013373a  movups  xmmword ptr [rbp+57h+WatchdogInformation.DpcTimeLimit], xmm0
0x14013373e  mov     [rbp+57h+WatchdogInformation.DpcTimeLimit], 1
0x140133745  movups  xmmword ptr [rbp+0Fh], xmm0
0x140133749  movzx   edx, byte ptr [rax]
0x14013374c  bts     edx, 9
0x140133750  mov     [rbp+57h+WatchdogInformation.DpcTimeCount], edx
0x140133753  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x14013375a  nop     dword ptr [rax+rax+00h]
0x14013375f  lea     rdx, [rbp+57h+WatchdogInformation]
0x140133763  mov     rcx, rdi
0x140133766  mov     [rbp+57h+QpcTimeStamp], rax
0x14013376a  call    cs:__imp_IoRecordIoAttribution
0x140133771  nop     dword ptr [rax+rax+00h]
0x140133776  mov     r14, [rbx+18h]
0x14013377a  xor     eax, eax
0x14013377c  mov     rdi, [rsi+0B8h]
0x140133783  xor     r13d, r13d
0x140133786  mov     [rbp+57h+var_98], ax
0x14013378a  xor     cl, cl
0x14013378c  mov     [rbp+57h+var_70], rax
0x140133790  xor     r9b, r9b
0x140133793  mov     r11, [r14+10h]
0x140133797  mov     [rbp+57h+var_90], eax
0x14013379a  mov     rax, 8765432100000003h
0x1401337a4  mov     [rbp+57h+var_CD], r13b
0x1401337a8  mov     rbx, [rdi+8]
0x1401337ac  mov     r8, [r11+88h]
0x1401337b3  mov     r12d, ebx
0x1401337b6  shr     r8, 20h
0x1401337ba  and     r8b, 1
0x1401337be  mov     [rbp+57h+ListEntry], r13
0x1401337c2  mov     [rbp+57h+var_CF], cl
0x1401337c5  mov     [rbp+57h+var_A0], r8
0x1401337c9  mov     [rbp+57h+var_D0], r9b
0x1401337cd  cmp     rbx, rax
0x1401337d0  jnz     short loc_1401337DC
0x1401337d2  mov     rdx, [rdi+18h]
0x1401337d6  mov     [rbp+57h+var_B0], rdx
0x1401337da  jmp     short loc_1401337F9
0x1401337dc  xor     edx, edx
0x1401337de  mov     rax, 0FEDCBA9000000000h
0x1401337e8  mov     [rbp+57h+var_B0], rdx
0x1401337ec  cmp     rbx, rax
0x1401337ef  jnz     short loc_1401337F9
0x1401337f1  mov     r13, [rdi+18h]
0x1401337f5  mov     [rbp+57h+ListEntry], r13
0x1401337f9  mov     eax, [r14+60h]
0x1401337fd  sub     eax, 5
0x140133800  cmp     eax, 1
0x140133803  jbe     loc_14013405F
0x140133809  movzx   ecx, byte ptr [rdi]
0x14013380c  cmp     cl, 3
0x14013380f  mov     [rbp+57h+var_CC], cl
0x140133812  setz    [rbp+57h+var_CE]
0x140133816  test    rdx, rdx
0x140133819  jz      loc_1401339BC
0x14013381f  xor     r15d, r15d
0x140133822  xor     cl, cl
0x140133824  xor     edi, edi
0x140133826  mov     [rbp+57h+var_CE], cl
0x140133829  mov     [rbp+57h+var_B8], r15d
0x14013382d  test    r8b, r8b
0x140133830  jnz     short loc_14013383B
0x140133832  lock inc word ptr [rdx+78h]
0x140133837  mov     [rbp+57h+var_D0], 1
0x14013383b  mov     r9d, 4
0x140133841  mov     rbx, rdx
0x140133844  nop     dword ptr [rax+00h]
0x140133848  nop     dword ptr [rax+rax+00000000h]
0x140133850  mov     r12, [rbx+60h]
0x140133854  mov     eax, 3
0x140133859  movzx   r13d, word ptr [rbx+22h]
0x14013385e  lock cmpxchg [rbx+68h], r9d
0x140133864  test    r8b, r8b
0x140133867  jnz     short loc_140133882
0x140133869  cmp     eax, 3
0x14013386c  jz      short loc_140133898
0x14013386e  mov     eax, [rbx+68h]
0x140133871  cmp     eax, 1
0x140133874  jnz     loc_140133931
0x14013387a  inc     di
0x14013387d  jmp     loc_140133931
0x140133882  cmp     eax, 3
0x140133885  jz      short loc_140133898
0x140133887  mov     eax, 1
0x14013388c  lock cmpxchg [rbx+68h], r9d
0x140133892  jnz     loc_140133931
0x140133898  mov     edx, [rbp+57h+var_C8]
0x14013389b  lea     rax, [rbp+57h+var_98]
0x14013389f  mov     byte ptr [rsp+130h+var_F0], cl
0x1401338a3  xor     r9d, r9d
0x1401338a6  mov     [rsp+130h+var_F8], rax
  ... truncated ...
```
