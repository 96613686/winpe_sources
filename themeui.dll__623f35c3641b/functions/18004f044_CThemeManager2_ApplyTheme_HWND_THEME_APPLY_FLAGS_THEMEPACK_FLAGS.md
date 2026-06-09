# CThemeManager2::_ApplyTheme(HWND__ *,THEME_APPLY_FLAGS,THEMEPACK_FLAGS)

- ea: `0x18004f044`
- end: `0x18004fb25`
- name: `?_ApplyTheme@CThemeManager2@@AEAAJPEAUHWND__@@W4THEME_APPLY_FLAGS@@W4THEMEPACK_FLAGS@@@Z`
- size: `2785`
- prototype: ``
- caller_count: `1`
- callee_count: `52`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180054e80`

## callees

- `0x180008a50`
- `0x18000c598`
- `0x18000cc2c`
- `0x1800104c0`
- `0x180014e40`
- `0x18001a930`
- `0x18001acc4`
- `0x18001b43c`
- `0x18001d4b4`
- `0x18001ea1c`
- `0x18001ed40`
- `0x18001fd98`
- `0x1800207b0`
- `0x180020908`
- `0x180021134`
- `0x180022110`
- `0x180022cdc`
- `0x180029324`
- `0x180030294`
- `0x180030bb4`
- `0x180030dac`
- `0x180030e2c`
- `0x180031ee0`
- `0x1800335c8`
- `0x180033cf0`
- `0x180034e50`
- `0x1800358c0`
- `0x18003c1f4`
- `0x18003cf08`
- `0x18003cff0`
- `0x18003d480`
- `0x180042664`
- `0x1800427dc`
- `0x18004a490`
- `0x18004aa8c`
- `0x18004aafc`
- `0x18004ba84`
- `0x18004c994`
- `0x18004ca20`
- `0x18004caac`
- `0x18004cc7c`
- `0x18004cd80`
- `0x18004d7ec`
- `0x18004d904`
- `0x18004d9f0`
- `0x18004eb1c`
- `0x18004f044`
- `0x18004fb2c`
- `0x180050380`
- `0x1800510bc`

## import_xrefs

- `USER32!SetCursor` at `0x18004f29b`
- `USER32!SetCursor` at `0x18004f9fb`
- `USER32!SetCursor` at `0x18004f29b`
- `USER32!SetCursor` at `0x18004f9fb`
- `USER32!LoadCursorW` at `0x18004f292`
- `USER32!LoadCursorW` at `0x18004f292`
- `UxTheme!__imp_QueryThemeServices` at `0x18004f391`
- `UxTheme!__imp_QueryThemeServices` at `0x18004f391`
- `OLEAUT32!__imp_SysFreeString` at `0x18004faef`
- `OLEAUT32!__imp_SysFreeString` at `0x18004faef`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f22d`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f22d`
- `WINMM!PlaySoundW` at `0x18004f1f7`
- `WINMM!PlaySoundW` at `0x18004f244`
- `WINMM!PlaySoundW` at `0x18004f1f7`
- `WINMM!PlaySoundW` at `0x18004f244`

## string_xrefs

- `0x18004f3e6`: `InstallTheme`
- `0x18004fa1b`: `Software\Microsoft\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThemeManager2::_ApplyTheme(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  unsigned int v5; // esi
  struct ITheme **v8; // r12
  char v9; // r13
  const wchar_t *v10; // r9
  unsigned int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  __int64 v14; // rcx
  HCURSOR CursorW; // rax
  int *v16; // rdx
  const wchar_t *v17; // r9
  int v18; // eax
  int updated; // edi
  __int64 v20; // r9
  int Path; // eax
  unsigned int v22; // edx
  struct ITheme *v23; // r15
  int Instance; // eax
  int v25; // ebx
  int v26; // eax
  int v27; // eax
  int v28; // ebx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // r15d
  __int64 v33; // rcx
  unsigned int v34; // r9d
  struct ITheme *v35; // rdi
  __int64 (__fastcall *v36)(struct ITheme *, GUID *, unsigned int *); // rbx
  int v37; // eax
  CThemeManager2 *v38; // rcx
  __int64 v39; // rdx
  int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  CThemeManager2 *v44; // rcx
  CThemeManager2 *v45; // rcx
  int v46; // eax
  int v47; // eax
  _QWORD *v48; // rcx
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // ecx
  unsigned int v53; // edi
  int v54; // r8d
  HCURSOR v55; // rbx
  unsigned int v57; // [rsp+20h] [rbp-E0h]
  char v58; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v59[3]; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v60; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v61[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v62; // [rsp+40h] [rbp-C0h] BYREF
  int v63; // [rsp+44h] [rbp-BCh]
  BSTR pbstr; // [rsp+48h] [rbp-B8h] BYREF
  int v65; // [rsp+50h] [rbp-B0h]
  _BYTE v66[336]; // [rsp+60h] [rbp-A0h] BYREF
  HCURSOR hCursor[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v63 = a4;
  v5 = a3;
  v8 = (struct ITheme **)(a1 + 2128);
  anonymous_namespace_::StartTelemetry(
    (struct wil::details::IFailureCallback *)v66,
    *(struct ITheme **)(a1 + 2120),
    *(struct ITheme **)(a1 + 2128),
    *(_BYTE *)(a1 + 2145),
    a3,
    a4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
  NotifyThemeCPLs(3);
  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v10 = L"is";
    if ( !*(_BYTE *)(a1 + 2145) )
      v10 = L"is not";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v10);
  }
  v11 = a4 | 4;
  if ( !*(_BYTE *)(a1 + 2145) )
    v11 = a4;
  v58 = 0;
  if ( (unsigned int)CSlideshowSettings::s_PolicyAllowsSlideshow()
    || (unsigned int)CThemeManager2::s_PromptToSubscribeToRSSIfNeeded(a2, *v8, v11, &v58) )
  {
    ThemesTelemetry::ThemeApply::SlideshowDisabled((ThemesTelemetry::ThemeApply *)v66);
    v58 = 0;
    v12 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
  }
  if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v12, (unsigned int)ApplyTheme_Start, v13, 1, (__int64)hCursor);
  pbstr = 0;
  if ( (a4 & 4) == 0 && !*(_BYTE *)(a1 + 2145) )
  {
    if ( PlaySoundW(0, 0, 0x200003u) )
    {
      if ( (*(int (__fastcall **)(struct ITheme *, const wchar_t *, __int64, BSTR *))(*(_QWORD *)*v8 + 336LL))(
             *v8,
             L"AppEvents\\Schemes\\Apps\\.Default\\ChangeTheme",
             0xFFFFFFFFLL,
             &pbstr) >= 0 )
      {
        if ( SysStringLen(pbstr) )
        {
          if ( PlaySoundW(pbstr, 0, 0x220003u) )
          {
            ThemesTelemetry::ThemeApply::ThemeApplySoundPlayed((ThemesTelemetry::ThemeApply *)v66);
            if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
              McTemplateU0z_EtwEventWriteTransfer(v14, PlayThemeApplySound_Info, pbstr);
          }
        }
      }
    }
  }
  hCursor[0] = 0;
  v65 = a4 & 3;
  if ( (a4 & 3) == 0 && (v5 & 0x100) == 0 )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    hCursor[0] = SetCursor(CursorW);
  }
  *(_BYTE *)(a1 + 2146) = IsUserHighContrastUser();
  ThemesTelemetry::ThemeApply::PreApplyHighContrastState<bool &>(v66, a1 + 2146);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v17 = L"on";
    if ( !*(_BYTE *)(a1 + 2146) )
      v17 = L"off";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v17);
  }
  v61[0] = 0;
  if ( (unsigned int)GetDwmColorizationColor(v61, v16) == 1 )
  {
    v9 = 1;
    v5 &= ~8u;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
    ThemesTelemetry::ThemeApply::ForceDWMColorization((ThemesTelemetry::ThemeApply *)v66);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v61[0]);
  }
  v59[0] = 0;
  if ( (QueryThemeServices() & 1) != 0 )
  {
    v18 = CThemeManager2::_ApplyVisualStyle(a1, v5, a4, v59);
    updated = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply visual style.", v18, -2147023834);
    if ( updated < 0 )
    {
      Path = 0;
      if ( !*(_WORD *)(a1 + 1052) )
      {
        Path = HrRegGetPath(
                 HKEY_CURRENT_USER,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                 L"InstallTheme",
                 (unsigned __int16 *)(a1 + 1052),
                 v57);
        if ( Path < 0 )
          Path = GetSystemDefaultTheme((unsigned __int16 *)(a1 + 1052), v22);
      }
      if ( Path >= 0 )
      {
        if ( *(_WORD *)(a1 + 1052) )
        {
          v23 = *v8;
          Instance = CThemeFile_CreateInstance((const unsigned __int16 *)(a1 + 1052), v8);
          if ( Instance >= 0 )
          {
            v25 = CThemeManager2::_ApplyVisualStyle(a1, v5, v63, v59);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                45,
                WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                (unsigned int)v25);
            if ( v25 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5BD,
                (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
                (const char *)(unsigned int)v25,
                v57);
            (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)*v8 + 16LL))(*v8);
            v26 = 0;
            if ( v25 < 0 )
              v26 = updated;
            updated = v26;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5B8,
              (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
              (const char *)(unsigned int)Instance,
              v57);
          }
          *v8 = v23;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5B3,
          (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
          (const char *)(unsigned int)Path,
          v57);
      }
    }
  }
  else
  {
    updated = -2147023834;
    ThemesTelemetry::ThemeApply::ThemesServiceDisabled((ThemesTelemetry::ThemeApply *)v66);
  }
  LOBYTE(v20) = v9 | v59[0];
  v27 = CThemeManager2::_ApplyGlassColor(a1, v5, v61[0], v20);
  v28 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply glass color.", v27, updated);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl);
  v29 = CThemeManager2::_ApplyColorModes((CThemeManager2 *)a1, *(_BYTE *)(a1 + 2362));
  v32 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply immersive color modes.", v29, v28);
  if ( *(_BYTE *)(a1 + 2145) )
  {
    v60 = 0;
    v61[0] = 0;
    v62 = 0;
    v33 = *(_QWORD *)(a1 + 2120);
    if ( v33
      && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 264LL))(v33, &v60) >= 0
      && v60
      && *v8
      && (*(int (__fastcall **)(struct ITheme *, unsigned int *))(*(_QWORD *)*v8 + 264LL))(*v8, v61) >= 0
      && v61[0] )
    {
      LOBYTE(v30) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorThemeFSIARestore>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorThemeFSIARestore>::GetImpl'::`2'::impl,
        v30);
      if ( (v5 & 1) != 0 )
      {
        if ( (int)SHRegGetBOOLWithREGSAM(
                    HKEY_CURRENT_USER,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                    L"ExecutingInFSIARestore",
                    v34,
                    &v62) >= 0
          && v62 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
          LOWORD(v5) = v5 & 0xFFFE;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v5);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v57 = v61[0];
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v60);
    }
  }
  LOBYTE(v30) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::GetImpl'::`2'::impl,
    v30);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl'::`2'::impl) )
  {
    v62 = 0;
    *(_QWORD *)v61 = 0;
    v35 = *v8;
    v36 = **(__int64 (__fastcall ***)(struct ITheme *, GUID *, unsigned int *))*v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v61);
    v37 = v36(v35, &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a, v61);
    if ( v37 >= 0 )
    {
      if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)v61 + 32LL))(*(_QWORD *)v61, &v62) >= 0 )
      {
        if ( v62 == 1 )
        {
          v40 = CThemeManager2::_ApplyDesktopSpotlight(v38);
          v60 = v40;
          if ( v40 < 0 )
          {
            LOBYTE(v39) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
              v39);
            if ( *(_BYTE *)(a1 + 2145) )
            {
              SHRegSetDWORD(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
                L"EnabledState",
                1u);
              LOWORD(v5) = v5 | 1;
              v60 = 1;
            }
            else
            {
              LOBYTE(v42) = 3;
              LOBYTE(v41) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
                v41,
                v42);
              LOBYTE(v43) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::GetImpl'::`2'::impl,
                v43);
              CThemeManager2::_DisableDesktopSpotlight(v44);
              v32 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply desktop spotlight", v40, v32);
            }
          }
          else
          {
            LOWORD(v5) = v5 | 1;
          }
          ThemesTelemetry::DesktopSpotlightThemeEnabled<long &>(&v60);
        }
        else
        {
          v45 = (CThemeManager2 *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
          CThemeManager2::_DisableDesktopSpotlight(v45);
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x623,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)(unsigned int)v37,
        v57);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v61);
  }
  if ( (v5 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
  }
  else
  {
    v46 = CThemeManager2::_ApplyDesktopBackground(a1, v58, v63);
    v32 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply desktop background.", v46, v32);
  }
  SafeRelease<CDimmedWindow>(a1 + 2136);
  if ( (v5 & 0x10) == 0 )
  {
    v47 = CThemeManager2::_ApplySounds((CThemeManager2 *)a1);
    v32 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply sounds.", v47, v32);
LABEL_111:
    v48 = WPP_GLOBAL_Control;
    goto LABEL_112;
  }
  v48 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
    goto LABEL_111;
  }
