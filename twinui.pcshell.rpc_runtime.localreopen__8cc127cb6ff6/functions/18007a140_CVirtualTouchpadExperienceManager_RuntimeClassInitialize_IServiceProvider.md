# CVirtualTouchpadExperienceManager::RuntimeClassInitialize(IServiceProvider *)

- ea: `0x18007a140`
- end: `0x18007a927`
- name: `?RuntimeClassInitialize@CVirtualTouchpadExperienceManager@@QEAAJPEAUIServiceProvider@@@Z`
- size: `2023`
- prototype: `int(CVirtualTouchpadExperienceManager *__hidden this, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ba2c`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180024b80`
- `0x180026e04`
- `0x18004a440`
- `0x18004baf0`
- `0x180053bcc`
- `0x18006c8d0`
- `0x18006e370`
- `0x180071c68`
- `0x1800726b8`
- `0x18007a140`
- `0x18007aaa0`
- `0x18007be08`
- `0x18007f488`
- `0x1800d5610`
- `0x1800d7ecc`
- `0x1800d7f24`
- `0x1800e5d24`
- `0x1800e7720`
- `0x1800e817c`
- `0x1800e93dc`
- `0x1800e9464`
- `0x1800e9554`
- `0x1800e9640`
- `0x1801c9a58`
- `0x18027f144`
- `0x18027f5ac`
- `0x18027f9f0`
- `0x18027fa64`
- `0x1802b2cd4`
- `0x1802bbaf8`
- `0x1802da538`
- `0x1802dd470`
- `0x180356360`
- `0x180356384`
- `0x1803886b4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a5b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a5d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a62c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a5b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a5d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a62c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a1a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a1f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a280`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a1a7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a1f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a26a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a1da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007a26a`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007a478`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18007a478`
- `ntdll!NtQueryWnfStateData` at `0x18007a3dc`
- `ntdll!NtQueryWnfStateData` at `0x18007a3dc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007a574`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007a574`

## string_xrefs

- `0x18007a56d`: `user32.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CVirtualTouchpadExperienceManager::RuntimeClassInitialize(
        CVirtualTouchpadExperienceManager *this,
        struct IServiceProvider *a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  HRESULT v6; // eax
  int LastError; // ebx
  __int64 v8; // rdx
  HRESULT v10; // eax
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rdi
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  wil::details *v15; // r14
  void *v16; // rax
  wil::details *v17; // rdi
  __int64 v18; // r8
  int v19; // ebx
  int v20; // ebx
  struct wil::details::wnf_subscription_state_base *v21; // rdx
  HMODULE *v22; // rbx
  HMODULE LibraryW; // rax
  const char *v24; // r9
  FARPROC ProcAddress; // rax
  FARPROC v26; // rax
  FARPROC v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  const char *v40; // r9
  void (*v41)(void); // rax
  int v42; // [rsp+20h] [rbp-148h]
  wil::details *v43; // [rsp+40h] [rbp-128h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-120h] BYREF
  __int64 v45; // [rsp+50h] [rbp-118h] BYREF
  _QWORD v46[2]; // [rsp+58h] [rbp-110h] BYREF
  wil::details *v47; // [rsp+68h] [rbp-100h] BYREF
  CVirtualTouchpadExperienceManager *v48; // [rsp+70h] [rbp-F8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-F0h] BYREF
  HSTRING string; // [rsp+90h] [rbp-D8h] BYREF
  HSTRING_HEADER v51; // [rsp+98h] [rbp-D0h] BYREF
  HSTRING v52; // [rsp+B0h] [rbp-B8h] BYREF
  char v53[8]; // [rsp+B8h] [rbp-B0h] BYREF
  char v54[104]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v55; // [rsp+128h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.ShellExperience.VirtualTouchpad", 0x30u, &hstringHeader, &string);
  if ( v4 < 0 )
    RaiseException(v4, 1u, 0, 0);
  v5 = string;
  v52 = 0;
  v6 = WindowsCreateStringReference(L"Microsoft.Windows.ShellExperienceHost_cw5n1h2txyewy!App", 0x37u, &v51, &v52);
  if ( v6 < 0 )
    RaiseException(v6, 1u, 0, 0);
  LastError = CSingleViewShellExperience::RuntimeClassInitialize(
                (CVirtualTouchpadExperienceManager *)((char *)this + 64),
                (struct IWeakReferenceSource *)(((unsigned __int64)this + 8)
                                              & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                a2,
                v52,
                v5);
  if ( LastError < 0 )
  {
    v8 = 214;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\touchpadcontrollerexperiencemanager.cpp",
      (const char *)(unsigned int)LastError,
      v42);
    return (unsigned int)LastError;
  }
  string = 0;
  v10 = WindowsCreateStringReference(L"ShellExperienceHostVS_ccv6fwk6gx0xp!App", 0x27u, &hstringHeader, &string);
  if ( v10 < 0 )
    RaiseException(v10, 1u, 0, 0);
  LastError = CSingleViewShellExperience::AddTestAumid((CVirtualTouchpadExperienceManager *)((char *)this + 64), string);
  if ( LastError < 0 )
  {
    v8 = 215;
    goto LABEL_7;
  }
  *((_DWORD *)this + 31) = 2;
  QueryService = a2->lpVtbl->QueryService;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 336);
  LastError = ((__int64 (__fastcall *)(struct IServiceProvider *, GUID *, GUID *, char *))QueryService)(
                a2,
                &GUID_d8c26227_b75e_4d8b_ac8c_c463a34ed11e,
                &GUID_d8c26227_b75e_4d8b_ac8c_c463a34ed11e,
                (char *)this + 336);
  if ( LastError < 0 )
  {
    v8 = 221;
    goto LABEL_7;
  }
  v48 = this;
  (*(void (__fastcall **)(CVirtualTouchpadExperienceManager *))(*(_QWORD *)this + 8LL))(this);
  v47 = 0;
  v12 = AgileGitPtr::Initialize<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(&v47, &v48);
  LastError = v12;
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
    v14 = 225;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\touchpadcontrollerexperiencemanager.cpp",
      (const char *)v13,
      v42);
    goto LABEL_50;
  }
  v43 = v47;
  if ( v47 )
    (*(void (__fastcall **)(wil::details *))(*(_QWORD *)v47 + 8LL))(v47);
  v55 = 0;
  v55 = wistd::__function::__func__lambda_717e164a524f047529d307b394259e9b__void___cdecl_unsigned_long_const____::__func__lambda_717e164a524f047529d307b394259e9b__void___cdecl_unsigned_long_const____(
          v54,
          &v43);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v43);
  v44 = 0;
  v15 = 0;
  v16 = operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  if ( v16
    && (v17 = (wil::details *)wil::details::wnf_subscription_state<unsigned long>::wnf_subscription_state<unsigned long>(
                                v16,
                                v53)) != 0 )
  {
    v18 = v44;
    if ( v44 == -1 )
    {
      LODWORD(v45) = 0;
      v19 = NtQueryWnfStateData(&WNF_SHEL_LOCKSCREEN_ACTIVE, 0, 0, &v44) | 0x10000000;
      if ( (int)(v19 + 0x80000000) >= 0 && v19 != -805306333 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
          (const char *)(unsigned int)v19,
          0);
LABEL_25:
        (**(void (__fastcall ***)(wil::details *, __int64))v17)(v17, 1);
        goto LABEL_33;
      }
      v18 = v44;
    }
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v17 + 8;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v42 = (int)v17;
    v20 = RtlSubscribeWnfStateChangeNotification(
            &hstringHeader.Reserved.Reserved2[8],
            WNF_SHEL_LOCKSCREEN_ACTIVE,
            v18,
            _lambda_a14e49ce427a1853f087bba834558a2c_::_lambda_invoker_cdecl_);
    if ( hstringHeader.Reserved.Reserved2[16] )
      wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(
        hstringHeader.Reserved.Reserved1,
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
    if ( v20 < 0 )
    {
      v19 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x3C7,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
              (const char *)(unsigned int)v20,
              (int)v17);
      goto LABEL_25;
    }
    v15 = v17;
    v19 = 0;
  }
  else
  {
    v19 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
      (const char *)0x8007000ELL,
      v42);
  }
