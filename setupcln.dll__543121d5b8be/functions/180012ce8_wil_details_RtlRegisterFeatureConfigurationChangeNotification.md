# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180012ce8`
- end: `0x180012d4c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800114bc`

## callees

- `0x1800129e0`
- `0x180012ce8`
- `0x180014010`

## string_xrefs

- `0x180012d0c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180012ce8  mov     [rsp+arg_0], rbx
0x180012ced  mov     [rsp+arg_8], rsi
0x180012cf2  push    rdi
0x180012cf3  sub     rsp, 30h
0x180012cf7  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180012cfe  mov     rbx, r9
0x180012d01  mov     rdi, rdx
0x180012d04  mov     rsi, rcx
0x180012d07  test    rax, rax
0x180012d0a  jnz     short loc_180012D2B
0x180012d0c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180012d13  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012d18  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180012d1f  test    rax, rax
0x180012d22  jnz     short loc_180012D2B
0x180012d24  mov     eax, 0C0000139h
0x180012d29  jmp     short loc_180012D3C
0x180012d2b  mov     r9, rbx
0x180012d2e  xor     r8d, r8d
0x180012d31  mov     rdx, rdi
0x180012d34  mov     rcx, rsi
0x180012d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d3c  mov     rbx, [rsp+38h+arg_0]
0x180012d41  mov     rsi, [rsp+38h+arg_8]
0x180012d46  add     rsp, 30h
0x180012d4a  pop     rdi
0x180012d4b  retn
```
