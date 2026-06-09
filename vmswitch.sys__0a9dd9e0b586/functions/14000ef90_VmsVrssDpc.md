# VmsVrssDpc

- ea: `0x14000ef90`
- end: `0x14001004e`
- name: `VmsVrssDpc`
- size: `4286`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000d5e4`
- `0x14000d828`
- `0x14000d990`
- `0x14000da60`
- `0x14000daf4`
- `0x14000dc3c`
- `0x14000dd84`
- `0x14000ddf0`
- `0x14000ef90`
- `0x140010054`
- `0x1400104d4`
- `0x140010840`
- `0x140010940`
- `0x140010aa8`
- `0x140010af0`
- `0x1400111f0`
- `0x14008e098`
- `0x1401bbcb0`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000f363`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000f363`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000f0bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000f425`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000f0bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000f425`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f103`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f4c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f103`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f4c3`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000f4f1`
- `ntoskrnl!KeInsertQueueDpc` at `0x14000f4f1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f156`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000f156`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f05c`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f07b`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f1f6`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f218`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f2e0`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f2fb`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f51a`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f539`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f05c`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f07b`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f1f6`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f218`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f2e0`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f2fb`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f51a`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x14000f539`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000ff0e`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14001003d`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000ff0e`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14001003d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f036`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f1c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f315`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f553`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f036`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f1c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f315`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000f553`
- `ntoskrnl!KeCancelTimer` at `0x14000fefb`
- `ntoskrnl!KeCancelTimer` at `0x14001002a`
- `ntoskrnl!KeCancelTimer` at `0x14000fefb`
- `ntoskrnl!KeCancelTimer` at `0x14001002a`
- `ntoskrnl!KeShouldYieldProcessor` at `0x14000f799`
- `ntoskrnl!KeShouldYieldProcessor` at `0x14000f799`
- `HAL!KeQueryPerformanceCounter` at `0x14000efdd`
- `HAL!KeQueryPerformanceCounter` at `0x14000f179`
- `HAL!KeQueryPerformanceCounter` at `0x14000efdd`
- `HAL!KeQueryPerformanceCounter` at `0x14000f179`

## pseudocode

```c
void __fastcall VmsVrssDpc(struct _KDPC *Dpc, _BYTE *DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)
{
  LARGE_INTEGER *v4; // rbx
  _BYTE *v5; // r14
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 QuadPart; // rcx
  LARGE_INTEGER v8; // rdx
  __int16 v9; // cx
  char v10; // r12
  PSLIST_ENTRY v11; // r15
  PSLIST_ENTRY v12; // rdi
  KSPIN_LOCK *v13; // r13
  __int64 *v14; // rbx
  __int64 *v15; // rdi
  __int64 *v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  unsigned __int64 v19; // rdx
  unsigned int v20; // r15d
  __int64 *v21; // rcx
  signed __int64 v22; // rdi
  LARGE_INTEGER v23; // rbx
  char v24; // dl
  signed __int64 v25; // rcx
  char *v26; // r15
  PSLIST_ENTRY v27; // r12
  union _SLIST_HEADER *v28; // rdi
  PSLIST_ENTRY v29; // rsi
  __int64 v30; // r8
  int v31; // eax
  PSLIST_ENTRY v32; // r12
  PSLIST_ENTRY v33; // rdi
  unsigned int Lock; // ecx
  __int64 **v35; // rax
  __int64 **v36; // rdx
  __int64 **v37; // rcx
  __int64 **v38; // rdx
  PSLIST_ENTRY v39; // r15
  PSLIST_ENTRY v40; // rdi
  PSLIST_ENTRY v41; // rsi
  __int64 v42; // rdx
  __int64 v43; // rcx
  unsigned int PlannedProcessorForEntry; // eax
  unsigned int v45; // ebx
  PSLIST_ENTRY v46; // rsi
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned int v49; // eax
  unsigned int v50; // ebx
  LARGE_INTEGER v51; // rdx
  LARGE_INTEGER v52; // rcx
  PSLIST_ENTRY v53; // rbx
  unsigned __int16 v54; // r13
  __int64 v55; // rsi
  __int64 v56; // rdx
  unsigned int v57; // r15d
  int v58; // r12d
  int v59; // edx
  int v60; // ecx
  int v61; // r8d
  int v62; // edx
  int v63; // ecx
  int v64; // r8d
  __int64 v65; // rdx
  LOGICAL ShouldYieldProcessor; // eax
  PSLIST_ENTRY v67; // rsi
  __int64 v68; // rdx
  __int64 v69; // rcx
  unsigned int v70; // eax
  unsigned int v71; // ebx
  PSLIST_ENTRY v72; // rbx
  __int64 v73; // r13
  __int64 v74; // rdx
  unsigned int v75; // esi
  int v76; // r12d
  int v77; // edx
  int v78; // r8d
  int v79; // edx
  int v80; // ecx
  int v81; // r8d
  __int64 v82; // rdx
  PSLIST_ENTRY v83; // r13
  __int64 v84; // rdx
  __int64 v85; // rcx
  unsigned int v86; // eax
  unsigned int v87; // edi
  PSLIST_ENTRY v88; // rdi
  _QWORD *p_Next; // rcx
  __int64 v90; // r9
  __int64 v91; // rdx
  __int64 v92; // r9
  unsigned int v93; // r12d
  int v94; // r13d
  int v95; // edx
  int v96; // r8d
  int v97; // edx
  int v98; // ecx
  int v99; // r8d
  __int64 v100; // rdx
  PSLIST_ENTRY v101; // rbx
  unsigned __int16 v102; // r13
  __int64 v103; // rsi
  __int64 v104; // rdx
  unsigned int v105; // r15d
  int v106; // r12d
  int v107; // edx
  int v108; // ecx
  int v109; // r8d
  int v110; // edx
  int v111; // ecx
  int v112; // r8d
  __int64 v113; // rdx
  __int64 *v114; // rdx
  struct _SLIST_ENTRY *Next; // rdi
  unsigned __int16 v116; // bx
  int v117; // ecx
  __int64 v118; // rtt
  struct _SLIST_ENTRY *v119; // rsi
  unsigned __int16 v120; // di
  __int64 v121; // r13
  struct _SLIST_ENTRY *v122; // rdi
  unsigned __int16 v123; // bx
  struct _SLIST_ENTRY *v124; // rdi
  unsigned __int16 v125; // bx
  char v126; // [rsp+40h] [rbp-79h]
  __int64 v127; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v128; // [rsp+68h] [rbp-51h] BYREF
  LARGE_INTEGER v129; // [rsp+70h] [rbp-49h] BYREF
  __int64 *v130; // [rsp+78h] [rbp-41h]
  __int64 v131; // [rsp+80h] [rbp-39h] BYREF
  _BYTE *v132; // [rsp+88h] [rbp-31h]
  char *v133; // [rsp+90h] [rbp-29h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+98h] [rbp-21h] BYREF
  struct _KLOCK_QUEUE_HANDLE WatchdogInformation; // [rsp+B0h] [rbp-9h] BYREF

  v4 = (LARGE_INTEGER *)(DeferredContext + 1152);
  v132 = DeferredContext;
  v133 = DeferredContext + 1152;
  v5 = DeferredContext;
  if ( *((_QWORD *)DeferredContext + 146) )
  {
    DeferredContext[1288] = 1;
  }
  else
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    QuadPart = v4->QuadPart;
    v4[2] = PerformanceCounter;
    v8 = *(LARGE_INTEGER *)(QuadPart + 13104);
    BYTE2(v4[6].u.LowPart) = 1;
    LOBYTE(v4[6].LowPart) = v8.QuadPart != 0;
    if ( v8.QuadPart && v4[1].QuadPart == v8.QuadPart )
    {
      BYTE1(v4[6].LowPart) = 1;
      v9 = 1;
      v4[1] = v8;
    }
    else
    {
      BYTE1(v4[6].LowPart) = 0;
      v9 = 0;
      v4[1] = v8;
      if ( v8.QuadPart )
      {
        v51.QuadPart = HIWORD(v4[6].QuadPart);
        v52 = v4[11];
        HIWORD(v4[6].QuadPart) = 1;
        v4[4] = PerformanceCounter;
        if ( v52.QuadPart <= (unsigned __int64)v51.QuadPart )
          v52 = v51;
        v4[3] = PerformanceCounter;
        ++v4[9].QuadPart;
        v4[11] = v52;
        v9 = 0;
        v4[5].QuadPart = 0;
        BYTE4(v4[6].QuadPart) = -1;
      }
    }
    HIWORD(v4[6].QuadPart) += v9;
  }
  KeGetCurrentProcessorNumberEx(0);
  v10 = 0;
  _mm_prefetch(v5 + 512, 1);
  _InterlockedIncrement((volatile signed __int32 *)v5 + 128);
  v11 = ExpInterlockedFlushSList((PSLIST_HEADER)v5 + 34);
  if ( v11 )
  {
    while ( 1 )
    {
      v41 = v11 - 1;
      v42 = *((unsigned __int16 *)&v11[1].Next + 4);
      v43 = (__int64)&v11[1].Next[40];
      v11 = v11->Next;
      PlannedProcessorForEntry = VmsPlanGetPlannedProcessorForEntry(v43, v42);
      v45 = PlannedProcessorForEntry;
      if ( PlannedProcessorForEntry == *(_DWORD *)v5 )
        goto LABEL_143;
      VmsQsMoveQueueToTargetProcessor(v5, v41, PlannedProcessorForEntry);
      if ( v45 == -1 )
        break;
LABEL_79:
      if ( !v11 )
        goto LABEL_8;
    }
    Next = v41[2].Next;
    v116 = *((_WORD *)&v41[2].Next + 4);
    v128 = -1;
    VmsPlanGetProcessorForEntryEx(&Next[40], v116, &v128);
    VmsPlanSetProcessorForEntry(&Next[40], v116, v128, 0xFFFFFFFFLL);
    if ( (*(_DWORD *)(&Next[160].Next + 1) & 0x10) == 0 )
      VmsQsMgmtRequestDeferredStateUpdate(v41[2].Next, 1);
LABEL_143:
    *((_DWORD *)&v41[2].Next + 3) = 0;
    VmsQsDropQueueMoveReference(v41);
    goto LABEL_79;
  }
