# AccessibilityDialog::RegisterUiHandlers(void)

- ea: `0x140021538`
- end: `0x140021d9a`
- name: `?RegisterUiHandlers@AccessibilityDialog@@AEAAXXZ`
- size: `2146`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400206e8`

## callees

- `0x140002760`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14000cd18`
- `0x14000cd74`
- `0x14000cdd0`
- `0x14000ce2c`
- `0x14001d1f0`
- `0x14001ec70`
- `0x14001f1b0`
- `0x14001f340`
- `0x14001f4a8`
- `0x14001f504`
- `0x14001f880`
- `0x140020f84`
- `0x140021000`
- `0x1400213e4`
- `0x140021538`
- `0x140022c90`
- `0x14002309c`
- `0x1400256b4`
- `0x140029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall AccessibilityDialog::RegisterUiHandlers(AccessibilityDialog *this)
{
  __int64 *weak; // rax
  __int64 v3; // rcx
  _DWORD *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 *v8; // rax
  __int64 v9; // rcx
  _DWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  _DWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 *v20; // rax
  __int64 v21; // rcx
  _DWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 *v26; // rax
  __int64 v27; // rcx
  _DWORD *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 *v32; // rax
  __int64 v33; // rcx
  _DWORD *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 *v38; // rax
  __int64 v39; // rcx
  _DWORD *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 *v44; // rax
  __int64 v45; // rcx
  __int64 *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rbx
  void (__fastcall ***v49)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 *v52; // rax
  __int64 v53; // rcx
  __int64 *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rbx
  void (__fastcall ***v57)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 *v61; // rax
  __int64 v62; // rcx
  _DWORD *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // rax
  __int64 *v67; // rax
  __int64 v68; // rdx
  __int64 *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rbx
  void (__fastcall ***v72)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v73; // [rsp+20h] [rbp-48h] BYREF
  __int64 v74; // [rsp+28h] [rbp-40h] BYREF
  __int64 v75; // [rsp+30h] [rbp-38h]
  __int64 v76; // [rsp+38h] [rbp-30h] BYREF
  __int64 v77; // [rsp+40h] [rbp-28h]
  __int64 v78; // [rsp+48h] [rbp-20h] BYREF
  __int64 v79; // [rsp+50h] [rbp-18h]
  __int64 v80; // [rsp+B0h] [rbp+48h] BYREF
  __int64 *v81; // [rsp+B8h] [rbp+50h] BYREF
  __int64 *v82; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v83; // [rsp+C8h] [rbp+60h] BYREF

  winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
    this,
    &v73);
  weak = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                      this,
                      &v82);
  v3 = *weak;
  *weak = 0;
  v80 = v3;
  v81 = &v80;
  v4 = operator new(0x18u);
  v4[2] = 1;
  v5 = v80;
  v80 = 0;
  *((_QWORD *)v4 + 2) = v5;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v4 = off_14002B548;
  v81 = (__int64 *)v4;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v7 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
         (char *)this + 56,
         &v78,
         v6,
         &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 128,
    v7);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v8 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                    this,
                    &v82);
  v9 = *v8;
  *v8 = 0;
  v80 = v9;
  v81 = &v80;
  v10 = operator new(0x18u);
  v10[2] = 1;
  v11 = v80;
  v80 = 0;
  *((_QWORD *)v10 + 2) = v11;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v10 = off_14002B528;
  v81 = (__int64 *)v10;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v13 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
          (char *)this + 72,
          &v78,
          v12,
          &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 192,
    v13);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v14 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v82);
  v15 = *v14;
  *v14 = 0;
  v80 = v15;
  v81 = &v80;
  v16 = operator new(0x18u);
  v16[2] = 1;
  v17 = v80;
  v80 = 0;
  *((_QWORD *)v16 + 2) = v17;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v16 = off_14002B4E8;
  v81 = (__int64 *)v16;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v19 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
          (char *)this + 64,
          &v78,
          v18,
          &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 208,
    v19);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v20 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v82);
  v21 = *v20;
  *v20 = 0;
  v80 = v21;
  v81 = &v80;
  v22 = operator new(0x18u);
  v22[2] = 1;
  v23 = v80;
  v80 = 0;
  *((_QWORD *)v22 + 2) = v23;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v22 = off_14002B508;
  v81 = (__int64 *)v22;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v25 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
          (char *)this + 80,
          &v78,
          v24,
          &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 176,
    v25);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v26 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v82);
  v27 = *v26;
  *v26 = 0;
  v80 = v27;
  v81 = &v80;
  v28 = operator new(0x18u);
  v28[2] = 1;
  v29 = v80;
  v80 = 0;
  *((_QWORD *)v28 + 2) = v29;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v28 = off_14002B4A8;
  v81 = (__int64 *)v28;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v31 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
          (char *)this + 88,
          &v78,
          v30,
          &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 144,
    v31);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v32 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v82);
  v33 = *v32;
  *v32 = 0;
  v80 = v33;
  v81 = &v80;
  v34 = operator new(0x18u);
  v34[2] = 1;
  v35 = v80;
  v80 = 0;
  *((_QWORD *)v34 + 2) = v35;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v34 = off_14002B4C8;
  v81 = (__int64 *)v34;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v37 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
          (char *)this + 96,
          &v78,
          v36,
          &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 160,
    v37);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v38 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v82);
  v39 = *v38;
  *v38 = 0;
  v80 = v39;
  v81 = &v80;
  v40 = operator new(0x18u);
  v40[2] = 1;
  v41 = v80;
  v80 = 0;
  *((_QWORD *)v40 + 2) = v41;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v40 = off_14002B468;
  v81 = (__int64 *)v40;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v43 = winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(
          (char *)this + 104,
          &v78,
          v42,
          &v81);
  __4__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 224,
    v43);
  __1__event_revoker_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIToggleSwitch_Controls_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BLA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  v44 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v83);
  v45 = *v44;
  *v44 = 0;
  v80 = v45;
  v81 = &v80;
  v46 = (__int64 *)operator new(0x18u);
  v81 = v46;
  *((_DWORD *)v46 + 2) = 1;
  v47 = v80;
  v80 = 0;
  v46[2] = v47;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v46 = (__int64)off_14002B488;
  v82 = v46;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v48 = *(_QWORD *)winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IFlyoutBase<winrt::Windows::UI::Xaml::Controls::Flyout>::Closed(
                     (char *)this + 120,
                     &v74,
                     &v82);
  v49 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))*((_QWORD *)this + 15);
  v81 = 0;
  if ( v49 )
    (**v49)(v49, winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::Primitives::IFlyoutBase>, &v81);
  winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>(
    &v76,
    &v81);
  v77 = v48;
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v81);
  v50 = v76;
  v76 = 0;
  v74 = v50;
  v75 = v77;
  std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&v74, (char *)this + 240);
  v51 = v75;
  v75 = *((_QWORD *)this + 31);
  *((_QWORD *)this + 31) = v51;
  __1__event_revoker_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt__X_impl_7_EAAHUevent_token_7___E1___989impl_7__BFI_AA_impl_winrt__QEAA_XZ(&v74);
  __1__event_revoker_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt__X_impl_7_EAAHUevent_token_7___E1___989impl_7__BFI_AA_impl_winrt__QEAA_XZ(&v76);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  if ( v83 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
  v52 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v83);
  v53 = *v52;
  *v52 = 0;
  v80 = v53;
  v81 = &v80;
  v54 = (__int64 *)operator new(0x18u);
  v81 = v54;
  *((_DWORD *)v54 + 2) = 1;
  v55 = v80;
  v80 = 0;
  v54[2] = v55;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v54 = (__int64)off_14002B428;
  v82 = v54;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v56 = *(_QWORD *)winrt::impl::consume_Windows_UI_Xaml_Controls_Primitives_IFlyoutBase<winrt::Windows::UI::Xaml::Controls::Flyout>::Opened(
                     (char *)this + 120,
                     &v74,
                     &v82);
  v57 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))*((_QWORD *)this + 15);
  v81 = 0;
  if ( v57 )
    (**v57)(v57, winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::Primitives::IFlyoutBase>, &v81);
  winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>(
    &v78,
    &v81);
  v79 = v56;
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v81);
  v58 = v78;
  v78 = 0;
  v76 = v58;
  v77 = v79;
  std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&v76, (char *)this + 256);
  v59 = v77;
  v77 = *((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = v59;
  __1__event_revoker_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt__X_impl_7_EAAHUevent_token_7___E1___989impl_7__BEI_AA_impl_winrt__QEAA_XZ(&v76);
  __1__event_revoker_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt___MP8type___abi_UIFlyoutBase_Primitives_Controls_Xaml_UI_Windows_winrt__X_impl_7_EAAHUevent_token_7___E1___989impl_7__BEI_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  if ( v83 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
  v60 = XamlUI::XamlContentRoot(*((_QWORD *)this + 6), &v83);
  v61 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v82);
  v62 = *v61;
  *v61 = 0;
  v80 = v62;
  v81 = &v80;
  v63 = operator new(0x18u);
  v63[2] = 1;
  v64 = v80;
  v80 = 0;
  *((_QWORD *)v63 + 2) = v64;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v63 = off_14002B448;
  v81 = (__int64 *)v63;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v66 = winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::Loaded(
          v60,
          &v78,
          v65,
          &v81,
          v73,
          v74);
  __4__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 272,
    v66);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
  if ( v82 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v83);
  v67 = (__int64 *)winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(
                     this,
                     &v83);
  v68 = *v67;
  *v67 = 0;
  v80 = v68;
  v81 = &v80;
  v69 = (__int64 *)operator new(0x18u);
  v81 = v69;
  *((_DWORD *)v69 + 2) = 1;
  v70 = v80;
  v80 = 0;
  v69[2] = v70;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v69 = (__int64)off_14002B408;
  v82 = v69;
  lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_(&v80);
  v71 = *(_QWORD *)winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>::Loaded(
                     (char *)this + 56,
                     &v74,
                     &v82);
  v72 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))*((_QWORD *)this + 7);
  v81 = 0;
  if ( v72 )
    (**v72)(v72, winrt::impl::guid_v<winrt::Windows::UI::Xaml::IFrameworkElement>, &v81);
  __0__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_AEBUIFrameworkElement_Xaml_UI_Windows_2_Uevent_token_2__Z(
    &v78,
    &v81,
    v71);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v81);
  __4__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    (char *)this + 288,
    &v78);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ(&v78);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
  if ( v83 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
  if ( v73 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v73);
}

```

