# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180028994`
- end: `0x1800289f8`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800274f8`

## callees

- `0x180024e78`
- `0x180028994`
- `0x180031010`

## string_xrefs

- `0x1800289b8`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180028994  mov     [rsp+arg_0], rbx
0x180028999  mov     [rsp+arg_8], rsi
0x18002899e  push    rdi
0x18002899f  sub     rsp, 30h
0x1800289a3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800289aa  mov     rbx, r9
0x1800289ad  mov     rdi, rdx
0x1800289b0  mov     rsi, rcx
0x1800289b3  test    rax, rax
0x1800289b6  jnz     short loc_1800289D7
0x1800289b8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800289bf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800289c4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800289cb  test    rax, rax
0x1800289ce  jnz     short loc_1800289D7
0x1800289d0  mov     eax, 0C0000139h
0x1800289d5  jmp     short loc_1800289E8
0x1800289d7  mov     r9, rbx
0x1800289da  xor     r8d, r8d
0x1800289dd  mov     rdx, rdi
0x1800289e0  mov     rcx, rsi
0x1800289e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289e8  mov     rbx, [rsp+38h+arg_0]
0x1800289ed  mov     rsi, [rsp+38h+arg_8]
0x1800289f2  add     rsp, 30h
0x1800289f6  pop     rdi
0x1800289f7  retn
```
