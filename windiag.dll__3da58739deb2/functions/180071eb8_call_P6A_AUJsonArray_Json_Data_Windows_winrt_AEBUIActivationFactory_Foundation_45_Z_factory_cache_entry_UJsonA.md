# ??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x180071eb8`
- end: `0x180071fd7`
- name: `??$call@P6A?AUJsonArray@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonArray@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074570`

## callees

- `0x180032ed9`
- `0x180071eb8`
- `0x180072264`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071edd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180071edd`

## string_xrefs

- `0x180071ef2`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonArray (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-10h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+88h] [rbp+38h] BYREF

  v9 = a1;
  if ( aWindowsDataJso_1[27] )
    abort();
  v7[0] = 1;
  v7[1] = 27;
  v8 = L"Windows.Data.Json.JsonArray";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_1800BEB48;
    _InterlockedIncrement64(&qword_1800BEB48);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800BEB50);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_1800BEB48);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v9);
  }
  if ( v9 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x180071eb8  mov     [rsp-18h+arg_8], rbx
0x180071ebd  mov     [rsp-18h+arg_0], rcx
0x180071ec2  push    rbp
0x180071ec3  push    rsi
0x180071ec4  push    rdi
0x180071ec5  mov     rbp, rsp
0x180071ec8  sub     rsp, 50h
0x180071ecc  mov     rdi, r8
0x180071ecf  mov     rbx, rdx
0x180071ed2  xor     esi, esi
0x180071ed4  cmp     word ptr cs:aWindowsDataJso_1+36h, si; ""
0x180071edb  jz      short loc_180071EE4
0x180071edd  call    cs:__imp_abort
0x180071ee4  mov     [rbp+var_20], 1
0x180071eeb  mov     [rbp+var_1C], 1Bh
0x180071ef2  lea     rax, aWindowsDataJso_1; "Windows.Data.Json.JsonArray"
0x180071ef9  mov     [rbp+var_10], rax
0x180071efd  lea     rax, [rbp+var_20]
0x180071f01  mov     [rbp+var_28], rax
0x180071f05  lea     rdx, [rbp+var_28]
0x180071f09  lea     rcx, [rbp+arg_0]
0x180071f0d  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x180071f12  nop
0x180071f13  mov     rcx, [rbp+arg_0]
0x180071f17  test    rcx, rcx
0x180071f1a  jz      loc_180071FA8
0x180071f20  mov     [rbp+arg_18], rsi
0x180071f24  mov     rax, [rcx]
0x180071f27  lea     r8, [rbp+arg_18]
0x180071f2b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180071f32  mov     rax, [rax]
0x180071f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f3a  mov     rax, [rbp+arg_18]
0x180071f3e  mov     [rbp+arg_18], rax
0x180071f42  test    rax, rax
0x180071f45  jz      short loc_180071FA8
0x180071f47  lea     rcx, [rbp+arg_18]
0x180071f4b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071f50  lea     rax, qword_1800BEB48
0x180071f57  mov     [rbp+arg_18], rax
0x180071f5b  lock inc cs:qword_1800BEB48
0x180071f63  mov     rcx, [rbp+arg_0]
0x180071f67  xor     eax, eax
0x180071f69  lock cmpxchg cs:??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x180071f72  jnz     short loc_180071F8B
0x180071f74  mov     [rbp+arg_0], rsi
0x180071f78  lea     rdx, stru_1800BEB50; ListEntry
0x180071f7f  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180071f86  call    WINRT_IMPL_InterlockedPushEntrySList
0x180071f8b  lea     rdx, ??$factory_cache_entry_v@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonArray@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Foundation::IActivationFactory>
0x180071f92  mov     rcx, rbx
0x180071f95  mov     rax, [rdi]
0x180071f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f9d  nop
0x180071f9e  lock dec cs:qword_1800BEB48
0x180071fa6  jmp     short loc_180071FB8
0x180071fa8  lea     rdx, [rbp+arg_0]
0x180071fac  mov     rcx, rbx
0x180071faf  mov     rax, [rdi]
0x180071fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fb7  nop
0x180071fb8  cmp     [rbp+arg_0], rsi
0x180071fbc  jz      short loc_180071FC7
0x180071fbe  lea     rcx, [rbp+arg_0]
0x180071fc2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180071fc7  mov     rax, rbx
0x180071fca  mov     rbx, [rsp+50h+arg_8]
0x180071fcf  add     rsp, 50h
0x180071fd3  pop     rdi
0x180071fd4  pop     rsi
0x180071fd5  pop     rbp
0x180071fd6  retn
```
