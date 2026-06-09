# wil_UninitializeFeatureStaging

- ea: `0x14000b178`
- end: `0x14000b1d2`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140004880`
- `0x1400049a0`

## callees

- `0x14000b178`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000b1ab`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000b1ab`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000b188`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000b188`

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
0x14000b178  sub     rsp, 28h
0x14000b17c  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000b183  test    rcx, rcx
0x14000b186  jz      short loc_14000B19F
0x14000b188  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000b18f  nop     dword ptr [rax+rax+00h]
0x14000b194  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000b19f  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000b1a6  test    rcx, rcx
0x14000b1a9  jz      short loc_14000B1C2
0x14000b1ab  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000b1b2  nop     dword ptr [rax+rax+00h]
0x14000b1b7  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000b1c2  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000b1cc  add     rsp, 28h
0x14000b1d0  retn
```