LABEL_8:
  v12 = ExpInterlockedFlushSList((PSLIST_HEADER)v5 + 33);
  if ( !v12 )
    goto LABEL_9;
  do
  {
    v101 = v12;
    v12 = v12->Next;
    *((_QWORD *)&v101->Next + 1) = v101;
    v101->Next = v101;
    v102 = *((_WORD *)&v101[2].Next + 4);
    v103 = (__int64)&v101[2].Next[40];
    v105 = VmsPlanGetPlannedProcessorForEntry(v103, v102);
    if ( v105 == *(_DWORD *)v5 )
    {
      v106 = *((_DWORD *)&v101[2].Next + 3);
      if ( v106 == 259 )
        continue;
      *((_DWORD *)&v101[2].Next + 3) = v106;
      v129.LowPart = -1;
      VmsPlanGetProcessorForEntryEx(v103, v104, &v129);
      LOBYTE(v107) = 4;
      WPP_RECORDER_SF_dddddd(
        v108,
        v107,
        v109,
        42,
        (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
        *(_DWORD *)v5,
        *(_DWORD *)(v103 + 1932),
        v102,
        v129.QuadPart,
        v105,
        v106);
      if ( !v106 )
      {
        VmsPlanSetProcessorForEntry(v103, v102, v129.LowPart, v105);
        VmsQsInsertIntoLocalQueueList(v5, v101);
        VmsQsDropQueueMoveReference(v101);
        v113 = 1;
LABEL_130:
        VmsQsMgmtRequestDeferredStateUpdate(v101[2].Next, v113);
        continue;
      }
      if ( v129.LowPart == v105 )
      {
        VmsQsInsertIntoLocalQueueList(v5, v101);
        VmsQsDropQueueMoveReference(v101);
        v113 = 4;
        goto LABEL_130;
      }
      LOBYTE(v110) = 4;
      WPP_RECORDER_SF_dddddd(
        v111,
        v110,
        v112,
        43,
        (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
        *(_DWORD *)v5,
        *(_DWORD *)(v103 + 1932),
        v102,
        v106,
        v129.QuadPart,
        v105);
      VmsPlanSetPlannedProcessorForEntry(v103, v102, v129.LowPart);
      VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v5 + 7), v101);
    }
    else
    {
      VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v5 + 7), v101);
    }
  }
  while ( v12 );
  v10 = 0;
