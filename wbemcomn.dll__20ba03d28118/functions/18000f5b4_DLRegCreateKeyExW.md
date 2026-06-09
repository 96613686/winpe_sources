# DLRegCreateKeyExW

- ea: `0x18000f5b4`
- end: `0x18000f65c`
- name: `DLRegCreateKeyExW`
- size: `168`
- prototype: `DWORD __fastcall(__int64, __int64, __int64, __int64, int, int, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f560`
- `0x18002cec0`
- `0x1800349a0`
- `0x180037950`
- `0x180037b20`

## callees

- `0x18000f5b4`
- `0x1800101cc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f654`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f5e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f5e7`

## string_xrefs

- `0x18000f5e0`: `RegCreateKeyExW`

## pseudocode

```c
DWORD __fastcall DLRegCreateKeyExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD, _QWORD, int, int, _QWORD, __int64, __int64); // r10
  DWORD result; // eax

  v9 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, int, _QWORD, __int64, __int64))qword_1800703E8;
  if ( !qword_1800703E8 )
  {
    result = DLpLoadRegistryDll();
    if ( result )
      return result;
    qword_1800703E8 = (__int64)GetProcAddress(g_hInstRegistryDLL, "RegCreateKeyExW");
    v9 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, int, _QWORD, __int64, __int64))qword_1800703E8;
    if ( !qword_1800703E8 )
      return GetLastError();
  }
  return v9(a1, a2, 0, 0, a5, a6, 0, a8, a9);
}

```

## disassembly

```asm
0x18000f5b4  mov     [rsp+arg_0], rbx
0x18000f5b9  push    rdi
0x18000f5ba  sub     rsp, 50h
0x18000f5be  mov     r10, cs:qword_1800703E8
0x18000f5c5  mov     rbx, rdx
0x18000f5c8  mov     rdi, rcx
0x18000f5cb  test    r10, r10
0x18000f5ce  jnz     short loc_18000F5FC
0x18000f5d0  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18000f5d5  test    eax, eax
0x18000f5d7  jnz     short loc_18000F649
0x18000f5d9  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000f5e0  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18000f5e7  call    cs:__imp_GetProcAddress
0x18000f5ed  mov     cs:qword_1800703E8, rax
0x18000f5f4  mov     r10, rax
0x18000f5f7  test    rax, rax
0x18000f5fa  jz      short loc_18000F654
0x18000f5fc  mov     rax, [rsp+58h+arg_40]
0x18000f604  xor     r9d, r9d
0x18000f607  mov     [rsp+58h+var_18], rax
0x18000f60c  xor     r8d, r8d
0x18000f60f  mov     rax, [rsp+58h+arg_38]
0x18000f617  mov     rdx, rbx
0x18000f61a  mov     [rsp+58h+var_20], rax
0x18000f61f  mov     rcx, rdi
0x18000f622  mov     eax, [rsp+58h+arg_28]
0x18000f629  mov     [rsp+58h+var_28], 0
0x18000f632  mov     [rsp+58h+var_30], eax
0x18000f636  mov     eax, [rsp+58h+arg_20]
0x18000f63d  mov     [rsp+58h+var_38], eax
0x18000f641  mov     rax, r10
0x18000f644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f649  mov     rbx, [rsp+58h+arg_0]
0x18000f64e  add     rsp, 50h
0x18000f652  pop     rdi
0x18000f653  retn
0x18000f654  call    cs:__imp_GetLastError
0x18000f65a  jmp     short loc_18000F649
```
