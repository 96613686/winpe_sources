# _ValidateLink(LINKPROP_DATA *)

- ea: `0x18046751c`
- end: `0x180467a29`
- name: `?_ValidateLink@@YAHPEAULINKPROP_DATA@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(struct LINKPROP_DATA *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180466330`

## callees

- `0x18000f6cc`
- `0x180026890`
- `0x18003d01c`
- `0x180063e10`
- `0x180078a24`
- `0x18007c180`
- `0x18009d460`
- `0x180249490`
- `0x18024a53c`
- `0x18027bf18`
- `0x18037d164`
- `0x180465304`
- `0x1804653b8`
- `0x180465478`
- `0x1804655a8`
- `0x180465934`
- `0x180465dfc`
- `0x18046751c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18046757e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18046757e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18046797e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18046797e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18046769e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18046779b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18046769e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18046779b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x18046767e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x18046767e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18046768e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18046768e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x180467801`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x180467801`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18046759a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18046759a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180467780`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180467780`
- `USER32!GetDlgItem` at `0x180467630`
- `USER32!GetDlgItem` at `0x180467630`
- `USER32!SetDlgItemTextW` at `0x1804678fe`
- `USER32!SetDlgItemTextW` at `0x18046799b`
- `USER32!SetDlgItemTextW` at `0x1804678fe`
- `USER32!SetDlgItemTextW` at `0x18046799b`
- `USER32!GetDlgItemTextW` at `0x180467967`
- `USER32!GetDlgItemTextW` at `0x180467967`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1804675c9`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1804675c9`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18046761b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180467707`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180467a18`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18046761b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180467707`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180467a18`
- `Windows.Storage!PathComposeWithArgs` at `0x180467934`
- `Windows.Storage!PathComposeWithArgs` at `0x180467934`
- `Windows.Storage!PathIsLnk` at `0x1804676c3`
- `Windows.Storage!PathIsLnk` at `0x1804676c3`
- `Windows.Storage!PathResolve` at `0x18046773f`
- `Windows.Storage!PathResolve` at `0x1804677ce`
- `Windows.Storage!PathResolve` at `0x18046773f`
- `Windows.Storage!PathResolve` at `0x1804677ce`

## string_xrefs

- `0x1804678ad`: `shell\shell32\linkprop.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _ValidateLink(HWND *a1, int a2)
{
  unsigned int v3; // r8d
  char IsEnabled; // al
  __int64 v5; // rcx
  HWND v6; // rdx
  int v7; // edx
  HWND DlgItem; // rax
  char v10; // al
  __int64 v11; // rcx
  HWND v12; // rdx
  unsigned int v13; // r8d
  int v14; // r14d
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  int v17; // eax
  char v18; // al
  __int64 v19; // rcx
  HWND v20; // rdx
  UINT fuStyle; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpString; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-C8h] BYREF
  PROPERTYKEY v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR dirs[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszStart[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR String[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v31[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  if ( *((_DWORD *)a1 + 8) )
  {
    GetDlgItemPath(a1[2], a2, pszStart);
    if ( pszStart[0]
      && !StrChrW(pszStart, 0x25u)
      && !PathIsUNCW(pszStart)
      && !(unsigned int)PathIsRemovable(pszStart)
      && !PathIsDirectoryW(pszStart) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl'::`2'::impl);
      v6 = a1[2];
      if ( IsEnabled )
        MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____2(v5, v6, 4209);
      else
        ShellMessageBoxW(g_hinst, v6, (LPCWSTR)0x1071, (LPCWSTR)0x1070, 0x30u, pszStart);
      v7 = 12290;
      goto LABEL_11;
    }
    if ( _GetPathAndArgs((struct LINKPROP_DATA *)a1, pszPath, v3, v31, 0x104u) < 0 || !pszPath[0] )
      goto LABEL_43;
    PathRemoveBlanksW(pszPath);
    PathUnquoteSpacesW(pszPath);
    if ( !PathIsRootW(pszPath) || !(unsigned int)PathIsRemovable(pszPath) )
    {
      if ( (unsigned int)PathIsLnk(pszPath) )
      {
        v10 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl'::`2'::impl);
        v12 = a1[2];
        if ( v10 )
          MessageBoxHelper::ShellMessageBoxTextScaled___7(v11, v12);
        else
          ShellMessageBoxW(g_hinst, v12, (LPCWSTR)0x107A, (LPCWSTR)0x1070, 0x30u);
LABEL_20:
        v7 = 13058;
LABEL_11:
        DlgItem = GetDlgItem(a1[2], v7);
        SetEditFocus(DlgItem);
        return 0;
      }
      dirs[0] = pszStart;
      dirs[1] = 0;
      if ( PathResolve(pszPath, dirs, 0xBu) )
        goto LABEL_27;
      if ( _GetPathAndArgs((struct LINKPROP_DATA *)a1, pszPath, v13, v31, 0x104u) < 0
        || !(unsigned int)SHExpandEnvironmentStringsW(pszPath, String, 260) )
      {
LABEL_43:
        v18 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl'::`2'::impl);
        v20 = a1[2];
        if ( v18 )
          MessageBoxHelper::ShellMessageBoxTextScaled_unsigned_short____2(v19, v20, 4210);
        else
          ShellMessageBoxW(g_hinst, v20, (LPCWSTR)0x1072, (LPCWSTR)0x1070, 0x30u, pszPath);
        goto LABEL_20;
      }
      if ( !PathIsRootW(String) || !(unsigned int)PathIsRemovable(String) )
      {
        if ( PathResolve(String, dirs, 0xBu) )
        {
LABEL_27:
          v14 = *((_DWORD *)a1 + 12);
          if ( *((_DWORD *)a1 + 11) )
            *((_DWORD *)a1 + 12) = 0;
          if ( *((_BYTE *)a1 + 1116) )
          {
            PathQuoteSpacesW(pszPath);
            v26 = 0;
            lpString = 0;
            v25 = 0;
            v15 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1[1];
            v16 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v15;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
            if ( v16(v15, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v26) < 0
              || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &v25,
                    0),
                  v24 = PKEY_Link_Arguments,
                  (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v26, &v24, &v25) < 0) )
            {
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v23,
                pszPath,
                -1);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &lpString,
                v23);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(v23);
            }
            else
            {
              v17 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &lpString,
                      L"%s %s",
                      pszPath,
                      v25);
              if ( v17 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x432,
                  (unsigned int)"shell\\shell32\\linkprop.cpp",
                  (const char *)(unsigned int)v17,
                  fuStyle);
            }
            if ( lpString )
              SetDlgItemTextW(a1[2], 13058, lpString);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v25);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpString);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
          }
          else
          {
            PathComposeWithArgs(pszPath, v31);
            memset_0(String, 0, 0x208u);
            GetDlgItemTextW(a1[2], 13058, String, 260);
            if ( lstrcmpiW(pszPath, String) )
              SetDlgItemTextW(a1[2], 13058, pszPath);
          }
          if ( *((_DWORD *)a1 + 11) )
            *((_DWORD *)a1 + 12) = v14;
          return 1;
        }
        goto LABEL_43;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18046751c  push    rbp
