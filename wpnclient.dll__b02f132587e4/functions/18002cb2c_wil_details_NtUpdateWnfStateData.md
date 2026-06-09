# wil_details_NtUpdateWnfStateData

- ea: `0x18002cb2c`
- end: `0x18002cbb2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002b2b4`
- `0x18002c3ac`

## callees

- `0x180022d58`
- `0x18002cb2c`
- `0x180032010`

## string_xrefs

- `0x18002cb50`: `NtUpdateWnfStateData`

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
0x18002cb2c  mov     [rsp+arg_0], rbx
0x18002cb31  mov     [rsp+arg_8], rsi
0x18002cb36  push    rdi
0x18002cb37  sub     rsp, 40h
0x18002cb3b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002cb42  mov     ebx, r8d
0x18002cb45  mov     rdi, rdx
0x18002cb48  mov     rsi, rcx
0x18002cb4b  test    r10, r10
0x18002cb4e  jnz     short loc_18002CB72
0x18002cb50  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002cb57  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002cb5c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002cb63  mov     r10, rax
0x18002cb66  test    rax, rax
0x18002cb69  jnz     short loc_18002CB72
0x18002cb6b  mov     eax, 0C0000139h
0x18002cb70  jmp     short loc_18002CBA2
0x18002cb72  mov     eax, [rsp+48h+arg_30]
0x18002cb79  xor     r9d, r9d
0x18002cb7c  mov     [rsp+48h+var_18], eax
0x18002cb80  mov     r8d, ebx
0x18002cb83  mov     eax, [rsp+48h+arg_28]
0x18002cb87  mov     rdx, rdi
0x18002cb8a  mov     [rsp+48h+var_20], eax
0x18002cb8e  mov     rcx, rsi
0x18002cb91  mov     rax, r10
0x18002cb94  mov     [rsp+48h+var_28], 0
0x18002cb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cba2  mov     rbx, [rsp+48h+arg_0]
0x18002cba7  mov     rsi, [rsp+48h+arg_8]
0x18002cbac  add     rsp, 40h
0x18002cbb0  pop     rdi
0x18002cbb1  retn
```
