# ??$call@P6AXAEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@2@@Z@Z

- ea: `0x14004f91c`
- end: `0x14004fa1a`
- name: `??$call@P6AXAEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@2@@Z@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009a88`

## callees

- `0x140044a2a`
- `0x14004f91c`
- `0x14004fcd8`
- `0x140052954`
- `0x140052bf8`
- `0x14005fcbc`
- `0x140067010`

## string_xrefs

- `0x14004f931`: `WindowsUdk.ApplicationModel.AppExtensions.AppExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::call<void (*)(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        void (__fastcall **a2)(__int64 *))
{
  _QWORD v3[2]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v4[32]; // [rsp+30h] [rbp-20h] BYREF
  void (__fastcall ***v5)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v6; // [rsp+70h] [rbp+20h] BYREF

  v5 = a1;
  v3[0] = L"WindowsUdk.ApplicationModel.AppExtensions.AppExtension";
  v3[1] = 54;
  winrt::param::hstring::hstring(v4, v3);
  winrt::get_activation_factory<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>(&v5, v4);
  if ( v5 && (v6 = 0, (**v5)(v5, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v6), v6) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v6);
    v6 = &qword_1400839B8;
    _InterlockedIncrement64(&qword_1400839B8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>,
            (signed __int64)v5,
            0) )
    {
      v5 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1400839C0);
    }
    (*a2)(&winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>);
    _InterlockedDecrement64(&qword_1400839B8);
  }
  else
  {
    (*a2)((__int64 *)&v5);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v5);
}

```

## disassembly

```asm
0x14004f91c  mov     [rsp-8+arg_8], rbx
0x14004f921  mov     [rsp-8+arg_0], rcx
0x14004f926  push    rbp
0x14004f927  mov     rbp, rsp
0x14004f92a  sub     rsp, 50h
0x14004f92e  mov     rbx, rdx
0x14004f931  lea     rax, aWindowsudkAppl; "WindowsUdk.ApplicationModel.AppExtensio"...
0x14004f938  mov     [rbp+var_30], rax
0x14004f93c  mov     [rbp+var_28], 36h ; '6'
0x14004f944  lea     rdx, [rbp+var_30]
0x14004f948  lea     rcx, [rbp+var_20]
0x14004f94c  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f951  lea     rdx, [rbp+var_20]
0x14004f955  lea     rcx, [rbp+arg_0]
0x14004f959  call    ??$get_activation_factory@UIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@winrt@@YA?AUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>(winrt::param::hstring const &)
0x14004f95e  nop
0x14004f95f  mov     rcx, [rbp+arg_0]
0x14004f963  test    rcx, rcx
0x14004f966  jz      loc_14004F9F9
0x14004f96c  mov     [rbp+arg_10], 0
0x14004f974  mov     rax, [rcx]
0x14004f977  lea     r8, [rbp+arg_10]
0x14004f97b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f982  mov     rax, [rax]
0x14004f985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f98a  mov     rax, [rbp+arg_10]
0x14004f98e  mov     [rbp+arg_10], rax
0x14004f992  test    rax, rax
0x14004f995  jz      short loc_14004F9F9
0x14004f997  lea     rcx, [rbp+arg_10]
0x14004f99b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f9a0  lea     rax, qword_1400839B8
0x14004f9a7  mov     [rbp+arg_10], rax
0x14004f9ab  lock inc cs:qword_1400839B8
0x14004f9b3  mov     rcx, [rbp+arg_0]
0x14004f9b7  xor     eax, eax
0x14004f9b9  lock cmpxchg cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A, rcx; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x14004f9c2  jnz     short loc_14004F9DF
0x14004f9c4  mov     [rbp+arg_0], 0
0x14004f9cc  lea     rdx, stru_1400839C0; ListEntry
0x14004f9d3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f9da  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f9df  lea     rcx, ??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x14004f9e6  mov     rax, [rbx]
0x14004f9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f9ee  nop
0x14004f9ef  lock dec cs:qword_1400839B8
0x14004f9f7  jmp     short loc_14004FA06
0x14004f9f9  lea     rcx, [rbp+arg_0]
0x14004f9fd  mov     rax, [rbx]
0x14004fa00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fa05  nop
0x14004fa06  lea     rcx, [rbp+arg_0]; this
0x14004fa0a  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004fa0f  mov     rbx, [rsp+50h+arg_8]
0x14004fa14  add     rsp, 50h
0x14004fa18  pop     rbp
0x14004fa19  retn
```
