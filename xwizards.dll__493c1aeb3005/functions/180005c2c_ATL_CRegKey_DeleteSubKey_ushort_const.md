# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180005c2c`
- end: `0x180005ce1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180007478`
- `0x1800078b0`

## callees

- `0x180005c2c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005c7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005c7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ccf`

## string_xrefs

- `0x180005c4a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180005c5c`: `RegDeleteKeyExW`
- `0x180005c77`: `advapi32.dll`
- `0x180005c89`: `RegDeleteKeyW`

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
0x180005c2c  mov     [rsp+arg_0], rbx
0x180005c31  push    rdi
0x180005c32  sub     rsp, 30h
0x180005c36  mov     rdi, rdx
0x180005c39  mov     rbx, rcx
0x180005c3c  cmp     qword ptr [rcx+8], 0
0x180005c41  jnz     short loc_180005C9D
0x180005c43  cmp     qword ptr [rcx+10h], 0
0x180005c48  jnz     short loc_180005C9D
0x180005c4a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180005c51  call    cs:__imp_GetModuleHandleW
0x180005c57  test    rax, rax
0x180005c5a  jz      short loc_180005C72
0x180005c5c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180005c63  mov     rcx, rax; hModule
0x180005c66  call    cs:__imp_GetProcAddress
0x180005c6c  mov     [rbx+8], rax
0x180005c70  jmp     short loc_180005C9D
0x180005c72  xor     r8d, r8d; dwFlags
0x180005c75  xor     edx, edx; hFile
0x180005c77  lea     rcx, LibFileName; "advapi32.dll"
0x180005c7e  call    cs:__imp_LoadLibraryExW
0x180005c84  test    rax, rax
0x180005c87  jz      short loc_180005C9D
0x180005c89  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180005c90  mov     rcx, rax; hModule
0x180005c93  call    cs:__imp_GetProcAddress
0x180005c99  mov     [rbx+10h], rax
0x180005c9d  mov     rax, [rbx+8]
0x180005ca1  test    rax, rax
0x180005ca4  jz      short loc_180005CB9
0x180005ca6  xor     r9d, r9d
0x180005ca9  xor     r8d, r8d
0x180005cac  mov     rdx, rdi
0x180005caf  mov     rcx, [rbx]
0x180005cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb7  jmp     short loc_180005CD6
0x180005cb9  mov     rax, [rbx+10h]
0x180005cbd  test    rax, rax
0x180005cc0  jz      short loc_180005CCF
0x180005cc2  mov     rdx, rdi
0x180005cc5  mov     rcx, [rbx]
0x180005cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ccd  jmp     short loc_180005CD6
0x180005ccf  call    cs:__imp_GetLastError
0x180005cd5  nop
0x180005cd6  mov     rbx, [rsp+38h+arg_0]
0x180005cdb  add     rsp, 30h
0x180005cdf  pop     rdi
0x180005ce0  retn
```
