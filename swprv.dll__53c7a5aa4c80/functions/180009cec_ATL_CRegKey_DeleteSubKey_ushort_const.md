# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180009cec`
- end: `0x180009da1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800090b0`
- `0x18000ba18`
- `0x18000bf80`

## callees

- `0x180009cec`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009d3e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009d3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d53`

## string_xrefs

- `0x180009d0a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180009d1c`: `RegDeleteKeyExW`
- `0x180009d37`: `advapi32.dll`
- `0x180009d49`: `RegDeleteKeyW`

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
0x180009cec  mov     [rsp+arg_0], rbx
0x180009cf1  push    rdi
0x180009cf2  sub     rsp, 30h
0x180009cf6  mov     rdi, rdx
0x180009cf9  mov     rbx, rcx
0x180009cfc  cmp     qword ptr [rcx+8], 0
0x180009d01  jnz     short loc_180009D5D
0x180009d03  cmp     qword ptr [rcx+10h], 0
0x180009d08  jnz     short loc_180009D5D
0x180009d0a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180009d11  call    cs:__imp_GetModuleHandleW
0x180009d17  test    rax, rax
0x180009d1a  jz      short loc_180009D32
0x180009d1c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180009d23  mov     rcx, rax; hModule
0x180009d26  call    cs:__imp_GetProcAddress
0x180009d2c  mov     [rbx+8], rax
0x180009d30  jmp     short loc_180009D5D
0x180009d32  xor     r8d, r8d; dwFlags
0x180009d35  xor     edx, edx; hFile
0x180009d37  lea     rcx, LibFileName; "advapi32.dll"
0x180009d3e  call    cs:__imp_LoadLibraryExW
0x180009d44  test    rax, rax
0x180009d47  jz      short loc_180009D5D
0x180009d49  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180009d50  mov     rcx, rax; hModule
0x180009d53  call    cs:__imp_GetProcAddress
0x180009d59  mov     [rbx+10h], rax
0x180009d5d  mov     rax, [rbx+8]
0x180009d61  test    rax, rax
0x180009d64  jz      short loc_180009D79
0x180009d66  xor     r9d, r9d
0x180009d69  xor     r8d, r8d
0x180009d6c  mov     rdx, rdi
0x180009d6f  mov     rcx, [rbx]
0x180009d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d77  jmp     short loc_180009D96
0x180009d79  mov     rax, [rbx+10h]
0x180009d7d  test    rax, rax
0x180009d80  jz      short loc_180009D8F
0x180009d82  mov     rdx, rdi
0x180009d85  mov     rcx, [rbx]
0x180009d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8d  jmp     short loc_180009D96
0x180009d8f  call    cs:__imp_GetLastError
0x180009d95  nop
0x180009d96  mov     rbx, [rsp+38h+arg_0]
0x180009d9b  add     rsp, 30h
0x180009d9f  pop     rdi
0x180009da0  retn
```