LABEL_9:
  v13 = (KSPIN_LOCK *)(v5 + 912);
  v14 = (__int64 *)(v5 + 896);
  while ( 2 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    v15 = 0;
    KeAcquireInStackQueuedSpinLockAtDpcLevel(v13, &LockHandle);
    v16 = (__int64 *)*v14;
    if ( (__int64 *)*v14 != v14 )
    {
      v17 = v5 + 896;
      if ( (_BYTE *)v16[1] == v5 + 896 )
      {
        v18 = (_QWORD *)*((_QWORD *)v5 + 113);
        if ( (_QWORD *)*v18 == v17 )
        {
          *v18 = v16;
          v15 = v16;
          v16[1] = (__int64)v18;
          *((_QWORD *)v5 + 113) = v5 + 896;
          *v17 = v17;
          goto LABEL_14;
        }
      }
LABEL_52:
      __fastfail(3u);
    }
LABEL_14:
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    if ( !v15 )
      break;
    v20 = 0;
    while ( 2 )
    {
      while ( 2 )
      {
        if ( !v15 )
          goto LABEL_54;
        v21 = (__int64 *)*v15;
        if ( (__int64 *)*v15 == v15 )
        {
          v130 = 0;
        }
        else
        {
          if ( (__int64 *)v21[1] != v15 )
            goto LABEL_52;
          v19 = v15[1];
          if ( *(__int64 **)v19 != v15 )
            goto LABEL_52;
          *(_QWORD *)v19 = v21;
          v21[1] = v19;
          v15[1] = (__int64)v15;
          *v15 = (__int64)v15;
          v130 = v21;
        }
        LOBYTE(v19) = 1;
        ((void (__fastcall *)(__int64 *, unsigned __int64))v15[8])(v15, v19);
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v15[2] + 352), (PSLIST_ENTRY)v15);
        v128 = ++v20;
        do
        {
          v22 = *((_QWORD *)v5 + 48);
          v23 = KeQueryPerformanceCounter(0);
          if ( v23.QuadPart - v22 < qword_140223F58 )
            goto LABEL_42;
          if ( !qword_140223F78 )
            goto LABEL_22;
          v117 = qword_1401FA000 - v23.LowPart;
          if ( (signed int)(qword_1401FA000 - v23.LowPart) < 0 )
            v117 = v23.LowPart - qword_1401FA000;
          if ( v117 >= qword_140223F78
            && (v118 = qword_1401FA000,
                v118 == _InterlockedCompareExchange64(&qword_1401FA000, v23.QuadPart, qword_1401FA000)) )
          {
LABEL_22:
            v24 = 1;
            v25 = v23.QuadPart;
          }
          else
          {
            v25 = v22 + qword_140223F78 * (unsigned int)(*(_DWORD *)v5 + 1);
            v24 = 0;
          }
        }
        while ( v22 != _InterlockedCompareExchange64((volatile signed __int64 *)v5 + 48, v25, v22) );
        if ( !v24 )
          goto LABEL_42;
        v26 = (char *)VmsPlanCpuTable + 5440 * KeGetCurrentProcessorNumberEx(0);
        _mm_prefetch(v26 + 512, 1);
        _InterlockedIncrement((volatile signed __int32 *)v26 + 128);
        v27 = ExpInterlockedFlushSList((PSLIST_HEADER)v26 + 34);
        if ( v27 )
        {
          while ( 1 )
          {
            v83 = v27 - 1;
            v84 = *((unsigned __int16 *)&v27[1].Next + 4);
            v85 = (__int64)&v27[1].Next[40];
            v27 = v27->Next;
            v86 = VmsPlanGetPlannedProcessorForEntry(v85, v84);
            v87 = v86;
            if ( v86 == *(_DWORD *)v26 )
              goto LABEL_154;
            VmsQsMoveQueueToTargetProcessor(v26, v83, v86);
            if ( v87 == -1 )
              break;
LABEL_116:
            if ( !v27 )
              goto LABEL_26;
          }
          v119 = v83[2].Next;
          v120 = *((_WORD *)&v83[2].Next + 4);
          LODWORD(v127) = -1;
          VmsPlanGetProcessorForEntryEx(&v119[40], v120, &v127);
          VmsPlanSetProcessorForEntry(&v119[40], v120, (unsigned int)v127, 0xFFFFFFFFLL);
          if ( (*(_DWORD *)(&v119[160].Next + 1) & 0x10) == 0 )
            VmsQsMgmtRequestDeferredStateUpdate(v83[2].Next, 1);
LABEL_154:
          *((_DWORD *)&v83[2].Next + 3) = 0;
          VmsQsDropQueueMoveReference(v83);
          goto LABEL_116;
        }
LABEL_26:
        v28 = (union _SLIST_HEADER *)(v26 + 528);
        v29 = ExpInterlockedFlushSList((PSLIST_HEADER)v26 + 33);
        if ( !v29 )
          goto LABEL_27;
        while ( 2 )
        {
          v88 = v29;
          p_Next = &v29->Next;
          v29 = v29->Next;
          *p_Next = v88;
          *((_QWORD *)&v88->Next + 1) = v88;
          v90 = (__int64)&v88[2].Next[40];
          LOWORD(v129.LowPart) = *((_WORD *)&v88[2].Next + 4);
          v131 = v90;
          v93 = VmsPlanGetPlannedProcessorForEntry(v90, LOWORD(v129.LowPart));
          if ( v93 == *(_DWORD *)v26 )
          {
            v94 = *((_DWORD *)&v88[2].Next + 3);
            if ( v94 != 259 )
            {
              *((_DWORD *)&v88[2].Next + 3) = v94;
              LODWORD(v127) = -1;
              VmsPlanGetProcessorForEntryEx(v92, v91, &v127);
              LOBYTE(v95) = 4;
              WPP_RECORDER_SF_dddddd(
                SLOWORD(v129.QuadPart),
                v95,
                v96,
                42,
                (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
                *(_DWORD *)v26,
                *(_DWORD *)(v131 + 1932),
                v129.QuadPart,
                v127,
                v93,
                v94);
              if ( !v94 )
              {
                VmsPlanSetProcessorForEntry(v131, LOWORD(v129.LowPart), (unsigned int)v127, v93);
                VmsQsInsertIntoLocalQueueList(v26, v88);
                VmsQsDropQueueMoveReference(v88);
                v100 = 1;
                goto LABEL_122;
              }
              if ( (_DWORD)v127 == v93 )
              {
                VmsQsInsertIntoLocalQueueList(v26, v88);
                VmsQsDropQueueMoveReference(v88);
                v100 = 4;
LABEL_122:
                VmsQsMgmtRequestDeferredStateUpdate(v88[2].Next, v100);
              }
              else
              {
                LOBYTE(v97) = 4;
                v126 = v94;
                v121 = v131;
                WPP_RECORDER_SF_dddddd(
                  v98,
                  v97,
                  v99,
                  43,
                  (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
                  *(_DWORD *)v26,
                  *(_DWORD *)(v131 + 1932),
                  v129.QuadPart,
                  v126,
                  v127,
                  v93);
                VmsPlanSetPlannedProcessorForEntry(v121, LOWORD(v129.LowPart), (unsigned int)v127);
                VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v26 + 7), v88);
              }
            }
          }
          else
          {
            VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v26 + 7), v88);
          }
          if ( v29 )
            continue;
          break;
        }
        v5 = v132;
        v28 = (union _SLIST_HEADER *)(v26 + 528);
