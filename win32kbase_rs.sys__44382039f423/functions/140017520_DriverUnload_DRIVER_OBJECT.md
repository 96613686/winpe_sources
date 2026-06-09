# DriverUnload(_DRIVER_OBJECT *)

- ea: `0x140017520`
- end: `0x14001757a`
- name: `?DriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `90`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140017520`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140017553`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140017553`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140017530`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140017530`

## pseudocode

```c
void __fastcall DriverUnload(struct _DRIVER_OBJECT *a1)
{
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
}

```

## disassembly

```asm
0x140017520  sub     rsp, 28h
0x140017524  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14001752b  test    rcx, rcx
0x14001752e  jz      short loc_140017547
0x140017530  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140017537  nop     dword ptr [rax+rax+00h]
0x14001753c  mov     cs:g_wil_details_featureChangeNotification, 0
0x140017547  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14001754e  test    rcx, rcx
0x140017551  jz      short loc_14001756A
0x140017553  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14001755a  nop     dword ptr [rax+rax+00h]
0x14001755f  mov     cs:g_wil_details_featureUsageProvider, 0
0x14001756a  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140017574  add     rsp, 28h
0x140017578  retn
```
