# wil_details_NtUpdateWnfStateData

- ea: `0x180018cac`
- end: `0x180018d32`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180016da0`
- `0x18001704c`

## callees

- `0x180011354`
- `0x180018cac`
- `0x180038010`

## string_xrefs

- `0x180018cd0`: `NtUpdateWnfStateData`

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
0x180018cac  mov     [rsp+arg_0], rbx
0x180018cb1  mov     [rsp+arg_8], rsi
0x180018cb6  push    rdi
0x180018cb7  sub     rsp, 40h
0x180018cbb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180018cc2  mov     ebx, r8d
0x180018cc5  mov     rdi, rdx
0x180018cc8  mov     rsi, rcx
0x180018ccb  test    r10, r10
0x180018cce  jnz     short loc_180018CF2
0x180018cd0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180018cd7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180018cdc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180018ce3  mov     r10, rax
0x180018ce6  test    rax, rax
0x180018ce9  jnz     short loc_180018CF2
0x180018ceb  mov     eax, 0C0000139h
0x180018cf0  jmp     short loc_180018D22
0x180018cf2  mov     eax, [rsp+48h+arg_30]
0x180018cf9  xor     r9d, r9d
0x180018cfc  mov     [rsp+48h+var_18], eax
0x180018d00  mov     r8d, ebx
0x180018d03  mov     eax, [rsp+48h+arg_28]
0x180018d07  mov     rdx, rdi
0x180018d0a  mov     [rsp+48h+var_20], eax
0x180018d0e  mov     rcx, rsi
0x180018d11  mov     rax, r10
0x180018d14  mov     [rsp+48h+var_28], 0
0x180018d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d22  mov     rbx, [rsp+48h+arg_0]
0x180018d27  mov     rsi, [rsp+48h+arg_8]
0x180018d2c  add     rsp, 40h
0x180018d30  pop     rdi
0x180018d31  retn
```
