# CThemePackManager::_CreateThemeFolder(ushort const *,ushort const *,CabReader::FILE_INFO const *,ushort *,unsigned __int64)

- ea: `0x180063708`
- end: `0x180063ace`
- name: `?_CreateThemeFolder@CThemePackManager@@AEAAJPEBG0PEBUFILE_INFO@CabReader@@PEAG_K@Z`
- size: `966`
- prototype: `int(CThemePackManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct CabReader::FILE_INFO *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180062f3c`

## callees

- `0x1800089c0`
- `0x18000ab10`
- `0x180030f64`
- `0x1800358c0`
- `0x180036318`
- `0x18003633c`
- `0x180063708`

## import_xrefs

- `SHCORE!__imp_SHCreateDirectory` at `0x1800639b6`
- `SHCORE!__imp_SHCreateDirectory` at `0x180063a36`
- `SHCORE!__imp_SHCreateDirectory` at `0x1800639b6`
- `SHCORE!__imp_SHCreateDirectory` at `0x180063a36`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063805`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006382e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063805`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006382e`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800638f7`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800638f7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800637a7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800638a9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800637a7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800638a9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180063948`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006396d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180063948`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006396d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006395b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006395b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063779`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063850`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063877`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18006399a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063779`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063850`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063877`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18006399a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800638e3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800638e3`

## pseudocode

```c
__int64 __fastcall CThemePackManager::_CreateThemeFolder(
        CThemePackManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        unsigned __int16 *pszPath)
{
  unsigned __int16 *v5; // r14
  const WCHAR *v7; // rsi
  CThemePackManager *v8; // rdi
  int Error; // ebx
  HANDLE FirstFileW; // r15
  int v11; // r12d
  unsigned __int16 *v12; // rdi
  BOOL NextFileW; // eax
  int v14; // r14d
  HANDLE v15; // rsi
  WORD v16; // dx
  WORD v17; // cx
  int v18; // eax
  int v19; // eax
  __int64 bIgnoreCase; // [rsp+20h] [rbp-E0h]
  struct _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME Buf1; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v24; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v25; // [rsp+48h] [rbp-B8h]
  CThemePackManager *v26; // [rsp+50h] [rbp-B0h]
  PCWSTR pszMore; // [rsp+58h] [rbp-A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  struct _WIN32_FIND_DATAW Buf2; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+500h] [rbp+400h] BYREF
  WCHAR pszPathIn[264]; // [rsp+710h] [rbp+610h] BYREF
  WCHAR FileName[264]; // [rsp+920h] [rbp+820h] BYREF

  v5 = pszPath;
  pszMore = a3;
  v24 = a2;
  v7 = a2;
  v26 = this;
  v8 = this;
  *((_DWORD *)this + 1238) = 0;
  v25 = pszPath;
  Error = PathCchCombine(pszPathOut, 0x104u, a2, L"*");
  if ( Error < 0 )
    return (unsigned int)Error;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(pszPathOut, &FindFileData);
  v11 = 2;
  if ( FirstFileW == (HANDLE)-1LL )
    goto LABEL_23;
  v12 = v25;
  NextFileW = 1;
  v14 = 0;
  while ( NextFileW )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      goto LABEL_20;
    if ( (FindFileData.dwFileAttributes & 2) != 0 )
      goto LABEL_20;
    if ( CompareStringOrdinal(L".", -1, FindFileData.cFileName, -1, 0) == 2 )
      goto LABEL_20;
    if ( CompareStringOrdinal(L"..", -1, FindFileData.cFileName, -1, 0) == 2 )
      goto LABEL_20;
    Error = PathCchCombine(pszPathIn, 0x104u, v7, FindFileData.cFileName);
    if ( Error < 0 )
      goto LABEL_20;
    Error = PathCchCombine(FileName, 0x104u, pszPathIn, a4 + 2);
    if ( Error < 0 )
      goto LABEL_20;
    memset_0(&Buf2, 0, sizeof(Buf2));
    v15 = FindFirstFileW(FileName, &Buf2);
    if ( v15 != (HANDLE)-1LL )
    {
      v16 = a4[263];
      v17 = a4[262];
      FileTime = 0;
      Buf1 = 0;
      if ( DosDateTimeToFileTime(v17, v16, &FileTime) && LocalFileTimeToFileTime(&FileTime, &Buf1) )
      {
        Error = 0;
LABEL_16:
        if ( !memcmp_0(&Buf1, &Buf2.ftCreationTime, 8u) )
        {
          v14 = 1;
          Error = StringCchCopyW(v12, 0x104u, pszPathIn);
        }
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error >= 0 )
          goto LABEL_16;
      }
      FindClose(v15);
    }
    v7 = v24;
