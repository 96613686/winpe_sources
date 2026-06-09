# wil_UninitializeFeatureStaging

- ea: `0x140023008`
- end: `0x140023062`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140014184`
- `0x1400145a0`

## callees

- `0x140023008`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002303b`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002303b`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140023018`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140023018`

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
0x140023008  sub     rsp, 28h
0x14002300c  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140023013  test    rcx, rcx
0x140023016  jz      short loc_14002302F
0x140023018  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14002301f  nop     dword ptr [rax+rax+00h]
0x140023024  mov     cs:g_wil_details_featureChangeNotification, 0
0x14002302f  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140023036  test    rcx, rcx
0x140023039  jz      short loc_140023052
0x14002303b  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140023042  nop     dword ptr [rax+rax+00h]
0x140023047  mov     cs:g_wil_details_featureUsageProvider, 0
0x140023052  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14002305c  add     rsp, 28h
0x140023060  retn
```
