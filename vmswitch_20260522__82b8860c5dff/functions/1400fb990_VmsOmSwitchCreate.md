# VmsOmSwitchCreate

- ea: `0x1400fb990`
- end: `0x1400fc71d`
- name: `VmsOmSwitchCreate`
- size: `3469`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, int, int, int, int, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b281c`
- `0x140108c38`

## callees

- `0x14001484c`
- `0x140014988`
- `0x140027a64`
- `0x14002e45c`
- `0x14003a450`
- `0x140046e5c`
- `0x140047204`
- `0x14004f5d8`
- `0x140066bec`
- `0x14006a330`
- `0x14006a4ac`
- `0x14006f2b8`
- `0x1400764b4`
- `0x140077bd0`
- `0x14008497c`
- `0x14009128c`
- `0x1400eb23c`
- `0x1400eb424`
- `0x1400fb810`
- `0x1400fb990`
- `0x1400fc724`
- `0x1400fc970`
- `0x1400fd61c`
- `0x1400fda70`
- `0x140105de8`
- `0x140106f38`
- `0x140106fe4`
- `0x140108afc`
- `0x140112d7c`
- `0x140151bc4`
- `0x140151ebc`
- `0x140159e04`
- `0x140176508`
- `0x140187c68`
- `0x14018d298`
- `0x1401b9240`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1400fc65e`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400fc65e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fc61a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fc61a`
- `ntoskrnl!RtlCreateHashTable` at `0x1400fc03e`
- `ntoskrnl!RtlCreateHashTable` at `0x1400fc03e`
- `ntoskrnl!KeInitializeEvent` at `0x1400fbfbd`
- `ntoskrnl!KeInitializeEvent` at `0x1400fbfbd`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400fbf06`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400fbf06`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400fc11b`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400fc11b`
- `ntoskrnl!KeInitializeDpc` at `0x1400fc106`
- `ntoskrnl!KeInitializeDpc` at `0x1400fc106`
- `ntoskrnl!RtlGUIDFromString` at `0x1400fbb68`
- `ntoskrnl!RtlGUIDFromString` at `0x1400fbb68`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fbff8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fbff8`
- `ntoskrnl!KeInitializeMutex` at `0x1400fbd2e`
- `ntoskrnl!KeInitializeMutex` at `0x1400fbd2e`
- `ntoskrnl!KeReleaseMutex` at `0x1400fc4ec`
- `ntoskrnl!KeReleaseMutex` at `0x1400fc4ec`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fc45c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fc45c`
- `NDIS!NdisPDStartup` at `0x1400fc499`
- `NDIS!NdisPDStartup` at `0x1400fc499`
- `NDIS!NdisReleaseRWLock` at `0x1400fc1a4`
- `NDIS!NdisReleaseRWLock` at `0x1400fc5b8`
- `NDIS!NdisReleaseRWLock` at `0x1400fc1a4`
- `NDIS!NdisReleaseRWLock` at `0x1400fc5b8`
- `NETIO!NmrRegisterClient` at `0x1400fc3d7`
- `NETIO!NmrRegisterClient` at `0x1400fc3d7`

## string_xrefs

- `0x1400fbc2e`: `((ULONG_PTR)objSwitch & (VmsCacheLineSizeInBytes-1)) == 0`
- `0x1400fbc7b`: `((ULONG_PTR)(&objSwitch->Stats) & (VmsCacheLineSizeInBytes-1)) == 0`

## pseudocode

```c
__int64 __fastcall VmsOmSwitchCreate(
        PCUNICODE_STRING SourceString,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int16 a9,
        int a10,
        __int64 a11,
        _QWORD *a12)
{
  const UNICODE_STRING *v13; // rbx
  _QWORD *v15; // rdi
  int v16; // edx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // esi
  NTSTATUS v21; // eax
  int v22; // edx
  int v23; // r9d
  int v24; // eax
  __int64 v25; // rcx
  int v26; // edx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rcx
  char v30; // al
  const UNICODE_STRING *v31; // rdx
  int v32; // edx
  __int64 v33; // rdx
  _QWORD *v34; // rax
  char v35; // al
  _QWORD *v36; // rbx
  __int64 v37; // rcx
  int WorkerQueue; // eax
  int v39; // edx
  int WorkItem; // eax
  int v41; // edx
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // edx
  int v46; // eax
  int v47; // edx
  NTSTATUS v48; // eax
  int v49; // edx
  int v50; // edx
  void *v51; // rcx
  int v52; // edx
  int v53; // r8d
  __int64 *Size; // [rsp+20h] [rbp-D1h]
  int Sizea; // [rsp+20h] [rbp-D1h]
  int EdgeCounters; // [rsp+80h] [rbp-71h]
  char v58; // [rsp+84h] [rbp-6Dh]
  char v59; // [rsp+85h] [rbp-6Ch]
  char v60; // [rsp+86h] [rbp-6Bh]
  char v61; // [rsp+87h] [rbp-6Ah]
  char v62; // [rsp+88h] [rbp-69h]
  char v63; // [rsp+89h] [rbp-68h]
  char v64; // [rsp+8Ah] [rbp-67h]
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp-59h] BYREF
  PVOID DeferredContext; // [rsp+A0h] [rbp-51h] BYREF
  int v68; // [rsp+A8h] [rbp-49h]
  __int64 v69; // [rsp+B0h] [rbp-41h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+B8h] [rbp-39h] BYREF
  PCUNICODE_STRING SourceStringa; // [rsp+C0h] [rbp-31h]
  PCUNICODE_STRING v72; // [rsp+C8h] [rbp-29h]
  _QWORD *v73; // [rsp+D0h] [rbp-21h]
  GUID Guid; // [rsp+D8h] [rbp-19h] BYREF

  v73 = a12;
  v13 = a3;
  SourceStringa = a4;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v15 = 0;
  v72 = a2;
  DeferredContext = 0;
  v61 = 0;
  v58 = 0;
  v69 = 0;
  v59 = 0;
  v60 = 0;
  v63 = 0;
  HashTable = 0;
  v62 = 0;
  Guid = 0;
  if ( !a5 )
  {
    WPP_RECORDER_SF_d(VmsIfrLog, 2, 20, 10, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, 0);
    EdgeCounters = -1073741811;
    v20 = 5;
    goto LABEL_95;
  }
  if ( !a6 )
  {
    WPP_RECORDER_SF_d(VmsIfrLog, 2, 20, 11, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, 0);
    EdgeCounters = -1073741811;
    v20 = 10;
    goto LABEL_95;
  }
  v68 = a9 & 8;
  if ( (a9 & 8) != 0 && (a9 & 0x10) != 0 )
  {
    WPP_RECORDER_SF_d(VmsIfrLog, 2, 20, 12, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, a9);
    EdgeCounters = -1073741811;
    v20 = 17;
    goto LABEL_95;
  }
  if ( (a9 & 1) != 0 )
  {
    if ( (a9 & 2) != 0 )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(VmsIfrLog, (_DWORD)a2, 20, 13, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids);
      EdgeCounters = -1073741811;
      v20 = 20;
      goto LABEL_95;
    }
    if ( a7 )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(VmsIfrLog, (_DWORD)a2, 20, 14, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids);
      EdgeCounters = -1073741811;
      v20 = 25;
      goto LABEL_95;
    }
  }
  v21 = RtlGUIDFromString(a4, &Guid);
  EdgeCounters = v21;
  if ( v21 )
  {
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_Zd(
      VmsIfrLog,
      v22,
      20,
      15,
      (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
      (__int64)a4,
      v21);
    v20 = 30;
    goto LABEL_94;
  }
  LOBYTE(v23) = 16;
  LOBYTE(v22) = 1;
  v24 = VmsOmpObjectAllocate(
          320 * VmsMaximumProcCount + 9664,
          v22,
          1,
          v23,
          SourceString,
          v72,
          v13,
          (__int64)VmsOmpSwitchDeleted,
          (__int64)&DeferredContext);
  v15 = DeferredContext;
  EdgeCounters = v24;
  if ( v24 < 0 )
  {
    v20 = 35;
    goto LABEL_94;
  }
  if ( ((VmsCacheLineSizeInBytes - 1) & (unsigned int)DeferredContext) != 0 )
  {
    WPP_RECORDER_SF_s(
      *((_QWORD *)DeferredContext + 1137),
      v16,
      19,
      16,
      (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
      (__int64)"((ULONG_PTR)objSwitch & (VmsCacheLineSizeInBytes-1)) == 0");
    if ( ((VmsCacheLineSizeInBytes - 1) & (unsigned int)v15) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( ((unsigned int)(VmsCacheLineSizeInBytes - 1) & (unsigned __int64)(v15 + 1208)) != 0 )
  {
    WPP_RECORDER_SF_s(
      v15[1137],
      v16,
      19,
      17,
      (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
      (__int64)"((ULONG_PTR)(&objSwitch->Stats) & (VmsCacheLineSizeInBytes-1)) == 0");
    if ( ((VmsCacheLineSizeInBytes - 1) & ((_DWORD)v15 + 9664)) != 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  memset(v15 + 812, 0, 0x808u);
  if ( (unsigned __int8)VmsOmIsObjectMarkedForDeletion(SourceString, 0, 0) )
  {
    VmsOmDeleteObjectRegistryKey(SourceString, 0, 0);
    EdgeCounters = -1073741738;
    v20 = 45;
    goto LABEL_95;
  }
  VmsUtilLockExclusive(v25, &LockState);
  v58 = 1;
  if ( !(unsigned int)VmsOmFindSwitchUnsafe(SourceString, &DeferredContext) )
  {
    EdgeCounters = -1073741771;
    v20 = 50;
    goto LABEL_95;
  }
  KeInitializeMutex((PRKMUTEX)(v15 + 143), 0xFFFFu);
  *((_DWORD *)v15 + 364) = a5;
  *((_DWORD *)v15 + 365) = a6;
  if ( a7 && a8 && a8 != 3 )
  {
    LOBYTE(v26) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v26, 20, 18, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, a8);
    EdgeCounters = -1073741637;
    v20 = 60;
    goto LABEL_95;
  }
  *((_DWORD *)v15 + 2142) = a7;
  *((_DWORD *)v15 + 2180) = a8;
  if ( (a9 & 1) != 0 )
    *((_BYTE *)v15 + 8904) = 1;
  if ( (a9 & 2) != 0 )
    *((_BYTE *)v15 + 8912) = 1;
  if ( (a9 & 0x20) != 0 )
    *((_BYTE *)v15 + 9176) = 1;
  if ( (a9 & 0x100) != 0 )
    *((_BYTE *)v15 + 8913) = 1;
  EdgeCounters = VmsOmpRscStructsAllocateAndInit(v15 + 1148);
  if ( EdgeCounters < 0 )
  {
    v20 = 61;
LABEL_41:
    v13 = a3;
    goto LABEL_94;
  }
  *((_DWORD *)v15 + 2286) = a10;
  if ( a11 )
  {
    *(_OWORD *)((char *)v15 + 9108) = *(_OWORD *)a11;
    *((_DWORD *)v15 + 2281) = *(_DWORD *)(a11 + 16);
  }
  else
  {
    v27 = VmsMinNumberOfQueuesPerVPort;
    *((_WORD *)v15 + 4554) = 257;
    *((_DWORD *)v15 + 2278) = 16;
    *((_DWORD *)v15 + 2279) = v27;
    *((_DWORD *)v15 + 2280) = 2;
    *((_WORD *)v15 + 4562) = 256;
    *((_BYTE *)v15 + 9127) = 0;
  }
  *((_DWORD *)v15 + 2229) = 0;
  v28 = *((_DWORD *)v15 + 2180);
  if ( v28 )
  {
    if ( v28 == 3 )
      goto LABEL_53;
  }
  else
  {
    if ( *((_DWORD *)v15 + 2142) )
    {
      *((_DWORD *)v15 + 2180) = 3;
      goto LABEL_53;
    }
    *((_DWORD *)v15 + 2180) = 2;
  }
  v15[1083] = 10000000000LL;
  v15[1082] = 10000000000LL;
  EdgeCounters = VmsScQosCreateLine(&v69, 0, v15[1083]);
  if ( EdgeCounters )
  {
    v20 = 65;
    goto LABEL_41;
  }
  v29 = v69;
  *(_QWORD *)(v69 + 240) = v15[1083];
  v15[1085] = v29;
LABEL_53:
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v15 + 10, 0, 0, 0x200u, 0xE0u, 0x43456E56u, 0);
  *((_BYTE *)v15 + 1408) = 1;
  *((_DWORD *)v15 + 353) = 0;
  *((_DWORD *)v15 + 358) = 0;
  v15[178] = v15 + 177;
  v15[177] = v15 + 177;
  v15[1070] = v15 + 1069;
  v15[1069] = v15 + 1069;
  v15[181] = v15 + 180;
  v15[180] = v15 + 180;
  v15[1119] = v15 + 1118;
  v15[1118] = v15 + 1118;
  v15[208] = v15 + 209;
  *((_DWORD *)v15 + 414) = 0x8000000;
  v15[466] = v15 + 467;
  *((_DWORD *)v15 + 930) = 0x1000000;
  v15[500] = v15 + 501;
  v30 = VmsDefaultPtNicDropLowResourcesPackets;
  *((_DWORD *)v15 + 998) = 0x1000000;
  *((_BYTE *)v15 + 9198) = v30;
  KeInitializeEvent((PRKEVENT)(v15 + 1144), NotificationEvent, 1u);
  v31 = SourceStringa;
  *(GUID *)(v15 + 539) = Guid;
  v15[542] = v15 + 543;
  *((_WORD *)v15 + 2164) = 0;
  *((_WORD *)v15 + 2165) = 256;
  RtlCopyUnicodeString((PUNICODE_STRING)(v15 + 541), v31);
  EdgeCounters = VmsExtIoAllocateEdgeCounters(v15);
  if ( EdgeCounters < 0 )
  {
    v20 = 66;
    goto LABEL_41;
  }
  *((_BYTE *)v15 + 1232) = 9;
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v15 + 1072);
  v63 = 1;
  v20 = 0;
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    EdgeCounters = -1073741823;
    LOBYTE(v32) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v32, 20, 19, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, 1);
    goto LABEL_41;
  }
  *((_DWORD *)v15 + 2243) = VmsDefaultTeamingAlgorithm;
  v62 = 1;
  if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(0, v15) )
  {
    *((_DWORD *)v15 + 2242) = 1;
    if ( v68 )
    {
      *((_DWORD *)v15 + 2243) = 4;
    }
    else if ( (a9 & 0x10) != 0 )
    {
      *((_DWORD *)v15 + 2243) = 5;
    }
  }
  else
  {
    *((_DWORD *)v15 + 2242) = 0;
  }
  EdgeCounters = VmsRouterSwitchAdded(v15);
  if ( EdgeCounters )
  {
    v20 = 70;
    goto LABEL_41;
  }
  v15[1096] = v15 + 1095;
  v15[1095] = v15 + 1095;
  KeInitializeDpc((PRKDPC)(v15 + 1097), VmsOmpSwitchUpdateStormPackets, v15);
  KeInitializeTimerEx((PKTIMER)(v15 + 1105), NotificationTimer);
  v34 = (_QWORD *)qword_140224D18;
  if ( *(__int64 **)qword_140224D18 != &VmsOmSwitchList )
    __fastfail(3u);
  v15[1] = qword_140224D18;
  *v15 = &VmsOmSwitchList;
  LOBYTE(v33) = 1;
  *v34 = v15;
  qword_140224D18 = (__int64)v15;
  ++VmsOmSwitchCount;
  *((_DWORD *)v15 + 17) = 1;
  v35 = VmsOmObjectPrepareForConfigStore(v15, v33, 1);
  v36 = v73;
  v64 = v35;
  if ( v73 )
  {
    VmsOmpObjectReference(v15, 0);
    *v36 = v15;
  }
  v61 = 1;
  NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
  v58 = 0;
  WorkerQueue = NvIoAllocateWorkerQueue(v37, v15 + 1156, v15 + 1169);
  EdgeCounters = WorkerQueue;
  if ( WorkerQueue < 0 )
  {
    LOBYTE(v39) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v39, 20, 20, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, WorkerQueue);
    goto LABEL_41;
  }
  WorkItem = NvIoAllocateWorkItem((PNPAGED_LOOKASIDE_LIST)v15[1169], 1, (__int64)(v15 + 1170));
  EdgeCounters = WorkItem;
  if ( WorkItem < 0 )
  {
    LOBYTE(v41) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v41, 20, 21, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, WorkItem);
    goto LABEL_41;
  }
  v15[1180] = v15 + 1179;
  v15[1179] = v15 + 1179;
  v42 = NvIoAllocateWorkItem((PNPAGED_LOOKASIDE_LIST)v15[1169], 6, (__int64)(v15 + 1181));
  EdgeCounters = v42;
  if ( v42 < 0 )
  {
    LOBYTE(v43) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v43, 20, 22, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, v42);
    goto LABEL_41;
  }
  v44 = NvIoAllocateWorkItem((PNPAGED_LOOKASIDE_LIST)v15[1169], 5, (__int64)(v15 + 1182));
  EdgeCounters = v44;
  if ( v44 < 0 )
  {
    LOBYTE(v45) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v45, 20, 23, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, v44);
    goto LABEL_41;
  }
  v15[1184] = v15 + 1183;
  v15[1183] = v15 + 1183;
  v46 = NvIoAllocateWorkItem((PNPAGED_LOOKASIDE_LIST)v15[1169], 15, (__int64)(v15 + 1185));
  EdgeCounters = v46;
  if ( v46 < 0 )
  {
    LOBYTE(v47) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v47, 20, 24, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, v46);
    goto LABEL_41;
  }
  *((_BYTE *)v15 + 9088) = 0;
  memset(v15 + 1126, 0, 0x50u);
  *((_DWORD *)v15 + 2257) = 2;
  v15[1130] = VmsTrcPktCapGetSourceInfo;
  *((_DWORD *)v15 + 2258) = 1;
  v15[1131] = VmsTrcPktCapSetEnabledLayers;
  v15[1133] = v15;
  v15[1132] = VmsTrcOnPktCapRundown;
  word_1401F716C = 2;
  v48 = NmrRegisterClient(&PktCapClientNotify, v15 + 1126, (PHANDLE)v15 + 1126);
  EdgeCounters = v48;
  if ( v48 )
  {
    LOBYTE(v49) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v49, 20, 25, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, v48);
    v20 = 75;
    goto LABEL_41;
  }
  v60 = 1;
  if ( v64 == 1 )
  {
    EdgeCounters = VmsOmSwitchStoreConfig(v15);
    if ( EdgeCounters )
    {
      v20 = 80;
      goto LABEL_41;
    }
  }
  if ( *((_BYTE *)v15 + 8904) )
  {
    KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
    if ( VmsProtocolHandle )
    {
      if ( !VmsPDClientHandle )
      {
        Size = &VmsPDPlatformDispatch;
        if ( (unsigned int)NdisPDStartup(VmsProtocolHandle, 0, VmsPDClientDispatch, &VmsPDClientHandle) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v50,
            19,
            26,
            (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
            (__int64)"funcStatus == NDIS_STATUS_SUCCESS");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
      }
    }
    ++VmsPDSwitchCount;
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
  }
  v13 = a3;
  EdgeCounters = VmsOmSwitchCreateDefaultObjects(v15);
  if ( EdgeCounters )
  {
    v20 = 85;
  }
  else
  {
    v59 = 1;
    EdgeCounters = VmsIfrLogCreate(a3);
    v17 = 95;
    if ( EdgeCounters )
      v20 = 95;
  }
LABEL_94:
  if ( !EdgeCounters )
  {
    VmsEtwTraceSwitchSuccess(
      (unsigned int)VM_SWITCH_SUCCESSFULLY_INITIALIZED,
      v16,
      v18,
      (_DWORD)SourceString,
      (__int64)v13,
      a9,
      a10);
    WPP_RECORDER_SF_ZZq(v15[1137], v52, v53, 28, Sizea, (__int64)SourceString, (__int64)v13, (char)v15);
    goto LABEL_117;
  }
LABEL_95:
  WPP_RECORDER_SF_ZZZZDDDLDDd(
    v17,
    v16,
    v18,
    v19,
    (__int64)Size,
    (__int64)SourceString,
    (__int64)v72,
    (__int64)a3,
    (__int64)SourceStringa,
    a5,
    a6,
    a7,
    a8,
    a9,
    a10,
    EdgeCounters);
  if ( v59 )
    VmsOmSwitchCleanupDefaultObjects(v15);
  if ( v58 )
    NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
  if ( v60 )
    PktCapClientUninitialize(v15 + 1126);
  if ( v61 )
  {
    if ( v73 )
    {
      *v73 = 0;
      VmsOmpObjectDereference(v15, 0);
    }
    VmsOmSwitchDelete(v15 + 9, 0, 0, 0);
  }
  else if ( v15 )
  {
    if ( *((_BYTE *)v15 + 1408) )
    {
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v15 + 10);
      *((_BYTE *)v15 + 1408) = 0;
    }
    v51 = (void *)v15[1085];
    if ( v51 )
    {
      VmsScQosDeleteLine(v51);
      v15[1085] = 0;
    }
    VmsPortMapDeInitialize(v15 + 812);
    if ( v62 )
      RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(v15 + 1072));
    if ( v63 )
      VmsExtIoDeleteEdgeCounters(v15);
    VmsOmpObjectCleanup(v15);
    v15 = 0;
  }
  VmsEtwTraceSwitchFailure(&VM_FAILED_TO_INITIALIZE_SWITCH, v20, (__int64)SourceString, (__int64)a3);
