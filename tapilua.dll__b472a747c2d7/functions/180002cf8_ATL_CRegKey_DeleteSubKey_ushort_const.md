# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180002cf8`
- end: `0x180002dac`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003398`
- `0x1800038f0`

## callees

- `0x180002cf8`
- `0x180006010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180002d1d`
- `KERNEL32!GetModuleHandleW` at `0x180002d1d`
- `KERNEL32!LoadLibraryExW` at `0x180002d4a`
- `KERNEL32!LoadLibraryExW` at `0x180002d4a`
- `KERNEL32!GetProcAddress` at `0x180002d32`
- `KERNEL32!GetProcAddress` at `0x180002d5f`
- `KERNEL32!GetProcAddress` at `0x180002d32`
- `KERNEL32!GetProcAddress` at `0x180002d5f`
- `KERNEL32!GetLastError` at `0x180002d9b`
- `KERNEL32!GetLastError` at `0x180002d9b`

## string_xrefs

- `0x180002d16`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180002d28`: `RegDeleteKeyExW`
- `0x180002d41`: `advapi32.dll`
- `0x180002d55`: `RegDeleteKeyW`

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
0x180002cf8  mov     [rsp+arg_0], rbx
0x180002cfd  push    rdi
0x180002cfe  sub     rsp, 30h
0x180002d02  cmp     qword ptr [rcx+8], 0
0x180002d07  mov     rdi, rdx
0x180002d0a  mov     rbx, rcx
0x180002d0d  jnz     short loc_180002D69
0x180002d0f  cmp     qword ptr [rcx+10h], 0
0x180002d14  jnz     short loc_180002D69
0x180002d16  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180002d1d  call    cs:__imp_GetModuleHandleW
0x180002d23  test    rax, rax
0x180002d26  jz      short loc_180002D3E
0x180002d28  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180002d2f  mov     rcx, rax; hModule
0x180002d32  call    cs:__imp_GetProcAddress
0x180002d38  mov     [rbx+8], rax
0x180002d3c  jmp     short loc_180002D69
0x180002d3e  xor     r8d, r8d; dwFlags
0x180002d41  lea     rcx, LibFileName; "advapi32.dll"
0x180002d48  xor     edx, edx; hFile
0x180002d4a  call    cs:__imp_LoadLibraryExW
0x180002d50  test    rax, rax
0x180002d53  jz      short loc_180002D69
0x180002d55  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180002d5c  mov     rcx, rax; hModule
0x180002d5f  call    cs:__imp_GetProcAddress
0x180002d65  mov     [rbx+10h], rax
0x180002d69  mov     rax, [rbx+8]
0x180002d6d  test    rax, rax
0x180002d70  jz      short loc_180002D85
0x180002d72  mov     rcx, [rbx]
0x180002d75  xor     r9d, r9d
0x180002d78  xor     r8d, r8d
0x180002d7b  mov     rdx, rdi
0x180002d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d83  jmp     short loc_180002DA1
0x180002d85  mov     rax, [rbx+10h]
0x180002d89  test    rax, rax
0x180002d8c  jz      short loc_180002D9B
0x180002d8e  mov     rcx, [rbx]
0x180002d91  mov     rdx, rdi
0x180002d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d99  jmp     short loc_180002DA1
0x180002d9b  call    cs:__imp_GetLastError
0x180002da1  mov     rbx, [rsp+38h+arg_0]
0x180002da6  add     rsp, 30h
0x180002daa  pop     rdi
0x180002dab  retn
```
