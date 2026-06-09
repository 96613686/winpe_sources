# AccessibilityDialog::SetUpControls(void)

- ea: `0x1400223d8`
- end: `0x140022845`
- name: `?SetUpControls@AccessibilityDialog@@AEAAXXZ`
- size: `1133`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400206e8`

## callees

- `0x140002480`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14000d2e8`
- `0x14000f914`
- `0x14001d730`
- `0x14001f304`
- `0x14001fcd8`
- `0x1400205a8`
- `0x1400223d8`
- `0x140022d84`
- `0x140022e08`
- `0x1400256b4`
- `0x140029010`

## string_xrefs

- `0x140022626`: `voiceaccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AccessibilityDialog::SetUpControls(AccessibilityDialog *this)
{
  __int64 v2; // rbx
  __int64 ToggleName; // rax
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 (__fastcall ***v38)(_QWORD, __int64 *, _QWORD *); // rcx
  __int64 v39; // rdi
  unsigned int v40; // eax
  _QWORD *v41; // rbx
  __int64 v42; // rbx
  __int64 (__fastcall ***v43)(_QWORD, __int64 *, _QWORD *); // rcx
  __int64 v44; // rdi
  unsigned int v45; // eax
  _QWORD *v46; // rbx
  __int64 v47; // [rsp+20h] [rbp-59h] BYREF
  __int64 v48; // [rsp+28h] [rbp-51h]
  _QWORD v49[2]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v50[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v51; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v52[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v53[2]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v54[32]; // [rsp+70h] [rbp-9h] BYREF
  int v55; // [rsp+90h] [rbp+17h] BYREF
  __int128 v56; // [rsp+98h] [rbp+1Fh]

  v2 = *((_QWORD *)this + 6);
  ToggleName = anonymous_namespace_::GetToggleName(&v55, L"magnifierpane");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ToggleName, ToggleName, v4);
  v48 = *(_QWORD *)(v5 + 16);
  v6 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v2, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 56, v6);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v7 = *((_QWORD *)this + 6);
  v8 = anonymous_namespace_::GetToggleName(&v55, L"highcontrast");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8, v8, v9);
  v48 = *(_QWORD *)(v10 + 16);
  v11 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v7, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 64, v11);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v12 = *((_QWORD *)this + 6);
  v13 = anonymous_namespace_::GetToggleName(&v55, L"narrator");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13, v13, v14);
  v48 = *(_QWORD *)(v15 + 16);
  v16 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v12, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 72, v16);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v17 = *((_QWORD *)this + 6);
  v18 = anonymous_namespace_::GetToggleName(&v55, L"osk");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18, v18, v19);
  v48 = *(_QWORD *)(v20 + 16);
  v21 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v17, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 80, v21);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v22 = *((_QWORD *)this + 6);
  v23 = anonymous_namespace_::GetToggleName(&v55, L"stickykeys");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23, v23, v24);
  v48 = *(_QWORD *)(v25 + 16);
  v26 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v22, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 88, v26);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v27 = *((_QWORD *)this + 6);
  v28 = anonymous_namespace_::GetToggleName(&v55, L"filterkeys");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28, v28, v29);
  v48 = *(_QWORD *)(v30 + 16);
  v31 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v27, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 96, v31);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v32 = *((_QWORD *)this + 6);
  v33 = anonymous_namespace_::GetToggleName(&v55, L"voiceaccess");
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33, v33, v34);
  v48 = *(_QWORD *)(v35 + 16);
  v36 = XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(v32, v49, &v47);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=((char *)this + 104, v36);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
  std::wstring::_Tidy_deallocate(&v55);
  v53[0] = L"RootGrid";
  v53[1] = 8;
  v37 = XamlUI::XamlContentRoot(*((_QWORD *)this + 6), &v47);
  winrt::param::hstring::hstring(v54, v53);
  v38 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *))winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FindName(
                                                                   v37,
                                                                   v49,
                                                                   v54);
  if ( v38 )
  {
    v53[0] = 0;
    v55 = 0;
    v56 = 0;
    v40 = (**v38)(v38, winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IGrid>, v53);
    winrt::check_hresult(v50, v40, &v55);
    v39 = v53[0];
    v51 = v53[0];
  }
  else
  {
    v51 = 0;
    v39 = 0;
  }
  if ( v49[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v49);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v47);
  v41 = (_QWORD *)((char *)this + 112);
  if ( (__int64 *)((char *)this + 112) != &v51 )
  {
    if ( *v41 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 112);
    v51 = 0;
    *v41 = v39;
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v51);
  v49[0] = L"FlyoutRoot";
  v49[1] = 10;
  v42 = XamlUI::XamlContentRoot(*((_QWORD *)this + 6), &v47);
  winrt::param::hstring::hstring(v54, v49);
  v43 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD *))winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FindName(
                                                                   v42,
                                                                   v53,
                                                                   v54);
  if ( v43 )
  {
    v49[0] = 0;
    v55 = 0;
    v56 = 0;
    v45 = (**v43)(v43, winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IFlyout>, v49);
    winrt::check_hresult(v50, v45, &v55);
    v44 = v49[0];
    v52[0] = v49[0];
  }
  else
  {
    v52[0] = 0;
    v44 = 0;
  }
  if ( v53[0] )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v53);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v47);
  v46 = (_QWORD *)((char *)this + 120);
  if ( (_QWORD *)((char *)this + 120) != v52 )
  {
    if ( *v46 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 120);
    v52[0] = 0;
    *v46 = v44;
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v52);
}

```

