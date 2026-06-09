# DeleteFolder(ushort const *)

- ea: `0x1800136ac`
- end: `0x18001396a`
- name: `?DeleteFolder@@YAJPEBG@Z`
- size: `702`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800136ac`
- `0x180036ae0`

## callees

- `0x180003f30`
- `0x1800136ac`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x180021d1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800138f2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800138e8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800138e8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800137df`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800137df`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013946`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180013946`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800138d7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800138d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800138ac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800138ac`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180013867`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001387d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180013867`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001387d`

## string_xrefs

- `0x180013711`: `DeleteFolder`
- `0x1800137b3`: `DeleteFolder`
- `0x18001392d`: `DeleteFolder`
- `0x180013718`: `szPath`
- `0x180013899`: `DeleteFolder failed: 0x%x in %s`
- `0x18001391a`: `DeleteFile failed: 0x%x in %s`
- `0x18001390e`: `RemoveDirectory failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall DeleteFolder(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  WCHAR *v4; // rcx
  const unsigned __int16 *v5; // rax
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  int v13; // eax
  HANDLE FirstFileW; // rsi
  signed int LastError; // eax
  int v16; // eax
  const char *v17; // rdx
  signed int v18; // eax
  signed int v19; // eax
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR PathName[264]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(PathName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "szPath", "DeleteFolder");
    return (unsigned int)-2147024809;
  }
  v3 = 2;
  v4 = FileName;
  v5 = a1;
  do
  {
    v6 = *((_OWORD *)v5 + 1);
    *(_OWORD *)v4 = *(_OWORD *)v5;
    v7 = *((_OWORD *)v5 + 2);
    *((_OWORD *)v4 + 1) = v6;
    v8 = *((_OWORD *)v5 + 3);
    *((_OWORD *)v4 + 2) = v7;
    v9 = *((_OWORD *)v5 + 4);
    *((_OWORD *)v4 + 3) = v8;
    v10 = *((_OWORD *)v5 + 5);
    *((_OWORD *)v4 + 4) = v9;
    v11 = *((_OWORD *)v5 + 6);
    *((_OWORD *)v4 + 5) = v10;
    v12 = *((_OWORD *)v5 + 7);
    v5 += 64;
    *((_OWORD *)v4 + 6) = v11;
    *((_OWORD *)v4 + 7) = v12;
    v4 += 64;
    --v3;
  }
  while ( v3 );
  *(_DWORD *)v4 = *(_DWORD *)v5;
  v13 = StringCchCatW(FileName, 0, L"\\*");
  v2 = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "StringCchCat failed: 0x%x in %s", v13, "DeleteFolder");
    return v2;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError == 3 )
    {
      v2 = 0;
    }
    else
    {
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "FindFirstFile");
    }
