# DriverEntry

- ea: `0x140040078`
- end: `0x140040989`
- name: `DriverEntry`
- size: `2321`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040010`

## callees

- `0x14000dc88`
- `0x14000de64`
- `0x14000e3dc`
- `0x14000e6c8`
- `0x14000f2e4`
- `0x140011560`
- `0x140011640`
- `0x1400119c0`
- `0x1400251f0`
- `0x140025310`
- `0x1400253b8`
- `0x140025480`
- `0x1400260f0`
- `0x140027cec`
- `0x14002ef08`
- `0x140040078`
- `0x140040990`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400407be`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400407be`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14004051f`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14004051f`
- `ntoskrnl!TmCurrentTransaction` at `0x1400405ae`
- `ntoskrnl!TmCurrentTransaction` at `0x1400405ae`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400408c3`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400408c3`
- `ntoskrnl!RtlGetVersion` at `0x14004042e`
- `ntoskrnl!RtlGetVersion` at `0x14004042e`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400408a4`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400408a4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400403b9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400403d1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400403e9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400403b9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400403d1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400403e9`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140040563`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140040563`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14004045b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140040471`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14004045b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140040471`
- `ntoskrnl!KeInitializeEvent` at `0x140040148`
- `ntoskrnl!KeInitializeEvent` at `0x1400404b7`
- `ntoskrnl!KeInitializeEvent` at `0x1400404f2`
- `ntoskrnl!KeInitializeEvent` at `0x140040148`
- `ntoskrnl!KeInitializeEvent` at `0x1400404b7`
- `ntoskrnl!KeInitializeEvent` at `0x1400404f2`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1400401f2`
- `WppRecorder!imp_WppRecorderConfigure` at `0x1400401f2`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1400402ca`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x1400402ca`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14004090d`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14004090d`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400402e1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400402e1`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x14004078c`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x14004078c`
- `FLTMGR!FltStartFiltering` at `0x140040872`
- `FLTMGR!FltStartFiltering` at `0x140040872`
- `FLTMGR!FltGetRoutineAddress` at `0x140040403`
- `FLTMGR!FltGetRoutineAddress` at `0x140040403`
- `FLTMGR!FltRegisterFilter` at `0x140040739`
- `FLTMGR!FltRegisterFilter` at `0x140040739`
- `FLTMGR!FltUnregisterFilter` at `0x1400408e9`
- `FLTMGR!FltUnregisterFilter` at `0x1400408e9`

## string_xrefs

- `0x1400400e2`: `ZwUpdateWnfStateData`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  const char *v4; // r8
  __int64 v5; // rax
  __int128 *v6; // rcx
  __int64 v7; // rdx
  __int128 *v8; // rax
  PDEVICE_OBJECT v9; // rcx
  int v10; // edx
  __int64 Default; // rax
  int v12; // edx
  PVOID RoutineAddress; // rax
  __int64 v14; // rsi
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  int v18; // edx
  int started; // ebx
  int v20; // r9d
  ULONG v21; // r8d
  __int64 v22; // r10
  __int64 v23; // rcx
  unsigned int v24; // edx
  ULONG v25; // eax
  int v26; // eax
  int v27; // r9d
  unsigned int i; // edi
  __int64 v29; // rcx
  __int64 (*v30)(void); // rax
  int v31; // eax
  int v32; // edx
  __int64 j; // rax
  __int64 v34; // rcx
  int v35; // edx
  __int64 v37; // [rsp+40h] [rbp-D8h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+48h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v39; // [rsp+58h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v40; // [rsp+68h] [rbp-B0h] BYREF
  _QWORD v41[2]; // [rsp+78h] [rbp-A0h] BYREF
  _QWORD v42[2]; // [rsp+88h] [rbp-90h] BYREF
  _QWORD v43[2]; // [rsp+98h] [rbp-80h] BYREF
  __int128 v44; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-60h]
  __int64 v46; // [rsp+C0h] [rbp-58h]
  __int128 v47; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-40h]

  v41[0] = 1441812;
  *(_QWORD *)&SystemRoutineName.Length = 3014700;
  SystemRoutineName.Buffer = L"MmMdlPageContentsState";
  *(_QWORD *)&v39.Length = 2490404;
  v39.Buffer = L"ExTryQueueWorkItem";
  *(_QWORD *)&v40.Length = 2752552;
  v40.Buffer = L"ZwUpdateWnfStateData";
  v42[0] = 1703960;
  v42[1] = L"NoAutoAttach";
  LODWORD(v37) = 0;
  v41[1] = L"AutoAttach";
  FastMutex.Count = 1;
  FastMutex.Owner = 0;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  byte_140018456 = 1;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WofTrace;
  FileTag = -2147483625;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  v43[0] = 0x100000010LL;
  v43[1] = 0x200000002LL;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, v43);
  v4 = "wof";
  v48 = 0;
  v5 = 2147483646;
  v47 = 0;
  v44 = 0x38u;
  v6 = &v47;
  LOBYTE(v47) = 0;
  v7 = 16;
  v45 = 0;
  v46 = 0x1000000000LL;
  do
  {
    if ( !v5 )
      break;
    if ( !*v4 )
      break;
    *(_BYTE *)v6 = *v4++;
    v6 = (__int128 *)((char *)v6 + 1);
    --v5;
    --v7;
  }
  while ( v7 );
  v8 = (__int128 *)((char *)v6 - 1);
  if ( v7 )
    v8 = v6;
  v9 = WPP_GLOBAL_Control;
  *(_BYTE *)v8 = 0;
  v48 = 0x200000002LL;
  *((_QWORD *)&v44 + 1) = 0x80000004000LL;
  if ( (int)imp_WppRecorderLogCreate(v9, &v44, &qword_1400190A0) >= 0 )
  {
    LODWORD(Default) = qword_1400190A0;
  }
  else
  {
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    qword_1400190A0 = Default;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_qZ(
      Default,
      v10,
      1,
      10,
      (__int64)WPP_804427da70a733063d46e28ea1c36e67_Traceguids,
      (char)DriverObject,
      (__int64)RegistryPath);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_qZ(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          11,
          (__int64)WPP_804427da70a733063d46e28ea1c36e67_Traceguids,
          (char)DriverObject,
          (__int64)RegistryPath);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          10,
          (__int64)WPP_88a3e6926d0435cc818663b0f0bf83d5_Traceguids);
      }
    }
  }
  TlgRegisterAggregateProvider();
  WofTelemetryRegistered = 1;
  MmMdlPageContentsStateWrapper = (__int64)MmGetSystemRoutineAddress(&SystemRoutineName);
  ExTryQueueWorkItemWrapper = (__int64)MmGetSystemRoutineAddress(&v39);
  ZwUpdateWnfStateDataWrapper = (__int64)MmGetSystemRoutineAddress(&v40);
  RoutineAddress = FltGetRoutineAddress("FltpTraceRedirectedFileIo");
  DeviceObject = (PDEVICE_OBJECT)DriverObject;
  FltTraceRedirectedFileIoWrapper = (__int64)RoutineAddress;
  VersionInformation.dwOSVersionInfoSize = 276;
  RtlGetVersion(&VersionInformation);
  dword_140018660 = 32;
  v14 = 0;
  v15 = 0;
  do
  {
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)&qword_1400186A8[v15]);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)&qword_1400186A8[v15 + 1]);
    *(PFLT_FILTER *)((char *)&WofGlobal + v15 * 8 + 928) = (PFLT_FILTER)&qword_1400186A8[v15];
    *(_DWORD *)((char *)&WofGlobal + v15 * 8 + 872) = 1;
    *(PFLT_FILTER *)((char *)&WofGlobal + v15 * 8 + 880) = 0;
    *(_DWORD *)((char *)&WofGlobal + v15 * 8 + 888) = 0;
    KeInitializeEvent((PRKEVENT)&qword_140018668[v15 + 3], SynchronizationEvent, 0);
    ++v14;
    v15 += 10;
  }
  while ( v14 != 32 );
  stru_140018628.Count = 1;
  stru_140018628.Owner = 0;
  stru_140018628.Contention = 0;
  KeInitializeEvent(&stru_140018628.Event, SynchronizationEvent, 0);
  RtlInitializeGenericTableAvl(
    &Table,
    WofProviderFsctlCompare,
    WofProviderFsctlAllocateRoutine,
    WofProviderFsctlFreeRoutine,
    0);
  WofQueryIntegerValueKey(RegistryPath, v41, 100, &dword_140018458);
  v16 = dword_140018458;
  if ( (unsigned int)dword_140018458 >= 3 )
  {
    v16 = 100;
    dword_140018458 = 100;
  }
  if ( v16 == 100 )
    dword_140018458 = (MmIsThisAnNtAsSystem() != 0) + 1;
  WofQueryIntegerValueKey(RegistryPath, v42, 0, &v37);
  if ( (_DWORD)v37 )
    dword_140018458 = 0;
  v37 = 0;
  if ( (unsigned int)TmCurrentTransaction(&v37) == -1073741637 )
    WofRegistration.TransactionNotificationCallback = 0;
  v17 = wil_InitializeFeatureStaging();
  started = v17;
  if ( v17 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_64:
      if ( g_wil_details_featureChangeNotification )
      {
        RtlUnregisterFeatureConfigurationChangeNotification();
        g_wil_details_featureChangeNotification = 0;
      }
      if ( g_wil_details_featureUsageProvider )
      {
        RtlUnregisterFeatureUsageProvider();
        g_wil_details_featureUsageProvider = 0;
      }
      g_wil_details_isFeatureStagingInitialized = 0;
      if ( WofGlobal )
        FltUnregisterFilter(WofGlobal);
      WofUnregisterTelemetry();
      if ( qword_1400190A0 )
      {
        imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
        qword_1400190A0 = 0;
      }
      WppCleanupKm();
      goto LABEL_73;
    }
    v20 = 12;
LABEL_30:
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      1,
      v20,
      (__int64)WPP_804427da70a733063d46e28ea1c36e67_Traceguids,
      v17);
    goto LABEL_64;
  }
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x6A0u);
  v17 = WimFSFInitializeProvider(qword_14001A2E8, (__int64)RegistryPath);
  started = v17;
  if ( v17 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    v20 = 13;
    goto LABEL_30;
  }
  v17 = FileProvInitializeProvider(qword_14001A490);
  started = v17;
  if ( v17 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    v20 = 14;
    goto LABEL_30;
  }
  v21 = 184;
  v22 = 0;
  v23 = 0;
  do
  {
    v24 = *(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 8);
    v25 = (*(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 4) + 7) & 0xFFFFFFF8;
    *(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 20) = v21;
    v21 += v25;
    v26 = dword_140018440;
    if ( v24 > dword_140018440 )
    {
      v26 = v24;
      dword_140018440 = v24;
    }
    v27 = dword_140018444;
    if ( *(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 12) > dword_140018444 )
    {
      v27 = *(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 12);
      dword_140018444 = v27;
    }
    if ( *(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 16) > dword_140018448 )
      dword_140018448 = *(ULONG *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v23 + 16);
    ++v22;
    v23 += 424;
  }
  while ( v22 != 4 );
  qword_140041080 = (unsigned int)(v26 + 64);
  qword_1400410F0 = (unsigned int)(v27 + 56);
  LODWORD(Size) = v21 + 184;
  qword_1400410B8 = v21 + 184;
  v17 = FltRegisterFilter(DriverObject, &WofRegistration, &WofGlobal);
  started = v17;
  if ( v17 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_64;
    v20 = 15;
    goto LABEL_30;
  }
  FltInitExtraCreateParameterLookasideList(WofGlobal, qword_140018340, 0, 0x10u, 0x72666F57u);
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0x30u, 0x54666F57u, 0);
  for ( i = 0; i < 4; ++i )
  {
    v29 = 424LL * i;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v29) )
    {
      v30 = *(__int64 (**)(void))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v29 + 32);
      if ( v30 )
      {
        v31 = v30();
        started = v31;
        if ( v31 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v32) = 2;
            WPP_RECORDER_SF_dd(
              WPP_GLOBAL_Control->DeviceExtension,
              v32,
              1,
              16,
              (__int64)WPP_804427da70a733063d46e28ea1c36e67_Traceguids,
              i,
              v31);
          }
          goto LABEL_64;
        }
      }
    }
  }
  for ( j = 0; j != 4; ++j )
  {
    v34 = 424 * j;
    if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * j) )
    {
      if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34 + 1) )
        byte_140018454 = 1;
      if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v34 + 2) )
        byte_140018455 = 1;
    }
  }
  started = FltStartFiltering(WofGlobal);
  if ( started < 0 )
    goto LABEL_64;
LABEL_73:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v35) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v35,
      1,
      17,
      (__int64)WPP_804427da70a733063d46e28ea1c36e67_Traceguids,
      started);
  }
  return started;
}

```

