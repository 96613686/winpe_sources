# wil_details_NtUpdateWnfStateData

- ea: `0x18002f924`
- end: `0x18002f9aa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002e988`
- `0x18002f4c8`

## callees

- `0x18002f4a0`
- `0x18002f924`
- `0x180042010`

## string_xrefs

- `0x18002f948`: `NtUpdateWnfStateData`

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
0x18002f924  mov     [rsp+arg_0], rbx
0x18002f929  mov     [rsp+arg_8], rsi
0x18002f92e  push    rdi
0x18002f92f  sub     rsp, 40h
0x18002f933  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002f93a  mov     ebx, r8d
0x18002f93d  mov     rdi, rdx
0x18002f940  mov     rsi, rcx
0x18002f943  test    r10, r10
0x18002f946  jnz     short loc_18002F96A
0x18002f948  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002f94f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002f954  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002f95b  mov     r10, rax
0x18002f95e  test    rax, rax
0x18002f961  jnz     short loc_18002F96A
0x18002f963  mov     eax, 0C0000139h
0x18002f968  jmp     short loc_18002F99A
0x18002f96a  mov     eax, [rsp+48h+arg_30]
0x18002f971  xor     r9d, r9d
0x18002f974  mov     [rsp+48h+var_18], eax
0x18002f978  mov     r8d, ebx
0x18002f97b  mov     eax, [rsp+48h+arg_28]
0x18002f97f  mov     rdx, rdi
0x18002f982  mov     [rsp+48h+var_20], eax
0x18002f986  mov     rcx, rsi
0x18002f989  mov     rax, r10
0x18002f98c  mov     [rsp+48h+var_28], 0
0x18002f995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f99a  mov     rbx, [rsp+48h+arg_0]
0x18002f99f  mov     rsi, [rsp+48h+arg_8]
0x18002f9a4  add     rsp, 40h
0x18002f9a8  pop     rdi
0x18002f9a9  retn
```
