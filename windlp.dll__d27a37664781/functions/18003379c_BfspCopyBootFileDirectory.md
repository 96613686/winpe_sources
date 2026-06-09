# BfspCopyBootFileDirectory

- ea: `0x18003379c`
- end: `0x180033ea8`
- name: `BfspCopyBootFileDirectory`
- size: `1804`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180032518`
- `0x18003379c`
- `0x180034c80`

## callees

- `0x180031598`
- `0x180031864`
- `0x18003206c`
- `0x1800323e0`
- `0x18003379c`
- `0x180033eb0`
- `0x18003527c`
- `0x18003538c`
- `0x180035b6c`
- `0x180035c20`
- `0x1800366b8`
- `0x180036ca8`
- `0x18003bcd8`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180033cc1`
- `msvcrt!_wcsicmp` at `0x180033cd5`
- `msvcrt!_wcsicmp` at `0x180033d99`
- `msvcrt!_wcsicmp` at `0x180033dae`
- `msvcrt!_wcsicmp` at `0x180033cc1`
- `msvcrt!_wcsicmp` at `0x180033cd5`
- `msvcrt!_wcsicmp` at `0x180033d99`
- `msvcrt!_wcsicmp` at `0x180033dae`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033c52`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033c52`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800339cf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800339cf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180033e69`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180033e69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033810`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003385e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800338a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033c01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033c35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033810`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003385e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800338a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033c01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033c35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033823`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003386c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800338b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033823`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003386c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800338b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033c43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033c5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e82`

## string_xrefs

- `0x180033e8b`: `Error copying %s to %s. Last Error = %#x`
- `0x1800339fa`: `Error creating %s path! Last Error = %#x`
- `0x180033dd1`: `Source, %s, is older than destination, %s, will not update`

## pseudocode

