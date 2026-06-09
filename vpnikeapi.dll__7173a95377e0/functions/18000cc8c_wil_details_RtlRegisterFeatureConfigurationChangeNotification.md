# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000cc8c`
- end: `0x18000ccf0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b2b0`

## callees

- `0x18000c12c`
- `0x18000cc8c`
- `0x18000e010`

## string_xrefs

- `0x18000ccb0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000cc8c  mov     [rsp+arg_0], rbx
0x18000cc91  mov     [rsp+arg_8], rsi
0x18000cc96  push    rdi
0x18000cc97  sub     rsp, 30h
0x18000cc9b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000cca2  mov     rbx, r9
0x18000cca5  mov     rdi, rdx
0x18000cca8  mov     rsi, rcx
0x18000ccab  test    rax, rax
0x18000ccae  jnz     short loc_18000CCCF
0x18000ccb0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ccb7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ccbc  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ccc3  test    rax, rax
0x18000ccc6  jnz     short loc_18000CCCF
0x18000ccc8  mov     eax, 0C0000139h
0x18000cccd  jmp     short loc_18000CCE0
0x18000cccf  mov     r9, rbx
0x18000ccd2  xor     r8d, r8d
0x18000ccd5  mov     rdx, rdi
0x18000ccd8  mov     rcx, rsi
0x18000ccdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cce0  mov     rbx, [rsp+38h+arg_0]
0x18000cce5  mov     rsi, [rsp+38h+arg_8]
0x18000ccea  add     rsp, 30h
0x18000ccee  pop     rdi
0x18000ccef  retn
```
