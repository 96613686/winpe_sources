# ??$call@P6A?AUShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@AEBUIActivationFactory@Foundation@Windows@5@@Z@?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@QEAA?A_P$$QEAP6A?AUShowShellViewOptions@Shell@UI@WindowsUdk@2@AEBUIActivationFactory@Foundation@Windows@2@@Z@Z

- ea: `0x14004f6e4`
- end: `0x14004f7fa`
- name: `??$call@P6A?AUShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@AEBUIActivationFactory@Foundation@Windows@5@@Z@?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@QEAA?A_P$$QEAP6A?AUShowShellViewOptions@Shell@UI@WindowsUdk@2@AEBUIActivationFactory@Foundation@Windows@2@@Z@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140058604`

## callees

- `0x140044a2a`
- `0x14004f6e4`
- `0x14004fc78`
- `0x140052954`
- `0x140052bf8`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"WindowsUdk.UI.Shell.ShowShellViewOptions";
  v6[1] = 40;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_140083938;
    _InterlockedIncrement64(&qword_140083938);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140083940);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_140083938);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v8);
  return a2;
}

```

## disassembly

```asm
0x14004f6e4  mov     [rsp-8+arg_8], rbx
0x14004f6e9  mov     [rsp-8+arg_10], rdi
0x14004f6ee  mov     [rsp-8+arg_0], rcx
0x14004f6f3  push    rbp
0x14004f6f4  mov     rbp, rsp
0x14004f6f7  sub     rsp, 60h
0x14004f6fb  mov     rdi, r8
0x14004f6fe  mov     rbx, rdx
0x14004f701  lea     rax, aWindowsudkUiSh_0; "WindowsUdk.UI.Shell.ShowShellViewOption"...
0x14004f708  mov     [rbp+var_38], rax
0x14004f70c  mov     [rbp+var_30], 28h ; '('
0x14004f714  lea     rdx, [rbp+var_38]
0x14004f718  lea     rcx, [rbp+var_28]
0x14004f71c  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f721  lea     rdx, [rbp+var_28]
0x14004f725  lea     rcx, [rbp+arg_0]
0x14004f729  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x14004f72e  nop
0x14004f72f  mov     rcx, [rbp+arg_0]
0x14004f733  test    rcx, rcx
0x14004f736  jz      loc_14004F7CC
0x14004f73c  mov     [rbp+arg_18], 0
0x14004f744  mov     rax, [rcx]
0x14004f747  lea     r8, [rbp+arg_18]
0x14004f74b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f752  mov     rax, [rax]
0x14004f755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f75a  mov     rax, [rbp+arg_18]
0x14004f75e  mov     [rbp+arg_18], rax
0x14004f762  test    rax, rax
0x14004f765  jz      short loc_14004F7CC
0x14004f767  lea     rcx, [rbp+arg_18]
0x14004f76b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f770  lea     rax, qword_140083938
0x14004f777  mov     [rbp+arg_18], rax
0x14004f77b  lock inc cs:qword_140083938
0x14004f783  mov     rcx, [rbp+arg_0]
0x14004f787  xor     eax, eax
0x14004f789  lock cmpxchg cs:??$factory_cache_entry_v@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@3U?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@12@A, rcx; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>
0x14004f792  jnz     short loc_14004F7AF
0x14004f794  mov     [rbp+arg_0], 0
0x14004f79c  lea     rdx, stru_140083940; ListEntry
0x14004f7a3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f7aa  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f7af  lea     rdx, ??$factory_cache_entry_v@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@impl@winrt@@3U?$factory_cache_entry@UShowShellViewOptions@Shell@UI@WindowsUdk@winrt@@UIActivationFactory@Foundation@Windows@5@@12@A; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShowShellViewOptions,winrt::Windows::Foundation::IActivationFactory>
0x14004f7b6  mov     rcx, rbx
0x14004f7b9  mov     rax, [rdi]
0x14004f7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f7c1  nop
0x14004f7c2  lock dec cs:qword_140083938
0x14004f7ca  jmp     short loc_14004F7DC
0x14004f7cc  lea     rdx, [rbp+arg_0]
0x14004f7d0  mov     rcx, rbx
0x14004f7d3  mov     rax, [rdi]
0x14004f7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f7db  nop
0x14004f7dc  lea     rcx, [rbp+arg_0]; this
0x14004f7e0  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f7e5  mov     rax, rbx
0x14004f7e8  lea     r11, [rsp+60h+var_s0]
0x14004f7ed  mov     rbx, [r11+18h]
0x14004f7f1  mov     rdi, [r11+20h]
0x14004f7f5  mov     rsp, r11
0x14004f7f8  pop     rbp
0x14004f7f9  retn
```
