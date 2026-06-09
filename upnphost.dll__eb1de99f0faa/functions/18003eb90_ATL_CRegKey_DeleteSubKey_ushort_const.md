# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18003eb90`
- end: `0x18003ec44`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004157c`
- `0x180041ab0`

## callees

- `0x18003eb90`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebf7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ebe2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ebe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ebb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ebb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec33`

## string_xrefs

- `0x18003ebae`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18003ebc0`: `RegDeleteKeyExW`
- `0x18003ebd9`: `advapi32.dll`
- `0x18003ebed`: `RegDeleteKeyW`

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
0x18003eb90  mov     [rsp+arg_0], rbx
0x18003eb95  push    rdi
0x18003eb96  sub     rsp, 30h
0x18003eb9a  cmp     qword ptr [rcx+8], 0
0x18003eb9f  mov     rdi, rdx
0x18003eba2  mov     rbx, rcx
0x18003eba5  jnz     short loc_18003EC01
0x18003eba7  cmp     qword ptr [rcx+10h], 0
0x18003ebac  jnz     short loc_18003EC01
0x18003ebae  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18003ebb5  call    cs:__imp_GetModuleHandleW
0x18003ebbb  test    rax, rax
0x18003ebbe  jz      short loc_18003EBD6
0x18003ebc0  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18003ebc7  mov     rcx, rax; hModule
0x18003ebca  call    cs:__imp_GetProcAddress
0x18003ebd0  mov     [rbx+8], rax
0x18003ebd4  jmp     short loc_18003EC01
0x18003ebd6  xor     r8d, r8d; dwFlags
0x18003ebd9  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18003ebe0  xor     edx, edx; hFile
0x18003ebe2  call    cs:__imp_LoadLibraryExW
0x18003ebe8  test    rax, rax
0x18003ebeb  jz      short loc_18003EC01
0x18003ebed  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18003ebf4  mov     rcx, rax; hModule
0x18003ebf7  call    cs:__imp_GetProcAddress
0x18003ebfd  mov     [rbx+10h], rax
0x18003ec01  mov     rax, [rbx+8]
0x18003ec05  test    rax, rax
0x18003ec08  jz      short loc_18003EC1D
0x18003ec0a  mov     rcx, [rbx]
0x18003ec0d  xor     r9d, r9d
0x18003ec10  xor     r8d, r8d
0x18003ec13  mov     rdx, rdi
0x18003ec16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec1b  jmp     short loc_18003EC39
0x18003ec1d  mov     rax, [rbx+10h]
0x18003ec21  test    rax, rax
0x18003ec24  jz      short loc_18003EC33
0x18003ec26  mov     rcx, [rbx]
0x18003ec29  mov     rdx, rdi
0x18003ec2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec31  jmp     short loc_18003EC39
0x18003ec33  call    cs:__imp_GetLastError
0x18003ec39  mov     rbx, [rsp+38h+arg_0]
0x18003ec3e  add     rsp, 30h
0x18003ec42  pop     rdi
0x18003ec43  retn
```
