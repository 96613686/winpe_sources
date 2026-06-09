# EnumeratePathEx

- ea: `0x18003e138`
- end: `0x18003e7b7`
- name: `EnumeratePathEx`
- size: `1663`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18003e7c0`
- `0x18003eba8`

## callees

- `0x180010508`
- `0x18003d150`
- `0x18003ddfc`
- `0x18003de88`
- `0x18003df40`
- `0x18003e0e4`
- `0x18003e138`
- `0x18003f074`
- `0x18003f1a0`
- `0x18003f704`
- `0x18003fbfc`
- `0x1800607b0`
- `0x180060cee`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!FindClose` at `0x18003e651`
- `KERNEL32!FindClose` at `0x18003e651`
- `KERNEL32!FindNextFileW` at `0x18003e5dc`
- `KERNEL32!FindNextFileW` at `0x18003e5dc`
- `KERNEL32!FindFirstFileW` at `0x18003e3bd`
- `KERNEL32!FindFirstFileW` at `0x18003e3bd`
- `KERNEL32!HeapFree` at `0x18003e578`
- `KERNEL32!HeapFree` at `0x18003e5b0`
- `KERNEL32!HeapFree` at `0x18003e73c`
- `KERNEL32!HeapFree` at `0x18003e761`
- `KERNEL32!HeapFree` at `0x18003e578`
- `KERNEL32!HeapFree` at `0x18003e5b0`
- `KERNEL32!HeapFree` at `0x18003e73c`
- `KERNEL32!HeapFree` at `0x18003e761`
- `KERNEL32!GetLastError` at `0x18003e23c`
- `KERNEL32!GetLastError` at `0x18003e5f5`
- `KERNEL32!GetLastError` at `0x18003e60c`
- `KERNEL32!GetLastError` at `0x18003e621`
- `KERNEL32!GetLastError` at `0x18003e662`
- `KERNEL32!GetLastError` at `0x18003e6f6`
- `KERNEL32!GetLastError` at `0x18003e23c`
- `KERNEL32!GetLastError` at `0x18003e5f5`
- `KERNEL32!GetLastError` at `0x18003e60c`
- `KERNEL32!GetLastError` at `0x18003e621`
- `KERNEL32!GetLastError` at `0x18003e662`
- `KERNEL32!GetLastError` at `0x18003e6f6`
- `KERNEL32!SetLastError` at `0x18003e228`
- `KERNEL32!SetLastError` at `0x18003e497`
- `KERNEL32!SetLastError` at `0x18003e76f`
- `KERNEL32!SetLastError` at `0x18003e786`
- `KERNEL32!SetLastError` at `0x18003e228`
- `KERNEL32!SetLastError` at `0x18003e497`
- `KERNEL32!SetLastError` at `0x18003e76f`
- `KERNEL32!SetLastError` at `0x18003e786`
- `KERNEL32!GetProcessHeap` at `0x18003e563`
- `KERNEL32!GetProcessHeap` at `0x18003e59b`
- `KERNEL32!GetProcessHeap` at `0x18003e728`
- `KERNEL32!GetProcessHeap` at `0x18003e74d`
- `KERNEL32!GetProcessHeap` at `0x18003e563`
- `KERNEL32!GetProcessHeap` at `0x18003e59b`
- `KERNEL32!GetProcessHeap` at `0x18003e728`
- `KERNEL32!GetProcessHeap` at `0x18003e74d`
- `KERNEL32!CompareStringW` at `0x18003e4e4`
- `KERNEL32!CompareStringW` at `0x18003e517`
- `KERNEL32!CompareStringW` at `0x18003e4e4`
- `KERNEL32!CompareStringW` at `0x18003e517`
- `ntdll!RtlFreeHeap` at `0x18003e6d8`
- `ntdll!RtlFreeHeap` at `0x18003e6d8`
- `ntdll!RtlAllocateHeap` at `0x18003e2cf`
- `ntdll!RtlAllocateHeap` at `0x18003e2cf`

## string_xrefs

