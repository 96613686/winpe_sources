# PathMakeSystemFolderW

- ea: `0x18000c8c0`
- end: `0x18000ca26`
- name: `PathMakeSystemFolderW`
- size: `358`
- prototype: `BOOL __stdcall(LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x18000c8c0`
- `0x18000ca2c`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9c3`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000c9ba`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000c9ba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c93d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c93d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c95e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ca02`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c95e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ca02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c99e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c99e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c974`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c974`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18000c9ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18000c9ed`
- `SHELL32!SHChangeNotify` at `0x18000c9d8`
- `SHELL32!SHChangeNotify` at `0x18000c9d8`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000c92a`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000c92a`

## pseudocode

```c
BOOL __stdcall PathMakeSystemFolderW(LPCWSTR pszPath)
{
  BOOL v2; // edi
  int v3; // esi
  DWORD FileAttributesW; // eax
  HANDLE FileW; // rax
  void *v6; // rsi
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-258h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-248h] BYREF

  v2 = 0;
  if ( pszPath && *pszPath )
  {
    if ( (unsigned int)IsSystemSpecialCase(pszPath) )
    {
      v2 = 1;
    }
    else
    {
      v3 = SHGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
             L"UseSystemForSystemFolders",
             0,
             0,
             0) != 0
         ? 1
         : 4;
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
      {
        v2 = SetFileAttributesW(pszPath, v3 | FileAttributesW & 0xFFFFFFFA);
        if ( v2 )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          FileW = CreateFileW(pszPath, 0x80000100, 5u, 0, 3u, 0x2000000u, 0);
          v6 = FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            SetFileTime(FileW, 0, 0, &SystemTimeAsFileTime);
            CloseHandle(v6);
          }
          SHChangeNotify(0x2000, 5u, pszPath, 0);
        }
      }
    }
    if ( PathCombineW(pszDest, pszPath, L"desktop.ini") )
      SetFileAttributesW(pszDest, 6u);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c8c0  push    rbx
0x18000c8c2  push    rbp
0x18000c8c3  push    rsi
0x18000c8c4  push    rdi
0x18000c8c5  sub     rsp, 278h
0x18000c8cc  mov     rax, cs:__security_cookie
0x18000c8d3  xor     rax, rsp
0x18000c8d6  mov     [rsp+298h+var_38], rax
0x18000c8de  xor     ebp, ebp
0x18000c8e0  mov     rbx, rcx
0x18000c8e3  mov     edi, ebp
0x18000c8e5  test    rcx, rcx
0x18000c8e8  jz      loc_18000CA08
0x18000c8ee  cmp     [rcx], bp
0x18000c8f1  jz      loc_18000CA08
0x18000c8f7  call    IsSystemSpecialCase
0x18000c8fc  test    eax, eax
0x18000c8fe  jz      short loc_18000C908
0x18000c900  lea     edi, [rbp+1]
0x18000c903  jmp     loc_18000C9DE
0x18000c908  mov     [rsp+298h+pcbData], rbp; pcbData
0x18000c90d  lea     r8, aUsesystemforsy_0; "UseSystemForSystemFolders"
0x18000c914  xor     r9d, r9d; pdwType
0x18000c917  mov     [rsp+298h+pvData], rbp; pvData
0x18000c91c  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c923  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c92a  call    cs:__imp_SHGetValueW
0x18000c930  neg     eax
0x18000c932  mov     rcx, rbx; lpFileName
0x18000c935  sbb     esi, esi
0x18000c937  and     esi, 0FFFFFFFDh
0x18000c93a  add     esi, 4
0x18000c93d  call    cs:__imp_GetFileAttributesW
0x18000c943  cmp     eax, 0FFFFFFFFh
0x18000c946  jz      loc_18000C9DE
0x18000c94c  test    al, 10h
0x18000c94e  jz      loc_18000C9DE
0x18000c954  and     eax, 0FFFFFFFAh
0x18000c957  mov     rcx, rbx; lpFileName
0x18000c95a  or      eax, esi
0x18000c95c  mov     edx, eax; dwFileAttributes
0x18000c95e  call    cs:__imp_SetFileAttributesW
0x18000c964  mov     edi, eax
0x18000c966  test    eax, eax
0x18000c968  jz      short loc_18000C9DE
0x18000c96a  lea     rcx, [rsp+298h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c96f  mov     qword ptr [rsp+298h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x18000c974  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c97a  xor     r9d, r9d; lpSecurityAttributes
0x18000c97d  mov     [rsp+298h+hTemplateFile], rbp; hTemplateFile
0x18000c982  mov     dword ptr [rsp+298h+pcbData], 2000000h; dwFlagsAndAttributes
0x18000c98a  mov     edx, 80000100h; dwDesiredAccess
0x18000c98f  mov     rcx, rbx; lpFileName
0x18000c992  mov     dword ptr [rsp+298h+pvData], 3; dwCreationDisposition
0x18000c99a  lea     r8d, [r9+5]; dwShareMode
0x18000c99e  call    cs:__imp_CreateFileW
0x18000c9a4  mov     rsi, rax
0x18000c9a7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c9ab  jz      short loc_18000C9C9
0x18000c9ad  lea     r9, [rsp+298h+SystemTimeAsFileTime]; lpLastWriteTime
0x18000c9b2  xor     r8d, r8d; lpLastAccessTime
0x18000c9b5  xor     edx, edx; lpCreationTime
0x18000c9b7  mov     rcx, rax; hFile
0x18000c9ba  call    cs:__imp_SetFileTime
0x18000c9c0  mov     rcx, rsi; hObject
0x18000c9c3  call    cs:__imp_CloseHandle
0x18000c9c9  xor     r9d, r9d; dwItem2
0x18000c9cc  mov     r8, rbx; dwItem1
0x18000c9cf  mov     ecx, 2000h; wEventId
0x18000c9d4  lea     edx, [r9+5]; uFlags
0x18000c9d8  call    cs:__imp_SHChangeNotify
0x18000c9de  lea     r8, pszFile; "desktop.ini"
0x18000c9e5  mov     rdx, rbx; pszDir
0x18000c9e8  lea     rcx, [rsp+298h+pszDest]; pszDest
0x18000c9ed  call    cs:__imp_PathCombineW
0x18000c9f3  test    rax, rax
0x18000c9f6  jz      short loc_18000CA08
0x18000c9f8  mov     edx, 6; dwFileAttributes
0x18000c9fd  lea     rcx, [rsp+298h+pszDest]; lpFileName
0x18000ca02  call    cs:__imp_SetFileAttributesW
0x18000ca08  mov     eax, edi
0x18000ca0a  mov     rcx, [rsp+298h+var_38]
0x18000ca12  xor     rcx, rsp; StackCookie
0x18000ca15  call    __security_check_cookie
0x18000ca1a  add     rsp, 278h
0x18000ca21  pop     rdi
0x18000ca22  pop     rsi
0x18000ca23  pop     rbp
0x18000ca24  pop     rbx
0x18000ca25  retn
```
