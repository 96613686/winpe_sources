# CThemeManager2::_ApplyDesktopBackground(bool,THEMEPACK_FLAGS)

- ea: `0x18004d9f0`
- end: `0x18004e39e`
- name: `?_ApplyDesktopBackground@CThemeManager2@@AEAAJ_NW4THEMEPACK_FLAGS@@@Z`
- size: `2478`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004f044`

## callees

- `0x180005410`
- `0x180008dd8`
- `0x18000ab10`
- `0x18000c598`
- `0x18001bcfc`
- `0x18001ed40`
- `0x1800208d4`
- `0x180021134`
- `0x18002fed4`
- `0x180032e48`
- `0x18003336c`
- `0x18003380c`
- `0x180033da8`
- `0x1800358c0`
- `0x18003633c`
- `0x18003cf08`
- `0x180042664`
- `0x1800427dc`
- `0x18004b2a4`
- `0x18004b610`
- `0x18004b7e8`
- `0x18004ca20`
- `0x18004cdd4`
- `0x18004d9f0`
- `0x18004e3a4`
- `0x180050414`
- `0x18005159c`
- `0x180051628`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x18004e28c`
- `SHELL32!SHParseDisplayName` at `0x18004e28c`
- `SHELL32!__imp_ILClone` at `0x18004dce5`
- `SHELL32!__imp_ILClone` at `0x18004dce5`
- `SHELL32!__imp_ILFree` at `0x18004dd2c`
- `SHELL32!__imp_ILFree` at `0x18004e2a5`
- `SHELL32!__imp_ILFree` at `0x18004dd2c`
- `SHELL32!__imp_ILFree` at `0x18004e2a5`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004e263`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18004e263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc27`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004dad9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004dad9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004debf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ded8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004df36`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e0e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e14e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e160`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e1e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18004debf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ded8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004df36`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e0e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e14e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e160`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e1e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CThemeManager2::_ApplyDesktopBackground(__int64 a1, char a2, int a3)
{
  char v3; // r12
  int v6; // edi
  const wchar_t *v7; // r9
  HRESULT Instance; // ebx
  char v9; // r13
  struct ISlideshowSettings *SlideshowSettings; // rax
  struct ISlideshowSettings *v11; // r15
  int v12; // eax
  int v13; // eax
  int v14; // eax
  struct CFileSource *SlideshowFileSource; // rax
  LPCITEMIDLIST *v16; // r14
  unsigned int v17; // edi
  int v18; // eax
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  struct _ITEMIDLIST_ABSOLUTE *v23; // rax
  ITEMIDLIST *v24; // r12
  wil::details::in1diag3 *v25; // rcx
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // ebx
  unsigned int v29; // eax
  int v30; // eax
  unsigned int v31; // r15d
  __int64 v32; // rcx
  int v33; // r12d
  __int64 (__fastcall *v34)(struct IDesktopWallpaperPrivate *, _QWORD, _QWORD); // rbx
  _QWORD *v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  int v38; // r8d
  int v39; // r15d
  __int64 (__fastcall ***v40)(_QWORD, GUID *, BSTR *); // rdi
  __int64 (__fastcall *v41)(_QWORD, GUID *, BSTR *); // rbx
  int v42; // eax
  const unsigned __int16 *DesktopSpotlightThemeFallbackImage; // rdx
  __int64 v44; // rcx
  __int64 (__fastcall *v45)(struct IDesktopWallpaperPrivate *, _QWORD, _QWORD); // rbx
  _QWORD *v46; // rax
  int v47; // edi
  int v48; // edx
  int v49; // r8d
  bool v50; // zf
  __int64 (__fastcall *v51)(struct IDesktopWallpaperPrivate *, _QWORD, _QWORD); // rbx
  _QWORD *v52; // rax
  int v53; // edi
  int v54; // eax
  CThemeManager2 *v55; // rcx
  int v56; // eax
  _QWORD *v57; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  int v62; // [rsp+40h] [rbp-C0h]
  struct IDesktopWallpaperPrivate *v63; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v65; // [rsp+54h] [rbp-ACh] BYREF
  int v66; // [rsp+58h] [rbp-A8h] BYREF
  int v67; // [rsp+5Ch] [rbp-A4h]
  BSTR v68; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+68h] [rbp-98h]
  _QWORD v70[42]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  CThemeManager2 *retaddr; // [rsp+418h] [rbp+318h]

  v3 = a3;
  v69 = a3;
  v6 = 0;
  v62 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v7 = L"on";
    if ( !a2 )
      v7 = L"off";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v7);
  }
  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v70);
  v70[0] = &ThemesTelemetry::ApplyDesktopBackground::`vftable';
  ThemesTelemetry::ApplyDesktopBackground::StartActivity((ThemesTelemetry::ApplyDesktopBackground *)v70);
  memset_0(pszPath, 0, 0x208u);
  v63 = 0;
  Instance = CoCreateInstance(
               &CLSID_DesktopWallpaper,
               0,
               4u,
               &GUID_c182461f_dfac_4375_ab6e_4cc45aa7f9cc,
               (LPVOID *)&v63);
  if ( Instance >= 0 )
  {
    v9 = 1;
    v67 = 1;
    v65 = 0;
    if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 2128) + 184LL))(
           *(_QWORD *)(a1 + 2128),
           &v65) < 0 )
      v65 = 4;
    v66 = 0;
    if ( !a2
      || (SlideshowSettings = CSlideshowSettingsAdapter_GetSlideshowSettings(*(struct ITheme **)(a1 + 2128)),
          (v11 = SlideshowSettings) == 0) )
    {
      if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 2128) + 432LL))(*(_QWORD *)(a1 + 2128), &v66) >= 0
        && v66 )
      {
        CThemeManager2::_LoadPerMonitorData((CThemeManager2 *)a1, v63);
        v31 = 0;
        while ( v31 < *(_DWORD *)(a1 + 2224) )
        {
          pv = 0;
          v32 = *(_QWORD *)(a1 + 2128);
          v64 = v31 + 1;
          v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v32 + 448LL))(v32, v31 + 1, &pv);
          v34 = *(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, _QWORD))(*(_QWORD *)v63 + 24LL);
          if ( v33 < 0 )
          {
            v35 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &Default);
            v6 |= 2u;
          }
          else
          {
            v35 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v68, (const struct ATL::CComBSTR *)&pv);
            v6 |= 1u;
          }
          v62 = v6;
          Instance = v34(v63, *(_QWORD *)(a1 + 8LL * v31 + 2232), *v35);
          if ( (v6 & 2) != 0 )
          {
            v6 &= ~2u;
            v62 = v6;
            SysFreeString(bstrString);
          }
          if ( (v6 & 1) != 0 )
          {
            v6 &= ~1u;
            v62 = v6;
            SysFreeString(v68);
          }
          if ( Instance >= 0 )
          {
            if ( v33 >= 0 && v9 )
            {
              (*(void (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD))(*(_QWORD *)v63 + 96LL))(v63, 0);
              StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)pv);
              v9 = 0;
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8AD,
              (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
              (const char *)(unsigned int)Instance,
              ppv);
          }
          SysFreeString((BSTR)pv);
          v31 = v64;
          if ( Instance < 0 )
            goto LABEL_94;
        }
        goto LABEL_92;
      }
      pv = 0;
      v36 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(a1 + 2128) + 168LL))(
              *(_QWORD *)(a1 + 2128),
              &pv);
      v39 = v36;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)pv, v38, v36, (__int64)pv);
      LOBYTE(v37) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
        v37);
      v64 = 0;
      bstrString = 0;
      v40 = *(__int64 (__fastcall ****)(_QWORD, GUID *, BSTR *))(a1 + 2128);
      v41 = **v40;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&bstrString);
      v42 = v41(v40, &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a, &bstrString);
      if ( v42 >= 0 )
      {
        if ( (*(int (__fastcall **)(BSTR, unsigned int *))(*(_QWORD *)bstrString + 32LL))(bstrString, &v64) >= 0
          && v64 == 1 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl'::`2'::impl) )
            DesktopSpotlightThemeFallbackImage = CThemeManager2::_GetDesktopSpotlightThemeFallbackImage((CThemeManager2 *)a1);
          else
            DesktopSpotlightThemeFallbackImage = L"%SystemRoot%\\Web\\Wallpaper\\windows\\img0.jpg";
          ATL::CComBSTR::operator=(&pv, DesktopSpotlightThemeFallbackImage);
          v39 = 0;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8C3,
          (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
          (const char *)(unsigned int)v42,
          ppv);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&bstrString);
      v44 = *(_QWORD *)v63;
      if ( *(_BYTE *)(a1 + 2145) )
      {
        v45 = *(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, _QWORD))(v44 + 152);
        if ( v39 < 0 )
        {
          v46 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v68, &Default);
          v47 = 8;
        }
        else
        {
          v46 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct ATL::CComBSTR *)&pv);
          v47 = 4;
        }
        v62 = v47;
        Instance = v45(v63, 0, *v46);
        if ( (v47 & 8) != 0 )
        {
          LOBYTE(v47) = v47 & 0xF7;
          SysFreeString(v68);
        }
        v50 = (v47 & 4) == 0;
      }
      else
      {
        v51 = *(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, _QWORD))(v44 + 24);
        if ( v39 < 0 )
        {
          v52 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v68, &Default);
          v53 = 32;
        }
        else
        {
          v52 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct ATL::CComBSTR *)&pv);
          v53 = 16;
        }
        v62 = v53;
        Instance = v51(v63, 0, *v52);
        if ( (v53 & 0x20) != 0 )
        {
          LOBYTE(v53) = v53 & 0xDF;
          SysFreeString(v68);
        }
        v50 = (v53 & 0x10) == 0;
      }
      if ( !v50 )
        SysFreeString(bstrString);
      if ( Instance >= 0 )
      {
        if ( v39 >= 0 )
        {
          (*(void (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD))(*(_QWORD *)v63 + 96LL))(v63, 0);
          StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)pv);
          NotifyThemeCPLs(6);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8DC,
          (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, v49, (_DWORD)pv, Instance);
      SysFreeString((BSTR)pv);
