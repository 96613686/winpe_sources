# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180004e60`
- end: `0x180004ec4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b630`

## callees

- `0x180004e60`
- `0x18000c070`
- `0x180016010`

## string_xrefs

- `0x180004e84`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180004e60  mov     [rsp+arg_0], rbx
0x180004e65  mov     [rsp+arg_8], rsi
0x180004e6a  push    rdi
0x180004e6b  sub     rsp, 30h
0x180004e6f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180004e76  mov     rbx, r9
0x180004e79  mov     rdi, rdx
0x180004e7c  mov     rsi, rcx
0x180004e7f  test    rax, rax
0x180004e82  jnz     short loc_180004EA3
0x180004e84  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180004e8b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180004e90  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180004e97  test    rax, rax
0x180004e9a  jnz     short loc_180004EA3
0x180004e9c  mov     eax, 0C0000139h
0x180004ea1  jmp     short loc_180004EB4
0x180004ea3  mov     r9, rbx
0x180004ea6  xor     r8d, r8d
0x180004ea9  mov     rdx, rdi
0x180004eac  mov     rcx, rsi
0x180004eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb4  mov     rbx, [rsp+38h+arg_0]
0x180004eb9  mov     rsi, [rsp+38h+arg_8]
0x180004ebe  add     rsp, 30h
0x180004ec2  pop     rdi
0x180004ec3  retn
```
