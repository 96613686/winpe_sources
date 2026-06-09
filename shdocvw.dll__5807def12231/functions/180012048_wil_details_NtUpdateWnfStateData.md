# wil_details_NtUpdateWnfStateData

- ea: `0x180012048`
- end: `0x1800120ce`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f81c`
- `0x180011974`

## callees

- `0x180004b90`
- `0x180012048`
- `0x180029010`

## string_xrefs

- `0x18001206c`: `NtUpdateWnfStateData`

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
0x180012048  mov     [rsp+arg_0], rbx
0x18001204d  mov     [rsp+arg_8], rsi
0x180012052  push    rdi
0x180012053  sub     rsp, 40h
0x180012057  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001205e  mov     ebx, r8d
0x180012061  mov     rdi, rdx
0x180012064  mov     rsi, rcx
0x180012067  test    r10, r10
0x18001206a  jnz     short loc_18001208E
0x18001206c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180012073  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012078  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001207f  mov     r10, rax
0x180012082  test    rax, rax
0x180012085  jnz     short loc_18001208E
0x180012087  mov     eax, 0C0000139h
0x18001208c  jmp     short loc_1800120BE
0x18001208e  mov     eax, [rsp+48h+arg_30]
0x180012095  xor     r9d, r9d
0x180012098  mov     [rsp+48h+var_18], eax
0x18001209c  mov     r8d, ebx
0x18001209f  mov     eax, [rsp+48h+arg_28]
0x1800120a3  mov     rdx, rdi
0x1800120a6  mov     [rsp+48h+var_20], eax
0x1800120aa  mov     rcx, rsi
0x1800120ad  mov     rax, r10
0x1800120b0  mov     [rsp+48h+var_28], 0
0x1800120b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120be  mov     rbx, [rsp+48h+arg_0]
0x1800120c3  mov     rsi, [rsp+48h+arg_8]
0x1800120c8  add     rsp, 40h
0x1800120cc  pop     rdi
0x1800120cd  retn
```
