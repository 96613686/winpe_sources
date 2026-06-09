# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18002fb00`
- end: `0x18002fb3b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800289f4`

## callees

- `0x18002f4a0`
- `0x18002fb00`
- `0x180042010`

## string_xrefs

- `0x18002fb15`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18002fb00  push    rbx
0x18002fb02  sub     rsp, 20h
0x18002fb06  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18002fb0d  mov     rbx, rcx
0x18002fb10  test    rax, rax
0x18002fb13  jnz     short loc_18002FB2D
0x18002fb15  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18002fb1c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002fb21  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18002fb28  test    rax, rax
0x18002fb2b  jz      short loc_18002FB35
0x18002fb2d  mov     rcx, rbx
0x18002fb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb35  add     rsp, 20h
0x18002fb39  pop     rbx
0x18002fb3a  retn
```
