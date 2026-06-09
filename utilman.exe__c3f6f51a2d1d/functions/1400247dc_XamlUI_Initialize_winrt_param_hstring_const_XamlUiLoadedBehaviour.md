# XamlUI::Initialize(winrt::param::hstring const &,XamlUiLoadedBehaviour)

- ea: `0x1400247dc`
- end: `0x140024a9f`
- name: `?Initialize@XamlUI@@QEAAXAEBUhstring@param@winrt@@W4XamlUiLoadedBehaviour@@@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400206e8`

## callees

- `0x140009ee0`
- `0x14000ccdc`
- `0x14000cdd0`
- `0x14000d2e8`
- `0x14001e51c`
- `0x14001f4a8`
- `0x140020f84`
- `0x140022de8`
- `0x1400235a0`
- `0x140023754`
- `0x1400237c4`
- `0x1400239f4`
- `0x140024100`
- `0x140024118`
- `0x14002434c`
- `0x1400243a0`
- `0x14002440c`
- `0x1400247dc`
- `0x140024ea4`
- `0x14002556c`
- `0x1400258a8`
- `0x140029010`

## string_xrefs

- `0x140024848`: `enduser\ezap\xamlcommon\xamlui.cpp`
- `0x140024878`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall XamlUI::Initialize(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  int v8; // eax
  int v9; // eax
  void (__fastcall *v10)(XamlUI *__hidden, const struct IInspectable *, const struct winrt::Windows::UI::Xaml::RoutedEventArgs *); // r14
  _QWORD *v11; // rdi
  __int64 v12; // rax
  void (__fastcall ***v13)(_QWORD, __int64 *, _QWORD); // rcx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  __int128 v20; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v21[16]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  void (__fastcall *v23)(XamlUI *__hidden, const struct IInspectable *, const struct winrt::Windows::UI::Xaml::RoutedEventArgs *); // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+48h] BYREF

  v6 = winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource::DesktopWindowXamlSource((winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource *)&v23);
  winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(a1 + 32, v6);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v23);
  winrt::impl::as<IDesktopWindowXamlSourceNative,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v19,
    *(_QWORD *)(a1 + 32));
  v7 = v19;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 24LL))(v19, *(_QWORD *)(a1 + 8));
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      (const char *)(unsigned int)v8,
      v17);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 32LL))(v7, a1 + 16);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      (const char *)(unsigned int)v9,
      v17);
  *(_DWORD *)(a1 + 24) = a3;
  v24 = a2;
  v18[0] = &qword_140047138;
  _InterlockedIncrement64(&qword_140047138);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics> )
  {
    _lambda_bbfd22c1d265b39b75be756b5c167b68_::operator()(
      &v24,
      &v23,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>);
    _InterlockedDecrement64(&qword_140047138);
  }
  else
  {
    _InterlockedDecrement64(&qword_140047138);
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>::call<_lambda_bbfd22c1d265b39b75be756b5c167b68_ &>(
      retaddr,
      &v23,
      &v24);
  }
  v10 = v23;
  winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v17,
    v23);
  v11 = (_QWORD *)(a1 + 40);
  if ( (__int64 *)(a1 + 40) != &v17 )
  {
    if ( *v11 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 40);
    v12 = v17;
    v17 = 0;
    *v11 = v12;
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v17);
  if ( v10 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  v13 = (void (__fastcall ***)(_QWORD, __int64 *, _QWORD))*v11;
  v23 = 0;
  if ( v13 )
    (**v13)(v13, winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>, &v23);
  winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
    a1 + 32,
    &v23);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v23);
  v23 = XamlUI::OnLoaded;
  v24 = a1;
  v20 = *(_OWORD *)_lambda_149d9d0f93016857415718f3165d8236_::_lambda_149d9d0f93016857415718f3165d8236_(v21, &v24, &v23);
  winrt::Windows::UI::Xaml::RoutedEventHandler::RoutedEventHandler(&v23, &v20);
  v15 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int64, void (__fastcall **)(XamlUI *__hidden, const struct IInspectable *, const struct winrt::Windows::UI::Xaml::RoutedEventArgs *), __int64))winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::Loaded)(
          a1 + 40,
          v18,
          v14,
          &v23,
          v17);
  __4__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
    a1 + 48,
    v15);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ(v18);
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
  XamlUI::SetFlowDirection((XamlUI *)a1);
  if ( *(_DWORD *)(a1 + 24) == 1 )
  {
    LODWORD(v23) = 0;
    v18[0] = &v23;
    *(_QWORD *)&v20 = &qword_1400470D8;
    _InterlockedIncrement64(&qword_1400470D8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory> )
    {
      _lambda_3207e8c3a392af88c709c9f0a8afe0f7_::operator()(
        v18,
        &v24,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>);
      _InterlockedDecrement64(&qword_1400470D8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1400470D8);
      winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>::call<_lambda_3207e8c3a392af88c709c9f0a8afe0f7_ &>(
        v16,
        &v24,
        v18);
    }
    winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(
      a1 + 32,
      v18,
      &v24);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v18);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v24);
  }
  if ( v7 )
    winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(&v19);
}

