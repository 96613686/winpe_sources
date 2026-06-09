# Microsoft::Diagnostics::UserManager::GetXuidForUserContext(unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1801bfdf0`
- end: `0x1801c01b9`
- name: `?GetXuidForUserContext@UserManager@Diagnostics@Microsoft@@AEBAJ_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801bf0a4`

## callees

- `0x180006670`
- `0x180026ecc`
- `0x180034d94`
- `0x18003fe04`
- `0x180040454`
- `0x180058b80`
- `0x18005d050`
- `0x180080054`
- `0x1800800bc`
- `0x180089d90`
- `0x18009682c`
- `0x180096cd0`
- `0x180096da4`
- `0x180096eac`
- `0x1800b5938`
- `0x1800b6524`
- `0x18012de40`
- `0x18015f810`
- `0x1801bf71c`
- `0x1801bfca4`
- `0x1801bfdf0`
- `0x180346010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c002b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c0087`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c00db`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c002b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c0087`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c00db`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801bffef`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801bffef`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1801bfe32`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1801bfe32`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801bff88`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801bff88`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1801bff53`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1801bff53`

## string_xrefs

- `0x1801bffa5`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1801c006a`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1801c0182`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1801c0194`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1801c01a6`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UserManager::GetXuidForUserContext(__int64 a1, wchar_t *a2, __int64 a3)
{
  char *v3; // rdi
  _WORD *v5; // rcx
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 String; // rax
  CONTEXT *v9; // rbx
  __int64 v10; // r8
  int v11; // eax
  unsigned int v12; // ebx
  int GamerAccountXuidForImpersonatedUser; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-A8h]
  wchar_t *v24; // [rsp+30h] [rbp-98h] BYREF
  HANDLE hToken; // [rsp+38h] [rbp-90h] BYREF
  unsigned __int64 v26; // [rsp+40h] [rbp-88h] BYREF
  char *v27; // [rsp+48h] [rbp-80h] BYREF
  const void *v28[2]; // [rsp+50h] [rbp-78h] BYREF
  _QWORD v29[7]; // [rsp+60h] [rbp-68h] BYREF
  _QWORD *v30; // [rsp+98h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v3 = (char *)a3;
  *(_QWORD *)(a3 + 16) = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v5 = (_WORD *)a3;
  else
    v5 = *(_WORD **)a3;
  *v5 = 0;
  if ( (unsigned int)XblaIsConsole() )
  {
    winrt::Windows::System::Internal::UserManager::GetUserForContext((unsigned __int64)&v26);
    v29[0] = off_180356A48;
    v29[1] = &v26;
    v30 = v29;
    Microsoft::Diagnostics::Utils::Os::GetAsyncResultsOrTimeout<winrt::Windows::Foundation::IInspectable>(
      &v24,
      v29,
      v6,
      3);
    if ( v30 )
    {
      v7 = v29;
      LOBYTE(v7) = v30 != v29;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v7);
      v30 = 0;
    }
    winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Foundation::IPropertyValue>(&v24, &hToken);
    String = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
               &hToken,
               &v27);
    winrt::hstring::operator std::wstring_view(String, v28);
    std::wstring::_Assign<wchar_t>((char **)v3, v28[0], (char *)v28[1]);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v27);
    winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&hToken);
    if ( v24 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v24);
    winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v26);
    goto LABEL_24;
  }
  hToken = 0;
  v9 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
  RtlCaptureContext(v9);
  LOBYTE(v10) = 2;
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(v28, 240000, v10, v9);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hToken,
    0);
  v11 = UMgrQueryUserToken(a2, &hToken);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      (const char *)(unsigned int)v11,
      v23);
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v28);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    return v12;
  }
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v28);
  if ( (char *)hToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL || !ImpersonateLoggedOnUser(hToken) )
  {
LABEL_23:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
LABEL_24:
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 2304) )
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(char **)v3;
      v27 = v3;
      v24 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
        v20,
        (unsigned int)&unk_1803C6C37,
        v21,
        v22,
        (__int64)&v24,
        (__int64)&v27);
    }
    return 0;
  }
  BYTE1(v26) = 1;
  v24 = 0;
  GamerAccountXuidForImpersonatedUser = XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(&v24);
  v15 = GamerAccountXuidForImpersonatedUser;
  if ( GamerAccountXuidForImpersonatedUser == -2147024894 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
        v16);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    return 2147942402LL;
  }
  if ( GamerAccountXuidForImpersonatedUser >= 0 )
  {
    v18 = -1;
    do
      ++v18;
    while ( v24[v18] );
    std::wstring::_Assign<wchar_t>((char **)v3, v24, (char *)v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
        v19);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E0,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
    (const char *)(unsigned int)GamerAccountXuidForImpersonatedUser,
    v23);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      v17);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  return v15;
}

```

