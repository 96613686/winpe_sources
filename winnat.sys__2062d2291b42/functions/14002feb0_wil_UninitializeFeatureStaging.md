# wil_UninitializeFeatureStaging

- ea: `0x14002feb0`
- end: `0x14002ff0a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002fe80`
- `0x140036078`

## callees

- `0x14002feb0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002fec0`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002fec0`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002fee3`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002fee3`

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
0x14002feb0  sub     rsp, 28h
0x14002feb4  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14002febb  test    rcx, rcx
0x14002febe  jz      short loc_14002FED7
0x14002fec0  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14002fec7  nop     dword ptr [rax+rax+00h]
0x14002fecc  mov     cs:g_wil_details_featureChangeNotification, 0
0x14002fed7  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14002fede  test    rcx, rcx
0x14002fee1  jz      short loc_14002FEFA
0x14002fee3  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14002feea  nop     dword ptr [rax+rax+00h]
0x14002feef  mov     cs:g_wil_details_featureUsageProvider, 0
0x14002fefa  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002ff04  add     rsp, 28h
0x14002ff08  retn
```