LABEL_27:
        v129 = v23;
        if ( byte_140223F45 )
        {
          v127 = 0;
          v131 = 0;
          VmsQsUpdatePerProcessorRuntimeStats(v26, &v127, &v131);
        }
        VmsQsUpdatePerProcessorPacketStats(v26);
        if ( HIBYTE(word_140223F42) )
        {
          if ( v23.QuadPart - *((_QWORD *)v26 + 49) < qword_140223F70 )
          {
            LOBYTE(v30) = 0;
          }
          else
          {
            LOBYTE(v30) = 1;
            *((LARGE_INTEGER *)v26 + 49) = v23;
          }
          if ( *((_DWORD *)v26 + 3) )
          {
            VmsQsProcessQueues(v26, 3, v30, &v129);
            v31 = *((_DWORD *)v26 + 129);
            if ( (v31 & 1) != 0 )
              *((_DWORD *)v26 + 129) = v31 | 4;
          }
        }
        _mm_prefetch(v26 + 512, 1);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 128, 0xFFFFFFFF) == 1 )
        {
          v32 = ExpInterlockedFlushSList((PSLIST_HEADER)v26 + 34);
          if ( !v32 )
            goto LABEL_37;
          while ( 1 )
          {
            v67 = v32 - 1;
            v68 = *((unsigned __int16 *)&v32[1].Next + 4);
            v69 = (__int64)&v32[1].Next[40];
            v32 = v32->Next;
            v70 = VmsPlanGetPlannedProcessorForEntry(v69, v68);
            v71 = v70;
            if ( v70 == *(_DWORD *)v26 )
              goto LABEL_161;
            VmsQsMoveQueueToTargetProcessor(v26, v67, v70);
            if ( v71 == -1 )
              break;
LABEL_102:
            if ( !v32 )
            {
              v28 = (union _SLIST_HEADER *)(v26 + 528);
LABEL_37:
              v33 = ExpInterlockedFlushSList(v28);
              if ( !v33 )
              {
LABEL_38:
                KeGetCurrentProcessorNumberEx(0);
                VmsQsFlushRssV2Context(*((_QWORD *)v26 + 7));
                if ( *((_DWORD *)v26 + 5) )
                {
                  VmsQsCpuStartTimer(v26);
                }
                else if ( _interlockedbittestandreset((volatile signed __int32 *)v26 + 129, 0) == 1 )
                {
                  KeCancelTimer((PKTIMER)v26 + 5);
                  KeRemoveQueueDpc((PRKDPC)v26 + 4);
                }
                goto LABEL_41;
              }
              while ( 2 )
              {
                v72 = v33;
                v33 = v33->Next;
                *((_QWORD *)&v72->Next + 1) = v72;
                v72->Next = v72;
                v73 = (__int64)&v72[2].Next[40];
                LOWORD(v129.LowPart) = *((_WORD *)&v72[2].Next + 4);
                v75 = VmsPlanGetPlannedProcessorForEntry(v73, LOWORD(v129.LowPart));
                if ( v75 == *(_DWORD *)v26 )
                {
                  v76 = *((_DWORD *)&v72[2].Next + 3);
                  if ( v76 != 259 )
                  {
                    *((_DWORD *)&v72[2].Next + 3) = v76;
                    LODWORD(v127) = -1;
                    VmsPlanGetProcessorForEntryEx(v73, v74, &v127);
                    LOBYTE(v77) = 4;
                    WPP_RECORDER_SF_dddddd(
                      SLOWORD(v129.QuadPart),
                      v77,
                      v78,
                      42,
                      (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
                      *(_DWORD *)v26,
                      *(_DWORD *)(v73 + 1932),
                      v129.QuadPart,
                      v127,
                      v75,
                      v76);
                    if ( !v76 )
                    {
                      VmsPlanSetProcessorForEntry(v73, LOWORD(v129.LowPart), (unsigned int)v127, v75);
                      VmsQsInsertIntoLocalQueueList(v26, v72);
                      VmsQsDropQueueMoveReference(v72);
                      v82 = 1;
                      goto LABEL_109;
                    }
                    if ( (_DWORD)v127 == v75 )
                    {
                      VmsQsInsertIntoLocalQueueList(v26, v72);
                      VmsQsDropQueueMoveReference(v72);
                      v82 = 4;
LABEL_109:
                      VmsQsMgmtRequestDeferredStateUpdate(v72[2].Next, v82);
                    }
                    else
                    {
                      LOBYTE(v79) = 4;
                      WPP_RECORDER_SF_dddddd(
                        v80,
                        v79,
                        v81,
                        43,
                        (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
                        *(_DWORD *)v26,
                        *(_DWORD *)(v73 + 1932),
                        v129.QuadPart,
                        v76,
                        v127,
                        v75);
                      VmsPlanSetPlannedProcessorForEntry(v73, LOWORD(v129.LowPart), (unsigned int)v127);
                      VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v26 + 7), v72);
                    }
                  }
                }
                else
                {
                  VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v26 + 7), v72);
                }
                if ( !v33 )
                {
                  v5 = v132;
                  goto LABEL_38;
                }
                continue;
              }
            }
          }
          v122 = v67[2].Next;
          v123 = *((_WORD *)&v67[2].Next + 4);
          LODWORD(v127) = -1;
          VmsPlanGetProcessorForEntryEx(&v122[40], v123, &v127);
          VmsPlanSetProcessorForEntry(&v122[40], v123, (unsigned int)v127, 0xFFFFFFFFLL);
          if ( (*(_DWORD *)(&v122[160].Next + 1) & 0x10) == 0 )
            VmsQsMgmtRequestDeferredStateUpdate(v67[2].Next, 1);
