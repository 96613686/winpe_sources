# VmsOmPortCreate

- ea: `0x14007f3c0`
- end: `0x140080404`
- name: `VmsOmPortCreate`
- size: `4164`
- prototype: ``
- caller_count: `3`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400cbde4`
- `0x1400fc724`
- `0x140107a74`

## callees

- `0x14001484c`
- `0x140014988`
- `0x140027a64`
- `0x14002df00`
- `0x14002e0f0`
- `0x14003a450`
- `0x140046d18`
- `0x140046e5c`
- `0x140046f1c`
- `0x140047204`
- `0x14005ddc4`
- `0x14006b084`
- `0x14006e100`
- `0x14006f2b8`
- `0x140070a00`
- `0x140070b04`
- `0x1400715e8`
- `0x140075cd0`
- `0x140077844`
- `0x140077bd0`
- `0x14007f3c0`
- `0x14008497c`
- `0x140086d28`
- `0x14008af60`
- `0x14009128c`
- `0x1400f0da8`
- `0x140105de8`
- `0x140106f38`
- `0x140108050`
- `0x14010b2bc`
- `0x14010b970`
- `0x14010d770`
- `0x14010ea8c`
- `0x14010ebc8`
- `0x14010f414`
- `0x1401110e0`
- `0x140112cb8`
- `0x140112dd8`
- `0x1401933cc`
- `0x1401bbb64`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1400802e9`
- `ntoskrnl!RtlDeleteHashTable` at `0x1400802e9`
- `ntoskrnl!RtlCreateHashTable` at `0x14007fbb1`
- `ntoskrnl!RtlCreateHashTable` at `0x14007fbb1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007fa1d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007fa77`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007fa1d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007fa77`
- `ntoskrnl!KeInitializeMutex` at `0x14007f7cc`
- `ntoskrnl!KeInitializeMutex` at `0x14007f7cc`
- `ntoskrnl!KeReleaseMutex` at `0x1400803c6`
- `ntoskrnl!KeReleaseMutex` at `0x1400803c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007f4f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007f4f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080315`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080315`
- `ntoskrnl!ExAllocatePool2` at `0x14007fc30`
- `ntoskrnl!ExAllocatePool2` at `0x14007fc30`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400802c5`
- `NDIS!NdisFreeNetBufferListPool` at `0x1400802c5`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14007fad8`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14007fad8`
- `NDIS!NdisReleaseRWLock` at `0x14007f556`
- `NDIS!NdisReleaseRWLock` at `0x14007fd47`
- `NDIS!NdisReleaseRWLock` at `0x14007fd62`
- `NDIS!NdisReleaseRWLock` at `0x14007ff7f`
- `NDIS!NdisReleaseRWLock` at `0x140080395`
- `NDIS!NdisReleaseRWLock` at `0x1401bce8a`
- `NDIS!NdisReleaseRWLock` at `0x1401bcebf`
- `NDIS!NdisReleaseRWLock` at `0x14007f556`
- `NDIS!NdisReleaseRWLock` at `0x14007fd47`
- `NDIS!NdisReleaseRWLock` at `0x14007fd62`
- `NDIS!NdisReleaseRWLock` at `0x14007ff7f`
- `NDIS!NdisReleaseRWLock` at `0x140080395`
- `NDIS!NdisReleaseRWLock` at `0x1401bce8a`
- `NDIS!NdisReleaseRWLock` at `0x1401bcebf`

## pseudocode

```c
__int64 __fastcall VmsOmPortCreate(
        __int64 a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        char **a11)
{
  int v15; // r9d
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // edx
  __int64 v20; // r8
  __int64 v21; // r15
  int v22; // edx
  char *v23; // rsi
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  NDIS_HANDLE NetBufferListPool; // rax
  int v28; // edx
  int v29; // edx
  __int64 Pool2; // rax
  int v31; // edx
  char **v32; // rcx
  int v33; // r8d
  int v34; // edx
  int v35; // edx
  _QWORD *v36; // rcx
  PVOID *v37; // rax
  __int64 v38; // rdx
  char **v39; // rax
  __int64 v40; // rdx
  _QWORD *v41; // rbx
  union _LARGE_INTEGER *v42; // r15
  __int64 v43; // rax
  const EVENT_DESCRIPTOR *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rbx
  __int64 v47; // r14
  __int64 v48; // r15
  __int64 v49; // rax
  int v50; // edx
  int v51; // r8d
  char *v52; // rbx
  int v53; // eax
  int v54; // r8d
  void *v55; // rcx
  void *v56; // rcx
  _QWORD *v57; // rax
  PVOID *v58; // rcx
  __int64 v60; // [rsp+0h] [rbp-178h] BYREF
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-158h]
  PCUNICODE_STRING v62; // [rsp+28h] [rbp-150h]
  PCUNICODE_STRING v63; // [rsp+30h] [rbp-148h]
  char v64[8]; // [rsp+38h] [rbp-140h]
  char v65[8]; // [rsp+40h] [rbp-138h]
  int SwitchUnsafe; // [rsp+80h] [rbp-F8h]
  char v67; // [rsp+84h] [rbp-F4h]
  char v68[4]; // [rsp+88h] [rbp-F0h]
  char v69; // [rsp+8Ch] [rbp-ECh]
  struct _LOCK_STATE_EX v70; // [rsp+90h] [rbp-E8h] BYREF
  char v71; // [rsp+94h] [rbp-E4h]
  char v72; // [rsp+95h] [rbp-E3h]
  char v73; // [rsp+96h] [rbp-E2h]
  char v74; // [rsp+97h] [rbp-E1h]
  char v75; // [rsp+98h] [rbp-E0h]
  char v76; // [rsp+99h] [rbp-DFh]
  char v77; // [rsp+9Ah] [rbp-DEh]
  struct _LOCK_STATE_EX LockState; // [rsp+9Ch] [rbp-DCh] BYREF
  __int64 *v79; // [rsp+A0h] [rbp-D8h]
  __int64 v80; // [rsp+A8h] [rbp-D0h] BYREF
  int v81; // [rsp+B0h] [rbp-C8h]
  PVOID DeferredContext; // [rsp+B8h] [rbp-C0h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-B8h]
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+C8h] [rbp-B0h] BYREF
  char v85[8]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-A0h]
  __int64 v87; // [rsp+E0h] [rbp-98h]
  __int64 v88; // [rsp+E8h] [rbp-90h]
  char **v89; // [rsp+F0h] [rbp-88h]
  __int64 v90; // [rsp+F8h] [rbp-80h]
  const UNICODE_STRING *v91; // [rsp+100h] [rbp-78h]
  __int64 v92; // [rsp+108h] [rbp-70h]
  __int64 v93; // [rsp+110h] [rbp-68h]
  char **v94; // [rsp+118h] [rbp-60h]
  _BYTE Parameters[20]; // [rsp+120h] [rbp-58h] BYREF

  v79 = &v60;
  v87 = (__int64)a4;
  v88 = (__int64)a2;
  v86 = a1;
  v93 = a1;
  v92 = (__int64)a2;
  v91 = a3;
  v90 = (__int64)a4;
  v89 = a11;
  v94 = a11;
  SwitchUnsafe = 0;
  v80 = 0;
  DeferredContext = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_WORD *)&v70.OldIrql = 0;
  v70.Flags = 0;
  memset(Parameters, 0, sizeof(Parameters));
  v73 = 0;
  v69 = 0;
  v77 = 0;
  HashTable = 0;
  v74 = 0;
  v75 = 0;
  v83 = 0;
  v76 = 0;
  v67 = 0;
  v72 = 0;
  v71 = 0;
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  if ( (unsigned __int8)VmsOmIsObjectMarkedForDeletion(a1, a2, 0) )
  {
    VmsOmDeleteObjectRegistryKey(a1, a2, 0);
    SwitchUnsafe = -1073741738;
    *(_DWORD *)v68 = 5;
    goto LABEL_3;
  }
  SwitchUnsafe = VmsOmpObjectAllocate(
                   0x51C0u,
                   0,
                   2,
                   8,
                   a2,
                   a3,
                   a4,
                   (__int64)VmsOmpPortDeleted,
                   (__int64 *)&DeferredContext);
  if ( SwitchUnsafe < 0 )
  {
    *(_DWORD *)v68 = 10;
    goto LABEL_3;
  }
  VmsUtilLockShared(v18, &LockState, 0);
  v69 = 1;
  SwitchUnsafe = VmsOmFindSwitchUnsafe(a1, &v80);
  if ( SwitchUnsafe )
  {
    SwitchUnsafe = -1073741766;
    *(_DWORD *)v68 = 15;
    goto LABEL_3;
  }
  *(_DWORD *)v68 = 0;
  v81 = (unsigned __int16)a5;
  if ( (a5 & 0x20000) != 0 && (unsigned __int16)a5 != 2 )
  {
    *(_DWORD *)v68 = 20;
    SwitchUnsafe = -1073741811;
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v80 + 9096), v19, 20, 27, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids);
    goto LABEL_3;
  }
  LOBYTE(v20) = 1;
  v21 = v80;
  VmsOmObjectLockExclusive(v80, &v70, v20);
  if ( *(_DWORD *)(v21 + 68) != 1 )
  {
    SwitchUnsafe = -1073741766;
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v21 + 9096),
      v22,
      20,
      28,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      *(_DWORD *)(v21 + 68));
    *(_DWORD *)v68 = 25;
    local_unwind_0(v79, &loc_14007F53B);
  }
  SwitchUnsafe = VmsOmpFindPortInListUnsafe(v21 + 1416, a2, v85);
  if ( !SwitchUnsafe )
  {
    SwitchUnsafe = -1073741771;
    *(_DWORD *)v68 = 30;
    local_unwind_0(v79, &loc_14007F53B);
  }
  SwitchUnsafe = VmsOmpFindPortInListUnsafe(v21 + 8552, a2, v85);
  if ( !SwitchUnsafe )
  {
    SwitchUnsafe = -1073741771;
    *(_DWORD *)v68 = 35;
    local_unwind_0(v79, &loc_14007F53B);
  }
  v23 = (char *)DeferredContext;
  KeInitializeMutex((PRKMUTEX)((char *)DeferredContext + 1144), 0xFFFFu);
  *((_DWORD *)v23 + 544) = 1;
  *((_WORD *)v23 + 1092) = 0;
  *((_QWORD *)v23 + 402) = 10;
  *((_QWORD *)v23 + 155) = v21;
  *((_DWORD *)v23 + 2634) = a5;
  *((_QWORD *)v23 + 406) = v23 + 3256;
  *((_DWORD *)v23 + 810) = 0x8000000;
  *((_QWORD *)v23 + 664) = v23 + 5320;
  *((_DWORD *)v23 + 1326) = 0x1000000;
  *((_QWORD *)v23 + 698) = v23 + 5592;
  *((_DWORD *)v23 + 1394) = 0x1000000;
  v23[12000] = VmsEnableHwTimestampOverVmbus;
  *(_DWORD *)(v23 + 12001) = 0;
  *((_DWORD *)v23 + 1578) = a6;
  if ( (unsigned __int16)a5 == 1 )
  {
    VmsOmSwitchCopyDefaultQueueOffloadInfo(v21, v23);
  }
  else
  {
    *((_WORD *)v23 + 3170) = 257;
    *((_DWORD *)v23 + 1586) = 16;
    *((_DWORD *)v23 + 1587) = VmsMinNumberOfQueuesPerVPort;
    *((_DWORD *)v23 + 1588) = VmsQsUserConfig;
    *((_WORD *)v23 + 3178) = 0;
    *((_DWORD *)v23 + 1590) = 3;
    v23[6364] = 1;
    if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
      McTemplateK0zzqqq_EtwWriteTransfer(v25, v24, v26, *((_QWORD *)v23 + 10), *((_QWORD *)v23 + 78), 0, 1, 0);
  }
  v23[6440] = 0;
  *((_QWORD *)v23 + 804) = 0;
  *((_DWORD *)v23 + 1607) = (unsigned __int16)VmsNumberOfIndirectionTableEntries;
  *((_DWORD *)v23 + 1611) = -1;
  *((_DWORD *)v23 + 1742) = -1;
  v23[6972] = VmsDefaultHostNicRecvUseL2RssTable;
  memset(v23 + 6448, 255, 0x200u);
  *((_DWORD *)v23 + 2321) = 0;
  VmsPlanClearParameters();
  VmsOmPortInitializePlanSettings(v23);
  *((_DWORD *)v23 + 1462) = a7;
  *((_DWORD *)v23 + 1500) = 0;
  *((_WORD *)v23 + 3002) = 0;
  *((_DWORD *)v23 + 1502) = 0;
  v23[6012] = 0;
  *((_WORD *)v23 + 3142) = 0;
  *((_DWORD *)v23 + 2992) = a10;
  SwitchUnsafe = VmsOmPortAclInitialize(v23);
  if ( SwitchUnsafe )
  {
    *(_DWORD *)v68 = 40;
    SwitchUnsafe = -1073741670;
    local_unwind_0(v79, &loc_14007F53B);
  }
  v73 = 1;
  *((_QWORD *)v23 + 1305) = v23 + 10432;
  *((_QWORD *)v23 + 1304) = v23 + 10432;
  *((_QWORD *)v23 + 1312) = v23 + 10488;
  *((_QWORD *)v23 + 1311) = v23 + 10488;
  *((_QWORD *)v23 + 1323) = v23 + 10576;
  *((_QWORD *)v23 + 1322) = v23 + 10576;
  *((_QWORD *)v23 + 1325) = v23 + 10592;
  *((_QWORD *)v23 + 1324) = v23 + 10592;
  if ( g_NVBugFixes2509SriovMacSpoofingEnabled )
  {
    KeInitializeSpinLock((PKSPIN_LOCK)v23 + 1503);
    *((_QWORD *)v23 + 1502) = v23 + 12008;
    *((_QWORD *)v23 + 1501) = v23 + 12008;
    *((_DWORD *)v23 + 3008) = 0;
    memset(v23 + 12040, 0, 0x200u);
    memset(v23 + 12552, 0, 0x1FFCu);
  }
  *((_QWORD *)v23 + 1499) = 0;
  *((_QWORD *)v23 + 1498) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)v23 + 738);
  Parameters[13] = 0;
  *(_WORD *)&Parameters[14] = 0;
  *(_DWORD *)&Parameters[16] = 0;
  *(_DWORD *)Parameters = 1311104;
  *(_DWORD *)&Parameters[4] = 15204608;
  strcpy(&Parameters[8], "VsNC");
  *((_DWORD *)v23 + 1579) = a9;
  NetBufferListPool = NdisAllocateNetBufferListPool(VmsProtocolHandle, (PNET_BUFFER_LIST_POOL_PARAMETERS)Parameters);
  *((_QWORD *)v23 + 739) = NetBufferListPool;
  if ( !NetBufferListPool )
  {
    SwitchUnsafe = -1073741670;
    LOBYTE(v28) = 2;
    WPP_RECORDER_SF_id(
      *(_QWORD *)(v21 + 9096),
      v28,
      20,
      29,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      (char)VmsProtocolHandle,
      154);
    *(_DWORD *)v68 = 45;
    local_unwind_0(v79, &loc_14007F53B);
  }
  SwitchUnsafe = VmsOmpPortInitializeFlowTable(v23);
  if ( SwitchUnsafe )
  {
    *(_DWORD *)v68 = 50;
    SwitchUnsafe = -1073741670;
    local_unwind_0(v79, &loc_14007F53B);
  }
  v75 = 1;
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v23 + 10368);
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    SwitchUnsafe = -1073741823;
    LOBYTE(v29) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v21 + 9096), v29, 20, 30, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, 1);
    *(_DWORD *)v68 = 55;
    local_unwind_0(v79, &loc_14007F53B);
  }
  v74 = 1;
  Pool2 = ExAllocatePool2(64, 1056, 1649374038);
  *((_QWORD *)v23 + 1318) = Pool2;
  if ( !Pool2 )
  {
    SwitchUnsafe = -1073741670;
    LOBYTE(v31) = 2;
    WPP_RECORDER_SF_ld(
      *(_QWORD *)(v21 + 9096),
      v31,
      20,
      31,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      32,
      154);
    *(_DWORD *)v68 = 60;
    local_unwind_0(v79, &loc_14007F53B);
  }
  SwitchUnsafe = VmsPortMapAssignIdUnsafe(v21 + 6496, v23);
  if ( SwitchUnsafe < 0 )
  {
    *(_DWORD *)v68 = 65;
    local_unwind_0(v79, &loc_14007F53B);
  }
  v76 = 1;
  v32 = *(char ***)(v21 + 8560);
  if ( *v32 != (char *)(v21 + 8552) )
    __fastfail(3u);
  *(_QWORD *)v23 = v21 + 8552;
  *((_QWORD *)v23 + 1) = v32;
  *v32 = v23;
  *(_QWORD *)(v21 + 8560) = v23;
  v67 = 1;
  VmsOmpObjectReference(v21, 0);
  v77 = 1;
  if ( v81 != 6 )
    VmsOmPortCopyDataUnsafe(v23, *((_QWORD *)v23 + 1318));
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v21 + 56), &v70);
  NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
  v69 = 0;
  if ( v81 != 6 )
  {
    v83 = *(_QWORD *)(*((_QWORD *)v23 + 155) + 4264LL);
    v34 = v83;
    *(_DWORD *)(*((_QWORD *)v23 + 1318) + 1052LL) = 1;
    v23[1268] = 1;
    SwitchUnsafe = VmsEptProcessPublicOid(v21, v34, v33, 66168, *((_QWORD *)v23 + 1318), 1056);
    if ( SwitchUnsafe < 0 )
    {
      VmsEtwTraceVmqAllocationFailure(&VM_CREATE_PORT_FAILED_EXTENSIBILITY, 0, v88, v87, v86, v21 + 616);
      *(_DWORD *)v68 = 70;
      goto LABEL_3;
    }
    v72 = 1;
  }
  VmsOmObjectLockExclusive(v21, &v70, 0);
  v36 = *(_QWORD **)v23;
  if ( *(char **)(*(_QWORD *)v23 + 8LL) != v23 || (v37 = (PVOID *)*((_QWORD *)v23 + 1), *v37 != v23) )
    __fastfail(3u);
  *v37 = v36;
  v36[1] = v37;
  v67 = 0;
  if ( *(_DWORD *)(v21 + 68) != 1 )
  {
    *(_DWORD *)v68 = 75;
    SwitchUnsafe = -1073741766;
    LOBYTE(v35) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(v21 + 9096),
      v35,
      20,
      32,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      *(_DWORD *)(v21 + 68));
    local_unwind_0(v79, &loc_14007F53B);
  }
  v23[10864] = VmsTrcEvaluatePortFilter(*((unsigned int *)v23 + 1480), v21 + 616);
  v39 = *(char ***)(v21 + 1424);
  if ( *v39 != (char *)(v21 + 1416) )
    __fastfail(3u);
  *(_QWORD *)v23 = v21 + 1416;
  *((_QWORD *)v23 + 1) = v39;
  *v39 = v23;
  *(_QWORD *)(v21 + 1424) = v23;
  ++*(_DWORD *)(v21 + 1412);
  v67 = 1;
  LOBYTE(v38) = 4;
  VmsOmpObjectReference(v21, v38);
  *((_DWORD *)v23 + 17) = 1;
  if ( (a8 & 1) != 0 )
  {
    LOBYTE(v40) = 2;
    VmsOmObjectPrepareForConfigStore(v23, v40, 1);
  }
  else
  {
    v23[1228] = 0;
  }
  if ( v89 )
  {
    *v89 = v23;
    VmsOmpObjectReference(v23, 0);
    v71 = 1;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v21 + 56), &v70);
  SwitchUnsafe = VmsOmPortSetSecurity(v23);
  if ( SwitchUnsafe )
  {
    *(_DWORD *)v68 = 80;
  }
  else if ( (a8 & 1) != 0 )
  {
    SwitchUnsafe = VmsOmpPortStoreConfig(v23);
    if ( SwitchUnsafe )
      *(_DWORD *)v68 = 85;
  }
