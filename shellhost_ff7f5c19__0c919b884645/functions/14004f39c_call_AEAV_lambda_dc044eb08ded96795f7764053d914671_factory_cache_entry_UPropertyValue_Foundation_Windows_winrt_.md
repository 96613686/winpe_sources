# ??$call@AEAV_lambda_dc044eb08ded96795f7764053d914671_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_dc044eb08ded96795f7764053d914671_@@@Z

- ea: `0x14004f39c`
- end: `0x14004f4ac`
- name: `??$call@AEAV_lambda_dc044eb08ded96795f7764053d914671_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_dc044eb08ded96795f7764053d914671_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140051ea0`

## callees

- `0x140044a2a`
- `0x14004f39c`
- `0x14004fd38`
- `0x140052954`
- `0x140052bf8`
- `0x1400543fc`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_dc044eb08ded96795f7764053d914671_ &>(
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
    _lambda_dc044eb08ded96795f7764053d914671_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _lambda_dc044eb08ded96795f7764053d914671_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  return a2;
}

```

## disassembly

```asm
0x14004f39c  mov     [rsp-18h+arg_8], rbx
0x14004f3a1  mov     [rsp-18h+arg_0], rcx
0x14004f3a6  push    rbp
0x14004f3a7  push    rsi
0x14004f3a8  push    rdi
0x14004f3a9  mov     rbp, rsp
0x14004f3ac  sub     rsp, 60h
0x14004f3b0  mov     rsi, r8
0x14004f3b3  mov     rbx, rdx
0x14004f3b6  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x14004f3bd  mov     [rbp+var_38], rax
0x14004f3c1  mov     [rbp+var_30], 20h ; ' '
0x14004f3c9  lea     rdx, [rbp+var_38]
0x14004f3cd  lea     rcx, [rbp+var_28]
0x14004f3d1  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f3d6  lea     rdx, [rbp+var_28]
0x14004f3da  lea     rcx, [rbp+arg_0]
0x14004f3de  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x14004f3e3  nop
0x14004f3e4  mov     rdi, [rbp+arg_0]
0x14004f3e8  test    rdi, rdi
0x14004f3eb  jz      loc_14004F480
0x14004f3f1  mov     [rbp+arg_18], 0
0x14004f3f9  mov     rax, [rdi]
0x14004f3fc  lea     r8, [rbp+arg_18]
0x14004f400  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f407  mov     rcx, rdi
0x14004f40a  mov     rax, [rax]
0x14004f40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f412  mov     rax, [rbp+arg_18]
0x14004f416  mov     [rbp+arg_18], rax
0x14004f41a  test    rax, rax
0x14004f41d  jz      short loc_14004F480
0x14004f41f  lea     rcx, [rbp+arg_18]
0x14004f423  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f428  lea     rax, qword_140083958
0x14004f42f  mov     [rbp+arg_18], rax
0x14004f433  lock inc cs:qword_140083958
0x14004f43b  xor     eax, eax
0x14004f43d  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f446  jnz     short loc_14004F463
0x14004f448  mov     [rbp+arg_0], 0
0x14004f450  lea     rdx, stru_140083960; ListEntry
0x14004f457  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f45e  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f463  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f46a  mov     rdx, rbx
0x14004f46d  mov     rcx, rsi
0x14004f470  call    ??R_lambda_dc044eb08ded96795f7764053d914671_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_dc044eb08ded96795f7764053d914671_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f475  nop
0x14004f476  lock dec cs:qword_140083958
0x14004f47e  jmp     short loc_14004F490
0x14004f480  lea     r8, [rbp+arg_0]
0x14004f484  mov     rdx, rbx
0x14004f487  mov     rcx, rsi
0x14004f48a  call    ??R_lambda_dc044eb08ded96795f7764053d914671_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_dc044eb08ded96795f7764053d914671_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f48f  nop
0x14004f490  lea     rcx, [rbp+arg_0]; this
0x14004f494  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f499  mov     rax, rbx
0x14004f49c  mov     rbx, [rsp+60h+arg_8]
0x14004f4a4  add     rsp, 60h
0x14004f4a8  pop     rdi
0x14004f4a9  pop     rsi
0x14004f4aa  pop     rbp
0x14004f4ab  retn
```
