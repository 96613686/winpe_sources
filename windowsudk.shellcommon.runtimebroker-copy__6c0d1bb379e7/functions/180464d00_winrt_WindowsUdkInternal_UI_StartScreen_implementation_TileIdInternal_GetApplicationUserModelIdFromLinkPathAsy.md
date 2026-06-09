# winrt::WindowsUdkInternal::UI::StartScreen::implementation::TileIdInternal::GetApplicationUserModelIdFromLinkPathAsync$_ResumeCoro$1

- ea: `0x180464d00`
- end: `0x180465248`
- name: `winrt::WindowsUdkInternal::UI::StartScreen::implementation::TileIdInternal::GetApplicationUserModelIdFromLinkPathAsync$_ResumeCoro$1`
- size: `1352`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1804652b4`

## callees

- `0x18000b510`
- `0x180025348`
- `0x1800260c0`
- `0x180026860`
- `0x180027af0`
- `0x18002e634`
- `0x180037df8`
- `0x1800483f4`
- `0x18004b894`
- `0x18005e2c8`
- `0x180064630`
- `0x180074bec`
- `0x1800e3a88`
- `0x180119c20`
- `0x18015cb00`
- `0x18015cfa0`
- `0x180287674`
- `0x18031af58`
- `0x1804627c0`
- `0x180464d00`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18046504e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18046504e`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180464f8f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180464f8f`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180464e0e`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180464e0e`

## string_xrefs

- `0x180464e23`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x180464ee5`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x180464f3e`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x180464fde`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x180465089`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`
- `0x18046513a`: `shellcommon\undockeddevkit\libs\windowsudkinternal.ui.startscreen\tileidinternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall winrt::WindowsUdkInternal::UI::StartScreen::implementation::TileIdInternal::GetApplicationUserModelIdFromLinkPathAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r12
  char v3; // r13
  __int64 v4; // rcx
  std::filesystem::path *v5; // rdi
  const wchar_t *v6; // rdx
  __int64 v7; // r15
  const WCHAR *v8; // rcx
  HRESULT v9; // eax
  __int64 *v10; // rbx
  const wchar_t **v11; // r15
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, __int64); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 **v16; // rdi
  int v17; // eax
  LPCITEMIDLIST *v18; // rbx
  __int64 v19; // rax
  int v20; // eax
  char v21; // di
  _QWORD *v22; // rdi
  HRESULT v23; // eax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // rdx
  __int64 (__fastcall *v26)(__int64, __int64, __int64); // rbx
  ITEMIDLIST *v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rdx
  int v30; // [rsp+20h] [rbp-128h]
  int v31; // [rsp+20h] [rbp-128h]
  int v32; // [rsp+30h] [rbp-118h]
  __int64 v33; // [rsp+58h] [rbp-F0h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  v3 = 1;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
    case 5:
      goto LABEL_45;
    case 2:
      *(_DWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 160) = a1 - 112;
      *(_BYTE *)(a1 + 12) = 0;
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(
        a1 - 112,
        a1 + 12);
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v4, a1);
      return;
    case 4:
      v5 = (std::filesystem::path *)(a1 + 16);
      v6 = winrt::hstring::c_str((winrt::hstring *)(a1 + 184));
      wil::ExpandEnvironmentStringsW<std::wstring,256>(a1 + 16, v6);
      v7 = a1 + 48;
      *(_QWORD *)(a1 + 48) = 0;
      if ( *(_QWORD *)(a1 + 40) <= 7u )
        v8 = (const WCHAR *)(a1 + 16);
      else
        v8 = *(const WCHAR **)v5;
      v9 = SHCreateItemFromParsingName(v8, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)(a1 + 48));
      if ( v9 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
          (const char *)(unsigned int)v9,
          v30);
        goto LABEL_43;
      }
      v10 = (__int64 *)(a1 + 56);
      wil::CoCreateInstance<StartMenuCacheAndAppResolver,IApplicationResolver2,wil::err_exception_policy>(a1 + 56);
      if ( !*(_QWORD *)(a1 + 56) )
        goto LABEL_42;
      v11 = (const wchar_t **)(a1 + 64);
      *(_QWORD *)(a1 + 64) = 0;
      v12 = *v10;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)*v10 + 136LL);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        a1 + 64,
        0);
      v14 = v13(v12, *(_QWORD *)(a1 + 48), 1, a1 + 64);
      v15 = v14;
      v32 = v14;
      if ( v14 == -2147217657 )
      {
        v16 = (__int64 **)(a1 + 72);
        *(_QWORD *)(a1 + 72) = 0;
        v31 = a1 + 72;
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const GUID *, GUID *))(**(_QWORD **)(a1 + 48) + 24LL))(
                *(_QWORD *)(a1 + 48),
                0,
                &BHID_SFUIObject,
                &GUID_000214f9_0000_0000_c000_000000000046);
        if ( v17 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xDF,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
            (const char *)(unsigned int)v17,
            v31);
LABEL_28:
          if ( *v11 && **v11 )
            v3 = 0;
          if ( v3 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xF1,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
              (const char *)v15,
              v31);
          wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(v16);
          goto LABEL_41;
        }
        v18 = (LPCITEMIDLIST *)(a1 + 80);
        *(_QWORD *)(a1 + 80) = 0;
        v19 = **v16;
        *(_QWORD *)(a1 + 88) = a1 + 80;
        *(_QWORD *)(a1 + 96) = 0;
        *(_BYTE *)(a1 + 104) = 1;
        *(_DWORD *)(a1 + 152) = 1;
        v20 = (*(__int64 (**)(void))(v19 + 32))();
        if ( v20 >= 0 )
        {
          v21 = 1;
          if ( *v18 )
            goto LABEL_16;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE2,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
            (const char *)(unsigned int)v20,
            v31);
        }
        v21 = 0;
LABEL_16:
        wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(a1 + 88);
        if ( !v21 )
        {
LABEL_25:
          v27 = (ITEMIDLIST *)*v18;
          *v18 = 0;
          if ( v27 )
            CoTaskMemFree(v27);
          v16 = (__int64 **)(a1 + 72);
          v15 = v32;
          goto LABEL_28;
        }
        v22 = (_QWORD *)(a1 + 112);
        *(_QWORD *)(a1 + 112) = 0;
        v23 = SHCreateItemFromIDList(*v18, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)(a1 + 112));
        v24 = retaddr;
        if ( v23 >= 0 )
        {
          *(_DWORD *)(a1 + 120) = 0x20000000;
          v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v22 + 48LL))(
                  *v22,
                  0x20000000,
                  a1 + 120);
          v24 = retaddr;
          if ( v23 >= 0 )
          {
            if ( (*(_DWORD *)(a1 + 120) & 0x20000000) != 0 )
            {
              v33 = *v22;
              v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)*v22 + 40LL);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
                a1 + 64,
                0);
              v32 = v26(v33, 2147647488LL, a1 + 64);
              v18 = (LPCITEMIDLIST *)(a1 + 80);
              v22 = (_QWORD *)(a1 + 112);
            }
            goto LABEL_24;
          }
          v25 = 232;
        }
        else
        {
          v25 = 229;
        }
        wil::details::in1diag3::_Log_Hr(
          v24,
          (void *)v25,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
          (const char *)(unsigned int)v23,
          v31);
LABEL_24:
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(v22);
        goto LABEL_25;
      }
      if ( v14 < 0 )
      {
        v28 = (unsigned int)v14;
        v29 = 259;
      }
      else
      {
        if ( *v11 && **v11 )
        {
          winrt::hstring::hstring((winrt::hstring *)(a1 + 128), *v11);
          std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *>::promise_type::return_value(
            *(_QWORD *)(a1 + 160),
            a1 + 128);
          winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 128);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(a1 + 64);
          wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 56);
          wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(a1 + 48);
          std::filesystem::path::~path((std::filesystem::path *)(a1 + 16));
          goto LABEL_44;
        }
        v28 = 2147942402LL;
        v29 = 254;
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudkinternal.ui.startscreen\\tileidinternal.cpp",
        (const char *)v28,
        v30);
LABEL_41:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(a1 + 64);
      v10 = (__int64 *)(a1 + 56);
      v5 = (std::filesystem::path *)(a1 + 16);
      v7 = a1 + 48;
LABEL_42:
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(v10);
LABEL_43:
      *(_QWORD *)(a1 + 136) = 0;
      std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *>::promise_type::return_value(
        *(_QWORD *)(a1 + 160),
        a1 + 136);
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 136);
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(v7);
      std::filesystem::path::~path(v5);
LABEL_44:
      *(_QWORD *)(a1 + 144) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::SystemSettings::DataModel::SettingsExtensibility const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_45:
        std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,std::wstring>::promise_type::~promise_type(a1 - 112);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v2 + 88);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), (const struct std::nothrow_t *)0x130);
      }
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180464d00  mov     r11, rsp
0x180464d03  mov     [r11+10h], rbx
0x180464d07  mov     [r11+18h], rsi
0x180464d0b  mov     [r11+8], rcx
0x180464d0f  push    rdi
0x180464d10  push    r12
0x180464d12  push    r13
0x180464d14  push    r14
0x180464d16  push    r15
0x180464d18  sub     rsp, 120h
0x180464d1f  mov     rax, cs:__security_cookie
0x180464d26  xor     rax, rsp
0x180464d29  mov     [rsp+148h+var_38], rax
0x180464d31  mov     r14, rcx
0x180464d34  mov     [rsp+148h+var_F8], rcx
0x180464d39  lea     r12, [r14+8]
0x180464d3d  mov     [rsp+148h+var_D0], r12
0x180464d42  movzx   eax, word ptr [r12]
0x180464d47  mov     [rsp+148h+var_108], ax
0x180464d4c  mov     r13d, 1
0x180464d52  add     ax, r13w
0x180464d56  cmp     ax, 6; switch 7 cases
0x180464d5a  ja      def_180464D75; jumptable 0000000180464D75 default case, case 1
0x180464d60  movsx   rax, ax
0x180464d64  lea     rdx, __ImageBase
0x180464d6b  mov     ecx, ds:(jpt_180464D75 - 180000000h)[rdx+rax*4]
0x180464d72  add     rcx, rdx
0x180464d75  jmp     rcx; switch jump
0x180464d77  xor     esi, esi; jumptable 0000000180464D75 case 4
0x180464d79  jmp     loc_1804651CF
0x180464d7e  xor     esi, esi; jumptable 0000000180464D75 case 3
0x180464d80  mov     [r14+98h], esi
0x180464d87  lea     rcx, [r14-70h]
0x180464d8b  mov     [r14+0A0h], rcx
0x180464d92  lea     rdx, [r14+0Ch]
0x180464d96  mov     [rdx], sil
0x180464d99  call    ??$await_transform@U?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@Uhstring@4@U54@@experimental@std@@U?$IAsyncOperation@UWisePredictor@MachineLearning@AI@WindowsUdk@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEAA$$QEAU?$IAsyncOperation@UPredictor@PredictionUnit@Internal@Windows@winrt@@@Foundation@Windows@2@$$QEAU3452@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::WindowsUdk::AI::MachineLearning::WisePredictor>,void>::await_transform<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor>>(winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::PredictionUnit::Predictor> &&)
0x180464d9e  lea     eax, [rsi+4]
0x180464da1  mov     [r12], ax
0x180464da6  mov     rdx, r14
0x180464da9  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x180464dae  jmp     loc_1804651FD
0x180464db3  xor     esi, esi; jumptable 0000000180464D75 case 6
0x180464db5  jmp     loc_1804651CF
0x180464dba  lea     rdi, [r14+10h]; jumptable 0000000180464D75 case 5
0x180464dbe  lea     rcx, [r12+0B0h]; this
0x180464dc6  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180464dcb  mov     rdx, rax
0x180464dce  mov     rcx, rdi
0x180464dd1  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x180464dd6  nop
0x180464dd7  lea     r15, [r14+30h]
0x180464ddb  xor     esi, esi
0x180464ddd  mov     [r15], rsi
0x180464de0  mov     rax, [r14+28h]
0x180464de4  mov     [rsp+148h+var_A8], rax
0x180464dec  cmp     rax, 7
0x180464df0  jbe     short loc_180464DFF
0x180464df2  mov     rcx, [rdi]
0x180464df5  mov     [rsp+148h+var_C0], rcx
0x180464dfd  jmp     short loc_180464E02
0x180464dff  mov     rcx, rdi; pszPath
0x180464e02  mov     r9, r15; ppv
0x180464e05  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180464e0c  xor     edx, edx; pbc
0x180464e0e  call    cs:__imp_SHCreateItemFromParsingName
0x180464e14  mov     rcx, [rsp+148h]; this
0x180464e1c  test    eax, eax
0x180464e1e  jns     short loc_180464E39
0x180464e20  mov     r9d, eax; char *
0x180464e23  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180464e2a  mov     edx, 0D3h; void *
0x180464e2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180464e34  jmp     loc_18046516B
0x180464e39  lea     rbx, [r14+38h]
0x180464e3d  mov     rcx, rbx
0x180464e40  call    ??$CoCreateInstance@VStartMenuCacheAndAppResolver@@UIApplicationResolver2@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIApplicationResolver2@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<StartMenuCacheAndAppResolver,IApplicationResolver2,wil::err_exception_policy>(ulong)
0x180464e45  nop
0x180464e46  mov     rax, [rbx]
0x180464e49  mov     [rsp+148h+var_E0], rax
0x180464e4e  test    rax, rax
0x180464e51  jz      loc_180465163
0x180464e57  lea     r15, [r14+40h]
0x180464e5b  mov     [r15], rsi
0x180464e5e  mov     rdi, [rbx]
0x180464e61  mov     [rsp+148h+var_E0], rdi
0x180464e66  mov     rax, [rdi]
0x180464e69  mov     rbx, [rax+88h]
0x180464e70  xor     edx, edx
0x180464e72  mov     rcx, r15
0x180464e75  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180464e7a  mov     rdx, [r14+30h]
0x180464e7e  mov     [rsp+148h+var_D8], rdx
0x180464e83  mov     r9, r15
0x180464e86  mov     r8d, r13d
0x180464e89  mov     rcx, rdi
0x180464e8c  mov     rax, rbx
0x180464e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180464e94  mov     ebx, eax
0x180464e96  mov     [rsp+148h+var_118], eax
0x180464e9a  cmp     eax, 80040F07h
0x180464e9f  jnz     loc_1804650A8
0x180464ea5  lea     rdi, [r14+48h]
0x180464ea9  mov     [rdi], rsi
0x180464eac  mov     rcx, [r14+30h]
0x180464eb0  mov     [rsp+148h+var_D8], rcx
0x180464eb5  mov     rax, [rcx]
0x180464eb8  mov     qword ptr [rsp+148h+var_128], rdi; int
0x180464ebd  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180464ec4  lea     r8, BHID_SFUIObject
0x180464ecb  xor     edx, edx
0x180464ecd  mov     rax, [rax+18h]
0x180464ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180464ed6  mov     rcx, [rsp+148h]; this
0x180464ede  test    eax, eax
0x180464ee0  jns     short loc_180464EFB
0x180464ee2  mov     r9d, eax; char *
0x180464ee5  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180464eec  mov     edx, 0DFh; void *
0x180464ef1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180464ef6  jmp     loc_18046505C
0x180464efb  lea     rbx, [r14+50h]
0x180464eff  mov     [rbx], rsi
0x180464f02  mov     rcx, [rdi]
0x180464f05  mov     [rsp+148h+var_C8], rcx
0x180464f0d  mov     rax, [rcx]
0x180464f10  mov     [r14+58h], rbx
0x180464f14  lea     rdx, [r14+60h]
0x180464f18  mov     [rdx], rsi
0x180464f1b  mov     [r14+68h], r13b
0x180464f1f  mov     [r14+98h], r13d
0x180464f26  mov     rax, [rax+20h]
0x180464f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180464f2f  mov     rcx, [rsp+148h]; this
0x180464f37  test    eax, eax
0x180464f39  jns     short loc_180464F51
0x180464f3b  mov     r9d, eax; char *
0x180464f3e  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180464f45  mov     edx, 0E2h; void *
0x180464f4a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180464f4f  jmp     short loc_180464F61
0x180464f51  mov     rax, [rbx]
0x180464f54  mov     [rsp+148h+var_100], rax
0x180464f59  test    rax, rax
0x180464f5c  mov     dil, r13b
0x180464f5f  jnz     short loc_180464F64
0x180464f61  mov     dil, sil
0x180464f64  lea     rcx, [r14+58h]
0x180464f68  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180464f6d  test    dil, dil
0x180464f70  jz      loc_18046503E
0x180464f76  lea     rdi, [r14+70h]
0x180464f7a  mov     [rdi], rsi
0x180464f7d  mov     rcx, [rbx]; pidl
0x180464f80  mov     [rsp+148h+var_100], rcx
0x180464f85  mov     r8, rdi; ppv
0x180464f88  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180464f8f  call    cs:__imp_SHCreateItemFromIDList
0x180464f95  mov     rcx, [rsp+148h]
0x180464f9d  test    eax, eax
0x180464f9f  jns     short loc_180464FA8
0x180464fa1  mov     edx, 0E5h
0x180464fa6  jmp     short loc_180464FDE
0x180464fa8  mov     r9d, 20000000h
0x180464fae  mov     [r14+78h], r9d
0x180464fb2  mov     rcx, [rdi]
0x180464fb5  mov     [rsp+148h+var_F0], rcx
0x180464fba  mov     rax, [rcx]
0x180464fbd  lea     r8, [r14+78h]
0x180464fc1  mov     edx, r9d
0x180464fc4  mov     rax, [rax+30h]
0x180464fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180464fcd  mov     rcx, [rsp+148h]; this
0x180464fd5  test    eax, eax
0x180464fd7  jns     short loc_180464FEF
0x180464fd9  mov     edx, 0E8h; void *
0x180464fde  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180464fe5  mov     r9d, eax; char *
0x180464fe8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180464fed  jmp     short loc_180465035
0x180464fef  mov     eax, [r14+78h]
0x180464ff3  mov     [rsp+148h+var_E8], eax
0x180464ff7  bt      eax, 1Dh
0x180464ffb  jnb     short loc_180465035
0x180464ffd  mov     rdi, [rdi]
0x180465000  mov     [rsp+148h+var_F0], rdi
0x180465005  mov     rax, [rdi]
0x180465008  mov     rbx, [rax+28h]
0x18046500c  xor     edx, edx
0x18046500e  mov     rcx, r15
0x180465011  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180465016  mov     r8, r15
0x180465019  mov     edx, 80028000h
0x18046501e  mov     rcx, rdi
0x180465021  mov     rax, rbx
0x180465024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180465029  mov     [rsp+148h+var_118], eax
0x18046502d  lea     rbx, [r14+50h]
0x180465031  lea     rdi, [r14+70h]
0x180465035  mov     rcx, rdi
0x180465038  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18046503d  nop
0x18046503e  mov     rcx, [rbx]; pv
0x180465041  mov     [rsp+148h+var_100], rcx
0x180465046  mov     [rbx], rsi
0x180465049  test    rcx, rcx
0x18046504c  jz      short loc_180465054
0x18046504e  call    cs:__imp_CoTaskMemFree
0x180465054  lea     rdi, [r14+48h]
0x180465058  mov     ebx, [rsp+148h+var_118]
0x18046505c  mov     rax, [r15]
0x18046505f  mov     [rsp+148h+var_110], rax
0x180465064  test    rax, rax
0x180465067  jz      short loc_180465079
0x180465069  mov     rax, [r15]
0x18046506c  mov     [rsp+148h+var_110], rax
0x180465071  cmp     [rax], si
0x180465074  jz      short loc_180465079
0x180465076  mov     r13b, sil
0x180465079  mov     rcx, [rsp+148h]; this
0x180465081  test    r13b, r13b
0x180465084  jz      short loc_18046509B
0x180465086  mov     r9d, ebx; char *
0x180465089  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180465090  mov     edx, 0F1h; void *
0x180465095  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18046509a  nop
0x18046509b  mov     rcx, rdi
0x18046509e  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1804650a3  jmp     loc_18046514F
0x1804650a8  test    eax, eax
0x1804650aa  js      loc_180465132
0x1804650b0  mov     rax, [r15]
0x1804650b3  mov     [rsp+148h+var_110], rax
0x1804650b8  test    rax, rax
0x1804650bb  jz      short loc_180465125
0x1804650bd  mov     rax, [r15]
0x1804650c0  mov     [rsp+148h+var_110], rax
0x1804650c5  cmp     [rax], si
0x1804650c8  jz      short loc_180465125
0x1804650ca  mov     rdx, [r15]; wchar_t *
0x1804650cd  mov     [rsp+148h+var_110], rdx
0x1804650d2  lea     rbx, [r14+80h]
0x1804650d9  mov     rcx, rbx; this
0x1804650dc  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1804650e1  mov     rdx, rbx
0x1804650e4  mov     rcx, [r14+0A0h]
0x1804650eb  call    ?return_value@promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAUDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@4@@experimental@std@@QEAAX$$QEAUhstring@winrt@@@Z; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *>::promise_type::return_value(winrt::hstring &&)
0x1804650f0  mov     rcx, rbx
0x1804650f3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1804650f8  nop
0x1804650f9  mov     rcx, r15
0x1804650fc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180465101  nop
0x180465102  lea     rcx, [r14+38h]
0x180465106  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18046510b  nop
0x18046510c  lea     rcx, [r14+30h]
0x180465110  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x180465115  nop
0x180465116  lea     rcx, [r14+10h]; this
0x18046511a  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18046511f  nop
0x180465120  jmp     loc_1804651AD
0x180465125  mov     r9d, 80070002h
0x18046512b  mov     edx, 0FEh
0x180465130  jmp     short loc_18046513A
0x180465132  mov     r9d, eax; char *
0x180465135  mov     edx, 103h; void *
0x18046513a  lea     r8, aShellcommonUnd_69; "shellcommon\\undockeddevkit\\libs\\wind"...
0x180465141  mov     rcx, [rsp+148h]; this
0x180465149  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18046514e  nop
0x18046514f  mov     rcx, r15
0x180465152  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180465157  lea     rbx, [r14+38h]
0x18046515b  lea     rdi, [r14+10h]
0x18046515f  lea     r15, [r14+30h]
0x180465163  mov     rcx, rbx
0x180465166  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18046516b  lea     rbx, [r14+88h]
0x180465172  mov     [rbx], rsi
0x180465175  mov     rdx, rbx
0x180465178  mov     rcx, [r14+0A0h]
0x18046517f  call    ?return_value@promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAUDictatedTextInputSession@implementation@Text@Input@UI@WindowsUdk@4@@experimental@std@@QEAAX$$QEAUhstring@winrt@@@Z; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::WindowsUdk::UI::Input::Text::implementation::DictatedTextInputSession *>::promise_type::return_value(winrt::hstring &&)
0x180465184  mov     rcx, rbx
0x180465187  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18046518c  nop
0x18046518d  mov     rcx, r15
0x180465190  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x180465195  nop
0x180465196  mov     rcx, rdi; this
0x180465199  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18046519e  nop
0x18046519f  jmp     short loc_1804651AD
0x1804651a1  xor     esi, esi
0x1804651a3  mov     r12, [rsp+148h+var_D0]
0x1804651a8  mov     r14, [rsp+148h+var_F8]
0x1804651ad  lea     rcx, [r14+90h]
0x1804651b4  lea     rax, [r14-70h]
  ... truncated ...
```
