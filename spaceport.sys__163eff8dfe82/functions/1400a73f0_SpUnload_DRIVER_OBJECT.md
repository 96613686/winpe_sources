# SpUnload(_DRIVER_OBJECT *)

- ea: `0x1400a73f0`
- end: `0x1400a7459`
- name: `?SpUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `105`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400bc078`

## callees

- `0x140035c24`
- `0x1400a73f0`
- `0x1400a7a70`
- `0x1400b3fe0`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400a7432`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400a7432`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400a740f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400a740f`

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
0x1400a73f0  sub     rsp, 28h
0x1400a73f4  call    McGenEventUnregister_EtwUnregister
0x1400a73f9  call    TlgUnregisterAggregateProvider
0x1400a73fe  call    WppCleanupKm
0x1400a7403  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x1400a740a  test    rcx, rcx
0x1400a740d  jz      short loc_1400A7426
0x1400a740f  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400a7416  nop     dword ptr [rax+rax+00h]
0x1400a741b  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x1400a7426  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400a742d  test    rcx, rcx
0x1400a7430  jz      short loc_1400A7449
0x1400a7432  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400a7439  nop     dword ptr [rax+rax+00h]
0x1400a743e  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400a7449  mov     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header, 0
0x1400a7453  add     rsp, 28h
0x1400a7457  retn
```