## disassembly

```asm
0x1400223d8  mov     [rsp-8+arg_8], rbx
0x1400223dd  mov     [rsp-8+arg_10], rsi
0x1400223e2  push    rbp
0x1400223e3  push    rdi
0x1400223e4  push    r14
0x1400223e6  lea     rbp, [rsp-47h]
0x1400223eb  sub     rsp, 0C0h
0x1400223f2  mov     rax, cs:__security_cookie
0x1400223f9  xor     rax, rsp
0x1400223fc  mov     [rbp+57h+var_20], rax
0x140022400  mov     rsi, rcx
0x140022403  xor     r14d, r14d
0x140022406  mov     rbx, [rcx+30h]
0x14002240a  lea     rdx, aMagnifierpane_1; "magnifierpane"
0x140022411  lea     rcx, [rbp+57h+var_40]
0x140022415  call    _anonymous_namespace___GetToggleName
0x14002241a  mov     rdx, rax
0x14002241d  mov     rcx, rax
0x140022420  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140022425  mov     [rbp+57h+var_B0], rax
0x140022429  mov     rax, [rdx+10h]
0x14002242d  mov     [rbp+57h+var_A8], rax
0x140022431  lea     r8, [rbp+57h+var_B0]
0x140022435  lea     rdx, [rbp+57h+var_A0]
0x140022439  mov     rcx, rbx
0x14002243c  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x140022441  lea     rcx, [rsi+38h]
0x140022445  mov     rdx, rax
0x140022448  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x14002244d  lea     rcx, [rbp+57h+var_A0]
0x140022451  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022456  nop
0x140022457  lea     rcx, [rbp+57h+var_40]
0x14002245b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140022460  mov     rbx, [rsi+30h]
0x140022464  lea     rdx, aHighcontrast_0; "highcontrast"
0x14002246b  lea     rcx, [rbp+57h+var_40]
0x14002246f  call    _anonymous_namespace___GetToggleName
0x140022474  mov     rdx, rax
0x140022477  mov     rcx, rax
0x14002247a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002247f  mov     [rbp+57h+var_B0], rax
0x140022483  mov     rax, [rdx+10h]
0x140022487  mov     [rbp+57h+var_A8], rax
0x14002248b  lea     r8, [rbp+57h+var_B0]
0x14002248f  lea     rdx, [rbp+57h+var_A0]
0x140022493  mov     rcx, rbx
0x140022496  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x14002249b  lea     rcx, [rsi+40h]
0x14002249f  mov     rdx, rax
0x1400224a2  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x1400224a7  lea     rcx, [rbp+57h+var_A0]
0x1400224ab  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400224b0  nop
0x1400224b1  lea     rcx, [rbp+57h+var_40]
0x1400224b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400224ba  mov     rbx, [rsi+30h]
0x1400224be  lea     rdx, aNarrator_1; "narrator"
0x1400224c5  lea     rcx, [rbp+57h+var_40]
0x1400224c9  call    _anonymous_namespace___GetToggleName
0x1400224ce  mov     rdx, rax
0x1400224d1  mov     rcx, rax
0x1400224d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400224d9  mov     [rbp+57h+var_B0], rax
0x1400224dd  mov     rax, [rdx+10h]
0x1400224e1  mov     [rbp+57h+var_A8], rax
0x1400224e5  lea     r8, [rbp+57h+var_B0]
0x1400224e9  lea     rdx, [rbp+57h+var_A0]
0x1400224ed  mov     rcx, rbx
0x1400224f0  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x1400224f5  lea     rcx, [rsi+48h]
0x1400224f9  mov     rdx, rax
0x1400224fc  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x140022501  lea     rcx, [rbp+57h+var_A0]
0x140022505  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14002250a  nop
0x14002250b  lea     rcx, [rbp+57h+var_40]
0x14002250f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140022514  mov     rbx, [rsi+30h]
0x140022518  lea     rdx, aOsk_1; "osk"
0x14002251f  lea     rcx, [rbp+57h+var_40]
0x140022523  call    _anonymous_namespace___GetToggleName
0x140022528  mov     rdx, rax
0x14002252b  mov     rcx, rax
0x14002252e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140022533  mov     [rbp+57h+var_B0], rax
0x140022537  mov     rax, [rdx+10h]
0x14002253b  mov     [rbp+57h+var_A8], rax
0x14002253f  lea     r8, [rbp+57h+var_B0]
0x140022543  lea     rdx, [rbp+57h+var_A0]
0x140022547  mov     rcx, rbx
0x14002254a  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x14002254f  lea     rcx, [rsi+50h]
0x140022553  mov     rdx, rax
0x140022556  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x14002255b  lea     rcx, [rbp+57h+var_A0]
0x14002255f  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022564  nop
0x140022565  lea     rcx, [rbp+57h+var_40]
0x140022569  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002256e  mov     rbx, [rsi+30h]
0x140022572  lea     rdx, aStickykeys_0; "stickykeys"
0x140022579  lea     rcx, [rbp+57h+var_40]
0x14002257d  call    _anonymous_namespace___GetToggleName
0x140022582  mov     rdx, rax
0x140022585  mov     rcx, rax
0x140022588  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002258d  mov     [rbp+57h+var_B0], rax
0x140022591  mov     rax, [rdx+10h]
0x140022595  mov     [rbp+57h+var_A8], rax
0x140022599  lea     r8, [rbp+57h+var_B0]
0x14002259d  lea     rdx, [rbp+57h+var_A0]
0x1400225a1  mov     rcx, rbx
0x1400225a4  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x1400225a9  lea     rcx, [rsi+58h]
0x1400225ad  mov     rdx, rax
0x1400225b0  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x1400225b5  lea     rcx, [rbp+57h+var_A0]
0x1400225b9  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400225be  nop
0x1400225bf  lea     rcx, [rbp+57h+var_40]
0x1400225c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400225c8  mov     rbx, [rsi+30h]
0x1400225cc  lea     rdx, aFilterkeys_0; "filterkeys"
0x1400225d3  lea     rcx, [rbp+57h+var_40]
0x1400225d7  call    _anonymous_namespace___GetToggleName
0x1400225dc  mov     rdx, rax
0x1400225df  mov     rcx, rax
0x1400225e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400225e7  mov     [rbp+57h+var_B0], rax
0x1400225eb  mov     rax, [rdx+10h]
0x1400225ef  mov     [rbp+57h+var_A8], rax
0x1400225f3  lea     r8, [rbp+57h+var_B0]
0x1400225f7  lea     rdx, [rbp+57h+var_A0]
0x1400225fb  mov     rcx, rbx
0x1400225fe  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x140022603  lea     rcx, [rsi+60h]
0x140022607  mov     rdx, rax
0x14002260a  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x14002260f  lea     rcx, [rbp+57h+var_A0]
0x140022613  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022618  nop
0x140022619  lea     rcx, [rbp+57h+var_40]
0x14002261d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140022622  mov     rbx, [rsi+30h]
0x140022626  lea     rdx, aVoiceaccess; "voiceaccess"
0x14002262d  lea     rcx, [rbp+57h+var_40]
0x140022631  call    _anonymous_namespace___GetToggleName
0x140022636  mov     rdx, rax
0x140022639  mov     rcx, rax
0x14002263c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140022641  mov     [rbp+57h+var_B0], rax
0x140022645  mov     rax, [rdx+10h]
0x140022649  mov     [rbp+57h+var_A8], rax
0x14002264d  lea     r8, [rbp+57h+var_B0]
0x140022651  lea     rdx, [rbp+57h+var_A0]
0x140022655  mov     rcx, rbx
0x140022658  call    ??$GetElementAs@UToggleSwitch@Controls@Xaml@UI@Windows@winrt@@@XamlUI@@QEBA?AUToggleSwitch@Controls@Xaml@UI@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; XamlUI::GetElementAs<winrt::Windows::UI::Xaml::Controls::ToggleSwitch>(std::basic_string_view<ushort>)
0x14002265d  lea     rcx, [rsi+68h]
0x140022661  mov     rdx, rax
0x140022664  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x140022669  lea     rcx, [rbp+57h+var_A0]
0x14002266d  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022672  nop
0x140022673  lea     rcx, [rbp+57h+var_40]
0x140022677  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002267c  lea     rax, aRootgrid; "RootGrid"
0x140022683  mov     [rbp+57h+var_70], rax
0x140022687  mov     [rbp+57h+var_68], 8
0x14002268f  lea     rdx, [rbp+57h+var_B0]
0x140022693  mov     rcx, [rsi+30h]
0x140022697  call    ?XamlContentRoot@XamlUI@@QEBA?AUFrameworkElement@Xaml@UI@Windows@winrt@@XZ; XamlUI::XamlContentRoot(void)
0x14002269c  mov     rbx, rax
0x14002269f  lea     rdx, [rbp+57h+var_70]
0x1400226a3  lea     rcx, [rbp+57h+var_60]
0x1400226a7  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x1400226ac  lea     r8, [rbp+57h+var_60]
0x1400226b0  lea     rdx, [rbp+57h+var_A0]
0x1400226b4  mov     rcx, rbx
0x1400226b7  call    ?FindName@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FindName(winrt::param::hstring const &)
0x1400226bc  nop
0x1400226bd  mov     rcx, [rax]
0x1400226c0  test    rcx, rcx
0x1400226c3  jnz     short loc_1400226CE
0x1400226c5  mov     [rbp+57h+var_88], r14
0x1400226c9  mov     edi, r14d
0x1400226cc  jmp     short loc_14002270B
0x1400226ce  mov     [rbp+57h+var_70], r14
0x1400226d2  mov     [rbp+57h+var_40], r14d
0x1400226d6  xorps   xmm0, xmm0
0x1400226d9  movdqu  [rbp+57h+var_38], xmm0
0x1400226de  mov     rax, [rcx]
0x1400226e1  lea     r8, [rbp+57h+var_70]
0x1400226e5  lea     rdx, ??$guid_v@UIGrid@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IGrid>
0x1400226ec  mov     rax, [rax]
0x1400226ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400226f4  lea     r8, [rbp+57h+var_40]
0x1400226f8  mov     edx, eax
0x1400226fa  lea     rcx, [rbp+57h+var_90]
0x1400226fe  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140022703  mov     rdi, [rbp+57h+var_70]
0x140022707  mov     [rbp+57h+var_88], rdi
0x14002270b  cmp     [rbp+57h+var_A0], r14
0x14002270f  jz      short loc_14002271B
0x140022711  lea     rcx, [rbp+57h+var_A0]
0x140022715  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002271a  nop
0x14002271b  lea     rcx, [rbp+57h+var_B0]
0x14002271f  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022724  lea     rbx, [rsi+70h]
0x140022728  lea     rax, [rbp+57h+var_88]
0x14002272c  cmp     rbx, rax
0x14002272f  jz      short loc_140022745
0x140022731  cmp     [rbx], r14
0x140022734  jz      short loc_14002273E
0x140022736  mov     rcx, rbx
0x140022739  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002273e  mov     [rbp+57h+var_88], r14
0x140022742  mov     [rbx], rdi
0x140022745  lea     rcx, [rbp+57h+var_88]
0x140022749  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14002274e  lea     rax, aFlyoutroot; "FlyoutRoot"
0x140022755  mov     [rbp+57h+var_A0], rax
0x140022759  mov     [rbp+57h+var_98], 0Ah
0x140022761  lea     rdx, [rbp+57h+var_B0]
0x140022765  mov     rcx, [rsi+30h]
0x140022769  call    ?XamlContentRoot@XamlUI@@QEBA?AUFrameworkElement@Xaml@UI@Windows@winrt@@XZ; XamlUI::XamlContentRoot(void)
0x14002276e  mov     rbx, rax
0x140022771  lea     rdx, [rbp+57h+var_A0]
0x140022775  lea     rcx, [rbp+57h+var_60]
0x140022779  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14002277e  lea     r8, [rbp+57h+var_60]
0x140022782  lea     rdx, [rbp+57h+var_70]
0x140022786  mov     rcx, rbx
0x140022789  call    ?FindName@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::FindName(winrt::param::hstring const &)
0x14002278e  nop
0x14002278f  mov     rcx, [rax]
0x140022792  test    rcx, rcx
0x140022795  jnz     short loc_1400227A0
0x140022797  mov     [rbp+57h+var_80], r14
0x14002279b  mov     rdi, r14
0x14002279e  jmp     short loc_1400227DD
0x1400227a0  mov     [rbp+57h+var_A0], r14
0x1400227a4  mov     [rbp+57h+var_40], r14d
0x1400227a8  xorps   xmm0, xmm0
0x1400227ab  movdqu  [rbp+57h+var_38], xmm0
0x1400227b0  mov     rax, [rcx]
0x1400227b3  lea     r8, [rbp+57h+var_A0]
0x1400227b7  lea     rdx, ??$guid_v@UIFlyout@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IFlyout>
0x1400227be  mov     rax, [rax]
0x1400227c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400227c6  lea     r8, [rbp+57h+var_40]
0x1400227ca  mov     edx, eax
0x1400227cc  lea     rcx, [rbp+57h+var_90]
0x1400227d0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1400227d5  mov     rdi, [rbp+57h+var_A0]
0x1400227d9  mov     [rbp+57h+var_80], rdi
0x1400227dd  cmp     [rbp+57h+var_70], r14
0x1400227e1  jz      short loc_1400227ED
0x1400227e3  lea     rcx, [rbp+57h+var_70]
0x1400227e7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400227ec  nop
0x1400227ed  lea     rcx, [rbp+57h+var_B0]
0x1400227f1  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400227f6  lea     rbx, [rsi+78h]
0x1400227fa  lea     rax, [rbp+57h+var_80]
0x1400227fe  cmp     rbx, rax
0x140022801  jz      short loc_140022817
0x140022803  cmp     [rbx], r14
0x140022806  jz      short loc_140022810
0x140022808  mov     rcx, rbx
0x14002280b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140022810  mov     [rbp+57h+var_80], r14
0x140022814  mov     [rbx], rdi
0x140022817  lea     rcx, [rbp+57h+var_80]
0x14002281b  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140022820  mov     rcx, [rbp+57h+var_20]
0x140022824  xor     rcx, rsp; StackCookie
0x140022827  call    __security_check_cookie
0x14002282c  lea     r11, [rsp+0D0h+var_10]
0x140022834  mov     rbx, [r11+28h]
0x140022838  mov     rsi, [r11+30h]
0x14002283c  mov     rsp, r11
0x14002283f  pop     r14
0x140022841  pop     rdi
0x140022842  pop     rbp
0x140022843  retn
```
