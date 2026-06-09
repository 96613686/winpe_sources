# CThemeManager2::_CopyToThemeFolder(ushort const *,ushort *,unsigned __int64)

- ea: `0x1800559cc`
- end: `0x180055c4b`
- name: `?_CopyToThemeFolder@CThemeManager2@@AEAAJPEBGPEAG_K@Z`
- size: `639`
- prototype: `int(CThemeManager2 *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180053650`
- `0x180054ad0`

## callees

- `0x1800089c0`
- `0x18000ab10`
- `0x180030f64`
- `0x1800358c0`
- `0x180036318`
- `0x18003633c`
- `0x1800559cc`
- `0x180055f00`

## import_xrefs

- `SHCORE!__imp_SHCreateDirectoryExW` at `0x180055b84`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x180055b84`
- `SHLWAPI!PathFindFileNameW` at `0x180055b20`
- `SHLWAPI!PathFindFileNameW` at `0x180055b20`
- `SHLWAPI!PathFileExistsW` at `0x180055b6e`
- `SHLWAPI!PathFileExistsW` at `0x180055c05`
- `SHLWAPI!PathFileExistsW` at `0x180055b6e`
- `SHLWAPI!PathFileExistsW` at `0x180055c05`
- `SHLWAPI!PathFindExtensionW` at `0x180055bbf`
- `SHLWAPI!PathFindExtensionW` at `0x180055bbf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180055a97`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180055a97`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180055a3e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180055a3e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180055b05`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180055b05`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055af8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055af8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180055ba9`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180055ba9`

## pseudocode

```c
__int64 __fastcall CThemeManager2::_CopyToThemeFolder(
        CThemeManager2 *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int ThemeFolder; // ebx
  HANDLE FirstFileW; // rsi
  const unsigned __int16 *FileNameW; // rax
  int v8; // eax
  LPWSTR ExtensionW; // rax
  int i; // esi
  __int64 v12; // [rsp+28h] [rbp-D8h]
  __int128 FileInformation; // [rsp+30h] [rbp-D0h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *a3 = 0;
  ThemeFolder = CThemeManager2::_GetThemeFolder(this, pszPath, (unsigned int)a3);
  if ( ThemeFolder >= 0 )
  {
    v15 = 0;
    FileInformation = 0;
    Buf1 = 0;
    if ( !GetFileAttributesExW(a2, GetFileExInfoStandard, &FileInformation) )
      goto LABEL_31;
    ThemeFolder = StringCchPrintfW(FileName, 0x104u, L"%s\\*.theme", pszPath);
    if ( ThemeFolder >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
        goto LABEL_31;
      do
      {
        if ( *a3 )
          break;
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && !memcmp_0((char *)&Buf1 + 4, &FindFileData.ftLastWriteTime, 8u) )
        {
          ThemeFolder = StringCchPrintfW(a3, 0x104u, L"%s\\%s", pszPath, FindFileData.cFileName);
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
      if ( ThemeFolder >= 0 )
      {
LABEL_31:
        if ( !*a3 )
        {
          FileNameW = PathFindFileNameW(a2);
          ThemeFolder = StringCchCopyW(FileName, 0x104u, FileNameW);
          if ( ThemeFolder >= 0 )
          {
            if ( (int)StringCchPrintfW(a3, 0x104u, L"%s\\%s", pszPath, FileName) < 0 || PathFileExistsW(a3) )
            {
              ExtensionW = PathFindExtensionW(FileName);
              if ( ExtensionW )
                *ExtensionW = 0;
              for ( i = 2; ; ++i )
              {
                LODWORD(v12) = i;
                ThemeFolder = StringCchPrintfW(a3, 0x104u, L"%s\\%s (%d).theme", pszPath, FileName, v12);
                if ( ThemeFolder >= 0 && !PathFileExistsW(a3) )
                  break;
                if ( ThemeFolder < 0 )
                  return (unsigned int)ThemeFolder;
              }
              goto LABEL_18;
            }
            v8 = SHCreateDirectoryExW(0, pszPath, 0);
            if ( !v8 || v8 == 183 || (ThemeFolder = ResultFromKnownLastError(), ThemeFolder >= 0) )
            {
LABEL_18:
              if ( CopyFileW(a2, a3, 0) )
                return 0;
              else
                return (unsigned int)ResultFromKnownLastError();
            }
          }
        }
      }
    }
  }
  return (unsigned int)ThemeFolder;
}

```

