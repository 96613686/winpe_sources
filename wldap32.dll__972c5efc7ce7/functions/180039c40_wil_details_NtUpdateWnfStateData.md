# wil_details_NtUpdateWnfStateData

- ea: `0x180039c40`
- end: `0x180039cc7`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800381e0`
- `0x1800398ec`

## callees

- `0x18002b440`
- `0x180039c40`
- `0x18004d010`

## string_xrefs

- `0x180039c64`: `NtUpdateWnfStateData`

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
0x180039c40  mov     [rsp+arg_0], rbx
0x180039c45  mov     [rsp+arg_8], rsi
0x180039c4a  push    rdi
0x180039c4b  sub     rsp, 40h
0x180039c4f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180039c56  mov     ebx, r8d
0x180039c59  mov     rdi, rdx
0x180039c5c  mov     rsi, rcx
0x180039c5f  test    r10, r10
0x180039c62  jnz     short loc_180039C86
0x180039c64  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180039c6b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180039c70  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180039c77  mov     r10, rax
0x180039c7a  test    rax, rax
0x180039c7d  jnz     short loc_180039C86
0x180039c7f  mov     eax, 0C0000139h
0x180039c84  jmp     short loc_180039CB6
0x180039c86  mov     eax, [rsp+48h+arg_30]
0x180039c8d  xor     r9d, r9d
0x180039c90  mov     [rsp+48h+var_18], eax
0x180039c94  mov     r8d, ebx
0x180039c97  mov     eax, [rsp+48h+arg_28]
0x180039c9b  mov     rdx, rdi
0x180039c9e  mov     [rsp+48h+var_20], eax
0x180039ca2  mov     rcx, rsi
0x180039ca5  mov     rax, r10
0x180039ca8  mov     [rsp+48h+var_28], 0
0x180039cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cb6  mov     rbx, [rsp+48h+arg_0]
0x180039cbb  mov     rsi, [rsp+48h+arg_8]
0x180039cc0  add     rsp, 40h
0x180039cc4  pop     rdi
0x180039cc5  retn
```
