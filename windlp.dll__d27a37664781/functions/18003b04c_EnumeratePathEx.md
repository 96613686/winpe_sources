# EnumeratePathEx

- ea: `0x18003b04c`
- end: `0x18003b620`
- name: `EnumeratePathEx`
- size: `1492`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int)`
- caller_count: `11`
- callee_count: `15`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180005e00`
- `0x1800190f0`
- `0x180019de8`
- `0x18001b484`
- `0x18003a380`
- `0x18003a4c8`
- `0x18003a800`
- `0x18003aa98`
- `0x18003afd0`
- `0x18003b6e4`
- `0x18003b810`

## callees

- `0x1800020b6`
- `0x180039394`
- `0x180039424`
- `0x18003b04c`
- `0x18003b668`
- `0x18003b998`
- `0x18003bae4`
- `0x18003bb64`
- `0x18003c048`
- `0x18003c464`
- `0x18003d694`
- `0x18003d86c`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003b575`
- `ntdll!RtlFreeHeap` at `0x18003b575`
- `ntdll!RtlAllocateHeap` at `0x18003b1cd`
- `ntdll!RtlAllocateHeap` at `0x18003b1cd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003b4fc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003b4fc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003b2bb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003b2bb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003b49b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003b49b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b3be`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b3e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b3be`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b3e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b440`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b5bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b5d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b440`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b5bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b5d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b44e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b477`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b5ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b5e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b44e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b477`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b5ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b5e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b42e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b5f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b42e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b58d`

## string_xrefs

- `0x18003b4d6`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x18003b4c7`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x18003b155`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x18003b541`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`
- `0x18003b510`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x18003b596`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall EnumeratePathEx(
        LPCWSTR lpFileName,
        __int64 (__fastcall *a2)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64),
        __int64 (__fastcall *a3)(DWORD *, __int64),
        __int64 a4,
        char a5)
{
  unsigned int v6; // r13d
  DWORD v7; // ecx
  DWORD LastError; // ebx
  DWORD v10; // ecx
  unsigned __int64 v11; // r12
  __int64 v12; // rdi
  WCHAR *v13; // rbx
  int v14; // r15d
  wchar_t *Heap; // rsi
  HRESULT v16; // eax
  unsigned __int16 v17; // di
  HRESULT v18; // eax
  HRESULT v19; // eax
  const WCHAR *v20; // rax
  void *v21; // rax
  wchar_t *v22; // rax
  const WCHAR *v23; // rax
  int v24; // edi
  __int64 (__fastcall *v25)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // r15
  int v26; // eax
  void *v27; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v29; // r15
  HANDLE v30; // rax
  int v31; // edi
  DWORD v32; // eax
  const wchar_t *v33; // r8
  HANDLE v34; // rax
  HANDLE v35; // rax
  STRSAFE_LPWSTR *ppszDestEnd; // [rsp+20h] [rbp-E0h]
  DWORD v37; // [rsp+30h] [rbp-D0h]
  DWORD v38; // [rsp+30h] [rbp-D0h]
  size_t cchDest; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v41)(DWORD *, __int64); // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  DWORD dwFileAttributes; // [rsp+60h] [rbp-A0h] BYREF
  FILETIME ftCreationTime; // [rsp+64h] [rbp-9Ch]
  FILETIME ftLastAccessTime; // [rsp+6Ch] [rbp-94h]
  FILETIME ftLastWriteTime; // [rsp+74h] [rbp-8Ch]
  int v47; // [rsp+7Ch] [rbp-84h]
  DWORD nFileSizeLow; // [rsp+80h] [rbp-80h]
  DWORD nFileSizeHigh; // [rsp+84h] [rbp-7Ch]
  LPVOID lpMem; // [rsp+88h] [rbp-78h]
  PCNZWCH lpString2[2]; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v52)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // [rsp+A0h] [rbp-60h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  v41 = a3;
  v52 = a2;
  v42 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  LODWORD(pszDest) = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = 87;
    goto LABEL_73;
  }
  v6 = 1;
  if ( (unsigned int)ReparsePointExists(lpFileName, &pszDest) && (_DWORD)pszDest )
  {
    LODWORD(cchDest) = 0;
    if ( (a5 & 2) != 0 )
      goto LABEL_11;
    if ( (unsigned int)ShouldEnumerateReparsePoint(lpFileName, &cchDest) && (_DWORD)cchDest )
      goto LABEL_16;
    LODWORD(cchDest) = 0;
    if ( (a5 & 1) != 0 )
    {
LABEL_11:
      v7 = 0;
      goto LABEL_12;
    }
    if ( (unsigned int)GetReparseTag(lpFileName) )
    {
      if ( (_DWORD)cchDest != -2147483640 )
        goto LABEL_11;
      goto LABEL_16;
    }
    LastError = GetLastError();
    if ( (unsigned int)ReparsePointExists(lpFileName, &pszDest) && (_DWORD)pszDest )
    {
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x",
        LastError);
      v10 = LastError;
LABEL_73:
      SetLastError(v10);
      return 0;
    }
  }