## disassembly

```asm
0x1800559cc  mov     [rsp-8+arg_0], rbx
0x1800559d1  mov     [rsp-8+arg_18], rsi
0x1800559d6  push    rbp
0x1800559d7  push    rdi
0x1800559d8  push    r12
0x1800559da  push    r14
0x1800559dc  push    r15
0x1800559de  lea     rbp, [rsp-5E0h]
0x1800559e6  sub     rsp, 6E0h
0x1800559ed  mov     rax, cs:__security_cookie
0x1800559f4  xor     rax, rsp
0x1800559f7  mov     [rbp+600h+var_30], rax
0x1800559fe  mov     r14, rdx
0x180055a01  xor     r15d, r15d
0x180055a04  lea     rdx, [rbp+600h+pszPath]; unsigned __int16 *
0x180055a0b  mov     [r8], r15w
0x180055a0f  mov     rdi, r8
0x180055a12  call    ?_GetThemeFolder@CThemeManager2@@AEAAJPEAGI@Z; CThemeManager2::_GetThemeFolder(ushort *,uint)
0x180055a17  mov     ebx, eax
0x180055a19  test    eax, eax
0x180055a1b  js      loc_180055C1E
0x180055a21  xorps   xmm0, xmm0
0x180055a24  lea     r8, [rsp+700h+FileInformation]; lpFileInformation
0x180055a29  xor     eax, eax
0x180055a2b  xor     edx, edx; fInfoLevelId
0x180055a2d  mov     rcx, r14; lpFileName
0x180055a30  mov     [rsp+700h+var_6B0], eax
0x180055a34  movups  [rsp+700h+FileInformation], xmm0
0x180055a39  movups  [rsp+700h+Buf1], xmm0
0x180055a3e  call    cs:__imp_GetFileAttributesExW
0x180055a44  mov     r12d, 104h
0x180055a4a  test    eax, eax
0x180055a4c  jz      loc_180055B13
0x180055a52  lea     r9, [rbp+600h+pszPath]
0x180055a59  mov     edx, r12d; unsigned __int64
0x180055a5c  lea     r8, aSTheme; "%s\\*.theme"
0x180055a63  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180055a6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055a6f  mov     ebx, eax
0x180055a71  test    eax, eax
0x180055a73  js      loc_180055C1E
0x180055a79  xor     edx, edx; Val
0x180055a7b  lea     rcx, [rsp+700h+FindFileData]; void *
0x180055a80  mov     r8d, 250h; Size
0x180055a86  call    memset_0
0x180055a8b  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x180055a90  lea     rcx, [rbp+600h+FileName]; lpFileName
0x180055a97  call    cs:__imp_FindFirstFileW
0x180055a9d  mov     rsi, rax
0x180055aa0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055aa4  jz      short loc_180055B13
0x180055aa6  cmp     [rdi], r15w
0x180055aaa  jnz     short loc_180055B02
0x180055aac  test    byte ptr [rsp+700h+FindFileData.dwFileAttributes], 10h
0x180055ab1  jnz     short loc_180055AF0
0x180055ab3  mov     r8d, 8; Size
0x180055ab9  lea     rdx, [rsp+700h+FindFileData.ftLastWriteTime]; Buf2
0x180055abe  lea     rcx, [rsp+700h+Buf1+4]; Buf1
0x180055ac3  call    memcmp_0
0x180055ac8  test    eax, eax
0x180055aca  jnz     short loc_180055AF0
0x180055acc  lea     rax, [rbp+600h+FindFileData.cFileName]
0x180055ad0  mov     rdx, r12; unsigned __int64
0x180055ad3  lea     r9, [rbp+600h+pszPath]
0x180055ada  mov     [rsp+700h+var_6E0], rax
0x180055adf  lea     r8, aSS; "%s\\%s"
0x180055ae6  mov     rcx, rdi; unsigned __int16 *
0x180055ae9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055aee  mov     ebx, eax
0x180055af0  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x180055af5  mov     rcx, rsi; hFindFile
0x180055af8  call    cs:__imp_FindNextFileW
0x180055afe  test    eax, eax
0x180055b00  jnz     short loc_180055AA6
0x180055b02  mov     rcx, rsi; hFindFile
0x180055b05  call    cs:__imp_FindClose
0x180055b0b  test    ebx, ebx
0x180055b0d  js      loc_180055C1E
0x180055b13  cmp     [rdi], r15w
0x180055b17  jnz     loc_180055C1E
0x180055b1d  mov     rcx, r14; pszPath
0x180055b20  call    cs:__imp_PathFindFileNameW
0x180055b26  mov     rdx, r12; unsigned __int64
0x180055b29  lea     rcx, [rbp+600h+FileName]; unsigned __int16 *
0x180055b30  mov     r8, rax; unsigned __int16 *
0x180055b33  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180055b38  mov     ebx, eax
0x180055b3a  test    eax, eax
0x180055b3c  js      loc_180055C1E
0x180055b42  lea     rax, [rbp+600h+FileName]
0x180055b49  mov     rdx, r12; unsigned __int64
0x180055b4c  lea     r9, [rbp+600h+pszPath]
0x180055b53  mov     [rsp+700h+var_6E0], rax
0x180055b58  lea     r8, aSS; "%s\\%s"
0x180055b5f  mov     rcx, rdi; unsigned __int16 *
0x180055b62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055b67  test    eax, eax
0x180055b69  js      short loc_180055BB8
0x180055b6b  mov     rcx, rdi; pszPath
0x180055b6e  call    cs:__imp_PathFileExistsW
0x180055b74  test    eax, eax
0x180055b76  jnz     short loc_180055BB8
0x180055b78  xor     r8d, r8d; psa
0x180055b7b  lea     rdx, [rbp+600h+pszPath]; pszPath
0x180055b82  xor     ecx, ecx; hwnd
0x180055b84  call    cs:__imp_SHCreateDirectoryExW
0x180055b8a  test    eax, eax
0x180055b8c  jz      short loc_180055BA0
0x180055b8e  cmp     eax, 0B7h
0x180055b93  jz      short loc_180055BA0
0x180055b95  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055b9a  mov     ebx, eax
0x180055b9c  test    eax, eax
0x180055b9e  js      short loc_180055C1E
0x180055ba0  xor     r8d, r8d; bFailIfExists
0x180055ba3  mov     rdx, rdi; lpNewFileName
0x180055ba6  mov     rcx, r14; lpExistingFileName
0x180055ba9  call    cs:__imp_CopyFileW
0x180055baf  test    eax, eax
0x180055bb1  jz      short loc_180055C17
0x180055bb3  mov     ebx, r15d
0x180055bb6  jmp     short loc_180055C1E
0x180055bb8  lea     rcx, [rbp+600h+FileName]; pszPath
0x180055bbf  call    cs:__imp_PathFindExtensionW
0x180055bc5  test    rax, rax
0x180055bc8  jz      short loc_180055BCE
0x180055bca  mov     [rax], r15w
0x180055bce  mov     esi, 2
0x180055bd3  lea     rax, [rbp+600h+FileName]
0x180055bda  mov     dword ptr [rsp+700h+var_6D8], esi
0x180055bde  lea     r9, [rbp+600h+pszPath]
0x180055be5  mov     [rsp+700h+var_6E0], rax
0x180055bea  lea     r8, aSSDTheme; "%s\\%s (%d).theme"
0x180055bf1  mov     rdx, r12; unsigned __int64
0x180055bf4  mov     rcx, rdi; unsigned __int16 *
0x180055bf7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055bfc  mov     ebx, eax
0x180055bfe  test    eax, eax
0x180055c00  js      short loc_180055C0F
0x180055c02  mov     rcx, rdi; pszPath
0x180055c05  call    cs:__imp_PathFileExistsW
0x180055c0b  test    eax, eax
0x180055c0d  jz      short loc_180055BA0
0x180055c0f  inc     esi
0x180055c11  test    ebx, ebx
0x180055c13  jns     short loc_180055BD3
0x180055c15  jmp     short loc_180055C1E
0x180055c17  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055c1c  mov     ebx, eax
0x180055c1e  mov     eax, ebx
0x180055c20  mov     rcx, [rbp+600h+var_30]
0x180055c27  xor     rcx, rsp; StackCookie
0x180055c2a  call    __security_check_cookie
0x180055c2f  lea     r11, [rsp+700h+var_20]
0x180055c37  mov     rbx, [r11+30h]
0x180055c3b  mov     rsi, [r11+48h]
0x180055c3f  mov     rsp, r11
0x180055c42  pop     r15
0x180055c44  pop     r14
0x180055c46  pop     r12
0x180055c48  pop     rdi
0x180055c49  pop     rbp
0x180055c4a  retn
```
