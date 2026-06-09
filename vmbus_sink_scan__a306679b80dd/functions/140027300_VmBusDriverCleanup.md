# VmBusDriverCleanup

- ea: `0x140027300`
- end: `0x140027373`
- name: `VmBusDriverCleanup`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140027380`
- `0x14003003c`

## callees

- `0x140003864`
- `0x14000d168`
- `0x140027300`
- `0x1400273f0`
- `0x1400283bc`
- `0x14002d388`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002734c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002734c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140027329`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140027329`

## pseudocode

```c
__int64 VmBusDriverCleanup()
{
  __int64 result; // rax

  InstanceCleanupNuma();
  CrashUninitialize();
  UninitializeTelemetryAssertsKM();
  McGenEventUnregister_EtwUnregister();
  result = WppCleanupKm();
  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 0;
  return result;
}

```

## disassembly

```asm
0x140027300  sub     rsp, 28h
0x140027304  call    InstanceCleanupNuma
0x140027309  call    CrashUninitialize
0x14002730e  call    UninitializeTelemetryAssertsKM
0x140027313  call    McGenEventUnregister_EtwUnregister
0x140027318  call    WppCleanupKm
0x14002731d  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140027324  test    rcx, rcx
0x140027327  jz      short loc_140027340
0x140027329  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140027330  nop     dword ptr [rax+rax+00h]
0x140027335  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x140027340  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140027347  test    rcx, rcx
0x14002734a  jz      short loc_140027363
0x14002734c  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140027353  nop     dword ptr [rax+rax+00h]
0x140027358  mov     cs:g_wil_details_featureUsageProvider, 0
0x140027363  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14002736d  add     rsp, 28h
0x140027371  retn
```
