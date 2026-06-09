# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18003c95c`
- end: `0x18003ca11`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18003c3b0`

## callees

- `0x18003c95c`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c981`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c981`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c996`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c996`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c9c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c9ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9ff`

## string_xrefs

- `0x18003c97a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18003c98c`: `RegDeleteKeyExW`
- `0x18003c9a7`: `advapi32.dll`
- `0x18003c9b9`: `RegDeleteKeyW`

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
0x18003c95c  mov     [rsp+arg_0], rbx
0x18003c961  push    rdi
0x18003c962  sub     rsp, 30h
0x18003c966  mov     rdi, rdx
0x18003c969  mov     rbx, rcx
0x18003c96c  cmp     qword ptr [rcx+8], 0
0x18003c971  jnz     short loc_18003C9CD
0x18003c973  cmp     qword ptr [rcx+10h], 0
0x18003c978  jnz     short loc_18003C9CD
0x18003c97a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18003c981  call    cs:__imp_GetModuleHandleW
0x18003c987  test    rax, rax
0x18003c98a  jz      short loc_18003C9A2
0x18003c98c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18003c993  mov     rcx, rax; hModule
0x18003c996  call    cs:__imp_GetProcAddress
0x18003c99c  mov     [rbx+8], rax
0x18003c9a0  jmp     short loc_18003C9CD
0x18003c9a2  xor     r8d, r8d; dwFlags
0x18003c9a5  xor     edx, edx; hFile
0x18003c9a7  lea     rcx, LibFileName; "advapi32.dll"
0x18003c9ae  call    cs:__imp_LoadLibraryExW
0x18003c9b4  test    rax, rax
0x18003c9b7  jz      short loc_18003C9CD
0x18003c9b9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18003c9c0  mov     rcx, rax; hModule
0x18003c9c3  call    cs:__imp_GetProcAddress
0x18003c9c9  mov     [rbx+10h], rax
0x18003c9cd  mov     rax, [rbx+8]
0x18003c9d1  test    rax, rax
0x18003c9d4  jz      short loc_18003C9E9
0x18003c9d6  xor     r9d, r9d
0x18003c9d9  xor     r8d, r8d
0x18003c9dc  mov     rdx, rdi
0x18003c9df  mov     rcx, [rbx]
0x18003c9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9e7  jmp     short loc_18003CA06
0x18003c9e9  mov     rax, [rbx+10h]
0x18003c9ed  test    rax, rax
0x18003c9f0  jz      short loc_18003C9FF
0x18003c9f2  mov     rdx, rdi
0x18003c9f5  mov     rcx, [rbx]
0x18003c9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9fd  jmp     short loc_18003CA06
0x18003c9ff  call    cs:__imp_GetLastError
0x18003ca05  nop
0x18003ca06  mov     rbx, [rsp+38h+arg_0]
0x18003ca0b  add     rsp, 30h
0x18003ca0f  pop     rdi
0x18003ca10  retn
```
