# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000ace4`
- end: `0x18000ad48`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010530`

## callees

- `0x18000ace4`
- `0x180010c54`
- `0x18001d010`

## string_xrefs

- `0x18000ad08`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000ace4  mov     [rsp+arg_0], rbx
0x18000ace9  mov     [rsp+arg_8], rsi
0x18000acee  push    rdi
0x18000acef  sub     rsp, 30h
0x18000acf3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000acfa  mov     rbx, r9
0x18000acfd  mov     rdi, rdx
0x18000ad00  mov     rsi, rcx
0x18000ad03  test    rax, rax
0x18000ad06  jnz     short loc_18000AD27
0x18000ad08  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ad0f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ad14  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ad1b  test    rax, rax
0x18000ad1e  jnz     short loc_18000AD27
0x18000ad20  mov     eax, 0C0000139h
0x18000ad25  jmp     short loc_18000AD38
0x18000ad27  mov     r9, rbx
0x18000ad2a  xor     r8d, r8d
0x18000ad2d  mov     rdx, rdi
0x18000ad30  mov     rcx, rsi
0x18000ad33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad38  mov     rbx, [rsp+38h+arg_0]
0x18000ad3d  mov     rsi, [rsp+38h+arg_8]
0x18000ad42  add     rsp, 30h
0x18000ad46  pop     rdi
0x18000ad47  retn
```
