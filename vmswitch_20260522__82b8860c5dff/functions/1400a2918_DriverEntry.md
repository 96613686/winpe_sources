# DriverEntry

- ea: `0x1400a2918`
- end: `0x1400a36f0`
- name: `DriverEntry`
- size: `3544`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14023a010`

## callees

- `0x140027a64`
- `0x14002ce7c`
- `0x14002e0f0`
- `0x14003a450`
- `0x140046e5c`
- `0x140046f1c`
- `0x140066bec`
- `0x14008497c`
- `0x14008d9e0`
- `0x1400a2918`
- `0x1400a36f8`
- `0x1400a37d8`
- `0x1400a3ca8`
- `0x1400a3e28`
- `0x1400a40e0`
- `0x1400a461c`
- `0x1400a4714`
- `0x1400a4b70`
- `0x1400a4dd4`
- `0x1400a5254`
- `0x1400a5fa8`
- `0x1400a6f64`
- `0x1400a8d8c`
- `0x1400f6570`
- `0x140106248`
- `0x140106418`
- `0x140117b4c`
- `0x14014c734`
- `0x14014ef60`
- `0x140151f94`
- `0x14015c9f0`
- `0x140176508`
- `0x1401768bc`
- `0x14018546c`
- `0x1401854f4`
- `0x14018a6b8`
- `0x1401a1cb0`
- `0x1401ad3bc`
- `0x1401b67ec`
- `0x1401b95d8`
- `0x1401b9884`
- `0x1401bb98c`
- `0x1401bc2c0`
- `0x14023a078`
- `0x14023a638`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x1400a2e01`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400a2d36`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400a2d36`
- `ntoskrnl!KeInitializeMutex` at `0x1400a2c5d`
- `ntoskrnl!KeInitializeMutex` at `0x1400a2c5d`
- `ntoskrnl!IoCreateDevice` at `0x1400a352c`
- `ntoskrnl!IoCreateDevice` at `0x1400a352c`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2acc`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400a2acc`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400a2ab8`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400a2ab8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400a2a87`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400a2a87`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400a2a50`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400a2a50`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a2a74`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a3283`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a329d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a32b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a33e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a34f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a2a74`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a3283`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a329d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a32b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a33e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a34f6`
- `NDIS!NdisRegisterProtocolDriver` at `0x1400a3492`
- `NDIS!NdisRegisterProtocolDriver` at `0x1400a3492`
- `NDIS!NdisIMAssociateMiniport` at `0x1400a2f01`
- `NDIS!NdisIMAssociateMiniport` at `0x1400a2f01`
- `NDIS!NdisMRegisterMiniportDriver` at `0x1400a3014`
- `NDIS!NdisMRegisterMiniportDriver` at `0x1400a3014`
- `NDIS!NdisSetOptionalHandlers` at `0x1400a31fe`
- `NDIS!NdisSetOptionalHandlers` at `0x1400a31fe`
- `NDIS!NdisAllocateRWLock` at `0x1400a2e29`
- `NDIS!NdisAllocateRWLock` at `0x1400a2e29`
- `NDIS!NdisFRegisterFilterDriver` at `0x1400a3388`
- `NDIS!NdisFRegisterFilterDriver` at `0x1400a3388`

## string_xrefs