```

## disassembly

```asm
0x1400247dc  mov     [rsp-28h+arg_8], rbx
0x1400247e1  push    rbp
0x1400247e2  push    rsi
0x1400247e3  push    rdi
0x1400247e4  push    r14
0x1400247e6  push    r15
0x1400247e8  mov     rbp, rsp
0x1400247eb  sub     rsp, 60h
0x1400247ef  mov     edi, r8d
0x1400247f2  mov     r14, rdx
0x1400247f5  mov     rsi, rcx
0x1400247f8  lea     rcx, [rbp+arg_0]; this
0x1400247fc  call    ??0DesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource::DesktopWindowXamlSource(void)
0x140024801  lea     r15, [rsi+20h]
0x140024805  mov     rdx, rax
0x140024808  mov     rcx, r15
0x14002480b  call    ??4ToggleSwitch@Controls@Xaml@UI@Windows@winrt@@QEAAAEAU012345@$$QEAU012345@@Z; winrt::Windows::UI::Xaml::Controls::ToggleSwitch::operator=(winrt::Windows::UI::Xaml::Controls::ToggleSwitch &&)
0x140024810  lea     rcx, [rbp+arg_0]
0x140024814  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024819  mov     rdx, [r15]
0x14002481c  lea     rcx, [rbp+var_28]
0x140024820  call    ??$as@UIDesktopWindowXamlSourceNative@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@$0A@@impl@winrt@@YA?AU?$com_ptr@UIDesktopWindowXamlSourceNative@@@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<IDesktopWindowXamlSourceNative,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x140024825  nop
0x140024826  mov     rbx, [rbp+var_28]
0x14002482a  mov     rax, [rbx]
0x14002482d  mov     rdx, [rsi+8]
0x140024831  mov     rcx, rbx
0x140024834  mov     rax, [rax+18h]
0x140024838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002483d  mov     rcx, [rbp+28h]; this
0x140024841  test    eax, eax
0x140024843  jns     short loc_14002485A
0x140024845  mov     r9d, eax; char *
0x140024848  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x14002484f  mov     edx, 72h ; 'r'; void *
0x140024854  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14002485a  mov     rax, [rbx]
0x14002485d  lea     rdx, [rsi+10h]
0x140024861  mov     rcx, rbx
0x140024864  mov     rax, [rax+20h]
0x140024868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002486d  mov     rcx, [rbp+28h]; this
0x140024871  test    eax, eax
0x140024873  jns     short loc_14002488A
0x140024875  mov     r9d, eax; char *
0x140024878  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x14002487f  mov     edx, 73h ; 's'; void *
0x140024884  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14002488a  mov     [rsi+18h], edi
0x14002488d  mov     [rbp+arg_18], r14
0x140024891  lea     rax, qword_140047138
0x140024898  mov     [rbp+var_38], rax
0x14002489c  lock inc cs:qword_140047138
0x1400248a4  cmp     cs:??$factory_cache_entry_v@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>
0x1400248ac  jz      short loc_1400248CD
0x1400248ae  lea     r8, ??$factory_cache_entry_v@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>
0x1400248b5  lea     rdx, [rbp+arg_0]
0x1400248b9  lea     rcx, [rbp+arg_18]
0x1400248bd  call    ??R_lambda_bbfd22c1d265b39b75be756b5c167b68_@@QEBA@AEBUIXamlReaderStatics@Markup@Xaml@UI@Windows@winrt@@@Z; _lambda_bbfd22c1d265b39b75be756b5c167b68_::operator()(winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics const &)
0x1400248c2  nop
0x1400248c3  lock dec cs:qword_140047138
0x1400248cb  jmp     short loc_1400248E3
0x1400248cd  lock dec cs:qword_140047138
0x1400248d5  lea     r8, [rbp+arg_18]
0x1400248d9  lea     rdx, [rbp+arg_0]
0x1400248dd  call    ??$call@AEAV_lambda_bbfd22c1d265b39b75be756b5c167b68_@@@?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_bbfd22c1d265b39b75be756b5c167b68_@@@Z
0x1400248e2  nop
0x1400248e3  mov     r14, [rbp+arg_0]
0x1400248e7  mov     rdx, r14
0x1400248ea  lea     rcx, [rbp+var_40]
0x1400248ee  call    ??$as@UFrameworkElement@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUFrameworkElement@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x1400248f3  lea     rdi, [rsi+28h]
0x1400248f7  lea     rax, [rbp+var_40]
0x1400248fb  cmp     rdi, rax
0x1400248fe  jz      short loc_14002491D
0x140024900  cmp     qword ptr [rdi], 0
0x140024904  jz      short loc_14002490E
0x140024906  mov     rcx, rdi
0x140024909  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002490e  mov     rax, [rbp+var_40]
0x140024912  mov     [rbp+var_40], 0
0x14002491a  mov     [rdi], rax
0x14002491d  lea     rcx, [rbp+var_40]
0x140024921  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024926  nop
0x140024927  test    r14, r14
0x14002492a  jz      short loc_140024935
0x14002492c  lea     rcx, [rbp+arg_0]
0x140024930  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024935  mov     rcx, [rdi]
0x140024938  mov     [rbp+arg_0], 0
0x140024940  test    rcx, rcx
0x140024943  jz      short loc_140024963
0x140024945  mov     rax, [rcx]
0x140024948  lea     r8, [rbp+arg_0]
0x14002494c  lea     rdx, ??$guid_v@UIUIElement@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::IUIElement>
0x140024953  mov     rax, [rax]
0x140024956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002495b  mov     rax, [rbp+arg_0]
0x14002495f  mov     [rbp+arg_0], rax
0x140024963  lea     rdx, [rbp+arg_0]
0x140024967  mov     rcx, r15
0x14002496a  call    ?Content@?$consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUUIElement@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(winrt::Windows::UI::Xaml::UIElement const &)
0x14002496f  nop
0x140024970  lea     rcx, [rbp+arg_0]
0x140024974  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024979  lea     rax, ?OnLoaded@XamlUI@@AEAAXAEBUIInspectable@Foundation@Windows@winrt@@AEBURoutedEventArgs@Xaml@UI@45@@Z; XamlUI::OnLoaded(winrt::Windows::Foundation::IInspectable const &,winrt::Windows::UI::Xaml::RoutedEventArgs const &)
0x140024980  mov     [rbp+arg_0], rax
0x140024984  mov     [rbp+arg_18], rsi
0x140024988  lea     r8, [rbp+arg_0]
0x14002498c  lea     rdx, [rbp+arg_18]
0x140024990  lea     rcx, [rbp+var_10]
0x140024994  call    ??0_lambda_149d9d0f93016857415718f3165d8236_@@QEAA@AEBQEAVXamlUI@@AEBQ81@EAAXAEBUIInspectable@Foundation@Windows@winrt@@AEBURoutedEventArgs@Xaml@UI@45@@_E@Z; _lambda_149d9d0f93016857415718f3165d8236_::_lambda_149d9d0f93016857415718f3165d8236_(XamlUI * const &,void (XamlUI::*const &)(winrt::Windows::Foundation::IInspectable const &,winrt::Windows::UI::Xaml::RoutedEventArgs const &),...)
0x140024999  movups  xmm0, xmmword ptr [rax]
0x14002499c  movdqu  [rbp+var_20], xmm0
0x1400249a1  lea     rdx, [rbp+var_20]
0x1400249a5  lea     rcx, [rbp+arg_0]
0x1400249a9  call    ??$?0V_lambda_149d9d0f93016857415718f3165d8236_@@@RoutedEventHandler@Xaml@UI@Windows@winrt@@QEAA@V_lambda_149d9d0f93016857415718f3165d8236_@@@Z; winrt::Windows::UI::Xaml::RoutedEventHandler::RoutedEventHandler(_lambda_149d9d0f93016857415718f3165d8236_)
0x1400249ae  nop
0x1400249af  lea     r9, [rbp+arg_0]
0x1400249b3  lea     rdx, [rbp+var_38]
0x1400249b7  mov     rcx, rdi
0x1400249ba  call    ?Loaded@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBURoutedEventHandler@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::Loaded(winrt::auto_revoke_t,winrt::Windows::UI::Xaml::RoutedEventHandler const &)
0x1400249bf  lea     rcx, [rsi+30h]
0x1400249c3  mov     rdx, rax
0x1400249c6  call    ??4?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x1400249cb  lea     rcx, [rbp+var_38]
0x1400249cf  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ
0x1400249d4  nop
0x1400249d5  cmp     [rbp+arg_0], 0
0x1400249da  jz      short loc_1400249E5
0x1400249dc  lea     rcx, [rbp+arg_0]
0x1400249e0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400249e5  mov     rcx, rsi; this
0x1400249e8  call    ?SetFlowDirection@XamlUI@@AEAAXXZ; XamlUI::SetFlowDirection(void)
0x1400249ed  cmp     dword ptr [rsi+18h], 1
0x1400249f1  jnz     loc_140024A7C
0x1400249f7  mov     dword ptr [rbp+arg_0], 0
0x1400249fe  lea     rax, [rbp+arg_0]
0x140024a02  mov     [rbp+var_38], rax
0x140024a06  lea     rax, qword_1400470D8
0x140024a0d  mov     qword ptr [rbp+var_20], rax
0x140024a11  lock inc cs:qword_1400470D8
0x140024a19  cmp     cs:??$factory_cache_entry_v@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>
0x140024a21  jz      short loc_140024A42
0x140024a23  lea     r8, ??$factory_cache_entry_v@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>
0x140024a2a  lea     rdx, [rbp+arg_18]
0x140024a2e  lea     rcx, [rbp+var_38]
0x140024a32  call    ??R_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@QEBA@AEBUIXamlSourceFocusNavigationRequestFactory@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_3207e8c3a392af88c709c9f0a8afe0f7_::operator()(winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory const &)
0x140024a37  nop
0x140024a38  lock dec cs:qword_1400470D8
0x140024a40  jmp     short loc_140024A58
0x140024a42  lock dec cs:qword_1400470D8
0x140024a4a  lea     r8, [rbp+var_38]
0x140024a4e  lea     rdx, [rbp+arg_18]
0x140024a52  call    ??$call@AEAV_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@@?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@@Z
0x140024a57  nop
0x140024a58  lea     r8, [rbp+arg_18]
0x140024a5c  lea     rdx, [rbp+var_38]
0x140024a60  mov     rcx, r15
0x140024a63  call    ?NavigateFocus@?$consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest const &)
0x140024a68  lea     rcx, [rbp+var_38]
0x140024a6c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024a71  nop
0x140024a72  lea     rcx, [rbp+arg_18]
0x140024a76  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024a7b  nop
0x140024a7c  test    rbx, rbx
0x140024a7f  jz      short loc_140024A8A
0x140024a81  lea     rcx, [rbp+var_28]
0x140024a85  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x140024a8a  mov     rbx, [rsp+60h+arg_8]
0x140024a92  add     rsp, 60h
0x140024a96  pop     r15
0x140024a98  pop     r14
0x140024a9a  pop     rdi
0x140024a9b  pop     rsi
0x140024a9c  pop     rbp
0x140024a9d  retn
```
