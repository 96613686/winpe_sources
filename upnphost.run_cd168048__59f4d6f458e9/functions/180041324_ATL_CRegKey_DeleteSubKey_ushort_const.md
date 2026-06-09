# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180041324`
- end: `0x1800413f7`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `211`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180043f38`
- `0x18004442c`

## callees

- `0x180041324`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041364`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004139d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041364`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004139d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041382`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041382`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041349`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413df`

## string_xrefs

- `0x180041342`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18004135a`: `RegDeleteKeyExW`
- `0x180041379`: `advapi32.dll`
- `0x180041393`: `RegDeleteKeyW`

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
0x180041324  mov     [rsp+arg_0], rbx
0x180041329  push    rdi
0x18004132a  sub     rsp, 30h
0x18004132e  cmp     qword ptr [rcx+8], 0
0x180041333  mov     rdi, rdx
0x180041336  mov     rbx, rcx
0x180041339  jnz     short loc_1800413AD
0x18004133b  cmp     qword ptr [rcx+10h], 0
0x180041340  jnz     short loc_1800413AD
0x180041342  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180041349  call    cs:__imp_GetModuleHandleW
0x180041350  nop     dword ptr [rax+rax+00h]
0x180041355  test    rax, rax
0x180041358  jz      short loc_180041376
0x18004135a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180041361  mov     rcx, rax; hModule
0x180041364  call    cs:__imp_GetProcAddress
0x18004136b  nop     dword ptr [rax+rax+00h]
0x180041370  mov     [rbx+8], rax
0x180041374  jmp     short loc_1800413AD
0x180041376  xor     r8d, r8d; dwFlags
0x180041379  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180041380  xor     edx, edx; hFile
0x180041382  call    cs:__imp_LoadLibraryExW
0x180041389  nop     dword ptr [rax+rax+00h]
0x18004138e  test    rax, rax
0x180041391  jz      short loc_1800413AD
0x180041393  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18004139a  mov     rcx, rax; hModule
0x18004139d  call    cs:__imp_GetProcAddress
0x1800413a4  nop     dword ptr [rax+rax+00h]
0x1800413a9  mov     [rbx+10h], rax
0x1800413ad  mov     rax, [rbx+8]
0x1800413b1  test    rax, rax
0x1800413b4  jz      short loc_1800413C9
0x1800413b6  mov     rcx, [rbx]
0x1800413b9  xor     r9d, r9d
0x1800413bc  xor     r8d, r8d
0x1800413bf  mov     rdx, rdi
0x1800413c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413c7  jmp     short loc_1800413EB
0x1800413c9  mov     rax, [rbx+10h]
0x1800413cd  test    rax, rax
0x1800413d0  jz      short loc_1800413DF
0x1800413d2  mov     rcx, [rbx]
0x1800413d5  mov     rdx, rdi
0x1800413d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413dd  jmp     short loc_1800413EB
0x1800413df  call    cs:__imp_GetLastError
0x1800413e6  nop     dword ptr [rax+rax+00h]
0x1800413eb  mov     rbx, [rsp+38h+arg_0]
0x1800413f0  add     rsp, 30h
0x1800413f4  pop     rdi
0x1800413f5  retn
```