LABEL_33:
  if ( v19 < 0 )
    v15 = 0;
  v43 = v15;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 784,
    &v43);
  if ( v43 )
    wil::details::delete_wnf_subscription_state(v43, v21);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 24LL))(v55);
  if ( !*((_QWORD *)this + 98) )
  {
    LastError = -2147467259;
    v14 = 240;
LABEL_48:
    v13 = (unsigned int)LastError;
    goto LABEL_49;
  }
  Microsoft::WRL::ComPtr<IDWriteTextFormat>::operator=((char *)this + 272, this);
  Microsoft::WRL::ComPtr<IDWriteTextFormat>::operator=((char *)this + 328, a2);
  v22 = (HMODULE *)((char *)this + 792);
  LibraryW = LoadLibraryW(L"user32.DLL");
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    (char *)this + 792,
    LibraryW);
  if ( !*((_QWORD *)this + 99) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF7,
                  (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\touchpadcontrollerexperiencemanager.cpp",
                  v24);
LABEL_50:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    return (unsigned int)LastError;
  }
  ProcAddress = GetProcAddress(*((HMODULE *)this + 99), "SetPhysicalCursorPos");
  *((_QWORD *)this + 100) = ProcAddress;
  if ( !ProcAddress )
  {
    v14 = 250;
LABEL_47:
    LastError = -2147024769;
    goto LABEL_48;
  }
  v26 = GetProcAddress(*v22, "CalculatePopupWindowPosition");
  *((_QWORD *)this + 101) = v26;
  if ( !v26 )
  {
    v14 = 253;
    goto LABEL_47;
  }
  v27 = GetProcAddress(*v22, "GetPhysicalCursorPos");
  *((_QWORD *)this + 102) = v27;
  if ( !v27 )
  {
    LastError = -2147024769;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\touchpadcontrollerexperiencemanager.cpp",
      (const char *)0x8007007FLL,
      v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    (*(void (__fastcall **)(CVirtualTouchpadExperienceManager *))(*(_QWORD *)this + 16LL))(this);
    return (unsigned int)LastError;
  }
  *(_OWORD *)&v51.Reserved.Reserved1 = 0;
  try
  {
    winrt::impl::resume_apartment_context::resume_apartment_context((winrt::impl::resume_apartment_context *)&v51);
    winrt::impl::resume_apartment_context::operator=((char *)this + 872, &v51);
    if ( v51.Reserved.Reserved1 )
      winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(&v51);
    v44 = 22;
    v46[0] = &v44;
    v51.Reserved.Reserved1 = &qword_1808D8918;
    _InterlockedIncrement64(&qword_1808D8918);
    if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory> )
    {
      winrt::impl::consume_WindowsUdk_UI_Shell_IShellViewCoordinatorFactory<winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::CreateInstance(
        &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>,
        &v43,
        &v44);
      _InterlockedDecrement64(&qword_1808D8918);
    }
    else
    {
      _InterlockedDecrement64(&qword_1808D8918);
      winrt::impl::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::call<_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_ &>(
        v28,
        &v43,
        v46);
    }
    winrt::WindowsUdk::UI::Shell::ShellViewCoordinator::operator=((char *)this + 832, &v43);
    if ( v43 )
      winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(&v43);
    v45 = 0;
    v46[0] = &v45;
    v29 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v46);
    v30 = Microsoft::WRL::AsWeak<CVirtualTouchpadExperienceManager>(this, v29);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\touchpadcontrollerexperiencemanager.cpp",
        (const char *)(unsigned int)v30,
        v42);
    v31 = lambda_66a952acffac4749430ca95fe1c551e0_::_lambda_66a952acffac4749430ca95fe1c551e0_(
            &hstringHeader,
            this,
            &v45);
    winrt::Windows::Foundation::TypedEventHandler_winrt::WindowsUdk::UI::Shell::ShellViewCoordinator_winrt::WindowsUdk::UI::Shell::ShowShellViewRequestedEventArgs_::TypedEventHandler_winrt::WindowsUdk::UI::Shell::ShellViewCoordinator_winrt::WindowsUdk::UI::Shell::ShowShellViewRequestedEventArgs___lambda_341c9eb6bde2f5519c2c695a2218853a___(
      &v43,
      v31);
    v33 = winrt::impl::consume_WindowsUdk_UI_Shell_IShellViewCoordinator<winrt::WindowsUdk::UI::Shell::IShellViewCoordinator>::ShowRequested(
            (char *)this + 832,
            v46,
            v32,
            &v43);
    __4__event_revoker_UIShellViewCoordinator_Shell_UI_WindowsUdk_winrt___MP8type___abi_UIShellViewCoordinator_Shell_UI_WindowsUdk_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
      (char *)this + 840,
      v33);
    if ( v46[0] )
    {
      v34 = winrt::weak_ref<winrt::WindowsUdk::UI::Shell::IShellViewCoordinator>::get(v46, &v51);
      _revoke_impl___event_revoker_UIShellViewCoordinator_Shell_UI_WindowsUdk_winrt___MP8type___abi_UIShellViewCoordinator_Shell_UI_WindowsUdk_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BDI_AA_impl_winrt__AEAAXUIShellViewCoordinator_Shell_UI_WindowsUdk_3__Z(
        v46,
        v34);
      if ( v46[0] )
        winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(v46);
    }
    if ( v43 )
      winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(&v43);
    v35 = lambda_66a952acffac4749430ca95fe1c551e0_::_lambda_66a952acffac4749430ca95fe1c551e0_(
            &hstringHeader,
            this,
            &v45);
    winrt::Windows::Foundation::TypedEventHandler_winrt::WindowsUdk::UI::Shell::ShellViewCoordinator_winrt::WindowsUdk::UI::Shell::DismissShellViewRequestedEventArgs_::TypedEventHandler_winrt::WindowsUdk::UI::Shell::ShellViewCoordinator_winrt::WindowsUdk::UI::Shell::DismissShellViewRequestedEventArgs___lambda_66a952acffac4749430ca95fe1c551e0___(
      &v43,
      v35);
    v37 = winrt::impl::consume_WindowsUdk_UI_Shell_IShellViewCoordinator<winrt::WindowsUdk::UI::Shell::IShellViewCoordinator>::DismissRequested(
            (char *)this + 832,
            v46,
            v36,
            &v43);
    __4__event_revoker_UIShellViewCoordinator_Shell_UI_WindowsUdk_winrt___MP8type___abi_UIShellViewCoordinator_Shell_UI_WindowsUdk_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
      (char *)this + 856,
      v37);
    if ( v46[0] )
    {
      v38 = winrt::weak_ref<winrt::WindowsUdk::UI::Shell::IShellViewCoordinator>::get(v46, &v51);
      _revoke_impl___event_revoker_UISnapLayoutPickerExtension2_Shell_UI_WindowsUdk_winrt___MP8type___abi_UISnapLayoutPickerExtension2_Shell_UI_WindowsUdk_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEI_AA_impl_winrt__AEAAXUISnapLayoutPickerExtension2_Shell_UI_WindowsUdk_3__Z(
        v46,
        v38);
      if ( v46[0] )
        winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(v46);
    }
    if ( v43 )
      winrt::com_ptr<winrt::Windows::Internal::Shell::implementation::AppBackupListener>::unconditional_release_ref(&v43);
    v39 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v41 = *(void (**)(void))(*(_QWORD *)this + 16LL);
  }
  catch ( ... )
  {
    LODWORD(v45) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x11B,
                     (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\touchpadcontrollerexperiencemanager.cpp",
                     v40);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v47);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    return (unsigned int)v45;
  }
  v41();
  return 0;
}

