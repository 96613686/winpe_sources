# _DDE_EvaluateCommandLine(_DDECONV *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18047470c`
- end: `0x180474a48`
- name: `?_DDE_EvaluateCommandLine@@YAJPEAU_DDECONV@@PEBG11PEAPEAG@Z`
- size: `828`
- prototype: `__int64 __fastcall(struct _DDECONV *, const unsigned __int16 *, LPCWSTR pszPath, const unsigned __int16 *, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180472120`

## callees

- `0x18001bf10`
- `0x180233280`
- `0x1804735e0`
- `0x18047470c`
- `0x180474a50`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180474a1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180474a1d`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1804749d2`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1804749d2`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1804749e0`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1804749e0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1804747a7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1804747a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18047475d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18047475d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18047476e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180474898`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18047476e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180474898`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1804748e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1804748e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1804749a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1804749a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1804749c7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1804749c7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x18047479a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x18047479a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180474889`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804748fc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180474889`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1804748fc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1804747b5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1804747b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180474a09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180474a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180474a09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180474a14`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1804749fc`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1804749fc`
- `Windows.Storage!PathComposeWithArgs` at `0x180474835`
- `Windows.Storage!PathComposeWithArgs` at `0x180474835`
- `Windows.Storage!SHParseDisplayName` at `0x180474935`
- `Windows.Storage!SHParseDisplayName` at `0x180474935`
- `Windows.Storage!ILFree` at `0x18047495b`
- `Windows.Storage!ILFree` at `0x18047495b`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x180474859`
- `Windows.Storage!SHEvaluateSystemCommandTemplate` at `0x180474859`
- `Windows.Storage!PathSeperateArgs` at `0x1804747f6`
- `Windows.Storage!PathSeperateArgs` at `0x1804747f6`
- `Windows.Storage!PathResolve` at `0x180474821`
- `Windows.Storage!PathResolve` at `0x180474821`

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
  void (__fastcall *v18)(__int64, const size_t *); // rbx
  BOOL IsUNCW; // eax
  const size_t *v20; // rdx
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
        v18 = *(void (__fastcall **)(__int64, const size_t *))(*(_QWORD *)v17 + 72LL);
        IsUNCW = PathIsUNCW(pszPath);
        v20 = &pszStart;
        if ( !IsUNCW )
          v20 = (const size_t *)pszPath;
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
0x18047470c  push    rbp
0x18047470e  push    rbx
0x18047470f  push    rsi
0x180474710  push    rdi
0x180474711  push    r12
0x180474713  push    r13
0x180474715  push    r14
0x180474717  push    r15
0x180474719  lea     rbp, [rsp-7A8h]
0x180474721  sub     rsp, 8A8h
0x180474728  mov     rax, cs:__security_cookie
0x18047472f  xor     rax, rsp
0x180474732  mov     [rbp+7E0h+var_50], rax
0x180474739  mov     r13, [rbp+7E0h+ppwsz]
0x180474740  xor     edi, edi
0x180474742  mov     r12, r9
0x180474745  mov     r14, r8
0x180474748  mov     rbx, rdx
0x18047474b  mov     r15, rcx
0x18047474e  mov     esi, edi
0x180474750  mov     [r13+0], rdi
0x180474754  cmp     word ptr [rdx], 22h ; '"'
0x180474758  jnz     short loc_1804747C0
0x18047475a  mov     rcx, rdx; pszSrch
0x18047475d  call    cs:__imp_StrDupW
0x180474763  mov     rsi, rax
0x180474766  test    rax, rax
0x180474769  jz      short loc_1804747C0
0x18047476b  mov     rcx, rax; lpString
0x18047476e  call    cs:__imp_lstrlenW
0x180474774  cmp     eax, 1
0x180474777  jle     short loc_1804747BD
0x180474779  movsxd  rdi, eax
0x18047477c  dec     rdi
0x18047477f  lea     rdi, [rsi+rdi*2]
0x180474783  cmp     word ptr [rdi], 22h ; '"'
0x180474787  jnz     short loc_1804747BB
0x180474789  lea     rbx, [rsi+2]
0x18047478d  cmp     rbx, rdi
0x180474790  jnb     short loc_1804747BB
0x180474792  movzx   ecx, word ptr [rbx]
0x180474795  mov     edx, 3FCh
0x18047479a  call    cs:__imp_PathIsValidCharW
0x1804747a0  test    eax, eax
0x1804747a2  jz      short loc_1804747B2
0x1804747a4  mov     rcx, rbx; lpsz
0x1804747a7  call    cs:__imp_CharNextW
0x1804747ad  mov     rbx, rax
0x1804747b0  jmp     short loc_18047478D
0x1804747b2  mov     rcx, rsi; lpsz
0x1804747b5  call    cs:__imp_PathUnquoteSpacesW
0x1804747bb  xor     edi, edi
0x1804747bd  mov     rbx, rsi
0x1804747c0  mov     r10d, 104h
0x1804747c6  lea     rcx, [rbp+7E0h+pszPath]; unsigned __int16 *
0x1804747cd  mov     edx, r10d; unsigned __int64
0x1804747d0  mov     r8, rbx; unsigned __int16 *
0x1804747d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804747d8  mov     ebx, eax
0x1804747da  test    eax, eax
0x1804747dc  js      loc_180474A1A
0x1804747e2  xor     r9d, r9d
0x1804747e5  lea     rdx, [rbp+7E0h+var_260]
0x1804747ec  mov     r8d, r10d
0x1804747ef  lea     rcx, [rbp+7E0h+pszPath]
0x1804747f6  call    cs:__imp_PathSeperateArgs
0x1804747fc  test    eax, eax
0x1804747fe  js      short loc_18047483B
0x180474800  test    r14, r14
0x180474803  jz      short loc_180474827
0x180474805  mov     r8d, 3; fFlags
0x18047480b  mov     [rsp+8E0h+dirs], r14
0x180474810  lea     rdx, [rsp+8E0h+dirs]; dirs
0x180474815  mov     [rsp+8E0h+var_898], rdi
0x18047481a  lea     rcx, [rbp+7E0h+pszPath]; pszPath
0x180474821  call    cs:__imp_PathResolve
0x180474827  lea     rdx, [rbp+7E0h+var_260]
0x18047482e  lea     rcx, [rbp+7E0h+pszPath]
0x180474835  call    cs:__imp_PathComposeWithArgs
0x18047483b  lea     r9, [rsp+8E0h+ppszParameters]; ppszParameters
0x180474840  mov     [rsp+8E0h+ppszApplication], rdi
0x180474845  xor     r8d, r8d; ppszCommandLine
0x180474848  mov     [rsp+8E0h+ppszParameters], rdi
0x18047484d  lea     rdx, [rsp+8E0h+ppszApplication]; ppszApplication
0x180474852  lea     rcx, [rbp+7E0h+pszPath]; pszCmdTemplate
0x180474859  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18047485f  mov     ebx, eax
0x180474861  test    eax, eax
0x180474863  js      loc_180474A1A
0x180474869  mov     rcx, [r15+28h]
0x18047486d  mov     rdx, [rsp+8E0h+ppszParameters]
0x180474872  mov     rax, [rcx]
0x180474875  mov     rax, [rax+58h]
0x180474879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047487e  test    byte ptr [r15], 1
0x180474882  jz      short loc_1804748B1
0x180474884  mov     rcx, [rsp+8E0h+ppszApplication]; pszPath
0x180474889  call    cs:__imp_PathIsUNCW
0x18047488f  test    eax, eax
0x180474891  jz      short loc_1804748B1
0x180474893  mov     rcx, [rsp+8E0h+ppszApplication]; lpString
0x180474898  call    cs:__imp_lstrlenW
0x18047489e  mov     rdx, [rsp+8E0h+ppszApplication]; unsigned __int16 *
0x1804748a3  mov     rcx, r15; struct _DDECONV *
0x1804748a6  lea     r8d, [rax+1]; unsigned int
0x1804748aa  call    ?_DDE_RemapShare@@YAJPEAU_DDECONV@@PEAGK@Z; _DDE_RemapShare(_DDECONV *,ushort *,ulong)
0x1804748af  mov     ebx, eax
0x1804748b1  test    ebx, ebx
0x1804748b3  js      loc_180474A04
0x1804748b9  test    r14, r14
0x1804748bc  jz      short loc_1804748C4
0x1804748be  cmp     [r14], di
0x1804748c2  jnz     short loc_1804748EE
0x1804748c4  mov     r8, [rsp+8E0h+ppszApplication]; unsigned __int16 *
0x1804748c9  lea     rcx, [rbp+7E0h+var_470]; unsigned __int16 *
0x1804748d0  mov     edx, 104h; unsigned __int64
0x1804748d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804748da  lea     rcx, [rbp+7E0h+var_470]; pszPath
0x1804748e1  call    cs:__imp_PathRemoveFileSpecW
0x1804748e7  lea     r14, [rbp+7E0h+var_470]
0x1804748ee  mov     rdi, [r15+28h]
0x1804748f2  mov     rcx, r14; pszPath
0x1804748f5  mov     rax, [rdi]
0x1804748f8  mov     rbx, [rax+48h]
0x1804748fc  call    cs:__imp_PathIsUNCW
0x180474902  lea     rdx, pszStart
0x180474909  mov     rcx, rdi
0x18047490c  test    eax, eax
0x18047490e  mov     rax, rbx
0x180474911  cmovz   rdx, r14
0x180474915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047491a  mov     rcx, [rsp+8E0h+ppszApplication]; pszName
0x18047491f  lea     r8, [rsp+8E0h+dirs]; ppidl
0x180474924  xor     edi, edi
0x180474926  xor     r9d, r9d; sfgaoIn
0x180474929  xor     edx, edx; pbc
0x18047492b  mov     [rsp+8E0h+dirs], rdi
0x180474930  mov     [rsp+8E0h+psfgaoOut], rdi; psfgaoOut
0x180474935  call    cs:__imp_SHParseDisplayName
0x18047493b  mov     ebx, eax
0x18047493d  test    eax, eax
0x18047493f  js      short loc_180474967
0x180474941  mov     rcx, [r15+28h]
0x180474945  mov     rdx, [rsp+8E0h+dirs]
0x18047494a  mov     rax, [rcx]
0x18047494d  mov     rax, [rax+28h]
0x180474951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180474956  mov     rcx, [rsp+8E0h+dirs]; pidl
0x18047495b  call    cs:__imp_ILFree
0x180474961  lea     r14d, [rdi+1]
0x180474965  jmp     short loc_180474975
0x180474967  test    byte ptr [r15], 40h
0x18047496b  mov     r14d, 1
0x180474971  cmovnz  ebx, r14d
0x180474975  test    ebx, ebx
0x180474977  jnz     loc_180474A04
0x18047497d  test    r12, r12
0x180474980  jz      short loc_18047499F
0x180474982  cmp     [r12], di
0x180474987  jz      short loc_18047499F
0x180474989  mov     r8, r12; unsigned __int16 *
0x18047498c  lea     rcx, [rsp+8E0h+sz]; unsigned __int16 *
0x180474991  mov     edx, 104h; unsigned __int64
0x180474996  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18047499b  mov     ebx, eax
0x18047499d  jmp     short loc_1804749E6
0x18047499f  mov     rcx, [rsp+8E0h+ppszApplication]; pszPath
0x1804749a4  call    cs:__imp_PathFindFileNameW
0x1804749aa  mov     edx, 104h; unsigned __int64
0x1804749af  lea     rcx, [rsp+8E0h+sz]; unsigned __int16 *
0x1804749b4  mov     r8, rax; unsigned __int16 *
0x1804749b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1804749bc  mov     ebx, eax
0x1804749be  test    eax, eax
0x1804749c0  js      short loc_1804749E6
0x1804749c2  lea     rcx, [rsp+8E0h+sz]; pszPath
0x1804749c7  call    cs:__imp_PathRemoveExtensionW
0x1804749cd  lea     rcx, [rsp+8E0h+sz]; lpsz
0x1804749d2  call    cs:__imp_CharLowerW
0x1804749d8  mov     edx, r14d; cchLength
0x1804749db  lea     rcx, [rsp+8E0h+sz]; lpsz
0x1804749e0  call    cs:__imp_CharUpperBuffW
0x1804749e6  test    ebx, ebx
0x1804749e8  js      short loc_180474A04
0x1804749ea  lea     rcx, [rsp+8E0h+sz]; lpsz
0x1804749ef  call    ?FileName_MakeLegal@@YAXPEAG@Z; FileName_MakeLegal(ushort *)
0x1804749f4  mov     rdx, r13; ppwsz
0x1804749f7  lea     rcx, [rsp+8E0h+sz]; psz
0x1804749fc  call    cs:__imp_SHStrDupW
0x180474a02  mov     ebx, eax
0x180474a04  mov     rcx, [rsp+8E0h+ppszApplication]; pv
0x180474a09  call    cs:__imp_CoTaskMemFree
0x180474a0f  mov     rcx, [rsp+8E0h+ppszParameters]; pv
0x180474a14  call    cs:__imp_CoTaskMemFree
0x180474a1a  mov     rcx, rsi; hMem
0x180474a1d  call    cs:__imp_LocalFree
0x180474a23  mov     eax, ebx
0x180474a25  mov     rcx, [rbp+7E0h+var_50]
0x180474a2c  xor     rcx, rsp; StackCookie
0x180474a2f  call    __security_check_cookie
0x180474a34  add     rsp, 8A8h
0x180474a3b  pop     r15
0x180474a3d  pop     r14
0x180474a3f  pop     r13
0x180474a41  pop     r12
0x180474a43  pop     rdi
0x180474a44  pop     rsi
0x180474a45  pop     rbx
0x180474a46  pop     rbp
0x180474a47  retn
```
