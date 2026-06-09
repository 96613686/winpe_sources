# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1801f4430`
- end: `0x1801f44e5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1801f3510`
- `0x1801f51e4`
- `0x1801f56c8`

## callees

- `0x1801f4430`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f4482`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f4482`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801f4455`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801f4455`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f446a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f4497`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f446a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f4497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f44d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f44d3`

## string_xrefs

- `0x1801f444e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1801f4460`: `RegDeleteKeyExW`
- `0x1801f447b`: `advapi32.dll`
- `0x1801f448d`: `RegDeleteKeyW`

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
0x1801f4430  mov     [rsp+arg_0], rbx
0x1801f4435  push    rdi
0x1801f4436  sub     rsp, 30h
0x1801f443a  mov     rdi, rdx
0x1801f443d  mov     rbx, rcx
0x1801f4440  cmp     qword ptr [rcx+8], 0
0x1801f4445  jnz     short loc_1801F44A1
0x1801f4447  cmp     qword ptr [rcx+10h], 0
0x1801f444c  jnz     short loc_1801F44A1
0x1801f444e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1801f4455  call    cs:__imp_GetModuleHandleW
0x1801f445b  test    rax, rax
0x1801f445e  jz      short loc_1801F4476
0x1801f4460  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1801f4467  mov     rcx, rax; hModule
0x1801f446a  call    cs:__imp_GetProcAddress
0x1801f4470  mov     [rbx+8], rax
0x1801f4474  jmp     short loc_1801F44A1
0x1801f4476  xor     r8d, r8d; dwFlags
0x1801f4479  xor     edx, edx; hFile
0x1801f447b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1801f4482  call    cs:__imp_LoadLibraryExW
0x1801f4488  test    rax, rax
0x1801f448b  jz      short loc_1801F44A1
0x1801f448d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1801f4494  mov     rcx, rax; hModule
0x1801f4497  call    cs:__imp_GetProcAddress
0x1801f449d  mov     [rbx+10h], rax
0x1801f44a1  mov     rax, [rbx+8]
0x1801f44a5  test    rax, rax
0x1801f44a8  jz      short loc_1801F44BD
0x1801f44aa  xor     r9d, r9d
0x1801f44ad  xor     r8d, r8d
0x1801f44b0  mov     rdx, rdi
0x1801f44b3  mov     rcx, [rbx]
0x1801f44b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f44bb  jmp     short loc_1801F44DA
0x1801f44bd  mov     rax, [rbx+10h]
0x1801f44c1  test    rax, rax
0x1801f44c4  jz      short loc_1801F44D3
0x1801f44c6  mov     rdx, rdi
0x1801f44c9  mov     rcx, [rbx]
0x1801f44cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f44d1  jmp     short loc_1801F44DA
0x1801f44d3  call    cs:__imp_GetLastError
0x1801f44d9  nop
0x1801f44da  mov     rbx, [rsp+38h+arg_0]
0x1801f44df  add     rsp, 30h
0x1801f44e3  pop     rdi
0x1801f44e4  retn
```
