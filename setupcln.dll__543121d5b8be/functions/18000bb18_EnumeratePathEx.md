# EnumeratePathEx

- ea: `0x18000bb18`
- end: `0x18000bfc6`
- name: `EnumeratePathEx`
- size: `1198`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64), __int64 (__fastcall *)(DWORD *, __int64), __int64, char)`
- caller_count: `4`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800040c0`
- `0x180006b48`
- `0x18000b380`
- `0x18000b5f8`

## callees

- `0x180008f64`
- `0x180009d30`
- `0x18000a0f0`
- `0x18000a780`
- `0x18000bb18`
- `0x18000bfcc`
- `0x18000c048`
- `0x18000c17c`
- `0x18000c1fc`
- `0x1800131a2`
- `0x1800131e0`
- `0x180014010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000bd14`
- `msvcrt!wcsrchr` at `0x18000bd14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bbf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bbf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf83`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bd8a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bdb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bd8a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bdb4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bec7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bec7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000be63`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000be63`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bc84`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bc84`

## string_xrefs

- `0x18000bc27`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x18000be92`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x18000bea1`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x18000bf36`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18000bedb`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x18000bf0e`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

## pseudocode

```c
__int64 __fastcall EnumeratePathEx(
        LPCWSTR lpFileName,
        __int64 (__fastcall *a2)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64),
        __int64 (__fastcall *a3)(DWORD *, __int64),
        __int64 a4,
        char a5)
{
  __int64 (__fastcall *v5)(DWORD *, __int64); // r15
  DWORD LastError; // ebx
  DWORD v9; // ecx
  WCHAR *v10; // rdi
  const wchar_t *v11; // rax
  wchar_t *v12; // r12
  const WCHAR *v13; // rax
  unsigned int v14; // r13d
  unsigned __int64 v15; // r14
  int v16; // ebx
  void *v17; // rax
  wchar_t *v18; // rax
  const WCHAR *v19; // rax
  int v20; // eax
  void *v21; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v23; // r15
  HANDLE v24; // rax
  BOOL NextFileW; // eax
  DWORD v26; // ebx
  DWORD v27; // eax
  const wchar_t *v28; // r8
  HANDLE v29; // rax
  HANDLE v30; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall *v34)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // [rsp+40h] [rbp-C0h]
  __int64 v35; // [rsp+48h] [rbp-B8h]
  DWORD dwFileAttributes; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME ftCreationTime; // [rsp+54h] [rbp-ACh]
  FILETIME ftLastAccessTime; // [rsp+5Ch] [rbp-A4h]
  FILETIME ftLastWriteTime; // [rsp+64h] [rbp-9Ch]
  int v40; // [rsp+6Ch] [rbp-94h]
  DWORD nFileSizeLow; // [rsp+70h] [rbp-90h]
  DWORD nFileSizeHigh; // [rsp+74h] [rbp-8Ch]
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  PCNZWCH v44[2]; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v45)(DWORD *, __int64); // [rsp+90h] [rbp-70h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a3;
  v45 = a3;
  v34 = a2;
  v35 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v32 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v9 = 87;
    goto LABEL_60;
  }
  if ( (unsigned int)ReparsePointExists(lpFileName, &v32) && v32 )
  {
    LODWORD(hFindFile) = 0;
    if ( (a5 & 2) != 0 )
      goto LABEL_11;
    if ( (unsigned int)ShouldEnumerateReparsePoint(lpFileName, &hFindFile) && (_DWORD)hFindFile )
      goto LABEL_15;
    LODWORD(hFindFile) = 0;
    if ( (a5 & 1) != 0 )
    {
LABEL_11:
      SetLastError(0);
      return 1;
    }
    if ( (unsigned int)GetReparseTag(lpFileName) )
    {
      if ( (_DWORD)hFindFile != -2147483640 )
        goto LABEL_11;
      goto LABEL_15;
    }
    LastError = GetLastError();
    if ( (unsigned int)ReparsePointExists(lpFileName, &v32) && v32 )
    {
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x",
        LastError);
      v9 = LastError;
LABEL_60:
      SetLastError(v9);
      return 0;
    }
  }
