# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800189c0`
- end: `0x180018a24`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180017224`

## callees

- `0x18000fe50`
- `0x1800189c0`
- `0x18001c010`

## string_xrefs

- `0x1800189e4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800189c0  mov     [rsp+arg_0], rbx
0x1800189c5  mov     [rsp+arg_8], rsi
0x1800189ca  push    rdi
0x1800189cb  sub     rsp, 30h
0x1800189cf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800189d6  mov     rbx, r9
0x1800189d9  mov     rdi, rdx
0x1800189dc  mov     rsi, rcx
0x1800189df  test    rax, rax
0x1800189e2  jnz     short loc_180018A03
0x1800189e4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800189eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800189f0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800189f7  test    rax, rax
0x1800189fa  jnz     short loc_180018A03
0x1800189fc  mov     eax, 0C0000139h
0x180018a01  jmp     short loc_180018A14
0x180018a03  mov     r9, rbx
0x180018a06  xor     r8d, r8d
0x180018a09  mov     rdx, rdi
0x180018a0c  mov     rcx, rsi
0x180018a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a14  mov     rbx, [rsp+38h+arg_0]
0x180018a19  mov     rsi, [rsp+38h+arg_8]
0x180018a1e  add     rsp, 30h
0x180018a22  pop     rdi
0x180018a23  retn
```
