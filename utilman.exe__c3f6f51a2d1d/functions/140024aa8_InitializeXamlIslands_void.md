# InitializeXamlIslands(void)

- ea: `0x140024aa8`
- end: `0x140024c21`
- name: `?InitializeXamlIslands@@YA?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@XZ`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000e72c`

## callees

- `0x14000ccdc`
- `0x14001fae4`
- `0x140022de8`
- `0x140023674`
- `0x140023c24`
- `0x140023d44`
- `0x140024aa8`
- `0x1400258a8`
- `0x140029010`

## import_xrefs

- `USER32!ShowWindow` at `0x140024bcd`
- `USER32!ShowWindow` at `0x140024bcd`

## string_xrefs

- `0x140024bb5`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall InitializeXamlIslands(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rax
  _QWORD *result; // rax
  int v7; // [rsp+20h] [rbp-28h]
  _QWORD v8[4]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 *v12; // [rsp+60h] [rbp+18h] BYREF
  HWND hWnd; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    v12 = &qword_1400470F8;
    _InterlockedIncrement64(&qword_1400470F8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics> )
    {
      winrt::impl::consume_Windows_UI_Core_ICoreWindowStatic<winrt::Windows::UI::Core::ICoreWindowStatic>::GetForCurrentThread(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>,
        &v11);
      _InterlockedDecrement64(&qword_1400470F8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1400470F8);
      v12 = (__int64 *)_lambda_55039be7b7b77d56f41928124535a284_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>::call<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager (*)(winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics const &)>(
        a1,
        &v11,
        &v12);
    }
    hWnd = (HWND)&qword_140047118;
    _InterlockedIncrement64(&qword_140047118);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> )
    {
      winrt::impl::consume_Windows_UI_Core_ICoreWindowStatic<winrt::Windows::UI::Core::ICoreWindowStatic>::GetForCurrentThread(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>,
        &v12);
      _InterlockedDecrement64(&qword_140047118);
    }
    else
    {
      _InterlockedDecrement64(&qword_140047118);
      hWnd = (HWND)_lambda_55039be7b7b77d56f41928124535a284_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::call<winrt::Windows::UI::Core::CoreWindow (*)(winrt::Windows::UI::Core::ICoreWindowStatic const &)>(
        v2,
        &v12,
        &hWnd);
    }
    if ( v12 )
    {
      winrt::impl::as<ICoreWindowInterop,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(v8);
      hWnd = 0;
      v3 = v8[0];
      v4 = (*(__int64 (__fastcall **)(_QWORD, HWND *))(*(_QWORD *)v8[0] + 24LL))(v8[0], &hWnd);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x11,
          (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
          (const char *)(unsigned int)v4,
          v7);
      ShowWindow(hWnd, 0);
      if ( v3 )
        winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(v8);
    }
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v12);
    v5 = v11;
    v11 = 0;
    *a1 = v5;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
    result = a1;
  }
  catch ( ... )
  {
    *a1 = 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x140024aa8  mov     [rsp+arg_0], rcx
0x140024aad  push    rbx
0x140024aae  push    rdi
0x140024aaf  sub     rsp, 38h
0x140024ab3  mov     rbx, rcx
0x140024ab6  lea     rax, qword_1400470F8
0x140024abd  mov     [rsp+48h+arg_10], rax
0x140024ac2  lock inc cs:qword_1400470F8
0x140024aca  cmp     cs:??$factory_cache_entry_v@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>
0x140024ad2  jz      short loc_140024AF0
0x140024ad4  lea     rdx, [rsp+48h+arg_8]
0x140024ad9  lea     rcx, ??$factory_cache_entry_v@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>
0x140024ae0  call    ?GetForCurrentThread@?$consume_Windows_UI_Core_ICoreWindowStatic@UICoreWindowStatic@Core@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Core_ICoreWindowStatic<winrt::Windows::UI::Core::ICoreWindowStatic>::GetForCurrentThread(void)
0x140024ae5  nop
0x140024ae6  lock dec cs:qword_1400470F8
0x140024aee  jmp     short loc_140024B14
0x140024af0  lock dec cs:qword_1400470F8
0x140024af8  lea     rax, ?_lambda_invoker_cdecl_@_lambda_55039be7b7b77d56f41928124535a284_@@CA@AEBUIWindowsXamlManagerStatics@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_55039be7b7b77d56f41928124535a284_::_lambda_invoker_cdecl_(winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics const &)
0x140024aff  mov     [rsp+48h+arg_10], rax
0x140024b04  lea     r8, [rsp+48h+arg_10]
0x140024b09  lea     rdx, [rsp+48h+arg_8]
0x140024b0e  call    ??$call@P6A?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@AEBUIWindowsXamlManagerStatics@23456@@Z@?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@2@AEBUIWindowsXamlManagerStatics@45672@@Z@Z
0x140024b13  nop
0x140024b14  lea     rax, qword_140047118
0x140024b1b  mov     [rsp+48h+hWnd], rax
0x140024b20  lock inc cs:qword_140047118
0x140024b28  cmp     cs:??$factory_cache_entry_v@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::winrt::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>
0x140024b30  jz      short loc_140024B4E
0x140024b32  lea     rdx, [rsp+48h+arg_10]
0x140024b37  lea     rcx, ??$factory_cache_entry_v@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::winrt::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>
0x140024b3e  call    ?GetForCurrentThread@?$consume_Windows_UI_Core_ICoreWindowStatic@UICoreWindowStatic@Core@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Core_ICoreWindowStatic<winrt::Windows::UI::Core::ICoreWindowStatic>::GetForCurrentThread(void)
0x140024b43  nop
0x140024b44  lock dec cs:qword_140047118
0x140024b4c  jmp     short loc_140024B72
0x140024b4e  lock dec cs:qword_140047118
0x140024b56  lea     rax, ?_lambda_invoker_cdecl_@_lambda_55039be7b7b77d56f41928124535a284_@@CA@AEBUIWindowsXamlManagerStatics@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_55039be7b7b77d56f41928124535a284_::_lambda_invoker_cdecl_(winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics const &)
0x140024b5d  mov     [rsp+48h+hWnd], rax
0x140024b62  lea     r8, [rsp+48h+hWnd]
0x140024b67  lea     rdx, [rsp+48h+arg_10]
0x140024b6c  call    ??$call@P6A?AUCoreWindow@Core@UI@Windows@winrt@@AEBUICoreWindowStatic@2345@@Z@?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUCoreWindow@Core@UI@Windows@2@AEBUICoreWindowStatic@4562@@Z@Z
0x140024b71  nop
0x140024b72  mov     rdx, [rsp+48h+arg_10]
0x140024b77  test    rdx, rdx
0x140024b7a  jz      short loc_140024BEA
0x140024b7c  lea     rcx, [rsp+48h+var_20]
0x140024b81  call    ??$as@UICoreWindowInterop@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@$0A@@impl@winrt@@YA?AU?$com_ptr@UICoreWindowInterop@@@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<ICoreWindowInterop,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x140024b86  nop
0x140024b87  mov     [rsp+48h+hWnd], 0
0x140024b90  mov     rdi, [rsp+48h+var_20]
0x140024b95  mov     rax, [rdi]
0x140024b98  lea     rdx, [rsp+48h+hWnd]
0x140024b9d  mov     rcx, rdi
0x140024ba0  mov     rax, [rax+18h]
0x140024ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024ba9  mov     rcx, [rsp+48h]; this
0x140024bae  test    eax, eax
0x140024bb0  jns     short loc_140024BC6
0x140024bb2  mov     r9d, eax; char *
0x140024bb5  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140024bbc  mov     edx, 11h; void *
0x140024bc1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140024bc6  xor     edx, edx; nCmdShow
0x140024bc8  mov     rcx, [rsp+48h+hWnd]; hWnd
0x140024bcd  call    cs:__imp_ShowWindow
0x140024bd4  nop     dword ptr [rax+rax+00h]
0x140024bd9  nop
0x140024bda  test    rdi, rdi
0x140024bdd  jz      short loc_140024BEA
0x140024bdf  lea     rcx, [rsp+48h+var_20]
0x140024be4  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x140024be9  nop
0x140024bea  lea     rcx, [rsp+48h+arg_10]
0x140024bef  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024bf4  mov     rax, [rsp+48h+arg_8]
0x140024bf9  mov     [rsp+48h+arg_8], 0
0x140024c02  mov     [rbx], rax
0x140024c05  lea     rcx, [rsp+48h+arg_8]
0x140024c0a  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140024c0f  mov     rax, rbx
0x140024c12  jmp     short loc_140024C19
0x140024c14  mov     rax, [rsp+48h+arg_0]
0x140024c19  add     rsp, 38h
0x140024c1d  pop     rdi
0x140024c1e  pop     rbx
0x140024c1f  retn
```
