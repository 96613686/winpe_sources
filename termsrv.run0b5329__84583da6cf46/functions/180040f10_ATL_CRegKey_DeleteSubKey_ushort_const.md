# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180040f10`
- end: `0x180040fc5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180048c30`
- `0x180049454`

## callees

- `0x180040f10`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040f35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040f35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180040f62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180040f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040fb3`

## string_xrefs

- `0x180040f2e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180040f40`: `RegDeleteKeyExW`
- `0x180040f5b`: `advapi32.dll`
- `0x180040f6d`: `RegDeleteKeyW`

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
0x180040f10  mov     [rsp+arg_0], rbx
0x180040f15  push    rdi
0x180040f16  sub     rsp, 30h
0x180040f1a  mov     rdi, rdx
0x180040f1d  mov     rbx, rcx
0x180040f20  cmp     qword ptr [rcx+8], 0
0x180040f25  jnz     short loc_180040F81
0x180040f27  cmp     qword ptr [rcx+10h], 0
0x180040f2c  jnz     short loc_180040F81
0x180040f2e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180040f35  call    cs:__imp_GetModuleHandleW
0x180040f3b  test    rax, rax
0x180040f3e  jz      short loc_180040F56
0x180040f40  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180040f47  mov     rcx, rax; hModule
0x180040f4a  call    cs:__imp_GetProcAddress
0x180040f50  mov     [rbx+8], rax
0x180040f54  jmp     short loc_180040F81
0x180040f56  xor     r8d, r8d; dwFlags
0x180040f59  xor     edx, edx; hFile
0x180040f5b  lea     rcx, LibFileName; "advapi32.dll"
0x180040f62  call    cs:__imp_LoadLibraryExW
0x180040f68  test    rax, rax
0x180040f6b  jz      short loc_180040F81
0x180040f6d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180040f74  mov     rcx, rax; hModule
0x180040f77  call    cs:__imp_GetProcAddress
0x180040f7d  mov     [rbx+10h], rax
0x180040f81  mov     rax, [rbx+8]
0x180040f85  test    rax, rax
0x180040f88  jz      short loc_180040F9D
0x180040f8a  xor     r9d, r9d
0x180040f8d  xor     r8d, r8d
0x180040f90  mov     rdx, rdi
0x180040f93  mov     rcx, [rbx]
0x180040f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f9b  jmp     short loc_180040FBA
0x180040f9d  mov     rax, [rbx+10h]
0x180040fa1  test    rax, rax
0x180040fa4  jz      short loc_180040FB3
0x180040fa6  mov     rdx, rdi
0x180040fa9  mov     rcx, [rbx]
0x180040fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fb1  jmp     short loc_180040FBA
0x180040fb3  call    cs:__imp_GetLastError
0x180040fb9  nop
0x180040fba  mov     rbx, [rsp+38h+arg_0]
0x180040fbf  add     rsp, 30h
0x180040fc3  pop     rdi
0x180040fc4  retn
```