LABEL_112:
  if ( (v5 & 4) == 0 )
  {
    v49 = CThemeManager2::_ApplyDesktopIcons((CThemeManager2 *)a1);
    v32 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply desktop icons.", v49, v32);
LABEL_117:
    v48 = WPP_GLOBAL_Control;
    goto LABEL_118;
  }
  if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 8) != 0 )
  {
    WPP_SF_(v48[2], 53, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
    goto LABEL_117;
  }
LABEL_118:
  if ( (v5 & 2) != 0 )
  {
    if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 8) != 0 )
      WPP_SF_(v48[2], 54, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
  }
  else
  {
    v50 = CThemeManager2::_ApplyMousePointers((CThemeManager2 *)a1);
    v32 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply mouse pointers.", v50, v32);
  }
  v51 = CThemeManager2::_ApplyLogonBackgroundFlag((CThemeManager2 *)a1);
  v53 = CThemeManager2::s_UpdateResultOrLogFailure(L"Failed to apply logon background flag.", v51, v32);
  if ( !v65 && (v5 & 0x100) == 0 )
    SetCursor(hCursor[0]);
  if ( *(_BYTE *)(a1 + 2145) )
  {
    v60 = 0;
    if ( (int)SHRegGetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Accessibility", L"TextScaleFactor", &v60) >= 0
      && v60 - 101 <= 0x7C )
    {
      Microsoft::WRL::Details::Make<Win32TextScale,>(hCursor);
      v55 = hCursor[0];
      if ( hCursor[0] )
        Win32TextScale::ApplyWin32TextScale((Win32TextScale *)(hCursor[0] + 8), (double)(int)v60 / 100.0);
      if ( v55 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::FtmBase,IWin32TextScale>::Release(v55);
    }
  }
  if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v52, (unsigned int)ApplyTheme_Stop, v54, 1, (__int64)hCursor);
  NotifyThemeCPLs(4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids, v53);
  wil::ActivityBase<ThemesLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v66, v53);
  SysFreeString(pbstr);
  ThemesTelemetry::ThemeApply::~ThemeApply((ThemesTelemetry::ThemeApply *)v66);
  return v53;
}