```c
__int64 __fastcall BfspCopyBootFileDirectory(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v11; // r12
  __int64 v12; // rax
  unsigned __int64 v13; // r15
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  unsigned int Path; // edi
  __int64 v18; // rax
  unsigned __int64 v19; // rdi
  SIZE_T v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // r12
  SIZE_T v24; // rbx
  HANDLE v25; // rax
  unsigned __int16 *v26; // r13
  wchar_t *v27; // rsi
  __int64 v28; // rax
  unsigned __int16 *v29; // r15
  __int64 v30; // rax
  const WCHAR *v31; // rdi
  __int64 v32; // rbx
  const wchar_t *v33; // rdx
  __int64 v34; // rcx
  unsigned __int16 *v35; // rax
  const wchar_t *v36; // r8
  __int64 v37; // rdx
  unsigned __int16 *v38; // rcx
  __int64 v39; // r10
  const wchar_t *v40; // rbx
  unsigned __int16 *v41; // r10
  WCHAR *cFileName; // r8
  __int64 v43; // rdx
  __int64 v44; // rcx
  wchar_t *v45; // rax
  wchar_t *v46; // rcx
  __int64 v47; // r8
  WCHAR *v48; // r9
  __int64 v49; // rdx
  unsigned __int16 *v50; // rax
  unsigned __int16 *v51; // rcx
  STRSAFE_LPWSTR v52; // rax
  WCHAR *v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rdx
  STRSAFE_LPWSTR v56; // rcx
  HANDLE v57; // rax
  HANDLE v58; // rax
  HANDLE v59; // rax
  __int64 v61; // rax
  size_t v62; // rdx
  unsigned __int64 v63; // rcx
  WCHAR *v64; // rbx
  int ThreadPagePriority; // ebx
  __int64 v66; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *lpFileName; // [rsp+48h] [rbp-B8h]
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *lpMem; // [rsp+68h] [rbp-98h]
  int v73; // [rsp+70h] [rbp-90h]
  unsigned __int16 *i; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(a1 + 2 * v12) );
  v13 = v12 + 262;
  v14 = 2 * (v12 + 262);
  ProcessHeap = GetProcessHeap();
  LODWORD(LastError) = 8;
  lpFileName = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v14);
  if ( !lpFileName )
  {
    Path = 0;
    goto LABEL_78;
  }
  if ( a2 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(a2 + 2 * v18) );
    v19 = v18 + 262;
    v20 = 2 * (v18 + 262);
    v21 = GetProcessHeap();
    lpMem = (unsigned __int16 *)HeapAlloc(v21, 8u, v20);
    if ( !lpMem )
    {
      Path = 0;
      goto LABEL_73;
    }
  }
  else
  {
    lpMem = 0;
    v19 = 0;
  }
  v22 = -1;
  do
    ++v22;
  while ( a3[v22] );
  v23 = v22 + 262;
  v24 = 2 * (v22 + 262);
  v25 = GetProcessHeap();
  v26 = (unsigned __int16 *)HeapAlloc(v25, 8u, v24);
  if ( !v26 )
  {
    v11 = -1;
    Path = 0;
    goto LABEL_73;
  }
  v27 = lpFileName;
  pszDest = 0;
  StringCchPrintfW(lpFileName, v13, L"%s\\", a1);
  v28 = -1;
  do
    ++v28;
  while ( lpFileName[v28] );
  v29 = &lpFileName[v28];
  if ( a2 )
  {
    StringCchPrintfW(lpMem, v19, L"%s\\", a2);
    v30 = -1;
    do
      ++v30;
    while ( lpMem[v30] );
    pszDest = &lpMem[v30];
  }
  v31 = a3;
  StringCchPrintfW(v26, v23, L"%s\\", a3);
  v32 = -1;
  do
    ++v32;
  while ( v26[v32] );
  v33 = L"*";
  v34 = 2147483646;
  if ( a4 )
    v33 = a4;
  v35 = v29;
  v73 = (int)v33;
  v36 = v33;
  v37 = 261;
  do
  {
    if ( !v34 )
      break;
    if ( !*v36 )
      break;
    *v35++ = *v36++;
    --v34;
    --v37;
  }
  while ( v37 );
  v38 = v35 - 1;
  if ( v37 )
    v38 = v35;
  *v38 = 0;
  hFindFile = FindFirstFileW(lpFileName, &FindFileData);
  v11 = (__int64)hFindFile;
  if ( hFindFile != (HANDLE)-1LL )
  {
    Path = CreatePath(a3);
    if ( !Path )
    {
      LastError = GetLastError();
      BfspLogMessage(4, L"Error creating %s path! Last Error = %#x", v26, LastError);
      goto LABEL_72;
    }
    v31 = a3;
  }
  if ( a6 && (Path = BfspSetFileDirectorySecurityDescriptor(v31)) == 0 || (Path = BfspSetAttributes(a3, 0x80u)) == 0 )
  {
    LODWORD(LastError) = GetLastError();
    goto LABEL_72;
  }
  v39 = v32;
  v40 = v29;
  v41 = &v26[v39];
  for ( i = v41; ; v41 = i )
  {
    cFileName = FindFileData.cFileName;
    v43 = 261;
    v44 = 2147483646;
    v45 = (wchar_t *)v40;
    do
    {
      if ( !v44 )
        break;
      if ( !*cFileName )
        break;
      *v45++ = *cFileName++;
      --v44;
      --v43;
    }
    while ( v43 );
    v46 = v45 - 1;
    v47 = 2147483646;
    v48 = FindFileData.cFileName;
    if ( v43 )
      v46 = v45;
    v49 = 261;
    v50 = v41;
    *v46 = 0;
    do
    {
      if ( !v47 )
        break;
      if ( !*v48 )
        break;
      *v50++ = *v48++;
      --v47;
      --v49;
    }
    while ( v49 );
    v51 = v50 - 1;
    if ( v49 )
      v51 = v50;
    *v51 = 0;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    if ( a2 )
    {
      v52 = pszDest;
      v53 = FindFileData.cFileName;
      v54 = 2147483646;
      v55 = 261;
      do
      {
        if ( !v54 )
          break;
        if ( !*v53 )
          break;
        *v52++ = *v53++;
        --v54;
        --v55;
      }
      while ( v55 );
      v56 = v52 - 1;
      if ( v55 )
        v56 = v52;
      *v56 = 0;
    }
    if ( a8
      && (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
    {
      Path = BfspCopyBootFileDirectory((_DWORD)v27, (_DWORD)lpMem, (_DWORD)v26, v73, a5, a6, a7, a8);
      if ( !Path )
        goto LABEL_67;
    }
LABEL_111:
    Path = FindNextFileW(hFindFile, &FindFileData);
    if ( !Path )
      goto LABEL_67;
  }
  if ( a2 )
    *pszDest = 0;
  if ( a7 )
  {
    v61 = -1;
    do
      ++v61;
    while ( v40[v61] );
    if ( (unsigned int)v61 < 4 || _wcsicmp(&v40[(unsigned int)v61 - 4], L".mui") )
    {
      if ( _wcsicmp(v40, L"bootfix.bin") )
        goto LABEL_111;
    }
  }
  if ( a6 )
  {
    Path = BfspSetFileDirectorySecurityDescriptor(v26);
    if ( !Path && GetLastError() != 2 )
      goto LABEL_67;
  }
  if ( a2 )
  {
    v62 = 0;
    v63 = -1;
    do
      ++v63;
    while ( FindFileData.cFileName[v63] );
    if ( v63 )
    {
      while ( 1 )
      {
        v64 = &FindFileData.cFileName[(unsigned int)v62];
        if ( *v64 == 46 )
          break;
        v62 = (unsigned int)(v62 + 1);
        if ( (unsigned int)v62 >= v63 )
          goto LABEL_99;
      }
      StringCchCatNW(pszDest, v62, FindFileData.cFileName, (unsigned int)v62);
      StringCchCatW(pszDest, 0x105u, L"_EX");
      StringCchCatW(pszDest, 0x105u, v64);
    }
LABEL_99:
    if ( (unsigned int)BfspFileExists(lpMem) )
      v27 = lpMem;
  }
  if ( !_wcsicmp(FindFileData.cFileName, L"boot.stl") || !_wcsicmp(FindFileData.cFileName, L"boot.pnd.stl") )
    goto LABEL_106;
  if ( !(unsigned int)BfspShouldFileBeCopied(v27) )
  {
    BfspLogMessage(3, L"Source, %s, is older than destination, %s, will not update", v27, v26);
    goto LABEL_106;
  }
  ThreadPagePriority = BfspGetThreadPagePriority();
  BfspSetThreadPagePriority(1);
  Path = BfspCopyFile(v27, v26);
  BfspSetThreadPagePriority(ThreadPagePriority);
  if ( Path )
  {
LABEL_106:
    if ( (unsigned int)BfspFileExists(v26) )
    {
      Path = BfspSetAttributes(v26, 0x80u);
      if ( !Path )
        goto LABEL_67;
      if ( a6 )
      {
        Path = BfspSetFileDirectorySecurityDescriptor(v26);
        if ( !Path )
          goto LABEL_67;
      }
    }
    v27 = lpFileName;
    v40 = v29;
    goto LABEL_111;
  }
  LODWORD(v66) = GetLastError();
  BfspLogMessage(4, L"Error copying %s to %s. Last Error = %#x", v27, v26, v66);
LABEL_67:
  if ( GetLastError() != 18
    || (Path = 1, LODWORD(LastError) = 0, a6) && (Path = BfspSetFileDirectorySecurityDescriptor(a3)) == 0 )
  {
    LODWORD(LastError) = GetLastError();
  }
  v11 = (__int64)hFindFile;
LABEL_72:
  v57 = GetProcessHeap();
  HeapFree(v57, 0, v26);
LABEL_73:
  v58 = GetProcessHeap();
  HeapFree(v58, 0, lpFileName);
  if ( lpMem )
  {
    v59 = GetProcessHeap();
    HeapFree(v59, 0, lpMem);
  }
  if ( v11 != -1 )
    FindClose((HANDLE)v11);
  if ( !Path )
LABEL_78:
    SetLastError(LastError);
  return Path;
}

```

