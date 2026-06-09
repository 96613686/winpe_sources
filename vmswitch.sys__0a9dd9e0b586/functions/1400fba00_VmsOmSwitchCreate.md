# VmsOmSwitchCreate

- ea: `0x1400fba00`
- end: `0x1400fc78d`
- name: `VmsOmSwitchCreate`
- size: `3469`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, int, int, int, int, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b288c`
- `0x140108ca8`

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
- `0x1400eb2ac`
- `0x1400eb494`
- `0x1400fb880`
- `0x1400fba00`
- `0x1400fc794`
- `0x1400fc9e0`
- `0x1400fd68c`
- `0x1400fdae0`
- `0x140105e58`
- `0x140106fa8`
- `0x140107054`
- `0x140108b6c`
- `0x140112dec`
- `0x140151c34`
- `0x140151f2c`
- `0x140159e74`
- `0x140176578`
- `0x140187cd8`
- `0x14018d308`
- `0x1401b92b0`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1400fc6ce`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400fc6ce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fc68a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fc68a`
- `ntoskrnl!RtlCreateHashTable` at `0x1400fc0ae`
- `ntoskrnl!RtlCreateHashTable` at `0x1400fc0ae`
- `ntoskrnl!KeInitializeEvent` at `0x1400fc02d`
- `ntoskrnl!KeInitializeEvent` at `0x1400fc02d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400fbf76`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400fbf76`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400fc18b`
- `ntoskrnl!KeInitializeTimerEx` at `0x1400fc18b`
- `ntoskrnl!KeInitializeDpc` at `0x1400fc176`
- `ntoskrnl!KeInitializeDpc` at `0x1400fc176`
- `ntoskrnl!RtlGUIDFromString` at `0x1400fbbd8`
- `ntoskrnl!RtlGUIDFromString` at `0x1400fbbd8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fc068`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fc068`
- `ntoskrnl!KeInitializeMutex` at `0x1400fbd9e`
- `ntoskrnl!KeInitializeMutex` at `0x1400fbd9e`
- `ntoskrnl!KeReleaseMutex` at `0x1400fc55c`
- `ntoskrnl!KeReleaseMutex` at `0x1400fc55c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fc4cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fc4cc`
- `NDIS!NdisPDStartup` at `0x1400fc509`
- `NDIS!NdisPDStartup` at `0x1400fc509`
- `NDIS!NdisReleaseRWLock` at `0x1400fc214`
- `NDIS!NdisReleaseRWLock` at `0x1400fc628`
- `NDIS!NdisReleaseRWLock` at `0x1400fc214`
- `NDIS!NdisReleaseRWLock` at `0x1400fc628`
- `NETIO!NmrRegisterClient` at `0x1400fc447`
- `NETIO!NmrRegisterClient` at `0x1400fc447`

## string_xrefs

