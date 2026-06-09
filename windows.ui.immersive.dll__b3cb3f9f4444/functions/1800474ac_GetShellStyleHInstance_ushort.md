# GetShellStyleHInstance(ushort * *)

- ea: `0x1800474ac`
- end: `0x1800475ca`
- name: `?GetShellStyleHInstance@@YAPEAUHINSTANCE__@@PEAPEAG@Z`
- size: `286`
- prototype: `HINSTANCE __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180032ea4`

## callees

- `0x1800474ac`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004755d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004759e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004755d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004759e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180047583`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180047583`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180047515`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18004752e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180047546`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180047515`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18004752e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x180047546`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800474fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800474fd`
- `UxTheme!GetCurrentThemeName` at `0x1800474e8`
- `UxTheme!GetCurrentThemeName` at `0x1800474e8`

## string_xrefs

- `0x18004753a`: `ShellStyle.dll`
- `0x18004757c`: `%SystemRoot%\System32\ShellStyle.dll`

## pseudocode

```c
HINSTANCE __fastcall GetShellStyleHInstance(unsigned __int16 **a1)
{
  HMODULE Library; // rbx
  WCHAR pszThemeFileName[264]; // [rsp+30h] [rbp-2F8h] BYREF
  WCHAR pszColorBuff[104]; // [rsp+240h] [rbp-E8h] BYREF

  Library = 0;
  if ( GetCurrentThemeName(pszThemeFileName, 260, pszColorBuff, 100, 0, 0) < 0
    || (PathRemoveFileSpecW(pszThemeFileName),
        PathAppendW(pszThemeFileName, L"Shell"),
        PathAppendW(pszThemeFileName, pszColorBuff),
        PathAppendW(pszThemeFileName, L"ShellStyle.dll"),
        (Library = LoadLibraryExW(pszThemeFileName, 0, 2u)) == 0) )
  {
    if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\ShellStyle.dll", pszThemeFileName, 0x104u) )
      return LoadLibraryExW(pszThemeFileName, 0, 2u);
  }
  return Library;
}

```

## disassembly

```asm
0x1800474ac  push    rbx
0x1800474ae  sub     rsp, 320h
0x1800474b5  mov     rax, cs:__security_cookie
0x1800474bc  xor     rax, rsp
0x1800474bf  mov     [rsp+328h+var_18], rax
0x1800474c7  xor     ebx, ebx
0x1800474c9  lea     r8, [rsp+328h+pszColorBuff]; pszColorBuff
0x1800474d1  mov     [rsp+328h+cchMaxSizeChars], ebx; cchMaxSizeChars
0x1800474d5  lea     rcx, [rsp+328h+pszThemeFileName]; pszThemeFileName
0x1800474da  mov     edx, 104h; cchMaxNameChars
0x1800474df  mov     [rsp+328h+pszSizeBuff], rbx; pszSizeBuff
0x1800474e4  lea     r9d, [rbx+64h]; cchMaxColorChars
0x1800474e8  call    cs:__imp_GetCurrentThemeName
0x1800474ef  nop     dword ptr [rax+rax+00h]
0x1800474f4  test    eax, eax
0x1800474f6  js      short loc_180047571
0x1800474f8  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x1800474fd  call    cs:__imp_PathRemoveFileSpecW
0x180047504  nop     dword ptr [rax+rax+00h]
0x180047509  lea     rdx, aShell; "Shell"
0x180047510  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x180047515  call    cs:__imp_PathAppendW
0x18004751c  nop     dword ptr [rax+rax+00h]
0x180047521  lea     rdx, [rsp+328h+pszColorBuff]; pszMore
0x180047529  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x18004752e  call    cs:__imp_PathAppendW
0x180047535  nop     dword ptr [rax+rax+00h]
0x18004753a  lea     rdx, aShellstyleDll; "ShellStyle.dll"
0x180047541  lea     rcx, [rsp+328h+pszThemeFileName]; pszPath
0x180047546  call    cs:__imp_PathAppendW
0x18004754d  nop     dword ptr [rax+rax+00h]
0x180047552  xor     edx, edx; hFile
0x180047554  lea     r8d, [rbx+2]; dwFlags
0x180047558  lea     rcx, [rsp+328h+pszThemeFileName]; lpLibFileName
0x18004755d  call    cs:__imp_LoadLibraryExW
0x180047564  nop     dword ptr [rax+rax+00h]
0x180047569  mov     rbx, rax
0x18004756c  test    rax, rax
0x18004756f  jnz     short loc_1800475AD
0x180047571  mov     r8d, 104h; nSize
0x180047577  lea     rdx, [rsp+328h+pszThemeFileName]; lpDst
0x18004757c  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\ShellStyle.dll"
0x180047583  call    cs:__imp_ExpandEnvironmentStringsW
0x18004758a  nop     dword ptr [rax+rax+00h]
0x18004758f  test    eax, eax
0x180047591  jz      short loc_1800475AD
0x180047593  xor     edx, edx; hFile
0x180047595  lea     rcx, [rsp+328h+pszThemeFileName]; lpLibFileName
0x18004759a  lea     r8d, [rdx+2]; dwFlags
0x18004759e  call    cs:__imp_LoadLibraryExW
0x1800475a5  nop     dword ptr [rax+rax+00h]
0x1800475aa  mov     rbx, rax
0x1800475ad  mov     rax, rbx
0x1800475b0  mov     rcx, [rsp+328h+var_18]
0x1800475b8  xor     rcx, rsp; StackCookie
0x1800475bb  call    __security_check_cookie
0x1800475c0  add     rsp, 320h
0x1800475c7  pop     rbx
0x1800475c8  retn
```