LABEL_161:
          *((_DWORD *)&v67[2].Next + 3) = 0;
          VmsQsDropQueueMoveReference(v67);
          goto LABEL_102;
        }
LABEL_41:
        v20 = v128;
LABEL_42:
        memset(&WatchdogInformation, 0, 20);
        if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)&WatchdogInformation) < 0 )
          goto LABEL_48;
        if ( LODWORD(WatchdogInformation.LockQueue.Next) )
        {
          v19 = (unsigned int)(100 * HIDWORD(WatchdogInformation.LockQueue.Next))
              % LODWORD(WatchdogInformation.LockQueue.Next);
          if ( (unsigned int)(100 * HIDWORD(WatchdogInformation.LockQueue.Next))
             / LODWORD(WatchdogInformation.LockQueue.Next) >= VmsSingleInstanceDpcLowThreshold )
          {
            Lock = (unsigned int)WatchdogInformation.LockQueue.Lock;
            if ( LODWORD(WatchdogInformation.LockQueue.Lock) )
              goto LABEL_46;
LABEL_47:
            if ( Lock - HIDWORD(WatchdogInformation.LockQueue.Lock) < LODWORD(WatchdogInformation.LockQueue.Next) )
            {
LABEL_48:
              v15 = v130;
              v10 = 0;
              continue;
            }
          }
        }
        else
        {
          Lock = (unsigned int)WatchdogInformation.LockQueue.Lock;
          if ( !LODWORD(WatchdogInformation.LockQueue.Lock) )
            goto LABEL_48;
LABEL_46:
          v19 = 100 * HIDWORD(WatchdogInformation.LockQueue.Lock) % Lock;
          if ( 100 * HIDWORD(WatchdogInformation.LockQueue.Lock) / Lock >= VmsCumulativeDpcLowThreshold )
            goto LABEL_47;
        }
        break;
      }
      ShouldYieldProcessor = KeShouldYieldProcessor();
      v15 = v130;
      if ( !ShouldYieldProcessor )
      {
        v10 = 0;
        continue;
      }
      break;
    }
    v10 = 1;
LABEL_54:
    memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
    if ( v15 || v20 )
    {
      v13 = (KSPIN_LOCK *)(v5 + 912);
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v5 + 114, &WatchdogInformation);
      v14 = (__int64 *)(v5 + 896);
      if ( v15 )
      {
        v35 = (__int64 **)*v14;
        if ( (__int64 *)*v14 == v14 )
        {
          v37 = 0;
        }
        else
        {
          if ( v35[1] != v14 )
            goto LABEL_52;
          v36 = (__int64 **)*((_QWORD *)v5 + 113);
          if ( *v36 != v14 )
            goto LABEL_52;
          *v36 = (__int64 *)v35;
          v37 = v35;
          v35[1] = (__int64 *)v36;
          v35 = (__int64 **)(v5 + 896);
          *((_QWORD *)v5 + 113) = v5 + 896;
          *v14 = (__int64)v14;
        }
        if ( v35[1] != v14 )
          goto LABEL_52;
        v38 = (__int64 **)*((_QWORD *)v5 + 113);
        if ( *v38 != v14 || *(__int64 **)(*v15 + 8) != v15 || *(__int64 **)v15[1] != v15 )
          goto LABEL_52;
        *v38 = v15;
        *((_QWORD *)v5 + 113) = v15[1];
        *(_QWORD *)v15[1] = v14;
        v15[1] = (__int64)v38;
        if ( v37 )
        {
          if ( *(__int64 **)(*v14 + 8) != v14 )
            goto LABEL_52;
          v114 = (_QWORD *)*((_QWORD *)v5 + 113);
          if ( (__int64 *)*v114 != v14 || (__int64 **)(*v37)[1] != v37 || (__int64 **)*v37[1] != v37 )
            goto LABEL_52;
          *v114 = v37;
          *((_QWORD *)v5 + 113) = v37[1];
          *v37[1] = (__int64)v14;
          v37[1] = v114;
        }
      }
      *((_DWORD *)v5 + 230) -= v20;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&WatchdogInformation);
    }
    else
    {
      v14 = (__int64 *)(v5 + 896);
      v13 = (KSPIN_LOCK *)(v5 + 912);
    }
    if ( !v10 )
      continue;
    break;
  }
  if ( v10 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)v5 + 129);
    KeInsertQueueDpc((PRKDPC)v5 + 11, 0, 0);
  }
  _mm_prefetch(v5 + 512, 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 128, 0xFFFFFFFF) == 1 )
  {
    v39 = ExpInterlockedFlushSList((PSLIST_HEADER)v5 + 34);
    if ( !v39 )
    {
LABEL_72:
      v40 = ExpInterlockedFlushSList((PSLIST_HEADER)v5 + 33);
      if ( !v40 )
      {
LABEL_73:
        KeGetCurrentProcessorNumberEx(0);
        VmsQsFlushRssV2Context(*((_QWORD *)v5 + 7));
        if ( *((_DWORD *)v5 + 5) )
        {
          VmsQsCpuStartTimer(v5);
        }
        else if ( _interlockedbittestandreset((volatile signed __int32 *)v5 + 129, 0) == 1 )
        {
          KeCancelTimer((PKTIMER)v5 + 5);
          KeRemoveQueueDpc((PRKDPC)v5 + 4);
        }
        goto LABEL_76;
      }
      while ( 2 )
      {
        v53 = v40;
        v40 = v40->Next;
        *((_QWORD *)&v53->Next + 1) = v53;
        v53->Next = v53;
        v54 = *((_WORD *)&v53[2].Next + 4);
        v55 = (__int64)&v53[2].Next[40];
        v57 = VmsPlanGetPlannedProcessorForEntry(v55, v54);
        if ( v57 == *(_DWORD *)v5 )
        {
          v58 = *((_DWORD *)&v53[2].Next + 3);
          if ( v58 != 259 )
          {
            *((_DWORD *)&v53[2].Next + 3) = v58;
            LODWORD(v127) = -1;
            VmsPlanGetProcessorForEntryEx(v55, v56, &v127);
            LOBYTE(v59) = 4;
            WPP_RECORDER_SF_dddddd(
              v60,
              v59,
              v61,
              42,
              (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
              *(_DWORD *)v5,
              *(_DWORD *)(v55 + 1932),
              v54,
              v127,
              v57,
              v58);
            if ( !v58 )
            {
              VmsPlanSetProcessorForEntry(v55, v54, (unsigned int)v127, v57);
              VmsQsInsertIntoLocalQueueList(v5, v53);
              VmsQsDropQueueMoveReference(v53);
              v65 = 1;
              goto LABEL_94;
            }
            if ( (_DWORD)v127 == v57 )
            {
              VmsQsInsertIntoLocalQueueList(v5, v53);
              VmsQsDropQueueMoveReference(v53);
              v65 = 4;
LABEL_94:
              VmsQsMgmtRequestDeferredStateUpdate(v53[2].Next, v65);
            }
            else
            {
              LOBYTE(v62) = 4;
              WPP_RECORDER_SF_dddddd(
                v63,
                v62,
                v64,
                43,
                (__int64)WPP_e2db972791d730153f73a3088ace90dc_Traceguids,
                *(_DWORD *)v5,
                *(_DWORD *)(v55 + 1932),
                v54,
                v58,
                v127,
                v57);
              VmsPlanSetPlannedProcessorForEntry(v55, v54, (unsigned int)v127);
              VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v5 + 7), v53);
            }
          }
        }
        else
        {
          VmsQsAppendAndFlushIfNeeded(*((_QWORD *)v5 + 7), v53);
        }
        if ( !v40 )
          goto LABEL_73;
        continue;
      }
    }
    while ( 2 )
    {
      v46 = v39 - 1;
      v47 = *((unsigned __int16 *)&v39[1].Next + 4);
      v48 = (__int64)&v39[1].Next[40];
      v39 = v39->Next;
      v49 = VmsPlanGetPlannedProcessorForEntry(v48, v47);
      v50 = v49;
      if ( v49 != *(_DWORD *)v5 )
      {
        VmsQsMoveQueueToTargetProcessor(v5, v46, v49);
        if ( v50 != -1 )
          goto LABEL_83;
        v124 = v46[2].Next;
        v125 = *((_WORD *)&v46[2].Next + 4);
        v128 = -1;
        VmsPlanGetProcessorForEntryEx(&v124[40], v125, &v128);
        VmsPlanSetProcessorForEntry(&v124[40], v125, v128, 0xFFFFFFFFLL);
        if ( (*(_DWORD *)(&v124[160].Next + 1) & 0x10) == 0 )
          VmsQsMgmtRequestDeferredStateUpdate(v46[2].Next, 1);
      }
      *((_DWORD *)&v46[2].Next + 3) = 0;
      VmsQsDropQueueMoveReference(v46);
LABEL_83:
      if ( !v39 )
        goto LABEL_72;
      continue;
    }
  }
