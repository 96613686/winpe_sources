# ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z

- ea: `0x14004ec70`
- end: `0x14004edb5`
- name: `??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140057574`

## callees

- `0x140044a2a`
- `0x14004ec70`
- `0x140050184`
- `0x140052954`
- `0x140052bf8`
- `0x140053ac4`
- `0x14005d654`
- `0x14005fcbc`
- `0x140067010`

## string_xrefs

- `0x14004ec8a`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  const wchar_t *v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _QWORD v9[4]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = a1;
  v7 = L"Windows.Foundation.Uri";
  *(_QWORD *)&v8 = 22;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>,
    (__int64)&v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v5 = v11;
  v10 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v11);
    v11 = &qword_140083978;
    _InterlockedIncrement64(&qword_140083978);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>);
    _InterlockedDecrement64(&qword_140083978);
  }
  else
  {
    _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v10);
  return a2;
}

```

## disassembly

```asm
0x14004ec70  mov     [rsp-18h+arg_8], rbx
0x14004ec75  mov     [rsp-18h+arg_0], rcx
0x14004ec7a  push    rbp
0x14004ec7b  push    rsi
0x14004ec7c  push    rdi
0x14004ec7d  mov     rbp, rsp
0x14004ec80  sub     rsp, 60h
0x14004ec84  mov     rsi, r8
0x14004ec87  mov     rbx, rdx
0x14004ec8a  lea     rax, aWindowsFoundat_0; "Windows.Foundation.Uri"
0x14004ec91  mov     [rbp+var_38], rax
0x14004ec95  mov     qword ptr [rbp+var_30], 16h
0x14004ec9d  lea     rdx, [rbp+var_38]
0x14004eca1  lea     rcx, [rbp+var_20]
0x14004eca5  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004ecaa  mov     [rbp+arg_18], 0
0x14004ecb2  mov     dword ptr [rbp+var_38], 0
0x14004ecb9  xorps   xmm0, xmm0
0x14004ecbc  movdqu  [rbp+var_30], xmm0
0x14004ecc1  lea     r9, [rbp+arg_18]
0x14004ecc5  lea     r8, ??$guid_v@UIUriRuntimeClassFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x14004eccc  lea     rdx, [rbp+var_20]
0x14004ecd0  lea     rcx, [rbp+arg_0]
0x14004ecd4  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x14004ecd9  lea     r8, [rbp+var_38]
0x14004ecdd  mov     edx, dword ptr [rbp+arg_0]
0x14004ece0  lea     rcx, [rbp+arg_0]
0x14004ece4  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14004ece9  mov     rdi, [rbp+arg_18]
0x14004eced  mov     [rbp+arg_0], rdi
0x14004ecf1  test    rdi, rdi
0x14004ecf4  jz      loc_14004ED89
0x14004ecfa  mov     [rbp+arg_18], 0
0x14004ed02  mov     rax, [rdi]
0x14004ed05  lea     r8, [rbp+arg_18]
0x14004ed09  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004ed10  mov     rcx, rdi
0x14004ed13  mov     rax, [rax]
0x14004ed16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ed1b  mov     rax, [rbp+arg_18]
0x14004ed1f  mov     [rbp+arg_18], rax
0x14004ed23  test    rax, rax
0x14004ed26  jz      short loc_14004ED89
0x14004ed28  lea     rcx, [rbp+arg_18]
0x14004ed2c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004ed31  lea     rax, qword_140083978
0x14004ed38  mov     [rbp+arg_18], rax
0x14004ed3c  lock inc cs:qword_140083978
0x14004ed44  xor     eax, eax
0x14004ed46  lock cmpxchg cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, rdi; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x14004ed4f  jnz     short loc_14004ED6C
0x14004ed51  mov     [rbp+arg_0], 0
0x14004ed59  lea     rdx, ListEntry; ListEntry
0x14004ed60  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004ed67  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004ed6c  lea     r8, ??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x14004ed73  mov     rdx, rbx
0x14004ed76  mov     rcx, rsi
0x14004ed79  call    ??R_lambda_0a61d549bec6c444b35123f4c9509ca7_@@QEBA@AEBUIUriRuntimeClassFactory@Foundation@Windows@winrt@@@Z; _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(winrt::Windows::Foundation::IUriRuntimeClassFactory const &)
0x14004ed7e  nop
0x14004ed7f  lock dec cs:qword_140083978
0x14004ed87  jmp     short loc_14004ED99
0x14004ed89  lea     r8, [rbp+arg_0]
0x14004ed8d  mov     rdx, rbx
0x14004ed90  mov     rcx, rsi
0x14004ed93  call    ??R_lambda_0a61d549bec6c444b35123f4c9509ca7_@@QEBA@AEBUIUriRuntimeClassFactory@Foundation@Windows@winrt@@@Z; _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(winrt::Windows::Foundation::IUriRuntimeClassFactory const &)
0x14004ed98  nop
0x14004ed99  lea     rcx, [rbp+arg_0]; this
0x14004ed9d  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004eda2  mov     rax, rbx
0x14004eda5  mov     rbx, [rsp+60h+arg_8]
0x14004edad  add     rsp, 60h
0x14004edb1  pop     rdi
0x14004edb2  pop     rsi
0x14004edb3  pop     rbp
0x14004edb4  retn
```
