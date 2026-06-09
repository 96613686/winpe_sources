# CThemePackManager::_SetFileList(ITheme *,ushort const *)

- ea: `0x180064a38`
- end: `0x180065032`
- name: `?_SetFileList@CThemePackManager@@AEAAJPEAUITheme@@PEBG@Z`
- size: `1530`
- prototype: `__int64 __fastcall(CThemePackManager *__hidden this, struct ITheme *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180062f3c`

## callees

- `0x180008dd8`
- `0x18000ab00`
- `0x1800179e0`
- `0x1800358c0`
- `0x180064328`
- `0x180064a38`
- `0x180068c08`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrCmpNW` at `0x180064aca`
- `SHLWAPI!StrCmpNW` at `0x180064aca`
- `SHLWAPI!PathIsFileSpecW` at `0x180064d5f`
- `SHLWAPI!PathIsFileSpecW` at `0x180064e5c`
- `SHLWAPI!PathIsFileSpecW` at `0x180064f66`
- `SHLWAPI!PathIsFileSpecW` at `0x180064d5f`
- `SHLWAPI!PathIsFileSpecW` at `0x180064e5c`
- `SHLWAPI!PathIsFileSpecW` at `0x180064f66`
- `SHLWAPI!PathIsRelativeW` at `0x180064b58`
- `SHLWAPI!PathIsRelativeW` at `0x180064bff`
- `SHLWAPI!PathIsRelativeW` at `0x180064b58`
- `SHLWAPI!PathIsRelativeW` at `0x180064bff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180064c9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180064c9e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064b88`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064c2c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064cbb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064da1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064e9e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064fa8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064b88`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064c2c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064cbb`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064da1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064e9e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180064fa8`
- `OLEAUT32!__imp_SysFreeString` at `0x180064c56`
- `OLEAUT32!__imp_SysFreeString` at `0x180064ce5`
- `OLEAUT32!__imp_SysFreeString` at `0x180064dcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180064ec9`
- `OLEAUT32!__imp_SysFreeString` at `0x180064fd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180065000`
- `OLEAUT32!__imp_SysFreeString` at `0x180064c56`
- `OLEAUT32!__imp_SysFreeString` at `0x180064ce5`
- `OLEAUT32!__imp_SysFreeString` at `0x180064dcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180064ec9`
- `OLEAUT32!__imp_SysFreeString` at `0x180064fd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180065000`

## pseudocode

