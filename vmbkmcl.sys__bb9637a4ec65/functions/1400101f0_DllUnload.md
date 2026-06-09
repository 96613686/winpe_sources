# DllUnload

- ea: `0x1400101f0`
- end: `0x1400102a3`
- name: `DllUnload`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400101f0`
- `0x1400103f4`
- `0x140011320`
- `0x14001d6fc`

## import_xrefs

- `ntoskrnl!PcwUnregister` at `0x140010200`
- `ntoskrnl!PcwUnregister` at `0x140010218`
- `ntoskrnl!PcwUnregister` at `0x140010230`
- `ntoskrnl!PcwUnregister` at `0x140010200`
- `ntoskrnl!PcwUnregister` at `0x140010218`
- `ntoskrnl!PcwUnregister` at `0x140010230`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001027a`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001027a`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140010257`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140010257`

## pseudocode

```c
__int64 DllUnload()
{
  if ( KmclPcChannel )
    PcwUnregister(KmclPcChannel);
  if ( KmclPcPipeChannel )
    PcwUnregister(KmclPcPipeChannel);
  if ( KmclPcChannelState )
    PcwUnregister(KmclPcChannelState);
  UninitializeTelemetryAssertsKM();
  McGenEventUnregister_EtwUnregister();
  WppCleanupKm();
  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 0;
  return 0;
}

```

## disassembly

```asm
0x1400101f0  sub     rsp, 28h
0x1400101f4  mov     rcx, cs:KmclPcChannel; Registration
0x1400101fb  test    rcx, rcx
0x1400101fe  jz      short loc_14001020C
0x140010200  call    cs:__imp_PcwUnregister
0x140010207  nop     dword ptr [rax+rax+00h]
0x14001020c  mov     rcx, cs:KmclPcPipeChannel; Registration
0x140010213  test    rcx, rcx
0x140010216  jz      short loc_140010224
0x140010218  call    cs:__imp_PcwUnregister
0x14001021f  nop     dword ptr [rax+rax+00h]
0x140010224  mov     rcx, cs:KmclPcChannelState; Registration
0x14001022b  test    rcx, rcx
0x14001022e  jz      short loc_14001023C
0x140010230  call    cs:__imp_PcwUnregister
0x140010237  nop     dword ptr [rax+rax+00h]
0x14001023c  call    UninitializeTelemetryAssertsKM
0x140010241  call    McGenEventUnregister_EtwUnregister
0x140010246  call    WppCleanupKm
0x14001024b  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140010252  test    rcx, rcx
0x140010255  jz      short loc_14001026E
0x140010257  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14001025e  nop     dword ptr [rax+rax+00h]
0x140010263  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x14001026e  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140010275  test    rcx, rcx
0x140010278  jz      short loc_140010291
0x14001027a  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140010281  nop     dword ptr [rax+rax+00h]
0x140010286  mov     cs:g_wil_details_featureUsageProvider, 0
0x140010291  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14001029b  xor     eax, eax
0x14001029d  add     rsp, 28h
0x1400102a1  retn
```