LABEL_91:
      if ( Instance < 0 )
      {
LABEL_94:
        (*(void (__fastcall **)(struct IDesktopWallpaperPrivate *))(*(_QWORD *)v63 + 184LL))(v63);
        (*(void (__fastcall **)(struct IDesktopWallpaperPrivate *))(*(_QWORD *)v63 + 16LL))(v63);
        if ( Instance < 0 )
        {
LABEL_108:
          v57 = WPP_GLOBAL_Control;
          goto LABEL_109;
        }
        if ( (v69 & 3) == 0 )
        {
          if ( (_BYTE)v67 )
          {
            PathRemoveFileSpecW(pszPath);
            bstrString = 0;
            if ( SHParseDisplayName(pszPath, 0, (LPITEMIDLIST *)&bstrString, 0, 0) >= 0 )
            {
              CThemeManager2::_SaveIDListToWallpaperMRU(v55, (struct _ITEMIDLIST_ABSOLUTE *)bstrString);
              ILFree((LPITEMIDLIST)bstrString);
            }
          }
        }
LABEL_99:
        NotifyThemeCPLs(7);
        goto LABEL_108;
      }
LABEL_92:
      v54 = (*(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD))(*(_QWORD *)v63 + 80LL))(v63, v65);
      Instance = v54;
      if ( v54 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8EC,
          (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
          (const char *)(unsigned int)v54,
          ppv);
      goto LABEL_94;
    }
    bstrString = 0;
    v12 = (*(__int64 (__fastcall **)(struct ISlideshowSettings *, BSTR *))(*(_QWORD *)SlideshowSettings + 88LL))(
            SlideshowSettings,
            &bstrString);
    Instance = v12;
    if ( v12 >= 0 )
    {
      pv = 0;
      v13 = (*(__int64 (__fastcall **)(BSTR, _QWORD, LPVOID *))(*(_QWORD *)bstrString + 32LL))(bstrString, 0, &pv);
      Instance = v13;
      if ( v13 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, _QWORD, LPVOID))(*(_QWORD *)v63 + 24LL))(
                v63,
                0,
                pv);
        Instance = v14;
        if ( v14 >= 0 )
          StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)pv);
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x873,
            (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
            (const char *)(unsigned int)v14,
            ppv);
        CoTaskMemFree(pv);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x870,
          (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
          (const char *)(unsigned int)v13,
          ppv);
      }
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x86C,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)(unsigned int)v12,
        ppv);
    }
    SlideshowFileSource = CSlideshowSettingsAdapter_GetSlideshowFileSource(v11);
    v16 = (LPCITEMIDLIST *)SlideshowFileSource;
    v17 = SlideshowFileSource == 0 ? 0x80004005 : 0;
    if ( !SlideshowFileSource )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x881,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)v17,
        ppv);
      goto LABEL_33;
    }
    pv = 0;
    v18 = CFileSource::s_ConvertToShellItemArray(SlideshowFileSource, (struct IShellItemArray **)&pv);
    v17 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x885,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)(unsigned int)v18,
        ppv);