- `0x18003e265`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x18003e618`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x18003e62d`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x18003e705`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18003e671`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x18003e6a4`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

## pseudocode

```c
__int64 __fastcall EnumeratePathEx(
        LPCWSTR lpFileName,
        __int64 (__fastcall *a2)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64),
        __int64 (__fastcall *a3)(DWORD *, __int64),
        __int64 a4,
        char a5)
{
  WCHAR *v6; // r12
  DWORD v7; // esi
  DWORD LastError; // ebx
  DWORD v10; // ecx
  unsigned __int64 v11; // r14
  int v12; // r15d
  __int64 v13; // rbx
  wchar_t *Heap; // r13
  HRESULT v15; // ebx
  HRESULT v16; // eax
  const WCHAR *v17; // rax
  HANDLE FirstFileW; // r15
  int v19; // ebx
  void *v20; // rax
  wchar_t *v21; // rax
  const WCHAR *v22; // rax
  int v23; // eax
  HANDLE ProcessHeap; // rax
  BOOL v25; // eax
  void *v26; // rcx
  HANDLE v27; // rax
  DWORD v28; // eax
  const wchar_t *v29; // r8
  HANDLE v30; // rax
  HANDLE v31; // rax
  STRSAFE_LPWSTR *ppszDestEnd; // [rsp+20h] [rbp-E0h]
  DWORD v33; // [rsp+30h] [rbp-D0h]
  DWORD v34; // [rsp+30h] [rbp-D0h]
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+54h] [rbp-ACh]
  unsigned int v39; // [rsp+58h] [rbp-A8h]
  size_t pcchRemaining[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwFileAttributes; // [rsp+70h] [rbp-90h] BYREF
  FILETIME ftCreationTime; // [rsp+74h] [rbp-8Ch]
  FILETIME ftLastAccessTime; // [rsp+7Ch] [rbp-84h]
  FILETIME ftLastWriteTime; // [rsp+84h] [rbp-7Ch]
  int v45; // [rsp+8Ch] [rbp-74h]
  unsigned __int64 v46; // [rsp+90h] [rbp-70h]
  LPVOID lpMem; // [rsp+98h] [rbp-68h]
  PCNZWCH lpString2[2]; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v49)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v50)(DWORD *, __int64); // [rsp+B8h] [rbp-48h]
  __int64 v51; // [rsp+C0h] [rbp-40h]
  size_t cchDest; // [rsp+C8h] [rbp-38h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF

  v50 = a3;
  v49 = a2;
  v51 = a4;
  v6 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v39 = 0;
  v7 = 0;
  v35 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = 87;
    goto LABEL_74;
  }
  if ( (unsigned int)ReparsePointExists(lpFileName, &v35) && v35 )
  {
    v37 = 0;
    if ( (a5 & 2) != 0 )
      goto LABEL_11;
    if ( (unsigned int)ShouldEnumerateReparsePoint(lpFileName, &v37) && v37 )
      goto LABEL_15;
    v38 = 0;
    if ( (a5 & 1) != 0 )
    {
LABEL_11:
      SetLastError(0);
      return 1;
    }
    if ( (unsigned int)GetReparseTag(lpFileName) )
    {
      if ( v38 != -2147483640 )
        goto LABEL_11;
      goto LABEL_15;
    }
    LastError = GetLastError();
    if ( (unsigned int)ReparsePointExists(lpFileName, &v35) && v35 )
    {
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x",
        LastError);
      v10 = LastError;
LABEL_74:
      SetLastError(v10);
      return 0;
    }
  }
