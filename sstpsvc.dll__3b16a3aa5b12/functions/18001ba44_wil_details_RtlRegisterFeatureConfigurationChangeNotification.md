# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001ba44`
- end: `0x18001baa8`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a91c`

## callees

- `0x18001b67c`
- `0x18001ba44`
- `0x18001d010`

## string_xrefs

- `0x18001ba68`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001ba44  mov     [rsp+arg_0], rbx
0x18001ba49  mov     [rsp+arg_8], rsi
0x18001ba4e  push    rdi
0x18001ba4f  sub     rsp, 30h
0x18001ba53  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001ba5a  mov     rbx, r9
0x18001ba5d  mov     rdi, rdx
0x18001ba60  mov     rsi, rcx
0x18001ba63  test    rax, rax
0x18001ba66  jnz     short loc_18001BA87
0x18001ba68  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001ba6f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001ba74  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001ba7b  test    rax, rax
0x18001ba7e  jnz     short loc_18001BA87
0x18001ba80  mov     eax, 0C0000139h
0x18001ba85  jmp     short loc_18001BA98
0x18001ba87  mov     r9, rbx
0x18001ba8a  xor     r8d, r8d
0x18001ba8d  mov     rdx, rdi
0x18001ba90  mov     rcx, rsi
0x18001ba93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba98  mov     rbx, [rsp+38h+arg_0]
0x18001ba9d  mov     rsi, [rsp+38h+arg_8]
0x18001baa2  add     rsp, 30h
0x18001baa6  pop     rdi
0x18001baa7  retn
```
