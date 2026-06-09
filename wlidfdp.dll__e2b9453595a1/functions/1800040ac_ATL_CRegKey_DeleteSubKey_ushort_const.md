# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800040ac`
- end: `0x180004161`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003ae0`

## callees

- `0x1800040ac`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800040d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800040d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800040fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800040fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004113`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000414f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000414f`

## string_xrefs

- `0x1800040ca`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800040dc`: `RegDeleteKeyExW`
- `0x1800040f7`: `advapi32.dll`
- `0x180004109`: `RegDeleteKeyW`

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
0x1800040ac  mov     [rsp+arg_0], rbx
0x1800040b1  push    rdi
0x1800040b2  sub     rsp, 30h
0x1800040b6  mov     rdi, rdx
0x1800040b9  mov     rbx, rcx
0x1800040bc  cmp     qword ptr [rcx+8], 0
0x1800040c1  jnz     short loc_18000411D
0x1800040c3  cmp     qword ptr [rcx+10h], 0
0x1800040c8  jnz     short loc_18000411D
0x1800040ca  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800040d1  call    cs:__imp_GetModuleHandleW
0x1800040d7  test    rax, rax
0x1800040da  jz      short loc_1800040F2
0x1800040dc  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800040e3  mov     rcx, rax; hModule
0x1800040e6  call    cs:__imp_GetProcAddress
0x1800040ec  mov     [rbx+8], rax
0x1800040f0  jmp     short loc_18000411D
0x1800040f2  xor     r8d, r8d; dwFlags
0x1800040f5  xor     edx, edx; hFile
0x1800040f7  lea     rcx, LibFileName; "advapi32.dll"
0x1800040fe  call    cs:__imp_LoadLibraryExW
0x180004104  test    rax, rax
0x180004107  jz      short loc_18000411D
0x180004109  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004110  mov     rcx, rax; hModule
0x180004113  call    cs:__imp_GetProcAddress
0x180004119  mov     [rbx+10h], rax
0x18000411d  mov     rax, [rbx+8]
0x180004121  test    rax, rax
0x180004124  jz      short loc_180004139
0x180004126  xor     r9d, r9d
0x180004129  xor     r8d, r8d
0x18000412c  mov     rdx, rdi
0x18000412f  mov     rcx, [rbx]
0x180004132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004137  jmp     short loc_180004156
0x180004139  mov     rax, [rbx+10h]
0x18000413d  test    rax, rax
0x180004140  jz      short loc_18000414F
0x180004142  mov     rdx, rdi
0x180004145  mov     rcx, [rbx]
0x180004148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414d  jmp     short loc_180004156
0x18000414f  call    cs:__imp_GetLastError
0x180004155  nop
0x180004156  mov     rbx, [rsp+38h+arg_0]
0x18000415b  add     rsp, 30h
0x18000415f  pop     rdi
0x180004160  retn
```
