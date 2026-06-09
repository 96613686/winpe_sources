# ??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z

- ea: `0x18001a868`
- end: `0x18001aa2d`
- name: `??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z`
- size: `453`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x1800045c9`
- `0x1800066dc`
- `0x180010550`
- `0x180017b60`
- `0x18001a868`
- `0x180029010`

## string_xrefs

- `0x18001a890`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_ &>(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  signed __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 28;
  v13 = L"Windows.Data.Json.JsonObject";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>,
    &v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_180034AF8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180034B00);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
                                                                    + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_180034AF8);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18001a868  mov     [rsp-18h+arg_8], rbx
0x18001a86d  mov     [rsp-18h+arg_0], rcx
0x18001a872  push    rbp
0x18001a873  push    rsi
0x18001a874  push    rdi
0x18001a875  mov     rbp, rsp
0x18001a878  sub     rsp, 70h
0x18001a87c  mov     rsi, r8
0x18001a87f  mov     rdi, rdx
0x18001a882  mov     [rbp+var_20], 1
0x18001a889  mov     [rbp+var_1C], 1Ch
0x18001a890  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18001a897  mov     [rbp+var_10], rax
0x18001a89b  lea     rax, [rbp+var_20]
0x18001a89f  mov     [rbp+var_28], rax
0x18001a8a3  mov     [rbp+arg_18], 0
0x18001a8ab  mov     [rbp+var_40], 0
0x18001a8b2  xorps   xmm0, xmm0
0x18001a8b5  movdqu  [rbp+var_38], xmm0
0x18001a8ba  lea     r9, [rbp+arg_18]
0x18001a8be  lea     r8, ??$guid_v@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001a8c5  lea     rdx, [rbp+var_28]
0x18001a8c9  lea     rcx, [rbp+arg_0]
0x18001a8cd  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001a8d2  mov     ecx, dword ptr [rbp+arg_0]
0x18001a8d5  test    ecx, ecx
0x18001a8d7  js      loc_18001AA17
0x18001a8dd  mov     rbx, [rbp+arg_18]
0x18001a8e1  mov     [rbp+arg_0], rbx
0x18001a8e5  test    rbx, rbx
0x18001a8e8  jz      loc_18001A9B4
0x18001a8ee  mov     [rbp+arg_18], 0
0x18001a8f6  mov     rax, [rbx]
0x18001a8f9  lea     r8, [rbp+arg_18]
0x18001a8fd  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001a904  mov     rcx, rbx
0x18001a907  mov     rax, [rax]
0x18001a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a90f  mov     rax, [rbp+arg_18]
0x18001a913  mov     [rbp+arg_18], rax
0x18001a917  test    rax, rax
0x18001a91a  jz      loc_18001A9B4
0x18001a920  lea     rcx, [rbp+arg_18]
0x18001a924  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001a929  lea     rax, qword_180034AF8
0x18001a930  mov     [rbp+var_48], rax
0x18001a934  lock inc cs:qword_180034AF8
0x18001a93c  xor     eax, eax
0x18001a93e  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001a947  jnz     short loc_18001A962
0x18001a949  xor     ebx, ebx
0x18001a94b  mov     [rbp+arg_0], rbx
0x18001a94f  lea     rdx, stru_180034B00; ListEntry
0x18001a956  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001a95d  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001a962  mov     [rbp+arg_18], 0
0x18001a96a  mov     rcx, cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18001a971  mov     [rbp+var_40], 0
0x18001a978  xorps   xmm0, xmm0
0x18001a97b  movdqu  [rbp+var_38], xmm0
0x18001a980  mov     rax, [rcx]
0x18001a983  mov     rdx, [rsi]
0x18001a986  lea     r8, [rbp+arg_18]
0x18001a98a  mov     rdx, [rdx]
0x18001a98d  mov     rax, [rax+30h]
0x18001a991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a996  test    eax, eax
0x18001a998  js      loc_18001AA21
0x18001a99e  mov     rax, [rbp+arg_18]
0x18001a9a2  mov     [rdi], rax
0x18001a9a5  lock dec cs:qword_180034AF8
0x18001a9ad  test    rbx, rbx
0x18001a9b0  jz      short loc_18001A9F8
0x18001a9b2  jmp     short loc_18001A9EF
0x18001a9b4  mov     [rbp+arg_18], 0
0x18001a9bc  mov     [rbp+var_40], 0
0x18001a9c3  xorps   xmm0, xmm0
0x18001a9c6  movdqu  [rbp+var_38], xmm0
0x18001a9cb  mov     rax, [rbx]
0x18001a9ce  mov     rdx, [rsi]
0x18001a9d1  lea     r8, [rbp+arg_18]
0x18001a9d5  mov     rdx, [rdx]
0x18001a9d8  mov     rcx, rbx
0x18001a9db  mov     rax, [rax+30h]
0x18001a9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9e4  test    eax, eax
0x18001a9e6  js      short loc_18001AA0B
0x18001a9e8  mov     rax, [rbp+arg_18]
0x18001a9ec  mov     [rdi], rax
0x18001a9ef  lea     rcx, [rbp+arg_0]
0x18001a9f3  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001a9f8  mov     rax, rdi
0x18001a9fb  mov     rbx, [rsp+70h+arg_8]
0x18001aa03  add     rsp, 70h
0x18001aa07  pop     rdi
0x18001aa08  pop     rsi
0x18001aa09  pop     rbp
0x18001aa0a  retn
0x18001aa0b  lea     rdx, [rbp+var_40]
0x18001aa0f  mov     ecx, eax
0x18001aa11  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001aa17  lea     rdx, [rbp+var_40]
0x18001aa1b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001aa21  lea     rdx, [rbp+var_40]
0x18001aa25  mov     ecx, eax
0x18001aa27  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
