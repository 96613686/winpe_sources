# AccessibilityDialog::Initialize(HINSTANCE__ *)

- ea: `0x1400206e8`
- end: `0x140020a1b`
- name: `?Initialize@AccessibilityDialog@@AEAAXPEAUHINSTANCE__@@@Z`
- size: `819`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140022098`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000c354`
- `0x14000ccdc`
- `0x14000ccf8`
- `0x14000cf60`
- `0x14000cfa0`
- `0x14000d32c`
- `0x14000d360`
- `0x14000e624`
- `0x14000f914`
- `0x14000ffc0`
- `0x14001091c`
- `0x14001d7bc`
- `0x14001e66c`
- `0x14001ebcc`
- `0x14001ecbc`
- `0x14001ee00`
- `0x14001f2d4`
- `0x14001f46c`
- `0x14001f714`
- `0x14001fb44`
- `0x140020474`
- `0x1400206e8`
- `0x140021538`
- `0x140021fdc`
- `0x14002235c`
- `0x1400223d8`
- `0x140022e08`
- `0x140022e6c`
- `0x140023104`
- `0x1400247dc`
- `0x140029010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140020822`
- `ADVAPI32!RegGetValueW` at `0x140020822`
- `USER32!SetForegroundWindow` at `0x140020968`
- `USER32!SetForegroundWindow` at `0x140020968`
- `USER32!SystemParametersInfoW` at `0x14002098a`
- `USER32!SystemParametersInfoW` at `0x14002098a`

## string_xrefs

