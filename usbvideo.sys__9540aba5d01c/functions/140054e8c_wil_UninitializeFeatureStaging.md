# wil_UninitializeFeatureStaging

- ea: `0x140054e8c`
- end: `0x140054ee6`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140054b30`
- `0x14005e078`

## callees

- `0x140054e8c`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140054ebf`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140054ebf`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140054e9c`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140054e9c`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

  if ( WPP_MAIN_CB.Dpc.SystemArgument2 )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.SystemArgument2 = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink) = 0;
  return result;
}

```

## disassembly

```asm
0x140054e8c  sub     rsp, 28h
0x140054e90  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument2
0x140054e97  test    rcx, rcx
0x140054e9a  jz      short loc_140054EB3
0x140054e9c  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140054ea3  nop     dword ptr [rax+rax+00h]
0x140054ea8  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument2, 0
0x140054eb3  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140054eba  test    rcx, rcx
0x140054ebd  jz      short loc_140054ED6
0x140054ebf  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140054ec6  nop     dword ptr [rax+rax+00h]
0x140054ecb  mov     cs:g_wil_details_featureUsageProvider, 0
0x140054ed6  mov     dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink, 0
0x140054ee0  add     rsp, 28h
0x140054ee4  retn
```
