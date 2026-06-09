# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800276fc`
- end: `0x180027760`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180027674`

## callees

- `0x1800276fc`
- `0x18002f4a0`
- `0x180042010`

## string_xrefs

- `0x180027720`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800276fc  mov     [rsp+arg_0], rbx
0x180027701  mov     [rsp+arg_8], rsi
0x180027706  push    rdi
0x180027707  sub     rsp, 30h
0x18002770b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180027712  mov     rbx, r9
0x180027715  mov     rdi, rdx
0x180027718  mov     rsi, rcx
0x18002771b  test    rax, rax
0x18002771e  jnz     short loc_18002773F
0x180027720  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180027727  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002772c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180027733  test    rax, rax
0x180027736  jnz     short loc_18002773F
0x180027738  mov     eax, 0C0000139h
0x18002773d  jmp     short loc_180027750
0x18002773f  mov     r9, rbx
0x180027742  xor     r8d, r8d
0x180027745  mov     rdx, rdi
0x180027748  mov     rcx, rsi
0x18002774b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027750  mov     rbx, [rsp+38h+arg_0]
0x180027755  mov     rsi, [rsp+38h+arg_8]
0x18002775a  add     rsp, 30h
0x18002775e  pop     rdi
0x18002775f  retn
```
