# wil_details_NtUpdateWnfStateData

- ea: `0x180013864`
- end: `0x1800138ea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800103c4`
- `0x180012948`

## callees

- `0x180012920`
- `0x180013864`
- `0x18003d010`

## string_xrefs

- `0x180013888`: `NtUpdateWnfStateData`

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
0x180013864  mov     [rsp+arg_0], rbx
0x180013869  mov     [rsp+arg_8], rsi
0x18001386e  push    rdi
0x18001386f  sub     rsp, 40h
0x180013873  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001387a  mov     ebx, r8d
0x18001387d  mov     rdi, rdx
0x180013880  mov     rsi, rcx
0x180013883  test    r10, r10
0x180013886  jnz     short loc_1800138AA
0x180013888  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001388f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013894  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001389b  mov     r10, rax
0x18001389e  test    rax, rax
0x1800138a1  jnz     short loc_1800138AA
0x1800138a3  mov     eax, 0C0000139h
0x1800138a8  jmp     short loc_1800138DA
0x1800138aa  mov     eax, [rsp+48h+arg_30]
0x1800138b1  xor     r9d, r9d
0x1800138b4  mov     [rsp+48h+var_18], eax
0x1800138b8  mov     r8d, ebx
0x1800138bb  mov     eax, [rsp+48h+arg_28]
0x1800138bf  mov     rdx, rdi
0x1800138c2  mov     [rsp+48h+var_20], eax
0x1800138c6  mov     rcx, rsi
0x1800138c9  mov     rax, r10
0x1800138cc  mov     [rsp+48h+var_28], 0
0x1800138d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138da  mov     rbx, [rsp+48h+arg_0]
0x1800138df  mov     rsi, [rsp+48h+arg_8]
0x1800138e4  add     rsp, 40h
0x1800138e8  pop     rdi
0x1800138e9  retn
```
