# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x180011958`
- end: `0x180011a0d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010dcc`
- `0x180012228`
- `0x1800126ec`

## callees

- `0x180011958`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001197d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001197d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011992`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800119bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011992`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800119bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800119aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800119aa`

## string_xrefs

- `0x180011976`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180011988`: `RegDeleteKeyExW`
- `0x1800119a3`: `advapi32.dll`
- `0x1800119b5`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const wchar_t *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const wchar_t *); // rax

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
  v6 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const wchar_t *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180011958  mov     [rsp+arg_0], rbx
0x18001195d  push    rdi
0x18001195e  sub     rsp, 30h
0x180011962  mov     rdi, rdx
0x180011965  mov     rbx, rcx
0x180011968  cmp     qword ptr [rcx+8], 0
0x18001196d  jnz     short loc_1800119C9
0x18001196f  cmp     qword ptr [rcx+10h], 0
0x180011974  jnz     short loc_1800119C9
0x180011976  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18001197d  call    cs:__imp_GetModuleHandleW
0x180011983  test    rax, rax
0x180011986  jz      short loc_18001199E
0x180011988  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18001198f  mov     rcx, rax; hModule
0x180011992  call    cs:__imp_GetProcAddress
0x180011998  mov     [rbx+8], rax
0x18001199c  jmp     short loc_1800119C9
0x18001199e  xor     r8d, r8d; dwFlags
0x1800119a1  xor     edx, edx; hFile
0x1800119a3  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800119aa  call    cs:__imp_LoadLibraryExW
0x1800119b0  test    rax, rax
0x1800119b3  jz      short loc_1800119C9
0x1800119b5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800119bc  mov     rcx, rax; hModule
0x1800119bf  call    cs:__imp_GetProcAddress
0x1800119c5  mov     [rbx+10h], rax
0x1800119c9  mov     rax, [rbx+8]
0x1800119cd  test    rax, rax
0x1800119d0  jz      short loc_1800119E5
0x1800119d2  xor     r9d, r9d
0x1800119d5  xor     r8d, r8d
0x1800119d8  mov     rdx, rdi
0x1800119db  mov     rcx, [rbx]
0x1800119de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119e3  jmp     short loc_180011A02
0x1800119e5  mov     rax, [rbx+10h]
0x1800119e9  test    rax, rax
0x1800119ec  jz      short loc_1800119FB
0x1800119ee  mov     rdx, rdi
0x1800119f1  mov     rcx, [rbx]
0x1800119f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f9  jmp     short loc_180011A02
0x1800119fb  call    cs:__imp_GetLastError
0x180011a01  nop
0x180011a02  mov     rbx, [rsp+38h+arg_0]
0x180011a07  add     rsp, 30h
0x180011a0b  pop     rdi
0x180011a0c  retn
```
