# USBC_DriverUnload

- ea: `0x140022810`
- end: `0x140022919`
- name: `USBC_DriverUnload`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400224a0`
- `0x140022810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140022827`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022872`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022827`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022872`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400228c6`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400228c6`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400228e9`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400228e9`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400228a3`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400228a3`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x14002284a`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x14002284a`

## pseudocode

```c
__int64 __fastcall USBC_DriverUnload(__int64 a1)
{
  if ( GenericCompositeUSBDeviceString )
  {
    ExFreePoolWithTag(GenericCompositeUSBDeviceString, 0);
    GenericCompositeUSBDeviceString = 0;
  }
  if ( g_SleepstudyLibraryHandle )
  {
    SleepstudyHelper_Uninitialize();
    g_SleepstudyLibraryHandle = 0;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0x43627355u);
    P = 0;
  }
  wmiInit = 0;
  if ( g_RecorderLog )
  {
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
    g_RecorderLog = 0;
  }
  if ( WPP_MAIN_CB.Dpc.DeferredContext )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredContext = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) = 0;
  return WppCleanupKm(a1);
}

```

## disassembly

```asm
0x140022810  push    rbx
0x140022812  sub     rsp, 20h
0x140022816  mov     rbx, rcx
0x140022819  mov     rcx, cs:GenericCompositeUSBDeviceString; P
0x140022820  test    rcx, rcx
0x140022823  jz      short loc_14002283E
0x140022825  xor     edx, edx; Tag
0x140022827  call    cs:__imp_ExFreePoolWithTag
0x14002282e  nop     dword ptr [rax+rax+00h]
0x140022833  mov     cs:GenericCompositeUSBDeviceString, 0
0x14002283e  mov     rcx, cs:g_SleepstudyLibraryHandle
0x140022845  test    rcx, rcx
0x140022848  jz      short loc_140022861
0x14002284a  call    cs:__imp_SleepstudyHelper_Uninitialize
0x140022851  nop     dword ptr [rax+rax+00h]
0x140022856  mov     cs:g_SleepstudyLibraryHandle, 0
0x140022861  mov     rcx, cs:P; P
0x140022868  test    rcx, rcx
0x14002286b  jz      short loc_140022889
0x14002286d  mov     edx, 43627355h; Tag
0x140022872  call    cs:__imp_ExFreePoolWithTag
0x140022879  nop     dword ptr [rax+rax+00h]
0x14002287e  mov     cs:P, 0
0x140022889  mov     rdx, cs:g_RecorderLog
0x140022890  mov     cs:wmiInit, 0
0x140022897  test    rdx, rdx
0x14002289a  jz      short loc_1400228BA
0x14002289c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228a3  call    cs:__imp_imp_WppRecorderLogDelete
0x1400228aa  nop     dword ptr [rax+rax+00h]
0x1400228af  mov     cs:g_RecorderLog, 0
0x1400228ba  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext
0x1400228c1  test    rcx, rcx
0x1400228c4  jz      short loc_1400228DD
0x1400228c6  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400228cd  nop     dword ptr [rax+rax+00h]
0x1400228d2  mov     cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400228dd  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400228e4  test    rcx, rcx
0x1400228e7  jz      short loc_140022900
0x1400228e9  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400228f0  nop     dword ptr [rax+rax+00h]
0x1400228f5  mov     cs:g_wil_details_featureUsageProvider, 0
0x140022900  mov     rcx, rbx
0x140022903  mov     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, 0
0x14002290d  call    WppCleanupKm
0x140022912  add     rsp, 20h
0x140022916  pop     rbx
0x140022917  retn
```
