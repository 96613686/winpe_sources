# ??$call@AEAV_lambda_12918d939973c46c384f4162aa40ffe3_@@@?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_12918d939973c46c384f4162aa40ffe3_@@@Z

- ea: `0x14004edbc`
- end: `0x14004ef01`
- name: `??$call@AEAV_lambda_12918d939973c46c384f4162aa40ffe3_@@@?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_12918d939973c46c384f4162aa40ffe3_@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400550d0`

## callees

- `0x140044a2a`
- `0x14004edbc`
- `0x140050184`
- `0x140052954`
- `0x140052bf8`
- `0x140053b2c`
- `0x14005d654`
- `0x14005fcbc`
- `0x140067010`

## string_xrefs

- `0x14004edd6`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::call<_lambda_12918d939973c46c384f4162aa40ffe3_ &>(
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
  v7 = L"Windows.Security.Cryptography.CryptographicBuffer";
  *(_QWORD *)&v8 = 49;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    (__int64)winrt::impl::guid_v<winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>,
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
    v11 = &qword_1400839D8;
    _InterlockedIncrement64(&qword_1400839D8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1400839E0);
    }
    _lambda_12918d939973c46c384f4162aa40ffe3_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>);
    _InterlockedDecrement64(&qword_1400839D8);
  }
  else
  {
    _lambda_12918d939973c46c384f4162aa40ffe3_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v10);
  return a2;
}

```

## disassembly

```asm
0x14004edbc  mov     [rsp-18h+arg_8], rbx
0x14004edc1  mov     [rsp-18h+arg_0], rcx
0x14004edc6  push    rbp
0x14004edc7  push    rsi
0x14004edc8  push    rdi
0x14004edc9  mov     rbp, rsp
0x14004edcc  sub     rsp, 60h
0x14004edd0  mov     rsi, r8
0x14004edd3  mov     rbx, rdx
0x14004edd6  lea     rax, aWindowsSecurit; "Windows.Security.Cryptography.Cryptogra"...
0x14004eddd  mov     [rbp+var_38], rax
0x14004ede1  mov     qword ptr [rbp+var_30], 31h ; '1'
0x14004ede9  lea     rdx, [rbp+var_38]
0x14004eded  lea     rcx, [rbp+var_20]
0x14004edf1  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004edf6  mov     [rbp+arg_18], 0
0x14004edfe  mov     dword ptr [rbp+var_38], 0
0x14004ee05  xorps   xmm0, xmm0
0x14004ee08  movdqu  [rbp+var_30], xmm0
0x14004ee0d  lea     r9, [rbp+arg_18]
0x14004ee11  lea     r8, ??$guid_v@UICryptographicBufferStatics@Cryptography@Security@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x14004ee18  lea     rdx, [rbp+var_20]
0x14004ee1c  lea     rcx, [rbp+arg_0]
0x14004ee20  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x14004ee25  lea     r8, [rbp+var_38]
0x14004ee29  mov     edx, dword ptr [rbp+arg_0]
0x14004ee2c  lea     rcx, [rbp+arg_0]
0x14004ee30  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14004ee35  mov     rdi, [rbp+arg_18]
0x14004ee39  mov     [rbp+arg_0], rdi
0x14004ee3d  test    rdi, rdi
0x14004ee40  jz      loc_14004EED5
0x14004ee46  mov     [rbp+arg_18], 0
0x14004ee4e  mov     rax, [rdi]
0x14004ee51  lea     r8, [rbp+arg_18]
0x14004ee55  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004ee5c  mov     rcx, rdi
0x14004ee5f  mov     rax, [rax]
0x14004ee62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ee67  mov     rax, [rbp+arg_18]
0x14004ee6b  mov     [rbp+arg_18], rax
0x14004ee6f  test    rax, rax
0x14004ee72  jz      short loc_14004EED5
0x14004ee74  lea     rcx, [rbp+arg_18]
0x14004ee78  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004ee7d  lea     rax, qword_1400839D8
0x14004ee84  mov     [rbp+arg_18], rax
0x14004ee88  lock inc cs:qword_1400839D8
0x14004ee90  xor     eax, eax
0x14004ee92  lock cmpxchg cs:??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x14004ee9b  jnz     short loc_14004EEB8
0x14004ee9d  mov     [rbp+arg_0], 0
0x14004eea5  lea     rdx, stru_1400839E0; ListEntry
0x14004eeac  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004eeb3  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004eeb8  lea     r8, ??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x14004eebf  mov     rdx, rbx
0x14004eec2  mov     rcx, rsi
0x14004eec5  call    ??R_lambda_12918d939973c46c384f4162aa40ffe3_@@QEBA@AEBUICryptographicBufferStatics@Cryptography@Security@Windows@winrt@@@Z; _lambda_12918d939973c46c384f4162aa40ffe3_::operator()(winrt::Windows::Security::Cryptography::ICryptographicBufferStatics const &)
0x14004eeca  nop
0x14004eecb  lock dec cs:qword_1400839D8
0x14004eed3  jmp     short loc_14004EEE5
0x14004eed5  lea     r8, [rbp+arg_0]
0x14004eed9  mov     rdx, rbx
0x14004eedc  mov     rcx, rsi
0x14004eedf  call    ??R_lambda_12918d939973c46c384f4162aa40ffe3_@@QEBA@AEBUICryptographicBufferStatics@Cryptography@Security@Windows@winrt@@@Z; _lambda_12918d939973c46c384f4162aa40ffe3_::operator()(winrt::Windows::Security::Cryptography::ICryptographicBufferStatics const &)
0x14004eee4  nop
0x14004eee5  lea     rcx, [rbp+arg_0]; this
0x14004eee9  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004eeee  mov     rax, rbx
0x14004eef1  mov     rbx, [rsp+60h+arg_8]
0x14004eef9  add     rsp, 60h
0x14004eefd  pop     rdi
0x14004eefe  pop     rsi
0x14004eeff  pop     rbp
0x14004ef00  retn
```
