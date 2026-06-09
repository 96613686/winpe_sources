# wil_details_NtUpdateWnfStateData

- ea: `0x1800202ec`
- end: `0x180020372`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800036c0`
- `0x180003b50`
- `0x180026af8`

## callees

- `0x18000363c`
- `0x1800202ec`
- `0x180042010`

## string_xrefs

- `0x180020310`: `NtUpdateWnfStateData`

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
0x1800202ec  mov     [rsp+arg_0], rbx
0x1800202f1  mov     [rsp+arg_8], rsi
0x1800202f6  push    rdi
0x1800202f7  sub     rsp, 40h
0x1800202fb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180020302  mov     ebx, r8d
0x180020305  mov     rdi, rdx
0x180020308  mov     rsi, rcx
0x18002030b  test    r10, r10
0x18002030e  jnz     short loc_180020332
0x180020310  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180020317  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002031c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180020323  mov     r10, rax
0x180020326  test    rax, rax
0x180020329  jnz     short loc_180020332
0x18002032b  mov     eax, 0C0000139h
0x180020330  jmp     short loc_180020362
0x180020332  mov     eax, [rsp+48h+arg_30]
0x180020339  xor     r9d, r9d
0x18002033c  mov     [rsp+48h+var_18], eax
0x180020340  mov     r8d, ebx
0x180020343  mov     eax, [rsp+48h+arg_28]
0x180020347  mov     rdx, rdi
0x18002034a  mov     [rsp+48h+var_20], eax
0x18002034e  mov     rcx, rsi
0x180020351  mov     rax, r10
0x180020354  mov     [rsp+48h+var_28], 0
0x18002035d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020362  mov     rbx, [rsp+48h+arg_0]
0x180020367  mov     rsi, [rsp+48h+arg_8]
0x18002036c  add     rsp, 40h
0x180020370  pop     rdi
0x180020371  retn
```