```

## disassembly

```asm
0x18004f044  push    rbp
0x18004f046  push    rbx
0x18004f047  push    rsi
0x18004f048  push    rdi
0x18004f049  push    r12
0x18004f04b  push    r13
0x18004f04d  push    r14
0x18004f04f  push    r15
0x18004f051  lea     rbp, [rsp-0D8h]
0x18004f059  sub     rsp, 1D8h
0x18004f060  mov     rax, cs:__security_cookie
0x18004f067  xor     rax, rsp
0x18004f06a  mov     [rbp+110h+var_50], rax
0x18004f071  mov     r15d, r9d
0x18004f074  mov     [rsp+210h+var_1CC], r9d
0x18004f079  mov     esi, r8d
0x18004f07c  mov     rdi, rdx
0x18004f07f  mov     r14, rcx
0x18004f082  lea     r12, [rcx+850h]
0x18004f089  mov     [rsp+210h+var_1E8], r9d; unsigned int
0x18004f08e  mov     dword ptr [rsp+210h+var_1F0], r8d; unsigned int
0x18004f093  mov     r9b, [rcx+861h]; bool
0x18004f09a  mov     r8, [r12]; struct ITheme *
0x18004f09e  mov     rdx, [rcx+848h]; struct ITheme *
0x18004f0a5  lea     rcx, [rsp+210h+var_1B0]; struct wil::details::IFailureCallback *
0x18004f0aa  call    _anonymous_namespace___StartTelemetry
0x18004f0af  nop
0x18004f0b0  lea     rbx, WPP_GLOBAL_Control
0x18004f0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0be  cmp     rcx, rbx
0x18004f0c1  jz      short loc_18004F0DE
0x18004f0c3  test    byte ptr [rcx+1Ch], 8
0x18004f0c7  jz      short loc_18004F0DE
0x18004f0c9  mov     edx, 27h ; '''
0x18004f0ce  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f0d5  mov     rcx, [rcx+10h]
0x18004f0d9  call    WPP_SF_
0x18004f0de  mov     ecx, 3; lParam
0x18004f0e3  call    ?NotifyThemeCPLs@@YAX_J@Z; NotifyThemeCPLs(__int64)
0x18004f0e8  xor     r13d, r13d
0x18004f0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0f2  cmp     rcx, rbx
0x18004f0f5  jz      short loc_18004F12A
0x18004f0f7  test    byte ptr [rcx+1Ch], 8
0x18004f0fb  jz      short loc_18004F12A
0x18004f0fd  lea     rax, aIsNot; "is not"
0x18004f104  lea     r9, aIs; "is"
0x18004f10b  cmp     [r14+861h], r13b
0x18004f112  cmovz   r9, rax
0x18004f116  lea     edx, [r13+28h]
0x18004f11a  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f121  mov     rcx, [rcx+10h]
0x18004f125  call    WPP_SF_S
0x18004f12a  mov     ebx, r15d
0x18004f12d  or      ebx, 4
0x18004f130  cmp     [r14+861h], r13b
0x18004f137  cmovz   ebx, r15d
0x18004f13b  mov     [rsp+210h+var_1E0], r13b
0x18004f140  call    ?s_PolicyAllowsSlideshow@CSlideshowSettings@@SAJXZ; CSlideshowSettings::s_PolicyAllowsSlideshow(void)
0x18004f145  test    eax, eax
0x18004f147  jnz     short loc_18004F16B
0x18004f149  lea     r9, [rsp+210h+var_1E0]
0x18004f14e  mov     r8d, ebx
0x18004f151  mov     rdx, [r12]
0x18004f155  mov     rcx, rdi
0x18004f158  call    ?s_PromptToSubscribeToRSSIfNeeded@CThemeManager2@@CAJPEAUHWND__@@PEAUITheme@@W4THEMEPACK_FLAGS@@PEA_N@Z; CThemeManager2::s_PromptToSubscribeToRSSIfNeeded(HWND__ *,ITheme *,THEMEPACK_FLAGS,bool *)
0x18004f15d  test    eax, eax
0x18004f15f  jnz     short loc_18004F16B
0x18004f161  mov     al, [rsp+210h+var_1E0]
0x18004f165  mov     [rsp+210h+var_1E0], al
0x18004f169  jmp     short loc_18004F1A8
0x18004f16b  lea     rcx, [rsp+210h+var_1B0]; this
0x18004f170  call    ?SlideshowDisabled@ThemeApply@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::ThemeApply::SlideshowDisabled(void)
0x18004f175  mov     [rsp+210h+var_1E0], r13b
0x18004f17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f181  lea     rax, WPP_GLOBAL_Control
0x18004f188  cmp     rcx, rax
0x18004f18b  jz      short loc_18004F1A8
0x18004f18d  test    byte ptr [rcx+1Ch], 8
0x18004f191  jz      short loc_18004F1A8
0x18004f193  mov     edx, 29h ; ')'
0x18004f198  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f19f  mov     rcx, [rcx+10h]
0x18004f1a3  call    WPP_SF_
0x18004f1a8  mov     edi, 1
0x18004f1ad  test    cs:Microsoft_Windows_ThemeUIEnableBits, dil
0x18004f1b4  jz      short loc_18004F1D1
0x18004f1b6  lea     rax, [rbp+110h+hCursor]
0x18004f1bd  mov     [rsp+210h+var_1F0], rax; int
0x18004f1c2  mov     r9d, edi
0x18004f1c5  lea     rdx, ApplyTheme_Start
0x18004f1cc  call    McGenEventWrite_EtwEventWriteTransfer
0x18004f1d1  mov     [rsp+210h+pbstr], r13
0x18004f1d6  test    r15b, 4
0x18004f1da  jnz     loc_18004F272
0x18004f1e0  cmp     [r14+861h], r13b
0x18004f1e7  jnz     loc_18004F272
0x18004f1ed  xor     edx, edx; hmod
0x18004f1ef  xor     ecx, ecx; pszSound
0x18004f1f1  mov     r8d, 200003h; fdwSound
0x18004f1f7  call    cs:__imp_PlaySoundW
0x18004f1fd  test    eax, eax
0x18004f1ff  jz      short loc_18004F272
0x18004f201  mov     rcx, [r12]
0x18004f205  mov     rax, [rcx]
0x18004f208  lea     r9, [rsp+210h+pbstr]
0x18004f20d  or      r8d, 0FFFFFFFFh
0x18004f211  lea     rdx, aAppeventsSchem_27; "AppEvents\\Schemes\\Apps\\.Default\\Cha"...
0x18004f218  mov     rax, [rax+150h]
0x18004f21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f224  test    eax, eax
0x18004f226  js      short loc_18004F272
0x18004f228  mov     rcx, [rsp+210h+pbstr]; pbstr
0x18004f22d  call    cs:__imp_SysStringLen
0x18004f233  test    eax, eax
0x18004f235  jz      short loc_18004F272
0x18004f237  xor     edx, edx; hmod
0x18004f239  mov     r8d, 220003h; fdwSound
0x18004f23f  mov     rcx, [rsp+210h+pbstr]; pszSound
0x18004f244  call    cs:__imp_PlaySoundW
0x18004f24a  test    eax, eax
0x18004f24c  jz      short loc_18004F272
0x18004f24e  lea     rcx, [rsp+210h+var_1B0]; this
0x18004f253  call    ?ThemeApplySoundPlayed@ThemeApply@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::ThemeApply::ThemeApplySoundPlayed(void)
0x18004f258  test    cs:Microsoft_Windows_ThemeUIEnableBits, dil
0x18004f25f  jz      short loc_18004F272
0x18004f261  mov     r8, [rsp+210h+pbstr]
0x18004f266  lea     rdx, PlayThemeApplySound_Info
0x18004f26d  call    McTemplateU0z_EtwEventWriteTransfer
0x18004f272  mov     [rbp+110h+hCursor], r13
0x18004f279  mov     eax, r15d
0x18004f27c  and     eax, 3
0x18004f27f  mov     [rsp+210h+var_1C0], eax
0x18004f283  jnz     short loc_18004F2A8
0x18004f285  bt      esi, 8
0x18004f289  jb      short loc_18004F2A8
0x18004f28b  mov     edx, 7F02h; lpCursorName
0x18004f290  xor     ecx, ecx; hInstance
0x18004f292  call    cs:__imp_LoadCursorW
0x18004f298  mov     rcx, rax; hCursor
0x18004f29b  call    cs:__imp_SetCursor
0x18004f2a1  mov     [rbp+110h+hCursor], rax
0x18004f2a8  lea     rbx, [r14+862h]
0x18004f2af  call    ?IsUserHighContrastUser@@YA_NXZ; IsUserHighContrastUser(void)
0x18004f2b4  mov     [rbx], al
0x18004f2b6  mov     rdx, rbx
0x18004f2b9  lea     rcx, [rsp+210h+var_1B0]
0x18004f2be  call    ??$PreApplyHighContrastState@AEA_N@ThemeApply@ThemesTelemetry@@QEAAXAEA_N@Z; ThemesTelemetry::ThemeApply::PreApplyHighContrastState<bool &>(bool &)
0x18004f2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f2ca  lea     rax, WPP_GLOBAL_Control
0x18004f2d1  cmp     rcx, rax
0x18004f2d4  jz      short loc_18004F306
0x18004f2d6  test    byte ptr [rcx+1Ch], 8
0x18004f2da  jz      short loc_18004F306
0x18004f2dc  lea     rax, aOff; "off"
0x18004f2e3  lea     r9, aOn; "on"
0x18004f2ea  cmp     [rbx], r13b
0x18004f2ed  cmovz   r9, rax
0x18004f2f1  mov     edx, 2Ah ; '*'
0x18004f2f6  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f2fd  mov     rcx, [rcx+10h]
0x18004f301  call    WPP_SF_S
0x18004f306  mov     [rsp+210h+var_1D8], r13d
0x18004f30b  lea     rcx, [rsp+210h+var_1D8]; unsigned int *
0x18004f310  call    ?GetDwmColorizationColor@@YAJPEAKPEAH@Z; GetDwmColorizationColor(ulong *,int *)
0x18004f315  cmp     eax, edi
0x18004f317  jnz     short loc_18004F359
0x18004f319  mov     r13b, dil
0x18004f31c  and     esi, 0FFFFFFF7h
0x18004f31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f326  lea     rax, WPP_GLOBAL_Control
0x18004f32d  cmp     rcx, rax
0x18004f330  jz      short loc_18004F34D
0x18004f332  test    byte ptr [rcx+1Ch], 8
0x18004f336  jz      short loc_18004F34D
0x18004f338  mov     edx, 2Bh ; '+'
0x18004f33d  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f344  mov     rcx, [rcx+10h]
0x18004f348  call    WPP_SF_
0x18004f34d  lea     rcx, [rsp+210h+var_1B0]; this
0x18004f352  call    ?ForceDWMColorization@ThemeApply@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::ThemeApply::ForceDWMColorization(void)
0x18004f357  jmp     short loc_18004F38C
0x18004f359  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f360  lea     rax, WPP_GLOBAL_Control
0x18004f367  cmp     rcx, rax
0x18004f36a  jz      short loc_18004F38C
0x18004f36c  test    byte ptr [rcx+1Ch], 8
0x18004f370  jz      short loc_18004F38C
0x18004f372  mov     edx, 2Ch ; ','
0x18004f377  mov     r9d, [rsp+210h+var_1D8]
0x18004f37c  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f383  mov     rcx, [rcx+10h]
0x18004f387  call    WPP_SF_d
0x18004f38c  mov     [rsp+210h+var_1DF], 0
0x18004f391  call    cs:__imp_QueryThemeServices
0x18004f397  test    dil, al
0x18004f39a  jz      loc_18004F4F4
0x18004f3a0  lea     r9, [rsp+210h+var_1DF]
0x18004f3a5  mov     r8d, r15d
0x18004f3a8  mov     edx, esi
0x18004f3aa  mov     rcx, r14
0x18004f3ad  call    ?_ApplyVisualStyle@CThemeManager2@@AEAAJW4THEME_APPLY_FLAGS@@W4THEMEPACK_FLAGS@@PEA_N@Z; CThemeManager2::_ApplyVisualStyle(THEME_APPLY_FLAGS,THEMEPACK_FLAGS,bool *)
0x18004f3b2  mov     edx, eax; int
0x18004f3b4  mov     r8d, 80070426h; int
0x18004f3ba  lea     rcx, aFailedToApplyV; "Failed to apply visual style."
0x18004f3c1  call    ?s_UpdateResultOrLogFailure@CThemeManager2@@CAJPEBGJJ@Z; CThemeManager2::s_UpdateResultOrLogFailure(ushort const *,long,long)
0x18004f3c6  mov     edi, eax
0x18004f3c8  xor     r15d, r15d
0x18004f3cb  test    eax, eax
0x18004f3cd  jns     loc_18004F503
0x18004f3d3  mov     eax, r15d
0x18004f3d6  lea     rbx, [r14+41Ch]
0x18004f3dd  cmp     [rbx], r15w
0x18004f3e1  jnz     short loc_18004F40C
0x18004f3e3  mov     r9, rbx; unsigned __int16 *
0x18004f3e6  lea     r8, aInstalltheme; "InstallTheme"
0x18004f3ed  lea     rdx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004f3f4  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18004f3fb  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x18004f400  test    eax, eax
0x18004f402  jns     short loc_18004F40C
0x18004f404  mov     rcx, rbx; unsigned __int16 *
0x18004f407  call    ?GetSystemDefaultTheme@@YAJPEAGK@Z; GetSystemDefaultTheme(ushort *,ulong)
0x18004f40c  mov     rcx, [rbp+118h]; this
0x18004f413  test    eax, eax
0x18004f415  jns     short loc_18004F430
0x18004f417  mov     r9d, eax; char *
0x18004f41a  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004f421  mov     edx, 5B3h; void *
0x18004f426  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004f42b  jmp     loc_18004F503
0x18004f430  cmp     [rbx], r15w
0x18004f434  jz      loc_18004F503
0x18004f43a  mov     r15, [r12]
0x18004f43e  mov     rdx, r12; struct ITheme **
0x18004f441  mov     rcx, rbx; unsigned __int16 *
0x18004f444  call    ?CThemeFile_CreateInstance@@YAJPEBGPEAPEAUITheme@@@Z; CThemeFile_CreateInstance(ushort const *,ITheme * *)
0x18004f449  mov     rcx, [rbp+118h]; this
0x18004f450  test    eax, eax
0x18004f452  jns     short loc_18004F46D
0x18004f454  mov     r9d, eax; char *
0x18004f457  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004f45e  mov     edx, 5B8h; void *
0x18004f463  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004f468  jmp     loc_18004F4EE
0x18004f46d  lea     r9, [rsp+210h+var_1DF]
0x18004f472  mov     r8d, [rsp+210h+var_1CC]
0x18004f477  mov     edx, esi
0x18004f479  mov     rcx, r14
0x18004f47c  call    ?_ApplyVisualStyle@CThemeManager2@@AEAAJW4THEME_APPLY_FLAGS@@W4THEMEPACK_FLAGS@@PEA_N@Z; CThemeManager2::_ApplyVisualStyle(THEME_APPLY_FLAGS,THEMEPACK_FLAGS,bool *)
0x18004f481  mov     ebx, eax
0x18004f483  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f48a  lea     rax, WPP_GLOBAL_Control
0x18004f491  cmp     rcx, rax
0x18004f494  jz      short loc_18004F4B4
0x18004f496  test    byte ptr [rcx+1Ch], 8
0x18004f49a  jz      short loc_18004F4B4
0x18004f49c  mov     edx, 2Dh ; '-'
0x18004f4a1  mov     r9d, ebx
0x18004f4a4  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x18004f4ab  mov     rcx, [rcx+10h]
0x18004f4af  call    WPP_SF_d
0x18004f4b4  mov     rcx, [rbp+118h]; this
0x18004f4bb  test    ebx, ebx
0x18004f4bd  jns     short loc_18004F4D3
0x18004f4bf  mov     r9d, ebx; char *
0x18004f4c2  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004f4c9  mov     edx, 5BDh; void *
0x18004f4ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004f4d3  mov     rcx, [r12]
0x18004f4d7  mov     rax, [rcx]
0x18004f4da  mov     rax, [rax+10h]
0x18004f4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4e3  xor     ecx, ecx
0x18004f4e5  mov     eax, ecx
0x18004f4e7  test    ebx, ebx
0x18004f4e9  cmovs   eax, edi
0x18004f4ec  mov     edi, eax
0x18004f4ee  mov     [r12], r15
0x18004f4f2  jmp     short loc_18004F503
0x18004f4f4  mov     edi, 80070426h
0x18004f4f9  lea     rcx, [rsp+210h+var_1B0]; this
0x18004f4fe  call    ?ThemesServiceDisabled@ThemeApply@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::ThemeApply::ThemesServiceDisabled(void)
0x18004f503  mov     r9b, [rsp+210h+var_1DF]
0x18004f508  or      r9b, r13b
0x18004f50b  mov     r8d, [rsp+210h+var_1D8]
0x18004f510  mov     edx, esi
0x18004f512  mov     rcx, r14
0x18004f515  call    ?_ApplyGlassColor@CThemeManager2@@AEAAJW4THEME_APPLY_FLAGS@@K_N@Z; CThemeManager2::_ApplyGlassColor(THEME_APPLY_FLAGS,ulong,bool)
0x18004f51a  mov     edx, eax; int
0x18004f51c  mov     r8d, edi; int
0x18004f51f  lea     rcx, aFailedToApplyG; "Failed to apply glass color."
0x18004f526  call    ?s_UpdateResultOrLogFailure@CThemeManager2@@CAJPEBGJJ@Z; CThemeManager2::s_UpdateResultOrLogFailure(ushort const *,long,long)
0x18004f52b  mov     ebx, eax
0x18004f52d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SystemLightTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme> `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl(void)'::`2'::impl
0x18004f534  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18004f539  mov     dl, [r14+93Ah]; bool
0x18004f540  mov     rcx, r14; this
0x18004f543  call    ?_ApplyColorModes@CThemeManager2@@AEAAJ_N@Z; CThemeManager2::_ApplyColorModes(bool)
0x18004f548  mov     edx, eax; int
  ... truncated ...
```
