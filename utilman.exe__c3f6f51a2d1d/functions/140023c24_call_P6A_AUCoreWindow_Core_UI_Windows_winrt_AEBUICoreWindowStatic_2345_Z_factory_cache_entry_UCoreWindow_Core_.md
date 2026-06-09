# ??$call@P6A?AUCoreWindow@Core@UI@Windows@winrt@@AEBUICoreWindowStatic@2345@@Z@?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUCoreWindow@Core@UI@Windows@2@AEBUICoreWindowStatic@4562@@Z@Z

- ea: `0x140023c24`
- end: `0x140023d3b`
- name: `??$call@P6A?AUCoreWindow@Core@UI@Windows@winrt@@AEBUICoreWindowStatic@2345@@Z@?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUCoreWindow@Core@UI@Windows@2@AEBUICoreWindowStatic@4562@@Z@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140024aa8`

## callees

- `0x140003539`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14001f304`
- `0x140023c24`
- `0x140023e7c`
- `0x140029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::call<winrt::Windows::UI::Core::CoreWindow (*)(winrt::Windows::UI::Core::ICoreWindowStatic const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.UI.Core.CoreWindow";
  v6[1] = 26;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::UI::Core::ICoreWindowStatic>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_140047118;
    _InterlockedIncrement64(&qword_140047118);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140047120);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>);
    _InterlockedDecrement64(&qword_140047118);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v8);
  return a2;
}

```

## disassembly

```asm
0x140023c24  mov     [rsp-8+arg_8], rbx
0x140023c29  mov     [rsp-8+arg_10], rdi
0x140023c2e  mov     [rsp-8+arg_0], rcx
0x140023c33  push    rbp
0x140023c34  mov     rbp, rsp
0x140023c37  sub     rsp, 60h
0x140023c3b  mov     rdi, r8
0x140023c3e  mov     rbx, rdx
0x140023c41  lea     rax, aWindowsUiCoreC; "Windows.UI.Core.CoreWindow"
0x140023c48  mov     [rbp+var_38], rax
0x140023c4c  mov     [rbp+var_30], 1Ah
0x140023c54  lea     rdx, [rbp+var_38]
0x140023c58  lea     rcx, [rbp+var_28]
0x140023c5c  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x140023c61  lea     rdx, [rbp+var_28]
0x140023c65  lea     rcx, [rbp+arg_0]
0x140023c69  call    ??$get_activation_factory@UICoreWindowStatic@Core@UI@Windows@winrt@@@winrt@@YA?AUICoreWindowStatic@Core@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Core::ICoreWindowStatic>(winrt::param::hstring const &)
0x140023c6e  nop
0x140023c6f  mov     rcx, [rbp+arg_0]
0x140023c73  test    rcx, rcx
0x140023c76  jz      loc_140023D0C
0x140023c7c  mov     [rbp+arg_18], 0
0x140023c84  mov     rax, [rcx]
0x140023c87  lea     r8, [rbp+arg_18]
0x140023c8b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140023c92  mov     rax, [rax]
0x140023c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023c9a  mov     rax, [rbp+arg_18]
0x140023c9e  mov     [rbp+arg_18], rax
0x140023ca2  test    rax, rax
0x140023ca5  jz      short loc_140023D0C
0x140023ca7  lea     rcx, [rbp+arg_18]
0x140023cab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140023cb0  lea     rax, qword_140047118
0x140023cb7  mov     [rbp+arg_18], rax
0x140023cbb  lock inc cs:qword_140047118
0x140023cc3  mov     rcx, [rbp+arg_0]
0x140023cc7  xor     eax, eax
0x140023cc9  lock cmpxchg cs:??$factory_cache_entry_v@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::winrt::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>
0x140023cd2  jnz     short loc_140023CEF
0x140023cd4  mov     [rbp+arg_0], 0
0x140023cdc  lea     rdx, stru_140047120; ListEntry
0x140023ce3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140023cea  call    WINRT_IMPL_InterlockedPushEntrySList
0x140023cef  lea     rdx, ??$factory_cache_entry_v@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@impl@winrt@@3U?$factory_cache_entry@UCoreWindow@Core@UI@Windows@winrt@@UICoreWindowStatic@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>::winrt::factory_cache_entry<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Core::CoreWindow,winrt::Windows::UI::Core::ICoreWindowStatic>
0x140023cf6  mov     rcx, rbx
0x140023cf9  mov     rax, [rdi]
0x140023cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023d01  nop
0x140023d02  lock dec cs:qword_140047118
0x140023d0a  jmp     short loc_140023D1C
0x140023d0c  lea     rdx, [rbp+arg_0]
0x140023d10  mov     rcx, rbx
0x140023d13  mov     rax, [rdi]
0x140023d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023d1b  nop
0x140023d1c  lea     rcx, [rbp+arg_0]
0x140023d20  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140023d25  mov     rax, rbx
0x140023d28  lea     r11, [rsp+60h+var_s0]
0x140023d2d  mov     rbx, [r11+18h]
0x140023d31  mov     rdi, [r11+20h]
0x140023d35  mov     rsp, r11
0x140023d38  pop     rbp
0x140023d39  retn
```