LABEL_20:
    NextFileW = FindNextFileW(FirstFileW, &FindFileData);
    if ( v14 )
      break;
  }
  FindClose(FirstFileW);
  v8 = v26;
  if ( !v14 )
  {
    v5 = v25;
LABEL_23:
    Error = PathCchCombine(pszPathOut, 0x104u, v7, pszMore);
    if ( Error >= 0 )
    {
      v18 = SHCreateDirectory(*(HWND *)v8, pszPathOut);
      if ( !v18 || v18 == 183 || v18 == 80 )
      {
        Error = 0;
        if ( v18 )
          goto LABEL_29;
        *((_DWORD *)v8 + 1238) = 1;
        Error = StringCchCopyW(v5, 0x104u, pszPathOut);
      }
      else
      {
        if ( v18 > 0 )
          Error = (unsigned __int16)v18 | 0x80070000;
        else
          Error = v18;
LABEL_29:
        *((_DWORD *)v8 + 1238) = 0;
      }
      if ( Error >= 0 && !*((_DWORD *)v8 + 1238) )
      {
        do
        {
          if ( *((_DWORD *)v8 + 1238) )
            break;
          LODWORD(bIgnoreCase) = v11;
          Error = StringCchPrintfW(v5, 0x104u, L"%s (%d)", pszPathOut, bIgnoreCase);
          if ( Error >= 0 )
          {
            v19 = SHCreateDirectory(*(HWND *)v8, v5);
            if ( !v19 || v19 == 183 || v19 == 80 )
            {
              Error = 0;
            }
            else if ( v19 > 0 )
            {
              Error = (unsigned __int16)v19 | 0x80070000;
            }
            else
            {
              Error = v19;
            }
            *((_DWORD *)v8 + 1238) = v19 == 0;
          }
          ++v11;
        }
        while ( Error >= 0 );
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180063708  push    rbp
0x18006370a  push    rbx
0x18006370b  push    rsi
0x18006370c  push    rdi
0x18006370d  push    r12
0x18006370f  push    r13
0x180063711  push    r14
0x180063713  push    r15
0x180063715  lea     rbp, [rsp-0A48h]
0x18006371d  sub     rsp, 0B48h
0x180063724  mov     rax, cs:__security_cookie
0x18006372b  xor     rax, rsp
0x18006372e  mov     [rbp+0A80h+var_50], rax
0x180063735  mov     r14, [rbp+0A80h+pszPath]
0x18006373c  mov     r13, r9
0x18006373f  mov     [rsp+0B80h+pszMore], r8
0x180063744  lea     r9, asc_1800721E4; "*"
0x18006374b  mov     r8, rdx; pszPathIn
0x18006374e  mov     [rsp+0B80h+var_B40], rdx
0x180063753  mov     rsi, rdx
0x180063756  mov     [rsp+0B80h+var_B30], rcx
0x18006375b  mov     rdi, rcx
0x18006375e  mov     dword ptr [rcx+1358h], 0
0x180063768  mov     edx, 104h; cchPathOut
0x18006376d  mov     [rsp+0B80h+var_B38], r14
0x180063772  lea     rcx, [rbp+0A80h+pszPathOut]; pszPathOut
0x180063779  call    cs:__imp_PathCchCombine
0x18006377f  mov     ebx, eax
0x180063781  test    eax, eax
0x180063783  js      loc_180063AA9
0x180063789  xor     edx, edx; Val
0x18006378b  lea     rcx, [rsp+0B80h+FindFileData]; void *
0x180063790  mov     r8d, 250h; Size
0x180063796  call    memset_0
0x18006379b  lea     rdx, [rsp+0B80h+FindFileData]; lpFindFileData
0x1800637a0  lea     rcx, [rbp+0A80h+pszPathOut]; lpFileName
0x1800637a7  call    cs:__imp_FindFirstFileW
0x1800637ad  mov     r15, rax
0x1800637b0  mov     r12d, 2
0x1800637b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800637ba  jz      loc_180063986
0x1800637c0  mov     rdi, [rsp+0B80h+var_B38]
0x1800637c5  lea     eax, [r12-1]
0x1800637ca  xor     r14d, r14d
0x1800637cd  test    eax, eax
0x1800637cf  jz      loc_18006396A
0x1800637d5  test    byte ptr [rsp+0B80h+FindFileData.dwFileAttributes], 10h
0x1800637da  jz      loc_180063953
0x1800637e0  test    byte ptr [rsp+0B80h+FindFileData.dwFileAttributes], r12b
0x1800637e5  jnz     loc_180063953
0x1800637eb  or      r9d, 0FFFFFFFFh; cchCount2
0x1800637ef  mov     [rsp+0B80h+bIgnoreCase], 0; bIgnoreCase
0x1800637f7  or      edx, r9d; cchCount1
0x1800637fa  lea     r8, [rbp+0A80h+FindFileData.cFileName]; lpString2
0x1800637fe  lea     rcx, asc_18007A724; "."
0x180063805  call    cs:__imp_CompareStringOrdinal
0x18006380b  cmp     eax, r12d
0x18006380e  jz      loc_180063953
0x180063814  or      r9d, 0FFFFFFFFh; cchCount2
0x180063818  mov     [rsp+0B80h+bIgnoreCase], 0; bIgnoreCase
0x180063820  or      edx, r9d; cchCount1
0x180063823  lea     r8, [rbp+0A80h+FindFileData.cFileName]; lpString2
0x180063827  lea     rcx, asc_18007A2A8; ".."
0x18006382e  call    cs:__imp_CompareStringOrdinal
0x180063834  cmp     eax, r12d
0x180063837  jz      loc_180063953
0x18006383d  lea     r9, [rbp+0A80h+FindFileData.cFileName]; pszMore
0x180063841  mov     r8, rsi; pszPathIn
0x180063844  mov     edx, 104h; cchPathOut
0x180063849  lea     rcx, [rbp+0A80h+pszPathIn]; pszPathOut
0x180063850  call    cs:__imp_PathCchCombine
0x180063856  mov     ebx, eax
0x180063858  test    eax, eax
0x18006385a  js      loc_180063953
0x180063860  lea     r9, [r13+4]; pszMore
0x180063864  mov     edx, 104h; cchPathOut
0x180063869  lea     r8, [rbp+0A80h+pszPathIn]; pszPathIn
0x180063870  lea     rcx, [rbp+0A80h+FileName]; pszPathOut
0x180063877  call    cs:__imp_PathCchCombine
0x18006387d  mov     ebx, eax
0x18006387f  test    eax, eax
0x180063881  js      loc_180063953
0x180063887  xor     edx, edx; Val
0x180063889  lea     rcx, [rbp+0A80h+Buf2]; void *
0x180063890  mov     r8d, 250h; Size
0x180063896  call    memset_0
0x18006389b  lea     rdx, [rbp+0A80h+Buf2]; lpFindFileData
0x1800638a2  lea     rcx, [rbp+0A80h+FileName]; lpFileName
0x1800638a9  call    cs:__imp_FindFirstFileW
0x1800638af  mov     rsi, rax
0x1800638b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800638b6  jz      loc_18006394E
0x1800638bc  movzx   edx, word ptr [r13+20Eh]; wFatTime
0x1800638c4  lea     r8, [rsp+0B80h+FileTime]; lpFileTime
0x1800638c9  movzx   ecx, word ptr [r13+20Ch]; wFatDate
0x1800638d1  mov     qword ptr [rsp+0B80h+FileTime.dwLowDateTime], 0
0x1800638da  mov     qword ptr [rsp+0B80h+Buf1.dwLowDateTime], 0
0x1800638e3  call    cs:__imp_DosDateTimeToFileTime
0x1800638e9  test    eax, eax
0x1800638eb  jz      short loc_180063905
0x1800638ed  lea     rdx, [rsp+0B80h+Buf1]; lpFileTime
0x1800638f2  lea     rcx, [rsp+0B80h+FileTime]; lpLocalFileTime
0x1800638f7  call    cs:__imp_LocalFileTimeToFileTime
0x1800638fd  test    eax, eax
0x1800638ff  jz      short loc_180063905
0x180063901  xor     ebx, ebx
0x180063903  jmp     short loc_180063910
0x180063905  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006390a  mov     ebx, eax
0x18006390c  test    eax, eax
0x18006390e  js      short loc_180063945
0x180063910  mov     r8d, 8; Size
0x180063916  lea     rdx, [rbp+0A80h+Buf2.ftCreationTime]; Buf2
0x18006391d  lea     rcx, [rsp+0B80h+Buf1]; Buf1
0x180063922  call    memcmp_0
0x180063927  test    eax, eax
0x180063929  jnz     short loc_180063945
0x18006392b  lea     r8, [rbp+0A80h+pszPathIn]; unsigned __int16 *
0x180063932  mov     edx, 104h; unsigned __int64
0x180063937  mov     rcx, rdi; unsigned __int16 *
0x18006393a  lea     r14d, [rax+1]
0x18006393e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063943  mov     ebx, eax
0x180063945  mov     rcx, rsi; hFindFile
0x180063948  call    cs:__imp_FindClose
0x18006394e  mov     rsi, [rsp+0B80h+var_B40]
0x180063953  lea     rdx, [rsp+0B80h+FindFileData]; lpFindFileData
0x180063958  mov     rcx, r15; hFindFile
0x18006395b  call    cs:__imp_FindNextFileW
0x180063961  test    r14d, r14d
0x180063964  jz      loc_1800637CD
0x18006396a  mov     rcx, r15; hFindFile
0x18006396d  call    cs:__imp_FindClose
0x180063973  mov     rdi, [rsp+0B80h+var_B30]
0x180063978  test    r14d, r14d
0x18006397b  jnz     loc_180063AA9
0x180063981  mov     r14, [rsp+0B80h+var_B38]
0x180063986  mov     r9, [rsp+0B80h+pszMore]; pszMore
0x18006398b  lea     rcx, [rbp+0A80h+pszPathOut]; pszPathOut
0x180063992  mov     r8, rsi; pszPathIn
0x180063995  mov     edx, 104h; cchPathOut
0x18006399a  call    cs:__imp_PathCchCombine
0x1800639a0  xor     esi, esi
0x1800639a2  mov     ebx, eax
0x1800639a4  test    eax, eax
0x1800639a6  js      loc_180063AA9
0x1800639ac  mov     rcx, [rdi]; hwnd
0x1800639af  lea     rdx, [rbp+0A80h+pszPathOut]; pszPath
0x1800639b6  call    cs:__imp_SHCreateDirectory
0x1800639bc  mov     r13d, 80070000h
0x1800639c2  mov     r15d, 0B7h
0x1800639c8  test    eax, eax
0x1800639ca  jz      loc_180063A5C
0x1800639d0  cmp     eax, r15d
0x1800639d3  jz      loc_180063A5C
0x1800639d9  cmp     eax, 50h ; 'P'
0x1800639dc  jz      short loc_180063A5C
0x1800639de  test    eax, eax
0x1800639e0  jg      short loc_180063A54
0x1800639e2  mov     ebx, eax
0x1800639e4  mov     [rdi+1358h], esi
0x1800639ea  test    ebx, ebx
0x1800639ec  js      loc_180063AA9
0x1800639f2  cmp     [rdi+1358h], esi
0x1800639f8  jnz     loc_180063AA9
0x1800639fe  cmp     [rdi+1358h], esi
0x180063a04  jnz     loc_180063AA9
0x180063a0a  lea     r9, [rbp+0A80h+pszPathOut]
0x180063a11  mov     [rsp+0B80h+bIgnoreCase], r12d
0x180063a16  lea     r8, aSD; "%s (%d)"
0x180063a1d  mov     edx, 104h; unsigned __int64
0x180063a22  mov     rcx, r14; unsigned __int16 *
0x180063a25  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180063a2a  mov     ebx, eax
0x180063a2c  test    eax, eax
0x180063a2e  js      short loc_180063A9E
0x180063a30  mov     rcx, [rdi]; hwnd
0x180063a33  mov     rdx, r14; pszPath
0x180063a36  call    cs:__imp_SHCreateDirectory
0x180063a3c  mov     ecx, eax
0x180063a3e  test    eax, eax
0x180063a40  jz      short loc_180063A8F
0x180063a42  cmp     eax, r15d
0x180063a45  jz      short loc_180063A8F
0x180063a47  cmp     eax, 50h ; 'P'
0x180063a4a  jz      short loc_180063A8F
0x180063a4c  test    eax, eax
0x180063a4e  jg      short loc_180063A87
0x180063a50  mov     ebx, eax
0x180063a52  jmp     short loc_180063A91
0x180063a54  movzx   ebx, ax
0x180063a57  or      ebx, r13d
0x180063a5a  jmp     short loc_1800639E4
0x180063a5c  mov     ebx, esi
0x180063a5e  test    eax, eax
0x180063a60  jnz     short loc_1800639E4
0x180063a62  lea     r8, [rbp+0A80h+pszPathOut]; unsigned __int16 *
0x180063a69  mov     dword ptr [rdi+1358h], 1
0x180063a73  mov     edx, 104h; unsigned __int64
0x180063a78  mov     rcx, r14; unsigned __int16 *
0x180063a7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063a80  mov     ebx, eax
0x180063a82  jmp     loc_1800639EA
0x180063a87  movzx   ebx, cx
0x180063a8a  or      ebx, r13d
0x180063a8d  jmp     short loc_180063A91
0x180063a8f  mov     ebx, esi
0x180063a91  mov     eax, esi
0x180063a93  test    ecx, ecx
0x180063a95  setz    al
0x180063a98  mov     [rdi+1358h], eax
0x180063a9e  inc     r12d
0x180063aa1  test    ebx, ebx
0x180063aa3  jns     loc_1800639FE
0x180063aa9  mov     eax, ebx
0x180063aab  mov     rcx, [rbp+0A80h+var_50]
0x180063ab2  xor     rcx, rsp; StackCookie
0x180063ab5  call    __security_check_cookie
0x180063aba  add     rsp, 0B48h
0x180063ac1  pop     r15
0x180063ac3  pop     r14
0x180063ac5  pop     r13
0x180063ac7  pop     r12
0x180063ac9  pop     rdi
0x180063aca  pop     rsi
0x180063acb  pop     rbx
0x180063acc  pop     rbp
0x180063acd  retn
```
