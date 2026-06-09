# ??$call@AEAV_lambda_bbfd22c1d265b39b75be756b5c167b68_@@@?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_bbfd22c1d265b39b75be756b5c167b68_@@@Z

- ea: `0x1400239f4`
- end: `0x140023b05`
- name: `??$call@AEAV_lambda_bbfd22c1d265b39b75be756b5c167b68_@@@?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_bbfd22c1d265b39b75be756b5c167b68_@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400247dc`

## callees

- `0x140003539`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14001f304`
- `0x1400239f4`
- `0x14002400c`
- `0x1400243a0`
- `0x140029010`

## string_xrefs

- `0x140023a0e`: `Windows.UI.Xaml.Markup.XamlReader`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>::call<_lambda_bbfd22c1d265b39b75be756b5c167b68_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.UI.Xaml.Markup.XamlReader";
  v7[1] = 33;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_140047138;
    _InterlockedIncrement64(&qword_140047138);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140047140);
    }
    _lambda_bbfd22c1d265b39b75be756b5c167b68_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>);
    _InterlockedDecrement64(&qword_140047138);
  }
  else
  {
    _lambda_bbfd22c1d265b39b75be756b5c167b68_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x1400239f4  mov     [rsp-18h+arg_8], rbx
0x1400239f9  mov     [rsp-18h+arg_0], rcx
0x1400239fe  push    rbp
0x1400239ff  push    rsi
0x140023a00  push    rdi
0x140023a01  mov     rbp, rsp
0x140023a04  sub     rsp, 60h
0x140023a08  mov     rsi, r8
0x140023a0b  mov     rbx, rdx
0x140023a0e  lea     rax, aWindowsUiXamlM; "Windows.UI.Xaml.Markup.XamlReader"
0x140023a15  mov     [rbp+var_38], rax
0x140023a19  mov     [rbp+var_30], 21h ; '!'
0x140023a21  lea     rdx, [rbp+var_38]
0x140023a25  lea     rcx, [rbp+var_28]
0x140023a29  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x140023a2e  lea     rdx, [rbp+var_28]
0x140023a32  lea     rcx, [rbp+arg_0]
0x140023a36  call    ??$get_activation_factory@UIXamlReaderStatics@Markup@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIXamlReaderStatics@Markup@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>(winrt::param::hstring const &)
0x140023a3b  nop
0x140023a3c  mov     rdi, [rbp+arg_0]
0x140023a40  test    rdi, rdi
0x140023a43  jz      loc_140023AD8
0x140023a49  mov     [rbp+arg_18], 0
0x140023a51  mov     rax, [rdi]
0x140023a54  lea     r8, [rbp+arg_18]
0x140023a58  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140023a5f  mov     rcx, rdi
0x140023a62  mov     rax, [rax]
0x140023a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023a6a  mov     rax, [rbp+arg_18]
0x140023a6e  mov     [rbp+arg_18], rax
0x140023a72  test    rax, rax
0x140023a75  jz      short loc_140023AD8
0x140023a77  lea     rcx, [rbp+arg_18]
0x140023a7b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140023a80  lea     rax, qword_140047138
0x140023a87  mov     [rbp+arg_18], rax
0x140023a8b  lock inc cs:qword_140047138
0x140023a93  xor     eax, eax
0x140023a95  lock cmpxchg cs:??$factory_cache_entry_v@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>
0x140023a9e  jnz     short loc_140023ABB
0x140023aa0  mov     [rbp+arg_0], 0
0x140023aa8  lea     rdx, stru_140047140; ListEntry
0x140023aaf  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140023ab6  call    WINRT_IMPL_InterlockedPushEntrySList
0x140023abb  lea     r8, ??$factory_cache_entry_v@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlReader@Markup@Xaml@UI@Windows@winrt@@UIXamlReaderStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Markup::XamlReader,winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics>
0x140023ac2  mov     rdx, rbx
0x140023ac5  mov     rcx, rsi
0x140023ac8  call    ??R_lambda_bbfd22c1d265b39b75be756b5c167b68_@@QEBA@AEBUIXamlReaderStatics@Markup@Xaml@UI@Windows@winrt@@@Z; _lambda_bbfd22c1d265b39b75be756b5c167b68_::operator()(winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics const &)
0x140023acd  nop
0x140023ace  lock dec cs:qword_140047138
0x140023ad6  jmp     short loc_140023AE8
0x140023ad8  lea     r8, [rbp+arg_0]
0x140023adc  mov     rdx, rbx
0x140023adf  mov     rcx, rsi
0x140023ae2  call    ??R_lambda_bbfd22c1d265b39b75be756b5c167b68_@@QEBA@AEBUIXamlReaderStatics@Markup@Xaml@UI@Windows@winrt@@@Z; _lambda_bbfd22c1d265b39b75be756b5c167b68_::operator()(winrt::Windows::UI::Xaml::Markup::IXamlReaderStatics const &)
0x140023ae7  nop
0x140023ae8  lea     rcx, [rbp+arg_0]
0x140023aec  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140023af1  mov     rax, rbx
0x140023af4  mov     rbx, [rsp+60h+arg_8]
0x140023afc  add     rsp, 60h
0x140023b00  pop     rdi
0x140023b01  pop     rsi
0x140023b02  pop     rbp
0x140023b03  retn
```
