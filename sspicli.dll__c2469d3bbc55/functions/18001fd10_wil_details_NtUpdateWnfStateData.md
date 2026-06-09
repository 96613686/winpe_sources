# wil_details_NtUpdateWnfStateData

- ea: `0x18001fd10`
- end: `0x18001fd96`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180015d84`
- `0x18001fa28`

## callees

- `0x180012f7c`
- `0x18001fd10`
- `0x180023010`

## string_xrefs

- `0x18001fd34`: `NtUpdateWnfStateData`

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
0x18001fd10  mov     [rsp+arg_0], rbx
0x18001fd15  mov     [rsp+arg_8], rsi
0x18001fd1a  push    rdi
0x18001fd1b  sub     rsp, 40h
0x18001fd1f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001fd26  mov     ebx, r8d
0x18001fd29  mov     rdi, rdx
0x18001fd2c  mov     rsi, rcx
0x18001fd2f  test    r10, r10
0x18001fd32  jnz     short loc_18001FD56
0x18001fd34  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001fd3b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001fd40  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001fd47  mov     r10, rax
0x18001fd4a  test    rax, rax
0x18001fd4d  jnz     short loc_18001FD56
0x18001fd4f  mov     eax, 0C0000139h
0x18001fd54  jmp     short loc_18001FD86
0x18001fd56  mov     eax, [rsp+48h+arg_30]
0x18001fd5d  xor     r9d, r9d
0x18001fd60  mov     [rsp+48h+var_18], eax
0x18001fd64  mov     r8d, ebx
0x18001fd67  mov     eax, [rsp+48h+arg_28]
0x18001fd6b  mov     rdx, rdi
0x18001fd6e  mov     [rsp+48h+var_20], eax
0x18001fd72  mov     rcx, rsi
0x18001fd75  mov     rax, r10
0x18001fd78  mov     [rsp+48h+var_28], 0
0x18001fd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd86  mov     rbx, [rsp+48h+arg_0]
0x18001fd8b  mov     rsi, [rsp+48h+arg_8]
0x18001fd90  add     rsp, 40h
0x18001fd94  pop     rdi
0x18001fd95  retn
```
