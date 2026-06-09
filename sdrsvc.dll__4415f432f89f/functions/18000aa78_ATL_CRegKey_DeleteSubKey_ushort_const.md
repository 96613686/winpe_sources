# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000aa78`
- end: `0x18000ab2c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180009930`
- `0x18000b718`
- `0x18000c254`

## callees

- `0x18000aa78`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000aaca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000aaca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aa9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aadf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab1b`

## string_xrefs

- `0x18000aa96`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000aaa8`: `RegDeleteKeyExW`
- `0x18000aac1`: `advapi32.dll`
- `0x18000aad5`: `RegDeleteKeyW`

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
0x18000aa78  mov     [rsp+arg_0], rbx
0x18000aa7d  push    rdi
0x18000aa7e  sub     rsp, 30h
0x18000aa82  cmp     qword ptr [rcx+8], 0
0x18000aa87  mov     rdi, rdx
0x18000aa8a  mov     rbx, rcx
0x18000aa8d  jnz     short loc_18000AAE9
0x18000aa8f  cmp     qword ptr [rcx+10h], 0
0x18000aa94  jnz     short loc_18000AAE9
0x18000aa96  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000aa9d  call    cs:__imp_GetModuleHandleW
0x18000aaa3  test    rax, rax
0x18000aaa6  jz      short loc_18000AABE
0x18000aaa8  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000aaaf  mov     rcx, rax; hModule
0x18000aab2  call    cs:__imp_GetProcAddress
0x18000aab8  mov     [rbx+8], rax
0x18000aabc  jmp     short loc_18000AAE9
0x18000aabe  xor     r8d, r8d; dwFlags
0x18000aac1  lea     rcx, LibFileName; "advapi32.dll"
0x18000aac8  xor     edx, edx; hFile
0x18000aaca  call    cs:__imp_LoadLibraryExW
0x18000aad0  test    rax, rax
0x18000aad3  jz      short loc_18000AAE9
0x18000aad5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000aadc  mov     rcx, rax; hModule
0x18000aadf  call    cs:__imp_GetProcAddress
0x18000aae5  mov     [rbx+10h], rax
0x18000aae9  mov     rax, [rbx+8]
0x18000aaed  test    rax, rax
0x18000aaf0  jz      short loc_18000AB05
0x18000aaf2  mov     rcx, [rbx]
0x18000aaf5  xor     r9d, r9d
0x18000aaf8  xor     r8d, r8d
0x18000aafb  mov     rdx, rdi
0x18000aafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab03  jmp     short loc_18000AB21
0x18000ab05  mov     rax, [rbx+10h]
0x18000ab09  test    rax, rax
0x18000ab0c  jz      short loc_18000AB1B
0x18000ab0e  mov     rcx, [rbx]
0x18000ab11  mov     rdx, rdi
0x18000ab14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab19  jmp     short loc_18000AB21
0x18000ab1b  call    cs:__imp_GetLastError
0x18000ab21  mov     rbx, [rsp+38h+arg_0]
0x18000ab26  add     rsp, 30h
0x18000ab2a  pop     rdi
0x18000ab2b  retn
```
