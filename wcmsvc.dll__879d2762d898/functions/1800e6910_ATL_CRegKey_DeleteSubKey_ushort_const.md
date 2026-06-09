# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800e6910`
- end: `0x1800e69c5`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e6e40`

## callees

- `0x1800e6910`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e6962`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e6962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e694a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e6977`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e694a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e6977`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e6935`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e6935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e69b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e69b3`

## string_xrefs

- `0x1800e696d`: `RegDeleteKeyW`
- `0x1800e6940`: `RegDeleteKeyExW`
- `0x1800e695b`: `advapi32.dll`
- `0x1800e692e`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`

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
0x1800e6910  mov     [rsp+arg_0], rbx
0x1800e6915  push    rdi
0x1800e6916  sub     rsp, 30h
0x1800e691a  mov     rdi, rdx
0x1800e691d  mov     rbx, rcx
0x1800e6920  cmp     qword ptr [rcx+8], 0
0x1800e6925  jnz     short loc_1800E6981
0x1800e6927  cmp     qword ptr [rcx+10h], 0
0x1800e692c  jnz     short loc_1800E6981
0x1800e692e  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800e6935  call    cs:__imp_GetModuleHandleW
0x1800e693b  test    rax, rax
0x1800e693e  jz      short loc_1800E6956
0x1800e6940  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800e6947  mov     rcx, rax; hModule
0x1800e694a  call    cs:__imp_GetProcAddress
0x1800e6950  mov     [rbx+8], rax
0x1800e6954  jmp     short loc_1800E6981
0x1800e6956  xor     r8d, r8d; dwFlags
0x1800e6959  xor     edx, edx; hFile
0x1800e695b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800e6962  call    cs:__imp_LoadLibraryExW
0x1800e6968  test    rax, rax
0x1800e696b  jz      short loc_1800E6981
0x1800e696d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800e6974  mov     rcx, rax; hModule
0x1800e6977  call    cs:__imp_GetProcAddress
0x1800e697d  mov     [rbx+10h], rax
0x1800e6981  mov     rax, [rbx+8]
0x1800e6985  test    rax, rax
0x1800e6988  jz      short loc_1800E699D
0x1800e698a  xor     r9d, r9d
0x1800e698d  xor     r8d, r8d
0x1800e6990  mov     rdx, rdi
0x1800e6993  mov     rcx, [rbx]
0x1800e6996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e699b  jmp     short loc_1800E69BA
0x1800e699d  mov     rax, [rbx+10h]
0x1800e69a1  test    rax, rax
0x1800e69a4  jz      short loc_1800E69B3
0x1800e69a6  mov     rdx, rdi
0x1800e69a9  mov     rcx, [rbx]
0x1800e69ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e69b1  jmp     short loc_1800E69BA
0x1800e69b3  call    cs:__imp_GetLastError
0x1800e69b9  nop
0x1800e69ba  mov     rbx, [rsp+38h+arg_0]
0x1800e69bf  add     rsp, 30h
0x1800e69c3  pop     rdi
0x1800e69c4  retn
```
