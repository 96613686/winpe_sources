# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18003eb94`
- end: `0x18003ec49`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18003f248`
- `0x18003f67c`

## callees

- `0x18003eb94`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ebb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ebb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ebfb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ebe6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ebe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec37`

## string_xrefs

- `0x18003ebb2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18003ebc4`: `RegDeleteKeyExW`
- `0x18003ebdf`: `advapi32.dll`
- `0x18003ebf1`: `RegDeleteKeyW`

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
0x18003eb94  mov     [rsp+arg_0], rbx
0x18003eb99  push    rdi
0x18003eb9a  sub     rsp, 30h
0x18003eb9e  mov     rdi, rdx
0x18003eba1  mov     rbx, rcx
0x18003eba4  cmp     qword ptr [rcx+8], 0
0x18003eba9  jnz     short loc_18003EC05
0x18003ebab  cmp     qword ptr [rcx+10h], 0
0x18003ebb0  jnz     short loc_18003EC05
0x18003ebb2  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18003ebb9  call    cs:__imp_GetModuleHandleW
0x18003ebbf  test    rax, rax
0x18003ebc2  jz      short loc_18003EBDA
0x18003ebc4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18003ebcb  mov     rcx, rax; hModule
0x18003ebce  call    cs:__imp_GetProcAddress
0x18003ebd4  mov     [rbx+8], rax
0x18003ebd8  jmp     short loc_18003EC05
0x18003ebda  xor     r8d, r8d; dwFlags
0x18003ebdd  xor     edx, edx; hFile
0x18003ebdf  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18003ebe6  call    cs:__imp_LoadLibraryExW
0x18003ebec  test    rax, rax
0x18003ebef  jz      short loc_18003EC05
0x18003ebf1  lea     rdx, aRegdeletekeyw_0; "RegDeleteKeyW"
0x18003ebf8  mov     rcx, rax; hModule
0x18003ebfb  call    cs:__imp_GetProcAddress
0x18003ec01  mov     [rbx+10h], rax
0x18003ec05  mov     rax, [rbx+8]
0x18003ec09  test    rax, rax
0x18003ec0c  jz      short loc_18003EC21
0x18003ec0e  xor     r9d, r9d
0x18003ec11  xor     r8d, r8d
0x18003ec14  mov     rdx, rdi
0x18003ec17  mov     rcx, [rbx]
0x18003ec1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec1f  jmp     short loc_18003EC3E
0x18003ec21  mov     rax, [rbx+10h]
0x18003ec25  test    rax, rax
0x18003ec28  jz      short loc_18003EC37
0x18003ec2a  mov     rdx, rdi
0x18003ec2d  mov     rcx, [rbx]
0x18003ec30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec35  jmp     short loc_18003EC3E
0x18003ec37  call    cs:__imp_GetLastError
0x18003ec3d  nop
0x18003ec3e  mov     rbx, [rsp+38h+arg_0]
0x18003ec43  add     rsp, 30h
0x18003ec47  pop     rdi
0x18003ec48  retn
```
