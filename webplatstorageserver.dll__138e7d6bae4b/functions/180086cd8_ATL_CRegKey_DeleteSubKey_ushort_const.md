# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180086cd8`
- end: `0x180086d8d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180086578`
- `0x1800874e8`
- `0x1800879c4`

## callees

- `0x180086cd8`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180086cfd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180086cfd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180086d12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180086d3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180086d12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180086d3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180086d2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180086d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d7b`

## string_xrefs

- `0x180086cf6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180086d08`: `RegDeleteKeyExW`
- `0x180086d23`: `advapi32.dll`
- `0x180086d35`: `RegDeleteKeyW`

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
0x180086cd8  mov     [rsp+arg_0], rbx
0x180086cdd  push    rdi
0x180086cde  sub     rsp, 30h
0x180086ce2  mov     rdi, rdx
0x180086ce5  mov     rbx, rcx
0x180086ce8  cmp     qword ptr [rcx+8], 0
0x180086ced  jnz     short loc_180086D49
0x180086cef  cmp     qword ptr [rcx+10h], 0
0x180086cf4  jnz     short loc_180086D49
0x180086cf6  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180086cfd  call    cs:__imp_GetModuleHandleW
0x180086d03  test    rax, rax
0x180086d06  jz      short loc_180086D1E
0x180086d08  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180086d0f  mov     rcx, rax; hModule
0x180086d12  call    cs:__imp_GetProcAddress
0x180086d18  mov     [rbx+8], rax
0x180086d1c  jmp     short loc_180086D49
0x180086d1e  xor     r8d, r8d; dwFlags
0x180086d21  xor     edx, edx; hFile
0x180086d23  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180086d2a  call    cs:__imp_LoadLibraryExW
0x180086d30  test    rax, rax
0x180086d33  jz      short loc_180086D49
0x180086d35  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180086d3c  mov     rcx, rax; hModule
0x180086d3f  call    cs:__imp_GetProcAddress
0x180086d45  mov     [rbx+10h], rax
0x180086d49  mov     rax, [rbx+8]
0x180086d4d  test    rax, rax
0x180086d50  jz      short loc_180086D65
0x180086d52  xor     r9d, r9d
0x180086d55  xor     r8d, r8d
0x180086d58  mov     rdx, rdi
0x180086d5b  mov     rcx, [rbx]
0x180086d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d63  jmp     short loc_180086D82
0x180086d65  mov     rax, [rbx+10h]
0x180086d69  test    rax, rax
0x180086d6c  jz      short loc_180086D7B
0x180086d6e  mov     rdx, rdi
0x180086d71  mov     rcx, [rbx]
0x180086d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d79  jmp     short loc_180086D82
0x180086d7b  call    cs:__imp_GetLastError
0x180086d81  nop
0x180086d82  mov     rbx, [rsp+38h+arg_0]
0x180086d87  add     rsp, 30h
0x180086d8b  pop     rdi
0x180086d8c  retn
```
