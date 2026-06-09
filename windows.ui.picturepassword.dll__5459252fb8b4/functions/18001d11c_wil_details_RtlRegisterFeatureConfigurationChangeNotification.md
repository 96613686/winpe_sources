# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001d11c`
- end: `0x18001d180`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c624`

## callees

- `0x18000b9b4`
- `0x18001d11c`
- `0x18001f010`

## string_xrefs

- `0x18001d140`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001d11c  mov     [rsp+arg_0], rbx
0x18001d121  mov     [rsp+arg_8], rsi
0x18001d126  push    rdi
0x18001d127  sub     rsp, 30h
0x18001d12b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001d132  mov     rbx, r9
0x18001d135  mov     rdi, rdx
0x18001d138  mov     rsi, rcx
0x18001d13b  test    rax, rax
0x18001d13e  jnz     short loc_18001D15F
0x18001d140  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001d147  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001d14c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001d153  test    rax, rax
0x18001d156  jnz     short loc_18001D15F
0x18001d158  mov     eax, 0C0000139h
0x18001d15d  jmp     short loc_18001D170
0x18001d15f  mov     r9, rbx
0x18001d162  xor     r8d, r8d
0x18001d165  mov     rdx, rdi
0x18001d168  mov     rcx, rsi
0x18001d16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d170  mov     rbx, [rsp+38h+arg_0]
0x18001d175  mov     rsi, [rsp+38h+arg_8]
0x18001d17a  add     rsp, 30h
0x18001d17e  pop     rdi
0x18001d17f  retn
```
