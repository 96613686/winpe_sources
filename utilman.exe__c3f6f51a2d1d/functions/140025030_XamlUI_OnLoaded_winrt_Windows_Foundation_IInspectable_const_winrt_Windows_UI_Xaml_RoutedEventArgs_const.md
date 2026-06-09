# XamlUI::OnLoaded(winrt::Windows::Foundation::IInspectable const &,winrt::Windows::UI::Xaml::RoutedEventArgs const &)

- ea: `0x140025030`
- end: `0x1400250ee`
- name: `?OnLoaded@XamlUI@@AEAAXAEBUIInspectable@Foundation@Windows@winrt@@AEBURoutedEventArgs@Xaml@UI@45@@Z`
- size: `190`
- prototype: `void __fastcall(XamlUI *__hidden this, const struct IInspectable *, const struct winrt::Windows::UI::Xaml::RoutedEventArgs *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009ee0`
- `0x140022dcc`
- `0x1400235f8`
- `0x140024208`
- `0x1400242f0`
- `0x140024cf4`
- `0x140025030`
- `0x1400252ac`

## import_xrefs

- `USER32!ShowWindow` at `0x140025071`
- `USER32!ShowWindow` at `0x140025071`

## string_xrefs

- `0x140025081`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XamlUI::OnLoaded(
        HWND *this,
        const struct IInspectable *a2,
        const struct winrt::Windows::UI::Xaml::RoutedEventArgs *a3)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ecx
  BOOL v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // rax
  const char *v11; // r9
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF

  XamlUI::ResizeParentWindowToFitXamlContent((XamlUI *)this, 1);
  v4 = 0;
  v5 = *((_DWORD *)this + 6);
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 == 1 )
        v4 = 7;
    }
    else
    {
      v4 = 1;
    }
  }
  else
  {
    v4 = 4;
  }
  v7 = ShowWindow(this[1], v4);
  try
  {
    if ( !v7 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x92,
        (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
        v8);
    ____0VXamlUI__P80_EAAXAEBUIInspectable_Foundation_Windows_winrt__0__E___EventHandler_UIInspectable_Foundation_Windows_winrt___Foundation_Windows_winrt__QEAA_PEAVXamlUI__P84_EAAXAEBUIInspectable_123_1__E_Z(
      &v14,
      this);
    v10 = winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::LayoutUpdated(
            this + 5,
            v12,
            v9,
            &v14);
    __4__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBJA_AA_impl_winrt__QEAAAEAU012___QEAU012__Z(
      this + 8,
      v10);
    __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBJA_AA_impl_winrt__QEAA_XZ(v12);
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x97,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v11);
  }
}

```

## disassembly

```asm
0x140025030  mov     [rsp+arg_8], rbx
0x140025035  push    rdi
0x140025036  sub     rsp, 30h
0x14002503a  mov     rbx, rcx
0x14002503d  mov     dl, 1; bool
0x14002503f  call    ?ResizeParentWindowToFitXamlContent@XamlUI@@AEAAX_N@Z; XamlUI::ResizeParentWindowToFitXamlContent(bool)
0x140025044  xor     edx, edx
0x140025046  mov     ecx, [rbx+18h]
0x140025049  test    ecx, ecx
0x14002504b  jz      short loc_140025063
0x14002504d  sub     ecx, 1
0x140025050  jz      short loc_14002505C
0x140025052  cmp     ecx, 1
0x140025055  jnz     short loc_140025068
0x140025057  lea     edx, [rcx+6]
0x14002505a  jmp     short loc_140025068
0x14002505c  mov     edx, 1
0x140025061  jmp     short loc_140025068
0x140025063  mov     edx, 4; nCmdShow
0x140025068  mov     rdi, [rsp+38h]
0x14002506d  mov     rcx, [rbx+8]; hWnd
0x140025071  call    cs:__imp_ShowWindow
0x140025078  nop     dword ptr [rax+rax+00h]
0x14002507d  test    eax, eax
0x14002507f  jnz     short loc_140025095
0x140025081  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140025088  mov     edx, 92h; void *
0x14002508d  mov     rcx, rdi; this
0x140025090  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140025095  mov     rdx, rbx
0x140025098  lea     rcx, [rsp+38h+arg_0]
0x14002509d  call    ??$?0VXamlUI@@P80@EAAXAEBUIInspectable@Foundation@Windows@winrt@@0@_E@?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@PEAVXamlUI@@P84@EAAXAEBUIInspectable@123@1@_E@Z
0x1400250a2  nop
0x1400250a3  lea     rcx, [rbx+28h]
0x1400250a7  lea     r9, [rsp+38h+arg_0]
0x1400250ac  lea     rdx, [rsp+38h+var_18]
0x1400250b1  call    ?LayoutUpdated@?$consume_Windows_UI_Xaml_IFrameworkElement@UIFrameworkElement@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@Uauto_revoke_t@3@AEBU?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_IFrameworkElement<winrt::Windows::UI::Xaml::IFrameworkElement>::LayoutUpdated(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable> const &)
0x1400250b6  lea     rcx, [rbx+40h]
0x1400250ba  mov     rdx, rax
0x1400250bd  call    ??4?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBJA@AA@impl@winrt@@QEAAAEAU012@$$QEAU012@@Z
0x1400250c2  lea     rcx, [rsp+38h+var_18]
0x1400250c7  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBJA@AA@impl@winrt@@QEAA@XZ
0x1400250cc  nop
0x1400250cd  cmp     [rsp+38h+arg_0], 0
0x1400250d3  jz      short loc_1400250E0
0x1400250d5  lea     rcx, [rsp+38h+arg_0]
0x1400250da  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400250df  nop
0x1400250e0  jmp     short $+2
0x1400250e2  mov     rbx, [rsp+38h+arg_8]
0x1400250e7  add     rsp, 30h
0x1400250eb  pop     rdi
0x1400250ec  retn
```
