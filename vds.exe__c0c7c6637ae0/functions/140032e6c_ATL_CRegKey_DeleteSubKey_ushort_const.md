# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140032e6c`
- end: `0x140032f21`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140031658`
- `0x140034838`
- `0x140034e1c`

## callees

- `0x140032e6c`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140032ebe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140032ebe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140032ea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140032ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140032ea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140032ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140032e91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140032e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032f0f`

## string_xrefs

- `0x140032e8a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x140032e9c`: `RegDeleteKeyExW`
- `0x140032eb7`: `advapi32.dll`
- `0x140032ec9`: `RegDeleteKeyW`

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
0x140032e6c  mov     [rsp+arg_0], rbx
0x140032e71  push    rdi
0x140032e72  sub     rsp, 30h
0x140032e76  mov     rdi, rdx
0x140032e79  mov     rbx, rcx
0x140032e7c  cmp     qword ptr [rcx+8], 0
0x140032e81  jnz     short loc_140032EDD
0x140032e83  cmp     qword ptr [rcx+10h], 0
0x140032e88  jnz     short loc_140032EDD
0x140032e8a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x140032e91  call    cs:__imp_GetModuleHandleW
0x140032e97  test    rax, rax
0x140032e9a  jz      short loc_140032EB2
0x140032e9c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x140032ea3  mov     rcx, rax; hModule
0x140032ea6  call    cs:__imp_GetProcAddress
0x140032eac  mov     [rbx+8], rax
0x140032eb0  jmp     short loc_140032EDD
0x140032eb2  xor     r8d, r8d; dwFlags
0x140032eb5  xor     edx, edx; hFile
0x140032eb7  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x140032ebe  call    cs:__imp_LoadLibraryExW
0x140032ec4  test    rax, rax
0x140032ec7  jz      short loc_140032EDD
0x140032ec9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140032ed0  mov     rcx, rax; hModule
0x140032ed3  call    cs:__imp_GetProcAddress
0x140032ed9  mov     [rbx+10h], rax
0x140032edd  mov     rax, [rbx+8]
0x140032ee1  test    rax, rax
0x140032ee4  jz      short loc_140032EF9
0x140032ee6  xor     r9d, r9d
0x140032ee9  xor     r8d, r8d
0x140032eec  mov     rdx, rdi
0x140032eef  mov     rcx, [rbx]
0x140032ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032ef7  jmp     short loc_140032F16
0x140032ef9  mov     rax, [rbx+10h]
0x140032efd  test    rax, rax
0x140032f00  jz      short loc_140032F0F
0x140032f02  mov     rdx, rdi
0x140032f05  mov     rcx, [rbx]
0x140032f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032f0d  jmp     short loc_140032F16
0x140032f0f  call    cs:__imp_GetLastError
0x140032f15  nop
0x140032f16  mov     rbx, [rsp+38h+arg_0]
0x140032f1b  add     rsp, 30h
0x140032f1f  pop     rdi
0x140032f20  retn
```
