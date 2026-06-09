# PathMakeSystemFolderA

- ea: `0x1800194f0`
- end: `0x18001966d`
- name: `PathMakeSystemFolderA`
- size: `381`
- prototype: `BOOL __stdcall(LPCSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x180012550`
- `0x1800180b4`
- `0x1800194f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019601`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800195f8`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800195f8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800195dc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800195dc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180019594`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180019640`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180019594`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180019640`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180019573`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180019573`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800195ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800195ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineA` at `0x18001962b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineA` at `0x18001962b`
- `SHELL32!SHChangeNotify` at `0x180019616`
- `SHELL32!SHChangeNotify` at `0x180019616`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueA` at `0x180019560`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueA` at `0x180019560`

## pseudocode

```c
BOOL __stdcall PathMakeSystemFolderA(LPCSTR pszPath)
{
  BOOL v1; // edi
  int v3; // esi
  DWORD FileAttributesA; // eax
  HANDLE FileA; // rax
  void *v6; // rsi
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-138h] BYREF
  CHAR pszDest[272]; // [rsp+50h] [rbp-128h] BYREF

  v1 = 0;
  if ( pszPath && *pszPath )
  {
    if ( (unsigned int)IsSystemSpecialCase_0(pszPath) )
    {
      v1 = 1;
    }
    else
    {
      v3 = SHGetValueA(
             HKEY_LOCAL_MACHINE,
             "Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
             "UseSystemForSystemFolders",
             0,
             0,
             0) != 0
         ? 1
         : 4;
      FileAttributesA = GetFileAttributesA(pszPath);
      if ( FileAttributesA != -1 && (FileAttributesA & 0x10) != 0 )
      {
        v1 = SetFileAttributesA(pszPath, v3 | FileAttributesA & 0xFFFFFFFA);
        if ( v1 )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          FileA = CreateFileA(pszPath, 0x80000100, 5u, 0, 3u, 0x2000000u, 0);
          v6 = FileA;
          if ( FileA != (HANDLE)-1LL )
          {
            SetFileTime(FileA, 0, 0, &SystemTimeAsFileTime);
            CloseHandle(v6);
          }
          SHChangeNotify(0x2000, 1u, pszPath, 0);
        }
      }
    }
    if ( PathCombineA(pszDest, pszPath, "desktop.ini") )
      SetFileAttributesA(pszDest, 6u);
  }
  return v1;
}

```

## disassembly

```asm
0x1800194f0  mov     [rsp+arg_8], rbx
0x1800194f5  mov     [rsp+arg_10], rsi
0x1800194fa  push    rdi
0x1800194fb  sub     rsp, 170h
0x180019502  mov     rax, cs:__security_cookie
0x180019509  xor     rax, rsp
0x18001950c  mov     [rsp+178h+var_18], rax
0x180019514  xor     edi, edi
0x180019516  mov     rbx, rcx
0x180019519  test    rcx, rcx
0x18001951c  jz      loc_180019646
0x180019522  cmp     [rcx], dil
0x180019525  jz      loc_180019646
0x18001952b  call    IsSystemSpecialCase_0
0x180019530  test    eax, eax
0x180019532  jz      short loc_18001953E
0x180019534  mov     edi, 1
0x180019539  jmp     loc_18001961C
0x18001953e  mov     [rsp+178h+pcbData], rdi; pcbData
0x180019543  lea     r8, aUsesystemforsy; "UseSystemForSystemFolders"
0x18001954a  xor     r9d, r9d; pdwType
0x18001954d  mov     [rsp+178h+pvData], rdi; pvData
0x180019552  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019559  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180019560  call    cs:__imp_SHGetValueA
0x180019566  neg     eax
0x180019568  mov     rcx, rbx; lpFileName
0x18001956b  sbb     esi, esi
0x18001956d  and     esi, 0FFFFFFFDh
0x180019570  add     esi, 4
0x180019573  call    cs:__imp_GetFileAttributesA
0x180019579  cmp     eax, 0FFFFFFFFh
0x18001957c  jz      loc_18001961C
0x180019582  test    al, 10h
0x180019584  jz      loc_18001961C
0x18001958a  and     eax, 0FFFFFFFAh
0x18001958d  mov     rcx, rbx; lpFileName
0x180019590  or      eax, esi
0x180019592  mov     edx, eax; dwFileAttributes
0x180019594  call    cs:__imp_SetFileAttributesA
0x18001959a  mov     edi, eax
0x18001959c  test    eax, eax
0x18001959e  jz      short loc_18001961C
0x1800195a0  lea     rcx, [rsp+178h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800195a5  mov     qword ptr [rsp+178h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800195ae  call    cs:__imp_GetSystemTimeAsFileTime
0x1800195b4  xor     r9d, r9d; lpSecurityAttributes
0x1800195b7  mov     [rsp+178h+hTemplateFile], 0; hTemplateFile
0x1800195c0  mov     dword ptr [rsp+178h+pcbData], 2000000h; dwFlagsAndAttributes
0x1800195c8  mov     edx, 80000100h; dwDesiredAccess
0x1800195cd  mov     rcx, rbx; lpFileName
0x1800195d0  mov     dword ptr [rsp+178h+pvData], 3; dwCreationDisposition
0x1800195d8  lea     r8d, [r9+5]; dwShareMode
0x1800195dc  call    cs:__imp_CreateFileA
0x1800195e2  mov     rsi, rax
0x1800195e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800195e9  jz      short loc_180019607
0x1800195eb  lea     r9, [rsp+178h+SystemTimeAsFileTime]; lpLastWriteTime
0x1800195f0  xor     r8d, r8d; lpLastAccessTime
0x1800195f3  xor     edx, edx; lpCreationTime
0x1800195f5  mov     rcx, rax; hFile
0x1800195f8  call    cs:__imp_SetFileTime
0x1800195fe  mov     rcx, rsi; hObject
0x180019601  call    cs:__imp_CloseHandle
0x180019607  xor     r9d, r9d; dwItem2
0x18001960a  mov     r8, rbx; dwItem1
0x18001960d  mov     ecx, 2000h; wEventId
0x180019612  lea     edx, [r9+1]; uFlags
0x180019616  call    cs:__imp_SHChangeNotify
0x18001961c  lea     r8, aDesktopIni; "desktop.ini"
0x180019623  mov     rdx, rbx; pszDir
0x180019626  lea     rcx, [rsp+178h+pszDest]; pszDest
0x18001962b  call    cs:__imp_PathCombineA
0x180019631  test    rax, rax
0x180019634  jz      short loc_180019646
0x180019636  mov     edx, 6; dwFileAttributes
0x18001963b  lea     rcx, [rsp+178h+pszDest]; lpFileName
0x180019640  call    cs:__imp_SetFileAttributesA
0x180019646  mov     eax, edi
0x180019648  mov     rcx, [rsp+178h+var_18]
0x180019650  xor     rcx, rsp; StackCookie
0x180019653  call    __security_check_cookie
0x180019658  lea     r11, [rsp+178h+var_8]
0x180019660  mov     rbx, [r11+18h]
0x180019664  mov     rsi, [r11+20h]
0x180019668  mov     rsp, r11
0x18001966b  pop     rdi
0x18001966c  retn
```