LABEL_32:
      CFileSource::Release((CFileSource *)v16);
LABEL_33:
      v25 = retaddr;
      if ( (v17 & 0x80000000) == 0 )
      {
        v28 = (*(__int64 (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)v11 + 48LL))(v11);
        v29 = (*(__int64 (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)v11 + 40LL))(v11);
        v30 = (*(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, bool, _QWORD))(*(_QWORD *)v63 + 112LL))(
                v63,
                v28 != 0,
                v29);
        Instance = v30;
        v25 = retaddr;
        if ( v30 >= 0 )
        {
LABEL_38:
          (*(void (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)v11 + 16LL))(v11);
          goto LABEL_91;
        }
        v26 = (unsigned int)v30;
        v27 = 2208;
      }
      else
      {
        v26 = v17;
        v27 = 2202;
      }
      wil::details::in1diag3::_Log_Hr(
        v25,
        (void *)v27,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)v26,
        ppv);
      goto LABEL_38;
    }
    v19 = (*(__int64 (__fastcall **)(struct IDesktopWallpaperPrivate *, LPVOID))(*(_QWORD *)v63 + 96LL))(v63, pv);
    v17 = v19;
    v20 = retaddr;
    if ( v19 >= 0 )
    {
      if ( (v3 & 3) != 0 )
      {
LABEL_31:
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        goto LABEL_32;
      }
      v23 = (struct _ITEMIDLIST_ABSOLUTE *)ILClone(v16[1]);
      v24 = (ITEMIDLIST *)v23;
      v17 = v23 == 0 ? 0x80004005 : 0;
      v20 = retaddr;
      if ( v23 )
      {
        CThemeManager2::_SaveIDListToWallpaperMRU(retaddr, v23);
        LOBYTE(v67) = 0;
        ILFree(v24);
        goto LABEL_31;
      }
      v21 = v17;
      v22 = 2189;
    }
    else
    {
      v21 = (unsigned int)v19;
      v22 = 2184;
    }
    wil::details::in1diag3::_Log_Hr(
      v20,
      (void *)v22,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)v21,
      ppv);
    goto LABEL_31;
  }
  if ( !*(_BYTE *)(a1 + 2145) )
    goto LABEL_108;
  v56 = CThemeManager2::_ApplyDesktopBackgroundLegacy((struct ITheme **)a1, a2);
  Instance = v56;
  if ( v56 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x906,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)(unsigned int)v56,
      ppv);
  v57 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
      (unsigned int)Instance);
    v57 = WPP_GLOBAL_Control;
  }
  if ( Instance >= 0 )
    goto LABEL_99;
