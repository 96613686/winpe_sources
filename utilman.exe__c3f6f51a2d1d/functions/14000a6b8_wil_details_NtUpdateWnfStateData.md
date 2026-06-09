# wil_details_NtUpdateWnfStateData

- ea: `0x14000a6b8`
- end: `0x14000a73f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140007be4`
- `0x14000a144`

## callees

- `0x14000a118`
- `0x14000a6b8`
- `0x140029010`

## string_xrefs

- `0x14000a6dc`: `NtUpdateWnfStateData`

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
0x14000a6b8  mov     [rsp+arg_0], rbx
0x14000a6bd  mov     [rsp+arg_8], rsi
0x14000a6c2  push    rdi
0x14000a6c3  sub     rsp, 40h
0x14000a6c7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000a6ce  mov     ebx, r8d
0x14000a6d1  mov     rdi, rdx
0x14000a6d4  mov     rsi, rcx
0x14000a6d7  test    r10, r10
0x14000a6da  jnz     short loc_14000A6FE
0x14000a6dc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000a6e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000a6e8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000a6ef  mov     r10, rax
0x14000a6f2  test    rax, rax
0x14000a6f5  jnz     short loc_14000A6FE
0x14000a6f7  mov     eax, 0C0000139h
0x14000a6fc  jmp     short loc_14000A72E
0x14000a6fe  mov     eax, [rsp+48h+arg_30]
0x14000a705  xor     r9d, r9d
0x14000a708  mov     [rsp+48h+var_18], eax
0x14000a70c  mov     r8d, ebx
0x14000a70f  mov     eax, [rsp+48h+arg_28]
0x14000a713  mov     rdx, rdi
0x14000a716  mov     [rsp+48h+var_20], eax
0x14000a71a  mov     rcx, rsi
0x14000a71d  mov     rax, r10
0x14000a720  mov     [rsp+48h+var_28], 0
0x14000a729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a72e  mov     rbx, [rsp+48h+arg_0]
0x14000a733  mov     rsi, [rsp+48h+arg_8]
0x14000a738  add     rsp, 40h
0x14000a73c  pop     rdi
0x14000a73d  retn
```
