# ??$call@AEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@Z

- ea: `0x14004f138`
- end: `0x14004f248`
- name: `??$call@AEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005b8bc`

## callees

- `0x140044a2a`
- `0x14004f138`
- `0x14004fcd8`
- `0x140052954`
- `0x140052bf8`
- `0x140053eb8`
- `0x14005fcbc`
- `0x140067010`

## string_xrefs

- `0x14004f152`: `WindowsUdk.ApplicationModel.AppExtensions.AppExtension`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::call<_lambda_57b55f0f887558b5f7921754fb17175c_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"WindowsUdk.ApplicationModel.AppExtensions.AppExtension";
  v7[1] = 54;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v10);
    v10 = &qword_1400839B8;
    _InterlockedIncrement64(&qword_1400839B8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1400839C0);
    }
    _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>);
    _InterlockedDecrement64(&qword_1400839B8);
  }
  else
  {
    _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  return a2;
}

```

## disassembly

```asm
0x14004f138  mov     [rsp-18h+arg_8], rbx
0x14004f13d  mov     [rsp-18h+arg_0], rcx
0x14004f142  push    rbp
0x14004f143  push    rsi
0x14004f144  push    rdi
0x14004f145  mov     rbp, rsp
0x14004f148  sub     rsp, 60h
0x14004f14c  mov     rsi, r8
0x14004f14f  mov     rbx, rdx
0x14004f152  lea     rax, aWindowsudkAppl; "WindowsUdk.ApplicationModel.AppExtensio"...
0x14004f159  mov     [rbp+var_38], rax
0x14004f15d  mov     [rbp+var_30], 36h ; '6'
0x14004f165  lea     rdx, [rbp+var_38]
0x14004f169  lea     rcx, [rbp+var_28]
0x14004f16d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f172  lea     rdx, [rbp+var_28]
0x14004f176  lea     rcx, [rbp+arg_0]
0x14004f17a  call    ??$get_activation_factory@UIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@winrt@@YA?AUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>(winrt::param::hstring const &)
0x14004f17f  nop
0x14004f180  mov     rdi, [rbp+arg_0]
0x14004f184  test    rdi, rdi
0x14004f187  jz      loc_14004F21C
0x14004f18d  mov     [rbp+arg_18], 0
0x14004f195  mov     rax, [rdi]
0x14004f198  lea     r8, [rbp+arg_18]
0x14004f19c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f1a3  mov     rcx, rdi
0x14004f1a6  mov     rax, [rax]
0x14004f1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1ae  mov     rax, [rbp+arg_18]
0x14004f1b2  mov     [rbp+arg_18], rax
0x14004f1b6  test    rax, rax
0x14004f1b9  jz      short loc_14004F21C
0x14004f1bb  lea     rcx, [rbp+arg_18]
0x14004f1bf  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f1c4  lea     rax, qword_1400839B8
0x14004f1cb  mov     [rbp+arg_18], rax
0x14004f1cf  lock inc cs:qword_1400839B8
0x14004f1d7  xor     eax, eax
0x14004f1d9  lock cmpxchg cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A, rdi; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x14004f1e2  jnz     short loc_14004F1FF
0x14004f1e4  mov     [rbp+arg_0], 0
0x14004f1ec  lea     rdx, stru_1400839C0; ListEntry
0x14004f1f3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f1fa  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f1ff  lea     r8, ??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x14004f206  mov     rdx, rbx
0x14004f209  mov     rcx, rsi
0x14004f20c  call    ??R_lambda_57b55f0f887558b5f7921754fb17175c_@@QEBA@AEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &)
0x14004f211  nop
0x14004f212  lock dec cs:qword_1400839B8
0x14004f21a  jmp     short loc_14004F22C
0x14004f21c  lea     r8, [rbp+arg_0]
0x14004f220  mov     rdx, rbx
0x14004f223  mov     rcx, rsi
0x14004f226  call    ??R_lambda_57b55f0f887558b5f7921754fb17175c_@@QEBA@AEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &)
0x14004f22b  nop
0x14004f22c  lea     rcx, [rbp+arg_0]; this
0x14004f230  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f235  mov     rax, rbx
0x14004f238  mov     rbx, [rsp+60h+arg_8]
0x14004f240  add     rsp, 60h
0x14004f244  pop     rdi
0x14004f245  pop     rsi
0x14004f246  pop     rbp
0x14004f247  retn
```