LABEL_109:
  if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 8) != 0 )
    WPP_SF_d(v57[2], 63, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, (unsigned int)Instance);
  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v70, (unsigned int)Instance);
  ThemesTelemetry::ApplyDesktopBackground::~ApplyDesktopBackground((ThemesTelemetry::ApplyDesktopBackground *)v70);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004d9f0  mov     [rsp-8+arg_10], rbx
0x18004d9f5  push    rbp
0x18004d9f6  push    rsi
0x18004d9f7  push    rdi
0x18004d9f8  push    r12
0x18004d9fa  push    r13
0x18004d9fc  push    r14
0x18004d9fe  push    r15
0x18004da00  lea     rbp, [rsp-2E0h]
0x18004da08  sub     rsp, 3E0h
0x18004da0f  mov     rax, cs:__security_cookie
0x18004da16  xor     rax, rsp
0x18004da19  mov     [rbp+310h+var_40], rax
0x18004da20  mov     r12d, r8d
0x18004da23  mov     [rsp+410h+var_3A8], r8d
0x18004da28  mov     sil, dl
0x18004da2b  mov     r14, rcx
0x18004da2e  xor     r15d, r15d
0x18004da31  mov     edi, r15d
0x18004da34  mov     [rsp+410h+var_3D0], r15d
0x18004da39  lea     r13, WPP_GLOBAL_Control
0x18004da40  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da47  cmp     rcx, r13
0x18004da4a  jz      short loc_18004DA7A
0x18004da4c  test    byte ptr [rcx+1Ch], 8
0x18004da50  jz      short loc_18004DA7A
0x18004da52  lea     rax, aOff; "off"
0x18004da59  lea     r9, aOn; "on"
0x18004da60  test    dl, dl
0x18004da62  cmovz   r9, rax
0x18004da66  lea     edx, [r15+3Bh]
0x18004da6a  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004da71  mov     rcx, [rcx+10h]
0x18004da75  call    WPP_SF_S
0x18004da7a  lea     rdx, aApplydesktopba; "ApplyDesktopBackground"
0x18004da81  lea     rcx, [rsp+410h+var_3A0]; struct wil::details::IFailureCallback *
0x18004da86  call    ??0?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004da8b  lea     rax, ??_7ApplyDesktopBackground@ThemesTelemetry@@6B@; const ThemesTelemetry::ApplyDesktopBackground::`vftable'
0x18004da92  mov     [rsp+410h+var_3A0], rax
0x18004da97  lea     rcx, [rsp+410h+var_3A0]; this
0x18004da9c  call    ?StartActivity@ApplyDesktopBackground@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::ApplyDesktopBackground::StartActivity(void)
0x18004daa1  nop
0x18004daa2  xor     edx, edx; Val
0x18004daa4  mov     r8d, 208h; Size
0x18004daaa  lea     rcx, [rbp+310h+pszPath]; void *
0x18004dab1  call    memset_0
0x18004dab6  mov     [rsp+410h+var_3C8], r15
0x18004dabb  lea     rax, [rsp+410h+var_3C8]
0x18004dac0  mov     qword ptr [rsp+410h+ppv], rax; int
0x18004dac5  lea     r9, _GUID_c182461f_dfac_4375_ab6e_4cc45aa7f9cc; riid
0x18004dacc  xor     edx, edx; pUnkOuter
0x18004dace  lea     r8d, [rdx+4]; dwClsContext
0x18004dad2  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x18004dad9  call    cs:__imp_CoCreateInstance
0x18004dadf  mov     ebx, eax
0x18004dae1  test    eax, eax
0x18004dae3  js      loc_18004E2BE
0x18004dae9  mov     r13d, 1
0x18004daef  mov     [rsp+410h+var_3B4], r13d
0x18004daf4  mov     [rsp+410h+var_3BC], r15d
0x18004daf9  mov     rcx, [r14+850h]
0x18004db00  mov     rax, [rcx]
0x18004db03  lea     rdx, [rsp+410h+var_3BC]
0x18004db08  mov     rax, [rax+0B8h]
0x18004db0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db14  test    eax, eax
0x18004db16  jns     short loc_18004DB20
0x18004db18  mov     [rsp+410h+var_3BC], 4
0x18004db20  mov     [rsp+410h+var_3B8], r15d
0x18004db25  test    sil, sil
0x18004db28  jz      loc_18004DDD1
0x18004db2e  mov     rcx, [r14+850h]; struct ITheme *
0x18004db35  call    ?CSlideshowSettingsAdapter_GetSlideshowSettings@@YAPEAUISlideshowSettings@@PEAUITheme@@@Z; CSlideshowSettingsAdapter_GetSlideshowSettings(ITheme *)
0x18004db3a  mov     r15, rax
0x18004db3d  test    rax, rax
0x18004db40  jz      loc_18004DDD1
0x18004db46  xor     r13d, r13d
0x18004db49  mov     [rsp+410h+bstrString], r13
0x18004db4e  mov     rcx, [rax]
0x18004db51  mov     rax, [rcx+58h]
0x18004db55  lea     rdx, [rsp+410h+bstrString]
0x18004db5a  mov     rcx, r15
0x18004db5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db62  mov     ebx, eax
0x18004db64  mov     rcx, [rbp+318h]; this
0x18004db6b  test    eax, eax
0x18004db6d  jns     short loc_18004DB8B
0x18004db6f  mov     r9d, eax; char *
0x18004db72  lea     rsi, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004db79  mov     r8, rsi; unsigned int
0x18004db7c  mov     edx, 86Ch; void *
0x18004db81  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004db86  jmp     loc_18004DC3E
0x18004db8b  mov     [rsp+410h+pv], r13
0x18004db90  mov     rcx, [rsp+410h+bstrString]
0x18004db95  mov     rax, [rcx]
0x18004db98  lea     r8, [rsp+410h+pv]
0x18004db9d  xor     edx, edx
0x18004db9f  mov     rax, [rax+20h]
0x18004dba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dba8  mov     ebx, eax
0x18004dbaa  mov     rcx, [rbp+318h]; this
0x18004dbb1  test    eax, eax
0x18004dbb3  jns     short loc_18004DBCE
0x18004dbb5  mov     r9d, eax; char *
0x18004dbb8  lea     rsi, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004dbbf  mov     r8, rsi; unsigned int
0x18004dbc2  mov     edx, 870h; void *
0x18004dbc7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dbcc  jmp     short loc_18004DC2D
0x18004dbce  mov     rcx, [rsp+410h+var_3C8]
0x18004dbd3  mov     rax, [rcx]
0x18004dbd6  mov     r8, [rsp+410h+pv]
0x18004dbdb  xor     edx, edx
0x18004dbdd  mov     rax, [rax+18h]
0x18004dbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbe6  mov     ebx, eax
0x18004dbe8  mov     rcx, [rbp+318h]; this
0x18004dbef  lea     rsi, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004dbf6  test    eax, eax
0x18004dbf8  jns     short loc_18004DC0C
0x18004dbfa  mov     r9d, eax; char *
0x18004dbfd  mov     r8, rsi; unsigned int
0x18004dc00  mov     edx, 873h; void *
0x18004dc05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dc0a  jmp     short loc_18004DC22
0x18004dc0c  mov     r8, [rsp+410h+pv]; unsigned __int16 *
0x18004dc11  mov     edx, 104h; unsigned __int64
0x18004dc16  lea     rcx, [rbp+310h+pszPath]; unsigned __int16 *
0x18004dc1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004dc22  mov     rcx, [rsp+410h+pv]; pv
0x18004dc27  call    cs:__imp_CoTaskMemFree
0x18004dc2d  mov     rcx, [rsp+410h+bstrString]
0x18004dc32  mov     rax, [rcx]
0x18004dc35  mov     rax, [rax+10h]
0x18004dc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc3e  mov     rcx, r15; struct ISlideshowSettings *
0x18004dc41  call    ?CSlideshowSettingsAdapter_GetSlideshowFileSource@@YAPEAVCFileSource@@PEAUISlideshowSettings@@@Z; CSlideshowSettingsAdapter_GetSlideshowFileSource(ISlideshowSettings *)
0x18004dc46  mov     r14, rax
0x18004dc49  mov     rcx, rax
0x18004dc4c  neg     rcx
0x18004dc4f  sbb     edi, edi
0x18004dc51  not     edi
0x18004dc53  and     edi, 80004005h
0x18004dc59  mov     rcx, [rbp+318h]; this
0x18004dc60  test    rax, rax
0x18004dc63  jnz     short loc_18004DC7A
0x18004dc65  mov     r9d, edi; char *
0x18004dc68  mov     r8, rsi; unsigned int
0x18004dc6b  mov     edx, 881h; void *
0x18004dc70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dc75  jmp     loc_18004DD4B
0x18004dc7a  mov     [rsp+410h+pv], r13
0x18004dc7f  lea     rdx, [rsp+410h+pv]; ppv
0x18004dc84  mov     rcx, r14; this
0x18004dc87  call    ?s_ConvertToShellItemArray@CFileSource@@SAJPEAV1@PEAPEAUIShellItemArray@@@Z; CFileSource::s_ConvertToShellItemArray(CFileSource *,IShellItemArray * *)
0x18004dc8c  mov     edi, eax
0x18004dc8e  mov     rcx, [rbp+318h]; this
0x18004dc95  test    eax, eax
0x18004dc97  jns     short loc_18004DCAE
0x18004dc99  mov     r9d, eax; char *
0x18004dc9c  mov     r8, rsi; unsigned int
0x18004dc9f  mov     edx, 885h; void *
0x18004dca4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dca9  jmp     loc_18004DD43
0x18004dcae  mov     rcx, [rsp+410h+var_3C8]
0x18004dcb3  mov     rax, [rcx]
0x18004dcb6  mov     rdx, [rsp+410h+pv]
0x18004dcbb  mov     rax, [rax+60h]
0x18004dcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcc4  mov     edi, eax
0x18004dcc6  mov     rcx, [rbp+318h]
0x18004dccd  test    eax, eax
0x18004dccf  jns     short loc_18004DCDB
0x18004dcd1  mov     r9d, eax
0x18004dcd4  mov     edx, 888h
0x18004dcd9  jmp     short loc_18004DD12
0x18004dcdb  test    r12b, 3
0x18004dcdf  jnz     short loc_18004DD32
0x18004dce1  mov     rcx, [r14+8]; pidl
0x18004dce5  call    cs:__imp_ILClone
0x18004dceb  mov     r12, rax
0x18004dcee  mov     rcx, rax
0x18004dcf1  neg     rcx
0x18004dcf4  sbb     edi, edi
0x18004dcf6  not     edi
0x18004dcf8  and     edi, 80004005h
0x18004dcfe  mov     rcx, [rbp+318h]; this
0x18004dd05  test    rax, rax
0x18004dd08  jnz     short loc_18004DD1C
0x18004dd0a  mov     r9d, edi; char *
0x18004dd0d  mov     edx, 88Dh; void *
0x18004dd12  mov     r8, rsi; unsigned int
0x18004dd15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dd1a  jmp     short loc_18004DD32
0x18004dd1c  mov     rdx, r12; struct _ITEMIDLIST_ABSOLUTE *
0x18004dd1f  call    ?_SaveIDListToWallpaperMRU@CThemeManager2@@AEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CThemeManager2::_SaveIDListToWallpaperMRU(_ITEMIDLIST_ABSOLUTE *)
0x18004dd24  mov     byte ptr [rsp+410h+var_3B4], r13b
0x18004dd29  mov     rcx, r12; pidl
0x18004dd2c  call    cs:__imp_ILFree
0x18004dd32  mov     rcx, [rsp+410h+pv]
0x18004dd37  mov     rax, [rcx]
0x18004dd3a  mov     rax, [rax+10h]
0x18004dd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd43  mov     rcx, r14; this
0x18004dd46  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x18004dd4b  mov     rcx, [rbp+318h]
0x18004dd52  test    edi, edi
0x18004dd54  jns     short loc_18004DD60
0x18004dd56  mov     r9d, edi
0x18004dd59  mov     edx, 89Ah
0x18004dd5e  jmp     short loc_18004DDB5
0x18004dd60  mov     rax, [r15]
0x18004dd63  mov     rcx, r15
0x18004dd66  mov     rax, [rax+30h]
0x18004dd6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd6f  mov     ebx, eax
0x18004dd71  mov     rcx, [r15]
0x18004dd74  mov     rax, [rcx+28h]
0x18004dd78  mov     rcx, r15
0x18004dd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd80  mov     r8d, eax
0x18004dd83  mov     rcx, [rsp+410h+var_3C8]
0x18004dd88  mov     rdx, [rcx]
0x18004dd8b  xor     r9d, r9d
0x18004dd8e  test    ebx, ebx
0x18004dd90  setnz   r9b
0x18004dd94  mov     rax, [rdx+70h]
0x18004dd98  mov     edx, r9d
0x18004dd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dda0  mov     ebx, eax
0x18004dda2  mov     rcx, [rbp+318h]; this
0x18004dda9  test    eax, eax
0x18004ddab  jns     short loc_18004DDBD
0x18004ddad  mov     r9d, eax; char *
0x18004ddb0  mov     edx, 8A0h; void *
0x18004ddb5  mov     r8, rsi; unsigned int
0x18004ddb8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ddbd  mov     rax, [r15]
0x18004ddc0  mov     rcx, r15
0x18004ddc3  mov     rax, [rax+10h]
0x18004ddc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddcc  jmp     loc_18004E1EB
0x18004ddd1  mov     rcx, [r14+850h]
0x18004ddd8  mov     rax, [rcx]
0x18004dddb  lea     rdx, [rsp+410h+var_3B8]
0x18004dde0  mov     rax, [rax+1B0h]
0x18004dde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddec  test    eax, eax
0x18004ddee  js      loc_18004DF4E
0x18004ddf4  cmp     [rsp+410h+var_3B8], 0
0x18004ddf9  jz      loc_18004DF4E
0x18004ddff  mov     rdx, [rsp+410h+var_3C8]; struct IDesktopWallpaperPrivate *
0x18004de04  mov     rcx, r14; this
0x18004de07  call    ?_LoadPerMonitorData@CThemeManager2@@AEAAXPEAUIDesktopWallpaperPrivate@@@Z; CThemeManager2::_LoadPerMonitorData(IDesktopWallpaperPrivate *)
0x18004de0c  xor     r15d, r15d
0x18004de0f  lea     rsi, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004de16  cmp     r15d, [r14+8B0h]
0x18004de1d  jnb     loc_18004E1EF
0x18004de23  mov     [rsp+410h+pv], 0
0x18004de2c  mov     rcx, [r14+850h]
0x18004de33  lea     edx, [r15+1]
0x18004de37  mov     [rsp+410h+var_3C0], edx
0x18004de3b  mov     rax, [rcx]
0x18004de3e  lea     r8, [rsp+410h+pv]
0x18004de43  mov     rax, [rax+1C0h]
0x18004de4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de4f  mov     r12d, eax
0x18004de52  mov     rcx, [rsp+410h+var_3C8]
0x18004de57  mov     rdx, [rcx]
0x18004de5a  mov     rbx, [rdx+18h]
0x18004de5e  test    eax, eax
0x18004de60  js      short loc_18004DE77
0x18004de62  lea     rdx, [rsp+410h+pv]; struct ATL::CComBSTR *
0x18004de67  lea     rcx, [rsp+410h+var_3B0]; this
0x18004de6c  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x18004de71  nop
0x18004de72  or      edi, 1
0x18004de75  jmp     short loc_18004DE8C
0x18004de77  lea     rdx, Default; unsigned __int16 *
0x18004de7e  lea     rcx, [rsp+410h+bstrString]; this
0x18004de83  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18004de88  nop
0x18004de89  or      edi, 2
0x18004de8c  mov     [rsp+410h+var_3D0], edi
0x18004de90  mov     edx, r15d
0x18004de93  mov     r8, [rax]
0x18004de96  mov     rdx, [r14+rdx*8+8B8h]
0x18004de9e  mov     rcx, [rsp+410h+var_3C8]
0x18004dea3  mov     rax, rbx
0x18004dea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004deab  mov     ebx, eax
0x18004dead  test    dil, 2
0x18004deb1  jz      short loc_18004DEC6
0x18004deb3  and     edi, 0FFFFFFFDh
0x18004deb6  mov     [rsp+410h+var_3D0], edi
0x18004deba  mov     rcx, [rsp+410h+bstrString]; bstrString
0x18004debf  call    cs:__imp_SysFreeString
0x18004dec5  nop
0x18004dec6  test    dil, 1
  ... truncated ...
```