- `0x1400fbc9e`: `((ULONG_PTR)objSwitch & (VmsCacheLineSizeInBytes-1)) == 0`
- `0x1400fbceb`: `((ULONG_PTR)(&objSwitch->Stats) & (VmsCacheLineSizeInBytes-1)) == 0`

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
0x1400fba00  push    rbp
0x1400fba02  push    rbx
0x1400fba03  push    rsi
0x1400fba04  push    rdi
0x1400fba05  push    r12
0x1400fba07  push    r13
0x1400fba09  push    r14
0x1400fba0b  push    r15
0x1400fba0d  lea     rbp, [rsp-7]
0x1400fba12  sub     rsp, 0F8h
0x1400fba19  mov     rax, cs:__security_cookie
0x1400fba20  xor     rax, rsp
0x1400fba23  mov     [rbp+3Fh+var_48], rax
0x1400fba27  mov     rax, [rbp+3Fh+arg_58]
0x1400fba2e  mov     r13, rcx
0x1400fba31  mov     r12d, dword ptr [rbp+3Fh+arg_40]
0x1400fba38  xor     ecx, ecx
0x1400fba3a  mov     [rbp+3Fh+var_60], rax
0x1400fba3e  mov     rbx, r8
0x1400fba41  xor     eax, eax
0x1400fba43  mov     [rbp+3Fh+SourceString], r9
0x1400fba47  mov     word ptr [rbp+3Fh+LockState.OldIrql], ax
0x1400fba4b  xorps   xmm0, xmm0
0x1400fba4e  mov     [rbp+3Fh+LockState.Flags], al
0x1400fba51  mov     r15, r9
0x1400fba54  mov     eax, [rbp+3Fh+arg_20]
0x1400fba57  mov     edi, ecx
0x1400fba59  mov     [rbp+3Fh+var_A0], rbx
0x1400fba5d  mov     [rbp+3Fh+var_68], rdx
0x1400fba61  mov     [rbp+3Fh+var_B0], 0C0000001h
0x1400fba68  mov     [rbp+3Fh+DeferredContext], rcx
0x1400fba6c  mov     [rbp+3Fh+var_A9], cl
0x1400fba6f  mov     [rbp+3Fh+var_AC], cl
0x1400fba72  mov     [rbp+3Fh+var_80], rcx
0x1400fba76  mov     [rbp+3Fh+var_AB], cl
0x1400fba79  mov     [rbp+3Fh+var_AA], cl
0x1400fba7c  mov     [rbp+3Fh+var_A7], cl
0x1400fba7f  mov     [rbp+3Fh+HashTable], rcx
0x1400fba83  mov     [rbp+3Fh+var_A8], cl
0x1400fba86  movups  xmmword ptr [rbp+3Fh+Guid.Data1], xmm0
0x1400fba8a  test    eax, eax
0x1400fba8c  jnz     short loc_1400FBAC4
0x1400fba8e  lea     r9d, [rcx+0Ah]
0x1400fba92  mov     [rsp+130h+Tag], eax
0x1400fba96  lea     edx, [rcx+2]
0x1400fba99  lea     r8d, [rcx+14h]
0x1400fba9d  mov     rcx, cs:VmsIfrLog
0x1400fbaa4  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbaab  mov     [rsp+130h+Size], r15
0x1400fbab0  call    WPP_RECORDER_SF_d
0x1400fbab5  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbabc  lea     esi, [rdi+5]
0x1400fbabf  jmp     loc_1400FC5AC
0x1400fbac4  mov     eax, [rbp+3Fh+arg_28]
0x1400fbac7  test    eax, eax
0x1400fbac9  jnz     short loc_1400FBB03
0x1400fbacb  mov     rcx, cs:VmsIfrLog
0x1400fbad2  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbad9  mov     [rsp+130h+Tag], eax
0x1400fbadd  lea     r9d, [rax+0Bh]
0x1400fbae1  lea     edx, [rax+2]
0x1400fbae4  mov     [rsp+130h+Size], r15
0x1400fbae9  lea     r8d, [rax+14h]
0x1400fbaed  call    WPP_RECORDER_SF_d
0x1400fbaf2  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbaf9  mov     esi, 0Ah
0x1400fbafe  jmp     loc_1400FC5AC
0x1400fbb03  mov     eax, r12d
0x1400fbb06  and     eax, 8
0x1400fbb09  mov     [rbp+3Fh+var_88], eax
0x1400fbb0c  jz      short loc_1400FBB50
0x1400fbb0e  test    r12b, 10h
0x1400fbb12  jz      short loc_1400FBB50
0x1400fbb14  mov     rcx, cs:VmsIfrLog
0x1400fbb1b  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbb22  mov     r9d, 0Ch
0x1400fbb28  mov     [rsp+130h+Tag], r12d
0x1400fbb2d  mov     [rsp+130h+Size], r15
0x1400fbb32  lea     edx, [r9-0Ah]
0x1400fbb36  lea     r8d, [r9+8]
0x1400fbb3a  call    WPP_RECORDER_SF_d
0x1400fbb3f  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbb46  mov     esi, 11h
0x1400fbb4b  jmp     loc_1400FC5AC
0x1400fbb50  mov     esi, r12d
0x1400fbb53  mov     r14d, 2
0x1400fbb59  and     esi, 1
0x1400fbb5c  jz      short loc_1400FBBD1
0x1400fbb5e  test    r14b, r12b
0x1400fbb61  jz      short loc_1400FBB96
0x1400fbb63  mov     rcx, cs:VmsIfrLog
0x1400fbb6a  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbb71  lea     r9d, [r14+0Bh]
0x1400fbb75  mov     [rsp+130h+Size], r15
0x1400fbb7a  lea     r8d, [r14+12h]
0x1400fbb7e  mov     dl, r14b
0x1400fbb81  call    WPP_RECORDER_SF_
0x1400fbb86  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbb8d  lea     esi, [r14+12h]
0x1400fbb91  jmp     loc_1400FC5AC
0x1400fbb96  cmp     [rbp+3Fh+arg_30], ecx
0x1400fbb99  jz      short loc_1400FBBD1
0x1400fbb9b  mov     rcx, cs:VmsIfrLog
0x1400fbba2  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbba9  mov     r9d, 0Eh
0x1400fbbaf  mov     [rsp+130h+Size], r15
0x1400fbbb4  mov     dl, r14b
0x1400fbbb7  lea     r8d, [r9+6]
0x1400fbbbb  call    WPP_RECORDER_SF_
0x1400fbbc0  mov     [rbp+3Fh+var_B0], 0C000000Dh
0x1400fbbc7  mov     esi, 19h
0x1400fbbcc  jmp     loc_1400FC5AC
0x1400fbbd1  lea     rdx, [rbp+3Fh+Guid]; Guid
0x1400fbbd5  mov     rcx, r15; GuidString
0x1400fbbd8  call    cs:__imp_RtlGUIDFromString
0x1400fbbdf  nop     dword ptr [rax+rax+00h]
0x1400fbbe4  mov     [rbp+3Fh+var_B0], eax
0x1400fbbe7  test    eax, eax
0x1400fbbe9  jz      short loc_1400FBC23
0x1400fbbeb  mov     rcx, cs:VmsIfrLog
0x1400fbbf2  mov     r9d, 0Fh
0x1400fbbf8  mov     dword ptr [rsp+130h+Depth], eax
0x1400fbbfc  mov     dl, r14b
0x1400fbbff  mov     qword ptr [rsp+130h+Tag], r15
0x1400fbc04  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbc0b  mov     [rsp+130h+Size], r15
0x1400fbc10  lea     r8d, [r9+5]
0x1400fbc14  call    WPP_RECORDER_SF_Zd
0x1400fbc19  mov     esi, 1Eh
0x1400fbc1e  jmp     loc_1400FC5A2
0x1400fbc23  mov     eax, cs:VmsMaximumProcCount
0x1400fbc29  mov     r8d, 1; int
0x1400fbc2f  mov     r9b, 10h; int
0x1400fbc32  mov     dl, r8b; int
0x1400fbc35  lea     ecx, [rax+rax*4]
0x1400fbc38  lea     rax, [rbp+3Fh+DeferredContext]
0x1400fbc3c  shl     ecx, 6
0x1400fbc3f  mov     [rsp+130h+var_F0], rax; __int64
0x1400fbc44  add     ecx, 25C0h; int
0x1400fbc4a  lea     rax, VmsOmpSwitchDeleted
0x1400fbc51  mov     [rsp+130h+var_F8], rax; __int64
0x1400fbc56  mov     rax, [rbp+3Fh+var_68]
0x1400fbc5a  mov     qword ptr [rsp+130h+Depth], rbx; PCUNICODE_STRING
0x1400fbc5f  mov     qword ptr [rsp+130h+Tag], rax; PCUNICODE_STRING
0x1400fbc64  mov     [rsp+130h+Size], r13; SourceString
0x1400fbc69  call    VmsOmpObjectAllocate
0x1400fbc6e  mov     rdi, [rbp+3Fh+DeferredContext]
0x1400fbc72  mov     [rbp+3Fh+var_B0], eax
0x1400fbc75  test    eax, eax
0x1400fbc77  jns     short loc_1400FBC83
0x1400fbc79  mov     esi, 23h ; '#'
0x1400fbc7e  jmp     loc_1400FC5A2
0x1400fbc83  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbc89  lea     r15, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fbc90  dec     ecx
0x1400fbc92  test    rdi, rcx
0x1400fbc95  jz      short loc_1400FBCD0
0x1400fbc97  mov     rcx, [rdi+2388h]
0x1400fbc9e  lea     rax, aUlongPtrObjswi; "((ULONG_PTR)objSwitch & (VmsCacheLineSi"...
0x1400fbca5  mov     r9d, 10h
0x1400fbcab  mov     qword ptr [rsp+130h+Tag], rax
0x1400fbcb0  mov     [rsp+130h+Size], r15
0x1400fbcb5  lea     r8d, [r9+3]
0x1400fbcb9  call    WPP_RECORDER_SF_s
0x1400fbcbe  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbcc4  dec     ecx
0x1400fbcc6  test    rdi, rcx
0x1400fbcc9  jz      short loc_1400FBCD0
0x1400fbccb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)objSwitch & (VmsCacheLineSizeInBytes-1)) == 0")
0x1400fbcd0  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbcd6  lea     rbx, [rdi+25C0h]
0x1400fbcdd  dec     ecx
0x1400fbcdf  test    rbx, rcx
0x1400fbce2  jz      short loc_1400FBD1D
0x1400fbce4  mov     rcx, [rdi+2388h]
0x1400fbceb  lea     rax, aUlongPtrObjswi_0; "((ULONG_PTR)(&objSwitch->Stats) & (VmsC"...
0x1400fbcf2  mov     r9d, 11h
0x1400fbcf8  mov     qword ptr [rsp+130h+Tag], rax
0x1400fbcfd  mov     [rsp+130h+Size], r15
0x1400fbd02  lea     r8d, [r9+2]
0x1400fbd06  call    WPP_RECORDER_SF_s
0x1400fbd0b  mov     ecx, cs:VmsCacheLineSizeInBytes
0x1400fbd11  dec     ecx
0x1400fbd13  test    rbx, rcx
0x1400fbd16  jz      short loc_1400FBD1D
0x1400fbd18  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((ULONG_PTR)(&objSwitch->Stats) & (VmsCacheLineSizeInBytes-1)) == 0")
0x1400fbd1d  lea     rcx, [rdi+1960h]; void *
0x1400fbd24  xor     edx, edx; Val
0x1400fbd26  mov     r8d, 808h; Size
0x1400fbd2c  call    memset
0x1400fbd31  xor     ebx, ebx
0x1400fbd33  xor     r8d, r8d
0x1400fbd36  xor     edx, edx
0x1400fbd38  mov     [rbp+3Fh+var_B0], ebx
0x1400fbd3b  mov     rcx, r13
0x1400fbd3e  call    VmsOmIsObjectMarkedForDeletion
0x1400fbd43  test    al, al
0x1400fbd45  jz      short loc_1400FBD63
0x1400fbd47  xor     r8d, r8d
0x1400fbd4a  xor     edx, edx
0x1400fbd4c  mov     rcx, r13
0x1400fbd4f  call    VmsOmDeleteObjectRegistryKey
0x1400fbd54  mov     [rbp+3Fh+var_B0], 0C0000056h
0x1400fbd5b  lea     esi, [rbx+2Dh]
0x1400fbd5e  jmp     loc_1400FC5AC
0x1400fbd63  lea     rdx, [rbp+3Fh+LockState]
0x1400fbd67  call    VmsUtilLockExclusive
0x1400fbd6c  lea     rdx, [rbp+3Fh+DeferredContext]
0x1400fbd70  mov     [rbp+3Fh+var_AC], 1
0x1400fbd74  mov     rcx, r13
0x1400fbd77  call    VmsOmFindSwitchUnsafe
0x1400fbd7c  mov     [rbp+3Fh+var_B0], eax
0x1400fbd7f  test    eax, eax
0x1400fbd81  jnz     short loc_1400FBD92
0x1400fbd83  mov     [rbp+3Fh+var_B0], 0C0000035h
0x1400fbd8a  lea     esi, [rax+32h]
0x1400fbd8d  jmp     loc_1400FC5AC
0x1400fbd92  lea     rcx, [rdi+478h]; Mutex
0x1400fbd99  mov     edx, 0FFFFh; Level
0x1400fbd9e  call    cs:__imp_KeInitializeMutex
0x1400fbda5  nop     dword ptr [rax+rax+00h]
0x1400fbdaa  mov     eax, [rbp+3Fh+arg_20]
0x1400fbdad  mov     ecx, [rbp+3Fh+arg_30]
0x1400fbdb0  mov     [rdi+5B0h], eax
0x1400fbdb6  mov     eax, [rbp+3Fh+arg_28]
0x1400fbdb9  mov     [rdi+5B4h], eax
0x1400fbdbf  mov     eax, [rbp+3Fh+arg_38]
0x1400fbdc5  test    ecx, ecx
0x1400fbdc7  jz      short loc_1400FBE05
0x1400fbdc9  test    eax, eax
0x1400fbdcb  jz      short loc_1400FBE05
0x1400fbdcd  cmp     eax, 3
0x1400fbdd0  jz      short loc_1400FBE05
0x1400fbdd2  mov     rcx, cs:VmsIfrLog
0x1400fbdd9  mov     r9d, 12h
0x1400fbddf  mov     [rsp+130h+Tag], eax
0x1400fbde3  mov     dl, r14b
0x1400fbde6  mov     [rsp+130h+Size], r15
0x1400fbdeb  lea     r8d, [r9+2]
0x1400fbdef  call    WPP_RECORDER_SF_d
0x1400fbdf4  mov     [rbp+3Fh+var_B0], 0C00000BBh
0x1400fbdfb  mov     esi, 3Ch ; '<'
0x1400fbe00  jmp     loc_1400FC5AC
0x1400fbe05  mov     [rdi+2178h], ecx
0x1400fbe0b  mov     [rdi+2210h], eax
0x1400fbe11  test    esi, esi
0x1400fbe13  jz      short loc_1400FBE1C
0x1400fbe15  mov     byte ptr [rdi+22C8h], 1
0x1400fbe1c  test    r14b, r12b
0x1400fbe1f  jz      short loc_1400FBE28
0x1400fbe21  mov     byte ptr [rdi+22D0h], 1
0x1400fbe28  test    r12b, 20h
0x1400fbe2c  jz      short loc_1400FBE35
0x1400fbe2e  mov     byte ptr [rdi+23D8h], 1
0x1400fbe35  mov     esi, 100h
0x1400fbe3a  test    esi, r12d
0x1400fbe3d  jz      short loc_1400FBE46
0x1400fbe3f  mov     byte ptr [rdi+22D1h], 1
0x1400fbe46  lea     rcx, [rdi+23E0h]
0x1400fbe4d  call    VmsOmpRscStructsAllocateAndInit
0x1400fbe52  mov     [rbp+3Fh+var_B0], eax
0x1400fbe55  test    eax, eax
0x1400fbe57  jns     short loc_1400FBE67
0x1400fbe59  mov     esi, 3Dh ; '='
0x1400fbe5e  mov     rbx, [rbp+3Fh+var_A0]
0x1400fbe62  jmp     loc_1400FC5A2
0x1400fbe67  mov     eax, [rbp+3Fh+arg_48]
0x1400fbe6d  mov     [rdi+23B8h], eax
0x1400fbe73  mov     rax, [rbp+3Fh+arg_50]
0x1400fbe7a  test    rax, rax
0x1400fbe7d  jz      short loc_1400FBE94
0x1400fbe7f  movups  xmm0, xmmword ptr [rax]
0x1400fbe82  movups  xmmword ptr [rdi+2394h], xmm0
0x1400fbe89  mov     eax, [rax+10h]
0x1400fbe8c  mov     [rdi+23A4h], eax
0x1400fbe92  jmp     short loc_1400FBEC7
0x1400fbe94  mov     eax, cs:VmsMinNumberOfQueuesPerVPort
0x1400fbe9a  mov     word ptr [rdi+2394h], 101h
0x1400fbea3  mov     dword ptr [rdi+2398h], 10h
0x1400fbead  mov     [rdi+239Ch], eax
0x1400fbeb3  mov     [rdi+23A0h], r14d
0x1400fbeba  mov     [rdi+23A4h], si
0x1400fbec1  mov     [rdi+23A7h], bl
0x1400fbec7  mov     [rdi+22D4h], ebx
0x1400fbecd  mov     eax, [rdi+2210h]
0x1400fbed3  test    eax, eax
0x1400fbed5  jnz     short loc_1400FBEF4
0x1400fbed7  cmp     [rdi+2178h], ebx
0x1400fbedd  jz      short loc_1400FBEEB
0x1400fbedf  mov     dword ptr [rdi+2210h], 3
0x1400fbee9  jmp     short loc_1400FBF4E
0x1400fbeeb  mov     [rdi+2210h], r14d
0x1400fbef2  jmp     short loc_1400FBEF9
0x1400fbef4  cmp     eax, 3
0x1400fbef7  jz      short loc_1400FBF4E
0x1400fbef9  mov     rax, 2540BE400h
0x1400fbf03  lea     rcx, [rbp+3Fh+var_80]
0x1400fbf07  mov     [rdi+21D8h], rax
0x1400fbf0e  mov     rdx, rbx
0x1400fbf11  mov     [rdi+21D0h], rax
  ... truncated ...
```