## disassembly

```asm
0x18003379c  push    rbp
0x18003379e  push    rbx
0x18003379f  push    rsi
0x1800337a0  push    rdi
0x1800337a1  push    r12
0x1800337a3  push    r13
0x1800337a5  push    r14
0x1800337a7  push    r15
0x1800337a9  lea     rbp, [rsp-1F8h]
0x1800337b1  sub     rsp, 2F8h
0x1800337b8  mov     rax, cs:__security_cookie
0x1800337bf  xor     rax, rsp
0x1800337c2  mov     [rbp+230h+var_50], rax
0x1800337c9  mov     r13, r8
0x1800337cc  mov     [rsp+330h+var_2D0], r8
0x1800337d1  mov     rdi, rdx
0x1800337d4  mov     [rsp+330h+var_2B8], rdx
0x1800337d9  mov     r14, rcx
0x1800337dc  mov     [rsp+330h+var_2C0], r9
0x1800337e1  xor     edx, edx; Val
0x1800337e3  lea     rcx, [rbp+230h+FindFileData]; void *
0x1800337e7  mov     r8d, 250h; Size
0x1800337ed  call    memset_0
0x1800337f2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800337f6  mov     rax, r12
0x1800337f9  xor     ecx, ecx
0x1800337fb  inc     rax
0x1800337fe  cmp     [r14+rax*2], cx
0x180033803  jnz     short loc_1800337FB
0x180033805  lea     r15, [rax+106h]
0x18003380c  lea     rbx, [r15+r15]
0x180033810  call    cs:__imp_GetProcessHeap
0x180033816  mov     esi, 8
0x18003381b  mov     r8, rbx; dwBytes
0x18003381e  mov     rcx, rax; hHeap
0x180033821  mov     edx, esi; dwFlags
0x180033823  call    cs:__imp_HeapAlloc
0x180033829  xor     edx, edx
0x18003382b  mov     [rsp+330h+lpFileName], rax
0x180033830  test    rax, rax
0x180033833  jnz     short loc_18003383C
0x180033835  mov     edi, edx
0x180033837  jmp     loc_180033C5C
0x18003383c  mov     [rsp+330h+hFindFile], r12
0x180033841  test    rdi, rdi
0x180033844  jz      short loc_180033885
0x180033846  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003384a  inc     rax
0x18003384d  cmp     [rdi+rax*2], dx
0x180033851  jnz     short loc_18003384A
0x180033853  lea     rdi, [rax+106h]
0x18003385a  lea     rbx, [rdi+rdi]
0x18003385e  call    cs:__imp_GetProcessHeap
0x180033864  mov     r8, rbx; dwBytes
0x180033867  mov     edx, esi; dwFlags
0x180033869  mov     rcx, rax; hHeap
0x18003386c  call    cs:__imp_HeapAlloc
0x180033872  xor     edx, edx
0x180033874  mov     [rsp+330h+lpMem], rax
0x180033879  test    rax, rax
0x18003387c  jnz     short loc_18003388D
0x18003387e  mov     edi, edx
0x180033880  jmp     loc_180033C15
0x180033885  mov     [rsp+330h+lpMem], rdx
0x18003388a  mov     rdi, rdx
0x18003388d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033891  inc     rax
0x180033894  cmp     [r13+rax*2+0], dx
0x18003389a  jnz     short loc_180033891
0x18003389c  lea     r12, [rax+106h]
0x1800338a3  lea     rbx, [r12+r12]
0x1800338a7  call    cs:__imp_GetProcessHeap
0x1800338ad  mov     r8, rbx; dwBytes
0x1800338b0  mov     edx, esi; dwFlags
0x1800338b2  mov     rcx, rax; hHeap
0x1800338b5  call    cs:__imp_HeapAlloc
0x1800338bb  xor     ebx, ebx
0x1800338bd  mov     r13, rax
0x1800338c0  test    rax, rax
0x1800338c3  jnz     short loc_1800338D1
0x1800338c5  mov     r12, [rsp+330h+hFindFile]
0x1800338ca  mov     edi, ebx
0x1800338cc  jmp     loc_180033C15
0x1800338d1  mov     rsi, [rsp+330h+lpFileName]
0x1800338d6  lea     r8, aS_3; "%s\\"
0x1800338dd  mov     rcx, rsi; unsigned __int16 *
0x1800338e0  mov     [rsp+330h+pszDest], rbx
0x1800338e5  mov     r9, r14
0x1800338e8  mov     rdx, r15; unsigned __int64
0x1800338eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800338f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800338f4  inc     rax
0x1800338f7  cmp     [rsi+rax*2], bx
0x1800338fb  jnz     short loc_1800338F4
0x1800338fd  mov     r14, [rsp+330h+lpMem]
0x180033902  lea     r15, [rsi+rax*2]
0x180033906  mov     rax, [rsp+330h+var_2B8]
0x18003390b  mov     [rsp+330h+String1], r15
0x180033910  test    rax, rax
0x180033913  jz      short loc_180033941
0x180033915  mov     r9, rax
0x180033918  lea     r8, aS_3; "%s\\"
0x18003391f  mov     rdx, rdi; unsigned __int64
0x180033922  mov     rcx, r14; unsigned __int16 *
0x180033925  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003392a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003392e  inc     rax
0x180033931  cmp     [r14+rax*2], bx
0x180033936  jnz     short loc_18003392E
0x180033938  lea     rax, [r14+rax*2]
0x18003393c  mov     [rsp+330h+pszDest], rax
0x180033941  mov     rdi, [rsp+330h+var_2D0]
0x180033946  lea     r8, aS_3; "%s\\"
0x18003394d  mov     r9, rdi
0x180033950  mov     rdx, r12; unsigned __int64
0x180033953  mov     rcx, r13; unsigned __int16 *
0x180033956  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003395b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003395f  xor     r10d, r10d
0x180033962  inc     rbx
0x180033965  cmp     [r13+rbx*2+0], r10w
0x18003396b  jnz     short loc_180033962
0x18003396d  mov     rax, [rsp+330h+var_2C0]
0x180033972  lea     rdx, asc_1800850E8; "*"
0x180033979  test    rax, rax
0x18003397c  mov     ecx, 7FFFFFFEh
0x180033981  cmovnz  rdx, rax
0x180033985  mov     rax, r15
0x180033988  mov     [rsp+330h+var_2C0], rdx
0x18003398d  mov     r8, rdx
0x180033990  mov     edx, 105h
0x180033995  test    rcx, rcx
0x180033998  jz      short loc_1800339B9
0x18003399a  movzx   r9d, word ptr [r8]
0x18003399e  test    r9w, r9w
0x1800339a2  jz      short loc_1800339B9
0x1800339a4  mov     [rax], r9w
0x1800339a8  add     r8, 2
0x1800339ac  add     rax, 2
0x1800339b0  dec     rcx
0x1800339b3  sub     rdx, 1
0x1800339b7  jnz     short loc_180033995
0x1800339b9  test    rdx, rdx
0x1800339bc  lea     rcx, [rax-2]
0x1800339c0  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1800339c4  cmovnz  rcx, rax
0x1800339c8  mov     [rcx], r10w
0x1800339cc  mov     rcx, rsi; lpFileName
0x1800339cf  call    cs:__imp_FindFirstFileW
0x1800339d5  mov     [rsp+330h+hFindFile], rax
0x1800339da  mov     r12, rax
0x1800339dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800339e1  jz      short loc_180033A18
0x1800339e3  mov     rcx, rdi
0x1800339e6  call    CreatePath
0x1800339eb  mov     edi, eax
0x1800339ed  test    eax, eax
0x1800339ef  jnz     short loc_180033A13
0x1800339f1  call    cs:__imp_GetLastError
0x1800339f7  mov     r8, r13
0x1800339fa  lea     rdx, aErrorCreatingS; "Error creating %s path! Last Error = %#"...
0x180033a01  mov     r9d, eax
0x180033a04  lea     ecx, [rdi+4]
0x180033a07  mov     esi, eax
0x180033a09  call    BfspLogMessage
0x180033a0e  jmp     loc_180033C01
0x180033a13  mov     rdi, [rsp+330h+var_2D0]
0x180033a18  mov     r15d, [rbp+230h+arg_28]
0x180033a1f  test    r15d, r15d
0x180033a22  jz      short loc_180033A48
0x180033a24  lea     r8, aOSgSdPACiGaSA0; "O:%sG:%sD:P(A;CI;GA;;;%s)(A;;0x1201bf;;"...
0x180033a2b  xor     edx, edx
0x180033a2d  mov     rcx, rdi; lpFileName
0x180033a30  call    BfspSetFileDirectorySecurityDescriptor
0x180033a35  mov     edi, eax
0x180033a37  test    eax, eax
0x180033a39  jnz     short loc_180033A48
0x180033a3b  call    cs:__imp_GetLastError
0x180033a41  mov     esi, eax
0x180033a43  jmp     loc_180033C01
0x180033a48  mov     rcx, [rsp+330h+var_2D0]; lpFileName
0x180033a4d  mov     edx, 80h
0x180033a52  call    BfspSetAttributes
0x180033a57  mov     edi, eax
0x180033a59  test    eax, eax
0x180033a5b  jz      short loc_180033A3B
0x180033a5d  mov     r12, [rsp+330h+var_2B8]
0x180033a62  lea     r10, ds:0[rbx*2]
0x180033a6a  mov     rbx, [rsp+330h+String1]
0x180033a6f  add     r10, r13
0x180033a72  mov     [rbp+230h+var_2B0], r10
0x180033a76  mov     r11d, 105h
0x180033a7c  lea     r8, [rbp+230h+FindFileData.cFileName]
0x180033a80  mov     edx, r11d
0x180033a83  mov     ecx, 7FFFFFFEh
0x180033a88  mov     rax, rbx
0x180033a8b  xor     edi, edi
0x180033a8d  test    rcx, rcx
0x180033a90  jz      short loc_180033AB1
0x180033a92  movzx   r9d, word ptr [r8]
0x180033a96  test    r9w, r9w
0x180033a9a  jz      short loc_180033AB1
0x180033a9c  mov     [rax], r9w
0x180033aa0  add     r8, 2
0x180033aa4  add     rax, 2
0x180033aa8  dec     rcx
0x180033aab  sub     rdx, 1
0x180033aaf  jnz     short loc_180033A8D
0x180033ab1  test    rdx, rdx
0x180033ab4  lea     rcx, [rax-2]
0x180033ab8  mov     r8d, 7FFFFFFEh
0x180033abe  lea     r9, [rbp+230h+FindFileData.cFileName]
0x180033ac2  cmovnz  rcx, rax
0x180033ac6  mov     rdx, r11
0x180033ac9  mov     rax, r10
0x180033acc  mov     [rcx], di
0x180033acf  test    r8, r8
0x180033ad2  jz      short loc_180033AF1
0x180033ad4  movzx   ecx, word ptr [r9]
0x180033ad8  test    cx, cx
0x180033adb  jz      short loc_180033AF1
0x180033add  mov     [rax], cx
0x180033ae0  add     r9, 2
0x180033ae4  add     rax, 2
0x180033ae8  dec     r8
0x180033aeb  sub     rdx, 1
0x180033aef  jnz     short loc_180033ACF
0x180033af1  test    rdx, rdx
0x180033af4  lea     rcx, [rax-2]
0x180033af8  cmovnz  rcx, rax
0x180033afc  mov     [rcx], di
0x180033aff  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x180033b03  jz      loc_180033C89
0x180033b09  test    r12, r12
0x180033b0c  jz      short loc_180033B51
0x180033b0e  mov     rax, [rsp+330h+pszDest]
0x180033b13  lea     r8, [rbp+230h+FindFileData.cFileName]
0x180033b17  mov     ecx, 7FFFFFFEh
0x180033b1c  mov     rdx, r11
0x180033b1f  test    rcx, rcx
0x180033b22  jz      short loc_180033B43
0x180033b24  movzx   r9d, word ptr [r8]
0x180033b28  test    r9w, r9w
0x180033b2c  jz      short loc_180033B43
0x180033b2e  mov     [rax], r9w
0x180033b32  add     r8, 2
0x180033b36  add     rax, 2
0x180033b3a  dec     rcx
0x180033b3d  sub     rdx, 1
0x180033b41  jnz     short loc_180033B1F
0x180033b43  test    rdx, rdx
0x180033b46  lea     rcx, [rax-2]
0x180033b4a  cmovnz  rcx, rax
0x180033b4e  mov     [rcx], di
0x180033b51  mov     ecx, [rbp+230h+arg_38]
0x180033b57  test    ecx, ecx
0x180033b59  jz      loc_180033E60
0x180033b5f  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x180033b64  movzx   eax, [rbp+230h+FindFileData.cFileName+2]
0x180033b68  jnz     short loc_180033B8A
0x180033b6a  test    ax, ax
0x180033b6d  jz      loc_180033E60
0x180033b73  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x180033b78  jnz     short loc_180033B8A
0x180033b7a  cmp     ax, 2Eh ; '.'
0x180033b7e  jnz     short loc_180033B8A
0x180033b80  cmp     [rbp+230h+FindFileData.cFileName+4], di
0x180033b84  jz      loc_180033E60
0x180033b8a  mov     eax, [rbp+230h+arg_30]
0x180033b90  mov     r8, r13
0x180033b93  mov     r9, [rsp+330h+var_2C0]
0x180033b98  mov     rdx, r14
0x180033b9b  mov     [rsp+330h+var_2F8], ecx
0x180033b9f  mov     rcx, rsi
0x180033ba2  mov     [rsp+330h+var_300], eax
0x180033ba6  mov     eax, [rbp+230h+arg_20]
0x180033bac  mov     [rsp+330h+var_308], r15d
0x180033bb1  mov     dword ptr [rsp+330h+var_310], eax
0x180033bb5  call    BfspCopyBootFileDirectory
0x180033bba  mov     edi, eax
0x180033bbc  test    eax, eax
0x180033bbe  jnz     loc_180033E60
0x180033bc4  xor     ebx, ebx
0x180033bc6  call    cs:__imp_GetLastError
0x180033bcc  cmp     eax, 12h
0x180033bcf  jnz     short loc_180033BF4
0x180033bd1  lea     edi, [rax-11h]
0x180033bd4  mov     esi, ebx
0x180033bd6  test    r15d, r15d
0x180033bd9  jz      short loc_180033BFC
0x180033bdb  mov     rcx, [rsp+330h+var_2D0]; lpFileName
0x180033be0  lea     r8, aOSgSdPACiGaSA0; "O:%sG:%sD:P(A;CI;GA;;;%s)(A;;0x1201bf;;"...
0x180033be7  mov     edx, edi
0x180033be9  call    BfspSetFileDirectorySecurityDescriptor
0x180033bee  mov     edi, eax
0x180033bf0  test    eax, eax
0x180033bf2  jnz     short loc_180033BFC
0x180033bf4  call    cs:__imp_GetLastError
0x180033bfa  mov     esi, eax
0x180033bfc  mov     r12, [rsp+330h+hFindFile]
  ... truncated ...
```