LABEL_15:
  v10 = 0;
  v11 = (const wchar_t *)BuildPath(lpFileName, L"*");
  v12 = (wchar_t *)v11;
  if ( !v11 || (v13 = (const WCHAR *)PrepareUnicodePathEx(v11), (v10 = (WCHAR *)v13) == 0) )
  {
    v26 = GetLastError();
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x",
      lpFileName,
      v26);
    v14 = 0;
    if ( v12 )
      goto LABEL_55;
    goto LABEL_56;
  }
  v14 = 0;
  v15 = -1;
  hFindFile = FindFirstFileW(v13, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v26 = GetLastError();
    LibLog(&g_WdsLibLog, 0x2000000, L"EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x", v10, v26);
    do
      ++v15;
    while ( v10[v15] );
    if ( v15 >= 0x104 )
    {
      LibLog(&g_WdsLibLog, 50331648, L"EnumeratePathEx: Failed search path is >= MAX_PATH!");
      v26 = 206;
    }
    goto LABEL_55;
  }
  memset_0(&dwFileAttributes, 0, 0x40u);
  do
  {
    v16 = 0;
    if ( !*lpFileName )
    {
      SetLastError(0x57u);
      goto LABEL_37;
    }
    dwFileAttributes = FindFileData.dwFileAttributes;
    ftCreationTime = FindFileData.ftCreationTime;
    ftLastAccessTime = FindFileData.ftLastAccessTime;
    ftLastWriteTime = FindFileData.ftLastWriteTime;
    nFileSizeLow = FindFileData.nFileSizeLow;
    nFileSizeHigh = FindFileData.nFileSizeHigh;
    v40 = 0;
    lpMem = 0;
    *(_OWORD *)v44 = 0;
    v17 = (void *)BuildPath(lpFileName, FindFileData.cFileName);
    lpMem = v17;
    if ( v17
      && ((v18 = wcsrchr((const wchar_t *)v17, 0x5Cu)) == 0 ? (v19 = (const WCHAR *)lpMem) : (v19 = v18 + 1),
          v44[0] = v19,
          (v44[1] = (PCNZWCH)FormFullPathName((LPCWSTR)lpMem)) != 0) )
    {
      v16 = 1;
    }
    else
    {
      FreeWdslibFindData(&dwFileAttributes);
    }
    if ( v16 == 1 )
    {
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( !v5 )
          goto LABEL_37;
        v20 = v5(&dwFileAttributes, v35);
        goto LABEL_33;
      }
      if ( v34
        && CompareStringW(0x409u, 1u, L".", -1, v44[0], -1) != 2
        && CompareStringW(0x409u, 1u, L"..", -1, v44[0], -1) != 2 )
      {
        v20 = v34(&dwFileAttributes, (__int64 (__fastcall *)(_QWORD, _QWORD))v5, v35);
LABEL_33:
        v16 = v20;
      }
    }
LABEL_37:
    v21 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      if ( HeapFree(ProcessHeap, 0, v21) )
        lpMem = 0;
    }
    v23 = (WCHAR *)v44[1];
    if ( v44[1] )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v23);
    }
    memset_0(&dwFileAttributes, 0, 0x40u);
    if ( v16 != 1 )
    {
      v27 = GetLastError();
      v28 = L"EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x";
      goto LABEL_48;
    }
    NextFileW = FindNextFileW(hFindFile, &FindFileData);
    v5 = v45;
  }
  while ( NextFileW );
  if ( GetLastError() == 18 )
  {
    v14 = 1;
    v26 = 0;
    goto LABEL_49;
  }
  v27 = GetLastError();
  v28 = L"EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x";
LABEL_48:
  LODWORD(lpString2) = v27;
  v26 = v27;
  LibLog(&g_WdsLibLog, 0x2000000, v28, v10, lpString2);
LABEL_49:
  FindClose(hFindFile);
LABEL_55:
  v29 = GetProcessHeap();
  HeapFree(v29, 0, v12);
LABEL_56:
  if ( v10 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v10);
  }
  SetLastError(v26);
  return v14;
}

