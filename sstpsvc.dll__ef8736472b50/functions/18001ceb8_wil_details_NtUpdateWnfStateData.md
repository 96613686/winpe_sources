# wil_details_NtUpdateWnfStateData

- ea: `0x18001ceb8`
- end: `0x18001cf3f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b450`
- `0x18001cb7c`

## callees

- `0x18001cb50`
- `0x18001ceb8`
- `0x18001e010`

## string_xrefs

- `0x18001cedc`: `NtUpdateWnfStateData`

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
0x18001ceb8  mov     [rsp+arg_0], rbx
0x18001cebd  mov     [rsp+arg_8], rsi
0x18001cec2  push    rdi
0x18001cec3  sub     rsp, 40h
0x18001cec7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001cece  mov     ebx, r8d
0x18001ced1  mov     rdi, rdx
0x18001ced4  mov     rsi, rcx
0x18001ced7  test    r10, r10
0x18001ceda  jnz     short loc_18001CEFE
0x18001cedc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001cee3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001cee8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001ceef  mov     r10, rax
0x18001cef2  test    rax, rax
0x18001cef5  jnz     short loc_18001CEFE
0x18001cef7  mov     eax, 0C0000139h
0x18001cefc  jmp     short loc_18001CF2E
0x18001cefe  mov     eax, [rsp+48h+arg_30]
0x18001cf05  xor     r9d, r9d
0x18001cf08  mov     [rsp+48h+var_18], eax
0x18001cf0c  mov     r8d, ebx
0x18001cf0f  mov     eax, [rsp+48h+arg_28]
0x18001cf13  mov     rdx, rdi
0x18001cf16  mov     [rsp+48h+var_20], eax
0x18001cf1a  mov     rcx, rsi
0x18001cf1d  mov     rax, r10
0x18001cf20  mov     [rsp+48h+var_28], 0
0x18001cf29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf2e  mov     rbx, [rsp+48h+arg_0]
0x18001cf33  mov     rsi, [rsp+48h+arg_8]
0x18001cf38  add     rsp, 40h
0x18001cf3c  pop     rdi
0x18001cf3d  retn
```
