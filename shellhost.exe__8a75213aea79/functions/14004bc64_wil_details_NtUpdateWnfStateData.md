# wil_details_NtUpdateWnfStateData

- ea: `0x14004bc64`
- end: `0x14004bcea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140048f18`
- `0x14004b708`

## callees

- `0x14004b6e0`
- `0x14004bc64`
- `0x140067010`

## string_xrefs

- `0x14004bc88`: `NtUpdateWnfStateData`

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
0x14004bc64  mov     [rsp+arg_0], rbx
0x14004bc69  mov     [rsp+arg_8], rsi
0x14004bc6e  push    rdi
0x14004bc6f  sub     rsp, 40h
0x14004bc73  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14004bc7a  mov     ebx, r8d
0x14004bc7d  mov     rdi, rdx
0x14004bc80  mov     rsi, rcx
0x14004bc83  test    r10, r10
0x14004bc86  jnz     short loc_14004BCAA
0x14004bc88  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14004bc8f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14004bc94  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14004bc9b  mov     r10, rax
0x14004bc9e  test    rax, rax
0x14004bca1  jnz     short loc_14004BCAA
0x14004bca3  mov     eax, 0C0000139h
0x14004bca8  jmp     short loc_14004BCDA
0x14004bcaa  mov     eax, [rsp+48h+arg_30]
0x14004bcb1  xor     r9d, r9d
0x14004bcb4  mov     [rsp+48h+var_18], eax
0x14004bcb8  mov     r8d, ebx
0x14004bcbb  mov     eax, [rsp+48h+arg_28]
0x14004bcbf  mov     rdx, rdi
0x14004bcc2  mov     [rsp+48h+var_20], eax
0x14004bcc6  mov     rcx, rsi
0x14004bcc9  mov     rax, r10
0x14004bccc  mov     [rsp+48h+var_28], 0
0x14004bcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bcda  mov     rbx, [rsp+48h+arg_0]
0x14004bcdf  mov     rsi, [rsp+48h+arg_8]
0x14004bce4  add     rsp, 40h
0x14004bce8  pop     rdi
0x14004bce9  retn
```
