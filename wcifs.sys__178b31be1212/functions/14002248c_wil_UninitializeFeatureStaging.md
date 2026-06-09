# wil_UninitializeFeatureStaging

- ea: `0x14002248c`
- end: `0x1400224e6`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140022270`
- `0x1400351b4`

## callees

- `0x14002248c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002249c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002249c`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400224bf`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400224bf`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 0;
  return result;
}

```

## disassembly

```asm
0x14002248c  sub     rsp, 28h
0x140022490  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x140022497  test    rcx, rcx
0x14002249a  jz      short loc_1400224B3
0x14002249c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400224a3  nop     dword ptr [rax+rax+00h]
0x1400224a8  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x1400224b3  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400224ba  test    rcx, rcx
0x1400224bd  jz      short loc_1400224D6
0x1400224bf  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400224c6  nop     dword ptr [rax+rax+00h]
0x1400224cb  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400224d6  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x1400224e0  add     rsp, 28h
0x1400224e4  retn
```
