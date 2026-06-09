# InitReportStore(tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180020dc4`
- end: `0x180020e63`
- name: `?InitReportStore@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014fa4`

## callees

- `0x180007cf8`
- `0x180020dc4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020e20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020e20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020e4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020e4b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020de2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020df5`

## string_xrefs

- `0x180020ddb`: `wer.dll`
- `0x180020e16`: `WerpCreateMachineStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitReportStore(__int64 a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  signed int LastError; // eax
  signed int v5; // ebx
  FARPROC ProcAddress; // rbx
  __int64 v7; // rax

  Library = LoadLibraryExW(L"wer.dll", 0, 0);
  v3 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "WerpCreateMachineStore")) != 0 )
  {
    v7 = tlx::replace<tlx::file_handle_traits>(a1);
    v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(v7);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
  }
  if ( v3 )
    FreeLibrary(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020dc4  mov     [rsp+arg_0], rbx
0x180020dc9  mov     [rsp+arg_10], rsi
0x180020dce  push    rdi
0x180020dcf  sub     rsp, 20h
0x180020dd3  mov     rsi, rcx
0x180020dd6  xor     r8d, r8d; dwFlags
0x180020dd9  xor     edx, edx; hFile
0x180020ddb  lea     rcx, aWerDll_0; "wer.dll"
0x180020de2  call    cs:__imp_LoadLibraryExW
0x180020de8  mov     rdi, rax
0x180020deb  mov     [rsp+28h+arg_8], rax
0x180020df0  test    rax, rax
0x180020df3  jnz     short loc_180020E16
0x180020df5  call    cs:__imp_GetLastError
0x180020dfb  mov     ebx, eax
0x180020dfd  test    eax, eax
0x180020dff  jle     short loc_180020E0A
0x180020e01  movzx   ebx, ax
0x180020e04  or      ebx, 80070000h
0x180020e0a  mov     eax, 80004005h
0x180020e0f  test    ebx, ebx
0x180020e11  cmovns  ebx, eax
0x180020e14  jmp     short loc_180020E43
0x180020e16  lea     rdx, aWerpcreatemach; "WerpCreateMachineStore"
0x180020e1d  mov     rcx, rdi; hModule
0x180020e20  call    cs:__imp_GetProcAddress
0x180020e26  mov     rbx, rax
0x180020e29  test    rax, rax
0x180020e2c  jz      short loc_180020DF5
0x180020e2e  mov     rcx, rsi
0x180020e31  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180020e36  mov     rcx, rax
0x180020e39  mov     rax, rbx
0x180020e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e41  mov     ebx, eax
0x180020e43  test    rdi, rdi
0x180020e46  jz      short loc_180020E51
0x180020e48  mov     rcx, rdi; hLibModule
0x180020e4b  call    cs:__imp_FreeLibrary
0x180020e51  mov     eax, ebx
0x180020e53  mov     rbx, [rsp+28h+arg_0]
0x180020e58  mov     rsi, [rsp+28h+arg_10]
0x180020e5d  add     rsp, 20h
0x180020e61  pop     rdi
0x180020e62  retn
```
