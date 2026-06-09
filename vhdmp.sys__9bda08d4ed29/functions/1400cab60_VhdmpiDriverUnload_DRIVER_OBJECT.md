# VhdmpiDriverUnload(_DRIVER_OBJECT *)

- ea: `0x1400cab60`
- end: `0x1400cac6c`
- name: `?VhdmpiDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `268`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400ee42c`

## callees

- `0x140034678`
- `0x140049280`
- `0x14005dc30`
- `0x1400b9260`
- `0x1400b9a1c`
- `0x1400bcf98`
- `0x1400c8368`
- `0x1400cab60`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400cabd9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400cabd9`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400cac14`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400cac14`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400cac37`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400cac37`
- `ntoskrnl!SeDeassignSecurity` at `0x1400cab7a`
- `ntoskrnl!SeDeassignSecurity` at `0x1400cab97`
- `ntoskrnl!SeDeassignSecurity` at `0x1400cab7a`
- `ntoskrnl!SeDeassignSecurity` at `0x1400cab97`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400cabf5`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400cabf5`

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
0x1400cab60  push    rbx
0x1400cab62  sub     rsp, 20h
0x1400cab66  cmp     cs:?VhdmpiIsoSecurityDescriptor@@3PEAXEA, 0; void * VhdmpiIsoSecurityDescriptor
0x1400cab6e  mov     rbx, rcx
0x1400cab71  jz      short loc_1400CAB86
0x1400cab73  lea     rcx, ?VhdmpiIsoSecurityDescriptor@@3PEAXEA; SecurityDescriptor
0x1400cab7a  call    cs:__imp_SeDeassignSecurity
0x1400cab81  nop     dword ptr [rax+rax+00h]
0x1400cab86  cmp     cs:?VhdmpiVhdSecurityDescriptor@@3PEAXEA, 0; void * VhdmpiVhdSecurityDescriptor
0x1400cab8e  jz      short loc_1400CABA3
0x1400cab90  lea     rcx, ?VhdmpiVhdSecurityDescriptor@@3PEAXEA; SecurityDescriptor
0x1400cab97  call    cs:__imp_SeDeassignSecurity
0x1400cab9e  nop     dword ptr [rax+rax+00h]
0x1400caba3  call    VhdmpiCleanupSurfaceRundown
0x1400caba8  call    ?VhdmpiTeardownPrefetchEngine@@YAXXZ; VhdmpiTeardownPrefetchEngine(void)
0x1400cabad  mov     rax, cs:?StorportDriverUnload@@3P6AXPEAU_DRIVER_OBJECT@@@ZEA; void (*StorportDriverUnload)(_DRIVER_OBJECT *)
0x1400cabb4  test    rax, rax
0x1400cabb7  jz      short loc_1400CABC1
0x1400cabb9  mov     rcx, rbx
0x1400cabbc  call    _guard_dispatch_icall
0x1400cabc1  call    VhdmpiCleanupSrbExtensionWorkQueues
0x1400cabc6  call    VhdmpiShutdownThreadPool
0x1400cabcb  mov     cl, 1; unsigned __int8
0x1400cabcd  call    ?VhdmpiFreeGlobalData@@YAXE@Z; VhdmpiFreeGlobalData(uchar)
0x1400cabd2  lea     rcx, StringOut; UnicodeString
0x1400cabd9  call    cs:__imp_RtlFreeUnicodeString
0x1400cabe0  nop     dword ptr [rax+rax+00h]
0x1400cabe5  cmp     cs:?VhdmpTraceBuffersInitialized@@3EA, 0; uchar VhdmpTraceBuffersInitialized
0x1400cabec  jz      short loc_1400CAC08
0x1400cabee  lea     rcx, WPP_MAIN_CB.Queue; Lookaside
0x1400cabf5  call    cs:__imp_ExDeleteLookasideListEx
0x1400cabfc  nop     dword ptr [rax+rax+00h]
0x1400cac01  mov     cs:?VhdmpTraceBuffersInitialized@@3EA, 0; uchar VhdmpTraceBuffersInitialized
0x1400cac08  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400cac0f  test    rcx, rcx
0x1400cac12  jz      short loc_1400CAC2B
0x1400cac14  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400cac1b  nop     dword ptr [rax+rax+00h]
0x1400cac20  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400cac2b  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400cac32  test    rcx, rcx
0x1400cac35  jz      short loc_1400CAC4E
0x1400cac37  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400cac3e  nop     dword ptr [rax+rax+00h]
0x1400cac43  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400cac4e  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400cac58  call    McGenEventUnregister_EtwUnregister
0x1400cac5d  mov     [rsp+28h+arg_8], 0
0x1400cac65  add     rsp, 20h
0x1400cac69  pop     rbx
0x1400cac6a  retn
```