LABEL_3:
  if ( v69 )
    NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
  if ( SwitchUnsafe )
  {
    v16 = v80;
    if ( v80 )
      v45 = *(_QWORD *)(v80 + 9096);
    else
      LODWORD(v45) = VmsIfrLog;
    v46 = v90;
    v47 = v92;
    v48 = v93;
    WPP_RECORDER_SF_ZZZZDDDDDDd(
      v45,
      (unsigned __int16)a5,
      HIWORD(a5),
      v15,
      (__int64)Timeout,
      v93,
      v92,
      (__int64)v91,
      v90,
      a5,
      SBYTE2(a5),
      a6,
      a7,
      a8,
      a9,
      SwitchUnsafe);
    v49 = 0;
    if ( v16 )
      v49 = v16 + 616;
    VmsEtwTraceVmqAllocationFailure(&VM_PORT_CREATE_FAILED, v68[0], v47, v46, v48, v49);
    v52 = (char *)DeferredContext;
    if ( DeferredContext )
    {
      v53 = *((_DWORD *)DeferredContext + 17);
      if ( v53 == 1 )
      {
        if ( v94 )
          *v94 = 0;
        if ( v71 )
          VmsOmpObjectDereference(v52, 0);
        VmsOmPortDelete(v16 + 72, v52 + 72, 0, 0);
      }
      else
      {
        if ( v53 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v50,
            19,
            35,
            (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
            (__int64)"objPort->ObjectHeader.State == VmsObjectPendingInitialize");
          if ( *((_DWORD *)v52 + 17) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( v72 )
        {
          *(_DWORD *)(*((_QWORD *)v52 + 1318) + 1052LL) = 2;
          VmsEptProcessPublicOid(v16, v83, v51, 66175, *((_QWORD *)v52 + 1318), 1056);
          v52[1268] = 0;
          *(_DWORD *)(*((_QWORD *)v52 + 1318) + 1052LL) = 3;
          VmsEptProcessPublicOid(v16, v83, v54, 66169, *((_QWORD *)v52 + 1318), 1056);
        }
        if ( v73 )
          VmsOmPortAclUninitialize(v52);
        v55 = (void *)*((_QWORD *)v52 + 739);
        if ( v55 )
        {
          NdisFreeNetBufferListPool(v55);
          *((_QWORD *)v52 + 739) = 0;
        }
        if ( v74 )
          RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)(v52 + 10368));
        if ( v75 )
          VmsOmpPortUninitializeFlowTable(v52);
        v56 = (void *)*((_QWORD *)v52 + 1318);
        if ( v56 )
          ExFreePoolWithTag(v56, 0);
        VmsPlanSettingsCleanup(v52 + 8640);
        if ( v16 )
        {
          VmsOmObjectLockExclusive(v16, &v70, 0);
          if ( v67 )
          {
            v57 = *(_QWORD **)v52;
            if ( *(char **)(*(_QWORD *)v52 + 8LL) != v52 || (v58 = (PVOID *)*((_QWORD *)v52 + 1), *v58 != v52) )
              __fastfail(3u);
            *v58 = v57;
            v57[1] = v58;
          }
          if ( v76 )
            VmsPortMapRevokeIdUnsafe(v16 + 6496, v52);
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v16 + 56), &v70);
        }
        VmsOmpObjectCleanup(v52);
      }
    }
  }
  else
  {
    v16 = v80;
    if ( v80 )
      v17 = *(_QWORD *)(v80 + 9096);
    else
      LODWORD(v17) = VmsIfrLog;
    v41 = DeferredContext;
    v42 = (union _LARGE_INTEGER *)((char *)DeferredContext + 616);
    WPP_RECORDER_SF_ZZZZqq(
      v17,
      *((_QWORD *)DeferredContext + 155) + 72,
      *((_QWORD *)DeferredContext + 155),
      33,
      (__int64)Timeout,
      (__int64)DeferredContext + 72,
      (__int64)DeferredContext + 616,
      *((_QWORD *)DeferredContext + 155) + 72LL,
      *((_QWORD *)DeferredContext + 155) + 616LL,
      (char)DeferredContext,
      *((_QWORD *)DeferredContext + 155));
    v43 = v41[155];
    *(_DWORD *)v65 = a10;
    *(_DWORD *)v64 = a8;
    v63 = (PCUNICODE_STRING)(v43 + 616);
    v62 = (PCUNICODE_STRING)(v43 + 72);
    Timeout = v42;
    v44 = (const EVENT_DESCRIPTOR *)VM_PORT_CREATED;
    if ( (unsigned int)(unsigned __int16)a5 - 1 <= 1 )
      v44 = &VM_PORT_CREATED_INT_EXT;
    VmsEtwTracePortSuccess(v44, (__int64)Timeout, (__int64)v62, (__int64)v63, v64[0], v65[0]);
  }
  if ( v77 )
    VmsOmpObjectDereference(v16, 0);
  KeReleaseMutex(&VmsOmIoctlMutex, 0);
  return (unsigned int)SwitchUnsafe;
}

