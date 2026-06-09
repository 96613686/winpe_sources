# ??$call@AEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@Z

- ea: `0x180071d1c`
- end: `0x180071eb1`
- name: `??$call@AEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_fa5bfa998c3b0e5f1b75589fad572465_@@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073450`

## callees

- `0x180032ed9`
- `0x180071d1c`
- `0x1800722c4`
- `0x180074344`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071d49`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071d49`

## string_xrefs

- `0x180071d5e`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_fa5bfa998c3b0e5f1b75589fad572465_ &>(
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
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
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
                                                             + 48LL))(
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
0x180071d1c  mov     [rsp-18h+arg_8], rbx
0x180071d21  mov     [rsp-18h+arg_10], rsi
0x180071d26  mov     [rsp-18h+arg_0], rcx
0x180071d2b  push    rbp
0x180071d2c  push    rdi
0x180071d2d  push    r14
0x180071d2f  mov     rbp, rsp
0x180071d32  sub     rsp, 70h
0x180071d36  mov     rsi, r8
0x180071d39  mov     rbx, rdx
0x180071d3c  xor     r14d, r14d
0x180071d3f  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x180071d47  jz      short loc_180071D50
0x180071d49  call    cs:__imp_abort
0x180071d50  mov     [rbp+var_20], 1
0x180071d57  mov     [rbp+var_1C], 1Bh
0x180071d5e  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180071d65  mov     [rbp+var_10], rax
0x180071d69  lea     rax, [rbp+var_20]
0x180071d6d  mov     [rbp+var_28], rax
0x180071d71  lea     rdx, [rbp+var_28]
0x180071d75  lea     rcx, [rbp+arg_0]
0x180071d79  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180071d7e  nop
0x180071d7f  mov     rdi, [rbp+arg_0]
0x180071d83  test    rdi, rdi
0x180071d86  jz      loc_180071E44
0x180071d8c  mov     [rbp+arg_18], r14
0x180071d90  mov     rax, [rdi]
0x180071d93  lea     r8, [rbp+arg_18]
0x180071d97  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180071d9e  mov     rcx, rdi
0x180071da1  mov     rax, [rax]
0x180071da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071da9  mov     rax, [rbp+arg_18]
0x180071dad  mov     [rbp+arg_18], rax
0x180071db1  test    rax, rax
0x180071db4  jz      loc_180071E44
0x180071dba  lea     rcx, [rbp+arg_18]
0x180071dbe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071dc3  lea     rax, qword_1800BEB08
0x180071dca  mov     [rbp+var_48], rax
0x180071dce  lock inc cs:qword_1800BEB08
0x180071dd6  xor     eax, eax
0x180071dd8  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071de1  jnz     short loc_180071DFD
0x180071de3  mov     [rbp+arg_0], r14
0x180071de7  lea     rdx, ListEntry; ListEntry
0x180071dee  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180071df5  call    WINRT_IMPL_InterlockedPushEntrySList
0x180071dfa  mov     rdi, r14
0x180071dfd  mov     [rbp+arg_18], r14
0x180071e01  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071e08  mov     [rbp+var_40], r14d
0x180071e0c  xorps   xmm0, xmm0
0x180071e0f  movdqu  [rbp+var_38], xmm0
0x180071e14  mov     rax, [rcx]
0x180071e17  mov     rdx, [rsi]
0x180071e1a  lea     r8, [rbp+arg_18]
0x180071e1e  mov     rdx, [rdx]
0x180071e21  mov     rax, [rax+30h]
0x180071e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e2a  test    eax, eax
0x180071e2c  js      short loc_180071EA5
0x180071e2e  mov     rax, [rbp+arg_18]
0x180071e32  mov     [rbx], rax
0x180071e35  lock dec cs:qword_1800BEB08
0x180071e3d  test    rdi, rdi
0x180071e40  jz      short loc_180071E81
0x180071e42  jmp     short loc_180071E78
0x180071e44  mov     [rbp+arg_18], r14
0x180071e48  mov     [rbp+var_40], r14d
0x180071e4c  xorps   xmm0, xmm0
0x180071e4f  movdqu  [rbp+var_38], xmm0
0x180071e54  mov     rax, [rdi]
0x180071e57  mov     rdx, [rsi]
0x180071e5a  lea     r8, [rbp+arg_18]
0x180071e5e  mov     rdx, [rdx]
0x180071e61  mov     rcx, rdi
0x180071e64  mov     rax, [rax+30h]
0x180071e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e6d  test    eax, eax
0x180071e6f  js      short loc_180071E99
0x180071e71  mov     rax, [rbp+arg_18]
0x180071e75  mov     [rbx], rax
0x180071e78  lea     rcx, [rbp+arg_0]
0x180071e7c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071e81  mov     rax, rbx
0x180071e84  lea     r11, [rsp+70h+var_s0]
0x180071e89  mov     rbx, [r11+28h]
0x180071e8d  mov     rsi, [r11+30h]
0x180071e91  mov     rsp, r11
0x180071e94  pop     r14
0x180071e96  pop     rdi
0x180071e97  pop     rbp
0x180071e98  retn
0x180071e99  lea     rdx, [rbp+var_40]
0x180071e9d  mov     ecx, eax
0x180071e9f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180071ea5  lea     rdx, [rbp+var_40]
0x180071ea9  mov     ecx, eax
0x180071eab  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
