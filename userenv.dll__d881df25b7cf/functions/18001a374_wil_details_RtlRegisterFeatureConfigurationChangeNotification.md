# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001a374`
- end: `0x18001a3d9`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180018b98`

## callees

- `0x180010c90`
- `0x18001a374`
- `0x18001d010`

## string_xrefs

- `0x18001a398`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
0x18001a374  mov     [rsp+arg_0], rbx
0x18001a379  mov     [rsp+arg_8], rsi
0x18001a37e  push    rdi
0x18001a37f  sub     rsp, 30h
0x18001a383  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001a38a  mov     rbx, r9
0x18001a38d  mov     rdi, rdx
0x18001a390  mov     rsi, rcx
0x18001a393  test    rax, rax
0x18001a396  jnz     short loc_18001A3B7
0x18001a398  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001a39f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001a3a4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001a3ab  test    rax, rax
0x18001a3ae  jnz     short loc_18001A3B7
0x18001a3b0  mov     eax, 0C0000139h
0x18001a3b5  jmp     short loc_18001A3C8
0x18001a3b7  mov     r9, rbx
0x18001a3ba  xor     r8d, r8d
0x18001a3bd  mov     rdx, rdi
0x18001a3c0  mov     rcx, rsi
0x18001a3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3c8  mov     rbx, [rsp+38h+arg_0]
0x18001a3cd  mov     rsi, [rsp+38h+arg_8]
0x18001a3d2  add     rsp, 30h
0x18001a3d6  pop     rdi
0x18001a3d7  retn
```
