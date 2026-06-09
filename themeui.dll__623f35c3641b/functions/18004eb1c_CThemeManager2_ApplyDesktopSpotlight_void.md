# CThemeManager2::_ApplyDesktopSpotlight(void)

- ea: `0x18004eb1c`
- end: `0x18004f03c`
- name: `?_ApplyDesktopSpotlight@CThemeManager2@@AEAAJXZ`
- size: `1312`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this)`
- caller_count: `2`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f044`
- `0x180054e80`

## callees

- `0x18000b644`
- `0x18000b9cc`
- `0x18000bb20`
- `0x18000c598`
- `0x18000dbcc`
- `0x18001ed40`
- `0x18002f8c0`
- `0x18002fed4`
- `0x180030bb4`
- `0x180031cb0`
- `0x180031cd8`
- `0x18003324c`
- `0x180033da8`
- `0x1800358c0`
- `0x1800406dc`
- `0x180042664`
- `0x18004b63c`
- `0x18004b964`
- `0x18004b9f0`
- `0x18004c070`
- `0x18004c0d0`
- `0x18004c854`
- `0x18004ca20`
- `0x18004caac`
- `0x18004ce6c`
- `0x18004d958`
- `0x18004eb1c`
- `0x180050380`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004eb9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004eb9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ef9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ef9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004efce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004efce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ef8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ef8d`

## string_xrefs

- `0x18004eca0`: `WindowsUdk.UI.Shell.DesktopSpotlight.DesktopSpotlightExtension`
- `0x18004ecc7`: `com.microsoft.windows.extension.desktopspotlight`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall CThemeManager2::_ApplyDesktopSpotlight(CThemeManager2 *this)
{
  HRESULT v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // ebx
  int v5; // esi
  void (__fastcall ***v7)(_QWORD, __int64 *, _QWORD *); // rcx
  unsigned int v8; // esi
  unsigned int active; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  const char *v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rdx
  CThemeManager2 *v19; // rcx
  int ppv; // [rsp+20h] [rbp-208h]
  int v21; // [rsp+30h] [rbp-1F8h]
  HKEY phkResult; // [rsp+38h] [rbp-1F0h] BYREF
  LPVOID v23; // [rsp+40h] [rbp-1E8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-1E0h] BYREF
  __int64 v25; // [rsp+50h] [rbp-1D8h] BYREF
  int v26; // [rsp+58h] [rbp-1D0h] BYREF
  void (__fastcall ***v27)(_QWORD, __int64 *, __int64 *); // [rsp+60h] [rbp-1C8h] BYREF
  const wchar_t *v28; // [rsp+68h] [rbp-1C0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-1B8h]
  int v30; // [rsp+80h] [rbp-1A8h] BYREF
  __int128 v31; // [rsp+88h] [rbp-1A0h]
  _BYTE v32[32]; // [rsp+A0h] [rbp-188h] BYREF
  _QWORD v33[42]; // [rsp+C0h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v33);
  v33[0] = &ThemesTelemetry::ApplyDesktopSpotlight::`vftable';
  ThemesTelemetry::ApplyDesktopSpotlight::StartActivity((ThemesTelemetry::ApplyDesktopSpotlight *)v33);
  v23 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v1 = CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_f7949936_6736_4411_8af8_00b292658bc0, &v23);
  v4 = v1;
  if ( v1 >= 0 )
  {
    v4 = 0;
    v21 = 0;
    LOBYTE(v3) = 3;
    LOBYTE(v2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
      v2,
      v3);
    winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings((winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings *)&phkResult);
    v5 = winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(&phkResult);
    if ( v5 == 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A2,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)0x80004005LL,
        ppv);
      winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&phkResult);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      ThemesTelemetry::ApplyDesktopSpotlight::~ApplyDesktopSpotlight((ThemesTelemetry::ApplyDesktopSpotlight *)v33);
      return 2147500037LL;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl'::`2'::impl)
      && v5 == 1 )
    {
      winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&phkResult);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      ThemesTelemetry::ApplyDesktopSpotlight::~ApplyDesktopSpotlight((ThemesTelemetry::ApplyDesktopSpotlight *)v33);
      return 0;
    }
    v26 = 1;
    winrt::impl::consume_WindowsUdk_System_UserProfile_IUserProfilePersonalizationSettings<winrt::WindowsUdk::System::UserProfile::IUserProfilePersonalizationSettings>::DesktopSpotlightStatus(
      &phkResult,
      &v26);
    v28 = L"WindowsUdk.UI.Shell.DesktopSpotlight.DesktopSpotlightExtension";
    *(_QWORD *)&v29 = 62;
    winrt::param::hstring::hstring(&v30, &v28);
    winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"com.microsoft.windows.extension.desktopspotlight");
    winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(
      (const struct winrt::param::hstring *)&v27,
      (const struct winrt::param::hstring *)v32);
    v7 = v27;
    if ( v27 )
    {
      v25 = 0;
      (**v27)(
        v27,
        winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtensionStatics>,
        &v25);
      if ( v25 )
      {
        winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtensionStatics<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtensionStatics>::GetDefault(
          &v25,
          &v24);
        if ( v24 )
        {
          v8 = winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(&v24);
          if ( v8 )
          {
            active = winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::ActiveWallpaperIndex(&v24);
            LODWORD(v28) = 0;
            v29 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 64LL))(v24, active < v8 ? active : 0);
            winrt::check_hresult(&v26, v10, &v28);
          }
          else
          {
            winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings((winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings *)&v28);
            v30 = 0;
            v31 = 0;
            v11 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)v28 + 80LL))(v28);
            winrt::check_hresult(&v26, v11, &v30);
            ThemesTelemetry::TraceLoggingInfo("_ApplyDesktopSpotlight - CDM Lite Setting Default Wallpaper");
            winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::RefreshAsync(
              &v24,
              &v26);
            winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&v26);
            winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&v28);
          }
        }
        else
        {
          v4 = -2147467259;
          v21 = -2147467259;
        }
        winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&v24);
      }
      else
      {
        v4 = -2147467259;
        v21 = -2147467259;
      }
      winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&v25);
      v7 = v27;
    }
    else
    {
      v4 = -2147467259;
      v21 = -2147467259;
    }
    if ( v7 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
    winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&phkResult);
    if ( v4 < 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl'::`2'::impl) )
      {
        try
        {
          winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings((winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings *)&v28);
          if ( (unsigned int)winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(&v28) == 1 )
          {
            v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, const wchar_t *))(*(_QWORD *)v23 + 200LL))(
                   v23,
                   0,
                   0,
                   L"1");
            v21 = v4;
          }
          winrt::Windows::Foundation::IAsyncAction::~IAsyncAction((winrt::Windows::Foundation::IAsyncAction *)&v28);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x4F6,
            (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
            v14);
          v4 = v21;
        }
      }
      else
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, const wchar_t *))(*(_QWORD *)v23 + 200LL))(
               v23,
               0,
               0,
               L"1");
      }
    }
    if ( v4 >= 0 )
    {
      LOBYTE(v13) = 3;
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
        v12,
        v13);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4FF,
        (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
        (const char *)(unsigned int)v4,
        ppv);
      LOBYTE(v15) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::GetImpl'::`2'::impl,
        v15);
      LOBYTE(v16) = 3;
      LOBYTE(v17) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
        v17,
        v16);
      LOBYTE(v18) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
        v18);
      CThemeManager2::_DisableDesktopSpotlight(v19);
      phkResult = 0;
      RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", 0, 2u, &phkResult);
      RegDeleteValueW(phkResult, L"Wallpaper");
      RegSetValueExW(phkResult, L"Wallpaper", 0, 1u, (const BYTE *)&Default, 0);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33, (unsigned int)v4);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x498,
      (unsigned int)"shell\\themes\\themeui\\themeapply.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  ThemesTelemetry::ApplyDesktopSpotlight::~ApplyDesktopSpotlight((ThemesTelemetry::ApplyDesktopSpotlight *)v33);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004eb1c  mov     [rsp+arg_0], rbx
