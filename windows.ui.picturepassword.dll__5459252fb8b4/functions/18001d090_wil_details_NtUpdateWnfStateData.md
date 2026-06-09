# wil_details_NtUpdateWnfStateData

- ea: `0x18001d090`
- end: `0x18001d116`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c150`
- `0x18001cddc`

## callees

- `0x18000b9b4`
- `0x18001d090`
- `0x18001f010`

## string_xrefs

- `0x18001d0b4`: `NtUpdateWnfStateData`

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
0x18001d090  mov     [rsp+arg_0], rbx
0x18001d095  mov     [rsp+arg_8], rsi
0x18001d09a  push    rdi
0x18001d09b  sub     rsp, 40h
0x18001d09f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001d0a6  mov     ebx, r8d
0x18001d0a9  mov     rdi, rdx
0x18001d0ac  mov     rsi, rcx
0x18001d0af  test    r10, r10
0x18001d0b2  jnz     short loc_18001D0D6
0x18001d0b4  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001d0bb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001d0c0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001d0c7  mov     r10, rax
0x18001d0ca  test    rax, rax
0x18001d0cd  jnz     short loc_18001D0D6
0x18001d0cf  mov     eax, 0C0000139h
0x18001d0d4  jmp     short loc_18001D106
0x18001d0d6  mov     eax, [rsp+48h+arg_30]
0x18001d0dd  xor     r9d, r9d
0x18001d0e0  mov     [rsp+48h+var_18], eax
0x18001d0e4  mov     r8d, ebx
0x18001d0e7  mov     eax, [rsp+48h+arg_28]
0x18001d0eb  mov     rdx, rdi
0x18001d0ee  mov     [rsp+48h+var_20], eax
0x18001d0f2  mov     rcx, rsi
0x18001d0f5  mov     rax, r10
0x18001d0f8  mov     [rsp+48h+var_28], 0
0x18001d101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d106  mov     rbx, [rsp+48h+arg_0]
0x18001d10b  mov     rsi, [rsp+48h+arg_8]
0x18001d110  add     rsp, 40h
0x18001d114  pop     rdi
0x18001d115  retn
```
