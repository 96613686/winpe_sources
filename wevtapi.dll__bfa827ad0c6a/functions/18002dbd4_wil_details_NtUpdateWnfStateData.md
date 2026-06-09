# wil_details_NtUpdateWnfStateData

- ea: `0x18002dbd4`
- end: `0x18002dc5a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002c004`
- `0x18002d798`

## callees

- `0x18002d770`
- `0x18002dbd4`
- `0x18003c010`

## string_xrefs

- `0x18002dbf8`: `NtUpdateWnfStateData`

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
0x18002dbd4  mov     [rsp+arg_0], rbx
0x18002dbd9  mov     [rsp+arg_8], rsi
0x18002dbde  push    rdi
0x18002dbdf  sub     rsp, 40h
0x18002dbe3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002dbea  mov     ebx, r8d
0x18002dbed  mov     rdi, rdx
0x18002dbf0  mov     rsi, rcx
0x18002dbf3  test    r10, r10
0x18002dbf6  jnz     short loc_18002DC1A
0x18002dbf8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002dbff  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002dc04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002dc0b  mov     r10, rax
0x18002dc0e  test    rax, rax
0x18002dc11  jnz     short loc_18002DC1A
0x18002dc13  mov     eax, 0C0000139h
0x18002dc18  jmp     short loc_18002DC4A
0x18002dc1a  mov     eax, [rsp+48h+arg_30]
0x18002dc21  xor     r9d, r9d
0x18002dc24  mov     [rsp+48h+var_18], eax
0x18002dc28  mov     r8d, ebx
0x18002dc2b  mov     eax, [rsp+48h+arg_28]
0x18002dc2f  mov     rdx, rdi
0x18002dc32  mov     [rsp+48h+var_20], eax
0x18002dc36  mov     rcx, rsi
0x18002dc39  mov     rax, r10
0x18002dc3c  mov     [rsp+48h+var_28], 0
0x18002dc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc4a  mov     rbx, [rsp+48h+arg_0]
0x18002dc4f  mov     rsi, [rsp+48h+arg_8]
0x18002dc54  add     rsp, 40h
0x18002dc58  pop     rdi
0x18002dc59  retn
```
