# ??$call@AEAV_lambda_5af0dbefa536f7ef53fc363f9496dddb_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_5af0dbefa536f7ef53fc363f9496dddb_@@@Z

- ea: `0x1800719e4`
- end: `0x180071b77`
- name: `??$call@AEAV_lambda_5af0dbefa536f7ef53fc363f9496dddb_@@@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_5af0dbefa536f7ef53fc363f9496dddb_@@@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074570`

## callees

- `0x180032ed9`
- `0x1800719e4`
- `0x1800722c4`
- `0x180074344`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071a11`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071a11`

## string_xrefs

- `0x180071a26`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::call<_lambda_5af0dbefa536f7ef53fc363f9496dddb_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _BYTE **a3)
{
  signed __int64 v5; // rdi
  _BYTE *v6; // rdx
  int v7; // eax
  _BYTE *v8; // rdx
  int v9; // eax
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int128 v12; // [rsp+38h] [rbp-38h]
  _DWORD *v13; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v14[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v15; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v16)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  v16 = a1;
  if ( aWindowsDataJso_0[27] )
    abort();
  v14[0] = 1;
  v14[1] = 27;
  v15 = L"Windows.Data.Json.JsonValue";
  v13 = v14;
  winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(&v16, &v13);
  v5 = (signed __int64)v16;
  if ( !v16 || (v17 = 0, (**v16)(v16, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v17), !v17) )
  {
    v17 = 0;
    v11 = 0;
    v12 = 0;
    v8 = *a3;
    LOBYTE(v8) = **a3;
    v9 = (*(__int64 (__fastcall **)(signed __int64, _BYTE *, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, v8, &v17);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v11);
    *a2 = v17;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
  _InterlockedIncrement64(&qword_1800BEB08);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
          v5,
          0) )
  {
    v16 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    v5 = 0;
  }
  v17 = 0;
  v11 = 0;
  v12 = 0;
  v6 = *a3;
  LOBYTE(v6) = **a3;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
                                                              + 64LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
         v6,
         &v17);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v11);
  *a2 = v17;
  _InterlockedDecrement64(&qword_1800BEB08);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  return a2;
}

```

## disassembly

```asm
0x1800719e4  mov     [rsp-18h+arg_8], rbx
0x1800719e9  mov     [rsp-18h+arg_10], rsi
0x1800719ee  mov     [rsp-18h+arg_0], rcx
0x1800719f3  push    rbp
0x1800719f4  push    rdi
0x1800719f5  push    r14
0x1800719f7  mov     rbp, rsp
0x1800719fa  sub     rsp, 70h
0x1800719fe  mov     rsi, r8
0x180071a01  mov     rbx, rdx
0x180071a04  xor     r14d, r14d
0x180071a07  cmp     word ptr cs:aWindowsDataJso_0+36h, r14w; ""
0x180071a0f  jz      short loc_180071A18
0x180071a11  call    cs:__imp_abort
0x180071a18  mov     [rbp+var_20], 1
0x180071a1f  mov     [rbp+var_1C], 1Bh
0x180071a26  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180071a2d  mov     [rbp+var_10], rax
0x180071a31  lea     rax, [rbp+var_20]
0x180071a35  mov     [rbp+var_28], rax
0x180071a39  lea     rdx, [rbp+var_28]
0x180071a3d  lea     rcx, [rbp+arg_0]
0x180071a41  call    ??$get_activation_factory@UIJsonValueStatics@Json@Data@Windows@winrt@@@winrt@@YA?AUIJsonValueStatics@Json@Data@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Data::Json::IJsonValueStatics>(winrt::param::hstring const &)
0x180071a46  nop
0x180071a47  mov     rdi, [rbp+arg_0]
0x180071a4b  test    rdi, rdi
0x180071a4e  jz      loc_180071B0B
0x180071a54  mov     [rbp+arg_18], r14
0x180071a58  mov     rax, [rdi]
0x180071a5b  lea     r8, [rbp+arg_18]
0x180071a5f  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180071a66  mov     rcx, rdi
0x180071a69  mov     rax, [rax]
0x180071a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a71  mov     rax, [rbp+arg_18]
0x180071a75  mov     [rbp+arg_18], rax
0x180071a79  test    rax, rax
0x180071a7c  jz      loc_180071B0B
0x180071a82  lea     rcx, [rbp+arg_18]
0x180071a86  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071a8b  lea     rax, qword_1800BEB08
0x180071a92  mov     [rbp+var_48], rax
0x180071a96  lock inc cs:qword_1800BEB08
0x180071a9e  xor     eax, eax
0x180071aa0  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071aa9  jnz     short loc_180071AC5
0x180071aab  mov     [rbp+arg_0], r14
0x180071aaf  lea     rdx, ListEntry; ListEntry
0x180071ab6  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180071abd  call    WINRT_IMPL_InterlockedPushEntrySList
0x180071ac2  mov     rdi, r14
0x180071ac5  mov     [rbp+arg_18], r14
0x180071ac9  mov     rcx, cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>
0x180071ad0  mov     [rbp+var_40], r14d
0x180071ad4  xorps   xmm0, xmm0
0x180071ad7  movdqu  [rbp+var_38], xmm0
0x180071adc  mov     rax, [rcx]
0x180071adf  mov     rdx, [rsi]
0x180071ae2  lea     r8, [rbp+arg_18]
0x180071ae6  mov     dl, [rdx]
0x180071ae8  mov     rax, [rax+40h]
0x180071aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071af1  test    eax, eax
0x180071af3  js      short loc_180071B6B
0x180071af5  mov     rax, [rbp+arg_18]
0x180071af9  mov     [rbx], rax
0x180071afc  lock dec cs:qword_1800BEB08
0x180071b04  test    rdi, rdi
0x180071b07  jz      short loc_180071B47
0x180071b09  jmp     short loc_180071B3E
0x180071b0b  mov     [rbp+arg_18], r14
0x180071b0f  mov     [rbp+var_40], r14d
0x180071b13  xorps   xmm0, xmm0
0x180071b16  movdqu  [rbp+var_38], xmm0
0x180071b1b  mov     rax, [rdi]
0x180071b1e  mov     rdx, [rsi]
0x180071b21  lea     r8, [rbp+arg_18]
0x180071b25  mov     dl, [rdx]
0x180071b27  mov     rcx, rdi
0x180071b2a  mov     rax, [rax+40h]
0x180071b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b33  test    eax, eax
0x180071b35  js      short loc_180071B5F
0x180071b37  mov     rax, [rbp+arg_18]
0x180071b3b  mov     [rbx], rax
0x180071b3e  lea     rcx, [rbp+arg_0]
0x180071b42  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071b47  mov     rax, rbx
0x180071b4a  lea     r11, [rsp+70h+var_s0]
0x180071b4f  mov     rbx, [r11+28h]
0x180071b53  mov     rsi, [r11+30h]
0x180071b57  mov     rsp, r11
0x180071b5a  pop     r14
0x180071b5c  pop     rdi
0x180071b5d  pop     rbp
0x180071b5e  retn
0x180071b5f  lea     rdx, [rbp+var_40]
0x180071b63  mov     ecx, eax
0x180071b65  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180071b6b  lea     rdx, [rbp+var_40]
0x180071b6f  mov     ecx, eax
0x180071b71  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
