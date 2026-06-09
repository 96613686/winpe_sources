# wil_details_NtUpdateWnfStateData

- ea: `0x18001a37c`
- end: `0x18001a402`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001969c`
- `0x180019c10`

## callees

- `0x18000ae00`
- `0x18001a37c`
- `0x18001b010`

## string_xrefs

- `0x18001a3a0`: `NtUpdateWnfStateData`

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
0x18001a37c  mov     [rsp+arg_0], rbx
0x18001a381  mov     [rsp+arg_8], rsi
0x18001a386  push    rdi
0x18001a387  sub     rsp, 40h
0x18001a38b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001a392  mov     ebx, r8d
0x18001a395  mov     rdi, rdx
0x18001a398  mov     rsi, rcx
0x18001a39b  test    r10, r10
0x18001a39e  jnz     short loc_18001A3C2
0x18001a3a0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001a3a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001a3ac  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001a3b3  mov     r10, rax
0x18001a3b6  test    rax, rax
0x18001a3b9  jnz     short loc_18001A3C2
0x18001a3bb  mov     eax, 0C0000139h
0x18001a3c0  jmp     short loc_18001A3F2
0x18001a3c2  mov     eax, [rsp+48h+arg_30]
0x18001a3c9  xor     r9d, r9d
0x18001a3cc  mov     [rsp+48h+var_18], eax
0x18001a3d0  mov     r8d, ebx
0x18001a3d3  mov     eax, [rsp+48h+arg_28]
0x18001a3d7  mov     rdx, rdi
0x18001a3da  mov     [rsp+48h+var_20], eax
0x18001a3de  mov     rcx, rsi
0x18001a3e1  mov     rax, r10
0x18001a3e4  mov     [rsp+48h+var_28], 0
0x18001a3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3f2  mov     rbx, [rsp+48h+arg_0]
0x18001a3f7  mov     rsi, [rsp+48h+arg_8]
0x18001a3fc  add     rsp, 40h
0x18001a400  pop     rdi
0x18001a401  retn
```
