# DriverCleanup

- ea: `0x140001660`
- end: `0x140001865`
- name: `DriverCleanup`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001660`
- `0x1400019c0`
- `0x140045570`
- `0x140077f40`
- `0x140092d54`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001774`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001774`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001712`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001712`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001756`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001791`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001756`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001791`
- `ntoskrnl!EtwUnregister` at `0x1400017b8`
- `ntoskrnl!EtwUnregister` at `0x1400017d8`
- `ntoskrnl!EtwUnregister` at `0x1400017f8`
- `ntoskrnl!EtwUnregister` at `0x1400017b8`
- `ntoskrnl!EtwUnregister` at `0x1400017d8`
- `ntoskrnl!EtwUnregister` at `0x1400017f8`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140001815`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140001815`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140001834`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140001834`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400016a9`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400016a9`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x1400016e6`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x1400016e6`

## pseudocode

```c
__int64 __fastcall DriverCleanup(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  KIRQL v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rax
  REGHANDLE v7; // rcx
  REGHANDLE v8; // rcx
  REGHANDLE v9; // rcx
  __int64 result; // rax

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B2C0);
  TlgUnregisterAggregateProvider();
  imp_WppRecorderLogDelete(WPP_GLOBAL_Control, *(_QWORD *)(v2 + 64));
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 944))(WdfDriverGlobals, a1);
  WppCleanupKm(v3);
  if ( *(_BYTE *)(v2 + 92) )
    SleepstudyHelper_Uninitialize(*(_QWORD *)(v2 + 96));
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
  {
    _InterlockedDecrement(&g_AssertsOperational);
    v4 = KeAcquireSpinLockRaiseToDpc(&g_AssertSpinLock);
    while ( 1 )
    {
      v5 = g_MicrosoftTelemetryAssertsTriggeredList;
      if ( (__int64 *)g_MicrosoftTelemetryAssertsTriggeredList == &g_MicrosoftTelemetryAssertsTriggeredList )
        break;
      if ( *(__int64 **)(g_MicrosoftTelemetryAssertsTriggeredList + 8) != &g_MicrosoftTelemetryAssertsTriggeredList
        || (v6 = *(_QWORD *)g_MicrosoftTelemetryAssertsTriggeredList,
            *(_QWORD *)(*(_QWORD *)g_MicrosoftTelemetryAssertsTriggeredList + 8LL) != g_MicrosoftTelemetryAssertsTriggeredList) )
      {
        __fastfail(3u);
      }
      g_MicrosoftTelemetryAssertsTriggeredList = *(_QWORD *)g_MicrosoftTelemetryAssertsTriggeredList;
      *(_QWORD *)(v6 + 8) = &g_MicrosoftTelemetryAssertsTriggeredList;
      ExFreePoolWithTag((PVOID)(v5 - 32), 0x74727341u);
    }
    KeReleaseSpinLock(&g_AssertSpinLock, v4);
    if ( g_ModuleName )
    {
      ExFreePoolWithTag(g_ModuleName, 0x74727341u);
      g_ModuleName = 0;
    }
    v7 = RegHandle;
    dword_140075078 = 0;
    RegHandle = 0;
    EtwUnregister(v7);
    v8 = qword_140075028;
    dword_140075008 = 0;
    qword_140075028 = 0;
    EtwUnregister(v8);
    v9 = qword_140075060;
    dword_140075040 = 0;
    qword_140075060 = 0;
    EtwUnregister(v9);
  }
  result = McGenEventUnregister_EtwUnregister();
  if ( *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  g_Usbhub3DriverObject = 0;
  return result;
}

