# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180039620`
- end: `0x1800396d5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180039fc8`
- `0x18003a3fc`
- `0x18005b550`

## callees

- `0x180039620`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039672`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003965a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039687`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003965a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039687`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039645`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396c3`

## string_xrefs

- `0x18003963e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180039650`: `RegDeleteKeyExW`
- `0x18003966b`: `advapi32.dll`
- `0x18003967d`: `RegDeleteKeyW`

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
0x180039620  mov     [rsp+arg_0], rbx
0x180039625  push    rdi
0x180039626  sub     rsp, 30h
0x18003962a  mov     rdi, rdx
0x18003962d  mov     rbx, rcx
0x180039630  cmp     qword ptr [rcx+8], 0
0x180039635  jnz     short loc_180039691
0x180039637  cmp     qword ptr [rcx+10h], 0
0x18003963c  jnz     short loc_180039691
0x18003963e  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180039645  call    cs:__imp_GetModuleHandleW
0x18003964b  test    rax, rax
0x18003964e  jz      short loc_180039666
0x180039650  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180039657  mov     rcx, rax; hModule
0x18003965a  call    cs:__imp_GetProcAddress
0x180039660  mov     [rbx+8], rax
0x180039664  jmp     short loc_180039691
0x180039666  xor     r8d, r8d; dwFlags
0x180039669  xor     edx, edx; hFile
0x18003966b  lea     rcx, LibFileName; "advapi32.dll"
0x180039672  call    cs:__imp_LoadLibraryExW
0x180039678  test    rax, rax
0x18003967b  jz      short loc_180039691
0x18003967d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180039684  mov     rcx, rax; hModule
0x180039687  call    cs:__imp_GetProcAddress
0x18003968d  mov     [rbx+10h], rax
0x180039691  mov     rax, [rbx+8]
0x180039695  test    rax, rax
0x180039698  jz      short loc_1800396AD
0x18003969a  xor     r9d, r9d
0x18003969d  xor     r8d, r8d
0x1800396a0  mov     rdx, rdi
0x1800396a3  mov     rcx, [rbx]
0x1800396a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396ab  jmp     short loc_1800396CA
0x1800396ad  mov     rax, [rbx+10h]
0x1800396b1  test    rax, rax
0x1800396b4  jz      short loc_1800396C3
0x1800396b6  mov     rdx, rdi
0x1800396b9  mov     rcx, [rbx]
0x1800396bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396c1  jmp     short loc_1800396CA
0x1800396c3  call    cs:__imp_GetLastError
0x1800396c9  nop
0x1800396ca  mov     rbx, [rsp+38h+arg_0]
0x1800396cf  add     rsp, 30h
0x1800396d3  pop     rdi
0x1800396d4  retn
```
