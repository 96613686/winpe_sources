# wil_UninitializeFeatureStaging

- ea: `0x14002eeb0`
- end: `0x14002ef0a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002ee80`
- `0x140035078`

## callees

- `0x14002eeb0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002eec0`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002eec0`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002eee3`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002eee3`

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
0x14002eeb0  sub     rsp, 28h
0x14002eeb4  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14002eebb  test    rcx, rcx
0x14002eebe  jz      short loc_14002EED7
0x14002eec0  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14002eec7  nop     dword ptr [rax+rax+00h]
0x14002eecc  mov     cs:g_wil_details_featureChangeNotification, 0
0x14002eed7  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14002eede  test    rcx, rcx
0x14002eee1  jz      short loc_14002EEFA
0x14002eee3  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14002eeea  nop     dword ptr [rax+rax+00h]
0x14002eeef  mov     cs:g_wil_details_featureUsageProvider, 0
0x14002eefa  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002ef04  add     rsp, 28h
0x14002ef08  retn
```