LABEL_16:
  v11 = -1;
  pszDest = 0;
  v12 = -1;
  cchDest = 0;
  v13 = 0;
  v14 = 0;
  do
    ++v12;
  while ( lpFileName[v12] );
  if ( (_DWORD)v12 && lpFileName[(unsigned int)(v12 - 1)] != 92 )
    v14 = 1;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v12 + v14 + 2));
  if ( !Heap )
  {
    NtCurrentTeb()->LastErrorValue = 8;
LABEL_66:
    Heap = 0;
LABEL_67:
    LODWORD(ppszDestEnd) = GetLastError();
    v31 = (int)ppszDestEnd;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x",
      lpFileName,
      ppszDestEnd);
    v6 = 0;
    if ( Heap )
      goto LABEL_68;
    goto LABEL_69;
  }
  v16 = StringCchCopyNExW(Heap, (unsigned int)(v12 + v14 + 2), lpFileName, (unsigned int)v12, &pszDest, &cchDest, v37);
  v17 = v16;
  if ( v16 < 0
    || v14 && (v18 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v38), v17 = v18, v18 < 0)
    || (v19 = StringCchCopyNW(pszDest, cchDest, L"*", 1u), v17 = v19, v19 < 0) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    NtCurrentTeb()->LastErrorValue = v17;
    goto LABEL_66;
  }
  NtCurrentTeb()->LastErrorValue = 0;
  v20 = (const WCHAR *)PrepareUnicodePathEx(Heap);
  v13 = (WCHAR *)v20;
  if ( !v20 )
    goto LABEL_67;
  v6 = 0;
  cchDest = (size_t)FindFirstFileW(v20, &FindFileData);
  if ( cchDest == -1 )
  {
    LODWORD(ppszDestEnd) = GetLastError();
    v31 = (int)ppszDestEnd;
    LibLog(&g_WdsLibLog, 0x2000000, L"EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x", v13, ppszDestEnd);
    do
      ++v11;
    while ( v13[v11] );
    if ( v11 >= 0x104 )
    {
      LibLog(&g_WdsLibLog, 50331648, L"EnumeratePathEx: Failed search path is >= MAX_PATH!");
      v31 = 206;
    }
    goto LABEL_68;
  }
  memset_0(&dwFileAttributes, 0, 0x40u);
  do
  {
    if ( !*lpFileName )
    {
      SetLastError(0x57u);
      v24 = 0;
      goto LABEL_48;
    }
    dwFileAttributes = FindFileData.dwFileAttributes;
    ftCreationTime = FindFileData.ftCreationTime;
    ftLastAccessTime = FindFileData.ftLastAccessTime;
    ftLastWriteTime = FindFileData.ftLastWriteTime;
    nFileSizeLow = FindFileData.nFileSizeLow;
    nFileSizeHigh = FindFileData.nFileSizeHigh;
    v47 = 0;
    lpMem = 0;
    *(_OWORD *)lpString2 = 0;
    v21 = (void *)BuildPath(lpFileName, FindFileData.cFileName);
    lpMem = v21;
    if ( v21
      && ((v22 = wcsrchr_0((const wchar_t *)v21, 0x5Cu)) == 0 ? (v23 = (const WCHAR *)lpMem) : (v23 = v22 + 1),
          lpString2[0] = v23,
          (lpString2[1] = (PCNZWCH)FormFullPathName((LPCWSTR)lpMem)) != 0) )
    {
      v24 = 1;
    }
    else
    {
      v24 = 0;
      FreeWdslibFindData(&dwFileAttributes);
    }
    if ( v24 == 1 )
    {
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( !v41 )
          goto LABEL_48;
        v26 = v41(&dwFileAttributes, v42);
        goto LABEL_44;
      }
      v25 = v52;
      if ( v52
        && CompareStringW(0x409u, 1u, L".", -1, lpString2[0], -1) != 2
        && CompareStringW(0x409u, 1u, L"..", -1, lpString2[0], -1) != 2 )
      {
        v26 = v25(&dwFileAttributes, (__int64 (__fastcall *)(_QWORD, _QWORD))v41, v42);
LABEL_44:
        v24 = v26;
      }
    }
