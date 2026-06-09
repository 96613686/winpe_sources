# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006cac`
- end: `0x180006d61`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180006598`
- `0x1800073c8`
- `0x1800078ec`

## callees

- `0x180006cac`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ce6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ce6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006d13`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006cfe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006cd1`

## string_xrefs

- `0x180006cf7`: `advapi32.dll`
- `0x180006cca`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006cdc`: `RegDeleteKeyExW`
- `0x180006d09`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180006cac  mov     [rsp+arg_0], rbx
0x180006cb1  push    rdi
0x180006cb2  sub     rsp, 30h
0x180006cb6  mov     rdi, rdx
0x180006cb9  mov     rbx, rcx
0x180006cbc  cmp     qword ptr [rcx+8], 0
0x180006cc1  jnz     short loc_180006D1D
0x180006cc3  cmp     qword ptr [rcx+10h], 0
0x180006cc8  jnz     short loc_180006D1D
0x180006cca  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180006cd1  call    cs:__imp_GetModuleHandleW
0x180006cd7  test    rax, rax
0x180006cda  jz      short loc_180006CF2
0x180006cdc  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180006ce3  mov     rcx, rax; hModule
0x180006ce6  call    cs:__imp_GetProcAddress
0x180006cec  mov     [rbx+8], rax
0x180006cf0  jmp     short loc_180006D1D
0x180006cf2  xor     r8d, r8d; dwFlags
0x180006cf5  xor     edx, edx; hFile
0x180006cf7  lea     rcx, LibFileName; "advapi32.dll"
0x180006cfe  call    cs:__imp_LoadLibraryExW
0x180006d04  test    rax, rax
0x180006d07  jz      short loc_180006D1D
0x180006d09  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180006d10  mov     rcx, rax; hModule
0x180006d13  call    cs:__imp_GetProcAddress
0x180006d19  mov     [rbx+10h], rax
0x180006d1d  mov     rax, [rbx+8]
0x180006d21  test    rax, rax
0x180006d24  jz      short loc_180006D39
0x180006d26  xor     r9d, r9d
0x180006d29  xor     r8d, r8d
0x180006d2c  mov     rdx, rdi
0x180006d2f  mov     rcx, [rbx]
0x180006d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d37  jmp     short loc_180006D56
0x180006d39  mov     rax, [rbx+10h]
0x180006d3d  test    rax, rax
0x180006d40  jz      short loc_180006D4F
0x180006d42  mov     rdx, rdi
0x180006d45  mov     rcx, [rbx]
0x180006d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4d  jmp     short loc_180006D56
0x180006d4f  call    cs:__imp_GetLastError
0x180006d55  nop
0x180006d56  mov     rbx, [rsp+38h+arg_0]
0x180006d5b  add     rsp, 30h
0x180006d5f  pop     rdi
0x180006d60  retn
```
