# wil_UninitializeFeatureStaging

- ea: `0x140017af0`
- end: `0x140017b4a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017550`
- `0x14001a078`

## callees

- `0x140017af0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140017b00`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140017b00`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140017b23`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140017b23`

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
0x140017af0  sub     rsp, 28h
0x140017af4  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140017afb  test    rcx, rcx
0x140017afe  jz      short loc_140017B17
0x140017b00  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140017b07  nop     dword ptr [rax+rax+00h]
0x140017b0c  mov     cs:g_wil_details_featureChangeNotification, 0
0x140017b17  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140017b1e  test    rcx, rcx
0x140017b21  jz      short loc_140017B3A
0x140017b23  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140017b2a  nop     dword ptr [rax+rax+00h]
0x140017b2f  mov     cs:g_wil_details_featureUsageProvider, 0
0x140017b3a  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140017b44  add     rsp, 28h
0x140017b48  retn
```
