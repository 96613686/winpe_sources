# ??$call@P6A?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUIActivationFactory@345@@Z@?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUValueSet@Collections@Foundation@Windows@2@AEBUIActivationFactory@562@@Z@Z

- ea: `0x14004f800`
- end: `0x14004f916`
- name: `??$call@P6A?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUIActivationFactory@345@@Z@?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUValueSet@Collections@Foundation@Windows@2@AEBUIActivationFactory@562@@Z@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140052594`

## callees

- `0x140044a2a`
- `0x14004f800`
- `0x14004fc78`
- `0x140052954`
- `0x140052bf8`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Foundation::Collections::ValueSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.Foundation.Collections.ValueSet";
  v6[1] = 39;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_140083998;
    _InterlockedIncrement64(&qword_140083998);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1400839A0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_140083998);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v8);
  return a2;
}

```

## disassembly

```asm
0x14004f800  mov     [rsp-8+arg_8], rbx
0x14004f805  mov     [rsp-8+arg_10], rdi
0x14004f80a  mov     [rsp-8+arg_0], rcx
0x14004f80f  push    rbp
0x14004f810  mov     rbp, rsp
0x14004f813  sub     rsp, 60h
0x14004f817  mov     rdi, r8
0x14004f81a  mov     rbx, rdx
0x14004f81d  lea     rax, aWindowsFoundat_1; "Windows.Foundation.Collections.ValueSet"
0x14004f824  mov     [rbp+var_38], rax
0x14004f828  mov     [rbp+var_30], 27h ; '''
0x14004f830  lea     rdx, [rbp+var_38]
0x14004f834  lea     rcx, [rbp+var_28]
0x14004f838  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f83d  lea     rdx, [rbp+var_28]
0x14004f841  lea     rcx, [rbp+arg_0]
0x14004f845  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x14004f84a  nop
0x14004f84b  mov     rcx, [rbp+arg_0]
0x14004f84f  test    rcx, rcx
0x14004f852  jz      loc_14004F8E8
0x14004f858  mov     [rbp+arg_18], 0
0x14004f860  mov     rax, [rcx]
0x14004f863  lea     r8, [rbp+arg_18]
0x14004f867  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f86e  mov     rax, [rax]
0x14004f871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f876  mov     rax, [rbp+arg_18]
0x14004f87a  mov     [rbp+arg_18], rax
0x14004f87e  test    rax, rax
0x14004f881  jz      short loc_14004F8E8
0x14004f883  lea     rcx, [rbp+arg_18]
0x14004f887  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f88c  lea     rax, qword_140083998
0x14004f893  mov     [rbp+arg_18], rax
0x14004f897  lock inc cs:qword_140083998
0x14004f89f  mov     rcx, [rbp+arg_0]
0x14004f8a3  xor     eax, eax
0x14004f8a5  lock cmpxchg cs:??$factory_cache_entry_v@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@3U?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@12@A, rcx; factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>
0x14004f8ae  jnz     short loc_14004F8CB
0x14004f8b0  mov     [rbp+arg_0], 0
0x14004f8b8  lea     rdx, stru_1400839A0; ListEntry
0x14004f8bf  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f8c6  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f8cb  lea     rdx, ??$factory_cache_entry_v@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@impl@winrt@@3U?$factory_cache_entry@UValueSet@Collections@Foundation@Windows@winrt@@UIActivationFactory@345@@12@A; factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::IActivationFactory>
0x14004f8d2  mov     rcx, rbx
0x14004f8d5  mov     rax, [rdi]
0x14004f8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f8dd  nop
0x14004f8de  lock dec cs:qword_140083998
0x14004f8e6  jmp     short loc_14004F8F8
0x14004f8e8  lea     rdx, [rbp+arg_0]
0x14004f8ec  mov     rcx, rbx
0x14004f8ef  mov     rax, [rdi]
0x14004f8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f8f7  nop
0x14004f8f8  lea     rcx, [rbp+arg_0]; this
0x14004f8fc  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f901  mov     rax, rbx
0x14004f904  lea     r11, [rsp+60h+var_s0]
0x14004f909  mov     rbx, [r11+18h]
0x14004f90d  mov     rdi, [r11+20h]
0x14004f911  mov     rsp, r11
0x14004f914  pop     rbp
0x14004f915  retn
```
