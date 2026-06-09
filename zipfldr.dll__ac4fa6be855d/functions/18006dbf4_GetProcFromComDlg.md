# _GetProcFromComDlg

- ea: `0x18006dbf4`
- end: `0x18006dc5c`
- name: `_GetProcFromComDlg`
- size: `104`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006db84`

## callees

- `0x18001fd40`
- `0x18006dbf4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006dc2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006dc2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006dc4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006dc4a`

## string_xrefs

- `0x18006dc04`: `comdlg32.dll`
- `0x18006dc1e`: `comdlg32.dll`

## pseudocode

```c
HMODULE GetProcFromComDlg()
{
  HMODULE result; // rax

  result = g_hinstCD;
  if ( g_hinstCD )
    goto LABEL_5;
  result = SHFusionLoadLibrary(L"comdlg32.dll");
  g_hinstCD = result;
  if ( !result )
  {
    result = LoadLibraryExW(L"comdlg32.dll", 0, 0x4000u);
    g_hinstCD = result;
  }
  if ( result )
LABEL_5:
    result = (HMODULE)GetProcAddress(result, "GetFileTitleW");
  qword_18008BD68 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x18006dbf4  sub     rsp, 28h
0x18006dbf8  mov     rax, cs:g_hinstCD
0x18006dbff  test    rax, rax
0x18006dc02  jnz     short loc_18006DC40
0x18006dc04  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18006dc0b  call    SHFusionLoadLibrary
0x18006dc10  mov     cs:g_hinstCD, rax
0x18006dc17  test    rax, rax
0x18006dc1a  jnz     short loc_18006DC38
0x18006dc1c  xor     edx, edx; hFile
0x18006dc1e  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x18006dc25  mov     r8d, 4000h; dwFlags
0x18006dc2b  call    cs:__imp_LoadLibraryExW
0x18006dc31  mov     cs:g_hinstCD, rax
0x18006dc38  mov     rcx, rax
0x18006dc3b  test    rax, rax
0x18006dc3e  jz      short loc_18006DC50
0x18006dc40  lea     rdx, aGetfiletitlew; "GetFileTitleW"
0x18006dc47  mov     rcx, rax; hModule
0x18006dc4a  call    cs:__imp_GetProcAddress
0x18006dc50  mov     cs:qword_18008BD68, rax
0x18006dc57  add     rsp, 28h
0x18006dc5b  retn
```
