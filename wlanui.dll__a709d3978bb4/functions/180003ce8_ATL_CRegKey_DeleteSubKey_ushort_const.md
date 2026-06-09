# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180003ce8`
- end: `0x180003d9c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004548`
- `0x1800049ec`

## callees

- `0x180003ce8`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180003d22`
- `KERNEL32!GetProcAddress` at `0x180003d4f`
- `KERNEL32!GetProcAddress` at `0x180003d22`
- `KERNEL32!GetProcAddress` at `0x180003d4f`
- `KERNEL32!GetModuleHandleW` at `0x180003d0d`
- `KERNEL32!GetModuleHandleW` at `0x180003d0d`
- `KERNEL32!GetLastError` at `0x180003d8b`
- `KERNEL32!GetLastError` at `0x180003d8b`
- `KERNEL32!LoadLibraryExW` at `0x180003d3a`
- `KERNEL32!LoadLibraryExW` at `0x180003d3a`

## string_xrefs

- `0x180003d06`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003d18`: `RegDeleteKeyExW`
- `0x180003d31`: `advapi32.dll`
- `0x180003d45`: `RegDeleteKeyW`

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
0x180003ce8  mov     [rsp+arg_0], rbx
0x180003ced  push    rdi
0x180003cee  sub     rsp, 30h
0x180003cf2  cmp     qword ptr [rcx+8], 0
0x180003cf7  mov     rdi, rdx
0x180003cfa  mov     rbx, rcx
0x180003cfd  jnz     short loc_180003D59
0x180003cff  cmp     qword ptr [rcx+10h], 0
0x180003d04  jnz     short loc_180003D59
0x180003d06  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003d0d  call    cs:__imp_GetModuleHandleW
0x180003d13  test    rax, rax
0x180003d16  jz      short loc_180003D2E
0x180003d18  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180003d1f  mov     rcx, rax; hModule
0x180003d22  call    cs:__imp_GetProcAddress
0x180003d28  mov     [rbx+8], rax
0x180003d2c  jmp     short loc_180003D59
0x180003d2e  xor     r8d, r8d; dwFlags
0x180003d31  lea     rcx, LibFileName; "advapi32.dll"
0x180003d38  xor     edx, edx; hFile
0x180003d3a  call    cs:__imp_LoadLibraryExW
0x180003d40  test    rax, rax
0x180003d43  jz      short loc_180003D59
0x180003d45  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180003d4c  mov     rcx, rax; hModule
0x180003d4f  call    cs:__imp_GetProcAddress
0x180003d55  mov     [rbx+10h], rax
0x180003d59  mov     rax, [rbx+8]
0x180003d5d  test    rax, rax
0x180003d60  jz      short loc_180003D75
0x180003d62  mov     rcx, [rbx]
0x180003d65  xor     r9d, r9d
0x180003d68  xor     r8d, r8d
0x180003d6b  mov     rdx, rdi
0x180003d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d73  jmp     short loc_180003D91
0x180003d75  mov     rax, [rbx+10h]
0x180003d79  test    rax, rax
0x180003d7c  jz      short loc_180003D8B
0x180003d7e  mov     rcx, [rbx]
0x180003d81  mov     rdx, rdi
0x180003d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d89  jmp     short loc_180003D91
0x180003d8b  call    cs:__imp_GetLastError
0x180003d91  mov     rbx, [rsp+38h+arg_0]
0x180003d96  add     rsp, 30h
0x180003d9a  pop     rdi
0x180003d9b  retn
```