```

## disassembly

```asm
0x14007f3c0  mov     r11, rsp
0x14007f3c3  push    rbx
0x14007f3c4  push    rsi
0x14007f3c5  push    rdi
0x14007f3c6  push    r12
0x14007f3c8  push    r13
0x14007f3ca  push    r14
0x14007f3cc  push    r15
0x14007f3ce  sub     rsp, 140h
0x14007f3d5  mov     rax, cs:__security_cookie
0x14007f3dc  xor     rax, rsp
0x14007f3df  mov     [rsp+178h+var_40], rax
0x14007f3e7  mov     [rsp+178h+var_D8], rsp
0x14007f3ef  mov     r15, r9
0x14007f3f2  mov     [rsp+178h+var_98], r9
0x14007f3fa  mov     r14, r8
0x14007f3fd  mov     rsi, rdx
0x14007f400  mov     [rsp+178h+var_90], rdx
0x14007f408  mov     rbx, rcx
0x14007f40b  mov     [rsp+178h+var_A0], rcx
0x14007f413  mov     [rsp+178h+var_68], rcx
0x14007f41b  mov     [rsp+178h+var_70], rdx
0x14007f423  mov     [rsp+178h+var_78], r8
0x14007f42b  mov     [rsp+178h+var_80], r9
0x14007f433  mov     rax, [rsp+178h+arg_50]
0x14007f43b  mov     [rsp+178h+var_88], rax
0x14007f443  mov     [rsp+178h+var_60], rax
0x14007f44b  xor     edi, edi
0x14007f44d  mov     [rsp+178h+var_F8], edi
0x14007f454  mov     [r11-0D0h], rdi
0x14007f45b  mov     [r11-0C0h], rdi
0x14007f462  xor     eax, eax
0x14007f464  mov     word ptr [rsp+178h+LockState.OldIrql], ax
0x14007f46c  mov     [rsp+178h+LockState.Flags], al
0x14007f473  mov     word ptr [rsp+178h+var_E8.OldIrql], ax
0x14007f47b  mov     [rsp+178h+var_E8.Flags], al
0x14007f482  xorps   xmm0, xmm0
0x14007f485  movups  xmmword ptr [r11-58h], xmm0
0x14007f48a  mov     [r11-48h], eax
0x14007f48e  mov     [rsp+178h+var_E2], dil
0x14007f496  mov     [rsp+178h+var_EC], dil
0x14007f49e  mov     [rsp+178h+var_DE], dil
0x14007f4a6  mov     [r11-0B0h], rdi
0x14007f4ad  mov     [rsp+178h+var_E1], dil
0x14007f4b5  mov     [rsp+178h+var_E0], dil
0x14007f4bd  mov     [rsp+178h+var_B8], rdi
0x14007f4c5  mov     [rsp+178h+var_DF], dil
0x14007f4cd  mov     [rsp+178h+var_F4], dil
0x14007f4d5  mov     [rsp+178h+var_E3], dil
0x14007f4dd  mov     [rsp+178h+var_E4], dil
0x14007f4e5  mov     [rsp+178h+Timeout], rdi; Timeout
0x14007f4ea  xor     r9d, r9d; Alertable
0x14007f4ed  xor     r8d, r8d; WaitMode
0x14007f4f0  xor     edx, edx; WaitReason
0x14007f4f2  lea     rcx, VmsOmIoctlMutex; Object
0x14007f4f9  call    cs:__imp_KeWaitForSingleObject
0x14007f500  nop     dword ptr [rax+rax+00h]
0x14007f505  xor     r8d, r8d
0x14007f508  mov     rdx, rsi
0x14007f50b  mov     rcx, rbx
0x14007f50e  call    VmsOmIsObjectMarkedForDeletion
0x14007f513  test    al, al
0x14007f515  jz      short loc_14007F58E
0x14007f517  xor     r8d, r8d
0x14007f51a  mov     rdx, rsi
0x14007f51d  mov     rcx, rbx
0x14007f520  call    VmsOmDeleteObjectRegistryKey
0x14007f525  mov     [rsp+178h+var_F8], 0C0000056h
0x14007f530  mov     dword ptr [rsp+178h+var_F0], 5
0x14007f53b  xor     edi, edi
0x14007f53d  cmp     [rsp+178h+var_EC], dil
0x14007f545  jz      short loc_14007F562
0x14007f547  lea     rdx, [rsp+178h+LockState]; LockState
0x14007f54f  mov     rcx, cs:VmsOmObjectListLock; Lock
0x14007f556  call    cs:__imp_NdisReleaseRWLock
0x14007f55d  nop     dword ptr [rax+rax+00h]
0x14007f562  mov     eax, [rsp+178h+var_F8]
0x14007f569  test    eax, eax
0x14007f56b  jnz     loc_1400800A4
0x14007f571  mov     rsi, [rsp+178h+var_D0]
0x14007f579  test    rsi, rsi
0x14007f57c  jz      loc_14007FFE7
0x14007f582  mov     rcx, [rsi+2388h]
0x14007f589  jmp     loc_14007FFEE
0x14007f58e  lea     rax, [rsp+178h+DeferredContext]
0x14007f596  mov     qword ptr [rsp+178h+var_138], rax; __int64
0x14007f59b  lea     rax, VmsOmpPortDeleted
0x14007f5a2  mov     qword ptr [rsp+178h+var_140], rax; __int64
0x14007f5a7  mov     [rsp+178h+var_148], r15; PCUNICODE_STRING
0x14007f5ac  mov     [rsp+178h+var_150], r14; PCUNICODE_STRING
0x14007f5b1  mov     [rsp+178h+Timeout], rsi; SourceString
0x14007f5b6  mov     r9b, 8; int
0x14007f5b9  mov     r12d, 2
0x14007f5bf  mov     r8d, r12d; int
0x14007f5c2  xor     edx, edx; int
0x14007f5c4  mov     ecx, 51C0h; int
0x14007f5c9  call    VmsOmpObjectAllocate
0x14007f5ce  mov     [rsp+178h+var_F8], eax
0x14007f5d5  test    eax, eax
0x14007f5d7  jns     short loc_14007F5E9
0x14007f5d9  mov     dword ptr [rsp+178h+var_F0], 0Ah
0x14007f5e4  jmp     loc_14007F53B
0x14007f5e9  xor     r8d, r8d
0x14007f5ec  lea     rdx, [rsp+178h+LockState]
0x14007f5f4  call    VmsUtilLockShared
0x14007f5f9  mov     r14d, 1
0x14007f5ff  mov     [rsp+178h+var_EC], r14b
0x14007f607  lea     rdx, [rsp+178h+var_D0]
0x14007f60f  mov     rcx, rbx
0x14007f612  call    VmsOmFindSwitchUnsafe
0x14007f617  mov     [rsp+178h+var_F8], eax
0x14007f61e  test    eax, eax
0x14007f620  jz      short loc_14007F63D
0x14007f622  mov     [rsp+178h+var_F8], 0C000003Ah
0x14007f62d  mov     dword ptr [rsp+178h+var_F0], 0Fh
0x14007f638  jmp     loc_14007F53B
0x14007f63d  mov     dword ptr [rsp+178h+var_F0], edi
0x14007f644  mov     ebx, [rsp+178h+arg_20]
0x14007f64b  movzx   r13d, bx
0x14007f64f  mov     [rsp+178h+var_C8], r13d
0x14007f657  bt      ebx, 11h
0x14007f65b  jnb     short loc_14007F6A8
0x14007f65d  cmp     r13d, r12d
0x14007f660  jz      short loc_14007F6A8
0x14007f662  mov     ebx, 14h
0x14007f667  mov     dword ptr [rsp+178h+var_F0], ebx
0x14007f66e  mov     [rsp+178h+var_F8], 0C000000Dh
0x14007f679  lea     r9d, [rbx+7]
0x14007f67d  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14007f684  mov     [rsp+178h+Timeout], rax
0x14007f689  mov     r8d, ebx
0x14007f68c  mov     dl, r12b
0x14007f68f  mov     rcx, [rsp+178h+var_D0]
0x14007f697  mov     rcx, [rcx+2388h]
0x14007f69e  call    WPP_RECORDER_SF_
0x14007f6a3  jmp     loc_14007F53B
0x14007f6a8  mov     r8b, r14b
0x14007f6ab  lea     rdx, [rsp+178h+var_E8]
0x14007f6b3  mov     r15, [rsp+178h+var_D0]
0x14007f6bb  mov     rcx, r15
0x14007f6be  call    VmsOmObjectLockExclusive
0x14007f6c3  cmp     [r15+44h], r14d
0x14007f6c7  jz      short loc_14007F720
0x14007f6c9  mov     [rsp+178h+var_F8], 0C000003Ah
0x14007f6d4  mov     r9d, 1Ch
0x14007f6da  mov     eax, [r15+44h]
0x14007f6de  mov     dword ptr [rsp+178h+var_150], eax
0x14007f6e2  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14007f6e9  mov     [rsp+178h+Timeout], rax
0x14007f6ee  lea     r8d, [r9-8]
0x14007f6f2  mov     dl, r12b
0x14007f6f5  mov     rcx, [r15+2388h]
0x14007f6fc  call    WPP_RECORDER_SF_d
0x14007f701  mov     dword ptr [rsp+178h+var_F0], 19h
0x14007f70c  lea     rdx, loc_14007F53B
0x14007f713  mov     rcx, [rsp+178h+var_D8]
0x14007f71b  call    _local_unwind_0
0x14007f720  lea     rcx, [r15+588h]
0x14007f727  lea     r8, [rsp+178h+var_A8]
0x14007f72f  mov     rdx, rsi
0x14007f732  call    VmsOmpFindPortInListUnsafe
0x14007f737  mov     [rsp+178h+var_F8], eax
0x14007f73e  test    eax, eax
0x14007f740  jnz     short loc_14007F76C
0x14007f742  mov     [rsp+178h+var_F8], 0C0000035h
0x14007f74d  mov     dword ptr [rsp+178h+var_F0], 1Eh
0x14007f758  lea     rdx, loc_14007F53B
0x14007f75f  mov     rcx, [rsp+178h+var_D8]
0x14007f767  call    _local_unwind_0
0x14007f76c  lea     rcx, [r15+2168h]
0x14007f773  lea     r8, [rsp+178h+var_A8]
0x14007f77b  mov     rdx, rsi
0x14007f77e  call    VmsOmpFindPortInListUnsafe
0x14007f783  mov     [rsp+178h+var_F8], eax
0x14007f78a  test    eax, eax
0x14007f78c  jnz     short loc_14007F7B8
0x14007f78e  mov     [rsp+178h+var_F8], 0C0000035h
0x14007f799  mov     dword ptr [rsp+178h+var_F0], 23h ; '#'
0x14007f7a4  lea     rdx, loc_14007F53B
0x14007f7ab  mov     rcx, [rsp+178h+var_D8]
0x14007f7b3  call    _local_unwind_0
0x14007f7b8  mov     rsi, [rsp+178h+DeferredContext]
0x14007f7c0  lea     rcx, [rsi+478h]; Mutex
0x14007f7c7  mov     edx, 0FFFFh; Level
0x14007f7cc  call    cs:__imp_KeInitializeMutex
0x14007f7d3  nop     dword ptr [rax+rax+00h]
0x14007f7d8  mov     [rsi+880h], r14d
0x14007f7df  mov     [rsi+888h], di
0x14007f7e6  mov     qword ptr [rsi+0C90h], 0Ah
0x14007f7f1  mov     [rsi+4D8h], r15
0x14007f7f8  mov     [rsi+2928h], ebx
0x14007f7fe  lea     rax, [rsi+0CB8h]
0x14007f805  mov     [rsi+0CB0h], rax
0x14007f80c  mov     dword ptr [rsi+0CA8h], 8000000h
0x14007f816  lea     rax, [rsi+14C8h]
0x14007f81d  mov     [rsi+14C0h], rax
0x14007f824  mov     dword ptr [rsi+14B8h], 1000000h
0x14007f82e  lea     rax, [rsi+15D8h]
0x14007f835  mov     [rsi+15D0h], rax
0x14007f83c  mov     dword ptr [rsi+15C8h], 1000000h
0x14007f846  mov     al, cs:VmsEnableHwTimestampOverVmbus
0x14007f84c  mov     [rsi+2EE0h], al
0x14007f852  mov     [rsi+2EE1h], edi
0x14007f858  mov     eax, [rsp+178h+arg_28]
0x14007f85f  mov     [rsi+18A8h], eax
0x14007f865  cmp     r13d, r14d
0x14007f868  jnz     short loc_14007F877
0x14007f86a  mov     rdx, rsi
0x14007f86d  mov     rcx, r15
0x14007f870  call    VmsOmSwitchCopyDefaultQueueOffloadInfo
0x14007f875  jmp     short loc_14007F8E7
0x14007f877  mov     word ptr [rsi+18C4h], 101h
0x14007f880  mov     dword ptr [rsi+18C8h], 10h
0x14007f88a  mov     eax, cs:VmsMinNumberOfQueuesPerVPort
0x14007f890  mov     [rsi+18CCh], eax
0x14007f896  mov     eax, dword ptr cs:VmsQsUserConfig
0x14007f89c  mov     [rsi+18D0h], eax
0x14007f8a2  mov     [rsi+18D4h], di
0x14007f8a9  mov     dword ptr [rsi+18D8h], 3
0x14007f8b3  mov     [rsi+18DCh], r14b
0x14007f8ba  mov     eax, cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits
0x14007f8c0  test    r12b, al
0x14007f8c3  jz      short loc_14007F8E7
0x14007f8c5  mov     dword ptr [rsp+178h+var_140], edi
0x14007f8c9  mov     dword ptr [rsp+178h+var_148], r14d
0x14007f8ce  mov     dword ptr [rsp+178h+var_150], edi
0x14007f8d2  mov     rax, [rsi+270h]
0x14007f8d9  mov     [rsp+178h+Timeout], rax
0x14007f8de  mov     r9, [rsi+50h]
0x14007f8e2  call    McTemplateK0zzqqq_EtwWriteTransfer
0x14007f8e7  mov     [rsi+1928h], dil
0x14007f8ee  mov     [rsi+1920h], rdi
0x14007f8f5  movzx   eax, cs:VmsNumberOfIndirectionTableEntries
0x14007f8fc  mov     [rsi+191Ch], eax
0x14007f902  mov     dword ptr [rsi+192Ch], 0FFFFFFFFh
0x14007f90c  mov     dword ptr [rsi+1B38h], 0FFFFFFFFh
0x14007f916  mov     al, cs:VmsDefaultHostNicRecvUseL2RssTable
0x14007f91c  mov     [rsi+1B3Ch], al
0x14007f922  lea     rcx, [rsi+1930h]; void *
0x14007f929  mov     ebx, 200h
0x14007f92e  mov     r8d, ebx; Size
0x14007f931  mov     edx, 0FFh; Val
0x14007f936  call    memset
0x14007f93b  lea     rcx, [rsi+21C0h]
0x14007f942  mov     [rcx+284h], edi
0x14007f948  call    VmsPlanClearParameters
0x14007f94d  mov     rcx, rsi
0x14007f950  call    VmsOmPortInitializePlanSettings
0x14007f955  mov     eax, [rsp+178h+arg_30]
0x14007f95c  mov     [rsi+16D8h], eax
0x14007f962  mov     [rsi+1770h], edi
0x14007f968  mov     [rsi+1774h], di
0x14007f96f  mov     [rsi+1778h], edi
0x14007f975  mov     [rsi+177Ch], dil
0x14007f97c  mov     [rsi+188Ch], di
0x14007f983  mov     eax, dword ptr [rsp+178h+arg_48]
0x14007f98a  mov     [rsi+2EC0h], eax
0x14007f990  mov     rcx, rsi
0x14007f993  call    VmsOmPortAclInitialize
0x14007f998  mov     [rsp+178h+var_F8], eax
0x14007f99f  test    eax, eax
0x14007f9a1  jz      short loc_14007F9CD
0x14007f9a3  mov     dword ptr [rsp+178h+var_F0], 28h ; '('
0x14007f9ae  mov     [rsp+178h+var_F8], 0C000009Ah
0x14007f9b9  lea     rdx, loc_14007F53B
0x14007f9c0  mov     rcx, [rsp+178h+var_D8]
0x14007f9c8  call    _local_unwind_0
0x14007f9cd  mov     [rsp+178h+var_E2], r14b
0x14007f9d5  lea     rax, [rsi+28C0h]
0x14007f9dc  mov     [rax+8], rax
0x14007f9e0  mov     [rax], rax
0x14007f9e3  lea     rax, [rsi+28F8h]
0x14007f9ea  mov     [rax+8], rax
0x14007f9ee  mov     [rax], rax
0x14007f9f1  lea     rax, [rsi+2950h]
0x14007f9f8  mov     [rax+8], rax
0x14007f9fc  mov     [rax], rax
0x14007f9ff  lea     rax, [rsi+2960h]
0x14007fa06  mov     [rax+8], rax
0x14007fa0a  mov     [rax], rax
0x14007fa0d  cmp     cs:g_NVBugFixes2509SriovMacSpoofingEnabled, 0
0x14007fa14  jz      short loc_14007FA62
0x14007fa16  lea     rcx, [rsi+2EF8h]; SpinLock
0x14007fa1d  call    cs:__imp_KeInitializeSpinLock
0x14007fa24  nop     dword ptr [rax+rax+00h]
0x14007fa29  lea     rax, [rsi+2EE8h]
0x14007fa30  mov     [rax+8], rax
0x14007fa34  mov     [rax], rax
0x14007fa37  mov     [rsi+2F00h], edi
0x14007fa3d  lea     rcx, [rsi+2F08h]; void *
0x14007fa44  mov     r8, rbx; Size
0x14007fa47  xor     edx, edx; Val
0x14007fa49  call    memset
0x14007fa4e  lea     rcx, [rsi+3108h]; void *
0x14007fa55  xor     edx, edx; Val
0x14007fa57  mov     r8d, 1FFCh; Size
0x14007fa5d  call    memset
0x14007fa62  mov     [rsi+2ED8h], rdi
0x14007fa69  mov     [rsi+2ED0h], rdi
0x14007fa70  lea     rcx, [rsi+1710h]; SpinLock
  ... truncated ...
```