LABEL_76:
  NetDispatchProfilerLeave(v133);
}

```

## disassembly

```asm
0x14000ef90  push    rbp
0x14000ef92  push    rbx
0x14000ef93  push    rsi
0x14000ef94  push    rdi
0x14000ef95  push    r12
0x14000ef97  push    r13
0x14000ef99  push    r14
0x14000ef9b  push    r15
0x14000ef9d  lea     rbp, [rsp-1Fh]
0x14000efa2  sub     rsp, 0D8h
0x14000efa9  mov     rax, cs:__security_cookie
0x14000efb0  xor     rax, rsp
0x14000efb3  mov     [rbp+57h+var_48], rax
0x14000efb7  lea     rbx, [rdx+480h]
0x14000efbe  mov     [rbp+57h+var_88], rdx
0x14000efc2  xor     r13d, r13d
0x14000efc5  mov     [rbp+57h+var_80], rbx
0x14000efc9  mov     r14, rdx
0x14000efcc  mov     edi, 1
0x14000efd1  cmp     [rbx+10h], r13
0x14000efd5  jnz     loc_14000F688
0x14000efdb  xor     ecx, ecx; PerformanceFrequency
0x14000efdd  call    cs:__imp_KeQueryPerformanceCounter
0x14000efe4  nop     dword ptr [rax+rax+00h]
0x14000efe9  mov     rcx, [rbx]
0x14000efec  mov     [rbx+10h], rax
0x14000eff0  mov     rdx, [rcx+3330h]
0x14000eff7  test    rdx, rdx
0x14000effa  mov     [rbx+32h], dil
0x14000effe  setnz   cl
0x14000f001  mov     [rbx+30h], cl
0x14000f004  test    rdx, rdx
0x14000f007  jz      short loc_14000F01C
0x14000f009  cmp     [rbx+8], rdx
0x14000f00d  jnz     short loc_14000F01C
0x14000f00f  mov     [rbx+31h], dil
0x14000f013  movzx   ecx, di
0x14000f016  mov     [rbx+8], rdx
0x14000f01a  jmp     short loc_14000F030
0x14000f01c  mov     [rbx+31h], r13b
0x14000f020  mov     ecx, r13d
0x14000f023  mov     [rbx+8], rdx
0x14000f027  test    rdx, rdx
0x14000f02a  jnz     loc_14000F648
0x14000f030  add     [rbx+36h], cx
0x14000f034  xor     ecx, ecx; ProcNumber
0x14000f036  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000f03d  nop     dword ptr [rax+rax+00h]
0x14000f042  xor     r12b, r12b
0x14000f045  prefetcht0 byte ptr [r14+200h]
0x14000f04d  lock inc dword ptr [r14+200h]
0x14000f055  lea     rcx, [r14+220h]; ListHead
0x14000f05c  call    cs:__imp_ExpInterlockedFlushSList
0x14000f063  nop     dword ptr [rax+rax+00h]
0x14000f068  mov     r15, rax
0x14000f06b  test    rax, rax
0x14000f06e  jnz     loc_14000F5B2
0x14000f074  lea     rcx, [r14+210h]; ListHead
0x14000f07b  call    cs:__imp_ExpInterlockedFlushSList
0x14000f082  nop     dword ptr [rax+rax+00h]
0x14000f087  mov     rdi, rax
0x14000f08a  test    rax, rax
0x14000f08d  jnz     loc_14000FA90
0x14000f093  lea     r13, [r14+390h]
0x14000f09a  mov     esi, 0FFFFFFFFh
0x14000f09f  lea     rbx, [r14+380h]
0x14000f0a6  xorps   xmm0, xmm0
0x14000f0a9  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f0ad  xor     eax, eax
0x14000f0af  mov     rcx, r13; SpinLock
0x14000f0b2  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f0b6  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f0ba  xor     edi, edi
0x14000f0bc  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000f0c3  nop     dword ptr [rax+rax+00h]
0x14000f0c8  mov     rcx, [rbx]
0x14000f0cb  cmp     rcx, rbx
0x14000f0ce  jz      short loc_14000F0FF
0x14000f0d0  lea     rax, [r14+380h]
0x14000f0d7  cmp     [rcx+8], rax
0x14000f0db  jnz     loc_14000F3F2
0x14000f0e1  mov     rdx, [rax+8]
0x14000f0e5  cmp     [rdx], rax
0x14000f0e8  jnz     loc_14000F3F2
0x14000f0ee  mov     [rdx], rcx
0x14000f0f1  mov     rdi, rcx
0x14000f0f4  mov     [rcx+8], rdx
0x14000f0f8  mov     [rax+8], rax
0x14000f0fc  mov     [rax], rax
0x14000f0ff  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f103  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000f10a  nop     dword ptr [rax+rax+00h]
0x14000f10f  test    rdi, rdi
0x14000f112  jz      loc_14000F4D8
0x14000f118  xor     r15d, r15d
0x14000f11b  test    rdi, rdi
0x14000f11e  jz      loc_14000F3FC
0x14000f124  mov     rcx, [rdi]
0x14000f127  mov     rbx, rdi
0x14000f12a  cmp     rcx, rdi
0x14000f12d  jnz     loc_14000F3CC
0x14000f133  xor     r9d, r9d
0x14000f136  mov     [rbp+57h+var_98], r9
0x14000f13a  mov     rax, [rdi+40h]
0x14000f13e  mov     dl, 1
0x14000f140  mov     rcx, rbx
0x14000f143  call    _guard_dispatch_icall
0x14000f148  mov     rcx, [rdi+10h]
0x14000f14c  mov     rdx, rbx; ListEntry
0x14000f14f  add     rcx, 160h; ListHead
0x14000f156  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000f15d  nop     dword ptr [rax+rax+00h]
0x14000f162  inc     r15d
0x14000f165  mov     [rbp+57h+var_A8], r15d
0x14000f169  nop     dword ptr [rax+00000000h]
0x14000f170  mov     rdi, [r14+180h]
0x14000f177  xor     ecx, ecx; PerformanceFrequency
0x14000f179  call    cs:__imp_KeQueryPerformanceCounter
0x14000f180  nop     dword ptr [rax+rax+00h]
0x14000f185  mov     rbx, rax
0x14000f188  sub     rax, rdi
0x14000f18b  cmp     rax, cs:qword_140223F58
0x14000f192  jl      loc_14000F353
0x14000f198  cmp     cs:qword_140223F78, 0
0x14000f1a0  jnz     loc_14000FCD2
0x14000f1a6  mov     dl, 1
0x14000f1a8  mov     rcx, rbx
0x14000f1ab  mov     rax, rdi
0x14000f1ae  lock cmpxchg [r14+180h], rcx
0x14000f1b7  jnz     short loc_14000F170
0x14000f1b9  test    dl, dl
0x14000f1bb  jz      loc_14000F353
0x14000f1c1  xor     ecx, ecx; ProcNumber
0x14000f1c3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000f1ca  nop     dword ptr [rax+rax+00h]
0x14000f1cf  mov     ecx, eax
0x14000f1d1  imul    r15, rcx, 1540h
0x14000f1d8  add     r15, cs:VmsPlanCpuTable
0x14000f1df  prefetcht0 byte ptr [r15+200h]
0x14000f1e7  lock inc dword ptr [r15+200h]
0x14000f1ef  lea     rcx, [r15+220h]; ListHead
0x14000f1f6  call    cs:__imp_ExpInterlockedFlushSList
0x14000f1fd  nop     dword ptr [rax+rax+00h]
0x14000f202  mov     r12, rax
0x14000f205  test    rax, rax
0x14000f208  jnz     loc_14000F930
0x14000f20e  lea     rdi, [r15+210h]
0x14000f215  mov     rcx, rdi; ListHead
0x14000f218  call    cs:__imp_ExpInterlockedFlushSList
0x14000f21f  nop     dword ptr [rax+rax+00h]
0x14000f224  mov     rsi, rax
0x14000f227  test    rax, rax
0x14000f22a  jnz     loc_14000FD7F
0x14000f230  cmp     cs:byte_140223F45, 0
0x14000f237  mov     [rbp+57h+var_A0], rbx
0x14000f23b  jz      short loc_14000F25D
0x14000f23d  lea     r8, [rbp+57h+var_90]
0x14000f241  mov     [rbp+57h+var_B0], 0
0x14000f249  lea     rdx, [rbp+57h+var_B0]
0x14000f24d  mov     [rbp+57h+var_90], 0
0x14000f255  mov     rcx, r15
0x14000f258  call    VmsQsUpdatePerProcessorRuntimeStats
0x14000f25d  mov     rcx, r15
0x14000f260  call    VmsQsUpdatePerProcessorPacketStats
0x14000f265  cmp     byte ptr cs:word_140223F42+1, 0
0x14000f26c  jz      short loc_14000F2BC
0x14000f26e  mov     rax, rbx
0x14000f271  sub     rax, [r15+188h]
0x14000f278  cmp     rax, cs:qword_140223F70
0x14000f27f  jl      loc_14000F91C
0x14000f285  mov     r8b, 1
0x14000f288  mov     [r15+188h], rbx
0x14000f28f  cmp     dword ptr [r15+0Ch], 0
0x14000f294  jz      short loc_14000F2BC
0x14000f296  lea     r9, [rbp+57h+var_A0]
0x14000f29a  mov     edx, 3
0x14000f29f  mov     rcx, r15
0x14000f2a2  call    VmsQsProcessQueues
0x14000f2a7  mov     eax, [r15+204h]
0x14000f2ae  test    al, 1
0x14000f2b0  jz      short loc_14000F2BC
0x14000f2b2  or      eax, 4
0x14000f2b5  mov     [r15+204h], eax
0x14000f2bc  prefetcht0 byte ptr [r15+200h]
0x14000f2c4  mov     esi, 0FFFFFFFFh
0x14000f2c9  mov     eax, esi
0x14000f2cb  lock xadd [r15+200h], eax
0x14000f2d4  cmp     eax, 1
0x14000f2d7  jnz     short loc_14000F34F
0x14000f2d9  lea     rcx, [r15+220h]; ListHead
0x14000f2e0  call    cs:__imp_ExpInterlockedFlushSList
0x14000f2e7  nop     dword ptr [rax+rax+00h]
0x14000f2ec  mov     r12, rax
0x14000f2ef  test    rax, rax
0x14000f2f2  jnz     loc_14000F7C0
0x14000f2f8  mov     rcx, rdi; ListHead
0x14000f2fb  call    cs:__imp_ExpInterlockedFlushSList
0x14000f302  nop     dword ptr [rax+rax+00h]
0x14000f307  mov     rdi, rax
0x14000f30a  test    rax, rax
0x14000f30d  jnz     loc_14000F81E
0x14000f313  xor     ecx, ecx; ProcNumber
0x14000f315  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000f31c  nop     dword ptr [rax+rax+00h]
0x14000f321  mov     rcx, [r15+38h]
0x14000f325  call    VmsQsFlushRssV2Context
0x14000f32a  cmp     dword ptr [r15+14h], 0
0x14000f32f  jnz     loc_14000F811
0x14000f335  lock btr dword ptr [r15+204h], 0
0x14000f33f  setb    al
0x14000f342  cmp     al, 1
0x14000f344  jz      loc_14000FEF4
0x14000f34a  mov     esi, 0FFFFFFFFh
0x14000f34f  mov     r15d, [rbp+57h+var_A8]
0x14000f353  xorps   xmm0, xmm0
0x14000f356  lea     rcx, [rbp+57h+WatchdogInformation]; WatchdogInformation
0x14000f35a  xor     eax, eax
0x14000f35c  movups  xmmword ptr [rbp+57h+WatchdogInformation], xmm0
0x14000f360  mov     dword ptr [rbp+57h+WatchdogInformation+10h], eax
0x14000f363  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14000f36a  nop     dword ptr [rax+rax+00h]
0x14000f36f  test    eax, eax
0x14000f371  js      short loc_14000F3C0
0x14000f373  mov     r8d, dword ptr [rbp+57h+WatchdogInformation]
0x14000f377  mov     r9d, dword ptr [rbp+57h+WatchdogInformation+0Ch]
0x14000f37b  test    r8d, r8d
0x14000f37e  jz      loc_14000FB8C
0x14000f384  imul    eax, dword ptr [rbp+57h+WatchdogInformation+4], 64h ; 'd'
0x14000f388  xor     edx, edx
0x14000f38a  div     r8d
0x14000f38d  cmp     eax, cs:VmsSingleInstanceDpcLowThreshold
0x14000f393  jb      loc_14000F799
0x14000f399  mov     ecx, dword ptr [rbp+57h+WatchdogInformation+8]
0x14000f39c  test    ecx, ecx
0x14000f39e  jz      short loc_14000F3B4
0x14000f3a0  imul    eax, r9d, 64h ; 'd'
0x14000f3a4  xor     edx, edx
0x14000f3a6  div     ecx
0x14000f3a8  cmp     eax, cs:VmsCumulativeDpcLowThreshold
0x14000f3ae  jb      loc_14000F799
0x14000f3b4  sub     ecx, r9d
0x14000f3b7  cmp     ecx, r8d
0x14000f3ba  jnb     loc_14000F799
0x14000f3c0  mov     rdi, [rbp+57h+var_98]
0x14000f3c4  xor     r12b, r12b
0x14000f3c7  jmp     loc_14000F11B
0x14000f3cc  cmp     [rcx+8], rdi
0x14000f3d0  jnz     short loc_14000F3F2
0x14000f3d2  mov     rdx, [rdi+8]
0x14000f3d6  cmp     [rdx], rdi
0x14000f3d9  jnz     short loc_14000F3F2
0x14000f3db  mov     [rdx], rcx
0x14000f3de  mov     [rcx+8], rdx
0x14000f3e2  mov     [rdi+8], rbx
0x14000f3e6  mov     [rdi], rbx
0x14000f3e9  mov     [rbp+57h+var_98], rcx
0x14000f3ed  jmp     loc_14000F13A
0x14000f3f2  mov     ecx, 3
0x14000f3f7  int     29h; Win8: RtlFailFast(ecx)
0x14000f3f9  mov     r12b, 1
0x14000f3fc  xor     eax, eax
0x14000f3fe  xorps   xmm0, xmm0
0x14000f401  mov     qword ptr [rbp+57h+WatchdogInformation+10h], rax
0x14000f405  movups  xmmword ptr [rbp+57h+WatchdogInformation], xmm0
0x14000f409  test    rdi, rdi
0x14000f40c  jnz     short loc_14000F417
0x14000f40e  test    r15d, r15d
0x14000f411  jz      loc_14000FF26
0x14000f417  lea     r13, [r14+390h]
0x14000f41e  mov     rcx, r13; SpinLock
0x14000f421  lea     rdx, [rbp+57h+WatchdogInformation]; LockHandle
0x14000f425  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000f42c  nop     dword ptr [rax+rax+00h]
0x14000f431  lea     rbx, [r14+380h]
0x14000f438  test    rdi, rdi
0x14000f43b  jz      short loc_14000F4B8
0x14000f43d  mov     rax, [rbx]
0x14000f440  cmp     rax, rbx
0x14000f443  jz      loc_14000FF1F
0x14000f449  cmp     [rax+8], rbx
0x14000f44d  jnz     short loc_14000F3F2
0x14000f44f  mov     rdx, [rbx+8]
0x14000f453  cmp     [rdx], rbx
0x14000f456  jnz     short loc_14000F3F2
0x14000f458  mov     [rdx], rax
0x14000f45b  mov     rcx, rax
0x14000f45e  mov     [rax+8], rdx
0x14000f462  mov     rax, rbx
0x14000f465  mov     [rbx+8], rbx
0x14000f469  mov     [rbx], rbx
0x14000f46c  cmp     [rax+8], rbx
0x14000f470  jnz     short loc_14000F3F2
0x14000f472  mov     rdx, [rbx+8]
0x14000f476  cmp     [rdx], rbx
0x14000f479  jnz     loc_14000F3F2
0x14000f47f  mov     rax, [rdi]
0x14000f482  cmp     [rax+8], rdi
0x14000f486  jnz     loc_14000F3F2
0x14000f48c  mov     rax, [rdi+8]
0x14000f490  cmp     [rax], rdi
  ... truncated ...
```
