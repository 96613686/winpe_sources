# wil_details_NtUpdateWnfStateData

- ea: `0x180011010`
- end: `0x180011096`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f5f8`
- `0x180010c7c`

## callees

- `0x180010c54`
- `0x180011010`
- `0x18001d010`

## string_xrefs

- `0x180011034`: `NtUpdateWnfStateData`

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
0x180011010  mov     [rsp+arg_0], rbx
0x180011015  mov     [rsp+arg_8], rsi
0x18001101a  push    rdi
0x18001101b  sub     rsp, 40h
0x18001101f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180011026  mov     ebx, r8d
0x180011029  mov     rdi, rdx
0x18001102c  mov     rsi, rcx
0x18001102f  test    r10, r10
0x180011032  jnz     short loc_180011056
0x180011034  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001103b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180011040  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180011047  mov     r10, rax
0x18001104a  test    rax, rax
0x18001104d  jnz     short loc_180011056
0x18001104f  mov     eax, 0C0000139h
0x180011054  jmp     short loc_180011086
0x180011056  mov     eax, [rsp+48h+arg_30]
0x18001105d  xor     r9d, r9d
0x180011060  mov     [rsp+48h+var_18], eax
0x180011064  mov     r8d, ebx
0x180011067  mov     eax, [rsp+48h+arg_28]
0x18001106b  mov     rdx, rdi
0x18001106e  mov     [rsp+48h+var_20], eax
0x180011072  mov     rcx, rsi
0x180011075  mov     rax, r10
0x180011078  mov     [rsp+48h+var_28], 0
0x180011081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011086  mov     rbx, [rsp+48h+arg_0]
0x18001108b  mov     rsi, [rsp+48h+arg_8]
0x180011090  add     rsp, 40h
0x180011094  pop     rdi
0x180011095  retn
```
