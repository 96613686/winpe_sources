# VhdmpiDriverUnload(_DRIVER_OBJECT *)

- ea: `0x1400cab70`
- end: `0x1400cac7c`
- name: `?VhdmpiDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `268`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400ee42c`

## callees

- `0x1400341b8`
- `0x140048e90`
- `0x14005d840`
- `0x1400b9270`
- `0x1400b9a2c`
- `0x1400bcfa8`
- `0x1400c8378`
- `0x1400cab70`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400cabe9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400cabe9`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400cac24`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400cac24`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400cac47`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400cac47`
- `ntoskrnl!SeDeassignSecurity` at `0x1400cab8a`
- `ntoskrnl!SeDeassignSecurity` at `0x1400caba7`
- `ntoskrnl!SeDeassignSecurity` at `0x1400cab8a`
- `ntoskrnl!SeDeassignSecurity` at `0x1400caba7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400cac05`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400cac05`

## pseudocode

```c
void __fastcall VhdmpiDriverUnload(struct _DRIVER_OBJECT *a1)
{
  if ( VhdmpiIsoSecurityDescriptor )
    SeDeassignSecurity(&VhdmpiIsoSecurityDescriptor);
  if ( VhdmpiVhdSecurityDescriptor )
    SeDeassignSecurity(&VhdmpiVhdSecurityDescriptor);
  VhdmpiCleanupSurfaceRundown();
  VhdmpiTeardownPrefetchEngine();
  if ( StorportDriverUnload )
    StorportDriverUnload(a1);
  VhdmpiCleanupSrbExtensionWorkQueues();
  VhdmpiShutdownThreadPool();
  VhdmpiFreeGlobalData(1u);
  RtlFreeUnicodeString(&StringOut);
  if ( VhdmpTraceBuffersInitialized )
  {
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&WPP_MAIN_CB.Queue);
    VhdmpTraceBuffersInitialized = 0;
  }
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
  McGenEventUnregister_EtwUnregister();
}

```

## disassembly

```asm
0x1400cab70  push    rbx
0x1400cab72  sub     rsp, 20h
0x1400cab76  cmp     cs:?VhdmpiIsoSecurityDescriptor@@3PEAXEA, 0; void * VhdmpiIsoSecurityDescriptor
0x1400cab7e  mov     rbx, rcx
0x1400cab81  jz      short loc_1400CAB96
0x1400cab83  lea     rcx, ?VhdmpiIsoSecurityDescriptor@@3PEAXEA; SecurityDescriptor
0x1400cab8a  call    cs:__imp_SeDeassignSecurity
0x1400cab91  nop     dword ptr [rax+rax+00h]
0x1400cab96  cmp     cs:?VhdmpiVhdSecurityDescriptor@@3PEAXEA, 0; void * VhdmpiVhdSecurityDescriptor
0x1400cab9e  jz      short loc_1400CABB3
0x1400caba0  lea     rcx, ?VhdmpiVhdSecurityDescriptor@@3PEAXEA; SecurityDescriptor
0x1400caba7  call    cs:__imp_SeDeassignSecurity
0x1400cabae  nop     dword ptr [rax+rax+00h]
0x1400cabb3  call    VhdmpiCleanupSurfaceRundown
0x1400cabb8  call    ?VhdmpiTeardownPrefetchEngine@@YAXXZ; VhdmpiTeardownPrefetchEngine(void)
0x1400cabbd  mov     rax, cs:?StorportDriverUnload@@3P6AXPEAU_DRIVER_OBJECT@@@ZEA; void (*StorportDriverUnload)(_DRIVER_OBJECT *)
0x1400cabc4  test    rax, rax
0x1400cabc7  jz      short loc_1400CABD1
0x1400cabc9  mov     rcx, rbx
0x1400cabcc  call    _guard_dispatch_icall
0x1400cabd1  call    VhdmpiCleanupSrbExtensionWorkQueues
0x1400cabd6  call    VhdmpiShutdownThreadPool
0x1400cabdb  mov     cl, 1; unsigned __int8
0x1400cabdd  call    ?VhdmpiFreeGlobalData@@YAXE@Z; VhdmpiFreeGlobalData(uchar)
0x1400cabe2  lea     rcx, StringOut; UnicodeString
0x1400cabe9  call    cs:__imp_RtlFreeUnicodeString
0x1400cabf0  nop     dword ptr [rax+rax+00h]
0x1400cabf5  cmp     cs:?VhdmpTraceBuffersInitialized@@3EA, 0; uchar VhdmpTraceBuffersInitialized
0x1400cabfc  jz      short loc_1400CAC18
0x1400cabfe  lea     rcx, WPP_MAIN_CB.Queue; Lookaside
0x1400cac05  call    cs:__imp_ExDeleteLookasideListEx
0x1400cac0c  nop     dword ptr [rax+rax+00h]
0x1400cac11  mov     cs:?VhdmpTraceBuffersInitialized@@3EA, 0; uchar VhdmpTraceBuffersInitialized
0x1400cac18  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400cac1f  test    rcx, rcx
0x1400cac22  jz      short loc_1400CAC3B
0x1400cac24  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400cac2b  nop     dword ptr [rax+rax+00h]
0x1400cac30  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400cac3b  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400cac42  test    rcx, rcx
0x1400cac45  jz      short loc_1400CAC5E
0x1400cac47  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400cac4e  nop     dword ptr [rax+rax+00h]
0x1400cac53  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400cac5e  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400cac68  call    McGenEventUnregister_EtwUnregister
0x1400cac6d  mov     [rsp+28h+arg_8], 0
0x1400cac75  add     rsp, 20h
0x1400cac79  pop     rbx
0x1400cac7a  retn
```
