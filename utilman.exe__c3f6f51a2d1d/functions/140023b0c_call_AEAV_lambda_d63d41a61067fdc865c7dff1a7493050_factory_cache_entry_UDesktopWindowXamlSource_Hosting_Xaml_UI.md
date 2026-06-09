# ??$call@AEAV_lambda_d63d41a61067fdc865c7dff1a7493050_@@@?$factory_cache_entry@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@UIDesktopWindowXamlSourceFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_d63d41a61067fdc865c7dff1a7493050_@@@Z

- ea: `0x140023b0c`
- end: `0x140023c1d`
- name: `??$call@AEAV_lambda_d63d41a61067fdc865c7dff1a7493050_@@@?$factory_cache_entry@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@UIDesktopWindowXamlSourceFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_d63d41a61067fdc865c7dff1a7493050_@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140024118`

## callees

- `0x140003539`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14001f304`
- `0x140023b0c`
- `0x140023ee0`
- `0x1400243c8`
- `0x140029010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>::call<_lambda_d63d41a61067fdc865c7dff1a7493050_ &>(
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
  v7[0] = L"Windows.UI.Xaml.Hosting.DesktopWindowXamlSource";
  v7[1] = 47;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v10);
    v10 = &qword_1400470B8;
    _InterlockedIncrement64(&qword_1400470B8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1400470C0);
    }
    _lambda_d63d41a61067fdc865c7dff1a7493050_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>);
    _InterlockedDecrement64(&qword_1400470B8);
  }
  else
  {
    _lambda_d63d41a61067fdc865c7dff1a7493050_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x140023b0c  mov     [rsp-18h+arg_8], rbx
0x140023b11  mov     [rsp-18h+arg_0], rcx
0x140023b16  push    rbp
0x140023b17  push    rsi
0x140023b18  push    rdi
0x140023b19  mov     rbp, rsp
0x140023b1c  sub     rsp, 60h
0x140023b20  mov     rsi, r8
0x140023b23  mov     rbx, rdx
0x140023b26  lea     rax, aWindowsUiXamlH_0; "Windows.UI.Xaml.Hosting.DesktopWindowXa"...
0x140023b2d  mov     [rbp+var_38], rax
0x140023b31  mov     [rbp+var_30], 2Fh ; '/'
0x140023b39  lea     rdx, [rbp+var_38]
0x140023b3d  lea     rcx, [rbp+var_28]
0x140023b41  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x140023b46  lea     rdx, [rbp+var_28]
0x140023b4a  lea     rcx, [rbp+arg_0]
0x140023b4e  call    ??$get_activation_factory@UIDesktopWindowXamlSourceFactory@Hosting@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIDesktopWindowXamlSourceFactory@Hosting@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>(winrt::param::hstring const &)
0x140023b53  nop
0x140023b54  mov     rdi, [rbp+arg_0]
0x140023b58  test    rdi, rdi
0x140023b5b  jz      loc_140023BF0
0x140023b61  mov     [rbp+arg_18], 0
0x140023b69  mov     rax, [rdi]
0x140023b6c  lea     r8, [rbp+arg_18]
0x140023b70  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140023b77  mov     rcx, rdi
0x140023b7a  mov     rax, [rax]
0x140023b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023b82  mov     rax, [rbp+arg_18]
0x140023b86  mov     [rbp+arg_18], rax
0x140023b8a  test    rax, rax
0x140023b8d  jz      short loc_140023BF0
0x140023b8f  lea     rcx, [rbp+arg_18]
0x140023b93  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140023b98  lea     rax, qword_1400470B8
0x140023b9f  mov     [rbp+arg_18], rax
0x140023ba3  lock inc cs:qword_1400470B8
0x140023bab  xor     eax, eax
0x140023bad  lock cmpxchg cs:??$factory_cache_entry_v@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@UIDesktopWindowXamlSourceFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@UIDesktopWindowXamlSourceFactory@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>
0x140023bb6  jnz     short loc_140023BD3
0x140023bb8  mov     [rbp+arg_0], 0
0x140023bc0  lea     rdx, stru_1400470C0; ListEntry
0x140023bc7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140023bce  call    WINRT_IMPL_InterlockedPushEntrySList
0x140023bd3  lea     r8, ??$factory_cache_entry_v@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@UIDesktopWindowXamlSourceFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@UIDesktopWindowXamlSourceFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::DesktopWindowXamlSource,winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory>
0x140023bda  mov     rdx, rbx
0x140023bdd  mov     rcx, rsi
0x140023be0  call    ??R_lambda_d63d41a61067fdc865c7dff1a7493050_@@QEBA@AEBUIDesktopWindowXamlSourceFactory@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_d63d41a61067fdc865c7dff1a7493050_::operator()(winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory const &)
0x140023be5  nop
0x140023be6  lock dec cs:qword_1400470B8
0x140023bee  jmp     short loc_140023C00
0x140023bf0  lea     r8, [rbp+arg_0]
0x140023bf4  mov     rdx, rbx
0x140023bf7  mov     rcx, rsi
0x140023bfa  call    ??R_lambda_d63d41a61067fdc865c7dff1a7493050_@@QEBA@AEBUIDesktopWindowXamlSourceFactory@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_d63d41a61067fdc865c7dff1a7493050_::operator()(winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSourceFactory const &)
0x140023bff  nop
0x140023c00  lea     rcx, [rbp+arg_0]
0x140023c04  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140023c09  mov     rax, rbx
0x140023c0c  mov     rbx, [rsp+60h+arg_8]
0x140023c14  add     rsp, 60h
0x140023c18  pop     rdi
0x140023c19  pop     rsi
0x140023c1a  pop     rbp
0x140023c1b  retn
```
