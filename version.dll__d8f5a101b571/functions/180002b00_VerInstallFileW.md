# VerInstallFileW

- ea: `0x180002b00`
- end: `0x1800030df`
- name: `VerInstallFileW`
- size: `1503`
- prototype: `DWORD __stdcall(DWORD uFlags, LPCWSTR szSrcFileName, LPCWSTR szDestFileName, LPCWSTR szSrcDir, LPCWSTR szDestDir, LPCWSTR szCurDir, LPWSTR szTmpFile, PUINT puTmpFileLen)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x180001a40`

## callees

- `0x180001d9c`
- `0x180001df8`
- `0x180001eb0`
- `0x180002198`
- `0x180002398`
- `0x1800025b8`
- `0x180002904`
- `0x1800029d0`
- `0x1800029f0`
- `0x180002a6c`
- `0x180002b00`
- `0x180003182`
- `0x1800031b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000306b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000306b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180002e82`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180002ea4`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180002e82`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180002ea4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002d5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002d5d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002f57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002fb4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003039`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003097`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002f57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002fb4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003039`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003097`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002c69`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002caa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002ce8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003014`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002c69`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002caa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002ce8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f2d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002c01`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180002c01`
- `KERNELBASE!lstrcmpiW` at `0x180002fef`
- `KERNELBASE!lstrcmpiW` at `0x180002fef`
- `KERNELBASE!lstrlenW` at `0x180002f8d`
- `KERNELBASE!lstrlenW` at `0x180002f8d`
- `KERNEL32!LZCreateFileW` at `0x180002bae`
- `KERNEL32!LZCreateFileW` at `0x180002bae`
- `KERNEL32!LZCloseFile` at `0x180002c31`
- `KERNEL32!LZCloseFile` at `0x1800030a8`
- `KERNEL32!LZCloseFile` at `0x180002c31`
- `KERNEL32!LZCloseFile` at `0x1800030a8`
- `KERNEL32!LZInit` at `0x180002d83`
- `KERNEL32!LZInit` at `0x180002d83`
- `KERNEL32!LZCopy` at `0x180002d91`
- `KERNEL32!LZCopy` at `0x180002d91`
- `KERNEL32!LZClose` at `0x180002d9b`
- `KERNEL32!LZClose` at `0x180002d9b`
- `KERNEL32!MoveFileW` at `0x180003061`
- `KERNEL32!MoveFileW` at `0x180003061`

## string_xrefs

- `0x180002cd2`: `temp.%03X`

## pseudocode

```c
DWORD __stdcall VerInstallFileW(
        DWORD uFlags,
        LPCWSTR szSrcFileName,
        LPCWSTR szDestFileName,
        LPCWSTR szSrcDir,
        LPCWSTR szDestDir,
        LPCWSTR szCurDir,
        LPWSTR szTmpFile,
        PUINT puTmpFileLen)
{
  char v8; // r12
  DWORD result; // eax
  DWORD v10; // edi
  int v11; // r14d
  unsigned int v12; // r15d
  int v13; // eax
  int v14; // r9d
  unsigned __int16 v15; // r15
  DWORD FileAttributesW; // eax
  int v17; // r9d
  DWORD v18; // r13d
  int v19; // r12d
  const unsigned __int16 *v20; // rdx
  int v21; // ebx
  unsigned __int64 v22; // rsi
  unsigned __int16 *v23; // r15
  int v24; // r8d
  LONG v25; // esi
  HANDLE FileW; // rax
  DWORD v27; // eax
  INT v28; // ebx
  struct tagVS_VERSION *FileVersionInfo; // rsi
  struct tagVS_VERSION *v30; // rbx
  unsigned int v31; // eax
  unsigned int v32; // r9d
  unsigned int v33; // ecx
  unsigned int v34; // edx
  unsigned int i; // r8d
  __int16 v36; // ax
  int v37; // eax
  int v38; // ecx
  int v39; // edi
  DWORD LastError; // eax
  const WCHAR *v41; // rsi
  unsigned int v42; // eax
  PUINT v43; // r15
  unsigned int v44; // ebx
  const unsigned __int16 *v45; // rbx
  int v46; // r9d
  const unsigned __int16 *v47; // rdx
  DWORD v48; // eax
  DWORD v49; // eax
  unsigned int puLen; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v51; // [rsp+44h] [rbp-BCh] BYREF
  int v52; // [rsp+48h] [rbp-B8h]
  WINBOOL UsedDefaultChar; // [rsp+4Ch] [rbp-B4h] BYREF
  INT hfSource; // [rsp+50h] [rbp-B0h]
  DWORD v55; // [rsp+54h] [rbp-ACh]
  unsigned __int16 *v56; // [rsp+58h] [rbp-A8h]
  LPVOID v57; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpBuffer; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpString2; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v60; // [rsp+78h] [rbp-88h]
  unsigned __int64 v61; // [rsp+80h] [rbp-80h]
  PUINT v62; // [rsp+88h] [rbp-78h]
  LPCWSTR lpString1; // [rsp+90h] [rbp-70h]
  _BYTE v64[128]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR FileName[264]; // [rsp+120h] [rbp+20h] BYREF
  CHAR MultiByteStr[272]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR NewFileName[264]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR v68[264]; // [rsp+650h] [rbp+550h] BYREF
  WCHAR WideCharStr[264]; // [rsp+860h] [rbp+760h] BYREF

  v8 = uFlags;
  lpString1 = szCurDir;
  v60 = (unsigned __int16 *)szDestFileName;
  v55 = uFlags;
  v62 = puTmpFileLen;
  lpString2 = szDestDir;
  v56 = szTmpFile;
  UsedDefaultChar = 0;
  MakeFileName(FileName, szSrcDir, szSrcFileName, (int)szSrcDir);
  result = InitDiamond();
  v10 = result;
  if ( !result )
  {
    v11 = 1;
    hfSource = LZCreateFileW(FileName, 0x80000000LL, 1, 3, WideCharStr);
    v12 = hfSource;
    if ( hfSource < 0 )
    {
      v10 = 0x10000;
LABEL_86:
      TermDiamond();
      return v10;
    }
    v52 = 0;
    v13 = WideCharToMultiByte(1u, 0, WideCharStr, -1, MultiByteStr, 260, 0, &UsedDefaultChar);
    if ( v13 )
    {
      if ( v13 <= 128 && !UsedDefaultChar )
      {
        v52 = IsDiamondFile(MultiByteStr);
        if ( v52 )
          LZCloseFile(v12);
      }
    }
    v61 = MakeFileName(NewFileName, szDestDir, v60, v14);
    v15 = v61;
    StringCchCopyW(FileName, 0x104u, NewFileName);
    FileAttributesW = GetFileAttributesW(FileName);
    v18 = HIWORD(FileAttributesW);
    if ( !HIWORD(FileAttributesW) && (FileAttributesW & 1) != 0 )
    {
      v10 = 64;
      goto LABEL_84;
    }
    v19 = v8 & 1;
    if ( v19 )
    {
      if ( *szTmpFile )
      {
        MakeFileName(FileName, lpString2, szTmpFile, v17);
        if ( !(GetFileAttributesW(FileName) >> 16) )
        {
LABEL_33:
          if ( !(_WORD)v18 )
          {
            v57 = 0;
            lpBuffer = 0;
            v51 = 0;
            puLen = 0;
            if ( !v19 )
            {
              FileVersionInfo = MyGetFileVersionInfo(NewFileName);
              if ( FileVersionInfo )
              {
                v30 = MyGetFileVersionInfo(FileName);
                if ( v30 )
                {
                  v31 = *((_DWORD *)FileVersionInfo + 12);
                  if ( v31 > *((_DWORD *)v30 + 12)
                    || v31 == *((_DWORD *)v30 + 12) && *((_DWORD *)FileVersionInfo + 13) > *((_DWORD *)v30 + 13) )
                  {
                    v10 = 6;
                  }
                  if ( *((_DWORD *)FileVersionInfo + 19) != *((_DWORD *)v30 + 19)
                    || *((_DWORD *)FileVersionInfo + 20) != *((_DWORD *)v30 + 20) )
                  {
                    v10 |= 0x22u;
                  }
                  if ( VerQueryValueW(FileVersionInfo, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) )
                  {
                    if ( VerQueryValueW(v30, L"\\VarFileInfo\\Translation", &v57, &v51) )
                    {
                      v32 = 0;
                      v33 = puLen >> 2;
                      v34 = v51 >> 2;
                      puLen = v33;
                      v51 >>= 2;
                      if ( v33 )
                      {
                        do
                        {
                          for ( i = 0; i < v34; ++i )
                          {
                            if ( *((_WORD *)lpBuffer + 2 * v32) == *((_WORD *)v57 + 2 * i) )
                            {
                              v36 = *((_WORD *)lpBuffer + 2 * v32 + 1);
                              if ( v36 )
                              {
                                if ( v36 == *((_WORD *)v57 + 2 * i + 1) )
                                  goto LABEL_57;
                              }
                              else if ( *((_WORD *)v57 + 2 * i + 1) != 1200 )
                              {
                                goto LABEL_57;
                              }
                            }
                          }
                          v10 |= 0xAu;
LABEL_57:
                          ++v32;
                        }
                        while ( v32 < v33 );
                      }
                    }
                  }
                  LocalFree(v30);
                }
                else
                {
                  v10 = 6;
                }
                LocalFree(FileVersionInfo);
              }
            }
            v37 = FileInUse(NewFileName, v20);
            v38 = v10 | 0x80;
            if ( !v37 )
              v38 = v10;
            v39 = v38;
            if ( v38 )
            {
              v41 = &FileName[(unsigned __int16)v61];
              v42 = lstrlenW(v41);
              v43 = v62;
              v44 = v42;
              if ( *v62 <= v42 )
              {
                DeleteFileW(FileName);
                v11 = 0x40000;
              }
              else
              {
                StringCchCopyW(v56, *v62, v41);
              }
              v10 = v11 | v39;
              *v43 = v44 + 1;
              goto LABEL_84;
            }
            if ( !DeleteFileW(NewFileName) )
            {
              LastError = GetLastError();
              v10 = FileErrFlag(LastError) | 0x1000;
LABEL_83:
              DeleteFileW(FileName);
              goto LABEL_84;
            }
            v10 = 0;
          }
          if ( (v55 & 2) == 0 )
          {
            v45 = lpString1;
            if ( lpString1 )
            {
              if ( *lpString1 )
              {
                if ( lstrcmpiW(lpString1, lpString2) )
                {
                  MakeFileName(v68, v45, v60, v46);
                  if ( !(GetFileAttributesW(v68) >> 16) && ((unsigned int)FileInUse(v68, v47) || !DeleteFileW(v68)) )
                  {
                    v48 = GetLastError();
                    v10 = FileErrFlag(v48) | 0x4000;
                  }
                }
              }
            }
          }
          if ( !MoveFileW(FileName, NewFileName) )
          {
            v49 = GetLastError();
            v10 |= FileErrFlag(v49) | 0x2000;
            goto LABEL_83;
          }
LABEL_84:
          if ( v52 )
            goto LABEL_86;
LABEL_85:
          LZCloseFile((unsigned int)hfSource);
          goto LABEL_86;
        }
      }
    }
    v21 = 0;
    v22 = 260LL - v15;
    v23 = &FileName[v15];
    while ( 1 )
    {
      StringCchPrintfW(v23, v22, L"temp.%03X", (unsigned int)v21);
      if ( GetFileAttributesW(FileName) >> 16 )
        break;
      if ( v21 > 4095 )
      {
        v10 = 2048;
        goto LABEL_84;
      }
      ++v21;
    }
    if ( v52 )
    {
      memset_0(v64, 0, 0x78u);
      v25 = ExpandDiamondFile(MultiByteStr, FileName, v24, (struct tagLZI *)v64);
    }
    else
    {
      FileW = CreateFileW(FileName, 0xC0000000, 1u, 0, 1u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v27 = GetLastError();
        v10 = FileErrFlag(v27) | 0x800;
        goto LABEL_85;
      }
      v28 = LZInit((INT)FileW);
      v25 = LZCopy(hfSource, v28);
      LZClose(v28);
    }
    if ( v25 != -8 && v25 != -7 )
    {
      switch ( v25 )
      {
        case -6:
        case -5:
          v10 = 0x8000;
          goto LABEL_83;
        case -4:
          goto LABEL_80;
        case -3:
          goto LABEL_82;
        case -2:
LABEL_80:
          v10 = 256;
          goto LABEL_83;
      }
      if ( v25 != -1 )
        goto LABEL_33;
    }
LABEL_82:
    v10 = 0x10000;
    goto LABEL_83;
  }
  return result;
}

