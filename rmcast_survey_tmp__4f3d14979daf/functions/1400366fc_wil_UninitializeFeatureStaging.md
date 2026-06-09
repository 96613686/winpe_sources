# wil_UninitializeFeatureStaging

- ea: `0x1400366fc`
- end: `0x140036756`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000702c`
- `0x14003a078`

## callees

- `0x1400366fc`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14003670c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14003670c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14003672f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14003672f`

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
0x1400366fc  sub     rsp, 28h
0x140036700  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140036707  test    rcx, rcx
0x14003670a  jz      short loc_140036723
0x14003670c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140036713  nop     dword ptr [rax+rax+00h]
0x140036718  mov     cs:g_wil_details_featureChangeNotification, 0
0x140036723  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14003672a  test    rcx, rcx
0x14003672d  jz      short loc_140036746
0x14003672f  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140036736  nop     dword ptr [rax+rax+00h]
0x14003673b  mov     cs:g_wil_details_featureUsageProvider, 0
0x140036746  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140036750  add     rsp, 28h
0x140036754  retn
```