```

## disassembly

```asm
0x18007a140  mov     [rsp+arg_10], rbx
0x18007a145  push    rsi
0x18007a146  push    rdi
0x18007a147  push    r12
0x18007a149  push    r14
0x18007a14b  push    r15
0x18007a14d  sub     rsp, 140h
0x18007a154  mov     rax, cs:__security_cookie
0x18007a15b  xor     rax, rsp
0x18007a15e  mov     [rsp+168h+var_38], rax
0x18007a166  mov     r15, rdx
0x18007a169  mov     rsi, rcx
0x18007a16c  xor     r12d, r12d
0x18007a16f  mov     [rsp+168h+string], r12
0x18007a177  lea     r9, [rsp+168h+string]; string
0x18007a17f  lea     r8, [rsp+168h+hstringHeader]; hstringHeader
0x18007a184  lea     edx, [r12+30h]; length
0x18007a189  lea     rcx, aWindowsInterna_36; "Windows.Internal.ShellExperience.Virtua"...
0x18007a190  call    cs:__imp_WindowsCreateStringReference
0x18007a196  test    eax, eax
0x18007a198  jns     short loc_18007A1AE
0x18007a19a  xor     r9d, r9d; lpArguments
0x18007a19d  xor     r8d, r8d; nNumberOfArguments
0x18007a1a0  lea     edx, [r12+1]; dwExceptionFlags
0x18007a1a5  mov     ecx, eax; dwExceptionCode
0x18007a1a7  call    cs:__imp_RaiseException
0x18007a1ad  nop
0x18007a1ae  mov     rbx, [rsp+168h+string]
0x18007a1b6  mov     [rsp+168h+var_B8], r12
0x18007a1be  lea     r9, [rsp+168h+var_B8]; string
0x18007a1c6  lea     r8, [rsp+168h+var_D0]; hstringHeader
0x18007a1ce  mov     edx, 37h ; '7'; length
0x18007a1d3  lea     rcx, aMicrosoftWindo_2; "Microsoft.Windows.ShellExperienceHost_c"...
0x18007a1da  call    cs:__imp_WindowsCreateStringReference
0x18007a1e0  test    eax, eax
0x18007a1e2  jns     short loc_18007A1F7
0x18007a1e4  xor     r9d, r9d; lpArguments
0x18007a1e7  xor     r8d, r8d; nNumberOfArguments
0x18007a1ea  lea     edx, [r9+1]; dwExceptionFlags
0x18007a1ee  mov     ecx, eax; dwExceptionCode
0x18007a1f0  call    cs:__imp_RaiseException
0x18007a1f6  nop
0x18007a1f7  mov     rax, rsi
0x18007a1fa  lea     rcx, [rsi+8]
0x18007a1fe  neg     rax
0x18007a201  sbb     rdx, rdx
0x18007a204  and     rdx, rcx; struct IWeakReferenceSource *
0x18007a207  mov     [rsp+168h+var_148], rbx; int
0x18007a20c  mov     r9, [rsp+168h+var_B8]; HSTRING
0x18007a214  mov     r8, r15; struct IServiceProvider *
0x18007a217  lea     rcx, [rsi+40h]; this
0x18007a21b  call    ?RuntimeClassInitialize@CSingleViewShellExperience@@QEAAJPEAUIWeakReferenceSource@@PEAUIServiceProvider@@PEAUHSTRING__@@2@Z; CSingleViewShellExperience::RuntimeClassInitialize(IWeakReferenceSource *,IServiceProvider *,HSTRING__ *,HSTRING__ *)
0x18007a220  mov     ebx, eax
0x18007a222  test    eax, eax
0x18007a224  jns     short loc_18007A249
0x18007a226  mov     edx, 0D6h; void *
0x18007a22b  mov     rcx, [rsp+168h]; this
0x18007a233  mov     r9d, ebx; char *
0x18007a236  lea     r8, aPcshellTwinuiE_22; "pcshell\\twinui\\experiencemanagers\\li"...
0x18007a23d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a242  mov     eax, ebx
0x18007a244  jmp     loc_18007A8FF
0x18007a249  mov     [rsp+168h+string], r12
0x18007a251  lea     r9, [rsp+168h+string]; string
0x18007a259  lea     r8, [rsp+168h+hstringHeader]; hstringHeader
0x18007a25e  mov     edx, 27h ; '''; length
0x18007a263  lea     rcx, aShellexperienc_1; "ShellExperienceHostVS_ccv6fwk6gx0xp!App"
0x18007a26a  call    cs:__imp_WindowsCreateStringReference
0x18007a270  test    eax, eax
0x18007a272  jns     short loc_18007A287
0x18007a274  xor     r9d, r9d; lpArguments
0x18007a277  xor     r8d, r8d; nNumberOfArguments
0x18007a27a  lea     edx, [r9+1]; dwExceptionFlags
0x18007a27e  mov     ecx, eax; dwExceptionCode
0x18007a280  call    cs:__imp_RaiseException
0x18007a286  nop
0x18007a287  mov     rdx, [rsp+168h+string]; HSTRING
0x18007a28f  lea     rcx, [rsi+40h]; this
0x18007a293  call    ?AddTestAumid@CSingleViewShellExperience@@QEAAJPEAUHSTRING__@@@Z; CSingleViewShellExperience::AddTestAumid(HSTRING__ *)
0x18007a298  mov     ebx, eax
0x18007a29a  test    eax, eax
0x18007a29c  jns     short loc_18007A2A5
0x18007a29e  mov     edx, 0D7h
0x18007a2a3  jmp     short loc_18007A22B
0x18007a2a5  mov     dword ptr [rsi+7Ch], 2
0x18007a2ac  mov     rax, [r15]
0x18007a2af  mov     rdi, [rax+18h]
0x18007a2b3  lea     rbx, [rsi+150h]
0x18007a2ba  mov     rcx, rbx
0x18007a2bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a2c2  mov     r9, rbx
0x18007a2c5  lea     rdx, _GUID_d8c26227_b75e_4d8b_ac8c_c463a34ed11e
0x18007a2cc  mov     r8, rdx
0x18007a2cf  mov     rcx, r15
0x18007a2d2  mov     rax, rdi
0x18007a2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2da  mov     ebx, eax
0x18007a2dc  test    eax, eax
0x18007a2de  jns     short loc_18007A2EA
0x18007a2e0  mov     edx, 0DDh
0x18007a2e5  jmp     loc_18007A22B
0x18007a2ea  mov     [rsp+168h+var_F8], rsi
0x18007a2ef  mov     rax, [rsi]
0x18007a2f2  mov     rcx, rsi
0x18007a2f5  mov     rax, [rax+8]
0x18007a2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2fe  nop
0x18007a2ff  mov     [rsp+168h+var_100], r12
0x18007a304  lea     rdx, [rsp+168h+var_F8]
0x18007a309  lea     rcx, [rsp+168h+var_100]
0x18007a30e  call    ??$Initialize@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@AgileGitPtr@@QEAAJAEBV?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Z; AgileGitPtr::Initialize<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager> const &)
0x18007a313  mov     ebx, eax
0x18007a315  test    eax, eax
0x18007a317  jns     short loc_18007A326
0x18007a319  mov     r9d, eax
0x18007a31c  mov     edx, 0E1h
0x18007a321  jmp     loc_18007A5F3
0x18007a326  mov     rcx, [rsp+168h+var_100]
0x18007a32b  mov     [rsp+168h+var_128], rcx
0x18007a330  test    rcx, rcx
0x18007a333  jz      short loc_18007A342
0x18007a335  mov     rax, [rcx]
0x18007a338  mov     rax, [rax+8]
0x18007a33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a341  nop
0x18007a342  mov     [rsp+168h+var_40], r12
0x18007a34a  lea     rdx, [rsp+168h+var_128]
0x18007a34f  lea     rcx, [rsp+168h+var_A8]
0x18007a357  call    wistd____function____func__lambda_717e164a524f047529d307b394259e9b__void___cdecl_unsigned_long_const________func__lambda_717e164a524f047529d307b394259e9b__void___cdecl_unsigned_long_const____
0x18007a35c  mov     [rsp+168h+var_40], rax
0x18007a364  lea     rcx, [rsp+168h+var_128]; void *
0x18007a369  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x18007a36e  mov     [rsp+168h+var_120], r12d
0x18007a373  mov     r14, r12
0x18007a376  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007a37d  mov     ecx, 88h; unsigned __int64
0x18007a382  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007a387  test    rax, rax
0x18007a38a  jz      loc_18007A4CB
0x18007a390  lea     rdx, [rsp+168h+var_B0]
0x18007a398  mov     rcx, rax
0x18007a39b  call    ??0?$wnf_subscription_state@K@details@wil@@QEAA@$$QEAV?$function@$$A6AXAEBK@Z@wistd@@@Z; wil::details::wnf_subscription_state<ulong>::wnf_subscription_state<ulong>(wistd::function<void (ulong const &)> &&)
0x18007a3a0  mov     rdi, rax
0x18007a3a3  test    rax, rax
0x18007a3a6  jz      loc_18007A4CB
0x18007a3ac  mov     r8d, [rsp+168h+var_120]
0x18007a3b1  cmp     r8d, 0FFFFFFFFh
0x18007a3b5  jnz     short loc_18007A435
0x18007a3b7  mov     dword ptr [rsp+168h+var_118], r12d
0x18007a3bc  lea     rax, [rsp+168h+var_118]
0x18007a3c1  mov     [rsp+168h+var_140], rax
0x18007a3c6  mov     [rsp+168h+var_148], r12; int
0x18007a3cb  lea     r9, [rsp+168h+var_120]
0x18007a3d0  xor     r8d, r8d
0x18007a3d3  xor     edx, edx
0x18007a3d5  lea     rcx, WNF_SHEL_LOCKSCREEN_ACTIVE
0x18007a3dc  call    cs:__imp_NtQueryWnfStateData
0x18007a3e2  mov     ebx, eax
0x18007a3e4  bts     ebx, 1Ch
0x18007a3e8  mov     eax, 80000000h
0x18007a3ed  lea     ecx, [rbx+rax]
0x18007a3f0  test    eax, ecx
0x18007a3f2  jnz     short loc_18007A430
0x18007a3f4  cmp     ebx, 0D0000023h
0x18007a3fa  jz      short loc_18007A430
0x18007a3fc  mov     rcx, [rsp+168h]; this
0x18007a404  mov     r9d, ebx; char *
0x18007a407  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18007a40e  mov     edx, 3B8h; void *
0x18007a413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a418  mov     rax, [rdi]
0x18007a41b  mov     edx, 1
0x18007a420  mov     rcx, rdi
0x18007a423  mov     rax, [rax]
0x18007a426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a42b  jmp     loc_18007A4ED
0x18007a430  mov     r8d, [rsp+168h+var_120]
0x18007a435  lea     rax, [rdi+8]
0x18007a439  mov     qword ptr [rsp+168h+hstringHeader.Reserved], rax
0x18007a43e  mov     qword ptr [rsp+168h+hstringHeader.Reserved+8], r12
0x18007a446  mov     byte ptr [rsp+168h+hstringHeader.Reserved+10h], 1
0x18007a44e  mov     [rsp+168h+var_130], r12d
0x18007a453  mov     [rsp+168h+var_138], r12d
0x18007a458  mov     [rsp+168h+var_140], r12
0x18007a45d  mov     [rsp+168h+var_148], rdi; int
0x18007a462  lea     r9, ?_lambda_invoker_cdecl_@_lambda_a14e49ce427a1853f087bba834558a2c_@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; _lambda_a14e49ce427a1853f087bba834558a2c_::_lambda_invoker_cdecl_(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18007a469  mov     rdx, cs:WNF_SHEL_LOCKSCREEN_ACTIVE
0x18007a470  lea     rcx, [rsp+168h+hstringHeader.Reserved+8]
0x18007a478  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18007a47e  mov     ebx, eax
0x18007a480  cmp     byte ptr [rsp+168h+hstringHeader.Reserved+10h], r12b
0x18007a488  jz      short loc_18007A49C
0x18007a48a  mov     rdx, qword ptr [rsp+168h+hstringHeader.Reserved+8]
0x18007a492  mov     rcx, qword ptr [rsp+168h+hstringHeader.Reserved]
0x18007a497  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_WNF_USER_SUBSCRIPTION@@P6AJPEAU1@@Z$1?RtlUnsubscribeWnfStateChangeNotification@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_WNF_USER_SUBSCRIPTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(_WNF_USER_SUBSCRIPTION *)
0x18007a49c  test    ebx, ebx
0x18007a49e  jns     short loc_18007A4C3
0x18007a4a0  mov     rcx, [rsp+168h]; this
0x18007a4a8  mov     r9d, ebx; char *
0x18007a4ab  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18007a4b2  mov     edx, 3C7h; void *
0x18007a4b7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007a4bc  mov     ebx, eax
0x18007a4be  jmp     loc_18007A418
0x18007a4c3  mov     r14, rdi
0x18007a4c6  mov     ebx, r12d
0x18007a4c9  jmp     short loc_18007A4ED
0x18007a4cb  mov     rcx, [rsp+168h]; this
0x18007a4d3  mov     ebx, 8007000Eh
0x18007a4d8  mov     r9d, ebx; char *
0x18007a4db  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x18007a4e2  mov     edx, 3B1h; void *
0x18007a4e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a4ec  nop
0x18007a4ed  test    ebx, ebx
0x18007a4ef  cmovs   r14, r12
0x18007a4f3  mov     [rsp+168h+var_128], r14
0x18007a4f8  lea     rbx, [rsi+310h]
0x18007a4ff  lea     rdx, [rsp+168h+var_128]
0x18007a504  mov     rcx, rbx
0x18007a507  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18007a50c  mov     rcx, [rsp+168h+var_128]; this
0x18007a511  test    rcx, rcx
0x18007a514  jz      short loc_18007A51B
0x18007a516  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18007a51b  mov     rcx, [rsp+168h+var_40]
0x18007a523  test    rcx, rcx
0x18007a526  jz      short loc_18007A534
0x18007a528  mov     rax, [rcx]
0x18007a52b  mov     rax, [rax+18h]
0x18007a52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a534  cmp     [rbx], r12
0x18007a537  jnz     short loc_18007A548
0x18007a539  mov     ebx, 80004005h
0x18007a53e  mov     edx, 0F0h
0x18007a543  jmp     loc_18007A5F0
0x18007a548  lea     rcx, [rsi+110h]
0x18007a54f  mov     rdx, rsi
0x18007a552  call    ??4?$ComPtr@UIDWriteTextFormat@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDWriteTextFormat@@@Z; Microsoft::WRL::ComPtr<IDWriteTextFormat>::operator=(IDWriteTextFormat *)
0x18007a557  lea     rcx, [rsi+148h]
0x18007a55e  mov     rdx, r15
0x18007a561  call    ??4?$ComPtr@UIDWriteTextFormat@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDWriteTextFormat@@@Z; Microsoft::WRL::ComPtr<IDWriteTextFormat>::operator=(IDWriteTextFormat *)
0x18007a566  lea     rbx, [rsi+318h]
0x18007a56d  lea     rcx, LibFileName; "user32.DLL"
0x18007a574  call    cs:__imp_LoadLibraryW
0x18007a57a  mov     rdx, rax
0x18007a57d  mov     rcx, rbx
0x18007a580  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18007a585  mov     rcx, [rbx]; hModule
0x18007a588  test    rcx, rcx
0x18007a58b  jnz     short loc_18007A5AA
0x18007a58d  mov     rcx, [rsp+168h]; this
0x18007a595  lea     r8, aPcshellTwinuiE_22; "pcshell\\twinui\\experiencemanagers\\li"...
0x18007a59c  mov     edx, 0F7h; void *
0x18007a5a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a5a6  mov     ebx, eax
0x18007a5a8  jmp     short loc_18007A608
0x18007a5aa  lea     rdx, aSetphysicalcur; "SetPhysicalCursorPos"
0x18007a5b1  call    cs:__imp_GetProcAddress
0x18007a5b7  mov     [rsi+320h], rax
0x18007a5be  test    rax, rax
0x18007a5c1  jnz     short loc_18007A5CA
0x18007a5c3  mov     edx, 0FAh
0x18007a5c8  jmp     short loc_18007A5EB
0x18007a5ca  lea     rdx, aCalculatepopup_0; "CalculatePopupWindowPosition"
0x18007a5d1  mov     rcx, [rbx]; hModule
0x18007a5d4  call    cs:__imp_GetProcAddress
0x18007a5da  mov     [rsi+328h], rax
0x18007a5e1  test    rax, rax
0x18007a5e4  jnz     short loc_18007A622
0x18007a5e6  mov     edx, 0FDh; void *
0x18007a5eb  mov     ebx, 8007007Fh
0x18007a5f0  mov     r9d, ebx; char *
0x18007a5f3  lea     r8, aPcshellTwinuiE_22; "pcshell\\twinui\\experiencemanagers\\li"...
0x18007a5fa  mov     rcx, [rsp+168h]; this
0x18007a602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a607  nop
0x18007a608  lea     rcx, [rsp+168h+var_100]; void *
0x18007a60d  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x18007a612  nop
0x18007a613  lea     rcx, [rsp+168h+var_F8]
0x18007a618  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a61d  jmp     loc_18007A242
0x18007a622  lea     rdx, aGetphysicalcur_0; "GetPhysicalCursorPos"
0x18007a629  mov     rcx, [rbx]; hModule
0x18007a62c  call    cs:__imp_GetProcAddress
0x18007a632  mov     [rsi+330h], rax
0x18007a639  test    rax, rax
0x18007a63c  jnz     short loc_18007A680
0x18007a63e  mov     rcx, [rsp+168h]; this
0x18007a646  mov     ebx, 8007007Fh
0x18007a64b  mov     r9d, ebx; char *
0x18007a64e  lea     r8, aPcshellTwinuiE_22; "pcshell\\twinui\\experiencemanagers\\li"...
0x18007a655  mov     edx, 100h; void *
0x18007a65a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a65f  nop
0x18007a660  lea     rcx, [rsp+168h+var_100]
0x18007a665  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007a66a  nop
0x18007a66b  mov     rdx, [rsi]
  ... truncated ...
```
