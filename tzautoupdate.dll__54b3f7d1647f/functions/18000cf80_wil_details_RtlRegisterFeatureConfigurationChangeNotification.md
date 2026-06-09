# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000cf80`
- end: `0x18000cfe4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800091dc`

## callees

- `0x18000ba00`
- `0x18000cf80`
- `0x18001d010`

## string_xrefs

- `0x18000cfa4`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC NtDllProcedureAddress; // rax

  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000cf80  mov     [rsp+arg_0], rbx
0x18000cf85  mov     [rsp+arg_8], rsi
0x18000cf8a  push    rdi
0x18000cf8b  sub     rsp, 30h
0x18000cf8f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000cf96  mov     rbx, r9
0x18000cf99  mov     rdi, rdx
0x18000cf9c  mov     rsi, rcx
0x18000cf9f  test    rax, rax
0x18000cfa2  jnz     short loc_18000CFC3
0x18000cfa4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000cfab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000cfb0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000cfb7  test    rax, rax
0x18000cfba  jnz     short loc_18000CFC3
0x18000cfbc  mov     eax, 0C0000139h
0x18000cfc1  jmp     short loc_18000CFD4
0x18000cfc3  mov     r9, rbx
0x18000cfc6  xor     r8d, r8d
0x18000cfc9  mov     rdx, rdi
0x18000cfcc  mov     rcx, rsi
0x18000cfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfd4  mov     rbx, [rsp+38h+arg_0]
0x18000cfd9  mov     rsi, [rsp+38h+arg_8]
0x18000cfde  add     rsp, 30h
0x18000cfe2  pop     rdi
0x18000cfe3  retn
```