LABEL_15:
  v11 = -1;
  v12 = 0;
  v13 = -1;
  do
    ++v13;
  while ( lpFileName[v13] );
  if ( (_DWORD)v13 && lpFileName[(unsigned int)(v13 - 1)] != 92 )
    v12 = 1;
  cchDest = (unsigned int)(v13 + v12 + 2);
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * cchDest);
  if ( !Heap )
  {
    Heap = 0;
    NtCurrentTeb()->LastErrorValue = 8;
    goto LABEL_67;
  }
  v15 = StringCchCopyNExW(Heap, cchDest, lpFileName, (unsigned int)v13, &pszDest, pcchRemaining, v33);
  if ( v15 < 0 )
    goto LABEL_66;
  if ( v12 )
    v15 = StringCchCopyNExW(pszDest, pcchRemaining[0], L"\\", 1u, &pszDest, pcchRemaining, v34);
  if ( v15 < 0 || (v16 = StringCchCopyNW(pszDest, pcchRemaining[0], L"*", 1u), LOWORD(v15) = v16, v16 < 0) )
  {
LABEL_66:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    Heap = 0;
    NtCurrentTeb()->LastErrorValue = (unsigned __int16)v15;
    goto LABEL_67;
  }
  NtCurrentTeb()->LastErrorValue = 0;
  v17 = (const WCHAR *)PrepareUnicodePath(Heap);
  v6 = (WCHAR *)v17;
  if ( !v17 )
  {
LABEL_67:
    LODWORD(ppszDestEnd) = GetLastError();
    v7 = (unsigned int)ppszDestEnd;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x",
      lpFileName,
      ppszDestEnd);
    goto LABEL_68;
  }
  FirstFileW = FindFirstFileW(v17, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LODWORD(ppszDestEnd) = GetLastError();
    v7 = (unsigned int)ppszDestEnd;
    LibLog(&g_WdsLibLog, 0x2000000, L"EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x", v6, ppszDestEnd);
    do
      ++v11;
    while ( v6[v11] );
    if ( v11 >= 0x104 )
    {
      LibLog(&g_WdsLibLog, 50331648, L"EnumeratePathEx: Failed search path is >= MAX_PATH!");
      v7 = 206;
    }
    goto LABEL_68;
  }
  memset_0(&dwFileAttributes, 0, 0x40u);
  do
  {
    v19 = 0;
    if ( *lpFileName )
    {
      v45 = 0;
      lpMem = 0;
      dwFileAttributes = FindFileData.dwFileAttributes;
      ftCreationTime = FindFileData.ftCreationTime;
      ftLastAccessTime = FindFileData.ftLastAccessTime;
      ftLastWriteTime = FindFileData.ftLastWriteTime;
      pszDest = (STRSAFE_LPWSTR)__PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
      v46 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
      *(_OWORD *)lpString2 = 0;
      v20 = (void *)BuildPath(lpFileName, FindFileData.cFileName);
      lpMem = v20;
      if ( v20
        && ((v21 = wcsrchr_0((const wchar_t *)v20, 0x5Cu)) == 0 ? (v22 = (const WCHAR *)lpMem) : (v22 = v21 + 1),
            lpString2[0] = v22,
            (lpString2[1] = (PCNZWCH)FormFullPathName((LPCWSTR)lpMem)) != 0) )
      {
        v19 = 1;
      }
      else
      {
        FreeWdslibFindData(&dwFileAttributes);
      }
    }
    else
    {
      SetLastError(0x57u);
    }
    if ( v19 == 1 )
    {
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( !v50 )
          goto LABEL_48;
        v23 = v50(&dwFileAttributes, v51);
        goto LABEL_47;
      }
      if ( v49
        && CompareStringW(0x409u, 1u, L".", -1, lpString2[0], -1) != 2
        && CompareStringW(0x409u, 1u, L"..", -1, lpString2[0], -1) != 2 )
      {
        v23 = v49(&dwFileAttributes, (__int64 (__fastcall *)(_QWORD, _QWORD))v50, v51);
LABEL_47:
        v19 = v23;
      }
    }
LABEL_48:
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      v25 = HeapFree(ProcessHeap, 0, lpMem);
      v26 = lpMem;
      if ( v25 )
        v26 = 0;
      lpMem = v26;
    }
    if ( lpString2[1] )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, (LPVOID)lpString2[1]);
    }
    memset_0(&dwFileAttributes, 0, 0x40u);
    if ( v19 != 1 )
    {
      v28 = GetLastError();
      v29 = L"EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x";
      goto LABEL_60;
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( GetLastError() == 18 )
  {
    v39 = 1;
    goto LABEL_61;
  }
  v28 = GetLastError();
  v29 = L"EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x";
LABEL_60:
  LODWORD(ppszDestEnd) = v28;
  v7 = v28;
  LibLog(&g_WdsLibLog, 0x2000000, v29, v6, ppszDestEnd);
LABEL_61:
  FindClose(FirstFileW);
LABEL_68:
  if ( Heap )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, Heap);
  }
  if ( v6 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v6);
  }
  SetLastError(v7);
  return v39;
}

