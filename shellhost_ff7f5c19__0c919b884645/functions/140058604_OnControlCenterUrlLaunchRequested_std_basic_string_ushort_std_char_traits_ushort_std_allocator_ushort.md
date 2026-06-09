# OnControlCenterUrlLaunchRequested(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140058604`
- end: `0x140058898`
- name: `?OnControlCenterUrlLaunchRequested@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1400584cc`

## callees

- `0x140009d6c`
- `0x140009f9c`
- `0x14000a0d4`
- `0x14000a10c`
- `0x14000a8c0`
- `0x14000b638`
- `0x14000f380`
- `0x14000f7e0`
- `0x14004c588`
- `0x14004ce80`
- `0x14004f250`
- `0x14004f6e4`
- `0x140051d34`
- `0x140052978`
- `0x140052bf8`
- `0x140054394`
- `0x140054de0`
- `0x140058604`
- `0x14005b298`
- `0x14005d654`
- `0x140067010`

## string_xrefs

- `0x140058777`: `?IsProtocol=true`
- `0x1400587c3`: `?IsProtocol=true`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OnControlCenterUrlLaunchRequested(_QWORD *a1)
{
  unsigned __int64 v2; // rax
  _QWORD *v3; // rsi
  char *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  void *v9; // rax
  __int64 v10; // rax
  int *v11; // rax
  unsigned int v12; // eax
  int *v14; // [rsp+20h] [rbp-89h] BYREF
  int v15; // [rsp+28h] [rbp-81h] BYREF
  __int64 v16; // [rsp+30h] [rbp-79h] BYREF
  __int64 v17; // [rsp+38h] [rbp-71h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-69h]
  _BYTE v19[32]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp-41h]
  _QWORD v21[4]; // [rsp+70h] [rbp-39h] BYREF
  int v22; // [rsp+90h] [rbp-19h] BYREF
  __int128 v23; // [rsp+98h] [rbp-11h]
  _BYTE v24[32]; // [rsp+B0h] [rbp+7h] BYREF

  v20 = a1;
  v2 = a1[2];
  if ( a1[3] <= 7u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  if ( v2 < 0x11 )
  {
    v6 = -1;
  }
  else
  {
    v4 = (char *)v3 + 2 * v2;
    v5 = _std_search_2(v3, v4, c_controlCenterUriScheme, 17);
    if ( (char *)v5 == v4 )
      return std::wstring::~wstring(a1);
    v6 = (v5 - (__int64)v3) >> 1;
  }
  if ( !v6 )
  {
    v15 = 6;
    v14 = &v15;
    v18 = &qword_140083918;
    _InterlockedIncrement64(&qword_140083918);
    if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory> )
    {
      _lambda_c784a7e41fe1a5698e55a9117bd5b7f8_::operator()(
        &v14,
        &v17,
        &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>);
      _InterlockedDecrement64(&qword_140083918);
    }
    else
    {
      _InterlockedDecrement64(&qword_140083918);
      winrt::impl::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::call<_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_ &>(
        a1,
        &v17,
        &v14);
    }
    v18 = &qword_140083938;
    _InterlockedIncrement64(&qword_140083938);
    if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory> )
    {
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions>(
        &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>,
        &v16);
      _InterlockedDecrement64(&qword_140083938);
    }
    else
    {
      _InterlockedDecrement64(&qword_140083938);
      v14 = (int *)_lambda_4412af45f4a36015e2ea70df7029dae5_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v7,
        &v16,
        &v14);
    }
    winrt::impl::consume_WindowsUdk_UI_Shell_IShowShellViewOptions3<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions>::TransferForegroundRights(&v16);
    std::wstring::substr(a1, v21, 17);
    if ( v21[2] )
    {
      v9 = (void *)std::operator+<unsigned short>(v24, v8, v21);
      v10 = std::wstring::_Append<unsigned short>(v9);
      std::wstring::wstring(&v22, v10);
      winrt::param::hstring::hstring(v19, &v22);
      winrt::impl::consume_WindowsUdk_UI_Shell_IShowShellViewOptions<winrt::WindowsUdk::UI::Shell::IShowShellViewOptions>::Context(
        &v16,
        v19);
      std::wstring::~wstring(&v22);
      std::wstring::~wstring(v24);
    }
    else
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v24, L"?IsProtocol=true");
      winrt::impl::consume_WindowsUdk_UI_Shell_IShowShellViewOptions<winrt::WindowsUdk::UI::Shell::IShowShellViewOptions>::Context(
        &v16,
        v24);
    }
    v11 = (int *)v21;
    if ( v21[3] > 7u )
      v11 = (int *)v21[0];
    v14 = v11;
    ShellHostTelemetry::UrlLaunchControlCenterRequested<unsigned short const *>(&v14);
    v14 = 0;
    v22 = 0;
    v23 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, int **))(*(_QWORD *)v17 + 88LL))(v17, v16, &v14);
    winrt::check_hresult(&v15, v12, &v22);
    winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<bool>>(&v14);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v14);
    std::wstring::~wstring(v21);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v16);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v17);
  }
  return std::wstring::~wstring(a1);
}

