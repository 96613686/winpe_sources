# wil_details_NtUpdateWnfStateData

- ea: `0x1800109f4`
- end: `0x180010a7b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000445c`
- `0x18000ca6c`

## callees

- `0x18000ca40`
- `0x1800109f4`
- `0x180017010`

## string_xrefs

- `0x180010a18`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)wil_details_GetNtDllProcedureAddress("NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x1800109f4  mov     [rsp+arg_0], rbx
0x1800109f9  mov     [rsp+arg_8], rsi
0x1800109fe  push    rdi
0x1800109ff  sub     rsp, 40h
0x180010a03  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180010a0a  mov     ebx, r8d
0x180010a0d  mov     rdi, rdx
0x180010a10  mov     rsi, rcx
0x180010a13  test    r10, r10
0x180010a16  jnz     short loc_180010A3A
0x180010a18  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180010a1f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180010a24  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180010a2b  mov     r10, rax
0x180010a2e  test    rax, rax
0x180010a31  jnz     short loc_180010A3A
0x180010a33  mov     eax, 0C0000139h
0x180010a38  jmp     short loc_180010A6A
0x180010a3a  mov     eax, [rsp+48h+arg_30]
0x180010a41  xor     r9d, r9d
0x180010a44  mov     [rsp+48h+var_18], eax
0x180010a48  mov     r8d, ebx
0x180010a4b  mov     eax, [rsp+48h+arg_28]
0x180010a4f  mov     rdx, rdi
0x180010a52  mov     [rsp+48h+var_20], eax
0x180010a56  mov     rcx, rsi
0x180010a59  mov     rax, r10
0x180010a5c  mov     [rsp+48h+var_28], 0
0x180010a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6a  mov     rbx, [rsp+48h+arg_0]
0x180010a6f  mov     rsi, [rsp+48h+arg_8]
0x180010a74  add     rsp, 40h
0x180010a78  pop     rdi
0x180010a79  retn
```