```c
__int64 __fastcall CThemePackManager::_SetFileList(
        CThemePackManager *this,
        struct ITheme *a2,
        const unsigned __int16 *a3)
{
  int **v3; // rax
  const WCHAR *v5; // r13
  int v7; // r15d
  int v8; // edi
  int *Ptr; // rbx
  int v10; // eax
  __int64 v11; // rax
  HRESULT v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // r15d
  OLECHAR *v16; // rbx
  int v17; // r15d
  OLECHAR *v18; // rbx
  const struct THEME_FALLBACK_VALUES near *v19; // rax
  int v20; // r15d
  OLECHAR *v21; // rbx
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszMore; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = (int **)*((_QWORD *)this + 548);
  pszMore = a3;
  v5 = a3;
  if ( *v3 )
  {
    v7 = **v3;
    v8 = 0;
    if ( v7 > 0 )
    {
      do
      {
        Ptr = (int *)g_pfn_DPA_GetPtr(**((HDPA **)this + 548), v8);
        *((_WORD *)Ptr + 264) = 128;
        if ( StrCmpNW((PCWSTR)Ptr + 2, L"DesktopBackground", 17) )
        {
          Ptr[133] = 0;
        }
        else
        {
          v10 = VerifyResourceFile((const unsigned __int16 *)Ptr + 2, 0);
          Ptr[133] = v10;
          if ( v10 )
          {
            ++*((_DWORD *)this + 39);
            *((_QWORD *)this + 20) += *Ptr;
          }
        }
        ++v8;
        Ptr[134] = 0;
      }
      while ( v8 < v7 );
      v5 = pszMore;
    }
  }
  v11 = *(_QWORD *)a2;
  pszPath = 0;
  v12 = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, LPCWSTR *))(v11 + 168))(a2, &pszPath) < 0
    || !pszPath
    || !(unsigned int)VerifyResourceFile(pszPath, 0)
    || !PathIsRelativeW(pszPath)
    || (v12 = CThemePackManager::_MarkFileToCopy(this, pszPath), v12 >= 0)
    && (v12 = PathCchCombine(pszPathOut, 0x104u, v5, pszPath), v12 >= 0)
    && (v12 = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)a2 + 176LL))(a2, pszPathOut), v12 >= 0) )
  {
    v13 = *(_QWORD *)a2;
    pszMore = 0;
    if ( (*(int (__fastcall **)(struct ITheme *, LPCWSTR *))(v13 + 536))(a2, &pszMore) >= 0 )
    {
      if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&pszMore) )
      {
        if ( (unsigned int)VerifyResourceFile(pszMore, 4) )
        {
          if ( PathIsRelativeW(pszMore) )
          {
            v12 = CThemePackManager::_MarkFileToCopy(this, pszMore);
            if ( v12 >= 0 )
            {
              v12 = PathCchCombine(pszPathOut, 0x104u, v5, pszMore);
              if ( v12 >= 0 )
                v12 = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)a2 + 544LL))(a2, pszPathOut);
            }
          }
        }
      }
    }
    SysFreeString((BSTR)pszMore);
    if ( v12 >= 0 )
    {
      v14 = *(_QWORD *)a2;
      pszMore = 0;
      if ( (*(int (__fastcall **)(struct ITheme *, LPCWSTR *))(v14 + 240))(a2, &pszMore) >= 0
        && CompareStringOrdinal(pszMore, -1, L"DesktopBackground", -1, 1) == 2 )
      {
        v12 = PathCchCombine(pszPathOut, 0x104u, v5, L"DesktopBackground");
        if ( v12 >= 0 )
          v12 = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)a2 + 248LL))(a2, pszPathOut);
      }
      SysFreeString((BSTR)pszMore);
      if ( v12 >= 0 )
      {
        v15 = 0;
        if ( !*(_WORD *)c_rgszDesktopIcons )
          goto LABEL_39;
        do
        {
          ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&pszMore, (const unsigned __int16 *)(&c_rgszDesktopIcons)[v15]);
          v16 = (OLECHAR *)pszMore;
          if ( (*(int (__fastcall **)(struct ITheme *, LPCWSTR, __int64, LPCWSTR *))(*(_QWORD *)a2 + 360LL))(
                 a2,
                 pszMore,
                 1,
                 &pszPath) >= 0 )
          {
            if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&pszPath) )
            {
              if ( PathIsFileSpecW(pszPath) )
              {
                if ( (unsigned int)VerifyResourceFile(pszPath, 1) )
                {
                  v12 = CThemePackManager::_MarkFileToCopy(this, pszPath);
                  if ( v12 >= 0 )
                  {
                    v12 = PathCchCombine(pszPathOut, 0x104u, v5, pszPath);
                    if ( v12 >= 0 )
                      v12 = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *, WCHAR *))(*(_QWORD *)a2 + 376LL))(
                              a2,
                              v16,
                              pszPathOut);
                  }
                }
              }
            }
          }
          SysFreeString(v16);
          ++v15;
        }
        while ( *(_WORD *)(&c_rgszDesktopIcons)[v15] );
        if ( v12 >= 0 )
        {
LABEL_39:
          v17 = 0;
          if ( !aArrow[0] )
            goto LABEL_49;
          do
          {
            ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&pszMore, off_18006E940[v17]);
            v18 = (OLECHAR *)pszMore;
            if ( (*(int (__fastcall **)(struct ITheme *, LPCWSTR, LPCWSTR *))(*(_QWORD *)a2 + 304LL))(
                   a2,
                   pszMore,
                   &pszPath) >= 0 )
            {
              if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&pszPath) )
              {
                if ( PathIsFileSpecW(pszPath) )
                {
                  if ( (unsigned int)VerifyResourceFile(pszPath, 2) )
                  {
                    v12 = CThemePackManager::_MarkFileToCopy(this, pszPath);
                    if ( v12 >= 0 )
                    {
                      v12 = PathCchCombine(pszPathOut, 0x104u, v5, pszPath);
                      if ( v12 >= 0 )
                        v12 = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *, WCHAR *))(*(_QWORD *)a2 + 312LL))(
                                a2,
                                v18,
                                pszPathOut);
                    }
                  }
                }
              }
            }
            SysFreeString(v18);
            ++v17;
          }
          while ( *off_18006E940[v17] );
          if ( v12 >= 0 )
          {
LABEL_49:
            v19 = c_rgThemeSoundsValues;
            v20 = 0;
            while ( *(_WORD *)v19 )
            {
              ATL::CComBSTR::CComBSTR(
                (ATL::CComBSTR *)&pszMore,
                *((const unsigned __int16 **)&c_rgThemeSoundsValues + 2 * v20));
              v21 = (OLECHAR *)pszMore;
              if ( (*(int (__fastcall **)(struct ITheme *, LPCWSTR, _QWORD, LPCWSTR *))(*(_QWORD *)a2 + 336LL))(
                     a2,
                     pszMore,
                     (unsigned int)dword_18006FAF8[4 * v20],
                     &pszPath) >= 0 )
              {
                if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&pszPath) )
                {
                  if ( PathIsFileSpecW(pszPath) )
                  {
                    if ( (unsigned int)VerifyResourceFile(pszPath, 3) )
                    {
                      v12 = CThemePackManager::_MarkFileToCopy(this, pszPath);
                      if ( v12 >= 0 )
                      {
                        v12 = PathCchCombine(pszPathOut, 0x104u, v5, pszPath);
                        if ( v12 >= 0 )
                          v12 = (*(__int64 (__fastcall **)(struct ITheme *, OLECHAR *, WCHAR *))(*(_QWORD *)a2 + 344LL))(
                                  a2,
                                  v21,
                                  pszPathOut);
                      }
                    }
                  }
                }
              }
              SysFreeString(v21);
              v19 = (const struct THEME_FALLBACK_VALUES near *)*((_QWORD *)&c_rgThemeSoundsValues + 2 * ++v20);
            }
          }
        }
      }
    }
  }
  SysFreeString((BSTR)pszPath);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180064a38  mov     [rsp-8+arg_18], rbx
0x180064a3d  push    rbp
0x180064a3e  push    rsi
0x180064a3f  push    rdi
0x180064a40  push    r12
0x180064a42  push    r13
0x180064a44  push    r14
0x180064a46  push    r15
0x180064a48  lea     rbp, [rsp-160h]
0x180064a50  sub     rsp, 260h
0x180064a57  mov     rax, cs:__security_cookie
0x180064a5e  xor     rax, rsp
0x180064a61  mov     [rbp+190h+var_40], rax
0x180064a68  mov     rax, [rcx+1120h]
0x180064a6f  mov     r14, rcx
0x180064a72  xor     r12d, r12d
0x180064a75  mov     [rsp+290h+pszMore], r8
0x180064a7a  mov     r13, r8
0x180064a7d  mov     rsi, rdx
0x180064a80  mov     rcx, [rax]
0x180064a83  test    rcx, rcx
0x180064a86  jz      loc_180064B16
0x180064a8c  mov     r15d, [rcx]
0x180064a8f  mov     edi, r12d
0x180064a92  test    r15d, r15d
0x180064a95  jle     short loc_180064B16
0x180064a97  xor     r13d, r13d
0x180064a9a  mov     rcx, [r14+1120h]
0x180064aa1  movsxd  rdx, edi; i
0x180064aa4  mov     rcx, [rcx]; hdpa
0x180064aa7  call    cs:g_pfn_DPA_GetPtr
0x180064aad  mov     r8d, 11h; nChar
0x180064ab3  lea     rdx, aDesktopbackgro; "DesktopBackground"
0x180064aba  mov     rbx, rax
0x180064abd  lea     rcx, [rax+4]; psz1
0x180064ac1  mov     word ptr [rax+210h], 80h
0x180064aca  call    cs:__imp_StrCmpNW
0x180064ad0  test    eax, eax
0x180064ad2  jnz     short loc_180064AFC
0x180064ad4  xor     edx, edx; int
0x180064ad6  lea     rcx, [rbx+4]; unsigned __int16 *
0x180064ada  call    ?VerifyResourceFile@@YAHPEBGH@Z; VerifyResourceFile(ushort const *,int)
0x180064adf  mov     [rbx+214h], eax
0x180064ae5  test    eax, eax
0x180064ae7  jz      short loc_180064B03
0x180064ae9  inc     dword ptr [r14+9Ch]
0x180064af0  movsxd  rax, dword ptr [rbx]
0x180064af3  add     [r14+0A0h], rax
0x180064afa  jmp     short loc_180064B03
0x180064afc  mov     [rbx+214h], r13d
0x180064b03  inc     edi
0x180064b05  mov     [rbx+218h], r13d
0x180064b0c  cmp     edi, r15d
0x180064b0f  jl      short loc_180064A9A
0x180064b11  mov     r13, [rsp+290h+pszMore]
0x180064b16  mov     rax, [rsi]
0x180064b19  lea     rdx, [rsp+290h+pszPath]
0x180064b1e  mov     rcx, rsi
0x180064b21  mov     [rsp+290h+pszPath], r12
0x180064b26  mov     edi, r12d
0x180064b29  mov     rax, [rax+0A8h]
0x180064b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b35  mov     ebx, 104h
0x180064b3a  test    eax, eax
0x180064b3c  js      short loc_180064BB9
0x180064b3e  mov     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x180064b43  test    rcx, rcx
0x180064b46  jz      short loc_180064BB9
0x180064b48  xor     edx, edx; int
0x180064b4a  call    ?VerifyResourceFile@@YAHPEBGH@Z; VerifyResourceFile(ushort const *,int)
0x180064b4f  test    eax, eax
0x180064b51  jz      short loc_180064BB9
0x180064b53  mov     rcx, [rsp+290h+pszPath]; pszPath
0x180064b58  call    cs:__imp_PathIsRelativeW
0x180064b5e  test    eax, eax
0x180064b60  jz      short loc_180064BB9
0x180064b62  mov     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x180064b67  mov     rcx, r14; this
0x180064b6a  call    ?_MarkFileToCopy@CThemePackManager@@AEAAJPEBG@Z; CThemePackManager::_MarkFileToCopy(ushort const *)
0x180064b6f  mov     edi, eax
0x180064b71  test    eax, eax
0x180064b73  js      loc_180064FFB
0x180064b79  mov     r9, [rsp+290h+pszPath]; pszMore
0x180064b7e  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180064b83  mov     r8, r13; pszPathIn
0x180064b86  mov     edx, ebx; cchPathOut
0x180064b88  call    cs:__imp_PathCchCombine
0x180064b8e  mov     edi, eax
0x180064b90  test    eax, eax
0x180064b92  js      loc_180064FFB
0x180064b98  mov     rax, [rsi]
0x180064b9b  lea     rdx, [rsp+290h+pszPathOut]
0x180064ba0  mov     rcx, rsi
0x180064ba3  mov     rax, [rax+0B0h]
0x180064baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064baf  mov     edi, eax
0x180064bb1  test    eax, eax
0x180064bb3  js      loc_180064FFB
0x180064bb9  mov     rax, [rsi]
0x180064bbc  lea     rdx, [rsp+290h+pszMore]
0x180064bc1  mov     rcx, rsi
0x180064bc4  mov     [rsp+290h+pszMore], r12
0x180064bc9  mov     rax, [rax+218h]
0x180064bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bd5  test    eax, eax
0x180064bd7  js      short loc_180064C51
0x180064bd9  lea     rcx, [rsp+290h+pszMore]; this
0x180064bde  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180064be3  test    eax, eax
0x180064be5  jz      short loc_180064C51
0x180064be7  mov     rcx, [rsp+290h+pszMore]; unsigned __int16 *
0x180064bec  mov     edx, 4; int
0x180064bf1  call    ?VerifyResourceFile@@YAHPEBGH@Z; VerifyResourceFile(ushort const *,int)
0x180064bf6  test    eax, eax
0x180064bf8  jz      short loc_180064C51
0x180064bfa  mov     rcx, [rsp+290h+pszMore]; pszPath
0x180064bff  call    cs:__imp_PathIsRelativeW
0x180064c05  test    eax, eax
0x180064c07  jz      short loc_180064C51
0x180064c09  mov     rdx, [rsp+290h+pszMore]; unsigned __int16 *
0x180064c0e  mov     rcx, r14; this
0x180064c11  call    ?_MarkFileToCopy@CThemePackManager@@AEAAJPEBG@Z; CThemePackManager::_MarkFileToCopy(ushort const *)
0x180064c16  mov     edi, eax
0x180064c18  test    eax, eax
0x180064c1a  js      short loc_180064C51
0x180064c1c  mov     r9, [rsp+290h+pszMore]; pszMore
0x180064c21  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180064c26  mov     r8, r13; pszPathIn
0x180064c29  mov     rdx, rbx; cchPathOut
0x180064c2c  call    cs:__imp_PathCchCombine
0x180064c32  mov     edi, eax
0x180064c34  test    eax, eax
0x180064c36  js      short loc_180064C51
0x180064c38  mov     rax, [rsi]
0x180064c3b  lea     rdx, [rsp+290h+pszPathOut]
0x180064c40  mov     rcx, rsi
0x180064c43  mov     rax, [rax+220h]
0x180064c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c4f  mov     edi, eax
0x180064c51  mov     rcx, [rsp+290h+pszMore]; bstrString
0x180064c56  call    cs:__imp_SysFreeString
0x180064c5c  test    edi, edi
0x180064c5e  js      loc_180064FFB
0x180064c64  mov     rax, [rsi]
0x180064c67  lea     rdx, [rsp+290h+pszMore]
0x180064c6c  mov     rcx, rsi
0x180064c6f  mov     [rsp+290h+pszMore], r12
0x180064c74  mov     rax, [rax+0F0h]
0x180064c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c80  test    eax, eax
0x180064c82  js      short loc_180064CE0
0x180064c84  mov     rcx, [rsp+290h+pszMore]; lpString1
0x180064c89  lea     r8, aDesktopbackgro; "DesktopBackground"
0x180064c90  or      edx, 0FFFFFFFFh; cchCount1
0x180064c93  mov     [rsp+290h+bIgnoreCase], 1; bIgnoreCase
0x180064c9b  mov     r9d, edx; cchCount2
0x180064c9e  call    cs:__imp_CompareStringOrdinal
0x180064ca4  cmp     eax, 2
0x180064ca7  jnz     short loc_180064CE0
0x180064ca9  lea     r9, aDesktopbackgro; "DesktopBackground"
0x180064cb0  mov     r8, r13; pszPathIn
0x180064cb3  mov     rdx, rbx; cchPathOut
0x180064cb6  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180064cbb  call    cs:__imp_PathCchCombine
0x180064cc1  mov     edi, eax
0x180064cc3  test    eax, eax
0x180064cc5  js      short loc_180064CE0
0x180064cc7  mov     rax, [rsi]
0x180064cca  lea     rdx, [rsp+290h+pszPathOut]
0x180064ccf  mov     rcx, rsi
0x180064cd2  mov     rax, [rax+0F8h]
0x180064cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cde  mov     edi, eax
0x180064ce0  mov     rcx, [rsp+290h+pszMore]; bstrString
0x180064ce5  call    cs:__imp_SysFreeString
0x180064ceb  test    edi, edi
0x180064ced  js      loc_180064FFB
0x180064cf3  mov     rax, cs:?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x180064cfa  lea     r8, __ImageBase
0x180064d01  mov     r15d, r12d
0x180064d04  cmp     [rax], r12w
0x180064d08  jz      loc_180064DFD
0x180064d0e  movsxd  rdx, r15d
0x180064d11  lea     rcx, [rsp+290h+pszMore]; this
0x180064d16  mov     rdx, ds:rva ?c_rgszDesktopIcons@@3QBQEBGB[r8+rdx*8]; unsigned __int16 *
0x180064d1e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180064d23  mov     rax, [rsi]
0x180064d26  lea     r9, [rsp+290h+pszPath]
0x180064d2b  mov     rbx, [rsp+290h+pszMore]
0x180064d30  mov     r8d, 1
0x180064d36  mov     rdx, rbx
0x180064d39  mov     rcx, rsi
0x180064d3c  mov     rax, [rax+168h]
0x180064d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d48  test    eax, eax
0x180064d4a  js      short loc_180064DC9
0x180064d4c  lea     rcx, [rsp+290h+pszPath]; this
0x180064d51  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180064d56  test    eax, eax
0x180064d58  jz      short loc_180064DC9
0x180064d5a  mov     rcx, [rsp+290h+pszPath]; pszPath
0x180064d5f  call    cs:__imp_PathIsFileSpecW
0x180064d65  test    eax, eax
0x180064d67  jz      short loc_180064DC9
0x180064d69  mov     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x180064d6e  mov     edx, 1; int
0x180064d73  call    ?VerifyResourceFile@@YAHPEBGH@Z; VerifyResourceFile(ushort const *,int)
0x180064d78  test    eax, eax
0x180064d7a  jz      short loc_180064DC9
0x180064d7c  mov     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x180064d81  mov     rcx, r14; this
0x180064d84  call    ?_MarkFileToCopy@CThemePackManager@@AEAAJPEBG@Z; CThemePackManager::_MarkFileToCopy(ushort const *)
0x180064d89  mov     edi, eax
0x180064d8b  test    eax, eax
0x180064d8d  js      short loc_180064DC9
0x180064d8f  mov     r9, [rsp+290h+pszPath]; pszMore
0x180064d94  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180064d99  mov     r8, r13; pszPathIn
0x180064d9c  mov     edx, 104h; cchPathOut
0x180064da1  call    cs:__imp_PathCchCombine
0x180064da7  mov     edi, eax
0x180064da9  test    eax, eax
0x180064dab  js      short loc_180064DC9
0x180064dad  mov     rax, [rsi]
0x180064db0  lea     r8, [rsp+290h+pszPathOut]
0x180064db5  mov     rdx, rbx
0x180064db8  mov     rcx, rsi
0x180064dbb  mov     rax, [rax+178h]
0x180064dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064dc7  mov     edi, eax
0x180064dc9  mov     rcx, rbx; bstrString
0x180064dcc  call    cs:__imp_SysFreeString
0x180064dd2  inc     r15d
0x180064dd5  lea     r8, __ImageBase
0x180064ddc  movsxd  rax, r15d
0x180064ddf  xor     ecx, ecx
0x180064de1  mov     rax, ds:rva ?c_rgszDesktopIcons@@3QBQEBGB[r8+rax*8]; ushort const * const near * const c_rgszDesktopIcons ...
0x180064de9  cmp     [rax], cx
0x180064dec  jnz     loc_180064D0E
0x180064df2  test    edi, edi
0x180064df4  js      loc_180064FFB
0x180064dfa  xor     r12d, r12d
0x180064dfd  mov     rax, cs:off_18006E940; "Arrow"
0x180064e04  mov     r15d, r12d
0x180064e07  cmp     [rax], r12w
0x180064e0b  jz      loc_180064EFA
0x180064e11  movsxd  rdx, r15d
0x180064e14  lea     rcx, [rsp+290h+pszMore]; this
0x180064e19  mov     rdx, ds:rva off_18006E940[r8+rdx*8]; unsigned __int16 *
0x180064e21  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180064e26  mov     rax, [rsi]
0x180064e29  lea     r8, [rsp+290h+pszPath]
0x180064e2e  mov     rbx, [rsp+290h+pszMore]
0x180064e33  mov     rcx, rsi
0x180064e36  mov     rdx, rbx
0x180064e39  mov     rax, [rax+130h]
0x180064e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064e45  test    eax, eax
0x180064e47  js      short loc_180064EC6
0x180064e49  lea     rcx, [rsp+290h+pszPath]; this
0x180064e4e  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180064e53  test    eax, eax
0x180064e55  jz      short loc_180064EC6
0x180064e57  mov     rcx, [rsp+290h+pszPath]; pszPath
0x180064e5c  call    cs:__imp_PathIsFileSpecW
0x180064e62  test    eax, eax
0x180064e64  jz      short loc_180064EC6
0x180064e66  mov     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x180064e6b  mov     edx, 2; int
0x180064e70  call    ?VerifyResourceFile@@YAHPEBGH@Z; VerifyResourceFile(ushort const *,int)
0x180064e75  test    eax, eax
0x180064e77  jz      short loc_180064EC6
0x180064e79  mov     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x180064e7e  mov     rcx, r14; this
0x180064e81  call    ?_MarkFileToCopy@CThemePackManager@@AEAAJPEBG@Z; CThemePackManager::_MarkFileToCopy(ushort const *)
0x180064e86  mov     edi, eax
0x180064e88  test    eax, eax
0x180064e8a  js      short loc_180064EC6
0x180064e8c  mov     r9, [rsp+290h+pszPath]; pszMore
0x180064e91  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x180064e96  mov     r8, r13; pszPathIn
0x180064e99  mov     edx, 104h; cchPathOut
0x180064e9e  call    cs:__imp_PathCchCombine
0x180064ea4  mov     edi, eax
0x180064ea6  test    eax, eax
0x180064ea8  js      short loc_180064EC6
0x180064eaa  mov     rax, [rsi]
0x180064ead  lea     r8, [rsp+290h+pszPathOut]
0x180064eb2  mov     rdx, rbx
0x180064eb5  mov     rcx, rsi
0x180064eb8  mov     rax, [rax+138h]
0x180064ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ec4  mov     edi, eax
0x180064ec6  mov     rcx, rbx; bstrString
0x180064ec9  call    cs:__imp_SysFreeString
0x180064ecf  inc     r15d
0x180064ed2  lea     r8, __ImageBase
0x180064ed9  movsxd  rax, r15d
0x180064edc  xor     ecx, ecx
0x180064ede  mov     rax, ds:rva off_18006E940[r8+rax*8]; "Arrow" ...
  ... truncated ...
```