## disassembly

```asm
0x140021538  push    rbp
0x14002153a  push    rbx
0x14002153b  push    rsi
0x14002153c  push    rdi
0x14002153d  push    r12
0x14002153f  push    r13
0x140021541  push    r14
0x140021543  push    r15
0x140021545  mov     rbp, rsp
0x140021548  sub     rsp, 68h
0x14002154c  mov     rdi, rcx
0x14002154f  xor     r15d, r15d
0x140021552  lea     rdx, [rbp+var_48]
0x140021556  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x14002155b  nop
0x14002155c  lea     r14, [rdi+38h]
0x140021560  lea     rdx, [rbp+arg_10]
0x140021564  mov     rcx, rdi
0x140021567  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x14002156c  nop
0x14002156d  mov     rcx, [rax]
0x140021570  mov     [rax], r15
0x140021573  mov     [rbp+arg_0], rcx
0x140021577  lea     rax, [rbp+arg_0]
0x14002157b  mov     [rbp+arg_8], rax
0x14002157f  lea     r12d, [r15+18h]
0x140021583  mov     ecx, r12d; Size
0x140021586  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002158b  mov     [rbp+arg_8], rax
0x14002158f  lea     r13d, [r15+1]
0x140021593  mov     [rax+8], r13d
0x140021597  mov     rcx, [rbp+arg_0]
0x14002159b  mov     [rbp+arg_0], r15
0x14002159f  mov     [rax+10h], rcx
0x1400215a3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1400215aa  lea     rcx, off_14002B548
0x1400215b1  mov     [rax], rcx
0x1400215b4  mov     [rbp+arg_8], rax
0x1400215b8  lea     rcx, [rbp+arg_0]
0x1400215bc  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x1400215c1  nop
0x1400215c2  lea     r9, [rbp+arg_8]
0x1400215c6  lea     rdx, [rbp+var_20]
0x1400215ca  mov     rcx, r14
0x1400215cd  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x1400215d2  lea     rcx, [rdi+80h]
0x1400215d9  mov     rdx, rax
0x1400215dc  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x1400215e1  lea     rcx, [rbp+var_20]
0x1400215e5  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x1400215ea  nop
0x1400215eb  lea     rcx, [rbp+arg_8]
0x1400215ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400215f4  nop
0x1400215f5  cmp     [rbp+arg_10], r15
0x1400215f9  jz      short loc_140021604
0x1400215fb  lea     rcx, [rbp+arg_10]
0x1400215ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140021604  lea     rdx, [rbp+arg_10]
0x140021608  mov     rcx, rdi
0x14002160b  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x140021610  nop
0x140021611  mov     rcx, [rax]
0x140021614  mov     [rax], r15
0x140021617  mov     [rbp+arg_0], rcx
0x14002161b  lea     rax, [rbp+arg_0]
0x14002161f  mov     [rbp+arg_8], rax
0x140021623  mov     rcx, r12; Size
0x140021626  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002162b  mov     [rbp+arg_8], rax
0x14002162f  mov     [rax+8], r13d
0x140021633  mov     rdx, [rbp+arg_0]
0x140021637  mov     [rbp+arg_0], r15
0x14002163b  mov     [rax+10h], rdx
0x14002163f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140021646  lea     rcx, off_14002B528
0x14002164d  mov     [rax], rcx
0x140021650  mov     [rbp+arg_8], rax
0x140021654  lea     rcx, [rbp+arg_0]
0x140021658  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x14002165d  nop
0x14002165e  lea     r9, [rbp+arg_8]
0x140021662  lea     rdx, [rbp+var_20]
0x140021666  lea     rcx, [rdi+48h]
0x14002166a  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x14002166f  lea     rcx, [rdi+0C0h]
0x140021676  mov     rdx, rax
0x140021679  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x14002167e  lea     rcx, [rbp+var_20]
0x140021682  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x140021687  nop
0x140021688  lea     rcx, [rbp+arg_8]
0x14002168c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140021691  nop
0x140021692  cmp     [rbp+arg_10], r15
0x140021696  jz      short loc_1400216A1
0x140021698  lea     rcx, [rbp+arg_10]
0x14002169c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400216a1  lea     rdx, [rbp+arg_10]
0x1400216a5  mov     rcx, rdi
0x1400216a8  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x1400216ad  nop
0x1400216ae  mov     rcx, [rax]
0x1400216b1  mov     [rax], r15
0x1400216b4  mov     [rbp+arg_0], rcx
0x1400216b8  lea     rax, [rbp+arg_0]
0x1400216bc  mov     [rbp+arg_8], rax
0x1400216c0  mov     rcx, r12; Size
0x1400216c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400216c8  mov     [rbp+arg_8], rax
0x1400216cc  mov     [rax+8], r13d
0x1400216d0  mov     rdx, [rbp+arg_0]
0x1400216d4  mov     [rbp+arg_0], r15
0x1400216d8  mov     [rax+10h], rdx
0x1400216dc  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1400216e3  lea     rcx, off_14002B4E8
0x1400216ea  mov     [rax], rcx
0x1400216ed  mov     [rbp+arg_8], rax
0x1400216f1  lea     rcx, [rbp+arg_0]
0x1400216f5  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x1400216fa  nop
0x1400216fb  lea     r9, [rbp+arg_8]
0x1400216ff  lea     rdx, [rbp+var_20]
0x140021703  lea     rcx, [rdi+40h]
0x140021707  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x14002170c  lea     rcx, [rdi+0D0h]
0x140021713  mov     rdx, rax
0x140021716  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x14002171b  lea     rcx, [rbp+var_20]
0x14002171f  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x140021724  nop
0x140021725  lea     rcx, [rbp+arg_8]
0x140021729  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002172e  nop
0x14002172f  cmp     [rbp+arg_10], r15
0x140021733  jz      short loc_14002173E
0x140021735  lea     rcx, [rbp+arg_10]
0x140021739  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002173e  lea     rdx, [rbp+arg_10]
0x140021742  mov     rcx, rdi
0x140021745  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x14002174a  nop
0x14002174b  mov     rcx, [rax]
0x14002174e  mov     [rax], r15
0x140021751  mov     [rbp+arg_0], rcx
0x140021755  lea     rax, [rbp+arg_0]
0x140021759  mov     [rbp+arg_8], rax
0x14002175d  mov     rcx, r12; Size
0x140021760  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140021765  mov     [rbp+arg_8], rax
0x140021769  mov     [rax+8], r13d
0x14002176d  mov     rdx, [rbp+arg_0]
0x140021771  mov     [rbp+arg_0], r15
0x140021775  mov     [rax+10h], rdx
0x140021779  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140021780  lea     rcx, off_14002B508
0x140021787  mov     [rax], rcx
0x14002178a  mov     [rbp+arg_8], rax
0x14002178e  lea     rcx, [rbp+arg_0]
0x140021792  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x140021797  nop
0x140021798  lea     r9, [rbp+arg_8]
0x14002179c  lea     rdx, [rbp+var_20]
0x1400217a0  lea     rcx, [rdi+50h]
0x1400217a4  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x1400217a9  lea     rcx, [rdi+0B0h]
0x1400217b0  mov     rdx, rax
0x1400217b3  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x1400217b8  lea     rcx, [rbp+var_20]
0x1400217bc  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x1400217c1  nop
0x1400217c2  lea     rcx, [rbp+arg_8]
0x1400217c6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400217cb  nop
0x1400217cc  cmp     [rbp+arg_10], r15
0x1400217d0  jz      short loc_1400217DB
0x1400217d2  lea     rcx, [rbp+arg_10]
0x1400217d6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400217db  lea     rdx, [rbp+arg_10]
0x1400217df  mov     rcx, rdi
0x1400217e2  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x1400217e7  nop
0x1400217e8  mov     rcx, [rax]
0x1400217eb  mov     [rax], r15
0x1400217ee  mov     [rbp+arg_0], rcx
0x1400217f2  lea     rax, [rbp+arg_0]
0x1400217f6  mov     [rbp+arg_8], rax
0x1400217fa  mov     rcx, r12; Size
0x1400217fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140021802  mov     [rbp+arg_8], rax
0x140021806  mov     [rax+8], r13d
0x14002180a  mov     rdx, [rbp+arg_0]
0x14002180e  mov     [rbp+arg_0], r15
0x140021812  mov     [rax+10h], rdx
0x140021816  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x14002181d  lea     rcx, off_14002B4A8
0x140021824  mov     [rax], rcx
0x140021827  mov     [rbp+arg_8], rax
0x14002182b  lea     rcx, [rbp+arg_0]
0x14002182f  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x140021834  nop
0x140021835  lea     r9, [rbp+arg_8]
0x140021839  lea     rdx, [rbp+var_20]
0x14002183d  lea     rcx, [rdi+58h]
0x140021841  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x140021846  lea     rcx, [rdi+90h]
0x14002184d  mov     rdx, rax
0x140021850  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x140021855  lea     rcx, [rbp+var_20]
0x140021859  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x14002185e  nop
0x14002185f  lea     rcx, [rbp+arg_8]
0x140021863  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140021868  nop
0x140021869  cmp     [rbp+arg_10], r15
0x14002186d  jz      short loc_140021878
0x14002186f  lea     rcx, [rbp+arg_10]
0x140021873  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140021878  lea     rdx, [rbp+arg_10]
0x14002187c  mov     rcx, rdi
0x14002187f  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x140021884  nop
0x140021885  mov     rcx, [rax]
0x140021888  mov     [rax], r15
0x14002188b  mov     [rbp+arg_0], rcx
0x14002188f  lea     rax, [rbp+arg_0]
0x140021893  mov     [rbp+arg_8], rax
0x140021897  mov     rcx, r12; Size
0x14002189a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002189f  mov     [rbp+arg_8], rax
0x1400218a3  mov     [rax+8], r13d
0x1400218a7  mov     rdx, [rbp+arg_0]
0x1400218ab  mov     [rbp+arg_0], r15
0x1400218af  mov     [rax+10h], rdx
0x1400218b3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1400218ba  lea     rcx, off_14002B4C8
0x1400218c1  mov     [rax], rcx
0x1400218c4  mov     [rbp+arg_8], rax
0x1400218c8  lea     rcx, [rbp+arg_0]
0x1400218cc  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x1400218d1  nop
0x1400218d2  lea     r9, [rbp+arg_8]
0x1400218d6  lea     rdx, [rbp+var_20]
0x1400218da  lea     rcx, [rdi+60h]
0x1400218de  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x1400218e3  lea     rcx, [rdi+0A0h]
0x1400218ea  mov     rdx, rax
0x1400218ed  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x1400218f2  lea     rcx, [rbp+var_20]
0x1400218f6  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x1400218fb  nop
0x1400218fc  lea     rcx, [rbp+arg_8]
0x140021900  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140021905  nop
0x140021906  cmp     [rbp+arg_10], r15
0x14002190a  jz      short loc_140021915
0x14002190c  lea     rcx, [rbp+arg_10]
0x140021910  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140021915  lea     rdx, [rbp+arg_10]
0x140021919  mov     rcx, rdi
0x14002191c  call    ?get_weak@?$implements@VAccessibilityDialog@@UIInspectable@Foundation@Windows@winrt@@UILightDismissNotification@@@winrt@@QEAA?AU?$weak_ref@VAccessibilityDialog@@@2@XZ; winrt::implements<AccessibilityDialog,winrt::Windows::Foundation::IInspectable,ILightDismissNotification>::get_weak(void)
0x140021921  nop
0x140021922  mov     rcx, [rax]
0x140021925  mov     [rax], r15
0x140021928  mov     [rbp+arg_0], rcx
0x14002192c  lea     rax, [rbp+arg_0]
0x140021930  mov     [rbp+arg_8], rax
0x140021934  mov     rcx, r12; Size
0x140021937  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002193c  mov     [rbp+arg_8], rax
0x140021940  mov     [rax+8], r13d
0x140021944  mov     rdx, [rbp+arg_0]
0x140021948  mov     [rbp+arg_0], r15
0x14002194c  mov     [rax+10h], rdx
0x140021950  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140021957  lea     rcx, off_14002B468
0x14002195e  mov     [rax], rcx
0x140021961  mov     [rbp+arg_8], rax
0x140021965  lea     rcx, [rbp+arg_0]
0x140021969  call    _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_____lambda_ecc77f3a22ba66689a70fd4c73bb93c9_
0x14002196e  nop
0x14002196f  lea     r9, [rbp+arg_8]
0x140021973  lea     rdx, [rbp+var_20]
0x140021977  lea     rcx, [rdi+68h]
0x14002197b  call    ?Toggled@?$consume_Windows_UI_Xaml_Controls_IToggleSwitch@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Controls_IToggleSwitch<winrt::Windows::UI::Xaml::Controls::IToggleSwitch>::Toggled(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x140021980  lea     rcx, [rdi+0E0h]
0x140021987  mov     rdx, rax
0x14002198a  call    ??4?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x14002198f  lea     rcx, [rbp+var_20]
0x140021993  call    ??1?$event_revoker@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIToggleSwitch@Controls@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BLA@AA@impl@winrt@@QEAA@XZ
0x140021998  nop
0x140021999  lea     rcx, [rbp+arg_8]
0x14002199d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400219a2  nop
0x1400219a3  cmp     [rbp+arg_10], r15
0x1400219a7  jz      short loc_1400219B2
0x1400219a9  lea     rcx, [rbp+arg_10]
0x1400219ad  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400219b2  lea     rsi, [rdi+78h]
0x1400219b6  lea     rdx, [rbp+arg_18]
  ... truncated ...
```
