# wil_details_NtUpdateWnfStateData

- ea: `0x18000f914`
- end: `0x18000f99a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180004154`
- `0x18000c098`

## callees

- `0x18000c070`
- `0x18000f914`
- `0x180016010`

## string_xrefs

- `0x18000f938`: `NtUpdateWnfStateData`

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
0x18000f914  mov     [rsp+arg_0], rbx
0x18000f919  mov     [rsp+arg_8], rsi
0x18000f91e  push    rdi
0x18000f91f  sub     rsp, 40h
0x18000f923  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000f92a  mov     ebx, r8d
0x18000f92d  mov     rdi, rdx
0x18000f930  mov     rsi, rcx
0x18000f933  test    r10, r10
0x18000f936  jnz     short loc_18000F95A
0x18000f938  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000f93f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f944  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000f94b  mov     r10, rax
0x18000f94e  test    rax, rax
0x18000f951  jnz     short loc_18000F95A
0x18000f953  mov     eax, 0C0000139h
0x18000f958  jmp     short loc_18000F98A
0x18000f95a  mov     eax, [rsp+48h+arg_30]
0x18000f961  xor     r9d, r9d
0x18000f964  mov     [rsp+48h+var_18], eax
0x18000f968  mov     r8d, ebx
0x18000f96b  mov     eax, [rsp+48h+arg_28]
0x18000f96f  mov     rdx, rdi
0x18000f972  mov     [rsp+48h+var_20], eax
0x18000f976  mov     rcx, rsi
0x18000f979  mov     rax, r10
0x18000f97c  mov     [rsp+48h+var_28], 0
0x18000f985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f98a  mov     rbx, [rsp+48h+arg_0]
0x18000f98f  mov     rsi, [rsp+48h+arg_8]
0x18000f994  add     rsp, 40h
0x18000f998  pop     rdi
0x18000f999  retn
```
