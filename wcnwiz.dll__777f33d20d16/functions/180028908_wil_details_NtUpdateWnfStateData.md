# wil_details_NtUpdateWnfStateData

- ea: `0x180028908`
- end: `0x18002898e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180027050`
- `0x180028600`

## callees

- `0x180024e78`
- `0x180028908`
- `0x180031010`

## string_xrefs

- `0x18002892c`: `NtUpdateWnfStateData`

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
0x180028908  mov     [rsp+arg_0], rbx
0x18002890d  mov     [rsp+arg_8], rsi
0x180028912  push    rdi
0x180028913  sub     rsp, 40h
0x180028917  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002891e  mov     ebx, r8d
0x180028921  mov     rdi, rdx
0x180028924  mov     rsi, rcx
0x180028927  test    r10, r10
0x18002892a  jnz     short loc_18002894E
0x18002892c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180028933  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180028938  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002893f  mov     r10, rax
0x180028942  test    rax, rax
0x180028945  jnz     short loc_18002894E
0x180028947  mov     eax, 0C0000139h
0x18002894c  jmp     short loc_18002897E
0x18002894e  mov     eax, [rsp+48h+arg_30]
0x180028955  xor     r9d, r9d
0x180028958  mov     [rsp+48h+var_18], eax
0x18002895c  mov     r8d, ebx
0x18002895f  mov     eax, [rsp+48h+arg_28]
0x180028963  mov     rdx, rdi
0x180028966  mov     [rsp+48h+var_20], eax
0x18002896a  mov     rcx, rsi
0x18002896d  mov     rax, r10
0x180028970  mov     [rsp+48h+var_28], 0
0x180028979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002897e  mov     rbx, [rsp+48h+arg_0]
0x180028983  mov     rsi, [rsp+48h+arg_8]
0x180028988  add     rsp, 40h
0x18002898c  pop     rdi
0x18002898d  retn
```
