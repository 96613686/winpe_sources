# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180013a40`
- end: `0x180013aa4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011624`

## callees

- `0x180012920`
- `0x180013a40`
- `0x18003d010`

## string_xrefs

- `0x180013a64`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180013a40  mov     [rsp+arg_0], rbx
0x180013a45  mov     [rsp+arg_8], rsi
0x180013a4a  push    rdi
0x180013a4b  sub     rsp, 30h
0x180013a4f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180013a56  mov     rbx, r9
0x180013a59  mov     rdi, rdx
0x180013a5c  mov     rsi, rcx
0x180013a5f  test    rax, rax
0x180013a62  jnz     short loc_180013A83
0x180013a64  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180013a6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013a70  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180013a77  test    rax, rax
0x180013a7a  jnz     short loc_180013A83
0x180013a7c  mov     eax, 0C0000139h
0x180013a81  jmp     short loc_180013A94
0x180013a83  mov     r9, rbx
0x180013a86  xor     r8d, r8d
0x180013a89  mov     rdx, rdi
0x180013a8c  mov     rcx, rsi
0x180013a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a94  mov     rbx, [rsp+38h+arg_0]
0x180013a99  mov     rsi, [rsp+38h+arg_8]
0x180013a9e  add     rsp, 30h
0x180013aa2  pop     rdi
0x180013aa3  retn
```
