# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18003dad0`
- end: `0x18003db34`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18003b734`

## callees

- `0x18003c898`
- `0x18003dad0`
- `0x180040010`

## string_xrefs

- `0x18003daf4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18003dad0  mov     [rsp+arg_0], rbx
0x18003dad5  mov     [rsp+arg_8], rsi
0x18003dada  push    rdi
0x18003dadb  sub     rsp, 30h
0x18003dadf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18003dae6  mov     rbx, r9
0x18003dae9  mov     rdi, rdx
0x18003daec  mov     rsi, rcx
0x18003daef  test    rax, rax
0x18003daf2  jnz     short loc_18003DB13
0x18003daf4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18003dafb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003db00  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18003db07  test    rax, rax
0x18003db0a  jnz     short loc_18003DB13
0x18003db0c  mov     eax, 0C0000139h
0x18003db11  jmp     short loc_18003DB24
0x18003db13  mov     r9, rbx
0x18003db16  xor     r8d, r8d
0x18003db19  mov     rdx, rdi
0x18003db1c  mov     rcx, rsi
0x18003db1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db24  mov     rbx, [rsp+38h+arg_0]
0x18003db29  mov     rsi, [rsp+38h+arg_8]
0x18003db2e  add     rsp, 30h
0x18003db32  pop     rdi
0x18003db33  retn
```