```

## disassembly

```asm
0x140001660  mov     [rsp+arg_0], rbx
0x140001665  mov     [rsp+arg_8], rsi
0x14000166a  push    rdi
0x14000166b  sub     rsp, 20h
0x14000166f  mov     rax, cs:WdfFunctions_01015
0x140001676  mov     rbx, rcx
0x140001679  mov     r8, cs:off_14006B2C0
0x140001680  mov     rdx, rcx
0x140001683  mov     rcx, cs:WdfDriverGlobals
0x14000168a  mov     rax, [rax+650h]
0x140001691  call    _guard_dispatch_icall
0x140001696  mov     rdi, rax
0x140001699  call    TlgUnregisterAggregateProvider
0x14000169e  mov     rdx, [rdi+40h]
0x1400016a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016a9  call    cs:__imp_imp_WppRecorderLogDelete
0x1400016b0  nop     dword ptr [rax+rax+00h]
0x1400016b5  mov     rcx, cs:WdfFunctions_01015
0x1400016bc  mov     rdx, rbx
0x1400016bf  mov     rax, [rcx+3B0h]
0x1400016c6  mov     rcx, cs:WdfDriverGlobals
0x1400016cd  call    _guard_dispatch_icall
0x1400016d2  mov     rcx, rax
0x1400016d5  call    WppCleanupKm
0x1400016da  xor     esi, esi
0x1400016dc  cmp     [rdi+5Ch], sil
0x1400016e0  jz      short loc_1400016F2
0x1400016e2  mov     rcx, [rdi+60h]
0x1400016e6  call    cs:__imp_SleepstudyHelper_Uninitialize
0x1400016ed  nop     dword ptr [rax+rax+00h]
0x1400016f2  mov     eax, esi
0x1400016f4  lock xadd cs:g_AssertsOperational, eax
0x1400016fc  test    eax, eax
0x1400016fe  jz      loc_140001804
0x140001704  lock dec cs:g_AssertsOperational
0x14000170b  lea     rcx, g_AssertSpinLock; SpinLock
0x140001712  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001719  nop     dword ptr [rax+rax+00h]
0x14000171e  mov     bl, al
0x140001720  lea     rdi, g_MicrosoftTelemetryAssertsTriggeredList
0x140001727  mov     rcx, cs:g_MicrosoftTelemetryAssertsTriggeredList
0x14000172e  cmp     rcx, rdi
0x140001731  jz      short loc_14000176B
0x140001733  cmp     [rcx+8], rdi
0x140001737  jnz     short loc_140001764
0x140001739  mov     rax, [rcx]
0x14000173c  cmp     [rax+8], rcx
0x140001740  jnz     short loc_140001764
0x140001742  mov     cs:g_MicrosoftTelemetryAssertsTriggeredList, rax
0x140001749  add     rcx, 0FFFFFFFFFFFFFFE0h; P
0x14000174d  mov     edx, 74727341h; Tag
0x140001752  mov     [rax+8], rdi
0x140001756  call    cs:__imp_ExFreePoolWithTag
0x14000175d  nop     dword ptr [rax+rax+00h]
0x140001762  jmp     short loc_140001727
0x140001764  mov     ecx, 3
0x140001769  int     29h; Win8: RtlFailFast(ecx)
0x14000176b  mov     dl, bl; NewIrql
0x14000176d  lea     rcx, g_AssertSpinLock; SpinLock
0x140001774  call    cs:__imp_KeReleaseSpinLock
0x14000177b  nop     dword ptr [rax+rax+00h]
0x140001780  mov     rcx, cs:g_ModuleName; P
0x140001787  test    rcx, rcx
0x14000178a  jz      short loc_1400017A4
0x14000178c  mov     edx, 74727341h; Tag
0x140001791  call    cs:__imp_ExFreePoolWithTag
0x140001798  nop     dword ptr [rax+rax+00h]
0x14000179d  mov     cs:g_ModuleName, rsi
0x1400017a4  mov     rcx, cs:RegHandle; RegHandle
0x1400017ab  mov     cs:dword_140075078, esi
0x1400017b1  mov     cs:RegHandle, rsi
0x1400017b8  call    cs:__imp_EtwUnregister
0x1400017bf  nop     dword ptr [rax+rax+00h]
0x1400017c4  mov     rcx, cs:qword_140075028; RegHandle
0x1400017cb  mov     cs:dword_140075008, esi
0x1400017d1  mov     cs:qword_140075028, rsi
0x1400017d8  call    cs:__imp_EtwUnregister
0x1400017df  nop     dword ptr [rax+rax+00h]
0x1400017e4  mov     rcx, cs:qword_140075060; RegHandle
0x1400017eb  mov     cs:dword_140075040, esi
0x1400017f1  mov     cs:qword_140075060, rsi
0x1400017f8  call    cs:__imp_EtwUnregister
0x1400017ff  nop     dword ptr [rax+rax+00h]
0x140001804  call    McGenEventUnregister_EtwUnregister
0x140001809  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x140001810  test    rcx, rcx
0x140001813  jz      short loc_140001828
0x140001815  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000181c  nop     dword ptr [rax+rax+00h]
0x140001821  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rsi
0x140001828  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000182f  test    rcx, rcx
0x140001832  jz      short loc_140001847
0x140001834  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000183b  nop     dword ptr [rax+rax+00h]
0x140001840  mov     cs:g_wil_details_featureUsageProvider, rsi
0x140001847  mov     cs:g_wil_details_isFeatureStagingInitialized, esi
0x14000184d  mov     cs:g_Usbhub3DriverObject, rsi
0x140001854  mov     rbx, [rsp+28h+arg_0]
0x140001859  mov     rsi, [rsp+28h+arg_8]
0x14000185e  add     rsp, 20h
0x140001862  pop     rdi
0x140001863  retn
```