```

## disassembly

```asm
0x18000bb18  push    rbp
0x18000bb1a  push    rbx
0x18000bb1b  push    rsi
0x18000bb1c  push    rdi
0x18000bb1d  push    r12
0x18000bb1f  push    r13
0x18000bb21  push    r14
0x18000bb23  push    r15
0x18000bb25  lea     rbp, [rsp-208h]
0x18000bb2d  sub     rsp, 308h
0x18000bb34  mov     rax, cs:__security_cookie
0x18000bb3b  xor     rax, rsp
0x18000bb3e  mov     [rbp+240h+var_50], rax
0x18000bb45  mov     r15, r8
0x18000bb48  mov     [rbp+240h+var_2B0], r8
0x18000bb4c  mov     [rsp+340h+var_300], rdx
0x18000bb51  mov     rsi, rcx
0x18000bb54  xor     edx, edx; Val
0x18000bb56  mov     [rsp+340h+var_2F8], r9
0x18000bb5b  mov     r8d, 250h; Size
0x18000bb61  lea     rcx, [rbp+240h+FindFileData]; void *
0x18000bb65  call    memset_0
0x18000bb6a  xor     r14d, r14d
0x18000bb6d  mov     [rsp+340h+var_310], r14d
0x18000bb72  test    rsi, rsi
0x18000bb75  jz      loc_18000BF96
0x18000bb7b  cmp     r14w, [rsi]
0x18000bb7f  jz      loc_18000BF96
0x18000bb85  lea     rdx, [rsp+340h+var_310]
0x18000bb8a  mov     rcx, rsi
0x18000bb8d  call    ReparsePointExists
0x18000bb92  test    eax, eax
0x18000bb94  jz      loc_18000BC46
0x18000bb9a  cmp     [rsp+340h+var_310], r14d
0x18000bb9f  jz      loc_18000BC46
0x18000bba5  mov     ebx, [rbp+240h+arg_20]
0x18000bbab  mov     dword ptr [rsp+340h+hFindFile], r14d
0x18000bbb0  test    bl, 2
0x18000bbb3  jnz     short loc_18000BBF2
0x18000bbb5  lea     rdx, [rsp+340h+hFindFile]
0x18000bbba  mov     rcx, rsi
0x18000bbbd  call    ShouldEnumerateReparsePoint
0x18000bbc2  test    eax, eax
0x18000bbc4  jz      short loc_18000BBCD
0x18000bbc6  cmp     dword ptr [rsp+340h+hFindFile], r14d
0x18000bbcb  jnz     short loc_18000BC46
0x18000bbcd  mov     dword ptr [rsp+340h+hFindFile], r14d
0x18000bbd2  test    bl, 1
0x18000bbd5  jnz     short loc_18000BBF2
0x18000bbd7  lea     rdx, [rsp+340h+hFindFile]
0x18000bbdc  mov     rcx, rsi; lpFileName
0x18000bbdf  call    GetReparseTag
0x18000bbe4  test    eax, eax
0x18000bbe6  jz      short loc_18000BC04
0x18000bbe8  cmp     dword ptr [rsp+340h+hFindFile], 80000008h
0x18000bbf0  jz      short loc_18000BC46
0x18000bbf2  xor     ecx, ecx; dwErrCode
0x18000bbf4  call    cs:__imp_SetLastError
0x18000bbfa  mov     eax, 1
0x18000bbff  jmp     loc_18000BFA3
0x18000bc04  call    cs:__imp_GetLastError
0x18000bc0a  lea     rdx, [rsp+340h+var_310]
0x18000bc0f  mov     rcx, rsi
0x18000bc12  mov     ebx, eax
0x18000bc14  call    ReparsePointExists
0x18000bc19  test    eax, eax
0x18000bc1b  jz      short loc_18000BC46
0x18000bc1d  cmp     [rsp+340h+var_310], r14d
0x18000bc22  jz      short loc_18000BC46
0x18000bc24  mov     r9d, ebx
0x18000bc27  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x18000bc2e  mov     edx, 2000000h
0x18000bc33  lea     rcx, g_WdsLibLog
0x18000bc3a  call    LibLog
0x18000bc3f  mov     ecx, ebx
0x18000bc41  jmp     loc_18000BF9B
0x18000bc46  lea     rdx, asc_180019E88; "*"
0x18000bc4d  mov     rcx, rsi; pszSrc
0x18000bc50  mov     rdi, r14
0x18000bc53  call    BuildPath
0x18000bc58  mov     r12, rax
0x18000bc5b  test    rax, rax
0x18000bc5e  jz      loc_18000BF2D
0x18000bc64  xor     edx, edx
0x18000bc66  mov     rcx, rax; pszSrc
0x18000bc69  call    PrepareUnicodePathEx
0x18000bc6e  mov     rdi, rax
0x18000bc71  test    rax, rax
0x18000bc74  jz      loc_18000BF2D
0x18000bc7a  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x18000bc7e  mov     rcx, rax; lpFileName
0x18000bc81  mov     r13d, r14d
0x18000bc84  call    cs:__imp_FindFirstFileW
0x18000bc8a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000bc8e  mov     [rsp+340h+hFindFile], rax
0x18000bc93  cmp     rax, r14
0x18000bc96  jz      loc_18000BED2
0x18000bc9c  xor     edx, edx; Val
0x18000bc9e  lea     r8d, [r14+41h]; Size
0x18000bca2  lea     rcx, [rsp+340h+var_2F0]; void *
0x18000bca7  call    memset_0
0x18000bcac  xor     ebx, ebx
0x18000bcae  cmp     bx, [rsi]
0x18000bcb1  jz      loc_18000BDF3
0x18000bcb7  mov     eax, [rbp+240h+FindFileData.dwFileAttributes]
0x18000bcba  lea     rdx, [rbp+240h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x18000bcbe  mov     [rsp+340h+var_2F0], eax
0x18000bcc2  xorps   xmm0, xmm0
0x18000bcc5  mov     rax, qword ptr [rbp+240h+FindFileData.ftCreationTime.dwLowDateTime]
0x18000bcc9  mov     rcx, rsi; pszSrc
0x18000bccc  mov     [rsp+340h+var_2EC], rax
0x18000bcd1  mov     rax, qword ptr [rbp+240h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x18000bcd5  mov     [rsp+340h+var_2E4], rax
0x18000bcda  mov     rax, qword ptr [rbp+240h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000bcde  mov     [rsp+340h+var_2DC], rax
0x18000bce3  mov     eax, [rbp+240h+FindFileData.nFileSizeLow]
0x18000bce6  mov     [rsp+340h+var_2D0], eax
0x18000bcea  mov     eax, [rbp+240h+FindFileData.nFileSizeHigh]
0x18000bced  mov     [rsp+340h+var_2CC], eax
0x18000bcf1  mov     [rsp+340h+var_2D4], ebx
0x18000bcf5  mov     [rsp+340h+lpMem], rbx
0x18000bcfa  movdqa  xmmword ptr [rbp+240h+var_2C0], xmm0
0x18000bcff  call    BuildPath
0x18000bd04  mov     [rsp+340h+lpMem], rax
0x18000bd09  test    rax, rax
0x18000bd0c  jz      short loc_18000BD46
0x18000bd0e  lea     edx, [rbx+5Ch]; Ch
0x18000bd11  mov     rcx, rax; Str
0x18000bd14  call    cs:__imp_wcsrchr
0x18000bd1a  mov     rcx, [rsp+340h+lpMem]; lpFileName
0x18000bd1f  test    rax, rax
0x18000bd22  jz      short loc_18000BD2A
0x18000bd24  add     rax, 2
0x18000bd28  jmp     short loc_18000BD2D
0x18000bd2a  mov     rax, rcx
0x18000bd2d  mov     [rbp+240h+var_2C0], rax
0x18000bd31  call    FormFullPathName
0x18000bd36  mov     [rbp+240h+var_2C0+8], rax
0x18000bd3a  test    rax, rax
0x18000bd3d  jz      short loc_18000BD46
0x18000bd3f  mov     ebx, 1
0x18000bd44  jmp     short loc_18000BD50
0x18000bd46  lea     rcx, [rsp+340h+var_2F0]; void *
0x18000bd4b  call    FreeWdslibFindData
0x18000bd50  cmp     ebx, 1
0x18000bd53  jnz     loc_18000BDFE
0x18000bd59  test    byte ptr [rsp+340h+var_2F0], 10h
0x18000bd5e  jz      short loc_18000BDDA
0x18000bd60  cmp     [rsp+340h+var_300], r13
0x18000bd65  jz      loc_18000BDFE
0x18000bd6b  mov     rax, [rbp+240h+var_2C0]
0x18000bd6f  lea     r8, String1; "."
0x18000bd76  mov     [rsp+340h+cchCount2], r14d; cchCount2
0x18000bd7b  mov     r9d, r14d; cchCount1
0x18000bd7e  mov     edx, ebx; dwCmpFlags
0x18000bd80  mov     [rsp+340h+lpString2], rax; lpString2
0x18000bd85  mov     ecx, 409h; Locale
0x18000bd8a  call    cs:__imp_CompareStringW
0x18000bd90  cmp     eax, 2
0x18000bd93  jz      short loc_18000BDFE
0x18000bd95  mov     rax, [rbp+240h+var_2C0]
0x18000bd99  lea     r8, asc_180019E90; ".."
0x18000bda0  mov     [rsp+340h+cchCount2], r14d; cchCount2
0x18000bda5  mov     r9d, r14d; cchCount1
0x18000bda8  mov     edx, ebx; dwCmpFlags
0x18000bdaa  mov     [rsp+340h+lpString2], rax; lpString2
0x18000bdaf  mov     ecx, 409h; Locale
0x18000bdb4  call    cs:__imp_CompareStringW
0x18000bdba  cmp     eax, 2
0x18000bdbd  jz      short loc_18000BDFE
0x18000bdbf  mov     r8, [rsp+340h+var_2F8]
0x18000bdc4  lea     rcx, [rsp+340h+var_2F0]
0x18000bdc9  mov     rax, [rsp+340h+var_300]
0x18000bdce  mov     rdx, r15
0x18000bdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdd6  mov     ebx, eax
0x18000bdd8  jmp     short loc_18000BDFE
0x18000bdda  test    r15, r15
0x18000bddd  jz      short loc_18000BDFE
0x18000bddf  mov     rdx, [rsp+340h+var_2F8]
0x18000bde4  lea     rcx, [rsp+340h+var_2F0]
0x18000bde9  mov     rax, r15
0x18000bdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf1  jmp     short loc_18000BDD6
0x18000bdf3  mov     ecx, 57h ; 'W'; dwErrCode
0x18000bdf8  call    cs:__imp_SetLastError
0x18000bdfe  mov     r15, [rsp+340h+lpMem]
0x18000be03  test    r15, r15
0x18000be06  jz      short loc_18000BE28
0x18000be08  call    cs:__imp_GetProcessHeap
0x18000be0e  mov     r8, r15; lpMem
0x18000be11  xor     edx, edx; dwFlags
0x18000be13  mov     rcx, rax; hHeap
0x18000be16  call    cs:__imp_HeapFree
0x18000be1c  xor     r15d, r15d
0x18000be1f  test    eax, eax
0x18000be21  jz      short loc_18000BE28
0x18000be23  mov     [rsp+340h+lpMem], r15
0x18000be28  mov     r15, [rbp+240h+var_2C0+8]
0x18000be2c  test    r15, r15
0x18000be2f  jz      short loc_18000BE45
0x18000be31  call    cs:__imp_GetProcessHeap
0x18000be37  mov     r8, r15; lpMem
0x18000be3a  xor     edx, edx; dwFlags
0x18000be3c  mov     rcx, rax; hHeap
0x18000be3f  call    cs:__imp_HeapFree
0x18000be45  xor     edx, edx; Val
0x18000be47  lea     rcx, [rsp+340h+var_2F0]; void *
0x18000be4c  lea     r8d, [rdx+40h]; Size
0x18000be50  call    memset_0
0x18000be55  cmp     ebx, 1
0x18000be58  jnz     short loc_18000BE9B
0x18000be5a  mov     rcx, [rsp+340h+hFindFile]; hFindFile
0x18000be5f  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x18000be63  call    cs:__imp_FindNextFileW
0x18000be69  mov     r15, [rbp+240h+var_2B0]
0x18000be6d  cmp     eax, ebx
0x18000be6f  jz      loc_18000BCAC
0x18000be75  call    cs:__imp_GetLastError
0x18000be7b  cmp     eax, 12h
0x18000be7e  jnz     short loc_18000BE8C
0x18000be80  xor     r14d, r14d
0x18000be83  lea     r13d, [rax-11h]
0x18000be87  mov     ebx, r14d
0x18000be8a  jmp     short loc_18000BEC2
0x18000be8c  call    cs:__imp_GetLastError
0x18000be92  lea     r8, aEnumeratepathe_4; "EnumeratePathEx: Unable to enumerate [%"...
0x18000be99  jmp     short loc_18000BEA8
0x18000be9b  call    cs:__imp_GetLastError
0x18000bea1  lea     r8, aEnumeratepathe_1; "EnumeratePathEx: Callback requested enu"...
0x18000bea8  mov     r9, rdi
0x18000beab  mov     dword ptr [rsp+340h+lpString2], eax
0x18000beaf  mov     edx, 2000000h
0x18000beb4  lea     rcx, g_WdsLibLog
0x18000bebb  mov     ebx, eax
0x18000bebd  call    LibLog
0x18000bec2  mov     rcx, [rsp+340h+hFindFile]; hFindFile
0x18000bec7  call    cs:__imp_FindClose
0x18000becd  jmp     loc_18000BF5C
0x18000bed2  call    cs:__imp_GetLastError
0x18000bed8  mov     r9, rdi
0x18000bedb  lea     r8, aEnumeratepathe_3; "EnumeratePathEx: FindFirstFile failed f"...
0x18000bee2  lea     rcx, g_WdsLibLog
0x18000bee9  mov     dword ptr [rsp+340h+lpString2], eax
0x18000beed  mov     edx, 2000000h
0x18000bef2  mov     ebx, eax
0x18000bef4  call    LibLog
0x18000bef9  xor     eax, eax
0x18000befb  inc     r14
0x18000befe  cmp     [rdi+r14*2], ax
0x18000bf03  jnz     short loc_18000BEFB
0x18000bf05  cmp     r14, 104h
0x18000bf0c  jb      short loc_18000BF5C
0x18000bf0e  lea     r8, aEnumeratepathe; "EnumeratePathEx: Failed search path is "...
0x18000bf15  mov     edx, 3000000h
0x18000bf1a  lea     rcx, g_WdsLibLog
0x18000bf21  call    LibLog
0x18000bf26  mov     ebx, 0CEh
0x18000bf2b  jmp     short loc_18000BF5C
0x18000bf2d  call    cs:__imp_GetLastError
0x18000bf33  mov     r9, rsi
0x18000bf36  lea     r8, aEnumeratepathe_2; "EnumeratePathEx: Unable to construct pa"...
0x18000bf3d  lea     rcx, g_WdsLibLog
0x18000bf44  mov     dword ptr [rsp+340h+lpString2], eax
0x18000bf48  mov     edx, 2000000h
0x18000bf4d  mov     ebx, eax
0x18000bf4f  call    LibLog
0x18000bf54  mov     r13d, r14d
0x18000bf57  test    r12, r12
0x18000bf5a  jz      short loc_18000BF70
0x18000bf5c  call    cs:__imp_GetProcessHeap
0x18000bf62  mov     r8, r12; lpMem
0x18000bf65  xor     edx, edx; dwFlags
0x18000bf67  mov     rcx, rax; hHeap
0x18000bf6a  call    cs:__imp_HeapFree
0x18000bf70  test    rdi, rdi
0x18000bf73  jz      short loc_18000BF89
0x18000bf75  call    cs:__imp_GetProcessHeap
0x18000bf7b  mov     r8, rdi; lpMem
0x18000bf7e  xor     edx, edx; dwFlags
0x18000bf80  mov     rcx, rax; hHeap
0x18000bf83  call    cs:__imp_HeapFree
0x18000bf89  mov     ecx, ebx; dwErrCode
0x18000bf8b  call    cs:__imp_SetLastError
0x18000bf91  mov     eax, r13d
0x18000bf94  jmp     short loc_18000BFA3
0x18000bf96  mov     ecx, 57h ; 'W'; dwErrCode
0x18000bf9b  call    cs:__imp_SetLastError
0x18000bfa1  xor     eax, eax
0x18000bfa3  mov     rcx, [rbp+240h+var_50]
0x18000bfaa  xor     rcx, rsp; StackCookie
0x18000bfad  call    __security_check_cookie
0x18000bfb2  add     rsp, 308h
0x18000bfb9  pop     r15
0x18000bfbb  pop     r14
0x18000bfbd  pop     r13
0x18000bfbf  pop     r12
0x18000bfc1  pop     rdi
0x18000bfc2  pop     rsi
0x18000bfc3  pop     rbx
  ... truncated ...
```
