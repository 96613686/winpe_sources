# UmpoNotifyInit

- ea: `0x180010e38`
- end: `0x1800110c6`
- name: `UmpoNotifyInit`
- size: `654`
- prototype: `DWORD __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed10`

## callees

- `0x18000f3dc`
- `0x180010e38`
- `0x180011384`
- `0x1800165a8`

## import_xrefs

- `ntdll!RtlAllocateWnfSerializationGroup` at `0x180010ecb`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x180010ecb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010efb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010f39`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010f77`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010fb5`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010ff3`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010efb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010f39`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010f77`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010fb5`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180010ff3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180011068`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001109b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180011068`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001109b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180011089`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180011089`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010e75`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010e89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010e9d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010e75`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010e89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180010e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001107f`

## pseudocode

```c
DWORD __fastcall UmpoNotifyInit(int a1)
{
  int WnfSerializationGroup; // eax
  struct _TP_WORK *ThreadpoolWork; // rax

  if ( a1 )
  {
    if ( a1 == 1 )
    {
      UmpoRestoreEsOverrideState();
      if ( UmpoScmWnfSubscription )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      WnfSerializationGroup = RtlAllocateWnfSerializationGroup();
      RtlSubscribeWnfStateChangeNotification(
        &UmpoScmWnfSubscription,
        WNF_SCM_AUTOSTART_STATE,
        0,
        UmpoWnfScmPhaseCallback,
        0,
        0,
        WnfSerializationGroup,
        0);
      if ( UmpoProvEngineWnfSubscription )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      RtlSubscribeWnfStateChangeNotification(
        &UmpoProvEngineWnfSubscription,
        WNF_PROV_TURN_COMPLETE,
        0,
        UmpoWnfProvEngineTurnCallback,
        0,
        0,
        0,
        0);
      if ( UmpoBatterySaverWnfSubscription )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      RtlSubscribeWnfStateChangeNotification(
        &UmpoBatterySaverWnfSubscription,
        WNF_SEB_ENERGY_SAVER_STATE_V2,
        0,
        UmpoWnfEnergySaverCallback,
        0,
        0,
        0,
        0);
      if ( UmpoBatteryInfoWnfSubscription )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      RtlSubscribeWnfStateChangeNotification(
        &UmpoBatteryInfoWnfSubscription,
        WNF_PO_COMPOSITE_BATTERY,
        0,
        UmpoWnfBatteryInfoCallback,
        0,
        0,
        0,
        0);
      if ( UmpoEnergySaverOverrideWnfSubscription )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      RtlSubscribeWnfStateChangeNotification(
        &UmpoEnergySaverOverrideWnfSubscription,
        WNF_PO_ENERGY_SAVER_OVERRIDE,
        0,
        UmpoWnfEnergySaverOverrideCallback,
        0,
        0,
        0,
        0);
      UmpoInitializeEffectivePowerModeCallbacks();
      if ( UmpoPnpInitWork )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      UmpoPnpInitWorkEnv.Version = 3;
      UmpoPnpInitWorkEnv.CleanupGroupCancelCallback = 0;
      UmpoPnpInitWorkEnv.FinalizationCallback = 0;
      UmpoPnpInitWorkEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      UmpoPnpInitWorkEnv.Size = 72;
      *(_OWORD *)&UmpoPnpInitWorkEnv.Pool = 0;
      UmpoPnpInitWorkEnv.u.Flags = 1;
      *(_OWORD *)&UmpoPnpInitWorkEnv.RaceDll = 0;
      ThreadpoolWork = CreateThreadpoolWork(UmpoPnpInitWorkCallback, 0, &UmpoPnpInitWorkEnv);
      UmpoPnpInitWork = ThreadpoolWork;
      if ( !ThreadpoolWork )
        return GetLastError();
      SubmitThreadpoolWork(ThreadpoolWork);
      UmpoPowerStatusChangeWorker = CreateThreadpoolWork(UmpoPowerStatusChangeWorkerCallback, 0, 0);
      UmpoPowerStateNotificationNeeded = 0;
      UmpoPowerStateNotifyInProgress = 0;
      if ( !UmpoPowerStatusChangeWorker )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  else
  {
    qword_180024F68 = (__int64)&UmpoLegacyEventRegistrantList;
    UmpoLegacyEventRegistrantList = &UmpoLegacyEventRegistrantList;
    qword_180024EA8 = (__int64)&UmpoPdcPpmProfileClientList;
    UmpoPdcPpmProfileClientList = &UmpoPdcPpmProfileClientList;
    InitializeCriticalSection(&UmpoSchemeLock);
    byte_180024FA8 = 1;
    InitializeCriticalSection(&UmpoNotification);
    byte_180024F48 = 1;
    InitializeCriticalSection(&UmpoPowerStateNotificationLock);
    byte_180024E88 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180010e38  push    rbx
0x180010e3a  sub     rsp, 40h
0x180010e3e  xor     ebx, ebx
0x180010e40  test    ecx, ecx
0x180010e42  jnz     short loc_180010EAF
0x180010e44  lea     rax, UmpoLegacyEventRegistrantList
0x180010e4b  mov     cs:qword_180024F68, rax
0x180010e52  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180010e59  mov     cs:UmpoLegacyEventRegistrantList, rax
0x180010e60  lea     rax, UmpoPdcPpmProfileClientList
0x180010e67  mov     cs:qword_180024EA8, rax
0x180010e6e  mov     cs:UmpoPdcPpmProfileClientList, rax
0x180010e75  call    cs:__imp_InitializeCriticalSection
0x180010e7b  lea     rcx, UmpoNotification; lpCriticalSection
0x180010e82  mov     cs:byte_180024FA8, 1
0x180010e89  call    cs:__imp_InitializeCriticalSection
0x180010e8f  lea     rcx, UmpoPowerStateNotificationLock; lpCriticalSection
0x180010e96  mov     cs:byte_180024F48, 1
0x180010e9d  call    cs:__imp_InitializeCriticalSection
0x180010ea3  mov     cs:byte_180024E88, 1
0x180010eaa  jmp     loc_1800110BE
0x180010eaf  cmp     ecx, 1
0x180010eb2  jnz     loc_1800110BE
0x180010eb8  call    UmpoRestoreEsOverrideState
0x180010ebd  cmp     cs:UmpoScmWnfSubscription, rbx
0x180010ec4  jz      short loc_180010ECB
0x180010ec6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010ecb  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x180010ed1  mov     rdx, cs:WNF_SCM_AUTOSTART_STATE
0x180010ed8  lea     r9, UmpoWnfScmPhaseCallback
0x180010edf  mov     [rsp+48h+var_10], ebx
0x180010ee3  lea     rcx, UmpoScmWnfSubscription
0x180010eea  mov     [rsp+48h+var_18], eax
0x180010eee  xor     r8d, r8d
0x180010ef1  mov     [rsp+48h+var_20], rbx
0x180010ef6  mov     [rsp+48h+var_28], rbx
0x180010efb  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010f01  cmp     cs:UmpoProvEngineWnfSubscription, rbx
0x180010f08  jz      short loc_180010F0F
0x180010f0a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010f0f  mov     rdx, cs:WNF_PROV_TURN_COMPLETE
0x180010f16  lea     r9, UmpoWnfProvEngineTurnCallback
0x180010f1d  mov     [rsp+48h+var_10], ebx
0x180010f21  lea     rcx, UmpoProvEngineWnfSubscription
0x180010f28  mov     [rsp+48h+var_18], ebx
0x180010f2c  xor     r8d, r8d
0x180010f2f  mov     [rsp+48h+var_20], rbx
0x180010f34  mov     [rsp+48h+var_28], rbx
0x180010f39  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010f3f  cmp     cs:UmpoBatterySaverWnfSubscription, rbx
0x180010f46  jz      short loc_180010F4D
0x180010f48  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010f4d  mov     rdx, cs:WNF_SEB_ENERGY_SAVER_STATE_V2
0x180010f54  lea     r9, UmpoWnfEnergySaverCallback
0x180010f5b  mov     [rsp+48h+var_10], ebx
0x180010f5f  lea     rcx, UmpoBatterySaverWnfSubscription
0x180010f66  mov     [rsp+48h+var_18], ebx
0x180010f6a  xor     r8d, r8d
0x180010f6d  mov     [rsp+48h+var_20], rbx
0x180010f72  mov     [rsp+48h+var_28], rbx
0x180010f77  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010f7d  cmp     cs:UmpoBatteryInfoWnfSubscription, rbx
0x180010f84  jz      short loc_180010F8B
0x180010f86  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010f8b  mov     rdx, cs:WNF_PO_COMPOSITE_BATTERY
0x180010f92  lea     r9, UmpoWnfBatteryInfoCallback
0x180010f99  mov     [rsp+48h+var_10], ebx
0x180010f9d  lea     rcx, UmpoBatteryInfoWnfSubscription
0x180010fa4  mov     [rsp+48h+var_18], ebx
0x180010fa8  xor     r8d, r8d
0x180010fab  mov     [rsp+48h+var_20], rbx
0x180010fb0  mov     [rsp+48h+var_28], rbx
0x180010fb5  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010fbb  cmp     cs:UmpoEnergySaverOverrideWnfSubscription, rbx
0x180010fc2  jz      short loc_180010FC9
0x180010fc4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010fc9  mov     rdx, cs:WNF_PO_ENERGY_SAVER_OVERRIDE
0x180010fd0  lea     r9, UmpoWnfEnergySaverOverrideCallback
0x180010fd7  mov     [rsp+48h+var_10], ebx
0x180010fdb  lea     rcx, UmpoEnergySaverOverrideWnfSubscription
0x180010fe2  mov     [rsp+48h+var_18], ebx
0x180010fe6  xor     r8d, r8d
0x180010fe9  mov     [rsp+48h+var_20], rbx
0x180010fee  mov     [rsp+48h+var_28], rbx
0x180010ff3  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180010ff9  call    UmpoInitializeEffectivePowerModeCallbacks
0x180010ffe  cmp     cs:UmpoPnpInitWork, rbx
0x180011005  jz      short loc_18001100C
0x180011007  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001100c  xorps   xmm0, xmm0
0x18001100f  mov     cs:UmpoPnpInitWorkEnv.Version, 3
0x180011019  xorps   xmm1, xmm1
0x18001101c  mov     cs:UmpoPnpInitWorkEnv.CleanupGroupCancelCallback, rbx
0x180011023  lea     r8, UmpoPnpInitWorkEnv; pcbe
0x18001102a  mov     cs:UmpoPnpInitWorkEnv.FinalizationCallback, rbx
0x180011031  xor     edx, edx; pv
0x180011033  mov     cs:UmpoPnpInitWorkEnv.CallbackPriority, 1
0x18001103d  lea     rcx, UmpoPnpInitWorkCallback; pfnwk
0x180011044  mov     cs:UmpoPnpInitWorkEnv.Size, 48h ; 'H'
0x18001104e  movdqu  xmmword ptr cs:UmpoPnpInitWorkEnv.Pool, xmm0
0x180011056  mov     dword ptr cs:UmpoPnpInitWorkEnv.u, 1
0x180011060  movdqu  xmmword ptr cs:UmpoPnpInitWorkEnv.RaceDll, xmm1
0x180011068  call    cs:__imp_CreateThreadpoolWork
0x18001106e  mov     cs:UmpoPnpInitWork, rax
0x180011075  test    rax, rax
0x180011078  jnz     short loc_180011086
0x18001107a  add     rsp, 40h
0x18001107e  pop     rbx
0x18001107f  jmp     cs:__imp_GetLastError
0x180011086  mov     rcx, rax; pwk
0x180011089  call    cs:__imp_SubmitThreadpoolWork
0x18001108f  xor     r8d, r8d; pcbe
0x180011092  lea     rcx, UmpoPowerStatusChangeWorkerCallback; pfnwk
0x180011099  xor     edx, edx; pv
0x18001109b  call    cs:__imp_CreateThreadpoolWork
0x1800110a1  mov     cs:UmpoPowerStatusChangeWorker, rax
0x1800110a8  mov     cs:UmpoPowerStateNotificationNeeded, bl
0x1800110ae  mov     cs:UmpoPowerStateNotifyInProgress, bl
0x1800110b4  test    rax, rax
0x1800110b7  jnz     short loc_1800110BE
0x1800110b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800110be  mov     eax, ebx
0x1800110c0  add     rsp, 40h
0x1800110c4  pop     rbx
0x1800110c5  retn
```