0x18004eb21  push    rsi
0x18004eb22  sub     rsp, 220h
0x18004eb29  mov     rax, cs:__security_cookie
0x18004eb30  xor     rax, rsp
0x18004eb33  mov     [rsp+228h+var_18], rax
0x18004eb3b  lea     rdx, aApplydesktopsp_0; "ApplyDesktopSpotlight"
0x18004eb42  lea     rcx, [rsp+228h+var_168]; struct wil::details::IFailureCallback *
0x18004eb4a  call    ??0?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004eb4f  lea     rax, ??_7ApplyDesktopSpotlight@ThemesTelemetry@@6B@; const ThemesTelemetry::ApplyDesktopSpotlight::`vftable'
0x18004eb56  mov     [rsp+228h+var_168], rax
0x18004eb5e  lea     rcx, [rsp+228h+var_168]; this
0x18004eb66  call    ?StartActivity@ApplyDesktopSpotlight@ThemesTelemetry@@QEAAXXZ; ThemesTelemetry::ApplyDesktopSpotlight::StartActivity(void)
0x18004eb6b  nop
0x18004eb6c  mov     [rsp+228h+var_1E8], 0
0x18004eb75  lea     rcx, [rsp+228h+var_1E8]
0x18004eb7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004eb7f  lea     rax, [rsp+228h+var_1E8]
0x18004eb84  mov     [rsp+228h+ppv], rax; int
0x18004eb89  lea     r9, _GUID_f7949936_6736_4411_8af8_00b292658bc0; riid
0x18004eb90  xor     edx, edx; pUnkOuter
0x18004eb92  lea     r8d, [rdx+4]; dwClsContext
0x18004eb96  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x18004eb9d  call    cs:__imp_CoCreateInstance
0x18004eba3  mov     ebx, eax
0x18004eba5  test    eax, eax
0x18004eba7  jns     short loc_18004EBCA
0x18004eba9  mov     rcx, [rsp+228h]; this
0x18004ebb1  mov     r9d, eax; char *
0x18004ebb4  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004ebbb  mov     edx, 498h; void *
0x18004ebc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ebc5  jmp     loc_18004F001
0x18004ebca  xor     ebx, ebx
0x18004ebcc  mov     [rsp+228h+var_1F8], ebx
0x18004ebd0  mov     r8b, 3
0x18004ebd3  mov     dl, 1
0x18004ebd5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl(void)'::`2'::impl
0x18004ebdc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004ebe1  nop
0x18004ebe2  lea     rcx, [rsp+228h+phkResult]; this
0x18004ebe7  call    ??0UserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings(void)
0x18004ebec  nop
0x18004ebed  lea     rcx, [rsp+228h+phkResult]
0x18004ebf2  call    ?WallpaperCount@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension@UIDesktopSpotlightExtension@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(void)
0x18004ebf7  mov     esi, eax
0x18004ebf9  cmp     eax, 2
0x18004ebfc  jnz     short loc_18004EC4A
0x18004ebfe  mov     rcx, [rsp+228h]; this
0x18004ec06  mov     ebx, 80004005h
0x18004ec0b  mov     r9d, ebx; char *
0x18004ec0e  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004ec15  mov     edx, 4A2h; void *
0x18004ec1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec1f  nop
0x18004ec20  lea     rcx, [rsp+228h+phkResult]; this
0x18004ec25  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ec2a  nop
0x18004ec2b  lea     rcx, [rsp+228h+var_1E8]
0x18004ec30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ec35  nop
0x18004ec36  lea     rcx, [rsp+228h+var_168]; this
0x18004ec3e  call    ??1ApplyDesktopSpotlight@ThemesTelemetry@@QEAA@XZ; ThemesTelemetry::ApplyDesktopSpotlight::~ApplyDesktopSpotlight(void)
0x18004ec43  mov     eax, ebx
0x18004ec45  jmp     loc_18004F01B
0x18004ec4a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl(void)'::`2'::impl
0x18004ec51  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(void)
0x18004ec56  test    al, al
0x18004ec58  jnz     short loc_18004EC89
0x18004ec5a  cmp     esi, 1
0x18004ec5d  jnz     short loc_18004EC89
0x18004ec5f  lea     rcx, [rsp+228h+phkResult]; this
0x18004ec64  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ec69  nop
0x18004ec6a  lea     rcx, [rsp+228h+var_1E8]
0x18004ec6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ec74  nop
0x18004ec75  lea     rcx, [rsp+228h+var_168]; this
0x18004ec7d  call    ??1ApplyDesktopSpotlight@ThemesTelemetry@@QEAA@XZ; ThemesTelemetry::ApplyDesktopSpotlight::~ApplyDesktopSpotlight(void)
0x18004ec82  xor     eax, eax
0x18004ec84  jmp     loc_18004F01B
0x18004ec89  mov     [rsp+228h+var_1D0], 1
0x18004ec91  lea     rdx, [rsp+228h+var_1D0]
0x18004ec96  lea     rcx, [rsp+228h+phkResult]
0x18004ec9b  call    ?DesktopSpotlightStatus@?$consume_WindowsUdk_System_UserProfile_IUserProfilePersonalizationSettings@UIUserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBW40UserProfile@System@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_System_UserProfile_IUserProfilePersonalizationSettings<winrt::WindowsUdk::System::UserProfile::IUserProfilePersonalizationSettings>::DesktopSpotlightStatus(winrt::WindowsUdk::System::UserProfile::DesktopSpotlightStatus const &)
0x18004eca0  lea     rax, aWindowsudkUiSh; "WindowsUdk.UI.Shell.DesktopSpotlight.De"...
0x18004eca7  mov     [rsp+228h+var_1C0], rax
0x18004ecac  mov     qword ptr [rsp+228h+var_1B8], 3Eh ; '>'
0x18004ecb5  lea     rdx, [rsp+228h+var_1C0]
0x18004ecba  lea     rcx, [rsp+228h+var_1A8]
0x18004ecc2  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18004ecc7  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.extension.desktop"...
0x18004ecce  lea     rcx, [rsp+228h+var_188]; this
0x18004ecd6  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18004ecdb  lea     r8, [rsp+228h+var_1A8]
0x18004ece3  lea     rdx, [rsp+228h+var_188]; struct winrt::param::hstring *
0x18004eceb  lea     rcx, [rsp+228h+var_1C8]; struct winrt::param::hstring *
0x18004ecf0  call    ?GetFactory@ExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@0@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004ecf5  nop
0x18004ecf6  mov     rcx, [rsp+228h+var_1C8]
0x18004ecfb  test    rcx, rcx
0x18004ecfe  jz      loc_18004EE56
0x18004ed04  mov     [rsp+228h+var_1D8], 0
0x18004ed0d  mov     rax, [rcx]
0x18004ed10  lea     r8, [rsp+228h+var_1D8]
0x18004ed15  lea     rdx, ??$guid_v@UIDesktopSpotlightExtensionStatics@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtensionStatics>
0x18004ed1c  mov     rax, [rax]
0x18004ed1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed24  mov     rax, [rsp+228h+var_1D8]
0x18004ed29  mov     [rsp+228h+var_1D8], rax
0x18004ed2e  test    rax, rax
0x18004ed31  jz      loc_18004EE3C
0x18004ed37  lea     rdx, [rsp+228h+var_1E0]
0x18004ed3c  lea     rcx, [rsp+228h+var_1D8]
0x18004ed41  call    ?GetDefault@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtensionStatics@UIDesktopSpotlightExtensionStatics@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtensionStatics<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtensionStatics>::GetDefault(void)
0x18004ed46  nop
0x18004ed47  cmp     [rsp+228h+var_1E0], 0
0x18004ed4d  jz      loc_18004EE27
0x18004ed53  lea     rcx, [rsp+228h+var_1E0]
0x18004ed58  call    ?WallpaperCount@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension@UIDesktopSpotlightExtension@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(void)
0x18004ed5d  mov     esi, eax
0x18004ed5f  test    eax, eax
0x18004ed61  jz      short loc_18004EDAE
0x18004ed63  lea     rcx, [rsp+228h+var_1E0]
0x18004ed68  call    ?ActiveWallpaperIndex@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension@UIDesktopSpotlightExtension@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::ActiveWallpaperIndex(void)
0x18004ed6d  mov     r8, [rsp+228h+var_1E0]
0x18004ed72  mov     dword ptr [rsp+228h+var_1C0], 0
0x18004ed7a  xorps   xmm0, xmm0
0x18004ed7d  movdqu  [rsp+228h+var_1B8], xmm0
0x18004ed83  mov     rcx, [r8]
0x18004ed86  cmp     eax, esi
0x18004ed88  sbb     edx, edx
0x18004ed8a  and     edx, eax
0x18004ed8c  mov     rax, [rcx+40h]
0x18004ed90  mov     rcx, r8
0x18004ed93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed98  lea     r8, [rsp+228h+var_1C0]
0x18004ed9d  mov     edx, eax
0x18004ed9f  lea     rcx, [rsp+228h+var_1D0]
0x18004eda4  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004eda9  jmp     loc_18004EE30
0x18004edae  lea     rcx, [rsp+228h+var_1C0]; this
0x18004edb3  call    ??0UserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings(void)
0x18004edb8  nop
0x18004edb9  mov     rcx, [rsp+228h+var_1C0]
0x18004edbe  mov     [rsp+228h+var_1A8], 0
0x18004edc9  xorps   xmm0, xmm0
0x18004edcc  movdqu  [rsp+228h+var_1A0], xmm0
0x18004edd5  mov     rax, [rcx]
0x18004edd8  mov     rax, [rax+50h]
0x18004eddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ede1  lea     r8, [rsp+228h+var_1A8]
0x18004ede9  mov     edx, eax
0x18004edeb  lea     rcx, [rsp+228h+var_1D0]
0x18004edf0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004edf5  lea     rcx, aApplydesktopsp; "_ApplyDesktopSpotlight - CDM Lite Setti"...
0x18004edfc  call    ?TraceLoggingInfo@ThemesTelemetry@@SAXPEBDZZ; ThemesTelemetry::TraceLoggingInfo(char const *,...)
0x18004ee01  lea     rdx, [rsp+228h+var_1D0]
0x18004ee06  lea     rcx, [rsp+228h+var_1E0]
0x18004ee0b  call    ?RefreshAsync@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension@UIDesktopSpotlightExtension@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::RefreshAsync(void)
0x18004ee10  lea     rcx, [rsp+228h+var_1D0]; this
0x18004ee15  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ee1a  nop
0x18004ee1b  lea     rcx, [rsp+228h+var_1C0]; this
0x18004ee20  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ee25  jmp     short loc_18004EE30
0x18004ee27  mov     ebx, 80004005h
0x18004ee2c  mov     [rsp+228h+var_1F8], ebx
0x18004ee30  lea     rcx, [rsp+228h+var_1E0]; this
0x18004ee35  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ee3a  jmp     short loc_18004EE45
0x18004ee3c  mov     ebx, 80004005h
0x18004ee41  mov     [rsp+228h+var_1F8], ebx
0x18004ee45  lea     rcx, [rsp+228h+var_1D8]; this
0x18004ee4a  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ee4f  mov     rcx, [rsp+228h+var_1C8]
0x18004ee54  jmp     short loc_18004EE5F
0x18004ee56  mov     ebx, 80004005h
0x18004ee5b  mov     [rsp+228h+var_1F8], ebx
0x18004ee5f  test    rcx, rcx
0x18004ee62  jz      short loc_18004EE6F
0x18004ee64  lea     rcx, [rsp+228h+var_1C8]
0x18004ee69  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18004ee6e  nop
0x18004ee6f  lea     rcx, [rsp+228h+phkResult]; this
0x18004ee74  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004ee79  nop
0x18004ee7a  jmp     short loc_18004EE80
0x18004ee7c  mov     ebx, [rsp+228h+var_1F8]
0x18004ee80  test    ebx, ebx
0x18004ee82  jns     loc_18004EF0D
0x18004ee88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::GetImpl(void)'::`2'::impl
0x18004ee8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOEMContentDefaultImages>::__private_IsEnabled(void)
0x18004ee94  test    al, al
0x18004ee96  jz      short loc_18004EEEB
0x18004ee98  lea     rcx, [rsp+228h+var_1C0]; this
0x18004ee9d  call    ??0UserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings(void)
0x18004eea2  nop
0x18004eea3  lea     rcx, [rsp+228h+var_1C0]
0x18004eea8  call    ?WallpaperCount@?$consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension@UIDesktopSpotlightExtension@DesktopSpotlight@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_DesktopSpotlight_IDesktopSpotlightExtension<winrt::WindowsUdk::UI::Shell::DesktopSpotlight::IDesktopSpotlightExtension>::WallpaperCount(void)
0x18004eead  cmp     eax, 1
0x18004eeb0  jnz     short loc_18004EED8
0x18004eeb2  mov     rcx, [rsp+228h+var_1E8]
0x18004eeb7  mov     rax, [rcx]
0x18004eeba  lea     r9, a1_0; "1"
0x18004eec1  xor     r8d, r8d
0x18004eec4  xor     edx, edx
0x18004eec6  mov     rax, [rax+0C8h]
0x18004eecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eed2  mov     ebx, eax
0x18004eed4  mov     [rsp+228h+var_1F8], eax
0x18004eed8  lea     rcx, [rsp+228h+var_1C0]; this
0x18004eedd  call    ??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)
0x18004eee2  nop
0x18004eee3  jmp     short loc_18004EF0D
0x18004eee5  mov     ebx, [rsp+228h+var_1F8]
0x18004eee9  jmp     short loc_18004EF0D
0x18004eeeb  mov     rcx, [rsp+228h+var_1E8]
0x18004eef0  mov     rax, [rcx]
0x18004eef3  lea     r9, a1_0; "1"
0x18004eefa  xor     r8d, r8d
0x18004eefd  xor     edx, edx
0x18004eeff  mov     rax, [rax+0C8h]
0x18004ef06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef0b  mov     ebx, eax
0x18004ef0d  mov     rcx, [rsp+228h]; this
0x18004ef15  test    ebx, ebx
0x18004ef17  jns     loc_18004EFE0
0x18004ef1d  mov     r9d, ebx; char *
0x18004ef20  lea     r8, aShellThemesThe_5; "shell\\themes\\themeui\\themeapply.cpp"
0x18004ef27  mov     edx, 4FFh; void *
0x18004ef2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ef31  mov     dl, 1
0x18004ef33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure> `wil::Feature<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::GetImpl(void)'::`2'::impl
0x18004ef3a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDesktopSpotlightOnFatalFailure>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004ef3f  mov     r8b, 3
0x18004ef42  mov     dl, 1
0x18004ef44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl(void)'::`2'::impl
0x18004ef4b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004ef50  mov     dl, 1
0x18004ef52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x18004ef59  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004ef5e  call    ?_DisableDesktopSpotlight@CThemeManager2@@AEAAJXZ; CThemeManager2::_DisableDesktopSpotlight(void)
0x18004ef63  mov     [rsp+228h+phkResult], 0
0x18004ef6c  lea     rax, [rsp+228h+phkResult]
0x18004ef71  mov     [rsp+228h+ppv], rax; phkResult
0x18004ef76  mov     r9d, 2; samDesired
0x18004ef7c  xor     r8d, r8d; ulOptions
0x18004ef7f  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x18004ef86  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18004ef8d  call    cs:__imp_RegOpenKeyExW
0x18004ef93  lea     rdx, aWallpaper; "Wallpaper"
0x18004ef9a  mov     rcx, [rsp+228h+phkResult]; hKey
0x18004ef9f  call    cs:__imp_RegDeleteValueW
0x18004efa5  mov     [rsp+228h+cbData], 0; cbData
0x18004efad  lea     rax, Default
0x18004efb4  mov     [rsp+228h+ppv], rax; lpData
0x18004efb9  mov     r9d, 1; dwType
0x18004efbf  xor     r8d, r8d; Reserved
0x18004efc2  lea     rdx, aWallpaper; "Wallpaper"
0x18004efc9  mov     rcx, [rsp+228h+phkResult]; hKey
0x18004efce  call    cs:__imp_RegSetValueExW
0x18004efd4  lea     rcx, [rsp+228h+phkResult]
0x18004efd9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004efde  jmp     short loc_18004EFF1
0x18004efe0  mov     r8b, 3
0x18004efe3  mov     dl, 1
0x18004efe5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl(void)'::`2'::impl
0x18004efec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004eff1  mov     edx, ebx
0x18004eff3  lea     rcx, [rsp+228h+var_168]
0x18004effb  call    ?Stop@?$ActivityBase@VThemesLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThemesLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004f000  nop
0x18004f001  lea     rcx, [rsp+228h+var_1E8]
0x18004f006  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f00b  nop
0x18004f00c  lea     rcx, [rsp+228h+var_168]; this
0x18004f014  call    ??1ApplyDesktopSpotlight@ThemesTelemetry@@QEAA@XZ; ThemesTelemetry::ApplyDesktopSpotlight::~ApplyDesktopSpotlight(void)
0x18004f019  mov     eax, ebx
0x18004f01b  mov     rcx, [rsp+228h+var_18]
0x18004f023  xor     rcx, rsp; StackCookie
0x18004f026  call    __security_check_cookie
0x18004f02b  mov     rbx, [rsp+228h+arg_0]
0x18004f033  add     rsp, 220h
0x18004f03a  pop     rsi
0x18004f03b  retn
```
