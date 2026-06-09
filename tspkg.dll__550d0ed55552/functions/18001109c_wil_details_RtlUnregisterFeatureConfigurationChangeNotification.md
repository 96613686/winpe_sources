# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18001109c`
- end: `0x1800110d7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a52c`

## callees

- `0x180010c54`
- `0x18001109c`
- `0x18001d010`

## string_xrefs

- `0x1800110b1`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18001109c  push    rbx
0x18001109e  sub     rsp, 20h
0x1800110a2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800110a9  mov     rbx, rcx
0x1800110ac  test    rax, rax
0x1800110af  jnz     short loc_1800110C9
0x1800110b1  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800110b8  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800110bd  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800110c4  test    rax, rax
0x1800110c7  jz      short loc_1800110D1
0x1800110c9  mov     rcx, rbx
0x1800110cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d1  add     rsp, 20h
0x1800110d5  pop     rbx
0x1800110d6  retn
```
