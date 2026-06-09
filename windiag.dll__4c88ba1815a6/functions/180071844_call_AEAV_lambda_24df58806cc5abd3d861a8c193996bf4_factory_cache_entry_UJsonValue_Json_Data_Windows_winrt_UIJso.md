# ??$call@AEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@Z

- ea: `0x180071844`
- end: `0x1800719de`
- name: `??$call@AEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_24df58806cc5abd3d861a8c193996bf4_@@@Z`
- size: `410`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074570`

## callees

- `0x180032ed9`
- `0x180071844`
- `0x1800722c4`
- `0x180074344`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071871`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071871`

## string_xrefs

- `0x180071886`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_24df58806cc5abd3d861a8c193996bf4_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD *a3)
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
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, *a3, &v15);
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
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 72LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
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
0x180071844  mov     [rsp-18h+arg_8], rbx
0x180071849  mov     [rsp-18h+arg_10], rsi
0x18007184e  mov     [rsp-18h+arg_0], rcx
0x180071853  push    rbp
0x180071854  push    rdi
0x180071855  push    r14
0x180071857  mov     rbp, rsp
0x18007185a  sub     rsp, 70h
0x18007185e  mov     rsi, r8
0x180071861  mov     rbx, rdx
0x180071864  xor     r14d, r14d
0x180071867  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x18007186f  jz      short loc_180071878
0x180071871  call    cs:__imp_abort
0x180071878  mov     [rbp+var_20], 1
0x18007187f  mov     [rbp+var_1C], 1Bh
0x180071886  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x18007188d  mov     [rbp+var_10], rax
0x180071891  lea     rax, [rbp+var_20]
0x180071895  mov     [rbp+var_28], rax
0x180071899  lea     rdx, [rbp+var_28]
0x18007189d  lea     rcx, [rbp+arg_0]
0x1800718a1  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x1800718a6  nop
0x1800718a7  mov     rdi, [rbp+arg_0]
0x1800718ab  test    rdi, rdi
0x1800718ae  jz      loc_180071970
0x1800718b4  mov     [rbp+arg_18], r14
0x1800718b8  mov     rax, [rdi]
0x1800718bb  lea     r8, [rbp+arg_18]
0x1800718bf  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800718c6  mov     rcx, rdi
0x1800718c9  mov     rax, [rax]
0x1800718cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718d1  mov     rax, [rbp+arg_18]
0x1800718d5  mov     [rbp+arg_18], rax
0x1800718d9  test    rax, rax
0x1800718dc  jz      loc_180071970
0x1800718e2  lea     rcx, [rbp+arg_18]
0x1800718e6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800718eb  lea     rax, qword_1800BEB08
0x1800718f2  mov     [rbp+var_48], rax
0x1800718f6  lock inc cs:qword_1800BEB08
0x1800718fe  xor     eax, eax
0x180071900  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071909  jnz     short loc_180071925
0x18007190b  mov     [rbp+arg_0], r14
0x18007190f  lea     rdx, ListEntry; ListEntry
0x180071916  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18007191d  call    WINRT_IMPL_InterlockedPushEntrySList
0x180071922  mov     rdi, r14
0x180071925  mov     [rbp+arg_18], r14
0x180071929  mov     rdx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071930  mov     [rbp+var_40], r14d
0x180071934  xorps   xmm0, xmm0
0x180071937  movdqu  [rbp+var_38], xmm0
0x18007193c  mov     rax, [rdx]
0x18007193f  mov     rcx, [rsi]
0x180071942  lea     r8, [rbp+arg_18]
0x180071946  movsd   xmm1, qword ptr [rcx]
0x18007194a  mov     rcx, rdx
0x18007194d  mov     rax, [rax+48h]
0x180071951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071956  test    eax, eax
0x180071958  js      short loc_1800719D2
0x18007195a  mov     rax, [rbp+arg_18]
0x18007195e  mov     [rbx], rax
0x180071961  lock dec cs:qword_1800BEB08
0x180071969  test    rdi, rdi
0x18007196c  jz      short loc_1800719AE
0x18007196e  jmp     short loc_1800719A5
0x180071970  mov     [rbp+arg_18], r14
0x180071974  mov     [rbp+var_40], r14d
0x180071978  xorps   xmm0, xmm0
0x18007197b  movdqu  [rbp+var_38], xmm0
0x180071980  mov     rax, [rdi]
0x180071983  mov     rdx, [rsi]
0x180071986  lea     r8, [rbp+arg_18]
0x18007198a  movsd   xmm1, qword ptr [rdx]
0x18007198e  mov     rcx, rdi
0x180071991  mov     rax, [rax+48h]
0x180071995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007199a  test    eax, eax
0x18007199c  js      short loc_1800719C6
0x18007199e  mov     rax, [rbp+arg_18]
0x1800719a2  mov     [rbx], rax
0x1800719a5  lea     rcx, [rbp+arg_0]
0x1800719a9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800719ae  mov     rax, rbx
0x1800719b1  lea     r11, [rsp+70h+var_s0]
0x1800719b6  mov     rbx, [r11+28h]
0x1800719ba  mov     rsi, [r11+30h]
0x1800719be  mov     rsp, r11
0x1800719c1  pop     r14
0x1800719c3  pop     rdi
0x1800719c4  pop     rbp
0x1800719c5  retn
0x1800719c6  lea     rdx, [rbp+var_40]
0x1800719ca  mov     ecx, eax
0x1800719cc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800719d2  lea     rdx, [rbp+var_40]
0x1800719d6  mov     ecx, eax
0x1800719d8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