- `0x1400a2a30`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services\VMSMP`
- `0x1400a3261`: `Hyper-V Virtual Switch Extension Filter`
- `0x1400a3637`: `Installed and Started.`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v4; // di
  int v5; // eax
  int v6; // r15d
  int v7; // edx
  __int64 *v8; // rcx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // edx
  int v14; // eax
  int v15; // edx
  int started; // eax
  int v17; // edx
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  NDIS_STATUS v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // r8d
  NTSTATUS v25; // eax
  int v26; // edx
  __int64 i; // rbx
  int v28; // edx
  int v29; // edx
  int Flags; // [rsp+20h] [rbp-E0h]
  char v32; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v33; // [rsp+51h] [rbp-AFh]
  char v34; // [rsp+53h] [rbp-ADh]
  int v35; // [rsp+54h] [rbp-ACh]
  int v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+5Ch] [rbp-A4h]
  int v38; // [rsp+60h] [rbp-A0h]
  _QWORD v39[2]; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING v41; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING v42; // [rsp+98h] [rbp-68h] BYREF
  UNICODE_STRING v43; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING v44; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+C8h] [rbp-38h] BYREF
  _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE MiniportDriverCharacteristics[160]; // [rsp+160h] [rbp+60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+200h] [rbp+100h] BYREF
  struct _UNICODE_STRING v49; // [rsp+210h] [rbp+110h] BYREF
  struct _UNICODE_STRING v50; // [rsp+220h] [rbp+120h] BYREF
  struct _UNICODE_STRING v51; // [rsp+230h] [rbp+130h] BYREF
  struct _UNICODE_STRING v52; // [rsp+240h] [rbp+140h] BYREF
  _BYTE OptionalHandlers[240]; // [rsp+250h] [rbp+150h] BYREF
  struct _NDIS_FILTER_DRIVER_CHARACTERISTICS FilterDriverCharacteristics; // [rsp+340h] [rbp+240h] BYREF
  int v55; // [rsp+480h] [rbp+380h] BYREF
  __int64 v56; // [rsp+488h] [rbp+388h] BYREF

  v49 = 0;
  v51 = 0;
  v50 = 0;
  memset(MiniportDriverCharacteristics, 0, sizeof(MiniportDriverCharacteristics));
  DestinationString = 0;
  memset(&ProtocolCharacteristics, 0, sizeof(ProtocolCharacteristics));
  v52 = 0;
  memset(OptionalHandlers, 0, 0xECu);
  memset(&FilterDriverCharacteristics, 0, 0xF0u);
  *(_QWORD *)&SourceString.Length = 1703960;
  SourceString.Buffer = L"DriverGlobal";
  *(_QWORD *)&v42.Length = 1441812;
  v42.Buffer = L"PortGlobal";
  *(_QWORD *)&v43.Length = 1310738;
  v43.Buffer = L"NicGlobal";
  *(_QWORD *)&v41.Length = 655368;
  v41.Buffer = L"VRSS";
  v4 = 10;
  *(_QWORD *)&v44.Length = 1441812;
  v44.Buffer = L"StackTrace";
  v39[1] = L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Services\\VMSMP";
  DeviceName = 0;
  v39[0] = 7602290;
  v56 = 0;
  v5 = KeQueryInterruptTimePrecise(&v56);
  VmsDriverObject = DriverObject;
  v6 = v5;
  RtlInitUnicodeString(&DestinationString, L"MmGetSystemRoutineAddressEx");
  VmsGetSystemRoutineAddressEx = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  VmsTrcLogInitialize(DriverObject, v39);
  VmsRteInitialize();
  wil_InitializeFeatureStaging();
  VmsActiveProcCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  VmsMaximumProcCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  v8 = WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids;
  if ( !VmsMaximumProcCount )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      23,
      (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids,
      (__int64)"VmsMaximumProcCount > 0");
    if ( !VmsMaximumProcCount )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  VmsEtwStartTrace(v8);
  InitializeTelemetryAssertsKMByDriverObject(DriverObject);
  if ( dword_1401F68A0 )
    VmsTraceLogDriverOperationBegin("DriverEntry", v9, "Started Loading");
  if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) != 0 )
    McTemplateK0qssttss_EtwWriteTransfer();
  VmsCdInitializeVswitchGeneration();
  VmsDefaultNblForwardingDetail = 1;
  VmsPDClientHandle = 0;
  VmsPDPlatformDispatch = 0;
  VmsPDSwitchCount = 0;
  v11 = VmsCsInitialize();
  if ( !v11 )
  {
    VmsReadGlobalParameters();
    v11 = VmsIfrLogCreate(&SourceString);
    if ( v11 )
    {
      v4 = 20;
      goto LABEL_69;
    }
    v11 = VmsIfrLogCreate(&v41);
    if ( v11 )
    {
      v4 = 21;
      goto LABEL_69;
    }
    v11 = VmsIfrLogCreate(&v42);
    if ( v11 )
    {
      v4 = 22;
      goto LABEL_69;
    }
    v11 = VmsIfrLogCreate(&v43);
    if ( v11 )
    {
      v4 = 23;
      goto LABEL_69;
    }
    v11 = VmsIfrLogCreate(&v44);
    if ( v11 )
    {
      v4 = 25;
      goto LABEL_69;
    }
    VmsPopulateCacheLineSize();
    v11 = ExecMonitorInit();
    if ( v11 )
    {
      v4 = 26;
      goto LABEL_69;
    }
    KeInitializeMutex(&Mutex, 0xFFFFu);
    byte_1401F95F0 = 1;
    v11 = VmsProxyRegister();
    if ( v11 )
    {
      v4 = 27;
      goto LABEL_69;
    }
    v11 = VmsCdNicProxyRegister();
    if ( v11 < 0 )
    {
      v4 = 28;
      goto LABEL_69;
    }
    v11 = VmsScQosInit();
    if ( v11 )
    {
      v4 = 30;
      goto LABEL_69;
    }
    Vms37HashSeed = MEMORY[0xFFFFF78000000008];
    v11 = VmsScIPsecOffloadStateInit();
    if ( v11 )
    {
      v4 = 40;
      goto LABEL_69;
    }
    v11 = VmsQsInitialize();
    if ( v11 )
    {
      v4 = 50;
      goto LABEL_69;
    }
    v11 = VmsPtInitialize();
    if ( v11 )
    {
      v4 = 60;
      goto LABEL_69;
    }
    if ( !byte_1401F96A0 )
    {
      v11 = ExInitializeLookasideListEx(&g_NvLibContext, 0, 0, NonPagedPoolNx, 0, 0x80u, 0x6C766E48u, 0);
      if ( v11 < 0 )
      {
        v4 = 70;
        goto LABEL_69;
      }
      byte_1401F96A0 = 1;
    }
    v11 = VmsVmInitialize();
    if ( v11 )
    {
      v4 = 90;
    }
    else
    {
      v37 = VmsVmMaxNBLsPerFlush;
      v35 = VmsVmMaxBatchesPerFlush;
      v36 = VmsVmBatchCopyLookAsideBatchSize;
      v38 = VmsVmBatchCopyOnStackBatchSize;
      v34 = 0;
      v33 = (VmsDiagnosticFlags & 2) != 0;
      v32 = 1;
      v11 = BLInitializeEx(&v32);
      if ( v11 )
      {
        v4 = 95;
      }
      else
      {
        byte_1401FA259 = 1;
        SegLibInitialize();
        byte_1401FA258 = 1;
        v11 = VmsOmLockInitialize();
        if ( v11 )
        {
          v4 = 105;
        }
        else
        {
          v11 = VmsOmInitialize();
          if ( v11 )
          {
            v4 = 115;
          }
          else
          {
            VmsIoctlInitialize(v12, ExFreePool);
            qword_1401F9908 = &qword_1401F9900;
            qword_1401F9900 = (__int64)&qword_1401F9900;
            Lock = NdisAllocateRWLock(VmsMiniportHandle);
            if ( Lock )
            {
              byte_1401F98F8 = 1;
            }
            else
            {
              LOBYTE(v13) = 2;
              WPP_RECORDER_SF_(VmsIfrLog, v13, 20, 12, (__int64)WPP_37e4495ad84b3e8f3e1366754a49d47d_Traceguids);
            }
            VmsMpNicCreateOrEnableAll();
            v14 = VmsRegisterProtocol();
            v11 = v14;
            if ( v14 )
            {
              LOBYTE(v15) = 2;
              WPP_RECORDER_SF_d(VmsIfrLog, v15, 20, 24, (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids, v14);
              v4 = 120;
            }
            else
            {
              started = VmsStartPD();
              v11 = started;
              if ( started )
              {
                LOBYTE(v17) = 2;
                WPP_RECORDER_SF_d(
                  VmsIfrLog,
                  v17,
                  20,
                  25,
                  (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids,
                  started);
                v4 = 125;
              }
              else
              {
                NdisIMAssociateMiniport(VmsMiniportHandle, VmsProtocolHandle);
                *(_DWORD *)MiniportDriverCharacteristics = 10486666;
                *(_QWORD *)&MiniportDriverCharacteristics[8] = 0;
                *(_QWORD *)&MiniportDriverCharacteristics[152] = 0;
                *(_DWORD *)&MiniportDriverCharacteristics[4] = 1266438;
                *(_QWORD *)&MiniportDriverCharacteristics[24] = VmsExtMpInitializeEx;
                *(_QWORD *)&MiniportDriverCharacteristics[96] = 0;
                *(_QWORD *)&MiniportDriverCharacteristics[32] = VmsExtMpHaltEx;
                *(_QWORD *)&MiniportDriverCharacteristics[104] = 0;
                *(_QWORD *)&MiniportDriverCharacteristics[40] = VmsExtMpDriverUnload;
                *(_QWORD *)&MiniportDriverCharacteristics[48] = VmsExtMpPause;
                *(_QWORD *)&MiniportDriverCharacteristics[56] = VmsExtMpRestart;
                *(_QWORD *)&MiniportDriverCharacteristics[64] = VmsExtMpOidRequest;
                *(_QWORD *)&MiniportDriverCharacteristics[128] = VmsMpNicCancelOidRequest;
                *(_QWORD *)&MiniportDriverCharacteristics[136] = VmsExtMpDirectOidRequest;
                *(_QWORD *)&MiniportDriverCharacteristics[144] = VmsMpNicCancelOidRequest;
                *(_QWORD *)&MiniportDriverCharacteristics[72] = VmsExtMpSendNetBufferLists;
                *(_QWORD *)&MiniportDriverCharacteristics[80] = VmsExtMpReturnNetBufferLists;
                *(_QWORD *)&MiniportDriverCharacteristics[88] = VmsMpNicCancelOidRequest;
                *(_QWORD *)&MiniportDriverCharacteristics[112] = VmsExtMpDevicePnPEvent;
                *(_QWORD *)&MiniportDriverCharacteristics[120] = VmsExtMpAdapterShutdownEx;
                *(_QWORD *)&MiniportDriverCharacteristics[16] = 0;
                v11 = NdisMRegisterMiniportDriver(
                        DriverObject,
                        RegistryPath,
                        0,
                        (PNDIS_MINIPORT_DRIVER_CHARACTERISTICS)MiniportDriverCharacteristics,
                        &VmsVswitchMiniportHandle);
                if ( v11 )
                {
                  WPP_RECORDER_SF_ddD(
                    MiniportDriverCharacteristics[4],
                    v18,
                    v19,
                    v20,
                    Flags,
                    MiniportDriverCharacteristics[4],
                    MiniportDriverCharacteristics[5],
                    v11);
                  v4 = -126;
                }
                else
                {
                  *(_QWORD *)&OptionalHandlers[8] = VmsExtMpNdisSwitchAllocateNblForwardingContext;
                  *(_QWORD *)OptionalHandlers = 15729336;
                  *(_QWORD *)&OptionalHandlers[16] = VmsExtMpNdisSwitchFreeNblForwardingContext;
                  *(_QWORD *)&OptionalHandlers[24] = VmsExtMpNdisSwitchSetNblSource;
                  *(_QWORD *)&OptionalHandlers[32] = VmsExtMpNdisSwitchAddNblDestination;
                  *(_QWORD *)&OptionalHandlers[40] = VmsExtMpNdisSwitchGrowNblDestinations;
                  *(_QWORD *)&OptionalHandlers[48] = VmsExtMpNdisSwitchGetNblDestinations;
                  *(_QWORD *)&OptionalHandlers[56] = VmsExtMpNdisSwitchUpdateNblDestinations;
                  *(_QWORD *)&OptionalHandlers[64] = &VmsExtMpNdisSwitchCopyNblInfo;
                  *(_QWORD *)&OptionalHandlers[72] = VmsExtMpNdisSwitchReferenceSwitchNic;
                  *(_QWORD *)&OptionalHandlers[80] = VmsExtMpNdisSwitchDereferenceSwitchNic;
                  *(_QWORD *)&OptionalHandlers[88] = VmsExtMpNdisSwitchReferenceSwitchPort;
                  *(_QWORD *)&OptionalHandlers[96] = VmsExtMpNdisSwitchDereferenceSwitchPort;
                  *(_QWORD *)&OptionalHandlers[104] = VmsExtMpNdisSwitchReportFilteredNbls;
                  *(_QWORD *)&OptionalHandlers[112] = VmsExtMpNdisSwitchSetNetBufferListSwitchContext;
                  *(_QWORD *)&OptionalHandlers[120] = VmsExtMpNdisSwitchGetNetBufferListSwitchContext;
                  *(_QWORD *)&OptionalHandlers[128] = &VmsIoExtMpNdisPDExtProviderRegisterClient;
                  *(_QWORD *)&OptionalHandlers[136] = VmsIoExtMpNdisPDExtProviderDeregisterClient;
                  *(_QWORD *)&OptionalHandlers[144] = VmsIoExtMpNdisPDExtProviderGetFreePDBuffer;
                  *(_QWORD *)&OptionalHandlers[152] = VmsIoExtMpNdisPDExtProviderReturnPDBuffer;
                  *(_QWORD *)&OptionalHandlers[160] = VmsIoExtMpNdisPDExtProviderInjectPDBuffer;
                  *(_QWORD *)&OptionalHandlers[168] = VmsIoExtMpNdisPDExtProviderCopyPDBufferInfo;
                  *(_QWORD *)&OptionalHandlers[176] = VmsIoExtMpNdisPDExtProviderGetPDBufferClientContext;
                  *(_QWORD *)&OptionalHandlers[184] = VmsIoExtMpNdisPDExtProviderGetPDBufferDestinations;
                  *(_QWORD *)&OptionalHandlers[192] = VmsIoExtMpNdisPDExtProviderAddPDBufferDestination;
                  *(_QWORD *)&OptionalHandlers[200] = VmsIoExtMpNdisPDExtProviderUpdatePDBufferDestinations;
                  *(_QWORD *)&OptionalHandlers[208] = VmsIoExtMpNdisPDExtProviderGetPDBufferForwardingDetail;
                  *(_QWORD *)&OptionalHandlers[216] = VmsIoExtMpNdisPDExtProviderSetupBufferFromPDBuffer;
                  *(_QWORD *)&OptionalHandlers[224] = VmsIoExtMpNdisPDExtProviderGrowPDBufferDestinations;
                  *(_QWORD *)&OptionalHandlers[232] = VmsIoExtMpNdisPDExtProviderGetSwitchInfo;
                  v21 = NdisSetOptionalHandlers(
                          VmsVswitchMiniportHandle,
                          (PNDIS_DRIVER_OPTIONAL_HANDLERS)OptionalHandlers);
                  v11 = v21;
                  if ( v21 )
                  {
                    LOBYTE(v22) = 2;
                    WPP_RECORDER_SF_id(
                      VmsIfrLog,
                      v22,
                      20,
                      27,
                      (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids,
                      (char)VmsVswitchMiniportHandle,
                      v21);
                    v4 = -116;
                  }
                  else
                  {
                    memset(&FilterDriverCharacteristics.Flags, 0, 0xE8u);
                    FilterDriverCharacteristics.Header = (NDIS_OBJECT_HEADER)15729547;
                    *(_DWORD *)&FilterDriverCharacteristics.MajorNdisVersion = 1266438;
                    RtlInitUnicodeString(&v49, L"Hyper-V Virtual Switch Extension Filter");
                    RtlInitUnicodeString(&v50, L"{529B8983-9625-49A5-8284-CE944FD8E242}");
                    RtlInitUnicodeString(&v51, L"VMSVSF");
                    FilterDriverCharacteristics.AttachHandler = (FILTER_ATTACH_HANDLER)VmsExtFilterAttach;
                    FilterDriverCharacteristics.SetOptionsHandler = 0;
                    FilterDriverCharacteristics.DetachHandler = (FILTER_DETACH_HANDLER)VmsExtFilterDetach;
                    FilterDriverCharacteristics.SetFilterModuleOptionsHandler = 0;
                    FilterDriverCharacteristics.RestartHandler = (FILTER_RESTART_HANDLER)VmsExtFilterRestart;
                    FilterDriverCharacteristics.CancelSendNetBufferListsHandler = 0;
                    FilterDriverCharacteristics.PauseHandler = (FILTER_PAUSE_HANDLER)VmsExtFilterPause;
                    FilterDriverCharacteristics.SendNetBufferListsHandler = (FILTER_SEND_NET_BUFFER_LISTS_HANDLER)VmsExtFilterSendNetBufferLists;
                    FilterDriverCharacteristics.SendNetBufferListsCompleteHandler = (FILTER_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)VmsExtFilterSendNetBufferListsComplete;
                    FilterDriverCharacteristics.FriendlyName = v49;
                    FilterDriverCharacteristics.ReceiveNetBufferListsHandler = (FILTER_RECEIVE_NET_BUFFER_LISTS_HANDLER)VmsExtFilterReceiveNetBufferLists;
                    FilterDriverCharacteristics.ReturnNetBufferListsHandler = (FILTER_RETURN_NET_BUFFER_LISTS_HANDLER)VmsExtFilterReturnNetBufferLists;
                    FilterDriverCharacteristics.UniqueName = v50;
                    FilterDriverCharacteristics.ServiceName = v51;
                    v11 = NdisFRegisterFilterDriver(
                            DriverObject,
                            0,
                            &FilterDriverCharacteristics,
                            &VmsVswitchFilterHandle);
                    if ( v11 )
                    {
                      WPP_RECORDER_SF_ddZD(
                        FilterDriverCharacteristics.MajorNdisVersion,
                        (unsigned int)&FilterDriverCharacteristics.FriendlyName,
                        v23,
                        28,
                        Flags,
                        FilterDriverCharacteristics.MajorNdisVersion,
                        FilterDriverCharacteristics.MinorNdisVersion,
                        (__int64)&FilterDriverCharacteristics.FriendlyName,
                        v11);
                      v4 = -106;
                    }
                    else
                    {
                      RtlInitUnicodeString(&v52, L"VMSVSP");
                      ProtocolCharacteristics.Header = (NDIS_OBJECT_HEADER)8389269;
                      *(_QWORD *)&ProtocolCharacteristics.Flags = 0;
                      *(_DWORD *)&ProtocolCharacteristics.MajorNdisVersion = 1266438;
                      ProtocolCharacteristics.BindAdapterHandlerEx = (BIND_HANDLER_EX)VmsExtPtBindAdapterEx;
                      ProtocolCharacteristics.SetOptionsHandler = 0;
                      ProtocolCharacteristics.UnbindAdapterHandlerEx = (UNBIND_HANDLER_EX)VmsExtPtUnbindAdapterEx;
                      ProtocolCharacteristics.UninstallHandler = 0;
                      ProtocolCharacteristics.OpenAdapterCompleteHandlerEx = (OPEN_ADAPTER_COMPLETE_HANDLER_EX)VmsExtPtOpenAdapterCompleteEx;
                      ProtocolCharacteristics.CloseAdapterCompleteHandlerEx = (CLOSE_ADAPTER_COMPLETE_HANDLER_EX)VmsExtPtCloseAdapterCompleteEx;
                      ProtocolCharacteristics.SendNetBufferListsCompleteHandler = (SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)VmsExtPtSendNetBufferListsComplete;
                      ProtocolCharacteristics.ReceiveNetBufferListsHandler = (RECEIVE_NET_BUFFER_LISTS_HANDLER)&VmsExtPtReceiveNetBufferLists;
                      ProtocolCharacteristics.OidRequestCompleteHandler = (OID_REQUEST_COMPLETE_HANDLER)VmsExtPtOidRequestComplete;
                      ProtocolCharacteristics.DirectOidRequestCompleteHandler = (DIRECT_OID_REQUEST_COMPLETE_HANDLER)VmsExtPtDirectOidRequestComplete;
                      ProtocolCharacteristics.StatusHandlerEx = (STATUS_HANDLER_EX)VmsExtPtStatusEx;
                      ProtocolCharacteristics.NetPnPEventHandler = (NET_PNP_EVENT_HANDLER)VmsExtPtNetPnPEvent;
                      ProtocolCharacteristics.Name = v52;
                      v11 = NdisRegisterProtocolDriver(0, &ProtocolCharacteristics, &VmsVswitchProtocolHandle);
                      if ( v11 )
                      {
                        WPP_RECORDER_SF_ddZD(
                          ProtocolCharacteristics.MajorNdisVersion,
                          (unsigned int)&ProtocolCharacteristics.Name,
                          v24,
                          29,
                          Flags,
                          ProtocolCharacteristics.MajorNdisVersion,
                          ProtocolCharacteristics.MinorNdisVersion,
                          (__int64)&ProtocolCharacteristics.Name,
                          v11);
                        v4 = -96;
                      }
                      else
                      {
                        v11 = PktMonClientInitialize();
                        if ( v11 )
                        {
                          v4 = -91;
                        }
                        else
                        {
                          RtlInitUnicodeString(&DeviceName, L"\\Device\\VmSwitchInternal");
                          v25 = IoCreateDevice(
                                  DriverObject,
                                  8u,
                                  &DeviceName,
                                  0x22u,
                                  0x100u,
                                  0,
                                  &VmsCdCtlDeviceObjectInternal);
                          v11 = v25;
                          if ( v25 < 0 )
                          {
                            LOBYTE(v26) = 2;
                            WPP_RECORDER_SF_Zd(
                              VmsIfrLog,
                              v26,
                              20,
                              30,
                              (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids,
                              (__int64)&DeviceName,
                              v25);
                            v4 = -86;
                          }
                          else
                          {
                            for ( i = 0; i != 3; ++i )
                            {
                              if ( !(unsigned __int8)VmsVmpGetProtocolVersionIndex(
                                                       *((unsigned int *)SavedStateToProtocolMapping + 3 * i + 1),
                                                       0,
                                                       (char *)&SavedStateToProtocolMapping[1] + 12 * i) )
                              {
                                WPP_RECORDER_SF_s(
                                  VmsIfrLog,
                                  v28,
                                  19,
                                  11,
                                  (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
                                  (__int64)"!\"VmsVmInitilizeVersions: Invalid version mapping\"");
                                MicrosoftTelemetryAssertTriggeredNoArgsKM();
                              }
                            }
                            IsVmsVmInitialized = 1;
                            v11 = 0;
                            v4 = 0;
                            VmsTmInitialize();
                            LOBYTE(v29) = 4;
                            WPP_RECORDER_SF_(
                              VmsIfrLog,
                              v29,
                              18,
                              31,
                              (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_69:
  if ( dword_1401F68A0 )
    VmsTraceLogDriverOperationEnd((unsigned int)"DriverEntry", v10, (unsigned int)"Installed and Started.", v6, v11);
  if ( v11 )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v10, 20, 32, (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids, v4, v11);
    v55 = v11;
    if ( VmsEtwTraceEnabled )
      VmsEtwWriteEvent(&VM_FAILED_TO_INITIALIZE, 0, 0, (char)&v55);
    VmsDriverUnload((__int64)DriverObject);
  }
  return v11;
}

```