## disassembly

```asm
0x1801bfdf0  mov     [rsp+arg_0], rbx
0x1801bfdf5  push    rsi
0x1801bfdf6  push    rdi
0x1801bfdf7  push    r14
0x1801bfdf9  sub     rsp, 0B0h
0x1801bfe00  mov     rax, cs:__security_cookie
0x1801bfe07  xor     rax, rsp
0x1801bfe0a  mov     [rsp+0C8h+var_28], rax
0x1801bfe12  mov     rdi, r8
0x1801bfe15  mov     rsi, rdx
0x1801bfe18  xor     r14d, r14d
0x1801bfe1b  mov     [r8+10h], r14
0x1801bfe1f  cmp     qword ptr [r8+18h], 7
0x1801bfe24  jbe     short loc_1801BFE2B
0x1801bfe26  mov     rcx, [r8]
0x1801bfe29  jmp     short loc_1801BFE2E
0x1801bfe2b  mov     rcx, rdi
0x1801bfe2e  mov     [rcx], r14w
0x1801bfe32  call    cs:__imp_XblaIsConsole
0x1801bfe39  nop     dword ptr [rax+rax+00h]
0x1801bfe3e  test    eax, eax
0x1801bfe40  jz      loc_1801BFF30
0x1801bfe46  mov     rdx, rsi
0x1801bfe49  lea     rcx, [rsp+0C8h+var_88]; unsigned __int64
0x1801bfe4e  call    ?GetUserForContext@UserManager@Internal@System@Windows@winrt@@SA@_K@Z; winrt::Windows::System::Internal::UserManager::GetUserForContext(unsigned __int64)
0x1801bfe53  nop
0x1801bfe54  lea     rax, off_180356A48
0x1801bfe5b  mov     [rsp+0C8h+var_68], rax
0x1801bfe60  lea     rax, [rsp+0C8h+var_88]
0x1801bfe65  mov     [rsp+0C8h+var_60], rax
0x1801bfe6a  lea     rax, [rsp+0C8h+var_68]
0x1801bfe6f  mov     [rsp+0C8h+var_30], rax
0x1801bfe77  mov     r9d, 3
0x1801bfe7d  lea     rdx, [rsp+0C8h+var_68]
0x1801bfe82  lea     rcx, [rsp+0C8h+var_98]
0x1801bfe87  call    ??$GetAsyncResultsOrTimeout@UIInspectable@Foundation@Windows@winrt@@@Os@Utils@Diagnostics@Microsoft@@SA?AUIInspectable@Foundation@Windows@winrt@@AEBV?$function@$$A6A?AU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@XZ@std@@KVAsyncOperationBucket@EnumDetails@123@KK@Z; Microsoft::Diagnostics::Utils::Os::GetAsyncResultsOrTimeout<winrt::Windows::Foundation::IInspectable>(std::function<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable> (void)> const &,ulong,Microsoft::Diagnostics::Utils::EnumDetails::AsyncOperationBucket,ulong,ulong)
0x1801bfe8c  nop
0x1801bfe8d  mov     rcx, [rsp+0C8h+var_30]
0x1801bfe95  test    rcx, rcx
0x1801bfe98  jz      short loc_1801BFEB9
0x1801bfe9a  mov     rax, [rcx]
0x1801bfe9d  lea     rdx, [rsp+0C8h+var_68]
0x1801bfea2  cmp     rcx, rdx
0x1801bfea5  setnz   dl
0x1801bfea8  mov     rax, [rax+20h]
0x1801bfeac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bfeb1  mov     [rsp+0C8h+var_30], r14
0x1801bfeb9  lea     rdx, [rsp+0C8h+hToken]
0x1801bfebe  lea     rcx, [rsp+0C8h+var_98]
0x1801bfec3  call    ??$as@UIPropertyValue@Foundation@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x1801bfec8  nop
0x1801bfec9  lea     rdx, [rsp+0C8h+var_80]
0x1801bfece  lea     rcx, [rsp+0C8h+hToken]
0x1801bfed3  call    ?GetString@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(void)
0x1801bfed8  nop
0x1801bfed9  lea     rdx, [rsp+0C8h+var_78]
0x1801bfede  mov     rcx, rax
0x1801bfee1  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x1801bfee6  mov     r8, [rsp+0C8h+var_70]
0x1801bfeeb  mov     rdx, [rsp+0C8h+var_78]
0x1801bfef0  mov     rcx, rdi
0x1801bfef3  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801bfef8  nop
0x1801bfef9  lea     rcx, [rsp+0C8h+var_80]
0x1801bfefe  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801bff03  nop
0x1801bff04  lea     rcx, [rsp+0C8h+hToken]; this
0x1801bff09  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1801bff0e  nop
0x1801bff0f  cmp     [rsp+0C8h+var_98], r14
0x1801bff14  jz      short loc_1801BFF21
0x1801bff16  lea     rcx, [rsp+0C8h+var_98]
0x1801bff1b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1801bff20  nop
0x1801bff21  lea     rcx, [rsp+0C8h+var_88]; this
0x1801bff26  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1801bff2b  jmp     loc_1801C0101
0x1801bff30  mov     [rsp+0C8h+hToken], r14
0x1801bff35  mov     ecx, cs:_tls_index
0x1801bff3b  mov     rax, gs:58h
0x1801bff44  mov     edx, 40h ; '@'
0x1801bff49  mov     rbx, [rax+rcx*8]
0x1801bff4d  add     rbx, rdx
0x1801bff50  mov     rcx, rbx; ContextRecord
0x1801bff53  call    cs:__imp_RtlCaptureContext
0x1801bff5a  nop     dword ptr [rax+rax+00h]
0x1801bff5f  mov     r9, rbx
0x1801bff62  mov     r8b, 2
0x1801bff65  mov     edx, 3A980h
0x1801bff6a  lea     rcx, [rsp+0C8h+var_78]
0x1801bff6f  call    ??0ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@KVExternalHangBucket@EnumDetails@23@AEBU_CONTEXT@@@Z; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(ulong,Microsoft::Diagnostics::EnumDetails::ExternalHangBucket,_CONTEXT const &)
0x1801bff74  xor     edx, edx
0x1801bff76  lea     rcx, [rsp+0C8h+hToken]
0x1801bff7b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801bff80  lea     rdx, [rsp+0C8h+hToken]
0x1801bff85  mov     rcx, rsi
0x1801bff88  call    cs:__imp_UMgrQueryUserToken
0x1801bff8f  nop     dword ptr [rax+rax+00h]
0x1801bff94  mov     ebx, eax
0x1801bff96  test    eax, eax
0x1801bff98  jns     short loc_1801BFFD2
0x1801bff9a  mov     rcx, [rsp+0C8h]; this
0x1801bffa2  mov     r9d, eax; char *
0x1801bffa5  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801bffac  mov     edx, 2CDh; void *
0x1801bffb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bffb6  lea     rcx, [rsp+0C8h+var_78]; this
0x1801bffbb  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x1801bffc0  nop
0x1801bffc1  lea     rcx, [rsp+0C8h+hToken]
0x1801bffc6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801bffcb  mov     eax, ebx
0x1801bffcd  jmp     loc_1801C015D
0x1801bffd2  lea     rcx, [rsp+0C8h+var_78]; this
0x1801bffd7  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x1801bffdc  mov     rcx, [rsp+0C8h+hToken]; hToken
0x1801bffe1  lea     rax, [rcx-1]
0x1801bffe5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801bffe9  ja      loc_1801C00F7
0x1801bffef  call    cs:__imp_ImpersonateLoggedOnUser
0x1801bfff6  nop     dword ptr [rax+rax+00h]
0x1801bfffb  test    eax, eax
0x1801bfffd  jz      loc_1801C00F7
0x1801c0003  mov     byte ptr [rsp+0C8h+var_88+1], 1
0x1801c0008  mov     [rsp+0C8h+var_98], r14
0x1801c000d  lea     rcx, [rsp+0C8h+var_98]; wchar_t **
0x1801c0012  call    ?GetGamerAccountXuidForImpersonatedUser@XblAuthConfig@@SAJPEAPEA_W@Z; XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(wchar_t * *)
0x1801c0017  mov     ebx, eax
0x1801c0019  cmp     eax, 80070002h
0x1801c001e  jnz     short loc_1801C005B
0x1801c0020  lea     rcx, [rsp+0C8h+var_98]
0x1801c0025  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c002a  nop
0x1801c002b  call    cs:__imp_RevertToSelf
0x1801c0032  nop     dword ptr [rax+rax+00h]
0x1801c0037  mov     rcx, [rsp+0C8h]; this
0x1801c003f  test    eax, eax
0x1801c0041  jz      loc_1801C0182
0x1801c0047  lea     rcx, [rsp+0C8h+hToken]
0x1801c004c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c0051  mov     eax, 80070002h
0x1801c0056  jmp     loc_1801C015D
0x1801c005b  test    ebx, ebx
0x1801c005d  jns     short loc_1801C00B4
0x1801c005f  mov     rcx, [rsp+0C8h]; this
0x1801c0067  mov     r9d, ebx; char *
0x1801c006a  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801c0071  mov     edx, 2E0h; void *
0x1801c0076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c007b  nop
0x1801c007c  lea     rcx, [rsp+0C8h+var_98]
0x1801c0081  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c0086  nop
0x1801c0087  call    cs:__imp_RevertToSelf
0x1801c008e  nop     dword ptr [rax+rax+00h]
0x1801c0093  mov     rcx, [rsp+0C8h]; this
0x1801c009b  test    eax, eax
0x1801c009d  jz      loc_1801C0194
0x1801c00a3  lea     rcx, [rsp+0C8h+hToken]
0x1801c00a8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c00ad  mov     eax, ebx
0x1801c00af  jmp     loc_1801C015D
0x1801c00b4  mov     rdx, [rsp+0C8h+var_98]
0x1801c00b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801c00bd  inc     r8
0x1801c00c0  cmp     [rdx+r8*2], r14w
0x1801c00c5  jnz     short loc_1801C00BD
0x1801c00c7  mov     rcx, rdi
0x1801c00ca  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801c00cf  nop
0x1801c00d0  lea     rcx, [rsp+0C8h+var_98]
0x1801c00d5  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c00da  nop
0x1801c00db  call    cs:__imp_RevertToSelf
0x1801c00e2  nop     dword ptr [rax+rax+00h]
0x1801c00e7  mov     rcx, [rsp+0C8h]; this
0x1801c00ef  test    eax, eax
0x1801c00f1  jz      loc_1801C01A6
0x1801c00f7  lea     rcx, [rsp+0C8h+hToken]
0x1801c00fc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c0101  mov     eax, cs:dword_18042D328
0x1801c0107  cmp     eax, 4
0x1801c010a  jbe     short loc_1801C0155
0x1801c010c  mov     edx, 900h
0x1801c0111  lea     rcx, dword_18042D328
0x1801c0118  call    _tlgKeywordOn
0x1801c011d  test    al, al
0x1801c011f  jz      short loc_1801C0155
0x1801c0121  cmp     qword ptr [rdi+18h], 7
0x1801c0126  jbe     short loc_1801C012B
0x1801c0128  mov     rdi, [rdi]
0x1801c012b  mov     [rsp+0C8h+var_80], rdi
0x1801c0130  mov     [rsp+0C8h+var_98], rsi
0x1801c0135  lea     rax, [rsp+0C8h+var_80]
0x1801c013a  mov     [rsp+0C8h+var_A0], rax
0x1801c013f  lea     rax, [rsp+0C8h+var_98]
0x1801c0144  mov     [rsp+0C8h+var_A8], rax
0x1801c0149  lea     rdx, unk_1803C6C37
0x1801c0150  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x1801c0155  xor     eax, eax
0x1801c0157  jmp     short loc_1801C015D
0x1801c0159  mov     eax, dword ptr [rsp+0C8h+var_88]
0x1801c015d  mov     rcx, [rsp+0C8h+var_28]
0x1801c0165  xor     rcx, rsp; StackCookie
0x1801c0168  call    __security_check_cookie
0x1801c016d  mov     rbx, [rsp+0C8h+arg_0]
0x1801c0175  add     rsp, 0B0h
0x1801c017c  pop     r14
0x1801c017e  pop     rdi
0x1801c017f  pop     rsi
0x1801c0180  retn
0x1801c0182  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801c0189  mov     edx, 2D8h; void *
0x1801c018e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c0194  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801c019b  mov     edx, 2D8h; void *
0x1801c01a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c01a6  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801c01ad  mov     edx, 2D8h; void *
0x1801c01b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
