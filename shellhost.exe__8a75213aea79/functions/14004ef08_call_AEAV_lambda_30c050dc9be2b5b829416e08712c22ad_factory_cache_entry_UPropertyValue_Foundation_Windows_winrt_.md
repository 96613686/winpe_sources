# ??$call@AEAV_lambda_30c050dc9be2b5b829416e08712c22ad_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_30c050dc9be2b5b829416e08712c22ad_@@@Z

- ea: `0x14004ef08`
- end: `0x14004f018`
- name: `??$call@AEAV_lambda_30c050dc9be2b5b829416e08712c22ad_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_30c050dc9be2b5b829416e08712c22ad_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14004ebf4`

## callees

- `0x140044a2a`
- `0x14004ef08`
- `0x14004fd38`
- `0x140052954`
- `0x140052bf8`
- `0x140053c44`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_30c050dc9be2b5b829416e08712c22ad_ &>(
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
    _lambda_30c050dc9be2b5b829416e08712c22ad_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _lambda_30c050dc9be2b5b829416e08712c22ad_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  return a2;
}

```

## disassembly

```asm
0x14004ef08  mov     [rsp-18h+arg_8], rbx
0x14004ef0d  mov     [rsp-18h+arg_0], rcx
0x14004ef12  push    rbp
0x14004ef13  push    rsi
0x14004ef14  push    rdi
0x14004ef15  mov     rbp, rsp
0x14004ef18  sub     rsp, 60h
0x14004ef1c  mov     rsi, r8
0x14004ef1f  mov     rbx, rdx
0x14004ef22  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x14004ef29  mov     [rbp+var_38], rax
0x14004ef2d  mov     [rbp+var_30], 20h ; ' '
0x14004ef35  lea     rdx, [rbp+var_38]
0x14004ef39  lea     rcx, [rbp+var_28]
0x14004ef3d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004ef42  lea     rdx, [rbp+var_28]
0x14004ef46  lea     rcx, [rbp+arg_0]
0x14004ef4a  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x14004ef4f  nop
0x14004ef50  mov     rdi, [rbp+arg_0]
0x14004ef54  test    rdi, rdi
0x14004ef57  jz      loc_14004EFEC
0x14004ef5d  mov     [rbp+arg_18], 0
0x14004ef65  mov     rax, [rdi]
0x14004ef68  lea     r8, [rbp+arg_18]
0x14004ef6c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004ef73  mov     rcx, rdi
0x14004ef76  mov     rax, [rax]
0x14004ef79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ef7e  mov     rax, [rbp+arg_18]
0x14004ef82  mov     [rbp+arg_18], rax
0x14004ef86  test    rax, rax
0x14004ef89  jz      short loc_14004EFEC
0x14004ef8b  lea     rcx, [rbp+arg_18]
0x14004ef8f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004ef94  lea     rax, qword_140083958
0x14004ef9b  mov     [rbp+arg_18], rax
0x14004ef9f  lock inc cs:qword_140083958
0x14004efa7  xor     eax, eax
0x14004efa9  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004efb2  jnz     short loc_14004EFCF
0x14004efb4  mov     [rbp+arg_0], 0
0x14004efbc  lea     rdx, stru_140083960; ListEntry
0x14004efc3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004efca  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004efcf  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004efd6  mov     rdx, rbx
0x14004efd9  mov     rcx, rsi
0x14004efdc  call    ??R_lambda_30c050dc9be2b5b829416e08712c22ad_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_30c050dc9be2b5b829416e08712c22ad_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004efe1  nop
0x14004efe2  lock dec cs:qword_140083958
0x14004efea  jmp     short loc_14004EFFC
0x14004efec  lea     r8, [rbp+arg_0]
0x14004eff0  mov     rdx, rbx
0x14004eff3  mov     rcx, rsi
0x14004eff6  call    ??R_lambda_30c050dc9be2b5b829416e08712c22ad_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_30c050dc9be2b5b829416e08712c22ad_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004effb  nop
0x14004effc  lea     rcx, [rbp+arg_0]; this
0x14004f000  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f005  mov     rax, rbx
0x14004f008  mov     rbx, [rsp+60h+arg_8]
0x14004f010  add     rsp, 60h
0x14004f014  pop     rdi
0x14004f015  pop     rsi
0x14004f016  pop     rbp
0x14004f017  retn
```
