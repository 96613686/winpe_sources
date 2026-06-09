# wil_details_NtUpdateWnfStateData

- ea: `0x1800144f8`
- end: `0x18001457f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f708`
- `0x180010ff0`

## callees

- `0x18000aac8`
- `0x1800144f8`
- `0x18001e010`

## string_xrefs

- `0x18001451c`: `NtUpdateWnfStateData`

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
0x1800144f8  mov     [rsp+arg_0], rbx
0x1800144fd  mov     [rsp+arg_8], rsi
0x180014502  push    rdi
0x180014503  sub     rsp, 40h
0x180014507  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001450e  mov     ebx, r8d
0x180014511  mov     rdi, rdx
0x180014514  mov     rsi, rcx
0x180014517  test    r10, r10
0x18001451a  jnz     short loc_18001453E
0x18001451c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180014523  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180014528  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001452f  mov     r10, rax
0x180014532  test    rax, rax
0x180014535  jnz     short loc_18001453E
0x180014537  mov     eax, 0C0000139h
0x18001453c  jmp     short loc_18001456E
0x18001453e  mov     eax, [rsp+48h+arg_30]
0x180014545  xor     r9d, r9d
0x180014548  mov     [rsp+48h+var_18], eax
0x18001454c  mov     r8d, ebx
0x18001454f  mov     eax, [rsp+48h+arg_28]
0x180014553  mov     rdx, rdi
0x180014556  mov     [rsp+48h+var_20], eax
0x18001455a  mov     rcx, rsi
0x18001455d  mov     rax, r10
0x180014560  mov     [rsp+48h+var_28], 0
0x180014569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001456e  mov     rbx, [rsp+48h+arg_0]
0x180014573  mov     rsi, [rsp+48h+arg_8]
0x180014578  add     rsp, 40h
0x18001457c  pop     rdi
0x18001457d  retn
```
