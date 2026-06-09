# CThemeManager2::_ApplyDesktopBackgroundLegacy(bool)

- ea: `0x18004e3a4`
- end: `0x18004eb16`
- name: `?_ApplyDesktopBackgroundLegacy@CThemeManager2@@AEAAJ_N@Z`
- size: `1906`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, bool)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004d9f0`

## callees

- `0x180005410`
- `0x180008dd8`
- `0x18000ab10`
- `0x18000c598`
- `0x18001ed40`
- `0x180020154`
- `0x1800208d4`
- `0x18003336c`
- `0x18003380c`
- `0x1800358c0`
- `0x18003633c`
- `0x18003cf08`
- `0x180042664`
- `0x1800427dc`
- `0x1800491a0`
- `0x18004b2a4`
- `0x18004b7e8`
- `0x18004ca20`
- `0x18004e3a4`
- `0x180050414`
- `0x1800516ac`
- `0x1800618d0`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18004ea2c`
- `SHELL32!SHCreateItemFromParsingName` at `0x18004ea2c`
- `SHELL32!SHGetIDListFromObject` at `0x18004ea5d`
- `SHELL32!SHGetIDListFromObject` at `0x18004ea5d`
- `SHELL32!__imp_ILClone` at `0x18004e93c`
- `SHELL32!__imp_ILClone` at `0x18004e93c`
- `SHELL32!__imp_ILFree` at `0x18004e955`
- `SHELL32!__imp_ILFree` at `0x18004ea76`
- `SHELL32!__imp_ILFree` at `0x18004e955`
- `SHELL32!__imp_ILFree` at `0x18004ea76`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004e8e2`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004e8e2`
- `SHLWAPI!PathIsPrefixW` at `0x18004ea07`
- `SHLWAPI!PathIsPrefixW` at `0x18004ea07`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004e9ee`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004e9ee`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e761`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004e761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e64d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e64d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e79c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e79c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e849`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e85a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004eadf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004eaeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e849`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e85a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004eadf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004eaeb`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e446`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e4dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e63c`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e8bd`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e446`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e4dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e63c`
- `OLEAUT32!__imp_SysStringLen` at `0x18004e8bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThemeManager2::_ApplyDesktopBackgroundLegacy(struct ITheme **this, char a2)
{
  const wchar_t *v4; // r9
  char v5; // r12
  struct ISlideshowSettings *SlideshowSettings; // rax
  __int64 v7; // rdx
  char v8; // r15
  struct ITheme *v9; // rdi
  __int64 (__fastcall *v10)(struct ITheme *, GUID *, LPVOID *); // rbx
  int v11; // eax
  const unsigned __int16 *DesktopSpotlightThemeFallbackImage; // rdx
  int v13; // ebx
  struct ISlideshowSettings *v14; // rdi
  HRESULT v15; // ebx
  void (__fastcall *v16)(LPVOID, _QWORD, _QWORD); // r12
  unsigned int v17; // r14d
  _QWORD *v18; // rax
  int v19; // ebx
  HRESULT v20; // eax
  int v21; // edx
  int v22; // r8d
  struct CFileSource *SlideshowFileSource; // rax
  CFileSource *v24; // rdi
  struct _ITEMIDLIST_ABSOLUTE *v25; // rax
  CThemeManager2 *v26; // rcx
  ITEMIDLIST *v27; // rsi
  int v28; // eax
  CThemeManager2 *v29; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  BSTR v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  struct IShellItem *v38; // [rsp+60h] [rbp-A0h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  struct ISlideshowSettings *v41; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPrefix[264]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  LODWORD(v38) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v4 = L"on";
    if ( !a2 )
      v4 = L"off";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v4);
  }
  pbstr = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, BSTR *))(*(_QWORD *)this[265] + 168LL))(this[265], &pbstr) >= 0
    && SysStringLen(pbstr) )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    SlideshowSettings = CSlideshowSettingsAdapter_GetSlideshowSettings(this[265]);
    if ( SlideshowSettings )
    {
      v5 = 1;
      (*(void (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)SlideshowSettings + 16LL))(SlideshowSettings);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, pbstr);
  }
  v34 = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, BSTR *))(*(_QWORD *)this[266] + 168LL))(this[266], &v34) < 0
    || (v8 = 1, !SysStringLen(v34)) )
  {
    v8 = 0;
  }
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
    v7);
  LODWORD(ppv) = 0;
  pv = 0;
  v9 = this[266];
  v10 = **(__int64 (__fastcall ***)(struct ITheme *, GUID *, LPVOID *))v9;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
  v11 = v10(v9, &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a, &pv);
  if ( v11 >= 0 )
  {
    if ( (*(int (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)pv + 32LL))(pv, &ppv) >= 0 && (_DWORD)ppv == 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl'::`2'::impl) )
        DesktopSpotlightThemeFallbackImage = CThemeManager2::_GetDesktopSpotlightThemeFallbackImage((CThemeManager2 *)this);
      else
        DesktopSpotlightThemeFallbackImage = L"%SystemRoot%\\Web\\Wallpaper\\windows\\img0.jpg";
      ATL::CComBSTR::operator=(&v34, DesktopSpotlightThemeFallbackImage);
      v8 = 1;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x93C,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
  if ( a2 )
  {
    ppidl = 0;
    v13 = (*(__int64 (__fastcall **)(struct ITheme *, LPITEMIDLIST *))(*(_QWORD *)this[266] + 224LL))(this[266], &ppidl);
    if ( v13 >= 0 )
    {
      ppv = 0;
      v13 = (*(__int64 (__fastcall **)(LPITEMIDLIST, LPVOID *))(*(_QWORD *)&ppidl->mkid.cb + 88LL))(ppidl, &ppv);
      if ( v13 >= 0 )
      {
        pv = 0;
        v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)ppv + 32LL))(ppv, 0, &pv);
        if ( v13 >= 0 )
        {
          ATL::CComBSTR::operator=(&v34, pv);
          v8 = SysStringLen(v34) != 0;
          CoTaskMemFree(pv);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
        (unsigned int)v13);
  }
  v37 = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)this[265] + 184LL))(this[265], &v37) < 0 )
    v37 = 6;
  v35 = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)this[266] + 184LL))(this[266], &v35) < 0 )
    v35 = 4;
  memset_0(pszPath, 0, 0x208u);
  if ( a2 )
    v14 = CSlideshowSettingsAdapter_GetSlideshowSettings(this[266]);
  else
    v14 = 0;
  v41 = v14;
  if ( !*((_BYTE *)this + 2145)
    && !*((_BYTE *)this + 2146)
    && v5 == v8
    && (!v5 || CompareStringOrdinal(pbstr, -1, v34, -1, 1) == 2)
    && v37 == v35 )
  {
    goto LABEL_64;
  }
  ppv = 0;
  v15 = CoCreateInstance(&CLSID_ActiveDesktop, 0, 1u, &GUID_f490eb00_1240_11d1_9888_006097deacf9, &ppv);
  if ( v15 >= 0 )
  {
    LODWORD(ppidl) = 8;
    HIDWORD(ppidl) = v35;
    (*(void (__fastcall **)(LPVOID, LPITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, &ppidl, 0);
    v16 = *(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 40LL);
    v17 = *((_BYTE *)this + 2145) != 0 ? 0x4000000 : 0;
    if ( v8 )
    {
      v18 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct ATL::CComBSTR *)&v34);
      v19 = 1;
    }
    else
    {
      v18 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&pv, &Default);
      v19 = 2;
    }
    LODWORD(v38) = v19;
    v16(ppv, *v18, v17);
    if ( (v19 & 2) != 0 )
    {
      LOBYTE(v19) = v19 & 0xFD;
      SysFreeString((BSTR)pv);
    }
    if ( (v19 & 1) != 0 )
      SysFreeString(bstrString);
    v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, v14 != 0 ? 7 : 71);
    v15 = v20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, (_DWORD)v34, v35, v20);
    if ( v15 >= 0 && SysStringLen(v34) && (int)StringCchCopyW(pszPath, 0x104u, v34) >= 0 )
      PathRemoveFileSpecW(pszPath);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v15 >= 0 )
    {
LABEL_64:
      if ( v14 )
      {
        v15 = (*(__int64 (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)v14 + 24LL))(v14);
        if ( v15 >= 0 )
        {
          SlideshowFileSource = CSlideshowSettingsAdapter_GetSlideshowFileSource(v14);
          v24 = SlideshowFileSource;
          if ( SlideshowFileSource )
          {
            v25 = (struct _ITEMIDLIST_ABSOLUTE *)ILClone(*((LPCITEMIDLIST *)SlideshowFileSource + 1));
            v27 = (ITEMIDLIST *)v25;
            if ( v25 )
            {
              CThemeManager2::_SaveIDListToWallpaperMRU(v26, v25);
              ILFree(v27);
            }
            CFileSource::Release(v24);
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
            (unsigned int)v15);
      }
      else
      {
        v28 = CSlideshowSettingsAdapter_DisableSlidehow();
        v15 = v28;
        if ( v28 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
            (unsigned int)v28);
        }
        if ( pszPath[0] )
        {
          if ( (unsigned int)SHExpandEnvironmentStringsW(L"%SystemRoot%\\Web\\Wallpaper", pszPrefix, 260) )
          {
            if ( !PathIsPrefixW(pszPrefix, pszPath) )
            {
              v38 = 0;
              if ( SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v38) >= 0 )
              {
                pv = 0;
                if ( (int)GetFilteredShellItem(v38, (struct IShellItem **)&pv) >= 0 )
                {
                  ppidl = 0;
                  if ( SHGetIDListFromObject((IUnknown *)pv, &ppidl) >= 0 )
                  {
                    CThemeManager2::_SaveIDListToWallpaperMRU(v29, (struct _ITEMIDLIST_ABSOLUTE *)ppidl);
                    ILFree(ppidl);
                  }
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                }
                ((void (__fastcall *)(struct IShellItem *))v38->lpVtbl->Release)(v38);
              }
            }
          }
        }
      }
    }
  }
  SafeRelease<IThemeStyle>(&v41);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
      (unsigned int)v15);
  SysFreeString(v34);
  SysFreeString(pbstr);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18004e3a4  push    rbp
