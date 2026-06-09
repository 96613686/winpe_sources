# mlib::WinSQMApis::LoadLibraryW(void)

- ea: `0x18000d8c0`
- end: `0x18000d990`
- name: `?LoadLibraryW@WinSQMApis@mlib@@QEAAKXZ`
- size: `208`
- prototype: `unsigned int __fastcall(mlib::WinSQMApis *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001210`
- `0x180010470`

## callees

- `0x18000d8c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d90d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d926`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d93f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d958`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d975`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d90d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d926`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d93f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d958`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8e3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d8d0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d8d0`

## string_xrefs

- `0x18000d8c9`: `ntdll.dll`

## pseudocode

```c
DWORD __fastcall mlib::WinSQMApis::LoadLibraryW(mlib::WinSQMApis *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax

  LibraryW = LoadLibraryW(L"ntdll.dll");
  *(_QWORD *)this = LibraryW;
  if ( !LibraryW )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryW, "WinSqmSetDWORD");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
    return GetLastError();
  v5 = GetProcAddress(*(HMODULE *)this, "WinSqmStartSession");
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = GetProcAddress(*(HMODULE *)this, "WinSqmEndSession");
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
    return GetLastError();
  v7 = GetProcAddress(*(HMODULE *)this, "WinSqmIncrementDWORD");
  *((_QWORD *)this + 4) = v7;
  if ( v7
    && (v8 = GetProcAddress(*(HMODULE *)this, "WinSqmSetString"), (*((_QWORD *)this + 5) = v8) != 0)
    && (v9 = GetProcAddress(*(HMODULE *)this, "WinSqmAddToStream"), (*((_QWORD *)this + 6) = v9) != 0) )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18000d8c0  push    rbx
0x18000d8c2  sub     rsp, 20h
0x18000d8c6  mov     rbx, rcx
0x18000d8c9  lea     rcx, LibFileName; "ntdll.dll"
0x18000d8d0  call    cs:__imp_LoadLibraryW
0x18000d8d6  mov     [rbx], rax
0x18000d8d9  test    rax, rax
0x18000d8dc  jnz     short loc_18000D8EA
0x18000d8de  add     rsp, 20h
0x18000d8e2  pop     rbx
0x18000d8e3  jmp     cs:__imp_GetLastError
0x18000d8ea  lea     rdx, ProcName; "WinSqmSetDWORD"
0x18000d8f1  mov     rcx, rax; hModule
0x18000d8f4  call    cs:__imp_GetProcAddress
0x18000d8fa  mov     [rbx+8], rax
0x18000d8fe  test    rax, rax
0x18000d901  jz      short loc_18000D8DE
0x18000d903  mov     rcx, [rbx]; hModule
0x18000d906  lea     rdx, aWinsqmstartses; "WinSqmStartSession"
0x18000d90d  call    cs:__imp_GetProcAddress
0x18000d913  mov     [rbx+10h], rax
0x18000d917  test    rax, rax
0x18000d91a  jz      short loc_18000D8DE
0x18000d91c  mov     rcx, [rbx]; hModule
0x18000d91f  lea     rdx, aWinsqmendsessi; "WinSqmEndSession"
0x18000d926  call    cs:__imp_GetProcAddress
0x18000d92c  mov     [rbx+18h], rax
0x18000d930  test    rax, rax
0x18000d933  jz      short loc_18000D8DE
0x18000d935  mov     rcx, [rbx]; hModule
0x18000d938  lea     rdx, aWinsqmincremen; "WinSqmIncrementDWORD"
0x18000d93f  call    cs:__imp_GetProcAddress
0x18000d945  mov     [rbx+20h], rax
0x18000d949  test    rax, rax
0x18000d94c  jz      short loc_18000D8DE
0x18000d94e  mov     rcx, [rbx]; hModule
0x18000d951  lea     rdx, aWinsqmsetstrin; "WinSqmSetString"
0x18000d958  call    cs:__imp_GetProcAddress
0x18000d95e  mov     [rbx+28h], rax
0x18000d962  test    rax, rax
0x18000d965  jz      loc_18000D8DE
0x18000d96b  mov     rcx, [rbx]; hModule
0x18000d96e  lea     rdx, aWinsqmaddtostr; "WinSqmAddToStream"
0x18000d975  call    cs:__imp_GetProcAddress
0x18000d97b  mov     [rbx+30h], rax
0x18000d97f  test    rax, rax
0x18000d982  jz      loc_18000D8DE
0x18000d988  xor     eax, eax
0x18000d98a  add     rsp, 20h
0x18000d98e  pop     rbx
0x18000d98f  retn
```