LABEL_117:
  VmsTraceLoggingSwitchCreate(v15, SourceString, v20, (unsigned int)EdgeCounters);
  return (unsigned int)EdgeCounters;
}

```

## disassembly

```asm
0x1400fb990  push    rbp
0x1400fb992  push    rbx
0x1400fb993  push    rsi
0x1400fb994  push    rdi
0x1400fb995  push    r12
0x1400fb997  push    r13
0x1400fb999  push    r14
0x1400fb99b  push    r15
0x1400fb99d  lea     rbp, [rsp-7]
0x1400fb9a2  sub     rsp, 0F8h
0x1400fb9a9  mov     rax, cs:__security_cookie
0x1400fb9b0  xor     rax, rsp
0x1400fb9b3  mov     [rbp+3Fh+var_48], rax
0x1400fb9b7  mov     rax, [rbp+3Fh+arg_58]
0x1400fb9be  mov     r13, rcx
0x1400fb9c1  mov     r12d, dword ptr [rbp+3Fh+arg_40]
0x1400fb9c8  xor     ecx, ecx
0x1400fb9ca  mov     [rbp+3Fh+var_60], rax
0x1400fb9ce  mov     rbx, r8
0x1400fb9d1  xor     eax, eax
0x1400fb9d3  mov     [rbp+3Fh+SourceString], r9
0x1400fb9d7  mov     word ptr [rbp+3Fh+LockState.OldIrql], ax
0x1400fb9db  xorps   xmm0, xmm0
0x1400fb9de  mov     [rbp+3Fh+LockState.Flags], al
0x1400fb9e1  mov     r15, r9
0x1400fb9e4  mov     eax, [rbp+3Fh+arg_20]
0x1400fb9e7  mov     edi, ecx
0x1400fb9e9  mov     [rbp+3Fh+var_A0], rbx
0x1400fb9ed  mov     [rbp+3Fh+var_68], rdx
0x1400fb9f1  mov     [rbp+3Fh+var_B0], 0C0000001h
0x1400fb9f8  mov     [rbp+3Fh+DeferredContext], rcx
0x1400fb9fc  mov     [rbp+3Fh+var_A9], cl
0x1400fb9ff  mov     [rbp+3Fh+var_AC], cl
0x1400fba02  mov     [rbp+3Fh+var_80], rcx
0x1400fba06  mov     [rbp+3Fh+var_AB], cl
0x1400fba09  mov     [rbp+3Fh+var_AA], cl
0x1400fba0c  mov     [rbp+3Fh+var_A7], cl
0x1400fba0f  mov     [rbp+3Fh+HashTable], rcx
0x1400fba13  mov     [rbp+3Fh+var_A8], cl
0x1400fba16  movups  xmmword ptr [rbp+3Fh+Guid.Data1], xmm0
0x1400fba1a  test    eax, eax
0x1400fba1c  jnz     short loc_1400FBA54
0x1400fba1e  lea     r9d, [rcx+0Ah]
0x1400fba22  mov     [rsp+130h+Tag], eax
0x1400fba26  lea     edx, [rcx+2]
0x1400fba29  lea     r8d, [rcx+14h]
0x1400fba2d  mov     rcx, cs:VmsIfrLog
0x1400fba34  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fba3b  mov     [rsp+130h+Size], r15
0x1400fba40  call    WPP_RECORDER_SF_d
0x1400fba45  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fba4c  lea     esi, [rdi+5]
0x1400fba4f  jmp     loc_1400FC53C
0x1400fba54  mov     eax, [rbp+3Fh+arg_28]
0x1400fba57  test    eax, eax
0x1400fba59  jnz     short loc_1400FBA93
0x1400fba5b  mov     rcx, cs:VmsIfrLog
0x1400fba62  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fba69  mov     [rsp+130h+Tag], eax
0x1400fba6d  lea     r9d, [rax+0Bh]
0x1400fba71  lea     edx, [rax+2]
0x1400fba74  mov     [rsp+130h+Size], r15
0x1400fba79  lea     r8d, [rax+14h]
0x1400fba7d  call    WPP_RECORDER_SF_d
0x1400fba82  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fba89  mov     esi, 0Ah
0x1400fba8e  jmp     loc_1400FC53C
0x1400fba93  mov     eax, r12d
0x1400fba96  and     eax, 8
0x1400fba99  mov     [rbp+3Fh+var_88], eax
0x1400fba9c  jz      short loc_1400FBAE0
0x1400fba9e  test    r12b, 10h
0x1400fbaa2  jz      short loc_1400FBAE0
0x1400fbaa4  mov     rcx, cs:VmsIfrLog
0x1400fbaab  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbab2  mov     r9d, 0Ch
0x1400fbab8  mov     [rsp+130h+Tag], r12d
0x1400fbabd  mov     [rsp+130h+Size], r15
0x1400fbac2  lea     edx, [r9-0Ah]
0x1400fbac6  lea     r8d, [r9+8]
0x1400fbaca  call    WPP_RECORDER_SF_d
0x1400fbacf  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbad6  mov     esi, 11h
0x1400fbadb  jmp     loc_1400FC53C
0x1400fbae0  mov     esi, r12d
0x1400fbae3  mov     r14d, 2
0x1400fbae9  and     esi, 1
0x1400fbaec  jz      short loc_1400FBB61
0x1400fbaee  test    r14b, r12b
0x1400fbaf1  jz      short loc_1400FBB26
0x1400fbaf3  mov     rcx, cs:VmsIfrLog
0x1400fbafa  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbb01  lea     r9d, [r14+0Bh]
0x1400fbb05  mov     [rsp+130h+Size], r15
0x1400fbb0a  lea     r8d, [r14+12h]
0x1400fbb0e  mov     dl, r14b
0x1400fbb11  call    WPP_RECORDER_SF_
0x1400fbb16  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbb1d  lea     esi, [r14+12h]
0x1400fbb21  jmp     loc_1400FC53C
0x1400fbb26  cmp     [rbp+3Fh+arg_30], ecx
0x1400fbb29  jz      short loc_1400FBB61
0x1400fbb2b  mov     rcx, cs:VmsIfrLog
0x1400fbb32  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbb39  mov     r9d, 0Eh
0x1400fbb3f  mov     [rsp+130h+Size], r15
0x1400fbb44  mov     dl, r14b
0x1400fbb47  lea     r8d, [r9+6]
0x1400fbb4b  call    WPP_RECORDER_SF_
0x1400fbb50  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbb57  mov     esi, 19h
0x1400fbb5c  jmp     loc_1400FC53C
0x1400fbb61  lea     rdx, [rbp+3Fh+Guid]; Guid
0x1400fbb65  mov     rcx, r15; GuidString
0x1400fbb68  call    cs:__imp_RtlGUIDFromString
0x1400fbb6f  nop     dword ptr [rax+rax+00h]
0x1400fbb74  mov     [rbp+3Fh+var_B0], eax
0x1400fbb77  test    eax, eax
0x1400fbb79  jz      short loc_1400FBBB3
0x1400fbb7b  mov     rcx, cs:VmsIfrLog
0x1400fbb82  mov     r9d, 0Fh
0x1400fbb88  mov     dword ptr [rsp+130h+Depth], eax
0x1400fbb8c  mov     dl, r14b
0x1400fbb8f  mov     qword ptr [rsp+130h+Tag], r15
0x1400fbb94  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbb9b  mov     [rsp+130h+Size], r15
0x1400fbba0  lea     r8d, [r9+5]
0x1400fbba4  call    WPP_RECORDER_SF_Zd
0x1400fbba9  mov     esi, 1Eh
0x1400fbbae  jmp     loc_1400FC532
0x1400fbbb3  mov     eax, cs:VmsMaximumProcCount
0x1400fbbb9  mov     r8d, 1; int
0x1400fbbbf  mov     r9b, 10h; int
0x1400fbbc2  mov     dl, r8b; int
0x1400fbbc5  lea     ecx, [rax+rax*4]
0x1400fbbc8  lea     rax, [rbp+3Fh+DeferredContext]
0x1400fbbcc  shl     ecx, 6
0x1400fbbcf  mov     [rsp+130h+var_F0], rax; __int64
0x1400fbbd4  add     ecx, 25C0h; int
0x1400fbbda  lea     rax, VmsOmpSwitchDeleted
0x1400fbbe1  mov     [rsp+130h+var_F8], rax; __int64
0x1400fbbe6  mov     rax, [rbp+3Fh+var_68]
0x1400fbbea  mov     qword ptr [rsp+130h+Depth], rbx; PCUNICODE_STRING
0x1400fbbef  mov     qword ptr [rsp+130h+Tag], rax; PCUNICODE_STRING
0x1400fbbf4  mov     [rsp+130h+Size], r13; SourceString
0x1400fbbf9  call    VmsOmpObjectAllocate
0x1400fbbfe  mov     rdi, [rbp+3Fh+DeferredContext]
0x1400fbc02  mov     [rbp+3Fh+var_B0], eax
0x1400fbc05  test    eax, eax
0x1400fbc07  jns     short loc_1400FBC13
0x1400fbc09  mov     esi, 23h ; '#'
0x1400fbc0e  jmp     loc_1400FC532
0x1400fbc13  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbc19  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbc20  dec     ecx
0x1400fbc22  test    rdi, rcx
0x1400fbc25  jz      short loc_1400FBC60
0x1400fbc27  mov     rcx, [rdi+2388h]
0x1400fbc2e  lea     rax, aUlongPtrObjswi; "((ULONG_PTR)objSwitch & (VmsCacheLineSi"...
0x1400fbc35  mov     r9d, 10h
0x1400fbc3b  mov     qword ptr [rsp+130h+Tag], rax
0x1400fbc40  mov     [rsp+130h+Size], r15
0x1400fbc45  lea     r8d, [r9+3]
0x1400fbc49  call    WPP_RECORDER_SF_s
0x1400fbc4e  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbc54  dec     ecx
0x1400fbc56  test    rdi, rcx
0x1400fbc59  jz      short loc_1400FBC60
0x1400fbc5b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)objSwitch & (VmsCacheLineSizeInBytes-1)) == 0")
0x1400fbc60  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbc66  lea     rbx, [rdi+25C0h]
0x1400fbc6d  dec     ecx
0x1400fbc6f  test    rbx, rcx
0x1400fbc72  jz      short loc_1400FBCAD
0x1400fbc74  mov     rcx, [rdi+2388h]
0x1400fbc7b  lea     rax, aUlongPtrObjswi_0; "((ULONG_PTR)(&objSwitch->Stats) & (VmsC"...
0x1400fbc82  mov     r9d, 11h
0x1400fbc88  mov     qword ptr [rsp+130h+Tag], rax
0x1400fbc8d  mov     [rsp+130h+Size], r15
0x1400fbc92  lea     r8d, [r9+2]
0x1400fbc96  call    WPP_RECORDER_SF_s
0x1400fbc9b  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbca1  dec     ecx
0x1400fbca3  test    rbx, rcx
0x1400fbca6  jz      short loc_1400FBCAD
0x1400fbca8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)(&objSwitch->Stats) & (VmsCacheLineSizeInBytes-1)) == 0")
0x1400fbcad  lea     rcx, [rdi+1960h]; void *
0x1400fbcb4  xor     edx, edx; Val
0x1400fbcb6  mov     r8d, 808h; Size
0x1400fbcbc  call    memset
0x1400fbcc1  xor     ebx, ebx
0x1400fbcc3  xor     r8d, r8d
0x1400fbcc6  xor     edx, edx
0x1400fbcc8  mov     [rbp+3Fh+var_B0], ebx
0x1400fbccb  mov     rcx, r13
0x1400fbcce  call    VmsOmIsObjectMarkedForDeletion
0x1400fbcd3  test    al, al
0x1400fbcd5  jz      short loc_1400FBCF3
0x1400fbcd7  xor     r8d, r8d
0x1400fbcda  xor     edx, edx
0x1400fbcdc  mov     rcx, r13
0x1400fbcdf  call    VmsOmDeleteObjectRegistryKey
0x1400fbce4  mov     [rbp+3Fh+var_B0], 0C0000056h
0x1400fbceb  lea     esi, [rbx+2Dh]
0x1400fbcee  jmp     loc_1400FC53C
0x1400fbcf3  lea     rdx, [rbp+3Fh+LockState]
0x1400fbcf7  call    VmsUtilLockExclusive
0x1400fbcfc  lea     rdx, [rbp+3Fh+DeferredContext]
0x1400fbd00  mov     [rbp+3Fh+var_AC], 1
0x1400fbd04  mov     rcx, r13
0x1400fbd07  call    VmsOmFindSwitchUnsafe
0x1400fbd0c  mov     [rbp+3Fh+var_B0], eax
0x1400fbd0f  test    eax, eax
0x1400fbd11  jnz     short loc_1400FBD22
0x1400fbd13  mov     [rbp+3Fh+var_B0], 0C0000035h
0x1400fbd1a  lea     esi, [rax+32h]
0x1400fbd1d  jmp     loc_1400FC53C
0x1400fbd22  lea     rcx, [rdi+478h]; Mutex
0x1400fbd29  mov     edx, 0FFFFh; Level
0x1400fbd2e  call    cs:__imp_KeInitializeMutex
0x1400fbd35  nop     dword ptr [rax+rax+00h]
0x1400fbd3a  mov     eax, [rbp+3Fh+arg_20]
0x1400fbd3d  mov     ecx, [rbp+3Fh+arg_30]
0x1400fbd40  mov     [rdi+5B0h], eax
0x1400fbd46  mov     eax, [rbp+3Fh+arg_28]
0x1400fbd49  mov     [rdi+5B4h], eax
0x1400fbd4f  mov     eax, [rbp+3Fh+arg_38]
0x1400fbd55  test    ecx, ecx
0x1400fbd57  jz      short loc_1400FBD95
0x1400fbd59  test    eax, eax
0x1400fbd5b  jz      short loc_1400FBD95
0x1400fbd5d  cmp     eax, 3
0x1400fbd60  jz      short loc_1400FBD95
0x1400fbd62  mov     rcx, cs:VmsIfrLog
0x1400fbd69  mov     r9d, 12h
0x1400fbd6f  mov     [rsp+130h+Tag], eax
0x1400fbd73  mov     dl, r14b
0x1400fbd76  mov     [rsp+130h+Size], r15
0x1400fbd7b  lea     r8d, [r9+2]
0x1400fbd7f  call    WPP_RECORDER_SF_d
0x1400fbd84  mov     [rbp+3Fh+var_B0], 0C00000BBh
0x1400fbd8b  mov     esi, 3Ch ; '<'
0x1400fbd90  jmp     loc_1400FC53C
0x1400fbd95  mov     [rdi+2178h], ecx
0x1400fbd9b  mov     [rdi+2210h], eax
0x1400fbda1  test    esi, esi
0x1400fbda3  jz      short loc_1400FBDAC
0x1400fbda5  mov     byte ptr [rdi+22C8h], 1
0x1400fbdac  test    r14b, r12b
0x1400fbdaf  jz      short loc_1400FBDB8
0x1400fbdb1  mov     byte ptr [rdi+22D0h], 1
0x1400fbdb8  test    r12b, 20h
0x1400fbdbc  jz      short loc_1400FBDC5
0x1400fbdbe  mov     byte ptr [rdi+23D8h], 1
0x1400fbdc5  mov     esi, 100h
0x1400fbdca  test    esi, r12d
0x1400fbdcd  jz      short loc_1400FBDD6
0x1400fbdcf  mov     byte ptr [rdi+22D1h], 1
0x1400fbdd6  lea     rcx, [rdi+23E0h]
0x1400fbddd  call    VmsOmpRscStructsAllocateAndInit
0x1400fbde2  mov     [rbp+3Fh+var_B0], eax
0x1400fbde5  test    eax, eax
0x1400fbde7  jns     short loc_1400FBDF7
0x1400fbde9  mov     esi, 3Dh ; '='
0x1400fbdee  mov     rbx, [rbp+3Fh+var_A0]
0x1400fbdf2  jmp     loc_1400FC532
0x1400fbdf7  mov     eax, [rbp+3Fh+arg_48]
0x1400fbdfd  mov     [rdi+23B8h], eax
0x1400fbe03  mov     rax, [rbp+3Fh+arg_50]
0x1400fbe0a  test    rax, rax
0x1400fbe0d  jz      short loc_1400FBE24
0x1400fbe0f  movups  xmm0, xmmword ptr [rax]
0x1400fbe12  movups  xmmword ptr [rdi+2394h], xmm0
0x1400fbe19  mov     eax, [rax+10h]
0x1400fbe1c  mov     [rdi+23A4h], eax
0x1400fbe22  jmp     short loc_1400FBE57
0x1400fbe24  mov     eax, cs:VmsMinNumberOfQueuesPerVPort
0x1400fbe2a  mov     word ptr [rdi+2394h], 101h
0x1400fbe33  mov     dword ptr [rdi+2398h], 10h
0x1400fbe3d  mov     [rdi+239Ch], eax
0x1400fbe43  mov     [rdi+23A0h], r14d
0x1400fbe4a  mov     [rdi+23A4h], si
0x1400fbe51  mov     [rdi+23A7h], bl
0x1400fbe57  mov     [rdi+22D4h], ebx
0x1400fbe5d  mov     eax, [rdi+2210h]
0x1400fbe63  test    eax, eax
0x1400fbe65  jnz     short loc_1400FBE84
0x1400fbe67  cmp     [rdi+2178h], ebx
0x1400fbe6d  jz      short loc_1400FBE7B
0x1400fbe6f  mov     dword ptr [rdi+2210h], 3
0x1400fbe79  jmp     short loc_1400FBEDE
0x1400fbe7b  mov     [rdi+2210h], r14d
0x1400fbe82  jmp     short loc_1400FBE89
0x1400fbe84  cmp     eax, 3
0x1400fbe87  jz      short loc_1400FBEDE
0x1400fbe89  mov     rax, 2540BE400h
0x1400fbe93  lea     rcx, [rbp+3Fh+var_80]
0x1400fbe97  mov     [rdi+21D8h], rax
0x1400fbe9e  mov     rdx, rbx
0x1400fbea1  mov     [rdi+21D0h], rax
  ... truncated ...
```
