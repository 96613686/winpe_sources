# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000ad1c`
- end: `0x18000ad80`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800097f0`

## callees

- `0x18000ad1c`
- `0x18000ae00`
- `0x18001b010`

## string_xrefs

- `0x18000ad40`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000ad1c  mov     [rsp+arg_0], rbx
0x18000ad21  mov     [rsp+arg_8], rsi
0x18000ad26  push    rdi
0x18000ad27  sub     rsp, 30h
0x18000ad2b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000ad32  mov     rbx, r9
0x18000ad35  mov     rdi, rdx
0x18000ad38  mov     rsi, rcx
0x18000ad3b  test    rax, rax
0x18000ad3e  jnz     short loc_18000AD5F
0x18000ad40  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ad47  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ad4c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ad53  test    rax, rax
0x18000ad56  jnz     short loc_18000AD5F
0x18000ad58  mov     eax, 0C0000139h
0x18000ad5d  jmp     short loc_18000AD70
0x18000ad5f  mov     r9, rbx
0x18000ad62  xor     r8d, r8d
0x18000ad65  mov     rdx, rdi
0x18000ad68  mov     rcx, rsi
0x18000ad6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad70  mov     rbx, [rsp+38h+arg_0]
0x18000ad75  mov     rsi, [rsp+38h+arg_8]
0x18000ad7a  add     rsp, 30h
0x18000ad7e  pop     rdi
0x18000ad7f  retn
```
