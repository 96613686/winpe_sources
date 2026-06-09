# ??$call@AEAV_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@@Z

- ea: `0x14004f5cc`
- end: `0x14004f6dc`
- name: `??$call@AEAV_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14005add4`

## callees

- `0x140044a2a`
- `0x14004f5cc`
- `0x14004fd38`
- `0x140052954`
- `0x140052bf8`
- `0x1400544d0`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_ee1a3feb73dd4935dd100918ed2c0202_ &>(
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
  v7[0] = L"Windows.Foundation.PropertyValue";
  v7[1] = 32;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v10);
    v10 = &qword_140083958;
    _InterlockedIncrement64(&qword_140083958);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140083960);
    }
    _lambda_ee1a3feb73dd4935dd100918ed2c0202_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _lambda_ee1a3feb73dd4935dd100918ed2c0202_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  return a2;
}

```

## disassembly

```asm
0x14004f5cc  mov     [rsp-18h+arg_8], rbx
0x14004f5d1  mov     [rsp-18h+arg_0], rcx
0x14004f5d6  push    rbp
0x14004f5d7  push    rsi
0x14004f5d8  push    rdi
0x14004f5d9  mov     rbp, rsp
0x14004f5dc  sub     rsp, 60h
0x14004f5e0  mov     rsi, r8
0x14004f5e3  mov     rbx, rdx
0x14004f5e6  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x14004f5ed  mov     [rbp+var_38], rax
0x14004f5f1  mov     [rbp+var_30], 20h ; ' '
0x14004f5f9  lea     rdx, [rbp+var_38]
0x14004f5fd  lea     rcx, [rbp+var_28]
0x14004f601  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f606  lea     rdx, [rbp+var_28]
0x14004f60a  lea     rcx, [rbp+arg_0]
0x14004f60e  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x14004f613  nop
0x14004f614  mov     rdi, [rbp+arg_0]
0x14004f618  test    rdi, rdi
0x14004f61b  jz      loc_14004F6B0
0x14004f621  mov     [rbp+arg_18], 0
0x14004f629  mov     rax, [rdi]
0x14004f62c  lea     r8, [rbp+arg_18]
0x14004f630  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f637  mov     rcx, rdi
0x14004f63a  mov     rax, [rax]
0x14004f63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f642  mov     rax, [rbp+arg_18]
0x14004f646  mov     [rbp+arg_18], rax
0x14004f64a  test    rax, rax
0x14004f64d  jz      short loc_14004F6B0
0x14004f64f  lea     rcx, [rbp+arg_18]
0x14004f653  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f658  lea     rax, qword_140083958
0x14004f65f  mov     [rbp+arg_18], rax
0x14004f663  lock inc cs:qword_140083958
0x14004f66b  xor     eax, eax
0x14004f66d  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f676  jnz     short loc_14004F693
0x14004f678  mov     [rbp+arg_0], 0
0x14004f680  lea     rdx, stru_140083960; ListEntry
0x14004f687  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f68e  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f693  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f69a  mov     rdx, rbx
0x14004f69d  mov     rcx, rsi
0x14004f6a0  call    ??R_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_ee1a3feb73dd4935dd100918ed2c0202_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f6a5  nop
0x14004f6a6  lock dec cs:qword_140083958
0x14004f6ae  jmp     short loc_14004F6C0
0x14004f6b0  lea     r8, [rbp+arg_0]
0x14004f6b4  mov     rdx, rbx
0x14004f6b7  mov     rcx, rsi
0x14004f6ba  call    ??R_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_ee1a3feb73dd4935dd100918ed2c0202_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f6bf  nop
0x14004f6c0  lea     rcx, [rbp+arg_0]; this
0x14004f6c4  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f6c9  mov     rax, rbx
0x14004f6cc  mov     rbx, [rsp+60h+arg_8]
0x14004f6d4  add     rsp, 60h
0x14004f6d8  pop     rdi
0x14004f6d9  pop     rsi
0x14004f6da  pop     rbp
0x14004f6db  retn
```
