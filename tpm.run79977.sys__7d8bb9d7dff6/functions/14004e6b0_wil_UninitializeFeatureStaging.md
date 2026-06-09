# wil_UninitializeFeatureStaging

- ea: `0x14004e6b0`
- end: `0x14004e70a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001ddc0`
- `0x14005003c`

## callees

- `0x14004e6b0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14004e6e3`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14004e6e3`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14004e6c0`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14004e6c0`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

  if ( g_wil_details_featureChangeNotification )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x14004e6b0  sub     rsp, 28h
0x14004e6b4  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14004e6bb  test    rcx, rcx
0x14004e6be  jz      short loc_14004E6D7
0x14004e6c0  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14004e6c7  nop     dword ptr [rax+rax+00h]
0x14004e6cc  mov     cs:g_wil_details_featureChangeNotification, 0
0x14004e6d7  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14004e6de  test    rcx, rcx
0x14004e6e1  jz      short loc_14004E6FA
0x14004e6e3  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14004e6ea  nop     dword ptr [rax+rax+00h]
0x14004e6ef  mov     cs:g_wil_details_featureUsageProvider, 0
0x14004e6fa  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14004e704  add     rsp, 28h
0x14004e708  retn
```
