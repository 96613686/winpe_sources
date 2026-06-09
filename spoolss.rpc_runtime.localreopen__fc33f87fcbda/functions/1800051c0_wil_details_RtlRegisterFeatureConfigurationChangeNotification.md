# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800051c0`
- end: `0x180005225`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bf50`

## callees

- `0x1800051c0`
- `0x18000ca40`
- `0x180017010`

## string_xrefs

- `0x1800051e4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800051c0  mov     [rsp+arg_0], rbx
0x1800051c5  mov     [rsp+arg_8], rsi
0x1800051ca  push    rdi
0x1800051cb  sub     rsp, 30h
0x1800051cf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800051d6  mov     rbx, r9
0x1800051d9  mov     rdi, rdx
0x1800051dc  mov     rsi, rcx
0x1800051df  test    rax, rax
0x1800051e2  jnz     short loc_180005203
0x1800051e4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800051eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800051f0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800051f7  test    rax, rax
0x1800051fa  jnz     short loc_180005203
0x1800051fc  mov     eax, 0C0000139h
0x180005201  jmp     short loc_180005214
0x180005203  mov     r9, rbx
0x180005206  xor     r8d, r8d
0x180005209  mov     rdx, rdi
0x18000520c  mov     rcx, rsi
0x18000520f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005214  mov     rbx, [rsp+38h+arg_0]
0x180005219  mov     rsi, [rsp+38h+arg_8]
0x18000521e  add     rsp, 30h
0x180005222  pop     rdi
0x180005223  retn
```
