# TouchKeyboardExperienceManager::InitializeTabTipAdapter(void)

- ea: `0x1800d6e94`
- end: `0x1800d7853`
- name: `?InitializeTabTipAdapter@TouchKeyboardExperienceManager@@AEAAJXZ`
- size: `2495`
- prototype: `__int64 __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180228770`

## callees

- `0x1800237c8`
- `0x180026e04`
- `0x180031c70`
- `0x18006adc4`
- `0x18006d458`
- `0x1800b0290`
- `0x1800c0910`
- `0x1800d55f0`
- `0x1800d5610`
- `0x1800d56dc`
- `0x1800d588c`
- `0x1800d5914`
- `0x1800d6e94`
- `0x1800d7c50`
- `0x1800d7ca0`
- `0x1800d7e94`
- `0x1800d7ecc`
- `0x1800d7f24`
- `0x1800e3c04`
- `0x180112b40`
- `0x1801c9a58`
- `0x1801d4058`
- `0x1801e46a8`
- `0x1801fe068`
- `0x180227814`
- `0x180268bd8`
- `0x180273fd4`
- `0x18027f7ec`
- `0x1802ad2d0`
- `0x1802afa84`
- `0x1802b1f5c`
- `0x1802dd470`
- `0x180356360`
- `0x180356384`
- `0x180356970`
- `0x1803bc514`
- `0x1804b398c`
- `0x1804b5dd8`
- `0x1804bad40`
- `0x1806fa010`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800d7506`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800d7506`
- `ntdll!NtQueryWnfStateData` at `0x1800d7470`
- `ntdll!NtQueryWnfStateData` at `0x1800d7470`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d6fa9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800d6fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d6f79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d6f79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d704c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d716c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d704c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d716c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d71b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d724e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d75f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d7092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d71b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d724e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d75f0`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x1800d777a`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x1800d77d5`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x1800d777a`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x1800d77d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall TouchKeyboardExperienceManager::InitializeTabTipAdapter(TouchKeyboardExperienceManager *this)
{
  KeyboardHosting::TabTipAdapter *v2; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // ebx
  const unsigned __int16 *v7; // rdx
  unsigned int *v8; // r8
  unsigned int v9; // eax
  __int64 (__fastcall *v10)(); // rcx
  __int64 v11; // rdx
  HKEY *v12; // rax
  LSTATUS Key; // eax
  bool v14; // sf
  __int64 (__fastcall *v15)(); // rcx
  __int64 v16; // rdx
  HKEY *v17; // rax
  LSTATUS v18; // eax
  bool v19; // sf
  int v20; // eax
  __int64 v21; // rdx
  unsigned int v22; // ebx
  __int64 (__fastcall *v23)(); // rcx
  __int64 v24; // r8
  int wnf_subscription; // eax
  HKEY v26; // rcx
  struct wil::details::wnf_subscription_state_base *v27; // rdx
  __int64 v28; // r14
  char *v29; // rax
  HKEY v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned int v34; // eax
  __int64 (__fastcall *v35)(); // rcx
  HKEY v36; // r15
  void *v37; // rax
  void (__fastcall ***v38)(_QWORD, _QWORD); // r14
  __int64 v39; // r8
  int v40; // ebx
  int v41; // ebx
  struct wil::details::wnf_subscription_state_base *v42; // rdx
  _QWORD *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // r8
  int v46; // eax
  HKEY v47; // rcx
  struct wil::details::wnf_subscription_state_base *v48; // rdx
  __int64 v49; // rax
  struct wil::details::wnf_subscription_state_base *v50; // rdx
  HWINEVENTHOOK v51; // rax
  HWINEVENTHOOK v52; // rax
  int phkResult; // [rsp+20h] [rbp-128h]
  unsigned int phkResulta; // [rsp+20h] [rbp-128h]
  int phkResultb; // [rsp+20h] [rbp-128h]
  int phkResultc; // [rsp+20h] [rbp-128h]
  int phkResultd; // [rsp+20h] [rbp-128h]
  int phkResulte; // [rsp+20h] [rbp-128h]
  int phkResultf; // [rsp+20h] [rbp-128h]
  HKEY v60; // [rsp+50h] [rbp-F8h] BYREF
  bool v61[8]; // [rsp+58h] [rbp-F0h] BYREF
  wil::details::registry_watcher_state *v62; // [rsp+60h] [rbp-E8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-E0h] BYREF
  HKEY *p_hKey; // [rsp+70h] [rbp-D8h] BYREF
  HKEY v65; // [rsp+78h] [rbp-D0h] BYREF
  char v66; // [rsp+80h] [rbp-C8h]
  _BYTE v67[8]; // [rsp+88h] [rbp-C0h] BYREF
  _BYTE v68[8]; // [rsp+90h] [rbp-B8h] BYREF
  __int64 (__fastcall **v69)(); // [rsp+98h] [rbp-B0h] BYREF
  __int64 (__fastcall *v70)(); // [rsp+A0h] [rbp-A8h]
  int v71; // [rsp+A8h] [rbp-A0h]
  int v72; // [rsp+ACh] [rbp-9Ch]
  TouchKeyboardExperienceManager *v73; // [rsp+B0h] [rbp-98h]
  __int64 (__fastcall ***v74)(); // [rsp+100h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v2 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  if ( !v2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1423,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)0x80004005LL,
      phkResult);
    return 2147500037LL;
  }
  KeyboardHosting::TabTipAdapter::Initialize(v2);
  v4 = TouchKeyboardExperienceManager::WorkAreaChanged(
         (TouchKeyboardExperienceManager *)((char *)this + 128),
         0,
         (const struct tagRECT *)((char *)this + 472));
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1427,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
    return v5;
  }
  hKey = 0;
  p_hKey = &hKey;
  v65 = 0;
  v66 = 1;
  v6 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\TabletTip\\1.7", 0, 3u, &v65);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( !v6 )
  {
    if ( (unsigned int)SHRegValueExists(hKey, v7, v8) )
    {
      v9 = RegDeleteValueW(hKey, L"KeyboardTheme_Updating");
      if ( v9 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x1430,
          (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
          (const char *)v9,
          phkResulta);
    }
  }
  v10 = *(__int64 (__fastcall **)())winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(
                                      v67,
                                      this);
  v69 = off_1807085F0;
  v70 = v10;
  v74 = &v69;
  v62 = 0;
  v60 = 0;
  v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                  &v60,
                  v11);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TabletTip\\1.7", 0, 0, 0, 0x10u, 0, v12, 0);
  v14 = Key < 0;
  if ( Key > 0 )
    v14 = 1;
  if ( v14 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
  }
  else
  {
    wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
      &v62,
      &v60,
      0,
      v68);
    if ( v60 )
      RegCloseKey(v60);
  }
  wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(
    (char *)this + 304,
    &v62);
  if ( v62 )
    wil::details::registry_watcher_state::Release(v62);
  if ( v74 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v74)[3])(v74);
  if ( !*((_QWORD *)this + 38) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x143D,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)0x8000FFFFLL,
      phkResultb);
  v15 = *(__int64 (__fastcall **)())winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(
                                      v67,
                                      this);
  v69 = off_1807085F0;
  v70 = v15;
  v74 = &v69;
  v62 = 0;
  v60 = 0;
  v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                  &v60,
                  v16);
  v18 = RegCreateKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\TabletTip\\1.7", 0, 0, 0, 0x10u, 0, v17, 0);
  v19 = v18 < 0;
  if ( v18 > 0 )
    v19 = 1;
  if ( v19 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
  }
  else
  {
    wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
      &v62,
      &v60,
      0,
      v68);
    if ( v60 )
      RegCloseKey(v60);
  }
  wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(
    (char *)this + 312,
    &v62);
  if ( v62 )
    wil::details::registry_watcher_state::Release(v62);
  if ( v74 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v74)[3])(v74);
  if ( !*((_QWORD *)this + 39) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1447,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)0x8000FFFFLL,
      phkResultc);
  v20 = TouchKeyboardExperienceManager::OnTabtipRegistryChanged(this);
  v22 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1448,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v20,
      phkResultc);
    if ( hKey )
      RegCloseKey(hKey);
    return v22;
  }
  LOBYTE(v21) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PATKTI>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_PATKTI>::GetImpl'::`2'::impl,
    v21);
  v23 = *(__int64 (__fastcall **)())winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(
                                      v67,
                                      this);
  v69 = off_180708618;
  v70 = v23;
  v74 = &v69;
  v60 = 0;
  wnf_subscription = wil::details::make_wnf_subscription_state<bool>(v23, v68, v24, &v60);
  v26 = 0;
  if ( wnf_subscription >= 0 )
    v26 = v60;
  v60 = v26;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 2216,
    &v60);
  if ( v60 )
    wil::details::delete_wnf_subscription_state((wil::details *)v60, v27);
  if ( v74 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v74)[3])(v74);
  v28 = *(_QWORD *)winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(
                     v67,
                     this);
  v29 = (char *)operator new(0x18u);
  winrt::impl::implements_delegate_base::implements_delegate_base((winrt::impl::implements_delegate_base *)(v29 + 8));
  *((_QWORD *)v30 + 2) = v28;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v30 = off_180708640;
  v60 = v30;
  v32 = winrt::impl::consume_Windows_Internal_ComposableShell_Multitasking_IVirtualDesktopDataSource<winrt::Windows::Internal::ComposableShell::Multitasking::IVirtualDesktopDataSource>::VirtualDesktopDataSourceChanged(
          (char *)this + 2184,
          &p_hKey,
          v31,
          &v60);
  __4__event_revoker_UITapInvokeSetting_TouchKeyboard_Shell_Internal_Windows_winrt___MP8type___abi_UITapInvokeSetting_TouchKeyboard_Shell_Internal_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BFA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 2192,
    v32);
  if ( p_hKey )
  {
    v33 = winrt::weak_ref<winrt::Windows::Internal::Shell::TouchKeyboard::ITapInvokeSetting>::get(&p_hKey, &v62);
    _revoke_impl___event_revoker_UIDesktopWindowXamlSource_Hosting_Xaml_UI_Windows_winrt___MP8type___abi_UIDesktopWindowXamlSource_Hosting_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BFA_AA_impl_winrt__AEAAXUIDesktopWindowXamlSource_Hosting_Xaml_UI_Windows_3__Z(
      &p_hKey,
      v33);
    if ( p_hKey )
      winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(&p_hKey);
  }
  winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(&v60);
  v34 = winrt::impl::consume_WindowsUdk_UI_Shell_IViewVisibilityChangedEventArgs<winrt::WindowsUdk::UI::Shell::IViewVisibilityChangedEventArgs>::View((char *)this + 2184);
  TouchKeyboardExperienceManager::OnTapInvokeEffectiveSettingChanged(this, v34);
  v35 = *(__int64 (__fastcall **)())winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(
                                      v67,
                                      this);
  v69 = off_1807152D0;
  v70 = v35;
  v74 = &v69;
  LODWORD(v62) = 0;
  v36 = 0;
  v37 = operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v37
    || (v38 = (void (__fastcall ***)(_QWORD, _QWORD))wil::details::wnf_subscription_state<unsigned long>::wnf_subscription_state<unsigned long>(
                                                       v37,
                                                       v68)) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
      (const char *)0x8007000ELL,
      phkResultc);
    v40 = -2147024882;
    goto LABEL_60;
  }
  v39 = (unsigned int)v62;
  if ( (_DWORD)v62 == -1 )
  {
    LODWORD(v60) = 0;
    v40 = NtQueryWnfStateData(&WNF_SHEL_LOCKSCREEN_ACTIVE, 0, 0, &v62) | 0x10000000;
    if ( (int)(v40 + 0x80000000) >= 0 && v40 != -805306333 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
        (const char *)(unsigned int)v40,
        0);
      goto LABEL_52;
    }
    v39 = (unsigned int)v62;
  }
  p_hKey = (HKEY *)(v38 + 1);
  v65 = 0;
  v66 = 1;
  phkResultd = (int)v38;
  v41 = RtlSubscribeWnfStateChangeNotification(
          &v65,
          WNF_SHEL_LOCKSCREEN_ACTIVE,
          v39,
          _lambda_a14e49ce427a1853f087bba834558a2c_::_lambda_invoker_cdecl_);
  if ( v66 )
    wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(
      p_hKey,
      v65);
  if ( v41 >= 0 )
  {
    v36 = (HKEY)v38;
    v40 = 0;
    goto LABEL_60;
  }
  v40 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x3C7,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
          (const char *)(unsigned int)v41,
          (int)v38);
