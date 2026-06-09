# wil_details_NtUpdateWnfStateData

- ea: `0x180012c5c`
- end: `0x180012ce2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180010840`
- `0x180012a08`

## callees

- `0x1800129e0`
- `0x180012c5c`
- `0x180014010`

## string_xrefs

- `0x180012c80`: `NtUpdateWnfStateData`

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
0x180012c5c  mov     [rsp+arg_0], rbx
0x180012c61  mov     [rsp+arg_8], rsi
0x180012c66  push    rdi
0x180012c67  sub     rsp, 40h
0x180012c6b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012c72  mov     ebx, r8d
0x180012c75  mov     rdi, rdx
0x180012c78  mov     rsi, rcx
0x180012c7b  test    r10, r10
0x180012c7e  jnz     short loc_180012CA2
0x180012c80  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180012c87  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012c8c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180012c93  mov     r10, rax
0x180012c96  test    rax, rax
0x180012c99  jnz     short loc_180012CA2
0x180012c9b  mov     eax, 0C0000139h
0x180012ca0  jmp     short loc_180012CD2
0x180012ca2  mov     eax, [rsp+48h+arg_30]
0x180012ca9  xor     r9d, r9d
0x180012cac  mov     [rsp+48h+var_18], eax
0x180012cb0  mov     r8d, ebx
0x180012cb3  mov     eax, [rsp+48h+arg_28]
0x180012cb7  mov     rdx, rdi
0x180012cba  mov     [rsp+48h+var_20], eax
0x180012cbe  mov     rcx, rsi
0x180012cc1  mov     rax, r10
0x180012cc4  mov     [rsp+48h+var_28], 0
0x180012ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cd2  mov     rbx, [rsp+48h+arg_0]
0x180012cd7  mov     rsi, [rsp+48h+arg_8]
0x180012cdc  add     rsp, 40h
0x180012ce0  pop     rdi
0x180012ce1  retn
```