```

## disassembly

```asm
0x18003e138  push    rbp
0x18003e13a  push    rbx
0x18003e13b  push    rsi
0x18003e13c  push    rdi
0x18003e13d  push    r12
0x18003e13f  push    r13
0x18003e141  push    r14
0x18003e143  push    r15
0x18003e145  lea     rbp, [rsp-238h]
0x18003e14d  sub     rsp, 338h
0x18003e154  mov     rax, cs:__security_cookie
0x18003e15b  xor     rax, rsp
0x18003e15e  mov     [rbp+270h+var_50], rax
0x18003e165  mov     [rbp+270h+var_2B8], r8
0x18003e169  mov     rdi, rcx
0x18003e16c  mov     [rbp+270h+var_2C0], rdx
0x18003e170  lea     rcx, [rbp+270h+FindFileData]; void *
0x18003e174  xor     r13d, r13d
0x18003e177  mov     [rbp+270h+var_2B0], r9
0x18003e17b  xor     edx, edx; Val
0x18003e17d  mov     r8d, 250h; Size
0x18003e183  mov     r12d, r13d
0x18003e186  call    memset_0
0x18003e18b  mov     [rsp+370h+var_318], r13d
0x18003e190  mov     esi, r13d
0x18003e193  mov     [rsp+370h+var_330], r13d
0x18003e198  test    rdi, rdi
0x18003e19b  jz      loc_18003E781
0x18003e1a1  cmp     r13w, [rdi]
0x18003e1a5  jz      loc_18003E781
0x18003e1ab  lea     rdx, [rsp+370h+var_330]
0x18003e1b0  mov     rcx, rdi
0x18003e1b3  call    ReparsePointExists
0x18003e1b8  lea     r14d, [r13+1]
0x18003e1bc  test    eax, eax
0x18003e1be  jz      loc_18003E284
0x18003e1c4  cmp     [rsp+370h+var_330], r13d
0x18003e1c9  jz      loc_18003E284
0x18003e1cf  mov     ebx, [rbp+270h+arg_20]
0x18003e1d5  mov     eax, ebx
0x18003e1d7  and     eax, 2
0x18003e1da  mov     [rsp+370h+var_320], r13d
0x18003e1df  test    al, al
0x18003e1e1  jnz     short loc_18003E226
0x18003e1e3  lea     rdx, [rsp+370h+var_320]
0x18003e1e8  mov     rcx, rdi
0x18003e1eb  call    ShouldEnumerateReparsePoint
0x18003e1f0  test    eax, eax
0x18003e1f2  jz      short loc_18003E1FF
0x18003e1f4  cmp     [rsp+370h+var_320], r13d
0x18003e1f9  jnz     loc_18003E284
0x18003e1ff  and     ebx, r14d
0x18003e202  mov     [rsp+370h+var_31C], r13d
0x18003e207  test    bl, bl
0x18003e209  jnz     short loc_18003E226
0x18003e20b  lea     rdx, [rsp+370h+var_31C]
0x18003e210  mov     rcx, rdi; lpFileName
0x18003e213  call    GetReparseTag
0x18003e218  test    eax, eax
0x18003e21a  jz      short loc_18003E23C
0x18003e21c  cmp     [rsp+370h+var_31C], 80000008h
0x18003e224  jz      short loc_18003E284
0x18003e226  xor     ecx, ecx; dwErrCode
0x18003e228  call    cs:__imp_SetLastError
0x18003e22f  nop     dword ptr [rax+rax+00h]
0x18003e234  mov     eax, r14d
0x18003e237  jmp     loc_18003E794
0x18003e23c  call    cs:__imp_GetLastError
0x18003e243  nop     dword ptr [rax+rax+00h]
0x18003e248  lea     rdx, [rsp+370h+var_330]
0x18003e24d  mov     rcx, rdi
0x18003e250  mov     ebx, eax
0x18003e252  call    ReparsePointExists
0x18003e257  test    eax, eax
0x18003e259  jz      short loc_18003E284
0x18003e25b  cmp     [rsp+370h+var_330], r13d
0x18003e260  jz      short loc_18003E284
0x18003e262  mov     r9d, ebx
0x18003e265  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x18003e26c  mov     edx, 2000000h
0x18003e271  lea     rcx, g_WdsLibLog
0x18003e278  call    LibLog
0x18003e27d  mov     ecx, ebx
0x18003e27f  jmp     loc_18003E786
0x18003e284  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003e288  mov     r15d, r13d
0x18003e28b  mov     rbx, r14
0x18003e28e  inc     rbx
0x18003e291  cmp     [rdi+rbx*2], r13w
0x18003e296  jnz     short loc_18003E28E
0x18003e298  mov     edx, 5Ch ; '\'
0x18003e29d  test    ebx, ebx
0x18003e29f  jz      short loc_18003E2AF
0x18003e2a1  lea     eax, [rbx-1]
0x18003e2a4  cmp     dx, [rdi+rax*2]
0x18003e2a8  lea     eax, [rdx-5Bh]
0x18003e2ab  cmovnz  r15d, eax
0x18003e2af  mov     rcx, gs:60h
0x18003e2b8  lea     eax, [r15+2]
0x18003e2bc  add     eax, ebx
0x18003e2be  mov     edx, 8; Flags
0x18003e2c3  mov     [rbp+270h+cchDest], rax
0x18003e2c7  mov     rcx, [rcx+30h]; HeapHandle
0x18003e2cb  lea     r8, [rax+rax]; Size
0x18003e2cf  call    cs:__imp_RtlAllocateHeap
0x18003e2d6  nop     dword ptr [rax+rax+00h]
0x18003e2db  xor     ecx, ecx
0x18003e2dd  mov     r13, rax
0x18003e2e0  test    rax, rax
0x18003e2e3  jnz     short loc_18003E2FD
0x18003e2e5  mov     rax, gs:30h
0x18003e2ee  mov     r13d, ecx
0x18003e2f1  mov     dword ptr [rax+68h], 8
0x18003e2f8  jmp     loc_18003E6F6
0x18003e2fd  mov     rdx, [rbp+270h+cchDest]; cchDest
0x18003e301  lea     rax, [rsp+370h+var_310]
0x18003e306  mov     [rsp+370h+pcchRemaining], rax; pcchRemaining
0x18003e30b  mov     r8, rdi; pszSrc
0x18003e30e  lea     rax, [rsp+370h+pszDest]
0x18003e313  mov     r9d, ebx; cchToCopy
0x18003e316  mov     rcx, r13; pszDest
0x18003e319  mov     [rsp+370h+ppszDestEnd], rax; ppszDestEnd
0x18003e31e  call    StringCchCopyNExW
0x18003e323  mov     ebx, eax
0x18003e325  test    eax, eax
0x18003e327  js      loc_18003E6C3
0x18003e32d  test    r15d, r15d
0x18003e330  jz      short loc_18003E364
0x18003e332  mov     rdx, [rsp+370h+var_310]; cchDest
0x18003e337  lea     rax, [rsp+370h+var_310]
0x18003e33c  mov     rcx, [rsp+370h+pszDest]; pszDest
0x18003e341  lea     r8, asc_180065EC0; "\\"
0x18003e348  mov     [rsp+370h+pcchRemaining], rax; pcchRemaining
0x18003e34d  mov     r9d, 1; cchToCopy
0x18003e353  lea     rax, [rsp+370h+pszDest]
0x18003e358  mov     [rsp+370h+ppszDestEnd], rax; ppszDestEnd
0x18003e35d  call    StringCchCopyNExW
0x18003e362  mov     ebx, eax
0x18003e364  xor     r15d, r15d
0x18003e367  test    ebx, ebx
0x18003e369  js      loc_18003E6C6
0x18003e36f  mov     rdx, [rsp+370h+var_310]; cchDest
0x18003e374  lea     r9d, [r15+1]; cchToCopy
0x18003e378  mov     rcx, [rsp+370h+pszDest]; pszDest
0x18003e37d  lea     r8, asc_18006843C; "*"
0x18003e384  call    StringCchCopyNW
0x18003e389  mov     ebx, eax
0x18003e38b  test    eax, eax
0x18003e38d  js      loc_18003E6C6
0x18003e393  mov     rax, gs:30h
0x18003e39c  xor     edx, edx
0x18003e39e  mov     rcx, r13; unsigned __int16 *
0x18003e3a1  mov     [rax+68h], r15d
0x18003e3a5  call    PrepareUnicodePath
0x18003e3aa  mov     r12, rax
0x18003e3ad  test    rax, rax
0x18003e3b0  jz      loc_18003E6F6
0x18003e3b6  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18003e3ba  mov     rcx, rax; lpFileName
0x18003e3bd  call    cs:__imp_FindFirstFileW
0x18003e3c4  nop     dword ptr [rax+rax+00h]
0x18003e3c9  mov     r15, rax
0x18003e3cc  cmp     rax, r14
0x18003e3cf  jz      loc_18003E662
0x18003e3d5  xor     edx, edx; Val
0x18003e3d7  lea     rcx, [rsp+370h+var_300]; void *
0x18003e3dc  lea     r8d, [rdx+40h]; Size
0x18003e3e0  call    memset_0
0x18003e3e5  xor     eax, eax
0x18003e3e7  mov     ebx, eax
0x18003e3e9  cmp     ax, [rdi]
0x18003e3ec  jz      loc_18003E492
0x18003e3f2  mov     [rbp+270h+var_2E4], eax
0x18003e3f5  lea     rdx, [rbp+270h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x18003e3f9  mov     [rbp+270h+lpMem], rax
0x18003e3fd  xorps   xmm0, xmm0
0x18003e400  mov     eax, [rbp+270h+FindFileData.dwFileAttributes]
0x18003e403  mov     rcx, rdi; pszSrc
0x18003e406  mov     [rsp+370h+var_300], eax
0x18003e40a  mov     rax, qword ptr [rbp+270h+FindFileData.ftCreationTime.dwLowDateTime]
0x18003e40e  mov     [rsp+370h+var_2FC], rax
0x18003e413  mov     rax, qword ptr [rbp+270h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x18003e417  mov     [rsp+370h+var_2F4], rax
0x18003e41c  mov     rax, qword ptr [rbp+270h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18003e420  mov     [rbp+270h+var_2EC], rax
0x18003e424  mov     eax, [rbp+270h+FindFileData.nFileSizeHigh]
0x18003e427  mov     dword ptr [rsp+370h+pszDest+4], eax
0x18003e42b  mov     eax, [rbp+270h+FindFileData.nFileSizeLow]
0x18003e42e  mov     dword ptr [rsp+370h+pszDest], eax
0x18003e432  mov     rax, [rsp+370h+pszDest]
0x18003e437  mov     [rbp+270h+var_2E0], rax
0x18003e43b  movdqa  xmmword ptr [rbp+270h+lpString2], xmm0
0x18003e440  call    BuildPath
0x18003e445  mov     [rbp+270h+lpMem], rax
0x18003e449  test    rax, rax
0x18003e44c  jz      short loc_18003E486
0x18003e44e  mov     edx, 5Ch ; '\'; Ch
0x18003e453  mov     rcx, rax; Str
0x18003e456  call    wcsrchr_0
0x18003e45b  mov     rcx, [rbp+270h+lpMem]; lpFileName
0x18003e45f  test    rax, rax
0x18003e462  jz      short loc_18003E46A
0x18003e464  add     rax, 2
0x18003e468  jmp     short loc_18003E46D
0x18003e46a  mov     rax, rcx
0x18003e46d  mov     [rbp+270h+lpString2], rax
0x18003e471  call    FormFullPathName
0x18003e476  mov     [rbp+270h+lpString2+8], rax
0x18003e47a  test    rax, rax
0x18003e47d  jz      short loc_18003E486
0x18003e47f  mov     ebx, 1
0x18003e484  jmp     short loc_18003E4A3
0x18003e486  lea     rcx, [rsp+370h+var_300]; void *
0x18003e48b  call    FreeWdslibFindData
0x18003e490  jmp     short loc_18003E4A3
0x18003e492  mov     ecx, 57h ; 'W'; dwErrCode
0x18003e497  call    cs:__imp_SetLastError
0x18003e49e  nop     dword ptr [rax+rax+00h]
0x18003e4a3  xor     eax, eax
0x18003e4a5  lea     ecx, [rax+1]
0x18003e4a8  cmp     ebx, ecx
0x18003e4aa  jnz     loc_18003E55B
0x18003e4b0  test    byte ptr [rsp+370h+var_300], 10h
0x18003e4b5  jz      loc_18003E541
0x18003e4bb  cmp     [rbp+270h+var_2C0], rax
0x18003e4bf  jz      loc_18003E55B
0x18003e4c5  mov     rax, [rbp+270h+lpString2]
0x18003e4c9  lea     r8, asc_18006933C; "."
0x18003e4d0  mov     edx, ecx; dwCmpFlags
0x18003e4d2  mov     dword ptr [rsp+370h+pcchRemaining], r14d; cchCount2
0x18003e4d7  mov     ecx, 409h; Locale
0x18003e4dc  mov     [rsp+370h+ppszDestEnd], rax; lpString2
0x18003e4e1  mov     r9d, r14d; cchCount1
0x18003e4e4  call    cs:__imp_CompareStringW
0x18003e4eb  nop     dword ptr [rax+rax+00h]
0x18003e4f0  cmp     eax, 2
0x18003e4f3  jz      short loc_18003E55B
0x18003e4f5  mov     rax, [rbp+270h+lpString2]
0x18003e4f9  lea     r8, asc_180069340; ".."
0x18003e500  mov     dword ptr [rsp+370h+pcchRemaining], r14d; cchCount2
0x18003e505  mov     r9d, r14d; cchCount1
0x18003e508  mov     edx, 1; dwCmpFlags
0x18003e50d  mov     [rsp+370h+ppszDestEnd], rax; lpString2
0x18003e512  mov     ecx, 409h; Locale
0x18003e517  call    cs:__imp_CompareStringW
0x18003e51e  nop     dword ptr [rax+rax+00h]
0x18003e523  cmp     eax, 2
0x18003e526  jz      short loc_18003E55B
0x18003e528  mov     r8, [rbp+270h+var_2B0]
0x18003e52c  lea     rcx, [rsp+370h+var_300]
0x18003e531  mov     rdx, [rbp+270h+var_2B8]
0x18003e535  mov     rax, [rbp+270h+var_2C0]
0x18003e539  call    cs:__guard_dispatch_icall_fptr
0x18003e53f  jmp     short loc_18003E559
0x18003e541  mov     rax, [rbp+270h+var_2B8]
0x18003e545  test    rax, rax
0x18003e548  jz      short loc_18003E55B
0x18003e54a  mov     rdx, [rbp+270h+var_2B0]
0x18003e54e  lea     rcx, [rsp+370h+var_300]
0x18003e553  call    cs:__guard_dispatch_icall_fptr
0x18003e559  mov     ebx, eax
0x18003e55b  xor     eax, eax
0x18003e55d  cmp     [rbp+270h+lpMem], rax
0x18003e561  jz      short loc_18003E595
0x18003e563  call    cs:__imp_GetProcessHeap
0x18003e56a  nop     dword ptr [rax+rax+00h]
0x18003e56f  mov     r8, [rbp+270h+lpMem]; lpMem
0x18003e573  xor     edx, edx; dwFlags
0x18003e575  mov     rcx, rax; hHeap
0x18003e578  call    cs:__imp_HeapFree
0x18003e57f  nop     dword ptr [rax+rax+00h]
0x18003e584  mov     rcx, [rbp+270h+lpMem]
0x18003e588  test    eax, eax
0x18003e58a  mov     rax, rsi
0x18003e58d  cmovnz  rcx, rax
0x18003e591  mov     [rbp+270h+lpMem], rcx
0x18003e595  cmp     [rbp+270h+lpString2+8], rax
0x18003e599  jz      short loc_18003E5BC
0x18003e59b  call    cs:__imp_GetProcessHeap
0x18003e5a2  nop     dword ptr [rax+rax+00h]
0x18003e5a7  mov     r8, [rbp+270h+lpString2+8]; lpMem
0x18003e5ab  xor     edx, edx; dwFlags
0x18003e5ad  mov     rcx, rax; hHeap
0x18003e5b0  call    cs:__imp_HeapFree
0x18003e5b7  nop     dword ptr [rax+rax+00h]
0x18003e5bc  xor     edx, edx; Val
0x18003e5be  lea     rcx, [rsp+370h+var_300]; void *
0x18003e5c3  lea     r8d, [rdx+40h]; Size
0x18003e5c7  call    memset_0
0x18003e5cc  mov     eax, 1
0x18003e5d1  cmp     ebx, eax
0x18003e5d3  jnz     short loc_18003E621
0x18003e5d5  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x18003e5d9  mov     rcx, r15; hFindFile
0x18003e5dc  call    cs:__imp_FindNextFileW
0x18003e5e3  nop     dword ptr [rax+rax+00h]
0x18003e5e8  mov     ebx, 1
0x18003e5ed  cmp     eax, ebx
0x18003e5ef  jz      loc_18003E3E5
0x18003e5f5  call    cs:__imp_GetLastError
  ... truncated ...
```
