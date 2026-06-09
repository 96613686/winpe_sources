# wil_UninitializeFeatureStaging

- ea: `0x14003d2dc`
- end: `0x14003d336`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14005f078`

## callees

- `0x14003d2dc`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14003d30f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14003d30f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14003d2ec`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14003d2ec`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

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
0x14003d2dc  sub     rsp, 28h
0x14003d2e0  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14003d2e7  test    rcx, rcx
0x14003d2ea  jz      short loc_14003D303
0x14003d2ec  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14003d2f3  nop     dword ptr [rax+rax+00h]
0x14003d2f8  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x14003d303  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14003d30a  test    rcx, rcx
0x14003d30d  jz      short loc_14003D326
0x14003d30f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14003d316  nop     dword ptr [rax+rax+00h]
0x14003d31b  mov     cs:g_wil_details_featureUsageProvider, 0
0x14003d326  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14003d330  add     rsp, 28h
0x14003d334  retn
```
