# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001cf48`
- end: `0x18001cfad`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001be58`

## callees

- `0x18001cb50`
- `0x18001cf48`
- `0x18001e010`

## string_xrefs

- `0x18001cf6c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001cf48  mov     [rsp+arg_0], rbx
0x18001cf4d  mov     [rsp+arg_8], rsi
0x18001cf52  push    rdi
0x18001cf53  sub     rsp, 30h
0x18001cf57  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001cf5e  mov     rbx, r9
0x18001cf61  mov     rdi, rdx
0x18001cf64  mov     rsi, rcx
0x18001cf67  test    rax, rax
0x18001cf6a  jnz     short loc_18001CF8B
0x18001cf6c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001cf73  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001cf78  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001cf7f  test    rax, rax
0x18001cf82  jnz     short loc_18001CF8B
0x18001cf84  mov     eax, 0C0000139h
0x18001cf89  jmp     short loc_18001CF9C
0x18001cf8b  mov     r9, rbx
0x18001cf8e  xor     r8d, r8d
0x18001cf91  mov     rdx, rdi
0x18001cf94  mov     rcx, rsi
0x18001cf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf9c  mov     rbx, [rsp+38h+arg_0]
0x18001cfa1  mov     rsi, [rsp+38h+arg_8]
0x18001cfa6  add     rsp, 30h
0x18001cfaa  pop     rdi
0x18001cfab  retn
```
