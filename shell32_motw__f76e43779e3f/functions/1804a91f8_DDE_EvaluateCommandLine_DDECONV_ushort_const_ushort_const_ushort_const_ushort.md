# _DDE_EvaluateCommandLine(_DDECONV *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x1804a91f8`
- end: `0x1804a95c3`
- name: `?_DDE_EvaluateCommandLine@@YAJPEAU_DDECONV@@PEBG11PEAPEAG@Z`
- size: `971`
- prototype: `__int64 __fastcall(struct _DDECONV *, const unsigned __int16 *, LPCWSTR pszPath, const unsigned __int16 *, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1804a6850`

## callees

- `0x18001aae0`
- `0x180249490`
- `0x1804a7f5c`
- `0x1804a91f8`
- `0x1804a95cc`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804a9591`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1804a9591`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1804a9528`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1804a9528`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1804a92a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1804a92a9`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1804a953c`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1804a953c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1804a924d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1804a924d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a9264`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a93c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a9264`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804a93c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1804a94ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1804a94ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1804a92bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1804a92bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1804a9517`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1804a9517`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1804a9296`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1804a9296`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804a93af`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804a9434`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804a93af`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804a9434`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1804a9413`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1804a9413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804a9571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804a9582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804a9571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804a9582`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1804a955e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1804a955e`
- `Windows.Storage!PathComposeWithArgs` at `0x1804a934f`
- `Windows.Storage!PathComposeWithArgs` at `0x1804a934f`
- `Windows.Storage!SHParseDisplayName` at `0x1804a9473`
- `Windows.Storage!SHParseDisplayName` at `0x1804a9473`
- `Windows.Storage!ILFree` at `0x1804a949f`
- `Windows.Storage!ILFree` at `0x1804a949f`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1804a9379`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x1804a9379`
- `Windows.Storage!PathSeperateArgs` at `0x1804a9304`
- `Windows.Storage!PathSeperateArgs` at `0x1804a9304`
- `Windows.Storage!PathResolve` at `0x1804a9335`
- `Windows.Storage!PathResolve` at `0x1804a9335`

## pseudocode

```c
__int64 __fastcall _DDE_EvaluateCommandLine(
        struct _DDECONV *a1,
        const unsigned __int16 *a2,
        WCHAR *pszPath,
        const unsigned __int16 *a4,
        LPWSTR *ppwsz)
{
  const unsigned __int16 *v7; // rbx
  WCHAR *v9; // rsi
  const WCHAR *v10; // rax
  int v11; // eax
  const WCHAR *v12; // rdi
  const WCHAR *i; // rbx
  HRESULT v14; // ebx
  unsigned int v15; // r10d
  int v16; // eax
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, const WCHAR *); // rbx
  BOOL IsUNCW; // eax
  const WCHAR *v20; // rdx
  const unsigned __int16 *FileNameW; // rax
  PWSTR ppszApplication; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszParameters; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR dirs[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR sz[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPatha[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v28[264]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v29[528]; // [rsp+680h] [rbp+580h] BYREF

  v7 = a2;
  v9 = 0;
  *ppwsz = 0;
  if ( *a2 == 34 )
  {
    v10 = StrDupW(a2);
    v9 = (WCHAR *)v10;
    if ( v10 )
    {
      v11 = lstrlenW(v10);
      if ( v11 > 1 )
      {
        v12 = &v9[v11 - 1];
        if ( *v12 == 34 )
        {
          for ( i = v9 + 1; i < v12; i = CharNextW(i) )
          {
            if ( !(unsigned int)PathIsValidCharW(*i, 1020) )
            {
              PathUnquoteSpacesW(v9);
              break;
            }
          }
        }
      }
      v7 = v9;
    }
  }
  v14 = StringCchCopyW(pszPatha, 0x104u, v7);
  if ( v14 >= 0 )
  {
    if ( (int)PathSeperateArgs(pszPatha, v29, v15, 0) >= 0 )
    {
      if ( pszPath )
      {
        dirs[0] = pszPath;
        dirs[1] = 0;
        PathResolve(pszPatha, dirs, 3u);
      }
      PathComposeWithArgs(pszPatha, v29);
    }
    ppszApplication = 0;
    ppszParameters = 0;
    v14 = SHEvaluateSystemCommandTemplate(pszPatha, &ppszApplication, 0, &ppszParameters);
    if ( v14 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, PWSTR))(**((_QWORD **)a1 + 5) + 88LL))(*((_QWORD *)a1 + 5), ppszParameters);
      if ( (*(_BYTE *)a1 & 1) != 0 && PathIsUNCW(ppszApplication) )
      {
        v16 = lstrlenW(ppszApplication);
        v14 = _DDE_RemapShare(a1, ppszApplication, v16 + 1);
      }
      if ( v14 >= 0 )
      {
        if ( !pszPath || !*pszPath )
        {
          StringCchCopyW(v28, 0x104u, ppszApplication);
          PathRemoveFileSpecW(v28);
          pszPath = v28;
        }
        v17 = *((_QWORD *)a1 + 5);
        v18 = *(void (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v17 + 72LL);
        IsUNCW = PathIsUNCW(pszPath);
        v20 = &pszStart;
        if ( !IsUNCW )
          v20 = pszPath;
        v18(v17, v20);
        dirs[0] = 0;
        v14 = SHParseDisplayName(ppszApplication, 0, (LPITEMIDLIST *)dirs, 0, 0);
        if ( v14 < 0 )
        {
          if ( (*(_BYTE *)a1 & 0x40) != 0 )
            v14 = 1;
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, PCWSTR))(**((_QWORD **)a1 + 5) + 40LL))(*((_QWORD *)a1 + 5), dirs[0]);
          ILFree((LPITEMIDLIST)dirs[0]);
        }
        if ( !v14 )
        {
          if ( a4 && *a4 )
          {
            v14 = StringCchCopyW(sz, 0x104u, a4);
          }
          else
          {
            FileNameW = PathFindFileNameW(ppszApplication);
            v14 = StringCchCopyW(sz, 0x104u, FileNameW);
            if ( v14 >= 0 )
            {
              PathRemoveExtensionW(sz);
              CharLowerW(sz);
              CharUpperBuffW(sz, 1u);
            }
          }
          if ( v14 >= 0 )
          {
            FileName_MakeLegal(sz);
            v14 = SHStrDupW(sz, ppwsz);
          }
        }
      }
      CoTaskMemFree(ppszApplication);
      CoTaskMemFree(ppszParameters);
    }
  }
  LocalFree(v9);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1804a91f8  push    rbp
