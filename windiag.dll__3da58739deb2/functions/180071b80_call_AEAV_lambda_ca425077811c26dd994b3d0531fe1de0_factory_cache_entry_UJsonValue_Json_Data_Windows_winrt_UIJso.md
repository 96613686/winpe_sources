# ??$call@AEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@Z

- ea: `0x180071b80`
- end: `0x180071d15`
- name: `??$call@AEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ca425077811c26dd994b3d0531fe1de0_@@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074570`

## callees

- `0x180032ed9`
- `0x180071b80`
- `0x1800722c4`
- `0x180074344`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071bad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071bad`

## string_xrefs

- `0x180071bc2`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_ca425077811c26dd994b3d0531fe1de0_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  if ( aWindowsDataJso_0[27] )
    abort();
  v12[0] = 1;
  v12[1] = 27;
  v13 = L"Windows.Data.Json.JsonValue";
  v11 = v12;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v14, &v11);
  v5 = (signed __int64)v14;
  if ( !v14 || (v15 = 0, (**v14)(v14, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v15), !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_1800BEB08);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    v5 = 0;
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_1800BEB08);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x180071b80  mov     [rsp-18h+arg_8], rbx
0x180071b85  mov     [rsp-18h+arg_10], rsi
0x180071b8a  mov     [rsp-18h+arg_0], rcx
0x180071b8f  push    rbp
0x180071b90  push    rdi
0x180071b91  push    r14
0x180071b93  mov     rbp, rsp
0x180071b96  sub     rsp, 70h
0x180071b9a  mov     rsi, r8
0x180071b9d  mov     rbx, rdx
0x180071ba0  xor     r14d, r14d
0x180071ba3  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x180071bab  jz      short loc_180071BB4
0x180071bad  call    cs:__imp_abort
0x180071bb4  mov     [rbp+var_20], 1
0x180071bbb  mov     [rbp+var_1C], 1Bh
0x180071bc2  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180071bc9  mov     [rbp+var_10], rax
0x180071bcd  lea     rax, [rbp+var_20]
0x180071bd1  mov     [rbp+var_28], rax
0x180071bd5  lea     rdx, [rbp+var_28]
0x180071bd9  lea     rcx, [rbp+arg_0]
0x180071bdd  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180071be2  nop
0x180071be3  mov     rdi, [rbp+arg_0]
0x180071be7  test    rdi, rdi
0x180071bea  jz      loc_180071CA8
0x180071bf0  mov     [rbp+arg_18], r14
0x180071bf4  mov     rax, [rdi]
0x180071bf7  lea     r8, [rbp+arg_18]
0x180071bfb  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180071c02  mov     rcx, rdi
0x180071c05  mov     rax, [rax]
0x180071c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c0d  mov     rax, [rbp+arg_18]
0x180071c11  mov     [rbp+arg_18], rax
0x180071c15  test    rax, rax
0x180071c18  jz      loc_180071CA8
0x180071c1e  lea     rcx, [rbp+arg_18]
0x180071c22  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071c27  lea     rax, qword_1800BEB08
0x180071c2e  mov     [rbp+var_48], rax
0x180071c32  lock inc cs:qword_1800BEB08
0x180071c3a  xor     eax, eax
0x180071c3c  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071c45  jnz     short loc_180071C61
0x180071c47  mov     [rbp+arg_0], r14
0x180071c4b  lea     rdx, ListEntry; ListEntry
0x180071c52  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180071c59  call    WINRT_IMPL_InterlockedPushEntrySList
0x180071c5e  mov     rdi, r14
0x180071c61  mov     [rbp+arg_18], r14
0x180071c65  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071c6c  mov     [rbp+var_40], r14d
0x180071c70  xorps   xmm0, xmm0
0x180071c73  movdqu  [rbp+var_38], xmm0
0x180071c78  mov     rax, [rcx]
0x180071c7b  mov     rdx, [rsi]
0x180071c7e  lea     r8, [rbp+arg_18]
0x180071c82  mov     rdx, [rdx]
0x180071c85  mov     rax, [rax+50h]
0x180071c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c8e  test    eax, eax
0x180071c90  js      short loc_180071D09
0x180071c92  mov     rax, [rbp+arg_18]
0x180071c96  mov     [rbx], rax
0x180071c99  lock dec cs:qword_1800BEB08
0x180071ca1  test    rdi, rdi
0x180071ca4  jz      short loc_180071CE5
0x180071ca6  jmp     short loc_180071CDC
0x180071ca8  mov     [rbp+arg_18], r14
0x180071cac  mov     [rbp+var_40], r14d
0x180071cb0  xorps   xmm0, xmm0
0x180071cb3  movdqu  [rbp+var_38], xmm0
0x180071cb8  mov     rax, [rdi]
0x180071cbb  mov     rdx, [rsi]
0x180071cbe  lea     r8, [rbp+arg_18]
0x180071cc2  mov     rdx, [rdx]
0x180071cc5  mov     rcx, rdi
0x180071cc8  mov     rax, [rax+50h]
0x180071ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cd1  test    eax, eax
0x180071cd3  js      short loc_180071CFD
0x180071cd5  mov     rax, [rbp+arg_18]
0x180071cd9  mov     [rbx], rax
0x180071cdc  lea     rcx, [rbp+arg_0]
0x180071ce0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071ce5  mov     rax, rbx
0x180071ce8  lea     r11, [rsp+70h+var_s0]
0x180071ced  mov     rbx, [r11+28h]
0x180071cf1  mov     rsi, [r11+30h]
0x180071cf5  mov     rsp, r11
0x180071cf8  pop     r14
0x180071cfa  pop     rdi
0x180071cfb  pop     rbp
0x180071cfc  retn
0x180071cfd  lea     rdx, [rbp+var_40]
0x180071d01  mov     ecx, eax
0x180071d03  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180071d09  lea     rdx, [rbp+var_40]
0x180071d0d  mov     ecx, eax
0x180071d0f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
