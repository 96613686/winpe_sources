# ??$call@P6A?AU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@34@@Z@?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@2@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@52@@Z@Z

- ea: `0x14001e66c`
- end: `0x14001e7b8`
- name: `??$call@P6A?AU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@34@@Z@?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@2@AEBUIUISettingsControllerStatics@Core@ViewManagement@UI@52@@Z@Z`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400206e8`

## callees

- `0x140003539`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14000f914`
- `0x14001e66c`
- `0x14001e86c`
- `0x14001f304`
- `0x140029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController> (*)(winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+38h] [rbp-38h] BYREF
  __int128 v8; // [rsp+40h] [rbp-30h]
  _QWORD v9[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+10h] BYREF
  signed __int64 v11; // [rsp+98h] [rbp+28h] BYREF

  v10 = a1;
  v6[0] = L"Windows.UI.ViewManagement.Core.UISettingsController";
  v6[1] = 51;
  winrt::param::hstring::hstring(v9, v6);
  v6[0] = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    (__int64)winrt::impl::guid_v<winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>,
    (__int64)v6);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v11 = v6[0];
  if ( v6[0]
    && (v10 = 0,
        (**(void (__fastcall ***)(_QWORD, __int64 *, __int64 **))v6[0])(
          v6[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v10),
        v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v10);
    v10 = &qword_140047378;
    _InterlockedIncrement64(&qword_140047378);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>,
            v11,
            0) )
    {
      v11 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>);
    _InterlockedDecrement64(&qword_140047378);
  }
  else
  {
    (*a3)(a2, &v11);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
  return a2;
}

```

## disassembly

```asm
0x14001e66c  mov     [rsp-8+arg_8], rbx
0x14001e671  mov     [rsp-8+arg_10], rdi
0x14001e676  mov     [rsp-8+arg_0], rcx
0x14001e67b  push    rbp
0x14001e67c  mov     rbp, rsp
0x14001e67f  sub     rsp, 70h
0x14001e683  mov     rdi, r8
0x14001e686  mov     rbx, rdx
0x14001e689  lea     rax, aWindowsUiViewm; "Windows.UI.ViewManagement.Core.UISettin"...
0x14001e690  mov     [rbp+var_48], rax
0x14001e694  mov     [rbp+var_40], 33h ; '3'
0x14001e69c  lea     rdx, [rbp+var_48]
0x14001e6a0  lea     rcx, [rbp+var_20]
0x14001e6a4  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14001e6a9  mov     [rbp+var_48], 0
0x14001e6b1  mov     [rbp+var_38], 0
0x14001e6b8  xorps   xmm0, xmm0
0x14001e6bb  movdqu  [rbp+var_30], xmm0
0x14001e6c0  lea     r9, [rbp+var_48]
0x14001e6c4  lea     r8, ??$guid_v@UIUISettingsControllerStatics@Core@ViewManagement@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>
0x14001e6cb  lea     rdx, [rbp+var_20]
0x14001e6cf  lea     rcx, [rbp+arg_0]
0x14001e6d3  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x14001e6d8  lea     r8, [rbp+var_38]
0x14001e6dc  mov     edx, dword ptr [rbp+arg_0]
0x14001e6df  lea     rcx, [rbp+arg_0]
0x14001e6e3  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14001e6e8  mov     rcx, [rbp+var_48]
0x14001e6ec  mov     [rbp+arg_18], rcx
0x14001e6f0  test    rcx, rcx
0x14001e6f3  jz      loc_14001E789
0x14001e6f9  mov     [rbp+arg_0], 0
0x14001e701  mov     rax, [rcx]
0x14001e704  lea     r8, [rbp+arg_0]
0x14001e708  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14001e70f  mov     rax, [rax]
0x14001e712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e717  mov     rax, [rbp+arg_0]
0x14001e71b  mov     [rbp+arg_0], rax
0x14001e71f  test    rax, rax
0x14001e722  jz      short loc_14001E789
0x14001e724  lea     rcx, [rbp+arg_0]
0x14001e728  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001e72d  lea     rax, qword_140047378
0x14001e734  mov     [rbp+arg_0], rax
0x14001e738  lock inc cs:qword_140047378
0x14001e740  mov     rcx, [rbp+arg_18]
0x14001e744  xor     eax, eax
0x14001e746  lock cmpxchg cs:??$factory_cache_entry_v@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>
0x14001e74f  jnz     short loc_14001E76C
0x14001e751  mov     [rbp+arg_18], 0
0x14001e759  lea     rdx, ListEntry; ListEntry
0x14001e760  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14001e767  call    WINRT_IMPL_InterlockedPushEntrySList
0x14001e76c  lea     rdx, ??$factory_cache_entry_v@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@UIUISettingsControllerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::ViewManagement::Core::UISettingsController,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>
0x14001e773  mov     rcx, rbx
0x14001e776  mov     rax, [rdi]
0x14001e779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e77e  nop
0x14001e77f  lock dec cs:qword_140047378
0x14001e787  jmp     short loc_14001E799
0x14001e789  lea     rdx, [rbp+arg_18]
0x14001e78d  mov     rcx, rbx
0x14001e790  mov     rax, [rdi]
0x14001e793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e798  nop
0x14001e799  lea     rcx, [rbp+arg_18]
0x14001e79d  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14001e7a2  mov     rax, rbx
0x14001e7a5  lea     r11, [rsp+70h+var_s0]
0x14001e7aa  mov     rbx, [r11+18h]
0x14001e7ae  mov     rdi, [r11+20h]
0x14001e7b2  mov     rsp, r11
0x14001e7b5  pop     rbp
0x14001e7b6  retn
```
