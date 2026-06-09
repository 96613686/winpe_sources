# wil_details_NtUpdateWnfStateData

- ea: `0x1800187e4`
- end: `0x18001886a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180016af8`
- `0x180017cf8`

## callees

- `0x18000fe50`
- `0x1800187e4`
- `0x18001c010`

## string_xrefs

- `0x180018808`: `NtUpdateWnfStateData`

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
0x1800187e4  mov     [rsp+arg_0], rbx
0x1800187e9  mov     [rsp+arg_8], rsi
0x1800187ee  push    rdi
0x1800187ef  sub     rsp, 40h
0x1800187f3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800187fa  mov     ebx, r8d
0x1800187fd  mov     rdi, rdx
0x180018800  mov     rsi, rcx
0x180018803  test    r10, r10
0x180018806  jnz     short loc_18001882A
0x180018808  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001880f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180018814  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001881b  mov     r10, rax
0x18001881e  test    rax, rax
0x180018821  jnz     short loc_18001882A
0x180018823  mov     eax, 0C0000139h
0x180018828  jmp     short loc_18001885A
0x18001882a  mov     eax, [rsp+48h+arg_30]
0x180018831  xor     r9d, r9d
0x180018834  mov     [rsp+48h+var_18], eax
0x180018838  mov     r8d, ebx
0x18001883b  mov     eax, [rsp+48h+arg_28]
0x18001883f  mov     rdx, rdi
0x180018842  mov     [rsp+48h+var_20], eax
0x180018846  mov     rcx, rsi
0x180018849  mov     rax, r10
0x18001884c  mov     [rsp+48h+var_28], 0
0x180018855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001885a  mov     rbx, [rsp+48h+arg_0]
0x18001885f  mov     rsi, [rsp+48h+arg_8]
0x180018864  add     rsp, 40h
0x180018868  pop     rdi
0x180018869  retn
```
