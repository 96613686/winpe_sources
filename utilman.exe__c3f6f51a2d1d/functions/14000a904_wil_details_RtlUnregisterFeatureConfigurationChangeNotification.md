# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000a904`
- end: `0x14000a940`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400048a4`

## callees

- `0x14000a118`
- `0x14000a904`
- `0x140029010`

## string_xrefs

- `0x14000a919`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000a904  push    rbx
0x14000a906  sub     rsp, 20h
0x14000a90a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000a911  mov     rbx, rcx
0x14000a914  test    rax, rax
0x14000a917  jnz     short loc_14000A931
0x14000a919  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000a920  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a925  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000a92c  test    rax, rax
0x14000a92f  jz      short loc_14000A939
0x14000a931  mov     rcx, rbx
0x14000a934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a939  add     rsp, 20h
0x14000a93d  pop     rbx
0x14000a93e  retn
```