LABEL_33:
    FindClose(FirstFileW);
    return v2;
  }
  do
  {
    v16 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
    v2 = v16;
    if ( v16 < 0 )
    {
      v17 = "StringCchPrintf failed: 0x%x in %s";
      goto LABEL_31;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( lstrcmpiW(FindFileData.cFileName, L".") )
      {
        if ( lstrcmpiW(FindFileData.cFileName, L"..") )
        {
          v16 = DeleteFolder(PathName);
          v2 = v16;
          if ( v16 < 0 )
          {
            v17 = "DeleteFolder failed: 0x%x in %s";
LABEL_31:
            _DbgPrintMessage(8, v17, (unsigned int)v16, "DeleteFolder");
            goto LABEL_32;
          }
        }
      }
    }
    else if ( !DeleteFileW(PathName) )
    {
      v18 = GetLastError();
      v2 = v18;
      if ( v18 > 0 )
        v2 = (unsigned __int16)v18 | 0x80070000;
      if ( (v2 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "DeleteFile failed: 0x%x in %s", v2, "DeleteFolder");
        goto LABEL_32;
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( !RemoveDirectoryW(a1) )
  {
    v19 = GetLastError();
    v2 = v19;
    if ( v19 > 0 )
      v2 = (unsigned __int16)v19 | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
      _DbgPrintMessage(8, "RemoveDirectory failed: 0x%x in %s", v2, "DeleteFolder");
  }
LABEL_32:
  if ( FirstFileW )
    goto LABEL_33;
  return v2;
}

```

## disassembly

```asm
0x1800136ac  push    rbp
0x1800136ae  push    rbx
0x1800136af  push    rsi
0x1800136b0  push    r14
0x1800136b2  lea     rbp, [rsp-5B8h]
0x1800136ba  sub     rsp, 6B8h
0x1800136c1  mov     rax, cs:__security_cookie
0x1800136c8  xor     rax, rsp
0x1800136cb  mov     [rbp+5D0h+var_30], rax
0x1800136d2  mov     r14, rcx
0x1800136d5  mov     ebx, 208h
0x1800136da  mov     r8d, ebx; Size
0x1800136dd  lea     rcx, [rbp+5D0h+FileName]; void *
0x1800136e4  xor     edx, edx; Val
0x1800136e6  call    memset_0
0x1800136eb  mov     r8d, ebx; Size
0x1800136ee  lea     rcx, [rbp+5D0h+PathName]; void *
0x1800136f5  xor     edx, edx; Val
0x1800136f7  call    memset_0
0x1800136fc  xor     edx, edx; Val
0x1800136fe  lea     r8d, [rbx+48h]; Size
0x180013702  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x180013707  call    memset_0
0x18001370c  test    r14, r14
0x18001370f  jnz     short loc_180013739
0x180013711  lea     r9, aDeletefolder; "DeleteFolder"
0x180013718  lea     r8, aSzpath_0; "szPath"
0x18001371f  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180013726  lea     ecx, [r14+8]; int
0x18001372a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001372f  mov     ebx, 80070057h
0x180013734  jmp     loc_18001394C
0x180013739  mov     edx, 2
0x18001373e  lea     rcx, [rbp+5D0h+FileName]
0x180013745  mov     rax, r14
0x180013748  lea     r8d, [rdx+7Eh]
0x18001374c  movups  xmm0, xmmword ptr [rax]
0x18001374f  movups  xmm1, xmmword ptr [rax+10h]
0x180013753  movups  xmmword ptr [rcx], xmm0
0x180013756  movups  xmm0, xmmword ptr [rax+20h]
0x18001375a  movups  xmmword ptr [rcx+10h], xmm1
0x18001375e  movups  xmm1, xmmword ptr [rax+30h]
0x180013762  movups  xmmword ptr [rcx+20h], xmm0
0x180013766  movups  xmm0, xmmword ptr [rax+40h]
0x18001376a  movups  xmmword ptr [rcx+30h], xmm1
0x18001376e  movups  xmm1, xmmword ptr [rax+50h]
0x180013772  movups  xmmword ptr [rcx+40h], xmm0
0x180013776  movups  xmm0, xmmword ptr [rax+60h]
0x18001377a  movups  xmmword ptr [rcx+50h], xmm1
0x18001377e  movups  xmm1, xmmword ptr [rax+70h]
0x180013782  add     rax, r8
0x180013785  movups  xmmword ptr [rcx+60h], xmm0
0x180013789  movups  xmmword ptr [rcx+70h], xmm1
0x18001378d  add     rcx, r8
0x180013790  sub     rdx, 1; unsigned __int64
0x180013794  jnz     short loc_18001374C
0x180013796  mov     eax, [rax]
0x180013798  lea     r8, asc_18006D438; "\\*"
0x18001379f  mov     [rcx], eax
0x1800137a1  lea     rcx, [rbp+5D0h+FileName]; unsigned __int16 *
0x1800137a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800137ad  mov     ebx, eax
0x1800137af  test    eax, eax
0x1800137b1  jns     short loc_1800137D3
0x1800137b3  lea     r9, aDeletefolder; "DeleteFolder"
0x1800137ba  mov     r8d, eax
0x1800137bd  lea     rdx, aStringcchcatFa; "StringCchCat failed: 0x%x in %s"
0x1800137c4  mov     ecx, 8; int
0x1800137c9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800137ce  jmp     loc_18001394C
0x1800137d3  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x1800137d8  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x1800137df  call    cs:__imp_FindFirstFileW
0x1800137e5  mov     rsi, rax
0x1800137e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800137ec  jnz     short loc_180013825
0x1800137ee  call    cs:__imp_GetLastError
0x1800137f4  mov     ebx, eax
0x1800137f6  cmp     eax, 3
0x1800137f9  jnz     short loc_180013802
0x1800137fb  xor     ebx, ebx
0x1800137fd  jmp     loc_180013943
0x180013802  test    eax, eax
0x180013804  jle     short loc_18001380F
0x180013806  movzx   ebx, ax
0x180013809  or      ebx, 80070000h
0x18001380f  lea     rdx, aFindfirstfile; "FindFirstFile"
0x180013816  mov     ecx, 8; int
0x18001381b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013820  jmp     loc_180013943
0x180013825  lea     rax, [rsp+6D0h+FindFileData.cFileName]
0x18001382a  mov     r9, r14
0x18001382d  lea     r8, aSS_0; "%s\\%s"
0x180013834  mov     [rsp+6D0h+var_6B0], rax
0x180013839  mov     edx, 104h; unsigned __int64
0x18001383e  lea     rcx, [rbp+5D0h+PathName]; unsigned __int16 *
0x180013845  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001384a  mov     ebx, eax
0x18001384c  test    eax, eax
0x18001384e  js      loc_180013923
0x180013854  test    byte ptr [rsp+6D0h+FindFileData.dwFileAttributes], 10h
0x180013859  jz      short loc_1800138A5
0x18001385b  lea     rdx, String2; "."
0x180013862  lea     rcx, [rsp+6D0h+FindFileData.cFileName]; lpString1
0x180013867  call    cs:__imp_lstrcmpiW
0x18001386d  test    eax, eax
0x18001386f  jz      short loc_1800138CF
0x180013871  lea     rdx, asc_180069B14; ".."
0x180013878  lea     rcx, [rsp+6D0h+FindFileData.cFileName]; lpString1
0x18001387d  call    cs:__imp_lstrcmpiW
0x180013883  test    eax, eax
0x180013885  jz      short loc_1800138CF
0x180013887  lea     rcx, [rbp+5D0h+PathName]; unsigned __int16 *
0x18001388e  call    ?DeleteFolder@@YAJPEBG@Z; DeleteFolder(ushort const *)
0x180013893  mov     ebx, eax
0x180013895  test    eax, eax
0x180013897  jns     short loc_1800138CF
0x180013899  lea     rdx, aDeletefolderFa; "DeleteFolder failed: 0x%x in %s"
0x1800138a0  jmp     loc_18001392A
0x1800138a5  lea     rcx, [rbp+5D0h+PathName]; lpFileName
0x1800138ac  call    cs:__imp_DeleteFileW
0x1800138b2  test    eax, eax
0x1800138b4  jnz     short loc_1800138CF
0x1800138b6  call    cs:__imp_GetLastError
0x1800138bc  mov     ebx, eax
0x1800138be  test    eax, eax
0x1800138c0  jle     short loc_1800138CB
0x1800138c2  movzx   ebx, ax
0x1800138c5  or      ebx, 80070000h
0x1800138cb  test    ebx, ebx
0x1800138cd  js      short loc_180013917
0x1800138cf  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x1800138d4  mov     rcx, rsi; hFindFile
0x1800138d7  call    cs:__imp_FindNextFileW
0x1800138dd  test    eax, eax
0x1800138df  jnz     loc_180013825
0x1800138e5  mov     rcx, r14; lpPathName
0x1800138e8  call    cs:__imp_RemoveDirectoryW
0x1800138ee  test    eax, eax
0x1800138f0  jnz     short loc_18001393E
0x1800138f2  call    cs:__imp_GetLastError
0x1800138f8  mov     ebx, eax
0x1800138fa  test    eax, eax
0x1800138fc  jle     short loc_180013907
0x1800138fe  movzx   ebx, ax
0x180013901  or      ebx, 80070000h
0x180013907  test    ebx, ebx
0x180013909  jns     short loc_18001393E
0x18001390b  mov     r8d, ebx
0x18001390e  lea     rdx, aRemovedirector; "RemoveDirectory failed: 0x%x in %s"
0x180013915  jmp     short loc_18001392D
0x180013917  mov     r8d, ebx
0x18001391a  lea     rdx, aDeletefileFail; "DeleteFile failed: 0x%x in %s"
0x180013921  jmp     short loc_18001392D
0x180013923  lea     rdx, aStringcchprint; "StringCchPrintf failed: 0x%x in %s"
0x18001392a  mov     r8d, eax
0x18001392d  lea     r9, aDeletefolder; "DeleteFolder"
0x180013934  mov     ecx, 8; int
0x180013939  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001393e  test    rsi, rsi
0x180013941  jz      short loc_18001394C
0x180013943  mov     rcx, rsi; hFindFile
0x180013946  call    cs:__imp_FindClose
0x18001394c  mov     eax, ebx
0x18001394e  mov     rcx, [rbp+5D0h+var_30]
0x180013955  xor     rcx, rsp; StackCookie
0x180013958  call    __security_check_cookie
0x18001395d  add     rsp, 6B8h
0x180013964  pop     r14
0x180013966  pop     rsi
0x180013967  pop     rbx
0x180013968  pop     rbp
0x180013969  retn
```
