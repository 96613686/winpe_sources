# CThemeManager2::_ApplyDesktopIcons(void)

- ea: `0x18001b43c`
- end: `0x18001b9f1`
- name: `?_ApplyDesktopIcons@CThemeManager2@@AEAAJXZ`
- size: `1461`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004f044`

## callees

- `0x180008dd8`
- `0x18000ab00`
- `0x18000ab10`
- `0x18000ed70`
- `0x18001987c`
- `0x18001b43c`
- `0x18001b9f8`
- `0x1800358c0`
- `0x18003633c`
- `0x18003e920`
- `0x180042900`
- `0x180046658`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHQueryRecycleBinW` at `0x18001b7fa`
- `SHELL32!SHQueryRecycleBinW` at `0x18001b7fa`
- `SHLWAPI!StrChrW` at `0x18001b597`
- `SHLWAPI!StrChrW` at `0x18001b597`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001b510`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001b510`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b600`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b680`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b73f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b843`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b871`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b89f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b920`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b600`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b680`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b73f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b843`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b871`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b89f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b920`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b646`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b705`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b8e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b646`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b705`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b8e6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b5a8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b5a8`
- `USER32!GetShellWindow` at `0x18001b9af`
- `USER32!GetShellWindow` at `0x18001b9af`
- `USER32!PostMessageW` at `0x18001b9c6`
- `USER32!PostMessageW` at `0x18001b9c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b98a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b98a`

## string_xrefs

- `0x18001b835`: `Software\Microsoft\Windows\CurrentVersion\Explorer\CLSID\{645FF040-5081-101B-9F08-00AA002F954E}\DefaultIcon`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThemeManager2::_ApplyDesktopIcons(CThemeManager2 *this)
{
  int Error; // ebx
  int v3; // r14d
  char v4; // r15
  int v5; // r12d
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64, LPCWCH *); // rbx
  _QWORD *v8; // rax
  const WCHAR *v9; // rax
  const WCHAR *v10; // rdi
  const unsigned __int16 *v11; // rax
  int v12; // eax
  LSTATUS ValueW; // eax
  _QWORD *v14; // rcx
  int v15; // edx
  LSTATUS v16; // eax
  int v17; // edi
  char v18; // cl
  LSTATUS v19; // eax
  HWND ShellWindow; // rax
  LPCWCH lpString2; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  _SHQUERYRBINFO pSHQueryRBInfo; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszStart[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String1[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pvData[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR v29[264]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v30[528]; // [rsp+8B0h] [rbp+7B0h] BYREF

  Error = 0;
  if ( *((_BYTE *)this + 2145) || CThemeManager2::_CanThemeChangeDesktopIcons(this) )
  {
    v3 = 0;
    v4 = 0;
    v5 = 0;
    if ( *(_WORD *)c_rgszDesktopIcons )
    {
      while ( 1 )
      {
        lpString2 = 0;
        v6 = *((_QWORD *)this + 266);
        v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPCWCH *))(*(_QWORD *)v6 + 360LL);
        v8 = (_QWORD *)ATL::CComBSTR::CComBSTR(
                         (ATL::CComBSTR *)&bstrString,
                         (const unsigned __int16 *)(&c_rgszDesktopIcons)[v5]);
        Error = v7(v6, *v8, 1, &lpString2);
        SysFreeString(bstrString);
        if ( Error >= 0 )
        {
          if ( (unsigned int)SHExpandEnvironmentStringsW(lpString2, v30, 260) )
          {
            memset_0(String1, 0, 0x208u);
            Error = StringCchCopyW(pszStart, 0x104u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer");
            if ( Error >= 0 )
            {
              Error = StringCchCatW(pszStart, 0x104u, L"\\");
              if ( Error >= 0 )
              {
                Error = StringCchCatW(pszStart, 0x104u, (const unsigned __int16 *)(&c_rgszDesktopIcons)[v5]);
                if ( Error >= 0 )
                {
                  v9 = StrChrW(pszStart, 0x3Au);
                  v10 = v9;
                  if ( !v9 || (v11 = CharNextW(v9), Error = StringCchCopyW(String1, 0x104u, v11), *v10 = 0, Error >= 0) )
                  {
                    if ( ATL::CComBSTR::Length((ATL::CComBSTR *)&lpString2) )
                    {
                      v12 = CompareStringOrdinal(String1, -1, L"DefaultValue", -1, 1);
                      pcbData = 520;
                      if ( v12 == 2 )
                      {
                        ValueW = RegGetValueW(HKEY_CURRENT_USER, pszStart, 0, 2u, 0, pvData, &pcbData);
                        Error = ValueW;
                        if ( ValueW )
                        {
                          pvData[0] = 0;
                          if ( ValueW > 0 )
                            Error = (unsigned __int16)ValueW | 0x80070000;
                        }
                        if ( Error < 0 || CompareStringOrdinal(pvData, -1, lpString2, -1, 1) != 2 )
                        {
                          Error = SHRegSetString(HKEY_CURRENT_USER, pszStart, 0, lpString2);
                          if ( Error >= 0 )
                            v4 = 1;
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                          {
                            v15 = 73;
                            goto LABEL_23;
                          }
                        }
                      }
                      else
                      {
                        v16 = RegGetValueW(HKEY_CURRENT_USER, pszStart, String1, 2u, 0, pvData, &pcbData);
                        Error = v16;
                        if ( v16 )
                        {
                          pvData[0] = 0;
                          if ( v16 > 0 )
                            Error = (unsigned __int16)v16 | 0x80070000;
                        }
                        if ( Error >= 0 && CompareStringOrdinal(pvData, -1, lpString2, -1, 1) == 2 )
                          goto LABEL_53;
                        v17 = SHRegSetString(HKEY_CURRENT_USER, pszStart, String1, lpString2);
                        Error = v17;
                        v18 = v4;
                        if ( v17 >= 0 )
                          v18 = 1;
                        v4 = v18;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        {
                          WPP_SF_SSS(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            74,
                            (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                            (unsigned int)pszStart,
                            (__int64)String1,
                            (__int64)lpString2);
                        }
                        if ( v17 < 0 )
                          goto LABEL_53;
                        if ( !v3 )
                        {
                          *(_QWORD *)&pSHQueryRBInfo.cbSize = 24;
                          *(_OWORD *)&pSHQueryRBInfo.i64Size = 0;
                          Error = SHQueryRecycleBinW(0, &pSHQueryRBInfo);
                          if ( Error < 0 )
                            goto LABEL_53;
                          v3 = (pSHQueryRBInfo.i64NumItems <= 0) + 1;
                        }
                        if ( CompareStringOrdinal(
                               pszStart,
                               -1,
                               L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CLSID\\{645FF040-5081-101B-9F08-0"
                                "0AA002F954E}\\DefaultIcon",
                               -1,
                               1) == 2
                          && (v3 == 2 && CompareStringOrdinal(String1, -1, L"empty", -1, 1) == 2
                           || v3 == 1 && CompareStringOrdinal(String1, -1, L"full", -1, 1) == 2) )
                        {
                          pcbData = 520;
                          v19 = RegGetValueW(HKEY_CURRENT_USER, pszStart, 0, 2u, 0, v29, &pcbData);
                          Error = v19;
                          if ( v19 )
                          {
                            v29[0] = 0;
                            if ( v19 > 0 )
                              Error = (unsigned __int16)v19 | 0x80070000;
                          }
                          if ( Error < 0 || CompareStringOrdinal(v29, -1, lpString2, -1, 1) != 2 )
                          {
                            Error = SHRegSetString(HKEY_CURRENT_USER, pszStart, 0, lpString2);
                            if ( Error >= 0 )
                              v4 = 1;
                            v14 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                            {
                              v15 = 75;
LABEL_23:
                              WPP_SF_SS(
                                v14[2],
                                v15,
                                (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                                (unsigned int)pszStart,
                                (__int64)lpString2);
                            }
                          }
                        }
                      }
LABEL_53:
                      if ( Error )
                        Error = ResultFromLastError();
                    }
                  }
                }
              }
            }
          }
          else
          {
            Error = -2147467259;
          }
        }
        SysFreeString((BSTR)lpString2);
        if ( !*(_WORD *)(&c_rgszDesktopIcons)[++v5] )
        {
          if ( v4 )
          {
            ShellWindow = GetShellWindow();
            PostMessageW(ShellWindow, 0x111u, 0xA220u, 0);
          }
          return (unsigned int)Error;
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001b43c  push    rbp
0x18001b43e  push    rbx
0x18001b43f  push    rsi
0x18001b440  push    rdi
0x18001b441  push    r12
0x18001b443  push    r13
0x18001b445  push    r14
0x18001b447  push    r15
0x18001b449  lea     rbp, [rsp-9D8h]
0x18001b451  sub     rsp, 0AD8h
0x18001b458  mov     rax, cs:__security_cookie
0x18001b45f  xor     rax, rsp
0x18001b462  mov     [rbp+0A10h+var_50], rax
0x18001b469  mov     r13, rcx
0x18001b46c  xor     esi, esi
0x18001b46e  mov     ebx, esi
0x18001b470  cmp     [rcx+861h], sil
0x18001b477  jnz     short loc_18001B486
0x18001b479  call    ?_CanThemeChangeDesktopIcons@CThemeManager2@@AEAA_NXZ; CThemeManager2::_CanThemeChangeDesktopIcons(void)
0x18001b47e  test    al, al
0x18001b480  jz      loc_18001B9CC
0x18001b486  mov     r14d, esi
0x18001b489  mov     r15b, sil
0x18001b48c  mov     r12d, esi
0x18001b48f  mov     rax, cs:?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x18001b496  cmp     [rax], si
0x18001b499  jz      loc_18001B9CC
0x18001b49f  lea     rcx, ?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x18001b4a6  mov     [rsp+0B10h+lpString2], rsi
0x18001b4ab  mov     rdi, [r13+850h]
0x18001b4b2  mov     rax, [rdi]
0x18001b4b5  mov     rbx, [rax+168h]
0x18001b4bc  movsxd  rsi, r12d
0x18001b4bf  mov     rdx, [rcx+rsi*8]; unsigned __int16 *
0x18001b4c3  lea     rcx, [rsp+0B10h+bstrString]; this
0x18001b4c8  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001b4cd  nop
0x18001b4ce  lea     r9, [rsp+0B10h+lpString2]
0x18001b4d3  mov     r8d, 1
0x18001b4d9  mov     rdx, [rax]
0x18001b4dc  mov     rcx, rdi
0x18001b4df  mov     rax, rbx
0x18001b4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4e7  mov     ebx, eax
0x18001b4e9  mov     rcx, [rsp+0B10h+bstrString]; bstrString
0x18001b4ee  call    cs:__imp_SysFreeString
0x18001b4f4  test    ebx, ebx
0x18001b4f6  js      loc_18001B983
0x18001b4fc  mov     edi, 104h
0x18001b501  mov     r8d, edi
0x18001b504  lea     rdx, [rbp+0A10h+var_260]
0x18001b50b  mov     rcx, [rsp+0B10h+lpString2]
0x18001b510  call    cs:__imp_SHExpandEnvironmentStringsW
0x18001b516  test    eax, eax
0x18001b518  jz      loc_18001B97E
0x18001b51e  xor     edx, edx; Val
0x18001b520  mov     r8d, 208h; Size
0x18001b526  lea     rcx, [rbp+0A10h+String1]; void *
0x18001b52d  call    memset_0
0x18001b532  lea     r8, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001b539  mov     edx, edi; unsigned __int64
0x18001b53b  lea     rcx, [rsp+0B10h+pszStart]; unsigned __int16 *
0x18001b540  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b545  mov     ebx, eax
0x18001b547  test    eax, eax
0x18001b549  js      loc_18001B983
0x18001b54f  lea     r8, Control; "\\"
0x18001b556  mov     edx, edi; unsigned __int64
0x18001b558  lea     rcx, [rsp+0B10h+pszStart]; unsigned __int16 *
0x18001b55d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b562  mov     ebx, eax
0x18001b564  test    eax, eax
0x18001b566  js      loc_18001B983
0x18001b56c  lea     r8, ?c_rgszDesktopIcons@@3QBQEBGB; ushort const * const near * const c_rgszDesktopIcons
0x18001b573  mov     r8, [r8+rsi*8]; unsigned __int16 *
0x18001b577  mov     edx, edi; unsigned __int64
0x18001b579  lea     rcx, [rsp+0B10h+pszStart]; unsigned __int16 *
0x18001b57e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b583  mov     ebx, eax
0x18001b585  xor     esi, esi
0x18001b587  test    eax, eax
0x18001b589  js      loc_18001B985
0x18001b58f  lea     edx, [rsi+3Ah]; wMatch
0x18001b592  lea     rcx, [rsp+0B10h+pszStart]; pszStart
0x18001b597  call    cs:__imp_StrChrW
0x18001b59d  mov     rdi, rax
0x18001b5a0  test    rax, rax
0x18001b5a3  jz      short loc_18001B5CF
0x18001b5a5  mov     rcx, rax; lpsz
0x18001b5a8  call    cs:__imp_CharNextW
0x18001b5ae  mov     r8, rax; unsigned __int16 *
0x18001b5b1  mov     edx, 104h; unsigned __int64
0x18001b5b6  lea     rcx, [rbp+0A10h+String1]; unsigned __int16 *
0x18001b5bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b5c2  mov     ebx, eax
0x18001b5c4  mov     [rdi], si
0x18001b5c7  test    eax, eax
0x18001b5c9  js      loc_18001B985
0x18001b5cf  lea     rcx, [rsp+0B10h+lpString2]; this
0x18001b5d4  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18001b5d9  test    eax, eax
0x18001b5db  jz      loc_18001B985
0x18001b5e1  mov     edi, 1
0x18001b5e6  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b5ea  or      eax, 0FFFFFFFFh
0x18001b5ed  mov     r9d, eax; cchCount2
0x18001b5f0  lea     r8, aDefaultvalue; "DefaultValue"
0x18001b5f7  mov     edx, eax; cchCount1
0x18001b5f9  lea     rcx, [rbp+0A10h+String1]; lpString1
0x18001b600  call    cs:__imp_CompareStringOrdinal
0x18001b606  lea     ecx, [rdi+1]
0x18001b609  mov     [rsp+0B10h+var_AC8], 208h
0x18001b611  mov     r9d, ecx; dwFlags
0x18001b614  lea     rdx, [rsp+0B10h+pszStart]; lpSubKey
0x18001b619  cmp     eax, ecx
0x18001b61b  lea     rax, [rsp+0B10h+var_AC8]
0x18001b620  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001b627  mov     [rsp+0B10h+pcbData], rax; pcbData
0x18001b62c  lea     rax, [rbp+0A10h+var_680]
0x18001b633  mov     [rsp+0B10h+pvData], rax; pvData
0x18001b638  mov     qword ptr [rsp+0B10h+bIgnoreCase], rsi; pdwType
0x18001b63d  jnz     loc_18001B6FE
0x18001b643  xor     r8d, r8d; lpValue
0x18001b646  call    cs:__imp_RegGetValueW
0x18001b64c  mov     ebx, eax
0x18001b64e  test    eax, eax
0x18001b650  jz      short loc_18001B664
0x18001b652  mov     [rbp+0A10h+var_680], si
0x18001b659  jle     short loc_18001B664
0x18001b65b  movzx   ebx, ax
0x18001b65e  or      ebx, 80070000h
0x18001b664  test    ebx, ebx
0x18001b666  js      short loc_18001B68F
0x18001b668  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b66c  or      eax, 0FFFFFFFFh
0x18001b66f  mov     r9d, eax; cchCount2
0x18001b672  mov     r8, [rsp+0B10h+lpString2]; lpString2
0x18001b677  mov     edx, eax; cchCount1
0x18001b679  lea     rcx, [rbp+0A10h+var_680]; lpString1
0x18001b680  call    cs:__imp_CompareStringOrdinal
0x18001b686  cmp     eax, 2
0x18001b689  jz      loc_18001B971
0x18001b68f  mov     r9, [rsp+0B10h+lpString2]; unsigned __int16 *
0x18001b694  xor     r8d, r8d; unsigned __int16 *
0x18001b697  lea     rdx, [rsp+0B10h+pszStart]; unsigned __int16 *
0x18001b69c  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001b6a3  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001b6a8  mov     ebx, eax
0x18001b6aa  movzx   r15d, r15b
0x18001b6ae  test    eax, eax
0x18001b6b0  cmovns  r15d, edi
0x18001b6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6bb  lea     rax, WPP_GLOBAL_Control
0x18001b6c2  cmp     rcx, rax
0x18001b6c5  jz      loc_18001B971
0x18001b6cb  test    byte ptr [rcx+1Ch], 8
0x18001b6cf  jz      loc_18001B971
0x18001b6d5  mov     edx, 49h ; 'I'
0x18001b6da  mov     rax, [rsp+0B10h+lpString2]
0x18001b6df  mov     qword ptr [rsp+0B10h+bIgnoreCase], rax
0x18001b6e4  lea     r9, [rsp+0B10h+pszStart]
0x18001b6e9  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18001b6f0  mov     rcx, [rcx+10h]
0x18001b6f4  call    WPP_SF_SS
0x18001b6f9  jmp     loc_18001B971
0x18001b6fe  lea     r8, [rbp+0A10h+String1]; lpValue
0x18001b705  call    cs:__imp_RegGetValueW
0x18001b70b  mov     ebx, eax
0x18001b70d  test    eax, eax
0x18001b70f  jz      short loc_18001B723
0x18001b711  mov     [rbp+0A10h+var_680], si
0x18001b718  jle     short loc_18001B723
0x18001b71a  movzx   ebx, ax
0x18001b71d  or      ebx, 80070000h
0x18001b723  test    ebx, ebx
0x18001b725  js      short loc_18001B74E
0x18001b727  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b72b  or      eax, 0FFFFFFFFh
0x18001b72e  mov     r9d, eax; cchCount2
0x18001b731  mov     r8, [rsp+0B10h+lpString2]; lpString2
0x18001b736  mov     edx, eax; cchCount1
0x18001b738  lea     rcx, [rbp+0A10h+var_680]; lpString1
0x18001b73f  call    cs:__imp_CompareStringOrdinal
0x18001b745  cmp     eax, 2
0x18001b748  jz      loc_18001B971
0x18001b74e  mov     r9, [rsp+0B10h+lpString2]; unsigned __int16 *
0x18001b753  lea     r8, [rbp+0A10h+String1]; unsigned __int16 *
0x18001b75a  lea     rdx, [rsp+0B10h+pszStart]; unsigned __int16 *
0x18001b75f  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001b766  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001b76b  mov     edi, eax
0x18001b76d  mov     ebx, eax
0x18001b76f  movzx   ecx, r15b
0x18001b773  test    eax, eax
0x18001b775  mov     eax, 1
0x18001b77a  cmovns  ecx, eax
0x18001b77d  movzx   r15d, cl
0x18001b781  mov     esi, ebx
0x18001b783  shr     esi, 1Fh
0x18001b786  xor     sil, al
0x18001b789  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b790  lea     rax, WPP_GLOBAL_Control
0x18001b797  cmp     rcx, rax
0x18001b79a  jz      short loc_18001B7D2
0x18001b79c  test    byte ptr [rcx+1Ch], 8
0x18001b7a0  jz      short loc_18001B7D2
0x18001b7a2  mov     edx, 4Ah ; 'J'
0x18001b7a7  mov     rax, [rsp+0B10h+lpString2]
0x18001b7ac  mov     [rsp+0B10h+pvData], rax
0x18001b7b1  lea     rax, [rbp+0A10h+String1]
0x18001b7b8  mov     qword ptr [rsp+0B10h+bIgnoreCase], rax
0x18001b7bd  lea     r9, [rsp+0B10h+pszStart]
0x18001b7c2  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18001b7c9  mov     rcx, [rcx+10h]
0x18001b7cd  call    WPP_SF_SSS
0x18001b7d2  test    sil, sil
0x18001b7d5  jz      loc_18001B96F
0x18001b7db  xor     esi, esi
0x18001b7dd  test    r14d, r14d
0x18001b7e0  jnz     short loc_18001B81E
0x18001b7e2  mov     qword ptr [rsp+0B10h+pSHQueryRBInfo.cbSize], 18h
0x18001b7eb  xorps   xmm0, xmm0
0x18001b7ee  movups  xmmword ptr [rsp+0B10h+pSHQueryRBInfo.i64Size], xmm0
0x18001b7f3  lea     rdx, [rsp+0B10h+pSHQueryRBInfo]; pSHQueryRBInfo
0x18001b7f8  xor     ecx, ecx; pszRootPath
0x18001b7fa  call    cs:__imp_SHQueryRecycleBinW
0x18001b800  mov     ebx, eax
0x18001b802  test    eax, eax
0x18001b804  js      loc_18001B971
0x18001b80a  mov     r14d, esi
0x18001b80d  cmp     [rsp+0B10h+pSHQueryRBInfo.i64NumItems], rsi
0x18001b812  setle   r14b
0x18001b816  lea     edi, [rsi+1]
0x18001b819  add     r14d, edi
0x18001b81c  jmp     short loc_18001B82B
0x18001b81e  test    edi, edi
0x18001b820  js      loc_18001B971
0x18001b826  mov     edi, 1
0x18001b82b  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b82f  or      eax, 0FFFFFFFFh
0x18001b832  mov     r9d, eax; cchCount2
0x18001b835  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001b83c  mov     edx, eax; cchCount1
0x18001b83e  lea     rcx, [rsp+0B10h+pszStart]; lpString1
0x18001b843  call    cs:__imp_CompareStringOrdinal
0x18001b849  cmp     eax, 2
0x18001b84c  jnz     loc_18001B971
0x18001b852  cmp     r14d, eax
0x18001b855  jnz     short loc_18001B87C
0x18001b857  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b85b  or      eax, 0FFFFFFFFh
0x18001b85e  mov     r9d, eax; cchCount2
0x18001b861  lea     r8, aEmpty; "empty"
0x18001b868  mov     edx, eax; cchCount1
0x18001b86a  lea     rcx, [rbp+0A10h+String1]; lpString1
0x18001b871  call    cs:__imp_CompareStringOrdinal
0x18001b877  cmp     eax, 2
0x18001b87a  jz      short loc_18001B8AE
0x18001b87c  cmp     r14d, edi
0x18001b87f  jnz     loc_18001B971
0x18001b885  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b889  or      eax, 0FFFFFFFFh
0x18001b88c  mov     r9d, eax; cchCount2
0x18001b88f  lea     r8, aFull; "full"
0x18001b896  mov     edx, eax; cchCount1
0x18001b898  lea     rcx, [rbp+0A10h+String1]; lpString1
0x18001b89f  call    cs:__imp_CompareStringOrdinal
0x18001b8a5  cmp     eax, 2
0x18001b8a8  jnz     loc_18001B971
0x18001b8ae  mov     [rsp+0B10h+var_AC8], 208h
0x18001b8b6  lea     rax, [rsp+0B10h+var_AC8]
0x18001b8bb  mov     [rsp+0B10h+pcbData], rax; pcbData
0x18001b8c0  lea     rax, [rbp+0A10h+var_470]
0x18001b8c7  mov     [rsp+0B10h+pvData], rax; pvData
0x18001b8cc  mov     qword ptr [rsp+0B10h+bIgnoreCase], rsi; pdwType
0x18001b8d1  mov     r9d, 2; dwFlags
0x18001b8d7  xor     r8d, r8d; lpValue
0x18001b8da  lea     rdx, [rsp+0B10h+pszStart]; lpSubKey
0x18001b8df  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001b8e6  call    cs:__imp_RegGetValueW
0x18001b8ec  mov     ebx, eax
0x18001b8ee  test    eax, eax
0x18001b8f0  jz      short loc_18001B904
0x18001b8f2  mov     [rbp+0A10h+var_470], si
0x18001b8f9  jle     short loc_18001B904
0x18001b8fb  movzx   ebx, ax
0x18001b8fe  or      ebx, 80070000h
0x18001b904  test    ebx, ebx
0x18001b906  js      short loc_18001B92B
0x18001b908  mov     [rsp+0B10h+bIgnoreCase], edi; bIgnoreCase
0x18001b90c  or      eax, 0FFFFFFFFh
0x18001b90f  mov     r9d, eax; cchCount2
0x18001b912  mov     r8, [rsp+0B10h+lpString2]; lpString2
0x18001b917  mov     edx, eax; cchCount1
0x18001b919  lea     rcx, [rbp+0A10h+var_470]; lpString1
0x18001b920  call    cs:__imp_CompareStringOrdinal
0x18001b926  cmp     eax, 2
0x18001b929  jz      short loc_18001B971
0x18001b92b  mov     r9, [rsp+0B10h+lpString2]; unsigned __int16 *
0x18001b930  xor     r8d, r8d; unsigned __int16 *
  ... truncated ...
```