```

## disassembly

```asm
0x140058604  push    rbp
0x140058606  push    rbx
0x140058607  push    rsi
0x140058608  push    rdi
0x140058609  lea     rbp, [rsp-3Fh]
0x14005860e  sub     rsp, 0E8h
0x140058615  mov     rax, cs:__security_cookie
0x14005861c  xor     rax, rsp
0x14005861f  mov     [rbp+57h+var_30], rax
0x140058623  mov     rdi, rcx
0x140058626  mov     [rbp+57h+var_98], rcx
0x14005862a  mov     rax, [rcx+10h]
0x14005862e  cmp     qword ptr [rcx+18h], 7
0x140058633  jbe     short loc_14005863A
0x140058635  mov     rsi, [rcx]
0x140058638  jmp     short loc_14005863D
0x14005863a  mov     rsi, rdi
0x14005863d  cmp     rax, 11h
0x140058641  jb      short loc_140058670
0x140058643  lea     rbx, [rsi+rax*2]
0x140058647  mov     r9d, 11h
0x14005864d  mov     r8, cs:?c_controlCenterUriScheme@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_controlCenterUriScheme
0x140058654  mov     rdx, rbx
0x140058657  mov     rcx, rsi
0x14005865a  call    __std_search_2
0x14005865f  cmp     rax, rbx
0x140058662  jz      loc_140058878
0x140058668  sub     rax, rsi
0x14005866b  sar     rax, 1
0x14005866e  jmp     short loc_140058674
0x140058670  or      rax, 0FFFFFFFFFFFFFFFFh
0x140058674  test    rax, rax
0x140058677  jnz     loc_140058878
0x14005867d  mov     [rsp+100h+var_D8], 6
0x140058685  lea     rax, [rsp+100h+var_D8]
0x14005868a  mov     [rsp+100h+var_E0], rax
0x14005868f  lea     rax, qword_140083918
0x140058696  mov     [rbp+57h+var_C0], rax
0x14005869a  lock inc cs:qword_140083918
0x1400586a2  cmp     cs:??$factory_cache_entry_v@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@12@A, 0; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>
0x1400586aa  jz      short loc_1400586CC
0x1400586ac  lea     r8, ??$factory_cache_entry_v@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>
0x1400586b3  lea     rdx, [rbp+57h+var_C8]
0x1400586b7  lea     rcx, [rsp+100h+var_E0]
0x1400586bc  call    ??R_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@QEBA@AEBUIShellViewCoordinatorFactory@Shell@UI@WindowsUdk@winrt@@@Z; _lambda_c784a7e41fe1a5698e55a9117bd5b7f8_::operator()(winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory const &)
0x1400586c1  nop
0x1400586c2  lock dec cs:qword_140083918
0x1400586ca  jmp     short loc_1400586E3
0x1400586cc  lock dec cs:qword_140083918
0x1400586d4  lea     r8, [rsp+100h+var_E0]
0x1400586d9  lea     rdx, [rbp+57h+var_C8]
0x1400586dd  call    ??$call@AEAV_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@@?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@@Z
0x1400586e2  nop
0x1400586e3  lea     rax, qword_140083938
0x1400586ea  mov     [rbp+57h+var_C0], rax
0x1400586ee  lock inc cs:qword_140083938
0x1400586f6  cmp     cs:??$factory_cache_entry_v@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@3U?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@12@A, 0; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>
0x1400586fe  jz      short loc_14005871B
0x140058700  lea     rdx, [rbp+57h+var_D0]
0x140058704  lea     rcx, ??$factory_cache_entry_v@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@3U?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@12@A; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>
0x14005870b  call    ??$ActivateInstance@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUShowShellViewOptions@Shell@UI@WindowsUdk@3@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions>(void)
0x140058710  nop
0x140058711  lock dec cs:qword_140083938
0x140058719  jmp     short loc_14005873E
0x14005871b  lock dec cs:qword_140083938
0x140058723  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4412af45f4a36015e2ea70df7029dae5_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_4412af45f4a36015e2ea70df7029dae5_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x14005872a  mov     [rsp+100h+var_E0], rax
0x14005872f  lea     r8, [rsp+100h+var_E0]
0x140058734  lea     rdx, [rbp+57h+var_D0]
0x140058738  call    ??$call@P6A?AUShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@AEBUIActivationFactory@Foundation@Windows@5@@Z@?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@QEAA?A_P$$QEAP6A?AUShowShellViewOptions@Shell@UI@WindowsUdk@2@AEBUIActivationFactory@Foundation@Windows@2@@Z@Z
0x14005873d  nop
0x14005873e  lea     rcx, [rbp+57h+var_D0]
0x140058742  call    ?TransferForegroundRights@?$consume_WindowsUdk_UI_Shell_IShowShellViewOptions3@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@_N@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShowShellViewOptions3<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions>::TransferForegroundRights(bool)
0x140058747  or      r9, 0FFFFFFFFFFFFFFFFh
0x14005874b  lea     r8d, [r9+12h]
0x14005874f  lea     rdx, [rbp+57h+var_90]
0x140058753  mov     rcx, rdi
0x140058756  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x14005875b  nop
0x14005875c  lea     rcx, [rbp+57h+var_50]; this
0x140058760  cmp     [rbp+57h+var_80], 0
0x140058765  jbe     short loc_1400587C3
0x140058767  lea     r8, [rbp+57h+var_90]
0x14005876b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x140058770  nop
0x140058771  mov     r8d, 10h
0x140058777  lea     rdx, aIsprotocolTrue; "?IsProtocol=true"
0x14005877e  mov     rcx, rax; Src
0x140058781  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x140058786  mov     rdx, rax
0x140058789  lea     rcx, [rbp+57h+var_70]
0x14005878d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x140058792  nop
0x140058793  lea     rdx, [rbp+57h+var_70]
0x140058797  lea     rcx, [rbp+57h+var_B8]
0x14005879b  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1400587a0  lea     rdx, [rbp+57h+var_B8]
0x1400587a4  lea     rcx, [rbp+57h+var_D0]
0x1400587a8  call    ?Context@?$consume_WindowsUdk_UI_Shell_IShowShellViewOptions@UIShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShowShellViewOptions<winrt::WindowsUdk::UI::Shell::IShowShellViewOptions>::Context(winrt::param::hstring const &)
0x1400587ad  nop
0x1400587ae  lea     rcx, [rbp+57h+var_70]
0x1400587b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400587b7  nop
0x1400587b8  lea     rcx, [rbp+57h+var_50]
0x1400587bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400587c1  jmp     short loc_1400587DC
0x1400587c3  lea     rdx, aIsprotocolTrue; "?IsProtocol=true"
0x1400587ca  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1400587cf  lea     rdx, [rbp+57h+var_50]
0x1400587d3  lea     rcx, [rbp+57h+var_D0]
0x1400587d7  call    ?Context@?$consume_WindowsUdk_UI_Shell_IShowShellViewOptions@UIShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShowShellViewOptions<winrt::WindowsUdk::UI::Shell::IShowShellViewOptions>::Context(winrt::param::hstring const &)
0x1400587dc  lea     rax, [rbp+57h+var_90]
0x1400587e0  cmp     [rbp+57h+var_78], 7
0x1400587e5  cmova   rax, [rbp+57h+var_90]
0x1400587ea  mov     [rsp+100h+var_E0], rax
0x1400587ef  lea     rcx, [rsp+100h+var_E0]
0x1400587f4  call    ??$UrlLaunchControlCenterRequested@PEBG@ShellHostTelemetry@@SAX$$QEAPEBG@Z; ShellHostTelemetry::UrlLaunchControlCenterRequested<ushort const *>(ushort const * &&)
0x1400587f9  mov     [rsp+100h+var_E0], 0
0x140058802  mov     rcx, [rbp+57h+var_C8]
0x140058806  mov     [rbp+57h+var_70], 0
0x14005880d  xorps   xmm0, xmm0
0x140058810  movdqu  [rbp+57h+var_68], xmm0
0x140058815  mov     rax, [rcx]
0x140058818  lea     r8, [rsp+100h+var_E0]
0x14005881d  mov     rdx, [rbp+57h+var_D0]
0x140058821  mov     rax, [rax+58h]
0x140058825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005882a  lea     r8, [rbp+57h+var_70]
0x14005882e  mov     edx, eax
0x140058830  lea     rcx, [rsp+100h+var_D8]
0x140058835  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005883a  mov     rax, [rsp+100h+var_E0]
0x14005883f  mov     [rsp+100h+var_E0], rax
0x140058844  lea     rcx, [rsp+100h+var_E0]
0x140058849  call    ??$wait_get@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@@Z
0x14005884e  nop
0x14005884f  lea     rcx, [rsp+100h+var_E0]; this
0x140058854  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140058859  nop
0x14005885a  lea     rcx, [rbp+57h+var_90]
0x14005885e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058863  nop
0x140058864  lea     rcx, [rbp+57h+var_D0]; this
0x140058868  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005886d  nop
0x14005886e  lea     rcx, [rbp+57h+var_C8]; this
0x140058872  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140058877  nop
0x140058878  mov     rcx, rdi
0x14005887b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058880  mov     rcx, [rbp+57h+var_30]
0x140058884  xor     rcx, rsp; StackCookie
0x140058887  call    __security_check_cookie
0x14005888c  add     rsp, 0E8h
0x140058893  pop     rdi
0x140058894  pop     rsi
0x140058895  pop     rbx
0x140058896  pop     rbp
0x140058897  retn
```