0x18046751e  push    rbx
0x18046751f  push    rsi
0x180467520  push    rdi
0x180467521  push    r14
0x180467523  push    r15
0x180467525  lea     rbp, [rsp-7D8h]
0x18046752d  sub     rsp, 8D8h
0x180467534  mov     rax, cs:__security_cookie
0x18046753b  xor     rax, rsp
0x18046753e  mov     [rbp+800h+var_40], rax
0x180467545  mov     rsi, rcx
0x180467548  xor     r15d, r15d
0x18046754b  cmp     [rcx+20h], r15d
0x18046754f  jz      loc_1804679B1
0x180467555  lea     r8, [rbp+800h+pszStart]; unsigned __int16 *
0x18046755c  mov     rcx, [rcx+10h]; HWND
0x180467560  call    ?GetDlgItemPath@@YAXPEAUHWND__@@HPEAG@Z; GetDlgItemPath(HWND__ *,int,ushort *)
0x180467565  cmp     [rbp+800h+pszStart], r15w
0x18046756d  jz      loc_18046764B
0x180467573  lea     edx, [r15+25h]; wMatch
0x180467577  lea     rcx, [rbp+800h+pszStart]; pszStart
0x18046757e  call    cs:__imp_StrChrW
0x180467585  nop     dword ptr [rax+rax+00h]
0x18046758a  test    rax, rax
0x18046758d  jnz     loc_18046764B
0x180467593  lea     rcx, [rbp+800h+pszStart]; pszPath
0x18046759a  call    cs:__imp_PathIsUNCW
0x1804675a1  nop     dword ptr [rax+rax+00h]
0x1804675a6  test    eax, eax
0x1804675a8  jnz     loc_18046764B
0x1804675ae  lea     rcx, [rbp+800h+pszStart]; unsigned __int16 *
0x1804675b5  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x1804675ba  test    eax, eax
0x1804675bc  jnz     loc_18046764B
0x1804675c2  lea     rcx, [rbp+800h+pszStart]; pszPath
0x1804675c9  call    cs:__imp_PathIsDirectoryW
0x1804675d0  nop     dword ptr [rax+rax+00h]
0x1804675d5  test    eax, eax
0x1804675d7  jnz     short loc_18046764B
0x1804675d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56287097@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097> `wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl(void)'::`2'::impl
0x1804675e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(void)
0x1804675e5  mov     r8d, 1071h; lpcText
0x1804675eb  mov     rdx, [rsi+10h]; hWnd
0x1804675ef  test    al, al
0x1804675f1  lea     rax, [rbp+800h+pszStart]
0x1804675f8  mov     [rsp+900h+var_8D8], rax
0x1804675fd  jz      short loc_180467606
0x1804675ff  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____2
0x180467604  jmp     short loc_180467627
0x180467606  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x18046760e  mov     r9d, 1070h; lpcTitle
0x180467614  mov     rcx, cs:g_hinst; hAppInst
0x18046761b  call    cs:__imp_ShellMessageBoxW
0x180467622  nop     dword ptr [rax+rax+00h]
0x180467627  mov     edx, 3002h; nIDDlgItem
0x18046762c  mov     rcx, [rsi+10h]; hDlg
0x180467630  call    cs:__imp_GetDlgItem
0x180467637  nop     dword ptr [rax+rax+00h]
0x18046763c  mov     rcx, rax; HWND
0x18046763f  call    ?SetEditFocus@@YAXPEAUHWND__@@@Z; SetEditFocus(HWND__ *)
0x180467644  xor     eax, eax
0x180467646  jmp     loc_1804679B6
0x18046764b  mov     ebx, 104h
0x180467650  mov     [rsp+900h+fuStyle], ebx; unsigned int
0x180467654  lea     r9, [rbp+800h+var_250]; unsigned __int16 *
0x18046765b  lea     rdx, [rbp+800h+pszPath]; unsigned __int16 *
0x18046765f  mov     rcx, rsi; struct LINKPROP_DATA *
0x180467662  call    ?_GetPathAndArgs@@YAJPEAULINKPROP_DATA@@PEAGI1I@Z; _GetPathAndArgs(LINKPROP_DATA *,ushort *,uint,ushort *,uint)
0x180467667  test    eax, eax
0x180467669  js      loc_1804679D6
0x18046766f  cmp     [rbp+800h+pszPath], r15w
0x180467674  jz      loc_1804679D6
0x18046767a  lea     rcx, [rbp+800h+pszPath]; pszPath
0x18046767e  call    cs:__imp_PathRemoveBlanksW
0x180467685  nop     dword ptr [rax+rax+00h]
0x18046768a  lea     rcx, [rbp+800h+pszPath]; lpsz
0x18046768e  call    cs:__imp_PathUnquoteSpacesW
0x180467695  nop     dword ptr [rax+rax+00h]
0x18046769a  lea     rcx, [rbp+800h+pszPath]; pszPath
0x18046769e  call    cs:__imp_PathIsRootW
0x1804676a5  nop     dword ptr [rax+rax+00h]
0x1804676aa  test    eax, eax
0x1804676ac  jz      short loc_1804676BF
0x1804676ae  lea     rcx, [rbp+800h+pszPath]; unsigned __int16 *
0x1804676b2  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x1804676b7  test    eax, eax
0x1804676b9  jnz     loc_1804679B1
0x1804676bf  lea     rcx, [rbp+800h+pszPath]
0x1804676c3  call    cs:__imp_PathIsLnk
0x1804676ca  nop     dword ptr [rax+rax+00h]
0x1804676cf  test    eax, eax
0x1804676d1  jz      short loc_18046771D
0x1804676d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56287097@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097> `wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl(void)'::`2'::impl
0x1804676da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(void)
0x1804676df  mov     rdx, [rsi+10h]; hWnd
0x1804676e3  test    al, al
0x1804676e5  jz      short loc_1804676EE
0x1804676e7  call    MessageBoxHelper__ShellMessageBoxTextScaled___7
0x1804676ec  jmp     short loc_180467713
0x1804676ee  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x1804676f6  mov     r9d, 1070h; lpcTitle
0x1804676fc  lea     r8d, [r9+0Ah]; lpcText
0x180467700  mov     rcx, cs:g_hinst; hAppInst
0x180467707  call    cs:__imp_ShellMessageBoxW
0x18046770e  nop     dword ptr [rax+rax+00h]
0x180467713  mov     edx, 3302h
0x180467718  jmp     loc_18046762C
0x18046771d  lea     rax, [rbp+800h+pszStart]
0x180467724  mov     [rsp+900h+dirs], rax
0x180467729  mov     [rsp+900h+var_888], r15
0x18046772e  mov     edi, 0Bh
0x180467733  mov     r8d, edi; fFlags
0x180467736  lea     rdx, [rsp+900h+dirs]; dirs
0x18046773b  lea     rcx, [rbp+800h+pszPath]; pszPath
0x18046773f  call    cs:__imp_PathResolve
0x180467746  nop     dword ptr [rax+rax+00h]
0x18046774b  test    eax, eax
0x18046774d  jnz     loc_1804677E2
0x180467753  mov     [rsp+900h+fuStyle], ebx; int
0x180467757  lea     r9, [rbp+800h+var_250]; unsigned __int16 *
0x18046775e  lea     rdx, [rbp+800h+pszPath]; unsigned __int16 *
0x180467762  mov     rcx, rsi; struct LINKPROP_DATA *
0x180467765  call    ?_GetPathAndArgs@@YAJPEAULINKPROP_DATA@@PEAGI1I@Z; _GetPathAndArgs(LINKPROP_DATA *,ushort *,uint,ushort *,uint)
0x18046776a  test    eax, eax
0x18046776c  js      loc_1804679D6
0x180467772  mov     r8d, ebx
0x180467775  lea     rdx, [rbp+800h+String]
0x18046777c  lea     rcx, [rbp+800h+pszPath]
0x180467780  call    cs:__imp_SHExpandEnvironmentStringsW
0x180467787  nop     dword ptr [rax+rax+00h]
0x18046778c  test    eax, eax
0x18046778e  jz      loc_1804679D6
0x180467794  lea     rcx, [rbp+800h+String]; pszPath
0x18046779b  call    cs:__imp_PathIsRootW
0x1804677a2  nop     dword ptr [rax+rax+00h]
0x1804677a7  test    eax, eax
0x1804677a9  jz      short loc_1804677BF
0x1804677ab  lea     rcx, [rbp+800h+String]; unsigned __int16 *
0x1804677b2  call    ?PathIsRemovable@@YAHPEBG@Z; PathIsRemovable(ushort const *)
0x1804677b7  test    eax, eax
0x1804677b9  jnz     loc_1804679B1
0x1804677bf  mov     r8d, edi; fFlags
0x1804677c2  lea     rdx, [rsp+900h+dirs]; dirs
0x1804677c7  lea     rcx, [rbp+800h+String]; pszPath
0x1804677ce  call    cs:__imp_PathResolve
0x1804677d5  nop     dword ptr [rax+rax+00h]
0x1804677da  test    eax, eax
0x1804677dc  jz      loc_1804679D6
0x1804677e2  mov     r14d, [rsi+30h]
0x1804677e6  cmp     [rsi+2Ch], r15d
0x1804677ea  jz      short loc_1804677F0
0x1804677ec  mov     [rsi+30h], r15d
0x1804677f0  lea     rcx, [rbp+800h+pszPath]; lpsz
0x1804677f4  cmp     [rsi+45Ch], r15b
0x1804677fb  jz      loc_18046792D
0x180467801  call    cs:__imp_PathQuoteSpacesW
0x180467808  nop     dword ptr [rax+rax+00h]
0x18046780d  mov     [rsp+900h+var_898], r15
0x180467812  mov     [rsp+900h+lpString], r15
0x180467817  mov     [rsp+900h+var_8A0], r15
0x18046781c  mov     rdi, [rsi+8]
0x180467820  mov     rax, [rdi]
0x180467823  mov     rbx, [rax]
0x180467826  lea     rcx, [rsp+900h+var_898]
0x18046782b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180467830  lea     r8, [rsp+900h+var_898]
0x180467835  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18046783c  mov     rcx, rdi
0x18046783f  mov     rax, rbx
0x180467842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180467847  test    eax, eax
0x180467849  js      short loc_1804678C0
0x18046784b  xor     edx, edx
0x18046784d  lea     rcx, [rsp+900h+var_8A0]
0x180467852  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180467857  movups  xmm0, xmmword ptr cs:PKEY_Link_Arguments.fmtid.Data1
0x18046785e  movaps  [rsp+900h+var_8C0], xmm0
0x180467863  mov     eax, cs:PKEY_Link_Arguments.pid
0x180467869  mov     [rsp+900h+var_8B0], eax
0x18046786d  lea     r8, [rsp+900h+var_8A0]
0x180467872  lea     rdx, [rsp+900h+var_8C0]
0x180467877  lea     rcx, [rsp+900h+var_898]
0x18046787c  call    ??$GetAsString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180467881  test    eax, eax
0x180467883  js      short loc_1804678C0
0x180467885  mov     r9, [rsp+900h+var_8A0]
0x18046788a  lea     r8, [rbp+800h+pszPath]
0x18046788e  lea     rdx, aSS_7; "%s %s"
0x180467895  lea     rcx, [rsp+900h+lpString]
0x18046789a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18046789f  mov     rcx, [rbp+808h]; this
0x1804678a6  test    eax, eax
0x1804678a8  jns     short loc_1804678EB
0x1804678aa  mov     r9d, eax; char *
0x1804678ad  lea     r8, aShellShell32Li_0; "shell\\shell32\\linkprop.cpp"
0x1804678b4  mov     edx, 432h; void *
0x1804678b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1804678be  jmp     short loc_1804678EB
0x1804678c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1804678c4  lea     rdx, [rbp+800h+pszPath]
0x1804678c8  lea     rcx, [rsp+900h+var_8C8]
0x1804678cd  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1804678d2  lea     rdx, [rsp+900h+var_8C8]
0x1804678d7  lea     rcx, [rsp+900h+lpString]
0x1804678dc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1804678e1  lea     rcx, [rsp+900h+var_8C8]; void *
0x1804678e6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1804678eb  mov     r8, [rsp+900h+lpString]; lpString
0x1804678f0  test    r8, r8
0x1804678f3  jz      short loc_18046790B
0x1804678f5  mov     edx, 3302h; nIDDlgItem
0x1804678fa  mov     rcx, [rsi+10h]; hDlg
0x1804678fe  call    cs:__imp_SetDlgItemTextW
0x180467905  nop     dword ptr [rax+rax+00h]
0x18046790a  nop
0x18046790b  lea     rcx, [rsp+900h+var_8A0]; void *
0x180467910  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180467915  nop
0x180467916  lea     rcx, [rsp+900h+lpString]; void *
0x18046791b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180467920  nop
0x180467921  lea     rcx, [rsp+900h+var_898]
0x180467926  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18046792b  jmp     short loc_1804679A7
0x18046792d  lea     rdx, [rbp+800h+var_250]
0x180467934  call    cs:__imp_PathComposeWithArgs
0x18046793b  nop     dword ptr [rax+rax+00h]
0x180467940  xor     edx, edx; Val
0x180467942  mov     r8d, 208h; Size
0x180467948  lea     rcx, [rbp+800h+String]; void *
0x18046794f  call    memset_0
0x180467954  mov     r9d, ebx; cchMax
0x180467957  lea     r8, [rbp+800h+String]; lpString
0x18046795e  mov     edx, 3302h; nIDDlgItem
0x180467963  mov     rcx, [rsi+10h]; hDlg
0x180467967  call    cs:__imp_GetDlgItemTextW
0x18046796e  nop     dword ptr [rax+rax+00h]
0x180467973  lea     rdx, [rbp+800h+String]; lpString2
0x18046797a  lea     rcx, [rbp+800h+pszPath]; lpString1
0x18046797e  call    cs:__imp_lstrcmpiW
0x180467985  nop     dword ptr [rax+rax+00h]
0x18046798a  test    eax, eax
0x18046798c  jz      short loc_1804679A7
0x18046798e  lea     r8, [rbp+800h+pszPath]; lpString
0x180467992  mov     edx, 3302h; nIDDlgItem
0x180467997  mov     rcx, [rsi+10h]; hDlg
0x18046799b  call    cs:__imp_SetDlgItemTextW
0x1804679a2  nop     dword ptr [rax+rax+00h]
0x1804679a7  cmp     [rsi+2Ch], r15d
0x1804679ab  jz      short loc_1804679B1
0x1804679ad  mov     [rsi+30h], r14d
0x1804679b1  mov     eax, 1
0x1804679b6  mov     rcx, [rbp+800h+var_40]
0x1804679bd  xor     rcx, rsp; StackCookie
0x1804679c0  call    __security_check_cookie
0x1804679c5  add     rsp, 8D8h
0x1804679cc  pop     r15
0x1804679ce  pop     r14
0x1804679d0  pop     rdi
0x1804679d1  pop     rsi
0x1804679d2  pop     rbx
0x1804679d3  pop     rbp
0x1804679d4  retn
0x1804679d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56287097@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097> `wil::Feature<__WilFeatureTraits_Feature_ID56287097>::GetImpl(void)'::`2'::impl
0x1804679dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56287097@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56287097>::__private_IsEnabled(void)
0x1804679e2  mov     r8d, 1072h; lpcText
0x1804679e8  mov     rdx, [rsi+10h]; hWnd
0x1804679ec  test    al, al
0x1804679ee  lea     rax, [rbp+800h+pszPath]
0x1804679f2  mov     [rsp+900h+var_8D8], rax
0x1804679f7  jz      short loc_180467A03
0x1804679f9  call    MessageBoxHelper__ShellMessageBoxTextScaled_unsigned_short____2
0x1804679fe  jmp     loc_180467713
0x180467a03  mov     [rsp+900h+fuStyle], 30h ; '0'; fuStyle
0x180467a0b  mov     r9d, 1070h; lpcTitle
0x180467a11  mov     rcx, cs:g_hinst; hAppInst
0x180467a18  call    cs:__imp_ShellMessageBoxW
0x180467a1f  nop     dword ptr [rax+rax+00h]
0x180467a24  jmp     loc_180467713
```