- `0x14002091a`: `\n    <Grid\n        Width="358"\n        Height="345"\n        x:Name="RootGrid"\n        CornerRadius="7"\n        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"\n        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"\n        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"\n        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006">\n        <Grid.Resources>\n            <ResourceDictionary>\n                <ResourceDictionary.Theme`
- `0x140020923`: `\n    <Grid\n        Width="358"\n        Height="345"\n        x:Name="RootGrid"\n        CornerRadius="7"\n        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"\n        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"\n        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"\n        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006">\n        <Grid.Resources>\n            <ResourceDictionary>\n                <ResourceDictionary.Theme`
- `0x14002080d`: `LastLoggedOnUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AccessibilityDialog::Initialize(AccessibilityDialog *this, HINSTANCE a2)
{
  char *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  LSTATUS ValueW; // eax
  AccessibilityDialog *v13; // rcx
  bool v14; // sf
  DWORD v15; // esi
  unsigned int v16; // eax
  char IsEnabled; // al
  const wchar_t *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rbx
  DWORD pvParam[2]; // [rsp+C0h] [rbp-80h] BYREF
  __int64 v22; // [rsp+C8h] [rbp-78h] BYREF
  _QWORD v23[2]; // [rsp+D0h] [rbp-70h] BYREF
  _BYTE v24[64]; // [rsp+E0h] [rbp-60h] BYREF
  int v25; // [rsp+120h] [rbp-20h] BYREF
  __int128 v26; // [rsp+128h] [rbp-18h]
  _OWORD v27[2]; // [rsp+140h] [rbp+0h] BYREF
  unsigned __int16 pvData[104]; // [rsp+160h] [rbp+20h] BYREF

  v4 = (char *)this + 320;
  v22 = 0;
  v5 = *((_QWORD *)this + 40);
  if ( !v5 || (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v5 + 8) )
  {
    v7 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,_GUID * &>(
           pvParam,
           &v22);
    wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::operator=(
      v4,
      v7);
    wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>(pvParam);
  }
  else
  {
    tip2::details::shared_data<1,0,0>::open_without_lock(v6, 0);
  }
  v8 = tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::ensure_data(v4);
  tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(
    v24,
    v8);
  *((_QWORD *)this + 4) = a2;
  AccessibilityDialog::CreateParentWindow(this);
  v9 = (__int64 *)std::make_unique<XamlUI,HWND__ * &,0>(&v22, (char *)this + 40);
  v10 = *v9;
  *v9 = 0;
  v11 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v10;
  if ( v11 )
    std::default_delete<XamlUI>::operator()();
  std::unique_ptr<XamlUI>::~unique_ptr<XamlUI>(&v22);
  v27[0] = 0;
  v27[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v27[0]) = 0;
  memset_0(pvData, 0, 0xC8u);
  pvParam[0] = 200;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
             L"LastLoggedOnUserSID",
             2u,
             0,
             pvData,
             pvParam);
  if ( pvParam[0] )
  {
    v14 = ValueW < 0;
    if ( ValueW > 0 )
      v14 = 1;
    if ( !v14 )
      AccessibilityDialog::GetTextScaleFactor(v13, pvData);
  }
  *(_QWORD *)pvParam = &qword_140047378;
  v15 = 1;
  _InterlockedAdd64(&qword_140047378, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics> )
  {
    _lambda_4d8e94c9ab6887d2b642d3b894f8b627_::operator()(
      v13,
      &v22,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>);
    _InterlockedDecrement64(&qword_140047378);
  }
  else
  {
    _InterlockedDecrement64(&qword_140047378);
    *(_QWORD *)pvParam = _lambda_4d8e94c9ab6887d2b642d3b894f8b627_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController> (*)(winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics const &)>(
      v13,
      &v22,
      pvParam);
  }
  winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>((winrt *)v23);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v22);
  v25 = 0;
  v26 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 80LL))(v23[0]);
  winrt::check_hresult(pvParam, v16, &v25);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FTW>::GetImpl'::`2'::impl);
  v18 = aGridWidth358He_0;
  if ( !IsEnabled )
    v18 = aGridWidth358He;
  v19 = XamlResourceUtils::LocalizeXaml<int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int>(
          &v25,
          v18,
          *((_QWORD *)this + 4));
  std::wstring::operator=(v27, v19);
  std::wstring::_Tidy_deallocate(&v25);
  v20 = *((_QWORD *)this + 6);
  winrt::param::hstring::hstring((winrt::param::hstring *)&v25);
  XamlUI::Initialize(v20, &v25, 1);
  SetForegroundWindow(*((HWND *)this + 5));
  AccessibilityDialog::SetUpControls(this);
  if ( SystemParametersInfoW(0xAAu, 0, pvParam, 0) && pvParam[0] || (pvParam[0] = 0, IsLogonUI()) )
    v15 = 2;
  pvParam[0] = v15;
  winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement2<winrt::Windows::UI::Xaml::Controls::Grid>::RequestedTheme(
    (char *)this + 112,
    pvParam);
  AccessibilityDialog::SetToggleUiStates(this);
  AccessibilityDialog::RegisterUiHandlers(this);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v23);
  std::wstring::_Tidy_deallocate(v27);
  tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::~test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(v24);
}

