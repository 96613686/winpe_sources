# DLRegSetValueExW

- ea: `0x180028de4`
- end: `0x180028e72`
- name: `DLRegSetValueExW`
- size: `142`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000eed4`
- `0x180010240`
- `0x180028d30`
- `0x180028d80`
- `0x18002ac50`
- `0x18002c190`
- `0x18002cb50`
- `0x18002cec0`
- `0x1800349a0`
- `0x180037b80`
- `0x180037bf0`

## callees

- `0x1800101cc`
- `0x180028de4`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028e1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028e1f`

## string_xrefs

- `0x180028e18`: `RegSetValueExW`

## pseudocode

```c
DWORD __fastcall DLRegSetValueExW(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, int a6)
{
  __int64 (__fastcall *v6)(__int64, __int64, _QWORD, _QWORD, __int64, int); // r10
  DWORD result; // eax

  v6 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64, int))qword_1800703E0;
  if ( qword_1800703E0 )
    return v6(a1, a2, 0, a4, a5, a6);
  result = DLpLoadRegistryDll();
  if ( result )
    return result;
  qword_1800703E0 = (__int64)GetProcAddress(g_hInstRegistryDLL, "RegSetValueExW");
  v6 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64, int))qword_1800703E0;
  if ( qword_1800703E0 )
    return v6(a1, a2, 0, a4, a5, a6);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180028de4  mov     [rsp+arg_0], rbx
0x180028de9  mov     [rsp+arg_8], rsi
0x180028dee  push    rdi
0x180028def  sub     rsp, 40h
0x180028df3  mov     r10, cs:qword_1800703E0
0x180028dfa  mov     ebx, r9d
0x180028dfd  mov     rdi, rdx
0x180028e00  mov     rsi, rcx
0x180028e03  test    r10, r10
0x180028e06  jnz     short loc_180028E3C
0x180028e08  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180028e0d  test    eax, eax
0x180028e0f  jnz     short loc_180028E62
0x180028e11  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180028e18  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180028e1f  call    cs:__imp_GetProcAddress
0x180028e25  mov     cs:qword_1800703E0, rax
0x180028e2c  mov     r10, rax
0x180028e2f  test    rax, rax
0x180028e32  jnz     short loc_180028E3C
0x180028e34  call    cs:__imp_GetLastError
0x180028e3a  jmp     short loc_180028E62
0x180028e3c  mov     eax, [rsp+48h+arg_28]
0x180028e40  mov     r9d, ebx
0x180028e43  mov     [rsp+48h+var_20], eax
0x180028e47  xor     r8d, r8d
0x180028e4a  mov     rax, [rsp+48h+arg_20]
0x180028e4f  mov     rdx, rdi
0x180028e52  mov     [rsp+48h+var_28], rax
0x180028e57  mov     rcx, rsi
0x180028e5a  mov     rax, r10
0x180028e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e62  mov     rbx, [rsp+48h+arg_0]
0x180028e67  mov     rsi, [rsp+48h+arg_8]
0x180028e6c  add     rsp, 40h
0x180028e70  pop     rdi
0x180028e71  retn
```