## disassembly

```asm
0x140040078  mov     r11, rsp
0x14004007b  mov     [r11+18h], rbx
0x14004007f  mov     [r11+20h], rsi
0x140040083  push    rdi
0x140040084  push    r12
0x140040086  push    r13
0x140040088  push    r14
0x14004008a  push    r15
0x14004008c  sub     rsp, 0F0h
0x140040093  mov     rax, cs:__security_cookie
0x14004009a  xor     rax, rsp
0x14004009d  mov     [rsp+118h+var_38], rax
0x1400400a5  xor     r15d, r15d
0x1400400a8  mov     [rsp+118h+var_A0], 160014h
0x1400400b1  lea     rax, aMmmdlpageconte; "MmMdlPageContentsState"
0x1400400b8  mov     qword ptr [rsp+118h+SystemRoutineName.Length], 2E002Ch
0x1400400c1  mov     [rsp+118h+SystemRoutineName.Buffer], rax
0x1400400c6  mov     rdi, rdx
0x1400400c9  lea     rax, aExtryqueuework; "ExTryQueueWorkItem"
0x1400400d0  mov     qword ptr [rsp+118h+var_C0.Length], 260024h
0x1400400d9  mov     [rsp+118h+var_C0.Buffer], rax
0x1400400de  lea     r12d, [r15+1]
0x1400400e2  lea     rax, aZwupdatewnfsta; "ZwUpdateWnfStateData"
0x1400400e9  mov     qword ptr [rsp+118h+var_B0.Length], 2A0028h
0x1400400f2  mov     [rsp+118h+var_B0.Buffer], rax
0x1400400f7  mov     r14, rcx
0x1400400fa  lea     rax, aNoautoattach; "NoAutoAttach"
0x140040101  mov     qword ptr [r11-90h], 1A0018h
0x14004010c  mov     [r11-88h], rax
0x140040113  lea     rcx, FastMutex.Event; Event
0x14004011a  lea     rax, aAutoattach; "AutoAttach"
0x140040121  mov     dword ptr [rsp+118h+var_D8], r15d
0x140040126  xor     r8d, r8d; State
0x140040129  mov     [r11-98h], rax
0x140040130  mov     edx, r12d; Type
0x140040133  mov     cs:FastMutex.Count, r12d
0x14004013a  mov     cs:FastMutex.Owner, r15
0x140040141  mov     cs:FastMutex.Contention, r15d
0x140040148  call    cs:__imp_KeInitializeEvent
0x14004014f  nop     dword ptr [rax+rax+00h]
0x140040154  lea     rax, WPP_ThisDir_CTLGUID_WofTrace
0x14004015b  mov     cs:byte_140018456, r12b
0x140040162  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140040169  mov     cs:FileTag, 80000017h
0x140040173  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x14004017a  mov     cs:WPP_MAIN_CB.NextDevice, r15
0x140040181  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x140040188  mov     cs:WPP_MAIN_CB.Timer, r12
0x14004018f  mov     cs:WPP_MAIN_CB.DeviceExtension, r15
0x140040196  mov     cs:WPP_MAIN_CB.DeviceType, r15d
0x14004019d  call    WppLoadTracingSupport
0x1400401a2  mov     rdx, rdi
0x1400401a5  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x1400401ac  mov     rcx, r14
0x1400401af  call    WppInitKm
0x1400401b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400401bb  lea     esi, [r15+10h]
0x1400401bf  xorps   xmm0, xmm0
0x1400401c2  lea     ebx, [rsi-0Eh]
0x1400401c5  movups  [rsp+118h+var_80], xmm0
0x1400401cd  lea     rdx, [rsp+118h+var_80]
0x1400401d5  mov     dword ptr [rsp+118h+var_80], esi
0x1400401dc  mov     byte ptr [rsp+118h+var_80+4], r12b
0x1400401e4  mov     dword ptr [rsp+118h+var_80+8], ebx
0x1400401eb  mov     dword ptr [rsp+118h+var_80+0Ch], ebx
0x1400401f2  call    cs:__imp_imp_WppRecorderConfigure
0x1400401f9  nop     dword ptr [rax+rax+00h]
0x1400401fe  xorps   xmm0, xmm0
0x140040201  lea     r8, aWof; "wof"
0x140040208  movups  [rsp+118h+var_60], xmm0
0x140040210  xor     eax, eax
0x140040212  mov     dword ptr [rsp+118h+var_60+0Ch], esi
0x140040219  movups  [rsp+118h+var_70], xmm0
0x140040221  mov     [rsp+118h+var_40], rax
0x140040229  mov     eax, 7FFFFFFEh
0x14004022e  movups  [rsp+118h+var_50], xmm0
0x140040236  mov     qword ptr [rsp+118h+var_70], 38h ; '8'
0x140040242  lea     rcx, [rsp+118h+var_50]
0x14004024a  mov     byte ptr [rsp+118h+var_50], r15b
0x140040252  mov     edx, esi
0x140040254  mov     qword ptr [rsp+118h+var_60], r15
0x14004025c  mov     byte ptr [rsp+118h+var_60+8], r15b
0x140040264  test    rax, rax
0x140040267  jz      short loc_140040282
0x140040269  mov     r9b, [r8]
0x14004026c  test    r9b, r9b
0x14004026f  jz      short loc_140040282
0x140040271  mov     [rcx], r9b
0x140040274  add     r8, r12
0x140040277  add     rcx, r12
0x14004027a  sub     rax, r12
0x14004027d  sub     rdx, r12
0x140040280  jnz     short loc_140040264
0x140040282  test    rdx, rdx
0x140040285  lea     rax, [rcx-1]
0x140040289  lea     r8, qword_1400190A0
0x140040290  cmovnz  rax, rcx
0x140040294  lea     rdx, [rsp+118h+var_70]
0x14004029c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400402a3  mov     [rax], r15b
0x1400402a6  mov     dword ptr [rsp+118h+var_40], ebx
0x1400402ad  mov     dword ptr [rsp+118h+var_40+4], ebx
0x1400402b4  mov     dword ptr [rsp+118h+var_70+8], 4000h
0x1400402bf  mov     dword ptr [rsp+118h+var_70+0Ch], 800h
0x1400402ca  call    cs:__imp_imp_WppRecorderLogCreate
0x1400402d1  nop     dword ptr [rax+rax+00h]
0x1400402d6  test    eax, eax
0x1400402d8  jns     short loc_1400402F6
0x1400402da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400402e1  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400402e8  nop     dword ptr [rax+rax+00h]
0x1400402ed  mov     cs:qword_1400190A0, rax
0x1400402f4  jmp     short loc_1400402FD
0x1400402f6  mov     rax, cs:qword_1400190A0
0x1400402fd  lea     r13, WPP_RECORDER_INITIALIZED
0x140040304  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004030b  lea     rbx, WPP_804427da70a733063d46e28ea1c36e67_Traceguids
0x140040312  jz      loc_1400403A8
0x140040318  mov     qword ptr [rsp+118h+Depth], rdi
0x14004031d  mov     esi, 0Ah
0x140040322  mov     r9d, esi
0x140040325  mov     qword ptr [rsp+118h+Tag], r14
0x14004032a  mov     r8d, r12d
0x14004032d  mov     [rsp+118h+TableContext], rbx
0x140040332  mov     dl, 4
0x140040334  mov     rcx, rax
0x140040337  call    WPP_RECORDER_SF_qZ
0x14004033c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140040343  jz      short loc_1400403A8
0x140040345  mov     rcx, cs:WPP_GLOBAL_Control
0x14004034c  cmp     [rcx+48h], r15w
0x140040351  jz      short loc_140040374
0x140040353  mov     rcx, [rcx+40h]
0x140040357  lea     r9d, [rsi+1]
0x14004035b  mov     qword ptr [rsp+118h+Depth], rdi
0x140040360  mov     r8d, r12d
0x140040363  mov     qword ptr [rsp+118h+Tag], r14
0x140040368  mov     dl, 5
0x14004036a  mov     [rsp+118h+TableContext], rbx
0x14004036f  call    WPP_RECORDER_SF_qZ
0x140040374  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004037b  jz      short loc_1400403A8
0x14004037d  mov     rcx, cs:WPP_GLOBAL_Control
0x140040384  cmp     [rcx+48h], r15w
0x140040389  jz      short loc_1400403A8
0x14004038b  mov     rcx, [rcx+40h]
0x14004038f  lea     rax, WPP_88a3e6926d0435cc818663b0f0bf83d5_Traceguids
0x140040396  mov     r9d, esi
0x140040399  mov     [rsp+118h+TableContext], rax
0x14004039e  mov     r8d, r12d
0x1400403a1  mov     dl, 5
0x1400403a3  call    WPP_RECORDER_SF_
0x1400403a8  call    TlgRegisterAggregateProvider
0x1400403ad  lea     rcx, [rsp+118h+SystemRoutineName]; SystemRoutineName
0x1400403b2  mov     cs:WofTelemetryRegistered, r12b
0x1400403b9  call    cs:__imp_MmGetSystemRoutineAddress
0x1400403c0  nop     dword ptr [rax+rax+00h]
0x1400403c5  lea     rcx, [rsp+118h+var_C0]; SystemRoutineName
0x1400403ca  mov     cs:MmMdlPageContentsStateWrapper, rax
0x1400403d1  call    cs:__imp_MmGetSystemRoutineAddress
0x1400403d8  nop     dword ptr [rax+rax+00h]
0x1400403dd  lea     rcx, [rsp+118h+var_B0]; SystemRoutineName
0x1400403e2  mov     cs:ExTryQueueWorkItemWrapper, rax
0x1400403e9  call    cs:__imp_MmGetSystemRoutineAddress
0x1400403f0  nop     dword ptr [rax+rax+00h]
0x1400403f5  lea     rcx, FltMgrRoutineName; "FltpTraceRedirectedFileIo"
0x1400403fc  mov     cs:ZwUpdateWnfStateDataWrapper, rax
0x140040403  call    cs:__imp_FltGetRoutineAddress
0x14004040a  nop     dword ptr [rax+rax+00h]
0x14004040f  lea     rcx, VersionInformation; lpVersionInformation
0x140040416  mov     cs:DeviceObject, r14
0x14004041d  mov     cs:FltTraceRedirectedFileIoWrapper, rax
0x140040424  mov     cs:VersionInformation.dwOSVersionInfoSize, 114h
0x14004042e  call    cs:__imp_RtlGetVersion
0x140040435  nop     dword ptr [rax+rax+00h]
0x14004043a  mov     cs:dword_140018660, 20h ; ' '
0x140040444  lea     r13, WofGlobal
0x14004044b  mov     rsi, r15
0x14004044e  mov     rbx, r15
0x140040451  lea     rcx, [r13+3A8h]
0x140040458  add     rcx, rbx; RunRef
0x14004045b  call    cs:__imp_ExInitializeRundownProtection
0x140040462  nop     dword ptr [rax+rax+00h]
0x140040467  lea     rcx, [r13+3B0h]
0x14004046e  add     rcx, rbx; RunRef
0x140040471  call    cs:__imp_ExInitializeRundownProtection
0x140040478  nop     dword ptr [rax+rax+00h]
0x14004047d  lea     rax, [r13+3A8h]
0x140040484  xor     r8d, r8d; State
0x140040487  add     rax, rbx
0x14004048a  lea     rcx, [r13+380h]
0x140040491  mov     [rbx+r13+3A0h], rax
0x140040499  add     rcx, rbx; Event
0x14004049c  mov     edx, r12d; Type
0x14004049f  mov     [rbx+r13+368h], r12d
0x1400404a7  mov     [rbx+r13+370h], r15
0x1400404af  mov     [rbx+r13+378h], r15d
0x1400404b7  call    cs:__imp_KeInitializeEvent
0x1400404be  nop     dword ptr [rax+rax+00h]
0x1400404c3  add     rsi, r12
0x1400404c6  add     rbx, 50h ; 'P'
0x1400404ca  cmp     rsi, 20h ; ' '
0x1400404ce  jnz     short loc_140040451
0x1400404d0  xor     r8d, r8d; State
0x1400404d3  mov     cs:stru_140018628.Count, r12d
0x1400404da  mov     edx, r12d; Type
0x1400404dd  mov     cs:stru_140018628.Owner, r15
0x1400404e4  lea     rcx, stru_140018628.Event; Event
0x1400404eb  mov     cs:stru_140018628.Contention, r15d
0x1400404f2  call    cs:__imp_KeInitializeEvent
0x1400404f9  nop     dword ptr [rax+rax+00h]
0x1400404fe  lea     r9, WofProviderFsctlFreeRoutine; FreeRoutine
0x140040505  mov     [rsp+118h+TableContext], r15; TableContext
0x14004050a  lea     r8, WofProviderFsctlAllocateRoutine; AllocateRoutine
0x140040511  lea     rdx, WofProviderFsctlCompare; CompareRoutine
0x140040518  lea     rcx, Table; Table
0x14004051f  call    cs:__imp_RtlInitializeGenericTableAvl
0x140040526  nop     dword ptr [rax+rax+00h]
0x14004052b  lea     ebx, [rsi+44h]
0x14004052e  mov     rcx, rdi
0x140040531  mov     r8d, ebx
0x140040534  lea     r9, dword_140018458
0x14004053b  lea     rdx, [rsp+118h+var_A0]
0x140040540  call    WofQueryIntegerValueKey
0x140040545  mov     eax, cs:dword_140018458
0x14004054b  lea     r13, WPP_RECORDER_INITIALIZED
0x140040552  cmp     eax, 3
0x140040555  jb      short loc_14004055F
0x140040557  mov     eax, ebx
0x140040559  mov     cs:dword_140018458, ebx
0x14004055f  cmp     eax, ebx
0x140040561  jnz     short loc_14004057E
0x140040563  call    cs:__imp_MmIsThisAnNtAsSystem
0x14004056a  nop     dword ptr [rax+rax+00h]
0x14004056f  neg     al
0x140040571  sbb     ecx, ecx
0x140040573  neg     ecx
0x140040575  add     ecx, r12d
0x140040578  mov     cs:dword_140018458, ecx
0x14004057e  lea     r9, [rsp+118h+var_D8]
0x140040583  xor     r8d, r8d
0x140040586  lea     rdx, [rsp+118h+var_90]
0x14004058e  mov     rcx, rdi
0x140040591  call    WofQueryIntegerValueKey
0x140040596  cmp     dword ptr [rsp+118h+var_D8], r15d
0x14004059b  jz      short loc_1400405A4
0x14004059d  mov     cs:dword_140018458, r15d
0x1400405a4  lea     rcx, [rsp+118h+var_D8]
0x1400405a9  mov     [rsp+118h+var_D8], r15
0x1400405ae  call    cs:__imp_TmCurrentTransaction
0x1400405b5  nop     dword ptr [rax+rax+00h]
0x1400405ba  cmp     eax, 0C00000BBh
0x1400405bf  jnz     short loc_1400405C8
0x1400405c1  mov     cs:WofRegistration.TransactionNotificationCallback, r15
0x1400405c8  call    wil_InitializeFeatureStaging
0x1400405cd  mov     ebx, eax
0x1400405cf  test    eax, eax
0x1400405d1  jns     short loc_140040610
0x1400405d3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400405da  lea     rdi, WPP_804427da70a733063d46e28ea1c36e67_Traceguids
0x1400405e1  jz      loc_140040898
0x1400405e7  mov     r9d, 0Ch
0x1400405ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400405f4  mov     r8d, r12d
0x1400405f7  mov     [rsp+118h+Tag], eax
0x1400405fb  mov     dl, 2
0x1400405fd  mov     [rsp+118h+TableContext], rdi
0x140040602  mov     rcx, [rcx+40h]
0x140040606  call    WPP_RECORDER_SF_d
0x14004060b  jmp     loc_140040898
0x140040610  lea     rsi, WPP_MAIN_CB.Queue+10h
0x140040617  xor     edx, edx; Val
0x140040619  mov     rcx, rsi; void *
0x14004061c  mov     r8d, 6A0h; Size
0x140040622  call    memset
0x140040627  mov     rdx, rdi
0x14004062a  lea     rcx, qword_14001A2E8
0x140040631  call    WimFSFInitializeProvider
0x140040636  mov     ebx, eax
0x140040638  test    eax, eax
0x14004063a  jns     short loc_140040658
0x14004063c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140040643  lea     rdi, WPP_804427da70a733063d46e28ea1c36e67_Traceguids
0x14004064a  jz      loc_140040898
0x140040650  mov     r9d, 0Dh
0x140040656  jmp     short loc_1400405ED
0x140040658  lea     rcx, qword_14001A490; void *
0x14004065f  call    FileProvInitializeProvider
0x140040664  mov     ebx, eax
0x140040666  test    eax, eax
0x140040668  jns     short loc_140040689
0x14004066a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140040671  lea     rdi, WPP_804427da70a733063d46e28ea1c36e67_Traceguids
0x140040678  jz      loc_140040898
0x14004067e  mov     r9d, 0Eh
0x140040684  jmp     loc_1400405ED
0x140040689  mov     r8d, 0B8h
0x14004068f  mov     r10, r15
0x140040692  mov     rcx, r15
0x140040695  mov     eax, [rcx+rsi+4]
  ... truncated ...
```