LABEL_48:
    v27 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      if ( HeapFree(ProcessHeap, 0, v27) )
        lpMem = 0;
    }
    v29 = (WCHAR *)lpString2[1];
    if ( lpString2[1] )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v29);
    }
    memset_0(&dwFileAttributes, 0, 0x40u);
    if ( v24 != 1 )
    {
      v32 = GetLastError();
      v33 = L"EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x";
      goto LABEL_59;
    }
  }
  while ( FindNextFileW((HANDLE)cchDest, &FindFileData) );
  if ( GetLastError() == 18 )
  {
    v31 = 0;
    v6 = 1;
    goto LABEL_60;
  }
  v32 = GetLastError();
  v33 = L"EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x";
LABEL_59:
  LODWORD(ppszDestEnd) = v32;
  v31 = v32;
  LibLog(&g_WdsLibLog, 0x2000000, v33, v13, ppszDestEnd);
LABEL_60:
  FindClose((HANDLE)cchDest);
LABEL_68:
  v34 = GetProcessHeap();
  HeapFree(v34, 0, Heap);
LABEL_69:
  if ( v13 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v13);
  }
  v7 = v31;
LABEL_12:
  SetLastError(v7);
  return v6;
}

```

## disassembly

```asm
0x18003b04c  push    rbp
0x18003b04e  push    rbx
0x18003b04f  push    rsi
0x18003b050  push    rdi
0x18003b051  push    r12
0x18003b053  push    r13
0x18003b055  push    r14
0x18003b057  push    r15
0x18003b059  lea     rbp, [rsp-218h]
0x18003b061  sub     rsp, 318h
0x18003b068  mov     rax, cs:__security_cookie
0x18003b06f  xor     rax, rsp
0x18003b072  mov     [rbp+250h+var_50], rax
0x18003b079  mov     [rsp+350h+var_300], r8
0x18003b07e  mov     r14, rcx
0x18003b081  mov     [rbp+250h+var_2B0], rdx
0x18003b085  lea     rcx, [rbp+250h+FindFileData]; void *
0x18003b089  xor     edx, edx; Val
0x18003b08b  mov     [rsp+350h+var_2F8], r9
0x18003b090  mov     r8d, 250h; Size
0x18003b096  call    memset_0
0x18003b09b  xor     esi, esi
0x18003b09d  mov     dword ptr [rsp+350h+pszDest], esi
0x18003b0a1  test    r14, r14
0x18003b0a4  jz      loc_18003B5F0
0x18003b0aa  cmp     si, [r14]
0x18003b0ae  jz      loc_18003B5F0
0x18003b0b4  lea     rdx, [rsp+350h+pszDest]
0x18003b0b9  mov     rcx, r14
0x18003b0bc  call    ReparsePointExists
0x18003b0c1  lea     r13d, [rsi+1]
0x18003b0c5  test    eax, eax
0x18003b0c7  jz      loc_18003B174
0x18003b0cd  cmp     dword ptr [rsp+350h+pszDest], esi
0x18003b0d1  jz      loc_18003B174
0x18003b0d7  mov     ebx, [rbp+250h+arg_20]
0x18003b0dd  mov     dword ptr [rsp+350h+cchDest], esi
0x18003b0e1  test    bl, 2
0x18003b0e4  jnz     short loc_18003B123
0x18003b0e6  lea     rdx, [rsp+350h+cchDest]
0x18003b0eb  mov     rcx, r14
0x18003b0ee  call    ShouldEnumerateReparsePoint
0x18003b0f3  test    eax, eax
0x18003b0f5  jz      short loc_18003B0FD
0x18003b0f7  cmp     dword ptr [rsp+350h+cchDest], esi
0x18003b0fb  jnz     short loc_18003B174
0x18003b0fd  and     ebx, r13d
0x18003b100  mov     dword ptr [rsp+350h+cchDest], esi
0x18003b104  test    bl, bl
0x18003b106  jnz     short loc_18003B123
0x18003b108  lea     rdx, [rsp+350h+cchDest]
0x18003b10d  mov     rcx, r14; lpFileName
0x18003b110  call    GetReparseTag
0x18003b115  test    eax, eax
0x18003b117  jz      short loc_18003B133
0x18003b119  cmp     dword ptr [rsp+350h+cchDest], 80000008h
0x18003b121  jz      short loc_18003B174
0x18003b123  xor     ecx, ecx; dwErrCode
0x18003b125  call    cs:__imp_SetLastError
0x18003b12b  mov     eax, r13d
0x18003b12e  jmp     loc_18003B5FD
0x18003b133  call    cs:__imp_GetLastError
0x18003b139  lea     rdx, [rsp+350h+pszDest]
0x18003b13e  mov     rcx, r14
0x18003b141  mov     ebx, eax
0x18003b143  call    ReparsePointExists
0x18003b148  test    eax, eax
0x18003b14a  jz      short loc_18003B174
0x18003b14c  cmp     dword ptr [rsp+350h+pszDest], esi
0x18003b150  jz      short loc_18003B174
0x18003b152  mov     r9d, ebx
0x18003b155  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x18003b15c  mov     edx, 2000000h
0x18003b161  lea     rcx, g_WdsLibLog
0x18003b168  call    LibLog
0x18003b16d  mov     ecx, ebx
0x18003b16f  jmp     loc_18003B5F5
0x18003b174  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003b178  mov     [rsp+350h+pszDest], rsi
0x18003b17d  mov     rdi, r12
0x18003b180  mov     [rsp+350h+cchDest], rsi
0x18003b185  mov     rbx, rsi
0x18003b188  mov     r15d, esi
0x18003b18b  inc     rdi
0x18003b18e  cmp     [r14+rdi*2], si
0x18003b193  jnz     short loc_18003B18B
0x18003b195  mov     edx, 5Ch ; '\'
0x18003b19a  test    edi, edi
0x18003b19c  jz      short loc_18003B1AA
0x18003b19e  lea     eax, [rdi-1]
0x18003b1a1  cmp     dx, [r14+rax*2]
0x18003b1a6  cmovnz  r15d, r13d
0x18003b1aa  mov     rcx, gs:60h
0x18003b1b3  lea     eax, [r15+2]
0x18003b1b7  add     eax, edi
0x18003b1b9  mov     edx, 8; Flags
0x18003b1be  mov     r13d, eax
0x18003b1c1  mov     rcx, [rcx+30h]; HeapHandle
0x18003b1c5  lea     r8, ds:0[rax*2]; Size
0x18003b1cd  call    cs:__imp_RtlAllocateHeap
0x18003b1d3  mov     rsi, rax
0x18003b1d6  test    rax, rax
0x18003b1d9  jnz     short loc_18003B1F3
0x18003b1db  mov     rax, gs:30h
0x18003b1e4  xor     r15d, r15d
0x18003b1e7  mov     dword ptr [rax+68h], 8
0x18003b1ee  jmp     loc_18003B58A
0x18003b1f3  lea     rax, [rsp+350h+cchDest]
0x18003b1f8  mov     r9d, edi; cchToCopy
0x18003b1fb  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18003b200  mov     r8, r14; pszSrc
0x18003b203  lea     rax, [rsp+350h+pszDest]
0x18003b208  mov     rdx, r13; cchDest
0x18003b20b  mov     rcx, rsi; pszDest
0x18003b20e  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x18003b213  call    StringCchCopyNExW
0x18003b218  mov     edi, eax
0x18003b21a  test    eax, eax
0x18003b21c  js      loc_18003B560
0x18003b222  test    r15d, r15d
0x18003b225  jz      short loc_18003B265
0x18003b227  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18003b22c  lea     rax, [rsp+350h+cchDest]
0x18003b231  mov     rcx, [rsp+350h+pszDest]; pszDest
0x18003b236  lea     r8, asc_180084C70; "\\"
0x18003b23d  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18003b242  mov     r9d, 1; cchToCopy
0x18003b248  lea     rax, [rsp+350h+pszDest]
0x18003b24d  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x18003b252  call    StringCchCopyNExW
0x18003b257  xor     r15d, r15d
0x18003b25a  mov     edi, eax
0x18003b25c  test    eax, eax
0x18003b25e  jns     short loc_18003B268
0x18003b260  jmp     loc_18003B563
0x18003b265  xor     r15d, r15d
0x18003b268  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18003b26d  lea     r8, asc_1800850E8; "*"
0x18003b274  mov     rcx, [rsp+350h+pszDest]; pszDest
0x18003b279  mov     r9d, 1; cchToCopy
0x18003b27f  call    StringCchCopyNW
0x18003b284  mov     edi, eax
0x18003b286  test    eax, eax
0x18003b288  js      loc_18003B563
0x18003b28e  mov     rax, gs:30h
0x18003b297  xor     edx, edx
0x18003b299  mov     rcx, rsi; pszSrc
0x18003b29c  mov     [rax+68h], r15d
0x18003b2a0  call    PrepareUnicodePathEx
0x18003b2a5  mov     rbx, rax
0x18003b2a8  test    rax, rax
0x18003b2ab  jz      loc_18003B58D
0x18003b2b1  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18003b2b5  mov     rcx, rax; lpFileName
0x18003b2b8  mov     r13d, r15d
0x18003b2bb  call    cs:__imp_FindFirstFileW
0x18003b2c1  mov     [rsp+350h+cchDest], rax
0x18003b2c6  cmp     rax, r12
0x18003b2c9  jz      loc_18003B507
0x18003b2cf  xor     edx, edx; Val
0x18003b2d1  lea     rcx, [rsp+350h+var_2F0]; void *
0x18003b2d6  lea     r8d, [rdx+40h]; Size
0x18003b2da  call    memset_0
0x18003b2df  cmp     r15w, [r14]
0x18003b2e3  jz      loc_18003B429
0x18003b2e9  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x18003b2ec  lea     rdx, [rbp+250h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x18003b2f0  mov     [rsp+350h+var_2F0], eax
0x18003b2f4  xorps   xmm0, xmm0
0x18003b2f7  mov     rax, qword ptr [rbp+250h+FindFileData.ftCreationTime.dwLowDateTime]
0x18003b2fb  mov     rcx, r14; pszSrc
0x18003b2fe  mov     [rsp+350h+var_2EC], rax
0x18003b303  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x18003b307  mov     [rsp+350h+var_2E4], rax
0x18003b30c  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18003b310  mov     [rsp+350h+var_2DC], rax
0x18003b315  mov     eax, [rbp+250h+FindFileData.nFileSizeLow]
0x18003b318  mov     [rbp+250h+var_2D0], eax
0x18003b31b  mov     eax, [rbp+250h+FindFileData.nFileSizeHigh]
0x18003b31e  mov     [rbp+250h+var_2CC], eax
0x18003b321  mov     [rsp+350h+var_2D4], r15d
0x18003b326  mov     [rbp+250h+lpMem], r15
0x18003b32a  movdqa  xmmword ptr [rbp+250h+lpString2], xmm0
0x18003b32f  call    BuildPath
0x18003b334  mov     [rbp+250h+lpMem], rax
0x18003b338  test    rax, rax
0x18003b33b  jz      short loc_18003B375
0x18003b33d  mov     edx, 5Ch ; '\'; Ch
0x18003b342  mov     rcx, rax; Str
0x18003b345  call    wcsrchr_0
0x18003b34a  mov     rcx, [rbp+250h+lpMem]; lpFileName
0x18003b34e  test    rax, rax
0x18003b351  jz      short loc_18003B359
0x18003b353  add     rax, 2
0x18003b357  jmp     short loc_18003B35C
0x18003b359  mov     rax, rcx
0x18003b35c  mov     [rbp+250h+lpString2], rax
0x18003b360  call    FormFullPathName
0x18003b365  mov     [rbp+250h+lpString2+8], rax
0x18003b369  test    rax, rax
0x18003b36c  jz      short loc_18003B375
0x18003b36e  mov     edi, 1
0x18003b373  jmp     short loc_18003B382
0x18003b375  lea     rcx, [rsp+350h+var_2F0]; void *
0x18003b37a  mov     edi, r15d
0x18003b37d  call    FreeWdslibFindData
0x18003b382  cmp     edi, 1
0x18003b385  jnz     loc_18003B437
0x18003b38b  test    byte ptr [rsp+350h+var_2F0], 10h
0x18003b390  jz      short loc_18003B40E
0x18003b392  mov     r15, [rbp+250h+var_2B0]
0x18003b396  test    r15, r15
0x18003b399  jz      loc_18003B437
0x18003b39f  mov     rax, [rbp+250h+lpString2]
0x18003b3a3  lea     r8, String1; "."
0x18003b3aa  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x18003b3af  mov     r9d, r12d; cchCount1
0x18003b3b2  mov     edx, edi; dwCmpFlags
0x18003b3b4  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x18003b3b9  mov     ecx, 409h; Locale
0x18003b3be  call    cs:__imp_CompareStringW
0x18003b3c4  cmp     eax, 2
0x18003b3c7  jz      short loc_18003B437
0x18003b3c9  mov     rax, [rbp+250h+lpString2]
0x18003b3cd  lea     r8, asc_180085160; ".."
0x18003b3d4  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x18003b3d9  mov     r9d, r12d; cchCount1
0x18003b3dc  mov     edx, edi; dwCmpFlags
0x18003b3de  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x18003b3e3  mov     ecx, 409h; Locale
0x18003b3e8  call    cs:__imp_CompareStringW
0x18003b3ee  cmp     eax, 2
0x18003b3f1  jz      short loc_18003B437
0x18003b3f3  mov     r8, [rsp+350h+var_2F8]
0x18003b3f8  lea     rcx, [rsp+350h+var_2F0]
0x18003b3fd  mov     rdx, [rsp+350h+var_300]
0x18003b402  mov     rax, r15
0x18003b405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b40a  mov     edi, eax
0x18003b40c  jmp     short loc_18003B437
0x18003b40e  mov     rax, [rsp+350h+var_300]
0x18003b413  test    rax, rax
0x18003b416  jz      short loc_18003B437
0x18003b418  mov     rdx, [rsp+350h+var_2F8]
0x18003b41d  lea     rcx, [rsp+350h+var_2F0]
0x18003b422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b427  jmp     short loc_18003B40A
0x18003b429  mov     ecx, 57h ; 'W'; dwErrCode
0x18003b42e  call    cs:__imp_SetLastError
0x18003b434  mov     edi, r15d
0x18003b437  mov     r15, [rbp+250h+lpMem]
0x18003b43b  test    r15, r15
0x18003b43e  jz      short loc_18003B460
0x18003b440  call    cs:__imp_GetProcessHeap
0x18003b446  mov     r8, r15; lpMem
0x18003b449  xor     edx, edx; dwFlags
0x18003b44b  mov     rcx, rax; hHeap
0x18003b44e  call    cs:__imp_HeapFree
0x18003b454  test    eax, eax
0x18003b456  jz      short loc_18003B460
0x18003b458  mov     [rbp+250h+lpMem], 0
0x18003b460  mov     r15, [rbp+250h+lpString2+8]
0x18003b464  test    r15, r15
0x18003b467  jz      short loc_18003B47D
0x18003b469  call    cs:__imp_GetProcessHeap
0x18003b46f  mov     r8, r15; lpMem
0x18003b472  xor     edx, edx; dwFlags
0x18003b474  mov     rcx, rax; hHeap
0x18003b477  call    cs:__imp_HeapFree
0x18003b47d  xor     edx, edx; Val
0x18003b47f  lea     rcx, [rsp+350h+var_2F0]; void *
0x18003b484  lea     r8d, [rdx+40h]; Size
0x18003b488  call    memset_0
0x18003b48d  cmp     edi, 1
0x18003b490  jnz     short loc_18003B4D0
0x18003b492  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x18003b497  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18003b49b  call    cs:__imp_FindNextFileW
0x18003b4a1  lea     r15d, [rdi-1]
0x18003b4a5  cmp     eax, edi
0x18003b4a7  jz      loc_18003B2DF
0x18003b4ad  call    cs:__imp_GetLastError
0x18003b4b3  cmp     eax, 12h
0x18003b4b6  jnz     short loc_18003B4C1
0x18003b4b8  mov     edi, r15d
0x18003b4bb  lea     r13d, [r15+1]
0x18003b4bf  jmp     short loc_18003B4F7
0x18003b4c1  call    cs:__imp_GetLastError
0x18003b4c7  lea     r8, aEnumeratepathe_4; "EnumeratePathEx: Unable to enumerate [%"...
0x18003b4ce  jmp     short loc_18003B4DD
0x18003b4d0  call    cs:__imp_GetLastError
0x18003b4d6  lea     r8, aEnumeratepathe_1; "EnumeratePathEx: Callback requested enu"...
0x18003b4dd  mov     r9, rbx
0x18003b4e0  mov     dword ptr [rsp+350h+ppszDestEnd], eax
0x18003b4e4  mov     edx, 2000000h
0x18003b4e9  lea     rcx, g_WdsLibLog
0x18003b4f0  mov     edi, eax
0x18003b4f2  call    LibLog
0x18003b4f7  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x18003b4fc  call    cs:__imp_FindClose
  ... truncated ...
```