```

## disassembly

```asm
0x1400206e8  mov     [rsp-8+arg_8], rbx
0x1400206ed  mov     [rsp-8+arg_10], rsi
0x1400206f2  push    rbp
0x1400206f3  push    rdi
0x1400206f4  push    r14
0x1400206f6  lea     rbp, [rsp-100h]
0x1400206fe  sub     rsp, 240h
0x140020705  mov     rax, cs:__security_cookie
0x14002070c  xor     rax, rsp
0x14002070f  mov     [rbp+110h+var_20], rax
0x140020716  mov     rsi, rdx
0x140020719  mov     rdi, rcx
0x14002071c  lea     rbx, [rcx+140h]
0x140020723  mov     [rbp+110h+var_188], 0
0x14002072b  mov     rax, [rbx]
0x14002072e  test    rax, rax
0x140020731  jz      short loc_140020749
0x140020733  lea     rcx, [rax+8]
0x140020737  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x14002073c  test    al, al
0x14002073e  jnz     short loc_140020749
0x140020740  xor     edx, edx
0x140020742  call    ?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)
0x140020747  jmp     short loc_14002076A
0x140020749  lea     rdx, [rbp+110h+var_188]
0x14002074d  lea     rcx, [rbp+110h+pvParam]
0x140020751  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,_GUID * &>(_GUID * &)
0x140020756  mov     rdx, rax
0x140020759  mov     rcx, rbx
0x14002075c  call    ??4?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy> &&)
0x140020761  lea     rcx, [rbp+110h+pvParam]
0x140020765  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>(void)
0x14002076a  mov     rcx, rbx
0x14002076d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::ensure_data(void)
0x140020772  mov     rdx, rax
0x140020775  lea     rcx, [rbp+110h+var_170]
0x140020779  call    ??0?$test_watcher@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy> &)
0x14002077e  nop
0x14002077f  mov     [rdi+20h], rsi
0x140020783  mov     rcx, rdi; this
0x140020786  call    ?CreateParentWindow@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::CreateParentWindow(void)
0x14002078b  lea     rdx, [rdi+28h]
0x14002078f  lea     rcx, [rbp+110h+var_188]
0x140020793  call    ??$make_unique@VXamlUI@@AEAPEAUHWND__@@$0A@@std@@YA?AV?$unique_ptr@VXamlUI@@U?$default_delete@VXamlUI@@@std@@@0@AEAPEAUHWND__@@@Z; std::make_unique<XamlUI,HWND__ * &,0>(HWND__ * &)
0x140020798  mov     rcx, [rax]
0x14002079b  mov     qword ptr [rax], 0
0x1400207a2  mov     rdx, [rdi+30h]
0x1400207a6  mov     [rdi+30h], rcx
0x1400207aa  test    rdx, rdx
0x1400207ad  jz      short loc_1400207B4
0x1400207af  call    ??R?$default_delete@VXamlUI@@@std@@QEBAXPEAVXamlUI@@@Z; std::default_delete<XamlUI>::operator()(XamlUI *)
0x1400207b4  lea     rcx, [rbp+110h+var_188]
0x1400207b8  call    ??1?$unique_ptr@VXamlUI@@U?$default_delete@VXamlUI@@@std@@@std@@QEAA@XZ; std::unique_ptr<XamlUI>::~unique_ptr<XamlUI>(void)
0x1400207bd  xorps   xmm0, xmm0
0x1400207c0  movups  [rbp+110h+var_110], xmm0
0x1400207c4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400207cc  movdqu  [rbp+110h+var_100], xmm1
0x1400207d1  xor     eax, eax
0x1400207d3  mov     word ptr [rbp+110h+var_110], ax
0x1400207d7  lea     ebx, [rax+64h]
0x1400207da  lea     esi, [rbx+64h]
0x1400207dd  mov     r8d, esi; Size
0x1400207e0  xor     edx, edx; Val
0x1400207e2  lea     rcx, [rbp+110h+var_F0]; void *
0x1400207e6  call    memset_0
0x1400207eb  mov     [rbp+110h+pvParam], esi
0x1400207ee  lea     rax, [rbp+110h+pvParam]
0x1400207f2  mov     [rsp+250h+pcbData], rax; pcbData
0x1400207f7  lea     rax, [rbp+110h+var_F0]
0x1400207fb  mov     [rsp+250h+pvData], rax; pvData
0x140020800  mov     [rsp+250h+pdwType], 0; pdwType
0x140020809  lea     r9d, [rbx-62h]; dwFlags
0x14002080d  lea     r8, aLastloggedonus; "LastLoggedOnUserSID"
0x140020814  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14002081b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140020822  call    cs:__imp_RegGetValueW
0x140020829  nop     dword ptr [rax+rax+00h]
0x14002082e  cmp     [rbp+110h+pvParam], 0
0x140020832  jz      short loc_14002084F
0x140020834  test    eax, eax
0x140020836  jle     short loc_140020842
0x140020838  movzx   eax, ax
0x14002083b  or      eax, 80070000h
0x140020840  test    eax, eax
0x140020842  js      short loc_14002084F
0x140020844  lea     rdx, [rbp+110h+var_F0]; unsigned __int16 *
0x140020848  call    ?GetTextScaleFactor@AccessibilityDialog@@AEAAHPEBG@Z; AccessibilityDialog::GetTextScaleFactor(ushort const *)
0x14002084d  mov     ebx, eax
0x14002084f  lea     rax, qword_140047378
0x140020856  mov     qword ptr [rbp+110h+pvParam], rax
0x14002085a  mov     esi, 1
0x14002085f  lock add cs:qword_140047378, rsi
0x140020867  cmp     cs:??$factory_cache_entry_v@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>
0x14002086f  jz      short loc_14002088C
0x140020871  lea     r8, ??$factory_cache_entry_v@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>
0x140020878  lea     rdx, [rbp+110h+var_188]
0x14002087c  call    ??R_lambda_4d8e94c9ab6887d2b642d3b894f8b627_@@QEBA@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@Windows@winrt@@@Z; _lambda_4d8e94c9ab6887d2b642d3b894f8b627_::operator()(winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics const &)
0x140020881  nop
0x140020882  lock dec cs:qword_140047378
0x14002088a  jmp     short loc_1400208AD
0x14002088c  lock dec cs:qword_140047378
0x140020894  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4d8e94c9ab6887d2b642d3b894f8b627_@@CA@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@Windows@winrt@@@Z; _lambda_4d8e94c9ab6887d2b642d3b894f8b627_::_lambda_invoker_cdecl_(winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics const &)
0x14002089b  mov     qword ptr [rbp+110h+pvParam], rax
0x14002089f  lea     r8, [rbp+110h+pvParam]
0x1400208a3  lea     rdx, [rbp+110h+var_188]
0x1400208a7  call    ??$call@P6A?AU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@34@@Z@?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@2@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@52@@Z@Z
0x1400208ac  nop
0x1400208ad  lea     rdx, [rbp+110h+var_188]
0x1400208b1  lea     rcx, [rbp+110h+var_180]; this
0x1400208b5  call    ??$wait_get@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@@Z
0x1400208ba  nop
0x1400208bb  lea     rcx, [rbp+110h+var_188]
0x1400208bf  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400208c4  mov     rcx, [rbp+110h+var_180]
0x1400208c8  mov     [rbp+110h+var_130], 0
0x1400208cf  xorps   xmm0, xmm0
0x1400208d2  movdqu  [rbp+110h+var_128], xmm0
0x1400208d7  mov     rax, [rcx]
0x1400208da  movd    xmm1, ebx
0x1400208de  cvtdq2ps xmm1, xmm1
0x1400208e1  divss   xmm1, cs:__real@42c80000
0x1400208e9  cvtps2pd xmm1, xmm1
0x1400208ec  mov     rax, [rax+50h]
0x1400208f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400208f5  lea     r8, [rbp+110h+var_130]
0x1400208f9  mov     edx, eax
0x1400208fb  lea     rcx, [rbp+110h+pvParam]
0x1400208ff  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140020904  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FTW@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FTW@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW> `wil::Feature<__WilFeatureTraits_Feature_FTW>::GetImpl(void)'::`2'::impl
0x14002090b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FTW@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FTW>::__private_IsEnabled(void)
0x140020910  mov     r8, [rdi+20h]
0x140020914  lea     rcx, [rbp+110h+var_130]
0x140020918  test    al, al
0x14002091a  lea     rdx, aGridWidth358He_0; "\n    <Grid\n        Width=\"358\"\n   "...
0x140020921  jnz     short loc_14002092A
0x140020923  lea     rdx, aGridWidth358He; "\n    <Grid\n        Width=\"358\"\n   "...
0x14002092a  call    ??$LocalizeXaml@HHHHHHHHHHHHHHHHHHHHH@XamlResourceUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAUHINSTANCE__@@HHHHHHHHHHHHHHHHHHHHH@Z; XamlResourceUtils::LocalizeXaml<int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int>(ushort const *,HINSTANCE__ *,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int,int)
0x14002092f  mov     rdx, rax
0x140020932  lea     rcx, [rbp+110h+var_110]
0x140020936  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14002093b  lea     rcx, [rbp+110h+var_130]
0x14002093f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140020944  mov     rbx, [rdi+30h]
0x140020948  lea     rdx, [rbp+110h+var_110]
0x14002094c  lea     rcx, [rbp+110h+var_130]; this
0x140020950  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x140020955  mov     r8d, esi
0x140020958  lea     rdx, [rbp+110h+var_130]
0x14002095c  mov     rcx, rbx
0x14002095f  call    ?Initialize@XamlUI@@QEAAXAEBUhstring@param@winrt@@W4XamlUiLoadedBehaviour@@@Z; XamlUI::Initialize(winrt::param::hstring const &,XamlUiLoadedBehaviour)
0x140020964  mov     rcx, [rdi+28h]; hWnd
0x140020968  call    cs:__imp_SetForegroundWindow
0x14002096f  nop     dword ptr [rax+rax+00h]
0x140020974  mov     rcx, rdi; this
0x140020977  call    ?SetUpControls@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::SetUpControls(void)
0x14002097c  xor     r9d, r9d; fWinIni
0x14002097f  lea     r8, [rbp+110h+pvParam]; pvParam
0x140020983  xor     edx, edx; uiParam
0x140020985  mov     ecx, 0AAh; uiAction
0x14002098a  call    cs:__imp_SystemParametersInfoW
0x140020991  nop     dword ptr [rax+rax+00h]
0x140020996  test    eax, eax
0x140020998  jz      short loc_1400209A0
0x14002099a  cmp     [rbp+110h+pvParam], 0
0x14002099e  jnz     short loc_1400209B0
0x1400209a0  mov     [rbp+110h+pvParam], 0
0x1400209a7  call    ?IsLogonUI@@YA_NXZ; IsLogonUI(void)
0x1400209ac  test    al, al
0x1400209ae  jz      short loc_1400209B5
0x1400209b0  mov     esi, 2
0x1400209b5  mov     [rbp+110h+pvParam], esi
0x1400209b8  lea     rcx, [rdi+70h]
0x1400209bc  lea     rdx, [rbp+110h+pvParam]
0x1400209c0  call    ?RequestedTheme@?$consume_Windows_UI_Xaml_IFrameworkElement2@UGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW4ElementTheme@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement2<winrt::Windows::UI::Xaml::Controls::Grid>::RequestedTheme(winrt::Windows::UI::Xaml::ElementTheme const &)
0x1400209c5  mov     rcx, rdi; this
0x1400209c8  call    ?SetToggleUiStates@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::SetToggleUiStates(void)
0x1400209cd  mov     rcx, rdi; this
0x1400209d0  call    ?RegisterUiHandlers@AccessibilityDialog@@AEAAXXZ; AccessibilityDialog::RegisterUiHandlers(void)
0x1400209d5  nop
0x1400209d6  lea     rcx, [rbp+110h+var_180]
0x1400209da  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400209df  nop
0x1400209e0  lea     rcx, [rbp+110h+var_110]
0x1400209e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400209e9  nop
0x1400209ea  lea     rcx, [rbp+110h+var_170]
0x1400209ee  call    ??1?$test_watcher@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>::~test_watcher<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>>(void)
0x1400209f3  mov     rcx, [rbp+110h+var_20]
0x1400209fa  xor     rcx, rsp; StackCookie
0x1400209fd  call    __security_check_cookie
0x140020a02  lea     r11, [rsp+250h+var_10]
0x140020a0a  mov     rbx, [r11+28h]
0x140020a0e  mov     rsi, [r11+30h]
0x140020a12  mov     rsp, r11
0x140020a15  pop     r14
0x140020a17  pop     rdi
0x140020a18  pop     rbp
0x140020a19  retn
```