LABEL_52:
  (**v38)(v38, 1);
LABEL_60:
  if ( v40 < 0 )
    v36 = 0;
  v60 = v36;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 328,
    &v60);
  if ( v60 )
    wil::details::delete_wnf_subscription_state((wil::details *)v60, v42);
  if ( v74 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v74)[3])(v74);
  if ( *((_QWORD *)this + 41) )
  {
    v43 = (_QWORD *)winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(
                      v67,
                      this);
    wistd::function_void___cdecl_enum_Windows::Internal::Shell::Holographic::UserDisplayContext_const____::function_void___cdecl_enum_Windows::Internal::Shell::Holographic::UserDisplayContext_const______lambda_465da9a331312912f50f4864e6ffccb4__void_(
      v68,
      *v43);
    v60 = 0;
    v46 = wil::details::make_wnf_subscription_state<enum Windows::Internal::Shell::Holographic::UserDisplayContext>(
            v44,
            v68,
            v45,
            &v60);
    v47 = 0;
    if ( v46 >= 0 )
      v47 = v60;
    v60 = v47;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 2296,
      &v60);
    if ( v60 )
      wil::details::delete_wnf_subscription_state((wil::details *)v60, v48);
    wistd::function<bool (long)>::~function<bool (long)>(v68);
    if ( *((_QWORD *)this + 287) )
    {
      if ( !*((_QWORD *)this + 294) )
      {
        v69 = (__int64 (__fastcall **)())&wistd::__function::__func<std::_Binder<std::_Unforced,long (TouchKeyboardExperienceManager::*)(void),TouchKeyboardExperienceManager *>,void (void)>::`vftable';
        v70 =  TouchKeyboardExperienceManager::`vcall'{56,{flat}};
        v71 = 144;
        v72 = HIDWORD(v65);
        v73 = this;
        v74 = &v69;
        v49 = wil::make_wnf_subscription<wil::details::empty_wnf_state>(
                &v60,
                WNF_SHEL_INVOKE_TOUCH_KEYBOARD,
                v68,
                0xFFFFFFFFLL);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
          (char *)this + 2352,
          v49);
        if ( v60 )
          wil::details::delete_wnf_subscription_state((wil::details *)v60, v50);
        wistd::function<bool (long)>::~function<bool (long)>(v68);
      }
      v51 = SetWinEventHook(0x23u, 0x23u, 0, TouchKeyboardExperienceManager::HandleUtilityChangeEvent, 0, 0, 2u);
      wil::details::unique_storage<wil::details::resource_policy<HWINEVENTHOOK__ *,int (*)(HWINEVENTHOOK__ *),&int UnhookWinEvent(HWINEVENTHOOK__ *),wistd::integral_constant<unsigned __int64,0>,HWINEVENTHOOK__ *,HWINEVENTHOOK__ *,0,std::nullptr_t>>::reset(
        (char *)this + 624,
        v51);
      if ( !*((_QWORD *)this + 78) )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1488,
          (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
          (const char *)0x80004005LL,
          phkResulte);
      v52 = SetWinEventHook(3u, 3u, 0, TouchKeyboardExperienceManager::HandleForegroundChangeEvent, 0, 0, 0);
      wil::details::unique_storage<wil::details::resource_policy<HWINEVENTHOOK__ *,int (*)(HWINEVENTHOOK__ *),&int UnhookWinEvent(HWINEVENTHOOK__ *),wistd::integral_constant<unsigned __int64,0>,HWINEVENTHOOK__ *,HWINEVENTHOOK__ *,0,std::nullptr_t>>::reset(
        (char *)this + 632,
        v52);
      if ( !*((_QWORD *)this + 79) )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x148C,
          (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
          (const char *)0x80004005LL,
          phkResultf);
      v61[0] = *((_QWORD *)this + 277) != 0;
      TouchKeyboardExperienceTelemetryLogger::TabTipAdapterInitialized<bool>(v61);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147F,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)0x8007000ELL,
        phkResultd);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1476,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)0x8007000ELL,
      phkResultd);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800d6e94  push    rbx