## disassembly

```asm
0x1400a2918  mov     [rsp-8+arg_8], rbx
0x1400a291d  push    rbp
0x1400a291e  push    rsi
0x1400a291f  push    rdi
0x1400a2920  push    r12
0x1400a2922  push    r13
0x1400a2924  push    r14
0x1400a2926  push    r15
0x1400a2928  lea     rbp, [rsp-330h]
0x1400a2930  sub     rsp, 430h
0x1400a2937  xorps   xmm0, xmm0
0x1400a293a  mov     r14, rdx
0x1400a293d  mov     rsi, rcx
0x1400a2940  xorps   xmm1, xmm1
0x1400a2943  xor     edx, edx; Val
0x1400a2945  lea     rcx, [rbp+360h+MiniportDriverCharacteristics]; void *
0x1400a2949  mov     r8d, 0A0h; Size
0x1400a294f  movups  xmmword ptr [rbp+360h+var_250.Length], xmm0
0x1400a2956  movups  xmmword ptr [rbp+360h+var_230.Length], xmm1
0x1400a295d  movups  xmmword ptr [rbp+360h+var_240.Length], xmm0
0x1400a2964  call    memset
0x1400a2969  xorps   xmm0, xmm0
0x1400a296c  lea     rcx, [rbp+360h+ProtocolCharacteristics]; void *
0x1400a2970  xor     edx, edx; Val
0x1400a2972  mov     r8d, 80h; Size
0x1400a2978  movups  xmmword ptr [rbp+360h+DestinationString.Length], xmm0
0x1400a297f  call    memset
0x1400a2984  xorps   xmm0, xmm0
0x1400a2987  lea     rcx, [rbp+360h+OptionalHandlers]; void *
0x1400a298e  xor     eax, eax
0x1400a2990  xor     edx, edx; Val
0x1400a2992  mov     r8d, 0ECh; Size
0x1400a2998  mov     dword ptr [rbp+360h+OptionalHandlers.Header.Type+4], eax
0x1400a299e  movups  xmmword ptr [rbp+360h+var_220.Length], xmm0
0x1400a29a5  call    memset
0x1400a29aa  xor     edx, edx; Val
0x1400a29ac  lea     rcx, [rbp+360h+FilterDriverCharacteristics]; void *
0x1400a29b3  mov     r8d, 0F0h; Size
0x1400a29b9  call    memset
0x1400a29be  lea     rax, aDriverglobal; "DriverGlobal"
0x1400a29c5  mov     qword ptr [rsp+460h+SourceString.Length], 1A0018h
0x1400a29ce  mov     [rbp+360h+SourceString.Buffer], rax
0x1400a29d2  lea     rcx, [rbp+360h+arg_18]
0x1400a29d9  lea     rax, aPortglobal; "PortGlobal"
0x1400a29e0  mov     qword ptr [rbp+360h+var_3C8.Length], 160014h
0x1400a29e8  mov     [rbp+360h+var_3C8.Buffer], rax
0x1400a29ec  xorps   xmm0, xmm0
0x1400a29ef  lea     rax, aNicglobal; "NicGlobal"
0x1400a29f6  mov     qword ptr [rbp+360h+var_3B8.Length], 140012h
0x1400a29fe  mov     [rbp+360h+var_3B8.Buffer], rax
0x1400a2a02  xor     r12d, r12d
0x1400a2a05  lea     rax, aVrss; "VRSS"
0x1400a2a0c  mov     qword ptr [rbp+360h+var_3D8.Length], 0A0008h
0x1400a2a14  mov     [rbp+360h+var_3D8.Buffer], rax
0x1400a2a18  mov     edi, 0Ah
0x1400a2a1d  lea     rax, aStacktrace; "StackTrace"
0x1400a2a24  mov     qword ptr [rbp+360h+var_3A8.Length], 160014h
0x1400a2a2c  mov     [rbp+360h+var_3A8.Buffer], rax
0x1400a2a30  lea     rax, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1400a2a37  mov     [rsp+460h+var_3F0], rax
0x1400a2a3c  movups  xmmword ptr [rbp+360h+DeviceName.Length], xmm0
0x1400a2a40  mov     [rsp+460h+var_3F8], 740072h
0x1400a2a49  mov     [rbp+360h+arg_18], r12
0x1400a2a50  call    cs:__imp_KeQueryInterruptTimePrecise
0x1400a2a57  nop     dword ptr [rax+rax+00h]
0x1400a2a5c  lea     rdx, SourceString; "MmGetSystemRoutineAddressEx"
0x1400a2a63  mov     cs:VmsDriverObject, rsi
0x1400a2a6a  lea     rcx, [rbp+360h+DestinationString]; DestinationString
0x1400a2a71  mov     r15, rax
0x1400a2a74  call    cs:__imp_RtlInitUnicodeString
0x1400a2a7b  nop     dword ptr [rax+rax+00h]
0x1400a2a80  lea     rcx, [rbp+360h+DestinationString]; SystemRoutineName
0x1400a2a87  call    cs:__imp_MmGetSystemRoutineAddress
0x1400a2a8e  nop     dword ptr [rax+rax+00h]
0x1400a2a93  lea     rdx, [rsp+460h+var_3F8]
0x1400a2a98  mov     rcx, rsi
0x1400a2a9b  mov     cs:VmsGetSystemRoutineAddressEx, rax
0x1400a2aa2  call    VmsTrcLogInitialize
0x1400a2aa7  call    VmsRteInitialize
0x1400a2aac  call    wil_InitializeFeatureStaging
0x1400a2ab1  mov     ebx, 0FFFFh
0x1400a2ab6  mov     ecx, ebx; GroupNumber
0x1400a2ab8  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400a2abf  nop     dword ptr [rax+rax+00h]
0x1400a2ac4  mov     ecx, ebx; GroupNumber
0x1400a2ac6  mov     cs:VmsActiveProcCount, eax
0x1400a2acc  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400a2ad3  nop     dword ptr [rax+rax+00h]
0x1400a2ad8  mov     cs:VmsMaximumProcCount, eax
0x1400a2ade  lea     rcx, WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids
0x1400a2ae5  test    eax, eax
0x1400a2ae7  jnz     short loc_1400A2B1C
0x1400a2ae9  lea     rax, aVmsmaximumproc; "VmsMaximumProcCount > 0"
0x1400a2af0  mov     [rsp+460h+Size], rax
0x1400a2af5  lea     r9d, [rdi+0Dh]
0x1400a2af9  mov     qword ptr [rsp+460h+Flags], rcx
0x1400a2afe  lea     r8d, [rdi+9]
0x1400a2b02  mov     rcx, cs:VmsIfrLog
0x1400a2b09  call    WPP_RECORDER_SF_s
0x1400a2b0e  cmp     cs:VmsMaximumProcCount, r12d
0x1400a2b15  ja      short loc_1400A2B1C
0x1400a2b17  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsMaximumProcCount > 0")
0x1400a2b1c  call    VmsEtwStartTrace
0x1400a2b21  mov     rcx, rsi
0x1400a2b24  call    InitializeTelemetryAssertsKMByDriverObject
0x1400a2b29  mov     eax, cs:dword_1401F68A0
0x1400a2b2f  test    eax, eax
0x1400a2b31  jz      short loc_1400A2B46
0x1400a2b33  lea     r8, aStartedLoading; "Started Loading"
0x1400a2b3a  lea     rcx, aDriverentry; "DriverEntry"
0x1400a2b41  call    VmsTraceLogDriverOperationBegin
0x1400a2b46  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits, 2
0x1400a2b4d  jz      short loc_1400A2B54
0x1400a2b4f  call    McTemplateK0qssttss_EtwWriteTransfer
0x1400a2b54  call    VmsCdInitializeVswitchGeneration
0x1400a2b59  mov     cs:VmsDefaultNblForwardingDetail, r12
0x1400a2b60  mov     r13d, 1
0x1400a2b66  mov     word ptr cs:VmsDefaultNblForwardingDetail, r13w
0x1400a2b6e  mov     cs:VmsPDClientHandle, r12
0x1400a2b75  mov     cs:VmsPDPlatformDispatch, r12
0x1400a2b7c  mov     cs:VmsPDSwitchCount, r12d
0x1400a2b83  call    VmsCsInitialize
0x1400a2b88  mov     ebx, eax
0x1400a2b8a  test    eax, eax
0x1400a2b8c  jnz     loc_1400A3619
0x1400a2b92  call    VmsReadGlobalParameters
0x1400a2b97  lea     rdx, VmsIfrLog
0x1400a2b9e  lea     rcx, [rsp+460h+SourceString]; SourceString
0x1400a2ba3  call    VmsIfrLogCreate
0x1400a2ba8  mov     ebx, eax
0x1400a2baa  test    eax, eax
0x1400a2bac  jz      short loc_1400A2BB7
0x1400a2bae  lea     edi, [r13+13h]
0x1400a2bb2  jmp     loc_1400A3619
0x1400a2bb7  lea     rdx, VmsVrssIfrLog
0x1400a2bbe  lea     rcx, [rbp+360h+var_3D8]; SourceString
0x1400a2bc2  call    VmsIfrLogCreate
0x1400a2bc7  mov     ebx, eax
0x1400a2bc9  test    eax, eax
0x1400a2bcb  jz      short loc_1400A2BD7
0x1400a2bcd  mov     edi, 15h
0x1400a2bd2  jmp     loc_1400A3619
0x1400a2bd7  lea     rdx, VmsIfrPortLog
0x1400a2bde  lea     rcx, [rbp+360h+var_3C8]; SourceString
0x1400a2be2  call    VmsIfrLogCreate
0x1400a2be7  mov     ebx, eax
0x1400a2be9  test    eax, eax
0x1400a2beb  jz      short loc_1400A2BF7
0x1400a2bed  mov     edi, 16h
0x1400a2bf2  jmp     loc_1400A3619
0x1400a2bf7  lea     rdx, VmsIfrNicLog
0x1400a2bfe  lea     rcx, [rbp+360h+var_3B8]; SourceString
0x1400a2c02  call    VmsIfrLogCreate
0x1400a2c07  mov     ebx, eax
0x1400a2c09  test    eax, eax
0x1400a2c0b  jz      short loc_1400A2C17
0x1400a2c0d  mov     edi, 17h
0x1400a2c12  jmp     loc_1400A3619
0x1400a2c17  lea     rdx, VmsStackTraceIfrLog
0x1400a2c1e  lea     rcx, [rbp+360h+var_3A8]; SourceString
0x1400a2c22  call    VmsIfrLogCreate
0x1400a2c27  mov     ebx, eax
0x1400a2c29  test    eax, eax
0x1400a2c2b  jz      short loc_1400A2C37
0x1400a2c2d  mov     edi, 19h
0x1400a2c32  jmp     loc_1400A3619
0x1400a2c37  call    VmsPopulateCacheLineSize
0x1400a2c3c  call    ExecMonitorInit
0x1400a2c41  mov     ebx, eax
0x1400a2c43  test    eax, eax
0x1400a2c45  jz      short loc_1400A2C51
0x1400a2c47  mov     edi, 1Ah
0x1400a2c4c  jmp     loc_1400A3619
0x1400a2c51  mov     edx, 0FFFFh; Level
0x1400a2c56  lea     rcx, Mutex; Mutex
0x1400a2c5d  call    cs:__imp_KeInitializeMutex
0x1400a2c64  nop     dword ptr [rax+rax+00h]
0x1400a2c69  mov     cs:byte_1401F95F0, r13b
0x1400a2c70  call    VmsProxyRegister
0x1400a2c75  mov     ebx, eax
0x1400a2c77  test    eax, eax
0x1400a2c79  jz      short loc_1400A2C85
0x1400a2c7b  mov     edi, 1Bh
0x1400a2c80  jmp     loc_1400A3619
0x1400a2c85  call    VmsCdNicProxyRegister
0x1400a2c8a  mov     ebx, eax
0x1400a2c8c  test    eax, eax
0x1400a2c8e  jns     short loc_1400A2C9A
0x1400a2c90  mov     edi, 1Ch
0x1400a2c95  jmp     loc_1400A3619
0x1400a2c9a  call    VmsScQosInit
0x1400a2c9f  mov     ebx, eax
0x1400a2ca1  test    eax, eax
0x1400a2ca3  jz      short loc_1400A2CAF
0x1400a2ca5  mov     edi, 1Eh
0x1400a2caa  jmp     loc_1400A3619
0x1400a2caf  mov     rax, ds:0FFFFF78000000008h
0x1400a2cb9  mov     cs:Vms37HashSeed, eax
0x1400a2cbf  call    VmsScIPsecOffloadStateInit
0x1400a2cc4  mov     ebx, eax
0x1400a2cc6  test    eax, eax
0x1400a2cc8  jz      short loc_1400A2CD4
0x1400a2cca  mov     edi, 28h ; '('
0x1400a2ccf  jmp     loc_1400A3619
0x1400a2cd4  call    VmsQsInitialize
0x1400a2cd9  mov     ebx, eax
0x1400a2cdb  test    eax, eax
0x1400a2cdd  jz      short loc_1400A2CE9
0x1400a2cdf  mov     edi, 32h ; '2'
0x1400a2ce4  jmp     loc_1400A3619
0x1400a2ce9  call    VmsPtInitialize
0x1400a2cee  mov     ebx, eax
0x1400a2cf0  test    eax, eax
0x1400a2cf2  jz      short loc_1400A2CFE
0x1400a2cf4  mov     edi, 3Ch ; '<'
0x1400a2cf9  jmp     loc_1400A3619
0x1400a2cfe  cmp     cs:byte_1401F96A0, r12b
0x1400a2d05  jnz     short loc_1400A2D4F
0x1400a2d07  mov     [rsp+460h+Depth], r12w; Depth
0x1400a2d0d  lea     rcx, g_NvLibContext; Lookaside
0x1400a2d14  mov     [rsp+460h+Tag], 6C766E48h; Tag
0x1400a2d1c  mov     edi, 80h
0x1400a2d21  mov     [rsp+460h+Size], rdi; Size
0x1400a2d26  mov     r9d, 200h; PoolType
0x1400a2d2c  xor     r8d, r8d; Free
0x1400a2d2f  mov     [rsp+460h+Flags], r12d; Flags
0x1400a2d34  xor     edx, edx; Allocate
0x1400a2d36  call    cs:__imp_ExInitializeLookasideListEx
0x1400a2d3d  nop     dword ptr [rax+rax+00h]
0x1400a2d42  mov     ebx, eax
0x1400a2d44  test    eax, eax
0x1400a2d46  js      short loc_1400A2D64
0x1400a2d48  mov     cs:byte_1401F96A0, r13b
0x1400a2d4f  call    VmsVmInitialize
0x1400a2d54  mov     ebx, eax
0x1400a2d56  test    eax, eax
0x1400a2d58  jz      short loc_1400A2D6E
0x1400a2d5a  mov     edi, 5Ah ; 'Z'
0x1400a2d5f  jmp     loc_1400A3619
0x1400a2d64  mov     edi, 46h ; 'F'
0x1400a2d69  jmp     loc_1400A3619
0x1400a2d6e  mov     eax, cs:VmsVmMaxNBLsPerFlush
0x1400a2d74  lea     rcx, [rsp+460h+var_410]
0x1400a2d79  mov     [rsp+460h+var_404], eax
0x1400a2d7d  mov     eax, cs:VmsVmMaxBatchesPerFlush
0x1400a2d83  mov     [rsp+460h+var_40C], eax
0x1400a2d87  mov     eax, cs:VmsVmBatchCopyLookAsideBatchSize
0x1400a2d8d  mov     [rsp+460h+var_408], eax
0x1400a2d91  mov     eax, cs:VmsVmBatchCopyOnStackBatchSize
0x1400a2d97  mov     [rsp+460h+var_400], eax
0x1400a2d9b  mov     al, byte ptr cs:VmsDiagnosticFlags
0x1400a2da1  shr     al, 1
0x1400a2da3  and     al, r13b
0x1400a2da6  mov     [rsp+460h+var_40E], r12w
0x1400a2dac  mov     [rsp+460h+var_40F], al
0x1400a2db0  mov     [rsp+460h+var_410], r13b
0x1400a2db5  call    BLInitializeEx
0x1400a2dba  mov     ebx, eax
0x1400a2dbc  test    eax, eax
0x1400a2dbe  jnz     loc_1400A3614
0x1400a2dc4  mov     cs:byte_1401FA259, r13b
0x1400a2dcb  call    SegLibInitialize
0x1400a2dd0  mov     cs:byte_1401FA258, r13b
0x1400a2dd7  call    VmsOmLockInitialize
0x1400a2ddc  mov     ebx, eax
0x1400a2dde  test    eax, eax
0x1400a2de0  jz      short loc_1400A2DEC
0x1400a2de2  mov     edi, 69h ; 'i'
0x1400a2de7  jmp     loc_1400A3619
0x1400a2dec  call    VmsOmInitialize
0x1400a2df1  mov     ebx, eax
0x1400a2df3  test    eax, eax
0x1400a2df5  jz      short loc_1400A2E01
0x1400a2df7  mov     edi, 73h ; 's'
0x1400a2dfc  jmp     loc_1400A3619
0x1400a2e01  mov     rdx, cs:__imp_ExFreePool
0x1400a2e08  call    VmsIoctlInitialize
0x1400a2e0d  mov     rcx, cs:VmsMiniportHandle; NdisHandle
0x1400a2e14  lea     rax, qword_1401F9900
0x1400a2e1b  mov     cs:qword_1401F9908, rax
0x1400a2e22  mov     cs:qword_1401F9900, rax
0x1400a2e29  call    cs:__imp_NdisAllocateRWLock
0x1400a2e30  nop     dword ptr [rax+rax+00h]
0x1400a2e35  mov     cs:Lock, rax
0x1400a2e3c  test    rax, rax
0x1400a2e3f  jnz     short loc_1400A2E65
0x1400a2e41  mov     rcx, cs:VmsIfrLog
0x1400a2e48  lea     r9d, [rax+0Ch]
0x1400a2e4c  lea     rax, WPP_37e4495ad84b3e8f3e1366754a49d47d_Traceguids
0x1400a2e53  mov     dl, 2
0x1400a2e55  lea     r8d, [r9+8]
0x1400a2e59  mov     qword ptr [rsp+460h+Flags], rax
0x1400a2e5e  call    WPP_RECORDER_SF_
0x1400a2e63  jmp     short loc_1400A2E6C
0x1400a2e65  mov     cs:byte_1401F98F8, r13b
0x1400a2e6c  call    VmsMpNicCreateOrEnableAll
0x1400a2e71  call    VmsRegisterProtocol
0x1400a2e76  mov     ebx, eax
0x1400a2e78  test    eax, eax
0x1400a2e7a  jz      short loc_1400A2EB2
  ... truncated ...
```
