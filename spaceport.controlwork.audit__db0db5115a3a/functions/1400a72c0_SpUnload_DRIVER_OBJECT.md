# SpUnload(_DRIVER_OBJECT *)

- ea: `0x1400a72c0`
- end: `0x1400a7329`
- name: `?SpUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `105`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400bc078`

## callees

- `0x140035b64`
- `0x1400a72c0`
- `0x1400a7940`
- `0x1400b3e40`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400a7302`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400a7302`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400a72df`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400a72df`

## pseudocode

```c
void __fastcall SpUnload(struct _DRIVER_OBJECT *a1)
{
  McGenEventUnregister_EtwUnregister(a1);
  TlgUnregisterAggregateProvider();
  WppCleanupKm();
  if ( *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  WPP_MAIN_CB.DeviceLock.Header.LockNV = 0;
}

```

## disassembly

```asm
0x1400a72c0  sub     rsp, 28h
0x1400a72c4  call    McGenEventUnregister_EtwUnregister
0x1400a72c9  call    TlgUnregisterAggregateProvider
0x1400a72ce  call    WppCleanupKm
0x1400a72d3  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x1400a72da  test    rcx, rcx
0x1400a72dd  jz      short loc_1400A72F6
0x1400a72df  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400a72e6  nop     dword ptr [rax+rax+00h]
0x1400a72eb  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x1400a72f6  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400a72fd  test    rcx, rcx
0x1400a7300  jz      short loc_1400A7319
0x1400a7302  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400a7309  nop     dword ptr [rax+rax+00h]
0x1400a730e  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400a7319  mov     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header, 0
0x1400a7323  add     rsp, 28h
0x1400a7327  retn
```
