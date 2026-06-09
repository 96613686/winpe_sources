# wil_details_NtUpdateWnfStateData

- ea: `0x18003d8f8`
- end: `0x18003d97e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18003a600`
- `0x18003c8c0`

## callees

- `0x18003c898`
- `0x18003d8f8`
- `0x180040010`

## string_xrefs

- `0x18003d91c`: `NtUpdateWnfStateData`

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
0x18003d8f8  mov     [rsp+arg_0], rbx
0x18003d8fd  mov     [rsp+arg_8], rsi
0x18003d902  push    rdi
0x18003d903  sub     rsp, 40h
0x18003d907  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18003d90e  mov     ebx, r8d
0x18003d911  mov     rdi, rdx
0x18003d914  mov     rsi, rcx
0x18003d917  test    r10, r10
0x18003d91a  jnz     short loc_18003D93E
0x18003d91c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18003d923  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003d928  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18003d92f  mov     r10, rax
0x18003d932  test    rax, rax
0x18003d935  jnz     short loc_18003D93E
0x18003d937  mov     eax, 0C0000139h
0x18003d93c  jmp     short loc_18003D96E
0x18003d93e  mov     eax, [rsp+48h+arg_30]
0x18003d945  xor     r9d, r9d
0x18003d948  mov     [rsp+48h+var_18], eax
0x18003d94c  mov     r8d, ebx
0x18003d94f  mov     eax, [rsp+48h+arg_28]
0x18003d953  mov     rdx, rdi
0x18003d956  mov     [rsp+48h+var_20], eax
0x18003d95a  mov     rcx, rsi
0x18003d95d  mov     rax, r10
0x18003d960  mov     [rsp+48h+var_28], 0
0x18003d969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d96e  mov     rbx, [rsp+48h+arg_0]
0x18003d973  mov     rsi, [rsp+48h+arg_8]
0x18003d978  add     rsp, 40h
0x18003d97c  pop     rdi
0x18003d97d  retn
```