```

## disassembly

```asm
0x180002b00  mov     [rsp-8+arg_0], rbx
0x180002b05  push    rbp
0x180002b06  push    rsi
0x180002b07  push    rdi
0x180002b08  push    r12
0x180002b0a  push    r13
0x180002b0c  push    r14
0x180002b0e  push    r15
0x180002b10  lea     rbp, [rsp-980h]
0x180002b18  sub     rsp, 0A80h
0x180002b1f  mov     rax, cs:__security_cookie
0x180002b26  xor     rax, rsp
0x180002b29  mov     [rbp+9B0h+var_40], rax
0x180002b30  mov     rax, [rbp+9B0h+szCurDir]
0x180002b37  mov     r12d, ecx
0x180002b3a  mov     r13, [rbp+9B0h+szDestDir]
0x180002b41  xor     esi, esi
0x180002b43  mov     rbx, [rbp+9B0h+szTmpFile]
0x180002b4a  mov     [rbp+9B0h+lpString1], rax
0x180002b4e  mov     rax, [rbp+9B0h+puTmpFileLen]
0x180002b55  mov     [rsp+0AB0h+var_A38], r8
0x180002b5a  mov     r8, rdx; unsigned __int16 *
0x180002b5d  mov     [rsp+0AB0h+var_A5C], ecx
0x180002b61  mov     rdx, r9; unsigned __int16 *
0x180002b64  lea     rcx, [rbp+9B0h+FileName]; unsigned __int16 *
0x180002b68  mov     [rbp+9B0h+var_A28], rax
0x180002b6c  mov     [rsp+0AB0h+lpString2], r13
0x180002b71  mov     [rsp+0AB0h+var_A58], rbx
0x180002b76  mov     [rsp+0AB0h+UsedDefaultChar], esi
0x180002b7a  call    ?MakeFileName@@YA_KPEAGPEBG1H@Z; MakeFileName(ushort *,ushort const *,ushort const *,int)
0x180002b7f  call    ?InitDiamond@@YAKXZ; InitDiamond(void)
0x180002b84  mov     edi, eax
0x180002b86  test    eax, eax
0x180002b88  jnz     loc_1800030B5
0x180002b8e  lea     rax, [rbp+9B0h+WideCharStr]
0x180002b95  mov     edx, 80000000h
0x180002b9a  lea     r14d, [rsi+1]
0x180002b9e  mov     [rsp+0AB0h+lpMultiByteStr], rax
0x180002ba3  mov     r8d, r14d
0x180002ba6  lea     r9d, [rsi+3]
0x180002baa  lea     rcx, [rbp+9B0h+FileName]
0x180002bae  call    cs:__imp_LZCreateFileW
0x180002bb4  mov     [rsp+0AB0h+hfSource], eax
0x180002bb8  mov     r15d, eax
0x180002bbb  test    eax, eax
0x180002bbd  jns     short loc_180002BC9
0x180002bbf  mov     edi, 10000h
0x180002bc4  jmp     loc_1800030AE
0x180002bc9  lea     rax, [rsp+0AB0h+UsedDefaultChar]
0x180002bce  mov     [rsp+0AB0h+var_A68], esi
0x180002bd2  mov     [rsp+0AB0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180002bd7  lea     r8, [rbp+9B0h+WideCharStr]; lpWideCharStr
0x180002bde  mov     [rsp+0AB0h+lpDefaultChar], rsi; lpDefaultChar
0x180002be3  lea     rax, [rbp+9B0h+MultiByteStr]
0x180002bea  mov     esi, 104h
0x180002bef  or      r9d, 0FFFFFFFFh; cchWideChar
0x180002bf3  mov     [rsp+0AB0h+cbMultiByte], esi; cbMultiByte
0x180002bf7  xor     edx, edx; dwFlags
0x180002bf9  mov     ecx, r14d; CodePage
0x180002bfc  mov     [rsp+0AB0h+lpMultiByteStr], rax; lpMultiByteStr
0x180002c01  call    cs:__imp_WideCharToMultiByte
0x180002c07  xor     ecx, ecx
0x180002c09  test    eax, eax
0x180002c0b  jz      short loc_180002C37
0x180002c0d  cmp     eax, 80h
0x180002c12  jg      short loc_180002C37
0x180002c14  cmp     [rsp+0AB0h+UsedDefaultChar], ecx
0x180002c18  jnz     short loc_180002C37
0x180002c1a  lea     rcx, [rbp+9B0h+MultiByteStr]; char *
0x180002c21  call    ?IsDiamondFile@@YAHPEAD@Z; IsDiamondFile(char *)
0x180002c26  mov     [rsp+0AB0h+var_A68], eax
0x180002c2a  test    eax, eax
0x180002c2c  jz      short loc_180002C37
0x180002c2e  mov     ecx, r15d
0x180002c31  call    cs:__imp_LZCloseFile
0x180002c37  mov     r8, [rsp+0AB0h+var_A38]; unsigned __int16 *
0x180002c3c  lea     rcx, [rbp+9B0h+NewFileName]; unsigned __int16 *
0x180002c43  mov     rdx, r13; unsigned __int16 *
0x180002c46  call    ?MakeFileName@@YA_KPEAGPEBG1H@Z; MakeFileName(ushort *,ushort const *,ushort const *,int)
0x180002c4b  lea     r8, [rbp+9B0h+NewFileName]; unsigned __int16 *
0x180002c52  mov     [rbp+9B0h+var_A30], rax
0x180002c56  mov     rdx, rsi; unsigned __int64
0x180002c59  lea     rcx, [rbp+9B0h+FileName]; unsigned __int16 *
0x180002c5d  mov     r15, rax
0x180002c60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002c65  lea     rcx, [rbp+9B0h+FileName]; lpFileName
0x180002c69  call    cs:__imp_GetFileAttributesW
0x180002c6f  mov     r13d, eax
0x180002c72  xor     ecx, ecx
0x180002c74  shr     r13d, 10h
0x180002c78  test    r13w, r13w
0x180002c7c  jnz     short loc_180002C8B
0x180002c7e  test    r14b, al
0x180002c81  jz      short loc_180002C8B
0x180002c83  lea     edi, [rcx+40h]
0x180002c86  jmp     loc_18000309D
0x180002c8b  and     r12d, r14d
0x180002c8e  jz      short loc_180002CBE
0x180002c90  cmp     [rbx], cx
0x180002c93  jz      short loc_180002CBE
0x180002c95  mov     rdx, [rsp+0AB0h+lpString2]; unsigned __int16 *
0x180002c9a  lea     rcx, [rbp+9B0h+FileName]; unsigned __int16 *
0x180002c9e  mov     r8, rbx; unsigned __int16 *
0x180002ca1  call    ?MakeFileName@@YA_KPEAGPEBG1H@Z; MakeFileName(ushort *,ushort const *,ushort const *,int)
0x180002ca6  lea     rcx, [rbp+9B0h+FileName]; lpFileName
0x180002caa  call    cs:__imp_GetFileAttributesW
0x180002cb0  shr     eax, 10h
0x180002cb3  xor     ecx, ecx
0x180002cb5  test    ax, ax
0x180002cb8  jz      loc_180002DE9
0x180002cbe  movzx   eax, r15w
0x180002cc2  mov     ebx, ecx
0x180002cc4  lea     r15, [rbp+9B0h+FileName]
0x180002cc8  sub     rsi, rax
0x180002ccb  lea     r15, [r15+rax*2]
0x180002ccf  mov     r9d, ebx
0x180002cd2  lea     r8, aTemp03x; "temp.%03X"
0x180002cd9  mov     rdx, rsi; unsigned __int64
0x180002cdc  mov     rcx, r15; unsigned __int16 *
0x180002cdf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002ce4  lea     rcx, [rbp+9B0h+FileName]; lpFileName
0x180002ce8  call    cs:__imp_GetFileAttributesW
0x180002cee  shr     eax, 10h
0x180002cf1  test    ax, ax
0x180002cf4  jnz     short loc_180002D0D
0x180002cf6  cmp     ebx, 0FFFh
0x180002cfc  jg      short loc_180002D03
0x180002cfe  add     ebx, r14d
0x180002d01  jmp     short loc_180002CCF
0x180002d03  mov     edi, 800h
0x180002d08  jmp     loc_18000309D
0x180002d0d  xor     eax, eax
0x180002d0f  cmp     [rsp+0AB0h+var_A68], eax
0x180002d13  jz      short loc_180002D3C
0x180002d15  xor     edx, edx; Val
0x180002d17  lea     r8d, [rax+78h]; Size
0x180002d1b  lea     rcx, [rbp+9B0h+var_A10]; void *
0x180002d1f  call    memset_0
0x180002d24  lea     r9, [rbp+9B0h+var_A10]; struct tagLZI *
0x180002d28  lea     rdx, [rbp+9B0h+FileName]; unsigned __int16 *
0x180002d2c  lea     rcx, [rbp+9B0h+MultiByteStr]; char *
0x180002d33  call    ?ExpandDiamondFile@@YAHPEADPEBGHPEAUtagLZI@@@Z; ExpandDiamondFile(char *,ushort const *,int,tagLZI *)
0x180002d38  mov     esi, eax
0x180002d3a  jmp     short loc_180002DA1
0x180002d3c  mov     [rsp+0AB0h+lpDefaultChar], rax; hTemplateFile
0x180002d41  lea     rcx, [rbp+9B0h+FileName]; lpFileName
0x180002d45  mov     [rsp+0AB0h+cbMultiByte], 80h; dwFlagsAndAttributes
0x180002d4d  xor     r9d, r9d; lpSecurityAttributes
0x180002d50  mov     r8d, r14d; dwShareMode
0x180002d53  mov     dword ptr [rsp+0AB0h+lpMultiByteStr], r14d; dwCreationDisposition
0x180002d58  mov     edx, 0C0000000h; dwDesiredAccess
0x180002d5d  call    cs:__imp_CreateFileW
0x180002d63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002d67  jnz     short loc_180002D81
0x180002d69  call    cs:__imp_GetLastError
0x180002d6f  mov     ecx, eax; int
0x180002d71  call    ?FileErrFlag@@YAKH@Z; FileErrFlag(int)
0x180002d76  bts     eax, 0Bh
0x180002d7a  mov     edi, eax
0x180002d7c  jmp     loc_1800030A4
0x180002d81  mov     ecx, eax; hfSource
0x180002d83  call    cs:__imp_LZInit
0x180002d89  mov     ecx, [rsp+0AB0h+hfSource]; hfSource
0x180002d8d  mov     edx, eax; hfDest
0x180002d8f  mov     ebx, eax
0x180002d91  call    cs:__imp_LZCopy
0x180002d97  mov     ecx, ebx; hFile
0x180002d99  mov     esi, eax
0x180002d9b  call    cs:__imp_LZClose
0x180002da1  cmp     esi, 0FFFFFFF8h
0x180002da4  jz      loc_18000308E
0x180002daa  cmp     esi, 0FFFFFFF9h
0x180002dad  jz      loc_18000308E
0x180002db3  cmp     esi, 0FFFFFFFAh
0x180002db6  jz      loc_180003087
0x180002dbc  cmp     esi, 0FFFFFFFBh
0x180002dbf  jz      loc_180003087
0x180002dc5  cmp     esi, 0FFFFFFFCh
0x180002dc8  jz      loc_180003080
0x180002dce  cmp     esi, 0FFFFFFFDh
0x180002dd1  jz      loc_18000308E
0x180002dd7  cmp     esi, 0FFFFFFFEh
0x180002dda  jz      loc_180003080
0x180002de0  cmp     esi, 0FFFFFFFFh
0x180002de3  jz      loc_18000308E
0x180002de9  test    r13w, r13w
0x180002ded  jnz     loc_180002FCE
0x180002df3  xor     r13d, r13d
0x180002df6  mov     [rsp+0AB0h+var_A50], r13
0x180002dfb  mov     [rsp+0AB0h+lpBuffer], r13
0x180002e00  mov     [rsp+0AB0h+var_A6C], r13d
0x180002e05  mov     [rsp+0AB0h+puLen], r13d
0x180002e0a  test    r12d, r12d
0x180002e0d  jnz     loc_180002F33
0x180002e13  lea     rcx, [rbp+9B0h+NewFileName]; lptstrFilename
0x180002e1a  call    ?MyGetFileVersionInfo@@YAPEAUtagVS_VERSION@@PEBG@Z; MyGetFileVersionInfo(ushort const *)
0x180002e1f  mov     rsi, rax
0x180002e22  test    rax, rax
0x180002e25  jz      loc_180002F33
0x180002e2b  lea     rcx, [rbp+9B0h+FileName]; lptstrFilename
0x180002e2f  call    ?MyGetFileVersionInfo@@YAPEAUtagVS_VERSION@@PEBG@Z; MyGetFileVersionInfo(ushort const *)
0x180002e34  mov     rbx, rax
0x180002e37  test    rax, rax
0x180002e3a  jnz     short loc_180002E44
0x180002e3c  lea     edi, [rax+6]
0x180002e3f  jmp     loc_180002F2A
0x180002e44  mov     eax, [rsi+30h]
0x180002e47  cmp     eax, [rbx+30h]
0x180002e4a  ja      short loc_180002E56
0x180002e4c  jnz     short loc_180002E5B
0x180002e4e  mov     eax, [rbx+34h]
0x180002e51  cmp     [rsi+34h], eax
0x180002e54  jbe     short loc_180002E5B
0x180002e56  mov     edi, 6
0x180002e5b  mov     eax, [rbx+4Ch]
0x180002e5e  cmp     [rsi+4Ch], eax
0x180002e61  jnz     short loc_180002E6B
0x180002e63  mov     eax, [rbx+50h]
0x180002e66  cmp     [rsi+50h], eax
0x180002e69  jz      short loc_180002E6E
0x180002e6b  or      edi, 22h
0x180002e6e  lea     r9, [rsp+0AB0h+puLen]; puLen
0x180002e73  mov     rcx, rsi; pBlock
0x180002e76  lea     r8, [rsp+0AB0h+lpBuffer]; lplpBuffer
0x180002e7b  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180002e82  call    cs:__imp_VerQueryValueW
0x180002e88  test    eax, eax
0x180002e8a  jz      loc_180002F21
0x180002e90  lea     r9, [rsp+0AB0h+var_A6C]; puLen
0x180002e95  mov     rcx, rbx; pBlock
0x180002e98  lea     r8, [rsp+0AB0h+var_A50]; lplpBuffer
0x180002e9d  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180002ea4  call    cs:__imp_VerQueryValueW
0x180002eaa  test    eax, eax
0x180002eac  jz      short loc_180002F21
0x180002eae  mov     ecx, [rsp+0AB0h+puLen]
0x180002eb2  mov     r9d, r13d
0x180002eb5  mov     edx, [rsp+0AB0h+var_A6C]
0x180002eb9  shr     ecx, 2
0x180002ebc  shr     edx, 2
0x180002ebf  mov     [rsp+0AB0h+puLen], ecx
0x180002ec3  mov     [rsp+0AB0h+var_A6C], edx
0x180002ec7  test    ecx, ecx
0x180002ec9  jz      short loc_180002F21
0x180002ecb  mov     r11, [rsp+0AB0h+var_A50]
0x180002ed0  mov     r12, [rsp+0AB0h+lpBuffer]
0x180002ed5  mov     r8d, r13d
0x180002ed8  mov     r15d, r9d
0x180002edb  cmp     r8d, edx
0x180002ede  jnb     short loc_180002F16
0x180002ee0  mov     r10d, r8d
0x180002ee3  movzx   eax, word ptr [r11+r10*4]
0x180002ee8  cmp     [r12+r15*4], ax
0x180002eed  jnz     short loc_180002F11
0x180002eef  movzx   eax, word ptr [r12+r15*4+2]
0x180002ef5  test    ax, ax
0x180002ef8  jnz     short loc_180002F09
0x180002efa  mov     eax, 4B0h
0x180002eff  cmp     [r11+r10*4+2], ax
0x180002f05  jnz     short loc_180002F19
0x180002f07  jmp     short loc_180002F11
0x180002f09  cmp     ax, [r11+r10*4+2]
0x180002f0f  jz      short loc_180002F19
0x180002f11  add     r8d, r14d
0x180002f14  jmp     short loc_180002EDB
0x180002f16  or      edi, 0Ah
0x180002f19  add     r9d, r14d
0x180002f1c  cmp     r9d, ecx
0x180002f1f  jb      short loc_180002ED5
0x180002f21  mov     rcx, rbx; hMem
0x180002f24  call    cs:__imp_LocalFree
0x180002f2a  mov     rcx, rsi; hMem
0x180002f2d  call    cs:__imp_LocalFree
0x180002f33  lea     rcx, [rbp+9B0h+NewFileName]; unsigned __int16 *
0x180002f3a  call    ?FileInUse@@YAHPEBG0@Z; FileInUse(ushort const *,ushort const *)
0x180002f3f  mov     ecx, edi
0x180002f41  bts     ecx, 7
0x180002f45  test    eax, eax
0x180002f47  cmovz   ecx, edi
0x180002f4a  mov     edi, ecx
0x180002f4c  test    ecx, ecx
0x180002f4e  jnz     short loc_180002F7E
0x180002f50  lea     rcx, [rbp+9B0h+NewFileName]; lpFileName
0x180002f57  call    cs:__imp_DeleteFileW
0x180002f5d  test    eax, eax
0x180002f5f  jnz     short loc_180002F79
0x180002f61  call    cs:__imp_GetLastError
0x180002f67  mov     ecx, eax; int
0x180002f69  call    ?FileErrFlag@@YAKH@Z; FileErrFlag(int)
0x180002f6e  mov     edi, eax
0x180002f70  bts     edi, 0Ch
0x180002f74  jmp     loc_180003093
0x180002f79  mov     edi, r13d
0x180002f7c  jmp     short loc_180002FD1
0x180002f7e  movzx   eax, word ptr [rbp+9B0h+var_A30]
0x180002f82  lea     rsi, [rbp+9B0h+FileName]
0x180002f86  lea     rsi, [rsi+rax*2]
0x180002f8a  mov     rcx, rsi; lpString
0x180002f8d  call    cs:__imp_lstrlenW
0x180002f93  mov     r15, [rbp+9B0h+var_A28]
  ... truncated ...
```
