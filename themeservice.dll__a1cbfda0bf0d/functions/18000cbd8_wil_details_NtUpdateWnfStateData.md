# wil_details_NtUpdateWnfStateData

- ea: `0x18000cbd8`
- end: `0x18000cc5e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bcd4`
- `0x18000c930`

## callees

- `0x18000a464`
- `0x18000cbd8`
- `0x180010010`

## string_xrefs

- `0x18000cbfc`: `NtUpdateWnfStateData`

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
0x18000cbd8  mov     [rsp+arg_0], rbx
0x18000cbdd  mov     [rsp+arg_8], rsi
0x18000cbe2  push    rdi
0x18000cbe3  sub     rsp, 40h
0x18000cbe7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000cbee  mov     ebx, r8d
0x18000cbf1  mov     rdi, rdx
0x18000cbf4  mov     rsi, rcx
0x18000cbf7  test    r10, r10
0x18000cbfa  jnz     short loc_18000CC1E
0x18000cbfc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000cc03  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000cc08  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000cc0f  mov     r10, rax
0x18000cc12  test    rax, rax
0x18000cc15  jnz     short loc_18000CC1E
0x18000cc17  mov     eax, 0C0000139h
0x18000cc1c  jmp     short loc_18000CC4E
0x18000cc1e  mov     eax, [rsp+48h+arg_30]
0x18000cc25  xor     r9d, r9d
0x18000cc28  mov     [rsp+48h+var_18], eax
0x18000cc2c  mov     r8d, ebx
0x18000cc2f  mov     eax, [rsp+48h+arg_28]
0x18000cc33  mov     rdx, rdi
0x18000cc36  mov     [rsp+48h+var_20], eax
0x18000cc3a  mov     rcx, rsi
0x18000cc3d  mov     rax, r10
0x18000cc40  mov     [rsp+48h+var_28], 0
0x18000cc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4e  mov     rbx, [rsp+48h+arg_0]
0x18000cc53  mov     rsi, [rsp+48h+arg_8]
0x18000cc58  add     rsp, 40h
0x18000cc5c  pop     rdi
0x18000cc5d  retn
```
