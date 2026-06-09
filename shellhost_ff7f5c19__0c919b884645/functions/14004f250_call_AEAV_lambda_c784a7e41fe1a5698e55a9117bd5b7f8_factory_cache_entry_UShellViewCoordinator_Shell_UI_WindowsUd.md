# ??$call@AEAV_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@@?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@@Z

- ea: `0x14004f250`
- end: `0x14004f395`
- name: `??$call@AEAV_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@@?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140058604`

## callees

- `0x140044a2a`
- `0x14004f250`
- `0x140050184`
- `0x140052954`
- `0x140052bf8`
- `0x140054394`
- `0x14005d654`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::call<_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_ &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  const wchar_t *v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _QWORD v9[4]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = a1;
  v7 = L"WindowsUdk.UI.Shell.ShellViewCoordinator";
  *(_QWORD *)&v8 = 40;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    (__int64)winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>,
    (__int64)&v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v5 = v11;
  v10 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v11);
    v11 = &qword_140083918;
    _InterlockedIncrement64(&qword_140083918);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140083920);
    }
    _lambda_c784a7e41fe1a5698e55a9117bd5b7f8_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>);
    _InterlockedDecrement64(&qword_140083918);
  }
  else
  {
    _lambda_c784a7e41fe1a5698e55a9117bd5b7f8_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v10);
  return a2;
}

```

## disassembly

```asm
0x14004f250  mov     [rsp-18h+arg_8], rbx
0x14004f255  mov     [rsp-18h+arg_0], rcx
0x14004f25a  push    rbp
0x14004f25b  push    rsi
0x14004f25c  push    rdi
0x14004f25d  mov     rbp, rsp
0x14004f260  sub     rsp, 60h
0x14004f264  mov     rsi, r8
0x14004f267  mov     rbx, rdx
0x14004f26a  lea     rax, aWindowsudkUiSh; "WindowsUdk.UI.Shell.ShellViewCoordinato"...
0x14004f271  mov     [rbp+var_38], rax
0x14004f275  mov     qword ptr [rbp+var_30], 28h ; '('
0x14004f27d  lea     rdx, [rbp+var_38]
0x14004f281  lea     rcx, [rbp+var_20]
0x14004f285  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14004f28a  mov     [rbp+arg_18], 0
0x14004f292  mov     dword ptr [rbp+var_38], 0
0x14004f299  xorps   xmm0, xmm0
0x14004f29c  movdqu  [rbp+var_30], xmm0
0x14004f2a1  lea     r9, [rbp+arg_18]
0x14004f2a5  lea     r8, ??$guid_v@UIShellViewCoordinatorFactory@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>
0x14004f2ac  lea     rdx, [rbp+var_20]
0x14004f2b0  lea     rcx, [rbp+arg_0]
0x14004f2b4  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x14004f2b9  lea     r8, [rbp+var_38]
0x14004f2bd  mov     edx, dword ptr [rbp+arg_0]
0x14004f2c0  lea     rcx, [rbp+arg_0]
0x14004f2c4  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14004f2c9  mov     rdi, [rbp+arg_18]
0x14004f2cd  mov     [rbp+arg_0], rdi
0x14004f2d1  test    rdi, rdi
0x14004f2d4  jz      loc_14004F369
0x14004f2da  mov     [rbp+arg_18], 0
0x14004f2e2  mov     rax, [rdi]
0x14004f2e5  lea     r8, [rbp+arg_18]
0x14004f2e9  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14004f2f0  mov     rcx, rdi
0x14004f2f3  mov     rax, [rax]
0x14004f2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f2fb  mov     rax, [rbp+arg_18]
0x14004f2ff  mov     [rbp+arg_18], rax
0x14004f303  test    rax, rax
0x14004f306  jz      short loc_14004F369
0x14004f308  lea     rcx, [rbp+arg_18]
0x14004f30c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004f311  lea     rax, qword_140083918
0x14004f318  mov     [rbp+arg_18], rax
0x14004f31c  lock inc cs:qword_140083918
0x14004f324  xor     eax, eax
0x14004f326  lock cmpxchg cs:??$factory_cache_entry_v@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@12@A, rdi; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>
0x14004f32f  jnz     short loc_14004F34C
0x14004f331  mov     [rbp+arg_0], 0
0x14004f339  lea     rdx, stru_140083920; ListEntry
0x14004f340  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14004f347  call    WINRT_IMPL_InterlockedPushEntrySList
0x14004f34c  lea     r8, ??$factory_cache_entry_v@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UShellViewCoordinator@Shell@UI@WindowsUdk@winrt@@UIShellViewCoordinatorFactory@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>::winrt::factory_cache_entry<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::UI::Shell::ShellViewCoordinator,winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory>
0x14004f353  mov     rdx, rbx
0x14004f356  mov     rcx, rsi
0x14004f359  call    ??R_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@QEBA@AEBUIShellViewCoordinatorFactory@Shell@UI@WindowsUdk@winrt@@@Z; _lambda_c784a7e41fe1a5698e55a9117bd5b7f8_::operator()(winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory const &)
0x14004f35e  nop
0x14004f35f  lock dec cs:qword_140083918
0x14004f367  jmp     short loc_14004F379
0x14004f369  lea     r8, [rbp+arg_0]
0x14004f36d  mov     rdx, rbx
0x14004f370  mov     rcx, rsi
0x14004f373  call    ??R_lambda_c784a7e41fe1a5698e55a9117bd5b7f8_@@QEBA@AEBUIShellViewCoordinatorFactory@Shell@UI@WindowsUdk@winrt@@@Z; _lambda_c784a7e41fe1a5698e55a9117bd5b7f8_::operator()(winrt::WindowsUdk::UI::Shell::IShellViewCoordinatorFactory const &)
0x14004f378  nop
0x14004f379  lea     rcx, [rbp+arg_0]; this
0x14004f37d  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004f382  mov     rax, rbx
0x14004f385  mov     rbx, [rsp+60h+arg_8]
0x14004f38d  add     rsp, 60h
0x14004f391  pop     rdi
0x14004f392  pop     rsi
0x14004f393  pop     rbp
0x14004f394  retn
```
