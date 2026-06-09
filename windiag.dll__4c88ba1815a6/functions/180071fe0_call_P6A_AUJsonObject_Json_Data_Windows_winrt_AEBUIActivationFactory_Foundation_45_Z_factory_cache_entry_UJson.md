# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x180071fe0`
- end: `0x1800720ff`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `287`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074570`

## callees

- `0x180032ed9`
- `0x180071fe0`
- `0x180072264`
- `0x180074d88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180072005`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180072005`

## string_xrefs

- `0x18007201a`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  if ( aWindowsDataJso[28] )
    abort();
  v7[0] = 1;
  v7[1] = 28;
  v8 = L"Windows.Data.Json.JsonObject";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_1800BEB28;
    _InterlockedIncrement64(&qword_1800BEB28);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800BEB30);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_1800BEB28);
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
0x180071fe0  mov     [rsp-18h+arg_8], rbx
0x180071fe5  mov     [rsp-18h+arg_0], rcx
0x180071fea  push    rbp
0x180071feb  push    rsi
0x180071fec  push    rdi
0x180071fed  mov     rbp, rsp
0x180071ff0  sub     rsp, 50h
0x180071ff4  mov     rdi, r8
0x180071ff7  mov     rbx, rdx
0x180071ffa  xor     esi, esi
0x180071ffc  cmp     word ptr cs:aWindowsDataJso+38h, si; ""
0x180072003  jz      short loc_18007200C
0x180072005  call    cs:__imp_abort
0x18007200c  mov     [rbp+var_20], 1
0x180072013  mov     [rbp+var_1C], 1Ch
0x18007201a  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x180072021  mov     [rbp+var_10], rax
0x180072025  lea     rax, [rbp+var_20]
0x180072029  mov     [rbp+var_28], rax
0x18007202d  lea     rdx, [rbp+var_28]
0x180072031  lea     rcx, [rbp+arg_0]
0x180072035  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18007203a  nop
0x18007203b  mov     rcx, [rbp+arg_0]
0x18007203f  test    rcx, rcx
0x180072042  jz      loc_1800720D0
0x180072048  mov     [rbp+arg_18], rsi
0x18007204c  mov     rax, [rcx]
0x18007204f  lea     r8, [rbp+arg_18]
0x180072053  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18007205a  mov     rax, [rax]
0x18007205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072062  mov     rax, [rbp+arg_18]
0x180072066  mov     [rbp+arg_18], rax
0x18007206a  test    rax, rax
0x18007206d  jz      short loc_1800720D0
0x18007206f  lea     rcx, [rbp+arg_18]
0x180072073  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180072078  lea     rax, qword_1800BEB28
0x18007207f  mov     [rbp+arg_18], rax
0x180072083  lock inc cs:qword_1800BEB28
0x18007208b  mov     rcx, [rbp+arg_0]
0x18007208f  xor     eax, eax
0x180072091  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18007209a  jnz     short loc_1800720B3
0x18007209c  mov     [rbp+arg_0], rsi
0x1800720a0  lea     rdx, stru_1800BEB30; ListEntry
0x1800720a7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800720ae  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800720b3  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x1800720ba  mov     rcx, rbx
0x1800720bd  mov     rax, [rdi]
0x1800720c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720c5  nop
0x1800720c6  lock dec cs:qword_1800BEB28
0x1800720ce  jmp     short loc_1800720E0
0x1800720d0  lea     rdx, [rbp+arg_0]
0x1800720d4  mov     rcx, rbx
0x1800720d7  mov     rax, [rdi]
0x1800720da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800720df  nop
0x1800720e0  cmp     [rbp+arg_0], rsi
0x1800720e4  jz      short loc_1800720EF
0x1800720e6  lea     rcx, [rbp+arg_0]
0x1800720ea  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800720ef  mov     rax, rbx
0x1800720f2  mov     rbx, [rsp+50h+arg_8]
0x1800720f7  add     rsp, 50h
0x1800720fb  pop     rdi
0x1800720fc  pop     rsi
0x1800720fd  pop     rbp
0x1800720fe  retn
```
