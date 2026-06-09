# ??$call@P6A?AUJsonValue@Json@Data@Windows@winrt@@AEBUIJsonValueStatics2@2345@@Z@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics2@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonValue@Json@Data@Windows@2@AEBUIJsonValueStatics2@4562@@Z@Z

- ea: `0x180072108`
- end: `0x18007225c`
- name: `??$call@P6A?AUJsonValue@Json@Data@Windows@winrt@@AEBUIJsonValueStatics2@2345@@Z@?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics2@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonValue@Json@Data@Windows@2@AEBUIJsonValueStatics2@4562@@Z@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800731ec`

## callees

- `0x180032ed9`
- `0x180072108`
- `0x1800726b8`
- `0x180074344`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18007212d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18007212d`

## string_xrefs

- `0x180072142`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>::call<winrt::Windows::Data::Json::JsonValue (*)(winrt::Windows::Data::Json::IJsonValueStatics2 const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+30h] [rbp-40h] BYREF
  __int128 v8; // [rsp+38h] [rbp-38h]
  _DWORD *v9; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v11; // [rsp+60h] [rbp-10h]
  __int64 *v12; // [rsp+90h] [rbp+20h] BYREF
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // [rsp+A8h] [rbp+38h] BYREF

  v12 = a1;
  if ( aWindowsDataJso_0[27] )
    abort();
  v10[0] = 1;
  v10[1] = 27;
  v11 = L"Windows.Data.Json.JsonValue";
  v9 = v10;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    (__int64)&winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics2>,
    (__int64)&v6);
  if ( (int)v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v7);
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v12 = 0, (**v6)(v6, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v12), v12) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
    v12 = &qword_1800BEAE8;
    _InterlockedIncrement64(&qword_1800BEAE8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>,
            (signed __int64)v13,
            0) )
    {
      v13 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800BEAF0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>);
    _InterlockedDecrement64(&qword_1800BEAE8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v13);
  }
  if ( v13 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  return a2;
}

```

## disassembly

```asm
0x180072108  mov     [rsp-18h+arg_8], rbx
0x18007210d  mov     [rsp-18h+arg_0], rcx
0x180072112  push    rbp
0x180072113  push    rsi
0x180072114  push    rdi
0x180072115  mov     rbp, rsp
0x180072118  sub     rsp, 70h
0x18007211c  mov     rdi, r8
0x18007211f  mov     rbx, rdx
0x180072122  xor     esi, esi
0x180072124  cmp     word ptr cs:aWindowsDataJso_0+36h, si; ""
0x18007212b  jz      short loc_180072134
0x18007212d  call    cs:__imp_abort
0x180072134  mov     [rbp+var_20], 1
0x18007213b  mov     [rbp+var_1C], 1Bh
0x180072142  lea     rax, aWindowsDataJso_0; "Windows.Data.Json.JsonValue"
0x180072149  mov     [rbp+var_10], rax
0x18007214d  lea     rax, [rbp+var_20]
0x180072151  mov     [rbp+var_28], rax
0x180072155  mov     [rbp+var_48], rsi
0x180072159  mov     [rbp+var_40], esi
0x18007215c  xorps   xmm0, xmm0
0x18007215f  movdqu  [rbp+var_38], xmm0
0x180072164  lea     r9, [rbp+var_48]
0x180072168  lea     r8, ??$guid_v@UIJsonValueStatics2@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValueStatics2>
0x18007216f  lea     rdx, [rbp+var_28]
0x180072173  lea     rcx, [rbp+arg_0]
0x180072177  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18007217c  mov     ecx, dword ptr [rbp+arg_0]
0x18007217f  test    ecx, ecx
0x180072181  js      loc_180072252
0x180072187  mov     rcx, [rbp+var_48]
0x18007218b  mov     [rbp+arg_18], rcx
0x18007218f  test    rcx, rcx
0x180072192  jz      loc_180072220
0x180072198  mov     [rbp+arg_0], rsi
0x18007219c  mov     rax, [rcx]
0x18007219f  lea     r8, [rbp+arg_0]
0x1800721a3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800721aa  mov     rax, [rax]
0x1800721ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721b2  mov     rax, [rbp+arg_0]
0x1800721b6  mov     [rbp+arg_0], rax
0x1800721ba  test    rax, rax
0x1800721bd  jz      short loc_180072220
0x1800721bf  lea     rcx, [rbp+arg_0]
0x1800721c3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800721c8  lea     rax, qword_1800BEAE8
0x1800721cf  mov     [rbp+arg_0], rax
0x1800721d3  lock inc cs:qword_1800BEAE8
0x1800721db  mov     rcx, [rbp+arg_18]
0x1800721df  xor     eax, eax
0x1800721e1  lock cmpxchg cs:??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics2@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>
0x1800721ea  jnz     short loc_180072203
0x1800721ec  mov     [rbp+arg_18], rsi
0x1800721f0  lea     rdx, stru_1800BEAF0; ListEntry
0x1800721f7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800721fe  call    WINRT_IMPL_InterlockedPushEntrySList
0x180072203  lea     rdx, ??$factory_cache_entry_v@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonValue@Json@Data@Windows@winrt@@UIJsonValueStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics2>
0x18007220a  mov     rcx, rbx
0x18007220d  mov     rax, [rdi]
0x180072210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072215  nop
0x180072216  lock dec cs:qword_1800BEAE8
0x18007221e  jmp     short loc_180072230
0x180072220  lea     rdx, [rbp+arg_18]
0x180072224  mov     rcx, rbx
0x180072227  mov     rax, [rdi]
0x18007222a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007222f  nop
0x180072230  cmp     [rbp+arg_18], rsi
0x180072234  jz      short loc_18007223F
0x180072236  lea     rcx, [rbp+arg_18]
0x18007223a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18007223f  mov     rax, rbx
0x180072242  mov     rbx, [rsp+70h+arg_8]
0x18007224a  add     rsp, 70h
0x18007224e  pop     rdi
0x18007224f  pop     rsi
0x180072250  pop     rbp
0x180072251  retn
0x180072252  lea     rdx, [rbp+var_40]
0x180072256  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