0x1804a91fa  push    rbx
0x1804a91fb  push    rsi
0x1804a91fc  push    rdi
0x1804a91fd  push    r12
0x1804a91ff  push    r13
0x1804a9201  push    r14
0x1804a9203  push    r15
0x1804a9205  lea     rbp, [rsp-7A8h]
0x1804a920d  sub     rsp, 8A8h
0x1804a9214  mov     rax, cs:__security_cookie
0x1804a921b  xor     rax, rsp
0x1804a921e  mov     [rbp+7E0h+var_50], rax
0x1804a9225  mov     r13, [rbp+7E0h+ppwsz]
0x1804a922c  xor     edi, edi
0x1804a922e  mov     r12, r9
0x1804a9231  mov     r14, r8
0x1804a9234  mov     rbx, rdx
0x1804a9237  mov     r15, rcx
0x1804a923a  mov     esi, edi
0x1804a923c  mov     [r13+0], rdi
0x1804a9240  cmp     word ptr [rdx], 22h ; '"'
0x1804a9244  jnz     loc_1804A92CE
0x1804a924a  mov     rcx, rdx; pszSrch
0x1804a924d  call    cs:__imp_StrDupW
0x1804a9254  nop     dword ptr [rax+rax+00h]
0x1804a9259  mov     rsi, rax
0x1804a925c  test    rax, rax
0x1804a925f  jz      short loc_1804A92CE
0x1804a9261  mov     rcx, rax; lpString
0x1804a9264  call    cs:__imp_lstrlenW
0x1804a926b  nop     dword ptr [rax+rax+00h]
0x1804a9270  cmp     eax, 1
0x1804a9273  jle     short loc_1804A92CB
0x1804a9275  movsxd  rdi, eax
0x1804a9278  dec     rdi
0x1804a927b  lea     rdi, [rsi+rdi*2]
0x1804a927f  cmp     word ptr [rdi], 22h ; '"'
0x1804a9283  jnz     short loc_1804A92C9
0x1804a9285  lea     rbx, [rsi+2]
0x1804a9289  cmp     rbx, rdi
0x1804a928c  jnb     short loc_1804A92C9
0x1804a928e  movzx   ecx, word ptr [rbx]
0x1804a9291  mov     edx, 3FCh
0x1804a9296  call    cs:__imp_PathIsValidCharW
0x1804a929d  nop     dword ptr [rax+rax+00h]
0x1804a92a2  test    eax, eax
0x1804a92a4  jz      short loc_1804A92BA
0x1804a92a6  mov     rcx, rbx; lpsz
0x1804a92a9  call    cs:__imp_CharNextW
0x1804a92b0  nop     dword ptr [rax+rax+00h]
0x1804a92b5  mov     rbx, rax
0x1804a92b8  jmp     short loc_1804A9289
0x1804a92ba  mov     rcx, rsi; lpsz
0x1804a92bd  call    cs:__imp_PathUnquoteSpacesW
0x1804a92c4  nop     dword ptr [rax+rax+00h]
0x1804a92c9  xor     edi, edi
0x1804a92cb  mov     rbx, rsi
0x1804a92ce  mov     r10d, 104h
0x1804a92d4  lea     rcx, [rbp+7E0h+pszPath]; unsigned __int16 *
0x1804a92db  mov     edx, r10d; unsigned __int64
0x1804a92de  mov     r8, rbx; unsigned __int16 *
0x1804a92e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804a92e6  mov     ebx, eax
0x1804a92e8  test    eax, eax
0x1804a92ea  js      loc_1804A958E
0x1804a92f0  xor     r9d, r9d
0x1804a92f3  lea     rdx, [rbp+7E0h+var_260]
0x1804a92fa  mov     r8d, r10d
0x1804a92fd  lea     rcx, [rbp+7E0h+pszPath]
0x1804a9304  call    cs:__imp_PathSeperateArgs
0x1804a930b  nop     dword ptr [rax+rax+00h]
0x1804a9310  test    eax, eax
0x1804a9312  js      short loc_1804A935B
0x1804a9314  test    r14, r14
0x1804a9317  jz      short loc_1804A9341
0x1804a9319  mov     r8d, 3; fFlags
0x1804a931f  mov     [rsp+8E0h+dirs], r14
0x1804a9324  lea     rdx, [rsp+8E0h+dirs]; dirs
0x1804a9329  mov     [rsp+8E0h+var_898], rdi
0x1804a932e  lea     rcx, [rbp+7E0h+pszPath]; pszPath
0x1804a9335  call    cs:__imp_PathResolve
0x1804a933c  nop     dword ptr [rax+rax+00h]
0x1804a9341  lea     rdx, [rbp+7E0h+var_260]
0x1804a9348  lea     rcx, [rbp+7E0h+pszPath]
0x1804a934f  call    cs:__imp_PathComposeWithArgs
0x1804a9356  nop     dword ptr [rax+rax+00h]
0x1804a935b  lea     r9, [rsp+8E0h+ppszParameters]; ppszParameters
0x1804a9360  mov     [rsp+8E0h+ppszApplication], rdi
0x1804a9365  xor     r8d, r8d; ppszCommandLine
0x1804a9368  mov     [rsp+8E0h+ppszParameters], rdi
0x1804a936d  lea     rdx, [rsp+8E0h+ppszApplication]; ppszApplication
0x1804a9372  lea     rcx, [rbp+7E0h+pszPath]; pszCmdTemplate
0x1804a9379  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x1804a9380  nop     dword ptr [rax+rax+00h]
0x1804a9385  mov     ebx, eax
0x1804a9387  test    eax, eax
0x1804a9389  js      loc_1804A958E
0x1804a938f  mov     rcx, [r15+28h]
0x1804a9393  mov     rdx, [rsp+8E0h+ppszParameters]
0x1804a9398  mov     rax, [rcx]
0x1804a939b  mov     rax, [rax+58h]
0x1804a939f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a93a4  test    byte ptr [r15], 1
0x1804a93a8  jz      short loc_1804A93E3
0x1804a93aa  mov     rcx, [rsp+8E0h+ppszApplication]; pszPath
0x1804a93af  call    cs:__imp_PathIsUNCW
0x1804a93b6  nop     dword ptr [rax+rax+00h]
0x1804a93bb  test    eax, eax
0x1804a93bd  jz      short loc_1804A93E3
0x1804a93bf  mov     rcx, [rsp+8E0h+ppszApplication]; lpString
0x1804a93c4  call    cs:__imp_lstrlenW
0x1804a93cb  nop     dword ptr [rax+rax+00h]
0x1804a93d0  mov     rdx, [rsp+8E0h+ppszApplication]; unsigned __int16 *
0x1804a93d5  mov     rcx, r15; struct _DDECONV *
0x1804a93d8  lea     r8d, [rax+1]; unsigned int
0x1804a93dc  call    ?_DDE_RemapShare@@YAJPEAU_DDECONV@@PEAGK@Z; _DDE_RemapShare(_DDECONV *,ushort *,ulong)
0x1804a93e1  mov     ebx, eax
0x1804a93e3  test    ebx, ebx
0x1804a93e5  js      loc_1804A956C
0x1804a93eb  test    r14, r14
0x1804a93ee  jz      short loc_1804A93F6
0x1804a93f0  cmp     [r14], di
0x1804a93f4  jnz     short loc_1804A9426
0x1804a93f6  mov     r8, [rsp+8E0h+ppszApplication]; unsigned __int16 *
0x1804a93fb  lea     rcx, [rbp+7E0h+var_470]; unsigned __int16 *
0x1804a9402  mov     edx, 104h; unsigned __int64
0x1804a9407  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804a940c  lea     rcx, [rbp+7E0h+var_470]; pszPath
0x1804a9413  call    cs:__imp_PathRemoveFileSpecW
0x1804a941a  nop     dword ptr [rax+rax+00h]
0x1804a941f  lea     r14, [rbp+7E0h+var_470]
0x1804a9426  mov     rdi, [r15+28h]
0x1804a942a  mov     rcx, r14; pszPath
0x1804a942d  mov     rax, [rdi]
0x1804a9430  mov     rbx, [rax+48h]
0x1804a9434  call    cs:__imp_PathIsUNCW
0x1804a943b  nop     dword ptr [rax+rax+00h]
0x1804a9440  lea     rdx, pszStart
0x1804a9447  mov     rcx, rdi
0x1804a944a  test    eax, eax
0x1804a944c  mov     rax, rbx
0x1804a944f  cmovz   rdx, r14
0x1804a9453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a9458  mov     rcx, [rsp+8E0h+ppszApplication]; pszName
0x1804a945d  lea     r8, [rsp+8E0h+dirs]; ppidl
0x1804a9462  xor     edi, edi
0x1804a9464  xor     r9d, r9d; sfgaoIn
0x1804a9467  xor     edx, edx; pbc
0x1804a9469  mov     [rsp+8E0h+dirs], rdi
0x1804a946e  mov     [rsp+8E0h+psfgaoOut], rdi; psfgaoOut
0x1804a9473  call    cs:__imp_SHParseDisplayName
0x1804a947a  nop     dword ptr [rax+rax+00h]
0x1804a947f  mov     ebx, eax
0x1804a9481  test    eax, eax
0x1804a9483  js      short loc_1804A94B1
0x1804a9485  mov     rcx, [r15+28h]
0x1804a9489  mov     rdx, [rsp+8E0h+dirs]
0x1804a948e  mov     rax, [rcx]
0x1804a9491  mov     rax, [rax+28h]
0x1804a9495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804a949a  mov     rcx, [rsp+8E0h+dirs]; pidl
0x1804a949f  call    cs:__imp_ILFree
0x1804a94a6  nop     dword ptr [rax+rax+00h]
0x1804a94ab  lea     r14d, [rdi+1]
0x1804a94af  jmp     short loc_1804A94BF
0x1804a94b1  test    byte ptr [r15], 40h
0x1804a94b5  mov     r14d, 1
0x1804a94bb  cmovnz  ebx, r14d
0x1804a94bf  test    ebx, ebx
0x1804a94c1  jnz     loc_1804A956C
0x1804a94c7  test    r12, r12
0x1804a94ca  jz      short loc_1804A94E9
0x1804a94cc  cmp     [r12], di
0x1804a94d1  jz      short loc_1804A94E9
0x1804a94d3  mov     r8, r12; unsigned __int16 *
0x1804a94d6  lea     rcx, [rsp+8E0h+sz]; unsigned __int16 *
0x1804a94db  mov     edx, 104h; unsigned __int64
0x1804a94e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804a94e5  mov     ebx, eax
0x1804a94e7  jmp     short loc_1804A9548
0x1804a94e9  mov     rcx, [rsp+8E0h+ppszApplication]; pszPath
0x1804a94ee  call    cs:__imp_PathFindFileNameW
0x1804a94f5  nop     dword ptr [rax+rax+00h]
0x1804a94fa  mov     edx, 104h; unsigned __int64
0x1804a94ff  lea     rcx, [rsp+8E0h+sz]; unsigned __int16 *
0x1804a9504  mov     r8, rax; unsigned __int16 *
0x1804a9507  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804a950c  mov     ebx, eax
0x1804a950e  test    eax, eax
0x1804a9510  js      short loc_1804A9548
0x1804a9512  lea     rcx, [rsp+8E0h+sz]; pszPath
0x1804a9517  call    cs:__imp_PathRemoveExtensionW
0x1804a951e  nop     dword ptr [rax+rax+00h]
0x1804a9523  lea     rcx, [rsp+8E0h+sz]; lpsz
0x1804a9528  call    cs:__imp_CharLowerW
0x1804a952f  nop     dword ptr [rax+rax+00h]
0x1804a9534  mov     edx, r14d; cchLength
0x1804a9537  lea     rcx, [rsp+8E0h+sz]; lpsz
0x1804a953c  call    cs:__imp_CharUpperBuffW
0x1804a9543  nop     dword ptr [rax+rax+00h]
0x1804a9548  test    ebx, ebx
0x1804a954a  js      short loc_1804A956C
0x1804a954c  lea     rcx, [rsp+8E0h+sz]; lpsz
0x1804a9551  call    ?FileName_MakeLegal@@YAXPEAG@Z; FileName_MakeLegal(ushort *)
0x1804a9556  mov     rdx, r13; ppwsz
0x1804a9559  lea     rcx, [rsp+8E0h+sz]; psz
0x1804a955e  call    cs:__imp_SHStrDupW
0x1804a9565  nop     dword ptr [rax+rax+00h]
0x1804a956a  mov     ebx, eax
0x1804a956c  mov     rcx, [rsp+8E0h+ppszApplication]; pv
0x1804a9571  call    cs:__imp_CoTaskMemFree
0x1804a9578  nop     dword ptr [rax+rax+00h]
0x1804a957d  mov     rcx, [rsp+8E0h+ppszParameters]; pv
0x1804a9582  call    cs:__imp_CoTaskMemFree
0x1804a9589  nop     dword ptr [rax+rax+00h]
0x1804a958e  mov     rcx, rsi; hMem
0x1804a9591  call    cs:__imp_LocalFree
0x1804a9598  nop     dword ptr [rax+rax+00h]
0x1804a959d  mov     eax, ebx
0x1804a959f  mov     rcx, [rbp+7E0h+var_50]
0x1804a95a6  xor     rcx, rsp; StackCookie
0x1804a95a9  call    __security_check_cookie
0x1804a95ae  add     rsp, 8A8h
0x1804a95b5  pop     r15
0x1804a95b7  pop     r14
0x1804a95b9  pop     r13
0x1804a95bb  pop     r12
0x1804a95bd  pop     rdi
0x1804a95be  pop     rsi
0x1804a95bf  pop     rbx
0x1804a95c0  pop     rbp
0x1804a95c1  retn
```
