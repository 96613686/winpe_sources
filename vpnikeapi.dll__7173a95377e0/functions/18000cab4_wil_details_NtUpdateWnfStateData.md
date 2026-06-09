# wil_details_NtUpdateWnfStateData

- ea: `0x18000cab4`
- end: `0x18000cb3a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a9a0`
- `0x18000c154`

## callees

- `0x18000c12c`
- `0x18000cab4`
- `0x18000e010`

## string_xrefs

- `0x18000cad8`: `NtUpdateWnfStateData`

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
0x18000cab4  mov     [rsp+arg_0], rbx
0x18000cab9  mov     [rsp+arg_8], rsi
0x18000cabe  push    rdi
0x18000cabf  sub     rsp, 40h
0x18000cac3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000caca  mov     ebx, r8d
0x18000cacd  mov     rdi, rdx
0x18000cad0  mov     rsi, rcx
0x18000cad3  test    r10, r10
0x18000cad6  jnz     short loc_18000CAFA
0x18000cad8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000cadf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000cae4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000caeb  mov     r10, rax
0x18000caee  test    rax, rax
0x18000caf1  jnz     short loc_18000CAFA
0x18000caf3  mov     eax, 0C0000139h
0x18000caf8  jmp     short loc_18000CB2A
0x18000cafa  mov     eax, [rsp+48h+arg_30]
0x18000cb01  xor     r9d, r9d
0x18000cb04  mov     [rsp+48h+var_18], eax
0x18000cb08  mov     r8d, ebx
0x18000cb0b  mov     eax, [rsp+48h+arg_28]
0x18000cb0f  mov     rdx, rdi
0x18000cb12  mov     [rsp+48h+var_20], eax
0x18000cb16  mov     rcx, rsi
0x18000cb19  mov     rax, r10
0x18000cb1c  mov     [rsp+48h+var_28], 0
0x18000cb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb2a  mov     rbx, [rsp+48h+arg_0]
0x18000cb2f  mov     rsi, [rsp+48h+arg_8]
0x18000cb34  add     rsp, 40h
0x18000cb38  pop     rdi
0x18000cb39  retn
```
