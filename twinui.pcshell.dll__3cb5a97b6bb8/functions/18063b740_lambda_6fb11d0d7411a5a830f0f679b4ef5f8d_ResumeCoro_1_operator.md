# _lambda_6fb11d0d7411a5a830f0f679b4ef5f8d_$_ResumeCoro$1::operator()

- ea: `0x18063b740`
- end: `0x18063bbcc`
- name: `_lambda_6fb11d0d7411a5a830f0f679b4ef5f8d_$_ResumeCoro$1::operator()`
- size: `1164`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18063bbf0`

## callees

- `0x18001b3d4`
- `0x18002d810`
- `0x180066030`
- `0x1800d55f0`
- `0x1800d7c50`
- `0x180163aa8`
- `0x18026bb3c`
- `0x1802882f8`
- `0x18033d960`
- `0x180356760`
- `0x1803aab6c`
- `0x1803b4a60`
- `0x1803bc514`
- `0x1803c55ec`
- `0x1803d1b7c`
- `0x180639e64`
- `0x18063a284`
- `0x18063b378`
- `0x18063b554`
- `0x18063b5b4`
- `0x18063b740`
- `0x18063e524`
- `0x18063f678`
- `0x180649c84`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18063bb30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18063bb30`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18063baaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18063baaa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18063b84d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18063b84d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063b8c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063b95d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063b8c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18063b95d`
- `ext-ms-win-ntuser-misc-l1-1-0!ExitWindowsEx` at `0x18063bb53`
- `ext-ms-win-ntuser-misc-l1-1-0!ExitWindowsEx` at `0x18063bb53`

## string_xrefs

- `0x18063b8bc`: `PhysicalDeviceAccessConfigured`
- `0x18063b83f`: `Software\Microsoft\Windows\BootToCloud\PhysicalDeviceAccess`
- `0x18063b956`: `SignOutConfiguredForPhysicalDeviceAccess`
- `0x18063baa3`: `SignOutConfiguredForPhysicalDeviceAccess`
- `0x18063b8da`: `pcshell\twinui\cloudpc\lib\cloudpccomponent.cpp`
- `0x18063b972`: `pcshell\twinui\cloudpc\lib\cloudpccomponent.cpp`
- `0x18063bac1`: `pcshell\twinui\cloudpc\lib\cloudpccomponent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall lambda_6fb11d0d7411a5a830f0f679b4ef5f8d___ResumeCoro_1::operator()(__int64 a1)
{
  __int64 v2; // r15
  HKEY *v3; // r14
  winrt::hstring *CorrelationId; // rax
  __int64 v5; // rdx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-D8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-D8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-D8h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_28;
    case 2:
      if ( CloudPCHelpers::IsPhysicalDeviceAccessConfigured((CloudPCHelpers *)a1) )
        goto LABEL_28;
      *(_QWORD *)(a1 + 208) = 0;
      v2 = a1 + 16;
      tip2::tip_test<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::start_and_watch_errors(
        a1 + 208,
        a1 + 16);
      wil::com_ptr_t<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>,wil::err_returncode_policy>(a1 + 208);
      *(_DWORD *)(a1 + 80) = 1;
      v3 = (HKEY *)(a1 + 88);
      *(_QWORD *)(a1 + 88) = 0;
      CorrelationId = (winrt::hstring *)winrt::Windows::Internal::Shell::implementation::RemoteSystemDataModel::GetCorrelationId(
                                          a1 + 104,
                                          &c_bootSystemId);
      *(_QWORD *)(a1 + 96) = winrt::hstring::c_str(CorrelationId);
      CloudPCTelemetryCore::AccessPhysicalDeviceTriggered<unsigned short const *>(a1 + 96);
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 104);
      winrt::Windows::Internal::Shell::implementation::RemoteSystemDataModel::SetPhysicalDeviceAccessState();
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                            a1 + 88,
                            v5);
      Key = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\BootToCloud\\PhysicalDeviceAccess",
              0,
              0,
              0,
              0x20006u,
              0,
              phkResult,
              0);
      v8 = retaddr;
      if ( Key )
      {
        v9 = 350;
LABEL_9:
        wil::details::in1diag3::_Log_Win32(
          v8,
          (void *)v9,
          (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\cloudpccomponent.cpp",
          (const char *)Key,
          dwOptionsa);
        goto LABEL_23;
      }
      v10 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 112) = v10;
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 280));
      tip2::details::shared_data<1,0,0>::begin_update(v10 + 8);
      *(_BYTE *)(v10 + 272) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(a1 + 112);
      Key = RegSetValueExW(*v3, L"PhysicalDeviceAccessConfigured", 0, 4u, (const BYTE *)(a1 + 80), 4u);
      v8 = retaddr;
      if ( Key )
      {
        v9 = 353;
        goto LABEL_9;
      }
      v11 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 120) = v11;
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 280));
      tip2::details::shared_data<1,0,0>::begin_update(v11 + 8);
      *(_BYTE *)(v11 + 273) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(a1 + 120);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FSOE>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FSOE>::GetImpl'::`2'::impl) )
      {
        v12 = RegSetValueExW(*v3, L"SignOutConfiguredForPhysicalDeviceAccess", 0, 4u, (const BYTE *)(a1 + 80), 4u);
        if ( v12 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x167,
            (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\cloudpccomponent.cpp",
            (const char *)v12,
            dwOptionsb);
        *(_BYTE *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = v2;
        *(_QWORD *)(a1 + 144) = a1 + 128;
        *(_BYTE *)(a1 + 152) = 0;
        *(_DWORD *)(a1 + 153) = 0;
        *(_WORD *)(a1 + 157) = 0;
        *(_BYTE *)(a1 + 159) = 0;
        *(_QWORD *)(a1 + 160) = a1;
        *(_WORD *)(a1 + 8) = 4;
        wil::details::coro::coroutine_withsuspend_awaiter_tip2::test_watcher_tip2::details::merged_data__tip_SetPhysicalDeviceAccessRegKeyTipTest__tip_SetPhysicalDeviceAccessRegKeyTipTest_____winrt::resume_background_::_2_::awaitable____::await_suspend_std::experimental::coroutine_handle_std::experimental::coroutine_traits_winrt::fire_and_forget__lambda_6fb11d0d7411a5a830f0f679b4ef5f8d__const___::promise_type___();
      }
      else
      {
LABEL_23:
        tip2::details::shared_data<1,0,0>::complete_without_lock(*(_QWORD *)(a1 + 72) + 8LL);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v3);
        tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(v2);
LABEL_28:
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)a1);
      }
      return;
    case 4:
      if ( *(_BYTE *)(a1 + 152) )
        wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(*(_QWORD *)(a1 + 136) + 8LL));
      *(_QWORD *)(a1 + 168) = 0;
      *(_QWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = 40000000;
      *(_QWORD *)(a1 + 192) = 0;
      *(_DWORD *)(a1 + 200) = 0;
      *(_WORD *)(a1 + 8) = 6;
      winrt::impl::timespan_awaiter::await_suspend<std::experimental::coroutine_traits<winrt::fire_and_forget,winrt::Windows::Internal::Shell::implementation::WindowTabHost *,unsigned __int64>::promise_type>(
        a1 + 168,
        a1);
      return;
    case 5:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a1 + 88);
      tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(a1 + 16);
      goto LABEL_28;
    case 6:
      winrt::impl::timespan_awaiter::await_resume((winrt::impl::timespan_awaiter *)(a1 + 168));
      winrt::impl::timespan_awaiter::~timespan_awaiter((winrt::impl::timespan_awaiter *)(a1 + 168));
      v3 = (HKEY *)(a1 + 88);
      v13 = RegDeleteValueW(*(HKEY *)(a1 + 88), L"SignOutConfiguredForPhysicalDeviceAccess");
      if ( v13 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x16A,
          (unsigned int)"pcshell\\twinui\\cloudpc\\lib\\cloudpccomponent.cpp",
          (const char *)v13,
          dwOptions);
        v2 = a1 + 16;
        goto LABEL_23;
      }
      tip2::details::shared_data<1,0,0>::complete_without_lock(*(_QWORD *)(a1 + 72) + 8LL);
      ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
      if ( `TestControlReporting'::`2'::s_pfnTestControlReporting
        || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
            ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestControlReporting"),
            (`TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress) != 0) )
      {
        ((void (__fastcall *)(_QWORD))ProcAddress)(0);
      }
      ExitWindowsEx(4u, 0x80000000);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a1 + 88);
      tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(a1 + 16);
      goto LABEL_28;
    case 7:
      winrt::impl::timespan_awaiter::~timespan_awaiter((winrt::impl::timespan_awaiter *)(a1 + 168));
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a1 + 88);
      tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(a1 + 16);
      goto LABEL_28;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18063b740  mov     [rsp+arg_10], rbx
0x18063b745  mov     [rsp+arg_18], rsi
0x18063b74a  mov     [rsp+Block], rcx
0x18063b74f  push    rdi
0x18063b750  push    r12
0x18063b752  push    r13
0x18063b754  push    r14
0x18063b756  push    r15
0x18063b758  sub     rsp, 0D0h
0x18063b75f  mov     rdi, [rsp+0F8h+Block]
0x18063b767  movzx   eax, word ptr [rdi+8]
0x18063b76b  mov     [rsp+0F8h+var_A8], ax
0x18063b770  mov     r14d, 1
0x18063b776  add     ax, r14w
0x18063b77a  cmp     ax, 8; switch 9 cases
0x18063b77e  ja      def_18063B799; jumptable 000000018063B799 default case, cases 1,2
0x18063b784  movsx   rax, ax
0x18063b788  lea     rdx, __ImageBase
0x18063b78f  mov     ecx, ds:(jpt_18063B799 - 180000000h)[rdx+rax*4]
0x18063b796  add     rcx, rdx; this
0x18063b799  jmp     rcx; switch jump
0x18063b79b  xor     esi, esi; jumptable 000000018063B799 case 4
0x18063b79d  jmp     loc_18063BB6D
0x18063b7a2  call    ?IsPhysicalDeviceAccessConfigured@CloudPCHelpers@@YA_NXZ; jumptable 000000018063B799 case 3
0x18063b7a7  xor     esi, esi
0x18063b7a9  test    al, al
0x18063b7ab  jz      short loc_18063B7B2
0x18063b7ad  jmp     loc_18063BB6D
0x18063b7b2  lea     rbx, [rdi+0D0h]
0x18063b7b9  mov     [rbx], rsi
0x18063b7bc  lea     r15, [rdi+10h]
0x18063b7c0  mov     rdx, r15
0x18063b7c3  mov     rcx, rbx
0x18063b7c6  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::start_and_watch_errors(void)
0x18063b7cb  mov     rcx, rbx
0x18063b7ce  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>,wil::err_returncode_policy>(void)
0x18063b7d3  nop
0x18063b7d4  lea     r13, [rdi+50h]
0x18063b7d8  mov     [r13+0], r14d
0x18063b7dc  lea     r14, [rdi+58h]
0x18063b7e0  mov     [r14], rsi
0x18063b7e3  lea     rdx, ?c_bootSystemId@@3Uhstring@winrt@@B; winrt::hstring const c_bootSystemId
0x18063b7ea  lea     rcx, [rdi+68h]
0x18063b7ee  call    ?GetCorrelationId@RemoteSystemDataModel@implementation@Shell@Internal@Windows@winrt@@SA?AUhstring@6@AEBU76@@Z; winrt::Windows::Internal::Shell::implementation::RemoteSystemDataModel::GetCorrelationId(winrt::hstring const &)
0x18063b7f3  mov     rcx, rax; this
0x18063b7f6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18063b7fb  mov     [rdi+60h], rax
0x18063b7ff  lea     rcx, [rdi+60h]
0x18063b803  call    ??$AccessPhysicalDeviceTriggered@PEBG@CloudPCTelemetryCore@@SAX$$QEAPEBG@Z; CloudPCTelemetryCore::AccessPhysicalDeviceTriggered<ushort const *>(ushort const * &&)
0x18063b808  lea     rcx, [rdi+68h]
0x18063b80c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18063b811  call    ?SetPhysicalDeviceAccessState@RemoteSystemDataModel@implementation@Shell@Internal@Windows@winrt@@SAXXZ; winrt::Windows::Internal::Shell::implementation::RemoteSystemDataModel::SetPhysicalDeviceAccessState(void)
0x18063b816  mov     rcx, r14
0x18063b819  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18063b81e  mov     [rsp+0F8h+lpdwDisposition], rsi; lpdwDisposition
0x18063b823  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18063b828  mov     [rsp+0F8h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18063b82d  mov     [rsp+0F8h+samDesired], 20006h; samDesired
0x18063b835  mov     [rsp+0F8h+dwOptions], esi; dwOptions
0x18063b839  xor     r9d, r9d; lpClass
0x18063b83c  xor     r8d, r8d; Reserved
0x18063b83f  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\BootToClo"...
0x18063b846  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18063b84d  call    cs:__imp_RegCreateKeyExW
0x18063b853  mov     rcx, [rsp+0F8h]
0x18063b85b  test    eax, eax
0x18063b85d  jz      short loc_18063B866
0x18063b85f  mov     edx, 15Eh
0x18063b864  jmp     short loc_18063B8DA
0x18063b866  mov     rbx, [rdi+48h]
0x18063b86a  mov     [rsp+0F8h+var_50], rbx
0x18063b872  mov     [rdi+70h], rbx
0x18063b876  test    rbx, rbx
0x18063b879  jz      short loc_18063B882
0x18063b87b  lock inc dword ptr [rbx+118h]
0x18063b882  lea     rcx, [rbx+8]
0x18063b886  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18063b88b  mov     byte ptr [rbx+110h], 1
0x18063b892  lea     rcx, [rdi+70h]
0x18063b896  call    ??1?$test_data_control@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(void)
0x18063b89b  mov     rcx, [r14]; hKey
0x18063b89e  mov     [rsp+0F8h+arg_8], rcx
0x18063b8a6  mov     r12d, 4
0x18063b8ac  mov     [rsp+0F8h+samDesired], r12d; cbData
0x18063b8b1  mov     qword ptr [rsp+0F8h+dwOptions], r13; unsigned int
0x18063b8b6  mov     r9d, r12d; dwType
0x18063b8b9  xor     r8d, r8d; Reserved
0x18063b8bc  lea     rdx, aPhysicaldevice; "PhysicalDeviceAccessConfigured"
0x18063b8c3  call    cs:__imp_RegSetValueExW
0x18063b8c9  mov     rcx, [rsp+0F8h]; this
0x18063b8d1  test    eax, eax
0x18063b8d3  jz      short loc_18063B8EE
0x18063b8d5  mov     edx, 161h; void *
0x18063b8da  lea     r8, aPcshellTwinuiC_10; "pcshell\\twinui\\cloudpc\\lib\\cloudpcc"...
0x18063b8e1  mov     r9d, eax; char *
0x18063b8e4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18063b8e9  jmp     loc_18063BAD6
0x18063b8ee  mov     rbx, [rdi+48h]
0x18063b8f2  mov     [rsp+0F8h+var_50], rbx
0x18063b8fa  mov     [rdi+78h], rbx
0x18063b8fe  test    rbx, rbx
0x18063b901  jz      short loc_18063B90A
0x18063b903  lock inc dword ptr [rbx+118h]
0x18063b90a  lea     rcx, [rbx+8]
0x18063b90e  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18063b913  mov     byte ptr [rbx+111h], 1
0x18063b91a  lea     rcx, [rdi+78h]
0x18063b91e  call    ??1?$test_data_control@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(void)
0x18063b923  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FSOE@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FSOE@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FSOE> `wil::Feature<__WilFeatureTraits_Feature_FSOE>::GetImpl(void)'::`2'::impl
0x18063b92a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FSOE@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FSOE>::__private_IsEnabled(void)
0x18063b92f  test    al, al
0x18063b931  jz      loc_18063BAD6
0x18063b937  mov     rcx, [r14]; hKey
0x18063b93a  mov     [rsp+0F8h+arg_8], rcx
0x18063b942  mov     [rsp+0F8h+samDesired], r12d; cbData
0x18063b947  lea     rax, [rdi+50h]
0x18063b94b  mov     qword ptr [rsp+0F8h+dwOptions], rax; unsigned int
0x18063b950  mov     r9d, r12d; dwType
0x18063b953  xor     r8d, r8d; Reserved
0x18063b956  lea     rdx, aSignoutconfigu; "SignOutConfiguredForPhysicalDeviceAcces"...
0x18063b95d  call    cs:__imp_RegSetValueExW
0x18063b963  mov     rcx, [rsp+0F8h]; this
0x18063b96b  test    eax, eax
0x18063b96d  jz      short loc_18063B983
0x18063b96f  mov     r9d, eax; char *
0x18063b972  lea     r8, aPcshellTwinuiC_10; "pcshell\\twinui\\cloudpc\\lib\\cloudpcc"...
0x18063b979  mov     edx, 167h; void *
0x18063b97e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18063b983  lea     rax, [rdi+80h]
0x18063b98a  mov     [rax], sil
0x18063b98d  lea     rcx, [rdi+88h]
0x18063b994  mov     [rcx], r15
0x18063b997  mov     [rdi+90h], rax
0x18063b99e  mov     [rdi+98h], sil
0x18063b9a5  xor     eax, eax
0x18063b9a7  mov     [rdi+99h], eax
0x18063b9ad  mov     [rdi+9Dh], ax
0x18063b9b4  mov     [rdi+9Fh], al
0x18063b9ba  lea     rdx, [rdi+0A0h]
0x18063b9c1  mov     [rdx], rdi
0x18063b9c4  mov     [rdi+8], r12w
0x18063b9c9  call    wil__details__coro__coroutine_withsuspend_awaiter_tip2__test_watcher_tip2__details__merged_data__tip_SetPhysicalDeviceAccessRegKeyTipTest__tip_SetPhysicalDeviceAccessRegKeyTipTest_____winrt__resume_background____2___awaitable______await_suspend_std__experimental__coroutine_handle_std__experimental__coroutine_traits_winrt__fire_and_forget__lambda_6fb11d0d7411a5a830f0f679b4ef5f8d__const_____promise_type___
0x18063b9ce  nop
0x18063b9cf  jmp     loc_18063BB87
0x18063b9d4  lea     rcx, [rdi+58h]; jumptable 000000018063B799 case 6
0x18063b9d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063b9dd  nop
0x18063b9de  lea     rcx, [rdi+10h]
0x18063b9e2  call    ??1?$test_watcher@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(void)
0x18063b9e7  nop
0x18063b9e8  xor     esi, esi
0x18063b9ea  jmp     loc_18063BB6D
0x18063b9ef  mov     al, [rdi+98h]; jumptable 000000018063B799 case 5
0x18063b9f5  mov     [rsp+0F8h+var_90], al
0x18063b9f9  xor     esi, esi
0x18063b9fb  test    al, al
0x18063b9fd  jz      short loc_18063BA15
0x18063b9ff  mov     rcx, [rdi+88h]
0x18063ba06  mov     [rsp+0F8h+var_A0], rcx
0x18063ba0b  add     rcx, 8; this
0x18063ba0f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18063ba14  nop
0x18063ba15  lea     rcx, [rdi+0A8h]
0x18063ba1c  mov     [rcx], rsi
0x18063ba1f  mov     [rdi+0B0h], rsi
0x18063ba26  mov     qword ptr [rdi+0B8h], 2625A00h
0x18063ba31  mov     [rdi+0C0h], rsi
0x18063ba38  mov     [rdi+0C8h], esi
0x18063ba3e  mov     eax, 6
0x18063ba43  mov     [rdi+8], ax
0x18063ba47  mov     rdx, rdi
0x18063ba4a  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUWindowTabHost@implementation@Shell@Internal@Windows@2@_K@experimental@std@@@timespan_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@PEAUWindowTabHost@implementation@Shell@Internal@Windows@2@_K@experimental@std@@@experimental@std@@@Z; winrt::impl::timespan_awaiter::await_suspend<std::experimental::coroutine_traits<winrt::fire_and_forget,winrt::Windows::Internal::Shell::implementation::WindowTabHost *,unsigned __int64>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::fire_and_forget,winrt::Windows::Internal::Shell::implementation::WindowTabHost *,unsigned __int64>::promise_type>)
0x18063ba4f  jmp     loc_18063B9CF
0x18063ba54  lea     rcx, [rdi+0A8h]; jumptable 000000018063B799 case 8
0x18063ba5b  call    ??1timespan_awaiter@impl@winrt@@QEAA@XZ; winrt::impl::timespan_awaiter::~timespan_awaiter(void)
0x18063ba60  nop
0x18063ba61  lea     rcx, [rdi+58h]
0x18063ba65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063ba6a  nop
0x18063ba6b  lea     rcx, [rdi+10h]
0x18063ba6f  call    ??1?$test_watcher@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(void)
0x18063ba74  nop
0x18063ba75  xor     esi, esi
0x18063ba77  jmp     loc_18063BB6D
0x18063ba7c  lea     rbx, [rdi+0A8h]; jumptable 000000018063B799 case 7
0x18063ba83  mov     rcx, rbx; this
0x18063ba86  call    ?await_resume@timespan_awaiter@impl@winrt@@QEAAXXZ; winrt::impl::timespan_awaiter::await_resume(void)
0x18063ba8b  nop
0x18063ba8c  mov     rcx, rbx; this
0x18063ba8f  call    ??1timespan_awaiter@impl@winrt@@QEAA@XZ; winrt::impl::timespan_awaiter::~timespan_awaiter(void)
0x18063ba94  lea     r14, [rdi+58h]
0x18063ba98  mov     rcx, [r14]; hKey
0x18063ba9b  mov     [rsp+0F8h+arg_8], rcx
0x18063baa3  lea     rdx, aSignoutconfigu; "SignOutConfiguredForPhysicalDeviceAcces"...
0x18063baaa  call    cs:__imp_RegDeleteValueW
0x18063bab0  mov     rcx, [rsp+0F8h]; this
0x18063bab8  xor     esi, esi
0x18063baba  test    eax, eax
0x18063babc  jz      short loc_18063BB00
0x18063babe  mov     r9d, eax; char *
0x18063bac1  lea     r8, aPcshellTwinuiC_10; "pcshell\\twinui\\cloudpc\\lib\\cloudpcc"...
0x18063bac8  mov     edx, 16Ah; void *
0x18063bacd  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18063bad2  lea     r15, [rdi+10h]
0x18063bad6  mov     rcx, [rdi+48h]
0x18063bada  mov     [rsp+0F8h+var_50], rcx
0x18063bae2  add     rcx, 8
0x18063bae6  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18063baeb  nop
0x18063baec  mov     rcx, r14
0x18063baef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063baf4  nop
0x18063baf5  mov     rcx, r15
0x18063baf8  call    ??1?$test_watcher@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(void)
0x18063bafd  nop
0x18063bafe  jmp     short loc_18063BB6D
0x18063bb00  mov     rcx, [rdi+48h]
0x18063bb04  mov     [rsp+0F8h+var_50], rcx
0x18063bb0c  add     rcx, 8
0x18063bb10  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18063bb15  mov     rax, cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x18063bb1c  test    rax, rax
0x18063bb1f  jnz     short loc_18063BB42
0x18063bb21  call    tip_details_GetKernelBaseModuleHandle
0x18063bb26  mov     rcx, rax; hModule
0x18063bb29  lea     rdx, aTestcontrolrep; "TestControlReporting"
0x18063bb30  call    cs:__imp_GetProcAddress
0x18063bb36  mov     cs:?s_pfnTestControlReporting@?1??TestControlReporting@@9@4P6AXW4TestReportingRequest@@@ZEA, rax; void (*`TestControlReporting'::`2'::s_pfnTestControlReporting)(TestReportingRequest)
0x18063bb3d  test    rax, rax
0x18063bb40  jz      short loc_18063BB49
0x18063bb42  xor     ecx, ecx
0x18063bb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18063bb49  mov     edx, 80000000h; dwReason
0x18063bb4e  mov     ecx, 4; uFlags
0x18063bb53  call    cs:__imp_ExitWindowsEx
0x18063bb59  nop
0x18063bb5a  mov     rcx, r14
0x18063bb5d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18063bb62  nop
0x18063bb63  lea     rcx, [rdi+10h]
0x18063bb67  call    ??1?$test_watcher@V?$merged_data@U_tip_SetPhysicalDeviceAccessRegKeyTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetPhysicalDeviceAccessRegKeyTipTest,_tip_SetPhysicalDeviceAccessRegKeyTipTest>>(void)
0x18063bb6c  nop
0x18063bb6d  jmp     short loc_18063BB71
0x18063bb6f  xor     esi, esi; jumptable 000000018063B799 case 0
0x18063bb71  cmp     [rdi+0Ah], si
0x18063bb75  jz      short loc_18063BB87
0x18063bb77  mov     edx, 0F0h
0x18063bb7c  mov     rcx, rdi; Block
0x18063bb7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18063bb84  jmp     short loc_18063BB87
0x18063bb86  int     3; Trap to Debugger
0x18063bb87  lea     r11, [rsp+0F8h+var_28]
0x18063bb8f  mov     rbx, [r11+40h]
0x18063bb93  mov     rsi, [r11+48h]
0x18063bb97  mov     rsp, r11
0x18063bb9a  pop     r15
0x18063bb9c  pop     r14
0x18063bb9e  pop     r13
0x18063bba0  pop     r12
0x18063bba2  pop     rdi
0x18063bba3  retn
```
