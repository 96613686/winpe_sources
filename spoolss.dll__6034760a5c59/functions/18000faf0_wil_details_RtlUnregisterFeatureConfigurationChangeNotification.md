# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000faf0`
- end: `0x18000fb2b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004898`

## callees

- `0x18000c070`
- `0x18000faf0`
- `0x180016010`

## string_xrefs

- `0x18000fb05`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 (*__fastcall wil_details_RtlUnregisterFeatureConfigurationChangeNotification(__int64 a1))(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64))result)(a1);
  result = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)result;
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x18000faf0  push    rbx
0x18000faf2  sub     rsp, 20h
0x18000faf6  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000fafd  mov     rbx, rcx
0x18000fb00  test    rax, rax
0x18000fb03  jnz     short loc_18000FB1D
0x18000fb05  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000fb0c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000fb11  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000fb18  test    rax, rax
0x18000fb1b  jz      short loc_18000FB25
0x18000fb1d  mov     rcx, rbx
0x18000fb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb25  add     rsp, 20h
0x18000fb29  pop     rbx
0x18000fb2a  retn
```
