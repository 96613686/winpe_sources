# wil_details_NtUpdateWnfStateData

- ea: `0x180023ea4`
- end: `0x180023f2a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180020b60`
- `0x180022b18`

## callees

- `0x180022af0`
- `0x180023ea4`
- `0x180033010`

## string_xrefs

- `0x180023ec8`: `NtUpdateWnfStateData`

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
0x180023ea4  mov     [rsp+arg_0], rbx
0x180023ea9  mov     [rsp+arg_8], rsi
0x180023eae  push    rdi
0x180023eaf  sub     rsp, 40h
0x180023eb3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180023eba  mov     ebx, r8d
0x180023ebd  mov     rdi, rdx
0x180023ec0  mov     rsi, rcx
0x180023ec3  test    r10, r10
0x180023ec6  jnz     short loc_180023EEA
0x180023ec8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180023ecf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180023ed4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180023edb  mov     r10, rax
0x180023ede  test    rax, rax
0x180023ee1  jnz     short loc_180023EEA
0x180023ee3  mov     eax, 0C0000139h
0x180023ee8  jmp     short loc_180023F1A
0x180023eea  mov     eax, [rsp+48h+arg_30]
0x180023ef1  xor     r9d, r9d
0x180023ef4  mov     [rsp+48h+var_18], eax
0x180023ef8  mov     r8d, ebx
0x180023efb  mov     eax, [rsp+48h+arg_28]
0x180023eff  mov     rdx, rdi
0x180023f02  mov     [rsp+48h+var_20], eax
0x180023f06  mov     rcx, rsi
0x180023f09  mov     rax, r10
0x180023f0c  mov     [rsp+48h+var_28], 0
0x180023f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f1a  mov     rbx, [rsp+48h+arg_0]
0x180023f1f  mov     rsi, [rsp+48h+arg_8]
0x180023f24  add     rsp, 40h
0x180023f28  pop     rdi
0x180023f29  retn
```
