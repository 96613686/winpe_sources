# DLRegOpenKeyExW

- ea: `0x18000fa30`
- end: `0x18000fab6`
- name: `DLRegOpenKeyExW`
- size: `134`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f990`
- `0x18000fac0`
- `0x18001e2b0`
- `0x1800290f0`
- `0x18002c310`
- `0x180034e00`

## callees

- `0x18000fa30`
- `0x1800101cc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fa99`

## string_xrefs

- `0x18000fa92`: `RegOpenKeyExW`

## pseudocode

```c
DWORD __fastcall DLRegOpenKeyExW(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 (__fastcall *v5)(__int64, __int64, _QWORD, _QWORD, __int64); // r10
  DWORD result; // eax

  v5 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64))qword_1800703C0;
  if ( qword_1800703C0 )
    return v5(a1, a2, 0, a4, a5);
  result = DLpLoadRegistryDll();
  if ( !result )
  {
    qword_1800703C0 = (__int64)GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
    v5 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64))qword_1800703C0;
    if ( !qword_1800703C0 )
      return GetLastError();
    return v5(a1, a2, 0, a4, a5);
  }
  return result;
}

```

## disassembly

```asm
0x18000fa30  mov     [rsp+arg_0], rbx
0x18000fa35  mov     [rsp+arg_8], rsi
0x18000fa3a  push    rdi
0x18000fa3b  sub     rsp, 30h
0x18000fa3f  mov     r10, cs:qword_1800703C0
0x18000fa46  mov     ebx, r9d
0x18000fa49  mov     rdi, rdx
0x18000fa4c  mov     rsi, rcx
0x18000fa4f  test    r10, r10
0x18000fa52  jz      short loc_18000FA82
0x18000fa54  mov     rax, [rsp+38h+arg_20]
0x18000fa59  mov     r9d, ebx
0x18000fa5c  mov     [rsp+38h+var_18], rax
0x18000fa61  xor     r8d, r8d
0x18000fa64  mov     rax, r10
0x18000fa67  mov     rdx, rdi
0x18000fa6a  mov     rcx, rsi
0x18000fa6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa72  mov     rbx, [rsp+38h+arg_0]
0x18000fa77  mov     rsi, [rsp+38h+arg_8]
0x18000fa7c  add     rsp, 30h
0x18000fa80  pop     rdi
0x18000fa81  retn
0x18000fa82  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18000fa87  test    eax, eax
0x18000fa89  jnz     short loc_18000FA72
0x18000fa8b  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000fa92  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000fa99  call    cs:__imp_GetProcAddress
0x18000fa9f  mov     cs:qword_1800703C0, rax
0x18000faa6  mov     r10, rax
0x18000faa9  test    rax, rax
0x18000faac  jnz     short loc_18000FA54
0x18000faae  call    cs:__imp_GetLastError
0x18000fab4  jmp     short loc_18000FA72
```
