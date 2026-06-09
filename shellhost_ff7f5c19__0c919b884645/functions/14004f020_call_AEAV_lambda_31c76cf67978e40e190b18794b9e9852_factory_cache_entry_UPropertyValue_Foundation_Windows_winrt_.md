# ??$call@AEAV_lambda_31c76cf67978e40e190b18794b9e9852_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_31c76cf67978e40e190b18794b9e9852_@@@Z

- ea: `0x14004f020`
- end: `0x14004f130`
- name: `??$call@AEAV_lambda_31c76cf67978e40e190b18794b9e9852_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_31c76cf67978e40e190b18794b9e9852_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140053fcc`

## callees

- `0x140044a2a`
- `0x14004f020`
- `0x14004fd38`
- `0x140052954`
- `0x140052bf8`
- `0x140053ce8`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_31c76cf67978e40e190b18794b9e9852_ &>(
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
    _lambda_31c76cf67978e40e190b18794b9e9852_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _lambda_31c76cf67978e40e190b18794b9e9852_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  return a2;
}

```

## disassembly

```asm
0x14004f020  mov     [rsp-18h+arg_8], rbx
0x14004f025  mov     [rsp-18h+arg_0], rcx
0x14004f02a  push    rbp
0x14004f02b  push    rsi
0x14004f02c  push    rdi
0x14004f02d  mov     rbp, rsp
0x14004f030  sub     rsp, 60h
0x14004f034  mov     rsi, r8
0x14004f037  mov     rbx, rdx
0x14004f03a  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x14004f041  mov     [rbp+var_38], rax
0x14004f045  mov     [rbp+var_30], 20h ; ' '
0x14004f04d  lea     rdx, [rbp+var_38]
0x14004f051  lea     rcx, [rbp+var_28]
0x14004f055  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f05a  lea     rdx, [rbp+var_28]
0x14004f05e  lea     rcx, [rbp+arg_0]
0x14004f062  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x14004f067  nop
0x14004f068  mov     rdi, [rbp+arg_0]
0x14004f06c  test    rdi, rdi
0x14004f06f  jz      loc_14004F104
0x14004f075  mov     [rbp+arg_18], 0
0x14004f07d  mov     rax, [rdi]
0x14004f080  lea     r8, [rbp+arg_18]
0x14004f084  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f08b  mov     rcx, rdi
0x14004f08e  mov     rax, [rax]
0x14004f091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f096  mov     rax, [rbp+arg_18]
0x14004f09a  mov     [rbp+arg_18], rax
0x14004f09e  test    rax, rax
0x14004f0a1  jz      short loc_14004F104
0x14004f0a3  lea     rcx, [rbp+arg_18]
0x14004f0a7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f0ac  lea     rax, qword_140083958
0x14004f0b3  mov     [rbp+arg_18], rax
0x14004f0b7  lock inc cs:qword_140083958
0x14004f0bf  xor     eax, eax
0x14004f0c1  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f0ca  jnz     short loc_14004F0E7
0x14004f0cc  mov     [rbp+arg_0], 0
0x14004f0d4  lea     rdx, stru_140083960; ListEntry
0x14004f0db  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f0e2  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f0e7  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f0ee  mov     rdx, rbx
0x14004f0f1  mov     rcx, rsi
0x14004f0f4  call    ??R_lambda_31c76cf67978e40e190b18794b9e9852_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_31c76cf67978e40e190b18794b9e9852_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f0f9  nop
0x14004f0fa  lock dec cs:qword_140083958
0x14004f102  jmp     short loc_14004F114
0x14004f104  lea     r8, [rbp+arg_0]
0x14004f108  mov     rdx, rbx
0x14004f10b  mov     rcx, rsi
0x14004f10e  call    ??R_lambda_31c76cf67978e40e190b18794b9e9852_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_31c76cf67978e40e190b18794b9e9852_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f113  nop
0x14004f114  lea     rcx, [rbp+arg_0]; this
0x14004f118  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f11d  mov     rax, rbx
0x14004f120  mov     rbx, [rsp+60h+arg_8]
0x14004f128  add     rsp, 60h
0x14004f12c  pop     rdi
0x14004f12d  pop     rsi
0x14004f12e  pop     rbp
0x14004f12f  retn
```