0x18004e3a6  push    rbx
0x18004e3a7  push    rsi
0x18004e3a8  push    rdi
0x18004e3a9  push    r12
0x18004e3ab  push    r13
0x18004e3ad  push    r14
0x18004e3af  push    r15
0x18004e3b1  lea     rbp, [rsp-3B8h]
0x18004e3b9  sub     rsp, 4B8h
0x18004e3c0  mov     rax, cs:__security_cookie
0x18004e3c7  xor     rax, rsp
0x18004e3ca  mov     [rbp+3F0h+var_50], rax
0x18004e3d1  mov     r13b, dl
0x18004e3d4  mov     r14, rcx
0x18004e3d7  xor     ebx, ebx
0x18004e3d9  mov     dword ptr [rsp+4F0h+var_490], ebx
0x18004e3dd  lea     rdi, WPP_GLOBAL_Control
0x18004e3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e3eb  cmp     rcx, rdi
0x18004e3ee  jz      short loc_18004E41D
0x18004e3f0  test    byte ptr [rcx+1Ch], 8
0x18004e3f4  jz      short loc_18004E41D
0x18004e3f6  lea     rax, aOff; "off"
0x18004e3fd  lea     r9, aOn; "on"
0x18004e404  test    dl, dl
0x18004e406  cmovz   r9, rax
0x18004e40a  lea     edx, [rbx+40h]
0x18004e40d  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004e414  mov     rcx, [rcx+10h]
0x18004e418  call    WPP_SF_S
0x18004e41d  mov     [rsp+4F0h+pbstr], rbx
0x18004e422  mov     rcx, [r14+848h]
0x18004e429  mov     rax, [rcx]
0x18004e42c  lea     rdx, [rsp+4F0h+pbstr]
0x18004e431  mov     rax, [rax+0A8h]
0x18004e438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e43d  test    eax, eax
0x18004e43f  js      short loc_18004E45A
0x18004e441  mov     rcx, [rsp+4F0h+pbstr]; pbstr
0x18004e446  call    cs:__imp_SysStringLen
0x18004e44c  test    eax, eax
0x18004e44e  jz      short loc_18004E45A
0x18004e450  mov     esi, 1
0x18004e455  mov     r12b, sil
0x18004e458  jmp     short loc_18004E4B4
0x18004e45a  mov     r12b, bl
0x18004e45d  mov     rcx, [r14+848h]; struct ITheme *
0x18004e464  call    ?CSlideshowSettingsAdapter_GetSlideshowSettings@@YAPEAUISlideshowSettings@@PEAUITheme@@@Z; CSlideshowSettingsAdapter_GetSlideshowSettings(ITheme *)
0x18004e469  mov     rdx, rax
0x18004e46c  mov     esi, 1
0x18004e471  test    rax, rax
0x18004e474  jz      short loc_18004E488
0x18004e476  mov     r12b, sil
0x18004e479  mov     rcx, [rax]
0x18004e47c  mov     rax, [rcx+10h]
0x18004e480  mov     rcx, rdx
0x18004e483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e488  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e48f  cmp     rcx, rdi
0x18004e492  jz      short loc_18004E4B4
0x18004e494  test    byte ptr [rcx+1Ch], 8
0x18004e498  jz      short loc_18004E4B4
0x18004e49a  mov     edx, 41h ; 'A'
0x18004e49f  mov     r9, [rsp+4F0h+pbstr]
0x18004e4a4  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004e4ab  mov     rcx, [rcx+10h]
0x18004e4af  call    WPP_SF_S
0x18004e4b4  mov     [rsp+4F0h+var_4B0], rbx
0x18004e4b9  mov     rcx, [r14+850h]
0x18004e4c0  mov     rax, [rcx]
0x18004e4c3  lea     rdx, [rsp+4F0h+var_4B0]
0x18004e4c8  mov     rax, [rax+0A8h]
0x18004e4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4d4  test    eax, eax
0x18004e4d6  js      short loc_18004E4EA
0x18004e4d8  mov     rcx, [rsp+4F0h+var_4B0]; pbstr
0x18004e4dd  call    cs:__imp_SysStringLen
0x18004e4e3  test    eax, eax
0x18004e4e5  mov     r15b, sil
0x18004e4e8  jnz     short loc_18004E4ED
0x18004e4ea  mov     r15b, bl
0x18004e4ed  mov     dl, sil
0x18004e4f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x18004e4f7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004e4fc  mov     dword ptr [rsp+4F0h+ppv], ebx
0x18004e500  mov     [rsp+4F0h+pv], rbx
0x18004e505  mov     rdi, [r14+850h]
0x18004e50c  mov     rax, [rdi]
0x18004e50f  mov     rbx, [rax]
0x18004e512  lea     rcx, [rsp+4F0h+pv]
0x18004e517  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e51c  lea     r8, [rsp+4F0h+pv]
0x18004e521  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x18004e528  mov     rcx, rdi
0x18004e52b  mov     rax, rbx
0x18004e52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e533  mov     rcx, [rbp+3F8h]; this
0x18004e53a  xor     edi, edi
0x18004e53c  test    eax, eax
0x18004e53e  jns     short loc_18004E556
0x18004e540  mov     r9d, eax; char *
0x18004e543  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004e54a  mov     edx, 93Ch; void *
0x18004e54f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e554  jmp     short loc_18004E5A7
0x18004e556  mov     rcx, [rsp+4F0h+pv]
0x18004e55b  mov     rax, [rcx]
0x18004e55e  lea     rdx, [rsp+4F0h+ppv]
0x18004e563  mov     rax, [rax+20h]
0x18004e567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e56c  test    eax, eax
0x18004e56e  js      short loc_18004E5A7
0x18004e570  cmp     dword ptr [rsp+4F0h+ppv], esi
0x18004e574  jnz     short loc_18004E5A7
0x18004e576  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl(void)'::`2'::impl
0x18004e57d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(void)
0x18004e582  test    al, al
0x18004e584  jz      short loc_18004E593
0x18004e586  mov     rcx, r14; this
0x18004e589  call    ?_GetDesktopSpotlightThemeFallbackImage@CThemeManager2@@AEAAPEAGXZ; CThemeManager2::_GetDesktopSpotlightThemeFallbackImage(void)
0x18004e58e  mov     rdx, rax
0x18004e591  jmp     short loc_18004E59A
0x18004e593  lea     rdx, aSystemrootWebW_1; "%SystemRoot%\\Web\\Wallpaper\\windows\\"...
0x18004e59a  lea     rcx, [rsp+4F0h+var_4B0]
0x18004e59f  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004e5a4  mov     r15b, sil
0x18004e5a7  lea     rcx, [rsp+4F0h+pv]
0x18004e5ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e5b1  test    r13b, r13b
0x18004e5b4  jz      loc_18004E6A6
0x18004e5ba  mov     [rsp+4F0h+ppidl], rdi
0x18004e5bf  mov     rcx, [r14+850h]
0x18004e5c6  mov     rax, [rcx]
0x18004e5c9  lea     rdx, [rsp+4F0h+ppidl]
0x18004e5ce  mov     rax, [rax+0E0h]
0x18004e5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5da  mov     ebx, eax
0x18004e5dc  test    eax, eax
0x18004e5de  js      loc_18004E675
0x18004e5e4  mov     [rsp+4F0h+ppv], rdi
0x18004e5e9  mov     rcx, [rsp+4F0h+ppidl]
0x18004e5ee  mov     rax, [rcx]
0x18004e5f1  lea     rdx, [rsp+4F0h+ppv]
0x18004e5f6  mov     rax, [rax+58h]
0x18004e5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5ff  mov     ebx, eax
0x18004e601  test    eax, eax
0x18004e603  js      short loc_18004E664
0x18004e605  mov     [rsp+4F0h+pv], rdi
0x18004e60a  mov     rcx, [rsp+4F0h+ppv]
0x18004e60f  mov     rax, [rcx]
0x18004e612  lea     r8, [rsp+4F0h+pv]
0x18004e617  xor     edx, edx
0x18004e619  mov     rax, [rax+20h]
0x18004e61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e622  mov     ebx, eax
0x18004e624  test    eax, eax
0x18004e626  js      short loc_18004E653
0x18004e628  mov     rdx, [rsp+4F0h+pv]
0x18004e62d  lea     rcx, [rsp+4F0h+var_4B0]
0x18004e632  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004e637  mov     rcx, [rsp+4F0h+var_4B0]; pbstr
0x18004e63c  call    cs:__imp_SysStringLen
0x18004e642  test    eax, eax
0x18004e644  setnz   r15b
0x18004e648  mov     rcx, [rsp+4F0h+pv]; pv
0x18004e64d  call    cs:__imp_CoTaskMemFree
0x18004e653  mov     rcx, [rsp+4F0h+ppv]
0x18004e658  mov     rax, [rcx]
0x18004e65b  mov     rax, [rax+10h]
0x18004e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e664  mov     rcx, [rsp+4F0h+ppidl]
0x18004e669  mov     rax, [rcx]
0x18004e66c  mov     rax, [rax+10h]
0x18004e670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e675  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e67c  lea     rax, WPP_GLOBAL_Control
0x18004e683  cmp     rcx, rax
0x18004e686  jz      short loc_18004E6A6
0x18004e688  test    byte ptr [rcx+1Ch], 8
0x18004e68c  jz      short loc_18004E6A6
0x18004e68e  mov     edx, 42h ; 'B'
0x18004e693  mov     r9d, ebx
0x18004e696  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004e69d  mov     rcx, [rcx+10h]
0x18004e6a1  call    WPP_SF_d
0x18004e6a6  mov     [rsp+4F0h+var_498], edi
0x18004e6aa  mov     rcx, [r14+848h]
0x18004e6b1  mov     rax, [rcx]
0x18004e6b4  lea     rdx, [rsp+4F0h+var_498]
0x18004e6b9  mov     rax, [rax+0B8h]
0x18004e6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6c5  test    eax, eax
0x18004e6c7  jns     short loc_18004E6D1
0x18004e6c9  mov     [rsp+4F0h+var_498], 6
0x18004e6d1  mov     [rsp+4F0h+var_4A8], edi
0x18004e6d5  mov     rcx, [r14+850h]
0x18004e6dc  mov     rax, [rcx]
0x18004e6df  lea     rdx, [rsp+4F0h+var_4A8]
0x18004e6e4  mov     rax, [rax+0B8h]
0x18004e6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6f0  test    eax, eax
0x18004e6f2  jns     short loc_18004E6FC
0x18004e6f4  mov     [rsp+4F0h+var_4A8], 4
0x18004e6fc  xor     edx, edx; Val
0x18004e6fe  mov     r8d, 208h; Size
0x18004e704  lea     rcx, [rbp+3F0h+pszPath]; void *
0x18004e708  call    memset_0
0x18004e70d  test    r13b, r13b
0x18004e710  jz      short loc_18004E726
0x18004e712  mov     rcx, [r14+850h]; struct ITheme *
0x18004e719  call    ?CSlideshowSettingsAdapter_GetSlideshowSettings@@YAPEAUISlideshowSettings@@PEAUITheme@@@Z; CSlideshowSettingsAdapter_GetSlideshowSettings(ITheme *)
0x18004e71e  mov     rdi, rax
0x18004e721  xor     r13d, r13d
0x18004e724  jmp     short loc_18004E72C
0x18004e726  xor     r13d, r13d
0x18004e729  mov     edi, r13d
0x18004e72c  mov     [rsp+4F0h+var_478], rdi
0x18004e731  cmp     [r14+861h], r13b
0x18004e738  jnz     short loc_18004E77A
0x18004e73a  cmp     [r14+862h], r13b
0x18004e741  jnz     short loc_18004E77A
0x18004e743  cmp     r12b, r15b
0x18004e746  jnz     short loc_18004E77A
0x18004e748  test    r12b, r12b
0x18004e74b  jz      short loc_18004E76C
0x18004e74d  mov     [rsp+4F0h+bIgnoreCase], esi; bIgnoreCase
0x18004e751  or      edx, 0FFFFFFFFh; cchCount1
0x18004e754  mov     r9d, edx; cchCount2
0x18004e757  mov     r8, [rsp+4F0h+var_4B0]; lpString2
0x18004e75c  mov     rcx, [rsp+4F0h+pbstr]; lpString1
0x18004e761  call    cs:__imp_CompareStringOrdinal
0x18004e767  cmp     eax, 2
0x18004e76a  jnz     short loc_18004E77A
0x18004e76c  mov     eax, [rsp+4F0h+var_4A8]
0x18004e770  cmp     [rsp+4F0h+var_498], eax
0x18004e774  jz      loc_18004E903
0x18004e77a  mov     [rsp+4F0h+ppv], r13
0x18004e77f  lea     rax, [rsp+4F0h+ppv]
0x18004e784  mov     qword ptr [rsp+4F0h+bIgnoreCase], rax; ppv
0x18004e789  lea     r9, _GUID_f490eb00_1240_11d1_9888_006097deacf9; riid
0x18004e790  mov     r8d, esi; dwClsContext
0x18004e793  xor     edx, edx; pUnkOuter
0x18004e795  lea     rcx, CLSID_ActiveDesktop; rclsid
0x18004e79c  call    cs:__imp_CoCreateInstance
0x18004e7a2  mov     ebx, eax
0x18004e7a4  test    eax, eax
0x18004e7a6  js      loc_18004EA9E
0x18004e7ac  mov     dword ptr [rsp+4F0h+ppidl], 8
0x18004e7b4  mov     eax, [rsp+4F0h+var_4A8]
0x18004e7b8  mov     dword ptr [rsp+4F0h+ppidl+4], eax
0x18004e7bc  mov     rcx, [rsp+4F0h+ppv]
0x18004e7c1  mov     rax, [rcx]
0x18004e7c4  xor     r8d, r8d
0x18004e7c7  lea     rdx, [rsp+4F0h+ppidl]
0x18004e7cc  mov     rax, [rax+38h]
0x18004e7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7d5  mov     rax, [rsp+4F0h+ppv]
0x18004e7da  mov     rcx, [rax]
0x18004e7dd  mov     r12, [rcx+28h]
0x18004e7e1  mov     al, [r14+861h]
0x18004e7e8  neg     al
0x18004e7ea  sbb     r14d, r14d
0x18004e7ed  and     r14d, 4000000h
0x18004e7f4  test    r15b, r15b
0x18004e7f7  jz      short loc_18004E80D
0x18004e7f9  lea     rdx, [rsp+4F0h+var_4B0]; struct ATL::CComBSTR *
0x18004e7fe  lea     rcx, [rsp+4F0h+bstrString]; this
0x18004e803  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x18004e808  nop
0x18004e809  mov     ebx, esi
0x18004e80b  jmp     short loc_18004E824
0x18004e80d  lea     rdx, Default; unsigned __int16 *
0x18004e814  lea     rcx, [rsp+4F0h+pv]; this
0x18004e819  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18004e81e  nop
0x18004e81f  mov     ebx, 2
0x18004e824  mov     dword ptr [rsp+4F0h+var_490], ebx
0x18004e828  mov     r8d, r14d
0x18004e82b  mov     rdx, [rax]
0x18004e82e  mov     rcx, [rsp+4F0h+ppv]
0x18004e833  mov     rax, r12
0x18004e836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e83b  nop
0x18004e83c  test    bl, 2
0x18004e83f  jz      short loc_18004E850
0x18004e841  and     ebx, 0FFFFFFFDh
0x18004e844  mov     rcx, [rsp+4F0h+pv]; bstrString
0x18004e849  call    cs:__imp_SysFreeString
0x18004e84f  nop
0x18004e850  test    sil, bl
0x18004e853  jz      short loc_18004E860
0x18004e855  mov     rcx, [rsp+4F0h+bstrString]; bstrString
0x18004e85a  call    cs:__imp_SysFreeString
0x18004e860  mov     rcx, [rsp+4F0h+ppv]
0x18004e865  mov     r8, [rcx]
0x18004e868  mov     rax, rdi
0x18004e86b  neg     rax
0x18004e86e  sbb     edx, edx
  ... truncated ...
```
