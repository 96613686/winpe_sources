# ??$call@AEAV_lambda_df12a01b87dd988dada7818cd16bb49c_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_df12a01b87dd988dada7818cd16bb49c_@@@Z

- ea: `0x14004f4b4`
- end: `0x14004f5c4`
- name: `??$call@AEAV_lambda_df12a01b87dd988dada7818cd16bb49c_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_df12a01b87dd988dada7818cd16bb49c_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140057e34`

## callees

- `0x140044a2a`
- `0x14004f4b4`
- `0x14004fd38`
- `0x140052954`
- `0x140052bf8`
- `0x140054468`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_df12a01b87dd988dada7818cd16bb49c_ &>(
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
    _lambda_df12a01b87dd988dada7818cd16bb49c_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _lambda_df12a01b87dd988dada7818cd16bb49c_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  return a2;
}

```

## disassembly

```asm
0x14004f4b4  mov     [rsp-18h+arg_8], rbx
0x14004f4b9  mov     [rsp-18h+arg_0], rcx
0x14004f4be  push    rbp
0x14004f4bf  push    rsi
0x14004f4c0  push    rdi
0x14004f4c1  mov     rbp, rsp
0x14004f4c4  sub     rsp, 60h
0x14004f4c8  mov     rsi, r8
0x14004f4cb  mov     rbx, rdx
0x14004f4ce  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x14004f4d5  mov     [rbp+var_38], rax
0x14004f4d9  mov     [rbp+var_30], 20h ; ' '
0x14004f4e1  lea     rdx, [rbp+var_38]
0x14004f4e5  lea     rcx, [rbp+var_28]
0x14004f4e9  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f4ee  lea     rdx, [rbp+var_28]
0x14004f4f2  lea     rcx, [rbp+arg_0]
0x14004f4f6  call    ??$get_activation_factory@UIPropertyValueStatics@Foundation@Windows@winrt@@@winrt@@YA?AUIPropertyValueStatics@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IPropertyValueStatics>(winrt::param::hstring const &)
0x14004f4fb  nop
0x14004f4fc  mov     rdi, [rbp+arg_0]
0x14004f500  test    rdi, rdi
0x14004f503  jz      loc_14004F598
0x14004f509  mov     [rbp+arg_18], 0
0x14004f511  mov     rax, [rdi]
0x14004f514  lea     r8, [rbp+arg_18]
0x14004f518  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f51f  mov     rcx, rdi
0x14004f522  mov     rax, [rax]
0x14004f525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f52a  mov     rax, [rbp+arg_18]
0x14004f52e  mov     [rbp+arg_18], rax
0x14004f532  test    rax, rax
0x14004f535  jz      short loc_14004F598
0x14004f537  lea     rcx, [rbp+arg_18]
0x14004f53b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f540  lea     rax, qword_140083958
0x14004f547  mov     [rbp+arg_18], rax
0x14004f54b  lock inc cs:qword_140083958
0x14004f553  xor     eax, eax
0x14004f555  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f55e  jnz     short loc_14004F57B
0x14004f560  mov     [rbp+arg_0], 0
0x14004f568  lea     rdx, stru_140083960; ListEntry
0x14004f56f  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f576  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f57b  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14004f582  mov     rdx, rbx
0x14004f585  mov     rcx, rsi
0x14004f588  call    ??R_lambda_df12a01b87dd988dada7818cd16bb49c_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_df12a01b87dd988dada7818cd16bb49c_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f58d  nop
0x14004f58e  lock dec cs:qword_140083958
0x14004f596  jmp     short loc_14004F5A8
0x14004f598  lea     r8, [rbp+arg_0]
0x14004f59c  mov     rdx, rbx
0x14004f59f  mov     rcx, rsi
0x14004f5a2  call    ??R_lambda_df12a01b87dd988dada7818cd16bb49c_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_df12a01b87dd988dada7818cd16bb49c_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14004f5a7  nop
0x14004f5a8  lea     rcx, [rbp+arg_0]; this
0x14004f5ac  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f5b1  mov     rax, rbx
0x14004f5b4  mov     rbx, [rsp+60h+arg_8]
0x14004f5bc  add     rsp, 60h
0x14004f5c0  pop     rdi
0x14004f5c1  pop     rsi
0x14004f5c2  pop     rbp
0x14004f5c3  retn
```
