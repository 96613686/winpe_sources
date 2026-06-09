# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000a898`
- end: `0x14000a8fd`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400091c0`

## callees

- `0x14000a118`
- `0x14000a898`
- `0x140029010`

## string_xrefs

- `0x14000a8bc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000a898  mov     [rsp+arg_0], rbx
0x14000a89d  mov     [rsp+arg_8], rsi
0x14000a8a2  push    rdi
0x14000a8a3  sub     rsp, 30h
0x14000a8a7  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000a8ae  mov     rbx, r9
0x14000a8b1  mov     rdi, rdx
0x14000a8b4  mov     rsi, rcx
0x14000a8b7  test    rax, rax
0x14000a8ba  jnz     short loc_14000A8DB
0x14000a8bc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000a8c3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a8c8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000a8cf  test    rax, rax
0x14000a8d2  jnz     short loc_14000A8DB
0x14000a8d4  mov     eax, 0C0000139h
0x14000a8d9  jmp     short loc_14000A8EC
0x14000a8db  mov     r9, rbx
0x14000a8de  xor     r8d, r8d
0x14000a8e1  mov     rdx, rdi
0x14000a8e4  mov     rcx, rsi
0x14000a8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8ec  mov     rbx, [rsp+38h+arg_0]
0x14000a8f1  mov     rsi, [rsp+38h+arg_8]
0x14000a8f6  add     rsp, 30h
0x14000a8fa  pop     rdi
0x14000a8fb  retn
```
