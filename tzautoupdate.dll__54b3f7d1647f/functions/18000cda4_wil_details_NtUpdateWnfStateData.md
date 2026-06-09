# wil_details_NtUpdateWnfStateData

- ea: `0x18000cda4`
- end: `0x18000ce2a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008024`
- `0x18000ba28`

## callees

- `0x18000ba00`
- `0x18000cda4`
- `0x18001d010`

## string_xrefs

- `0x18000cdc8`: `NtUpdateWnfStateData`

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
0x18000cda4  mov     [rsp+arg_0], rbx
0x18000cda9  mov     [rsp+arg_8], rsi
0x18000cdae  push    rdi
0x18000cdaf  sub     rsp, 40h
0x18000cdb3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000cdba  mov     ebx, r8d
0x18000cdbd  mov     rdi, rdx
0x18000cdc0  mov     rsi, rcx
0x18000cdc3  test    r10, r10
0x18000cdc6  jnz     short loc_18000CDEA
0x18000cdc8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000cdcf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000cdd4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000cddb  mov     r10, rax
0x18000cdde  test    rax, rax
0x18000cde1  jnz     short loc_18000CDEA
0x18000cde3  mov     eax, 0C0000139h
0x18000cde8  jmp     short loc_18000CE1A
0x18000cdea  mov     eax, [rsp+48h+arg_30]
0x18000cdf1  xor     r9d, r9d
0x18000cdf4  mov     [rsp+48h+var_18], eax
0x18000cdf8  mov     r8d, ebx
0x18000cdfb  mov     eax, [rsp+48h+arg_28]
0x18000cdff  mov     rdx, rdi
0x18000ce02  mov     [rsp+48h+var_20], eax
0x18000ce06  mov     rcx, rsi
0x18000ce09  mov     rax, r10
0x18000ce0c  mov     [rsp+48h+var_28], 0
0x18000ce15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce1a  mov     rbx, [rsp+48h+arg_0]
0x18000ce1f  mov     rsi, [rsp+48h+arg_8]
0x18000ce24  add     rsp, 40h
0x18000ce28  pop     rdi
0x18000ce29  retn
```
