# ??$call@AEAV_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@@?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@@Z

- ea: `0x1400237c4`
- end: `0x1400238d5`
- name: `??$call@AEAV_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@@?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@@Z`
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
- `0x1400237c4`
- `0x140024070`
- `0x14002434c`
- `0x140029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>::call<_lambda_3207e8c3a392af88c709c9f0a8afe0f7_ &>(
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
  v7[0] = L"Windows.UI.Xaml.Hosting.XamlSourceFocusNavigationRequest";
  v7[1] = 56;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v10);
    v10 = &qword_1400470D8;
    _InterlockedIncrement64(&qword_1400470D8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1400470E0);
    }
    _lambda_3207e8c3a392af88c709c9f0a8afe0f7_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>);
    _InterlockedDecrement64(&qword_1400470D8);
  }
  else
  {
    _lambda_3207e8c3a392af88c709c9f0a8afe0f7_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x1400237c4  mov     [rsp-18h+arg_8], rbx
0x1400237c9  mov     [rsp-18h+arg_0], rcx
0x1400237ce  push    rbp
0x1400237cf  push    rsi
0x1400237d0  push    rdi
0x1400237d1  mov     rbp, rsp
0x1400237d4  sub     rsp, 60h
0x1400237d8  mov     rsi, r8
0x1400237db  mov     rbx, rdx
0x1400237de  lea     rax, aWindowsUiXamlH; "Windows.UI.Xaml.Hosting.XamlSourceFocus"...
0x1400237e5  mov     [rbp+var_38], rax
0x1400237e9  mov     [rbp+var_30], 38h ; '8'
0x1400237f1  lea     rdx, [rbp+var_38]
0x1400237f5  lea     rcx, [rbp+var_28]
0x1400237f9  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x1400237fe  lea     rdx, [rbp+var_28]
0x140023802  lea     rcx, [rbp+arg_0]
0x140023806  call    ??$get_activation_factory@UIXamlSourceFocusNavigationRequestFactory@Hosting@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIXamlSourceFocusNavigationRequestFactory@Hosting@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>(winrt::param::hstring const &)
0x14002380b  nop
0x14002380c  mov     rdi, [rbp+arg_0]
0x140023810  test    rdi, rdi
0x140023813  jz      loc_1400238A8
0x140023819  mov     [rbp+arg_18], 0
0x140023821  mov     rax, [rdi]
0x140023824  lea     r8, [rbp+arg_18]
0x140023828  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14002382f  mov     rcx, rdi
0x140023832  mov     rax, [rax]
0x140023835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002383a  mov     rax, [rbp+arg_18]
0x14002383e  mov     [rbp+arg_18], rax
0x140023842  test    rax, rax
0x140023845  jz      short loc_1400238A8
0x140023847  lea     rcx, [rbp+arg_18]
0x14002384b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140023850  lea     rax, qword_1400470D8
0x140023857  mov     [rbp+arg_18], rax
0x14002385b  lock inc cs:qword_1400470D8
0x140023863  xor     eax, eax
0x140023865  lock cmpxchg cs:??$factory_cache_entry_v@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>
0x14002386e  jnz     short loc_14002388B
0x140023870  mov     [rbp+arg_0], 0
0x140023878  lea     rdx, stru_1400470E0; ListEntry
0x14002387f  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140023886  call    WINRT_IMPL_InterlockedPushEntrySList
0x14002388b  lea     r8, ??$factory_cache_entry_v@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@UIXamlSourceFocusNavigationRequestFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest,winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory>
0x140023892  mov     rdx, rbx
0x140023895  mov     rcx, rsi
0x140023898  call    ??R_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@QEBA@AEBUIXamlSourceFocusNavigationRequestFactory@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_3207e8c3a392af88c709c9f0a8afe0f7_::operator()(winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory const &)
0x14002389d  nop
0x14002389e  lock dec cs:qword_1400470D8
0x1400238a6  jmp     short loc_1400238B8
0x1400238a8  lea     r8, [rbp+arg_0]
0x1400238ac  mov     rdx, rbx
0x1400238af  mov     rcx, rsi
0x1400238b2  call    ??R_lambda_3207e8c3a392af88c709c9f0a8afe0f7_@@QEBA@AEBUIXamlSourceFocusNavigationRequestFactory@Hosting@Xaml@UI@Windows@winrt@@@Z; _lambda_3207e8c3a392af88c709c9f0a8afe0f7_::operator()(winrt::Windows::UI::Xaml::Hosting::IXamlSourceFocusNavigationRequestFactory const &)
0x1400238b7  nop
0x1400238b8  lea     rcx, [rbp+arg_0]
0x1400238bc  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400238c1  mov     rax, rbx
0x1400238c4  mov     rbx, [rsp+60h+arg_8]
0x1400238cc  add     rsp, 60h
0x1400238d0  pop     rdi
0x1400238d1  pop     rsi
0x1400238d2  pop     rbp
0x1400238d3  retn
```
