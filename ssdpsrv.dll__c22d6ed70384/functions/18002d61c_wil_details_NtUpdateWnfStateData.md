# wil_details_NtUpdateWnfStateData

- ea: `0x18002d61c`
- end: `0x18002d6a2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002ae10`
- `0x18002c658`

## callees

- `0x18002c630`
- `0x18002d61c`
- `0x180036010`

## string_xrefs

- `0x18002d640`: `NtUpdateWnfStateData`

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
0x18002d61c  mov     [rsp+arg_0], rbx
0x18002d621  mov     [rsp+arg_8], rsi
0x18002d626  push    rdi
0x18002d627  sub     rsp, 40h
0x18002d62b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002d632  mov     ebx, r8d
0x18002d635  mov     rdi, rdx
0x18002d638  mov     rsi, rcx
0x18002d63b  test    r10, r10
0x18002d63e  jnz     short loc_18002D662
0x18002d640  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002d647  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002d64c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002d653  mov     r10, rax
0x18002d656  test    rax, rax
0x18002d659  jnz     short loc_18002D662
0x18002d65b  mov     eax, 0C0000139h
0x18002d660  jmp     short loc_18002D692
0x18002d662  mov     eax, [rsp+48h+arg_30]
0x18002d669  xor     r9d, r9d
0x18002d66c  mov     [rsp+48h+var_18], eax
0x18002d670  mov     r8d, ebx
0x18002d673  mov     eax, [rsp+48h+arg_28]
0x18002d677  mov     rdx, rdi
0x18002d67a  mov     [rsp+48h+var_20], eax
0x18002d67e  mov     rcx, rsi
0x18002d681  mov     rax, r10
0x18002d684  mov     [rsp+48h+var_28], 0
0x18002d68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d692  mov     rbx, [rsp+48h+arg_0]
0x18002d697  mov     rsi, [rsp+48h+arg_8]
0x18002d69c  add     rsp, 40h
0x18002d6a0  pop     rdi
0x18002d6a1  retn
```
