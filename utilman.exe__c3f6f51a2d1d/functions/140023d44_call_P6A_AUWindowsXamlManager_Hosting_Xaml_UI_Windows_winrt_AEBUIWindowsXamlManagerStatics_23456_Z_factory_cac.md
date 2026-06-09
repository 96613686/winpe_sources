# ??$call@P6A?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@AEBUIWindowsXamlManagerStatics@23456@@Z@?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@2@AEBUIWindowsXamlManagerStatics@45672@@Z@Z

- ea: `0x140023d44`
- end: `0x140023e5b`
- name: `??$call@P6A?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@AEBUIWindowsXamlManagerStatics@23456@@Z@?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUWindowsXamlManager@Hosting@Xaml@UI@Windows@2@AEBUIWindowsXamlManagerStatics@45672@@Z@Z`
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
- `0x140023d44`
- `0x140023fa8`
- `0x140029010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>::call<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager (*)(winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.UI.Xaml.Hosting.WindowsXamlManager";
  v6[1] = 42;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_1400470F8;
    _InterlockedIncrement64(&qword_1400470F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140047100);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>);
    _InterlockedDecrement64(&qword_1400470F8);
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
0x140023d44  mov     [rsp-8+arg_8], rbx
0x140023d49  mov     [rsp-8+arg_10], rdi
0x140023d4e  mov     [rsp-8+arg_0], rcx
0x140023d53  push    rbp
0x140023d54  mov     rbp, rsp
0x140023d57  sub     rsp, 60h
0x140023d5b  mov     rdi, r8
0x140023d5e  mov     rbx, rdx
0x140023d61  lea     rax, aWindowsUiXamlH_1; "Windows.UI.Xaml.Hosting.WindowsXamlMana"...
0x140023d68  mov     [rbp+var_38], rax
0x140023d6c  mov     [rbp+var_30], 2Ah ; '*'
0x140023d74  lea     rdx, [rbp+var_38]
0x140023d78  lea     rcx, [rbp+var_28]
0x140023d7c  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x140023d81  lea     rdx, [rbp+var_28]
0x140023d85  lea     rcx, [rbp+arg_0]
0x140023d89  call    ??$get_activation_factory@UIWindowsXamlManagerStatics@Hosting@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIWindowsXamlManagerStatics@Hosting@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>(winrt::param::hstring const &)
0x140023d8e  nop
0x140023d8f  mov     rcx, [rbp+arg_0]
0x140023d93  test    rcx, rcx
0x140023d96  jz      loc_140023E2C
0x140023d9c  mov     [rbp+arg_18], 0
0x140023da4  mov     rax, [rcx]
0x140023da7  lea     r8, [rbp+arg_18]
0x140023dab  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140023db2  mov     rax, [rax]
0x140023db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023dba  mov     rax, [rbp+arg_18]
0x140023dbe  mov     [rbp+arg_18], rax
0x140023dc2  test    rax, rax
0x140023dc5  jz      short loc_140023E2C
0x140023dc7  lea     rcx, [rbp+arg_18]
0x140023dcb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140023dd0  lea     rax, qword_1400470F8
0x140023dd7  mov     [rbp+arg_18], rax
0x140023ddb  lock inc cs:qword_1400470F8
0x140023de3  mov     rcx, [rbp+arg_0]
0x140023de7  xor     eax, eax
0x140023de9  lock cmpxchg cs:??$factory_cache_entry_v@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>
0x140023df2  jnz     short loc_140023E0F
0x140023df4  mov     [rbp+arg_0], 0
0x140023dfc  lea     rdx, stru_140047100; ListEntry
0x140023e03  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x140023e0a  call    WINRT_IMPL_InterlockedPushEntrySList
0x140023e0f  lea     rdx, ??$factory_cache_entry_v@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UWindowsXamlManager@Hosting@Xaml@UI@Windows@winrt@@UIWindowsXamlManagerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Hosting::WindowsXamlManager,winrt::Windows::UI::Xaml::Hosting::IWindowsXamlManagerStatics>
0x140023e16  mov     rcx, rbx
0x140023e19  mov     rax, [rdi]
0x140023e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023e21  nop
0x140023e22  lock dec cs:qword_1400470F8
0x140023e2a  jmp     short loc_140023E3C
0x140023e2c  lea     rdx, [rbp+arg_0]
0x140023e30  mov     rcx, rbx
0x140023e33  mov     rax, [rdi]
0x140023e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023e3b  nop
0x140023e3c  lea     rcx, [rbp+arg_0]
0x140023e40  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140023e45  mov     rax, rbx
0x140023e48  lea     r11, [rsp+60h+var_s0]
0x140023e4d  mov     rbx, [r11+18h]
0x140023e51  mov     rdi, [r11+20h]
0x140023e55  mov     rsp, r11
0x140023e58  pop     rbp
0x140023e59  retn
```