0x1800d6e96  push    rdi
0x1800d6e97  push    r12
0x1800d6e99  push    r13
0x1800d6e9b  push    r14
0x1800d6e9d  push    r15
0x1800d6e9f  sub     rsp, 118h
0x1800d6ea6  mov     rax, cs:__security_cookie
0x1800d6ead  xor     rax, rsp
0x1800d6eb0  mov     [rsp+148h+var_40], rax
0x1800d6eb8  mov     rdi, rcx
0x1800d6ebb  xor     r13d, r13d
0x1800d6ebe  mov     rcx, [rcx+248h]; this
0x1800d6ec5  test    rcx, rcx
0x1800d6ec8  jnz     short loc_1800D6EF3
0x1800d6eca  mov     rcx, [rsp+148h]; this
0x1800d6ed2  mov     r9d, 80004005h; char *
0x1800d6ed8  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800d6edf  mov     edx, 1423h; void *
0x1800d6ee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d6ee9  mov     eax, 80004005h
0x1800d6eee  jmp     loc_1800D7830
0x1800d6ef3  call    ?Initialize@TabTipAdapter@KeyboardHosting@@QEAAXXZ; KeyboardHosting::TabTipAdapter::Initialize(void)
0x1800d6ef8  lea     r8, [rdi+1D8h]; struct tagRECT *
0x1800d6eff  lea     rcx, [rdi+80h]; this
0x1800d6f06  xor     edx, edx; unsigned int
0x1800d6f08  call    ?WorkAreaChanged@TouchKeyboardExperienceManager@@UEAAJKPEBUtagRECT@@@Z; TouchKeyboardExperienceManager::WorkAreaChanged(ulong,tagRECT const *)
0x1800d6f0d  mov     ebx, eax
0x1800d6f0f  test    eax, eax
0x1800d6f11  jns     short loc_1800D6F36
0x1800d6f13  mov     rcx, [rsp+148h]; this
0x1800d6f1b  mov     r9d, eax; char *
0x1800d6f1e  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800d6f25  mov     edx, 1427h; void *
0x1800d6f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d6f2f  mov     eax, ebx
0x1800d6f31  jmp     loc_1800D7830
0x1800d6f36  mov     [rsp+148h+hKey], r13
0x1800d6f3b  lea     rax, [rsp+148h+hKey]
0x1800d6f40  mov     [rsp+148h+var_D8], rax
0x1800d6f45  mov     [rsp+148h+var_D0], r13
0x1800d6f4a  mov     [rsp+148h+var_C8], 1
0x1800d6f52  lea     rax, [rsp+148h+var_D0]
0x1800d6f57  mov     [rsp+148h+phkResult], rax; unsigned int
0x1800d6f5c  mov     r9d, 3; samDesired
0x1800d6f62  xor     r8d, r8d; ulOptions
0x1800d6f65  lea     r14, aSoftwareMicros_40; "SOFTWARE\\Microsoft\\TabletTip\\1.7"
0x1800d6f6c  mov     rdx, r14; lpSubKey
0x1800d6f6f  mov     r15, 0FFFFFFFF80000001h
0x1800d6f76  mov     rcx, r15; hKey
0x1800d6f79  call    cs:__imp_RegOpenKeyExW
0x1800d6f7f  mov     ebx, eax
0x1800d6f81  lea     rcx, [rsp+148h+var_D8]
0x1800d6f86  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d6f8b  test    ebx, ebx
0x1800d6f8d  jnz     short loc_1800D6FCF
0x1800d6f8f  mov     rcx, [rsp+148h+hKey]; HKEY
0x1800d6f94  call    ?SHRegValueExists@@YAHPEAUHKEY__@@PEBGPEAK@Z; SHRegValueExists(HKEY__ *,ushort const *,ulong *)
0x1800d6f99  test    eax, eax
0x1800d6f9b  jz      short loc_1800D6FCF
0x1800d6f9d  lea     rdx, aKeyboardthemeU; "KeyboardTheme_Updating"
0x1800d6fa4  mov     rcx, [rsp+148h+hKey]; hKey
0x1800d6fa9  call    cs:__imp_RegDeleteValueW
0x1800d6faf  mov     rcx, [rsp+148h]; this
0x1800d6fb7  test    eax, eax
0x1800d6fb9  jz      short loc_1800D6FCF
0x1800d6fbb  mov     r9d, eax; char *
0x1800d6fbe  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800d6fc5  mov     edx, 1430h; void *
0x1800d6fca  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800d6fcf  mov     rdx, rdi
0x1800d6fd2  lea     rcx, [rsp+148h+var_C0]
0x1800d6fda  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator &)
0x1800d6fdf  mov     rcx, [rax]
0x1800d6fe2  lea     rax, off_1807085F0
0x1800d6fe9  mov     [rsp+148h+var_B0], rax
0x1800d6ff1  mov     [rsp+148h+var_A8], rcx
0x1800d6ff9  lea     rax, [rsp+148h+var_B0]
0x1800d7001  mov     [rsp+148h+var_48], rax
0x1800d7009  mov     [rsp+148h+var_E8], r13
0x1800d700e  mov     [rsp+148h+var_F8], r13
0x1800d7013  lea     rcx, [rsp+148h+var_F8]
0x1800d7018  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d701d  mov     [rsp+148h+lpdwDisposition], r13; lpdwDisposition
0x1800d7022  mov     [rsp+148h+var_110], rax; phkResult
0x1800d7027  mov     [rsp+148h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800d702c  mov     r12d, 10h
0x1800d7032  mov     [rsp+148h+samDesired], r12d; samDesired
0x1800d7037  mov     dword ptr [rsp+148h+phkResult], r13d; int
0x1800d703c  xor     r9d, r9d; lpClass
0x1800d703f  xor     r8d, r8d; Reserved
0x1800d7042  mov     rdx, r14; lpSubKey
0x1800d7045  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d704c  call    cs:__imp_RegCreateKeyExW
0x1800d7052  test    eax, eax
0x1800d7054  jle     short loc_1800D7060
0x1800d7056  movzx   eax, ax
0x1800d7059  or      eax, 80070000h
0x1800d705e  test    eax, eax
0x1800d7060  jns     short loc_1800D706E
0x1800d7062  lea     rcx, [rsp+148h+var_F8]
0x1800d7067  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d706c  jmp     short loc_1800D7099
0x1800d706e  lea     r9, [rsp+148h+var_B8]
0x1800d7076  xor     r8d, r8d
0x1800d7079  lea     rdx, [rsp+148h+var_F8]
0x1800d707e  lea     rcx, [rsp+148h+var_E8]
0x1800d7083  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800d7088  mov     rcx, [rsp+148h+var_F8]; hKey
0x1800d708d  test    rcx, rcx
0x1800d7090  jz      short loc_1800D7099
0x1800d7092  call    cs:__imp_RegCloseKey
0x1800d7098  nop
0x1800d7099  lea     rbx, [rdi+130h]
0x1800d70a0  lea     rdx, [rsp+148h+var_E8]
0x1800d70a5  mov     rcx, rbx
0x1800d70a8  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>> &&)
0x1800d70ad  mov     rcx, [rsp+148h+var_E8]; this
0x1800d70b2  test    rcx, rcx
0x1800d70b5  jz      short loc_1800D70BC
0x1800d70b7  call    ?Release@registry_watcher_state@details@wil@@QEAAXXZ; wil::details::registry_watcher_state::Release(void)
0x1800d70bc  mov     rcx, [rsp+148h+var_48]
0x1800d70c4  test    rcx, rcx
0x1800d70c7  jz      short loc_1800D70D5
0x1800d70c9  mov     rax, [rcx]
0x1800d70cc  mov     rax, [rax+18h]
0x1800d70d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d70d5  mov     rcx, [rsp+148h]; this
0x1800d70dd  cmp     [rbx], r13
0x1800d70e0  jnz     short loc_1800D70F9
0x1800d70e2  mov     r9d, 8000FFFFh; char *
0x1800d70e8  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800d70ef  mov     edx, 143Dh; void *
0x1800d70f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d70f9  mov     rdx, rdi
0x1800d70fc  lea     rcx, [rsp+148h+var_C0]
0x1800d7104  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator &)
0x1800d7109  mov     rcx, [rax]
0x1800d710c  lea     rax, off_1807085F0
0x1800d7113  mov     [rsp+148h+var_B0], rax
0x1800d711b  mov     [rsp+148h+var_A8], rcx
0x1800d7123  lea     rax, [rsp+148h+var_B0]
0x1800d712b  mov     [rsp+148h+var_48], rax
0x1800d7133  mov     [rsp+148h+var_E8], r13
0x1800d7138  mov     [rsp+148h+var_F8], r13
0x1800d713d  lea     rcx, [rsp+148h+var_F8]
0x1800d7142  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800d7147  mov     [rsp+148h+lpdwDisposition], r13; lpdwDisposition
0x1800d714c  mov     [rsp+148h+var_110], rax; phkResult
0x1800d7151  mov     [rsp+148h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800d7156  mov     [rsp+148h+samDesired], r12d; samDesired
0x1800d715b  mov     dword ptr [rsp+148h+phkResult], r13d; int
0x1800d7160  xor     r9d, r9d; lpClass
0x1800d7163  xor     r8d, r8d; Reserved
0x1800d7166  mov     rdx, r14; lpSubKey
0x1800d7169  mov     rcx, r15; hKey
0x1800d716c  call    cs:__imp_RegCreateKeyExW
0x1800d7172  test    eax, eax
0x1800d7174  jle     short loc_1800D7180
0x1800d7176  movzx   eax, ax
0x1800d7179  or      eax, 80070000h
0x1800d717e  test    eax, eax
0x1800d7180  jns     short loc_1800D718E
0x1800d7182  lea     rcx, [rsp+148h+var_F8]
0x1800d7187  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d718c  jmp     short loc_1800D71B9
0x1800d718e  lea     r9, [rsp+148h+var_B8]
0x1800d7196  xor     r8d, r8d
0x1800d7199  lea     rdx, [rsp+148h+var_F8]
0x1800d719e  lea     rcx, [rsp+148h+var_E8]
0x1800d71a3  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800d71a8  mov     rcx, [rsp+148h+var_F8]; hKey
0x1800d71ad  test    rcx, rcx
0x1800d71b0  jz      short loc_1800D71B9
0x1800d71b2  call    cs:__imp_RegCloseKey
0x1800d71b8  nop
0x1800d71b9  lea     rbx, [rdi+138h]
0x1800d71c0  lea     rdx, [rsp+148h+var_E8]
0x1800d71c5  mov     rcx, rbx
0x1800d71c8  call    ??4?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(wil::unique_any_t<wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>> &&)
0x1800d71cd  mov     rcx, [rsp+148h+var_E8]; this
0x1800d71d2  test    rcx, rcx
0x1800d71d5  jz      short loc_1800D71DC
0x1800d71d7  call    ?Release@registry_watcher_state@details@wil@@QEAAXXZ; wil::details::registry_watcher_state::Release(void)
0x1800d71dc  mov     rcx, [rsp+148h+var_48]
0x1800d71e4  test    rcx, rcx
0x1800d71e7  jz      short loc_1800D71F5
0x1800d71e9  mov     rax, [rcx]
0x1800d71ec  mov     rax, [rax+18h]
0x1800d71f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d71f5  mov     rcx, [rsp+148h]; this
0x1800d71fd  cmp     [rbx], r13
0x1800d7200  jnz     short loc_1800D7219
0x1800d7202  mov     r9d, 8000FFFFh; char *
0x1800d7208  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800d720f  mov     edx, 1447h; void *
0x1800d7214  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d7219  mov     rcx, rdi; this
0x1800d721c  call    ?OnTabtipRegistryChanged@TouchKeyboardExperienceManager@@AEAAJXZ; TouchKeyboardExperienceManager::OnTabtipRegistryChanged(void)
0x1800d7221  mov     ebx, eax
0x1800d7223  test    eax, eax
0x1800d7225  jns     short loc_1800D725B
0x1800d7227  mov     rcx, [rsp+148h]; this
0x1800d722f  mov     r9d, eax; char *
0x1800d7232  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800d7239  mov     edx, 1448h; void *
0x1800d723e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7243  nop
0x1800d7244  mov     rcx, [rsp+148h+hKey]; hKey
0x1800d7249  test    rcx, rcx
0x1800d724c  jz      short loc_1800D7254
0x1800d724e  call    cs:__imp_RegCloseKey
0x1800d7254  mov     eax, ebx
0x1800d7256  jmp     loc_1800D7830
0x1800d725b  mov     dl, 1
0x1800d725d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PATKTI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PATKTI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PATKTI> `wil::Feature<__WilFeatureTraits_Feature_PATKTI>::GetImpl(void)'::`2'::impl
0x1800d7264  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PATKTI@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PATKTI>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800d7269  mov     rdx, rdi
0x1800d726c  lea     rcx, [rsp+148h+var_C0]
0x1800d7274  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator &)
0x1800d7279  mov     rcx, [rax]
0x1800d727c  lea     rax, off_180708618
0x1800d7283  mov     [rsp+148h+var_B0], rax
0x1800d728b  mov     [rsp+148h+var_A8], rcx
0x1800d7293  lea     rax, [rsp+148h+var_B0]
0x1800d729b  mov     [rsp+148h+var_48], rax
0x1800d72a3  mov     [rsp+148h+var_F8], r13
0x1800d72a8  lea     r9, [rsp+148h+var_F8]
0x1800d72ad  lea     rdx, [rsp+148h+var_B8]
0x1800d72b5  call    ??$make_wnf_subscription_state@_N@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEB_N@Z@wistd@@KPEAPEAU?$wnf_subscription_state@_N@01@@Z; wil::details::make_wnf_subscription_state<bool>(_WNF_STATE_NAME const &,wistd::function<void (bool const &)> &&,ulong,wil::details::wnf_subscription_state<bool> * *)
0x1800d72ba  mov     rcx, r13
0x1800d72bd  test    eax, eax
0x1800d72bf  cmovns  rcx, [rsp+148h+var_F8]
0x1800d72c5  mov     [rsp+148h+var_F8], rcx
0x1800d72ca  lea     r12, [rdi+8A8h]
0x1800d72d1  lea     rdx, [rsp+148h+var_F8]
0x1800d72d6  mov     rcx, r12
0x1800d72d9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x1800d72de  mov     rcx, [rsp+148h+var_F8]; this
0x1800d72e3  test    rcx, rcx
0x1800d72e6  jz      short loc_1800D72ED
0x1800d72e8  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x1800d72ed  mov     rcx, [rsp+148h+var_48]
0x1800d72f5  test    rcx, rcx
0x1800d72f8  jz      short loc_1800D7306
0x1800d72fa  mov     rax, [rcx]
0x1800d72fd  mov     rax, [rax+18h]
0x1800d7301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7306  lea     rbx, [rdi+888h]
0x1800d730d  mov     rdx, rdi
0x1800d7310  lea     rcx, [rsp+148h+var_C0]
0x1800d7318  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator &)
0x1800d731d  mov     r14, [rax]
0x1800d7320  mov     ecx, 18h; Size
0x1800d7325  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d732a  mov     rdx, rax
0x1800d732d  lea     rcx, [rax+8]; this
0x1800d7331  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x1800d7336  mov     [rdx+10h], r14
0x1800d733a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800d7341  lea     rax, off_180708640
0x1800d7348  mov     [rdx], rax
0x1800d734b  mov     [rsp+148h+var_F8], rdx
0x1800d7350  lea     r9, [rsp+148h+var_F8]
0x1800d7355  lea     rdx, [rsp+148h+var_D8]
0x1800d735a  mov     rcx, rbx
0x1800d735d  call    ?VirtualDesktopDataSourceChanged@?$consume_Windows_Internal_ComposableShell_Multitasking_IVirtualDesktopDataSource@UIVirtualDesktopDataSource@Multitasking@ComposableShell@Internal@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$TypedEventHandler@UIVirtualDesktopDataSource@Multitasking@ComposableShell@Internal@Windows@winrt@@UIVirtualDesktopDataSourceChangedEventArgs@23456@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Internal_ComposableShell_Multitasking_IVirtualDesktopDataSource<winrt::Windows::Internal::ComposableShell::Multitasking::IVirtualDesktopDataSource>::VirtualDesktopDataSourceChanged(winrt::auto_revoke_t,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::ComposableShell::Multitasking::IVirtualDesktopDataSource,winrt::Windows::Internal::ComposableShell::Multitasking::IVirtualDesktopDataSourceChangedEventArgs> const &)
0x1800d7362  lea     rcx, [rdi+890h]
0x1800d7369  mov     rdx, rax
0x1800d736c  call    ??4?$event_revoker@UITapInvokeSetting@TouchKeyboard@Shell@Internal@Windows@winrt@@$MP8type@?$abi@UITapInvokeSetting@TouchKeyboard@Shell@Internal@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BFA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x1800d7371  mov     rax, [rsp+148h+var_D8]
0x1800d7376  test    rax, rax
0x1800d7379  jz      short loc_1800D73AC
0x1800d737b  lea     rdx, [rsp+148h+var_E8]
0x1800d7380  lea     rcx, [rsp+148h+var_D8]
0x1800d7385  call    ?get@?$weak_ref@UITapInvokeSetting@TouchKeyboard@Shell@Internal@Windows@winrt@@@winrt@@QEBA@XZ; winrt::weak_ref<winrt::Windows::Internal::Shell::TouchKeyboard::ITapInvokeSetting>::get(void)
0x1800d738a  mov     rdx, rax
0x1800d738d  lea     rcx, [rsp+148h+var_D8]
0x1800d7392  call    ?revoke_impl@?$event_revoker@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BFA@AA@impl@winrt@@AEAAXUIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@3@@Z
0x1800d7397  mov     rax, [rsp+148h+var_D8]
0x1800d739c  test    rax, rax
0x1800d739f  jz      short loc_1800D73AC
0x1800d73a1  lea     rcx, [rsp+148h+var_D8]
0x1800d73a6  call    ?unconditional_release_ref@?$com_ptr@UAppBackupListener@implementation@Shell@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(void)
0x1800d73ab  nop
0x1800d73ac  lea     rcx, [rsp+148h+var_F8]
0x1800d73b1  call    ?unconditional_release_ref@?$com_ptr@UAppBackupListener@implementation@Shell@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(void)
0x1800d73b6  mov     rcx, rbx
0x1800d73b9  call    ?View@?$consume_WindowsUdk_UI_Shell_IViewVisibilityChangedEventArgs@UIViewVisibilityChangedEventArgs@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_Shell_IViewVisibilityChangedEventArgs<winrt::WindowsUdk::UI::Shell::IViewVisibilityChangedEventArgs>::View(void)
0x1800d73be  mov     edx, eax
0x1800d73c0  mov     rcx, rdi
0x1800d73c3  call    ?OnTapInvokeEffectiveSettingChanged@TouchKeyboardExperienceManager@@AEAAXW4TapInvokeSettingValue@TouchKeyboard@Shell@Internal@Windows@winrt@@@Z; TouchKeyboardExperienceManager::OnTapInvokeEffectiveSettingChanged(winrt::Windows::Internal::Shell::TouchKeyboard::TapInvokeSettingValue)
0x1800d73c8  mov     rdx, rdi
0x1800d73cb  lea     rcx, [rsp+148h+var_C0]
0x1800d73d3  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@V?$map@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@URemoteSystem@Shell@Internal@Windows@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem,std::map<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Internal::Shell::RemoteSystem>,winrt::impl::collection_version>::iterator &)
0x1800d73d8  mov     rcx, [rax]
0x1800d73db  lea     rax, off_1807152D0
0x1800d73e2  mov     [rsp+148h+var_B0], rax
0x1800d73ea  mov     [rsp+148h+var_A8], rcx
0x1800d73f2  lea     rax, [rsp+148h+var_B0]
  ... truncated ...
```
