# winrt::WindowsUdk::UI::Shell::implementation::SearchBoxPlaceholder::EnsureRegistryWatcher(void)

- ea: `0x180009db0`
- end: `0x18000a0dd`
- name: `?EnsureRegistryWatcher@SearchBoxPlaceholder@implementation@Shell@UI@WindowsUdk@winrt@@CAXXZ`
- size: `813`
- prototype: `void(void)`
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c46c0`
- `0x1800c4bf0`
- `0x180102250`
- `0x18041a124`
- `0x18041a1d4`
- `0x18041b290`
- `0x18041b830`

## callees

- `0x180007e18`
- `0x1800086e8`
- `0x180008f78`
- `0x18000911c`
- `0x180009db0`
- `0x18000ac2c`
- `0x18000ac60`
- `0x180010940`
- `0x180010990`
- `0x180011088`
- `0x1800252a0`
- `0x1800260c0`
- `0x180027af0`
- `0x1800795e4`
- `0x1800cd5a4`
- `0x18015cb00`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ddf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009ec7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009ec7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009f89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a006`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009f65`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009f65`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000a04d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000a04d`

## string_xrefs

- `0x18000a0b6`: `shellcommon\undockeddevkit\libs\windowsudk.ui.shell.search\searchboxplaceholder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void winrt::WindowsUdk::UI::Shell::implementation::SearchBoxPlaceholder::EnsureRegistryWatcher(void)
{
  const WCHAR *v0; // rbx
  const WCHAR *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rbx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  bool v6; // sf
  int v7; // ecx
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v13[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+78h] [rbp-88h] BYREF
  __m128i si128; // [rsp+88h] [rbp-78h]
  _BYTE v16[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 (__fastcall **v17)(); // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall ***v18)(); // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  AcquireSRWLockExclusive(&SRWLock);
  v13[1] = &SRWLock;
  if ( !qword_1805EC8C0 )
  {
    winrt::hstring::hstring((winrt::hstring *)&hKey, L"current");
    *(_OWORD *)lpSubKey = 0;
    si128 = 0;
    std::wstring::_Construct<1,wchar_t *>(
      lpSubKey,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\Dynamic\\Current",
      72);
    GetRegString((winrt::hstring *)v13, (LPCWSTR)lpSubKey, (winrt::hstring *)&hKey);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(lpSubKey[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpSubKey[0]) = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&hKey);
    v0 = &String1;
    if ( v13[0] )
    {
      v1 = *(const WCHAR **)(v13[0] + 16LL);
      v2 = *(unsigned int *)(v13[0] + 4LL);
    }
    else
    {
      v1 = &String1;
      v2 = 0;
    }
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v1, v2, &String1, 0) )
    {
      v12 = 0;
      winrt::to_hstring(&hKey, &v12);
      *(_OWORD *)lpSubKey = 0;
      si128 = 0;
      std::wstring::_Construct<1,wchar_t *>(
        lpSubKey,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\Dynamic\\Current",
        72);
      if ( hKey )
        v7 = *((_DWORD *)hKey + 1);
      else
        v7 = 0;
      if ( hKey )
        v0 = (const WCHAR *)*((_QWORD *)hKey + 2);
      v8 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v8 = lpSubKey[0];
      v9 = RegSetKeyValueW(HKEY_CURRENT_USER, v8, L"current", 2u, v0, 2 * v7 + 2);
      if ( v9 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x73,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.ui.shell.search\\searchboxplaceholder.cpp",
          (const char *)v9,
          dwOptions);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpSubKey[0], 2 * si128.m128i_i64[1] + 2);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&hKey);
    }
    else
    {
      winrt::WindowsUdk::UI::Shell::implementation::SearchBoxPlaceholder::StartExpiryTimer();
    }
    v17 = off_1804B6398;
    v18 = &v17;
    v3 = 0;
    *(_QWORD *)&v12 = 0;
    hKey = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\Dynamic\\Current",
            0,
            0,
            0,
            0x10u,
            0,
            phkResult,
            0);
    v6 = Key < 0;
    if ( Key > 0 )
      v6 = 1;
    if ( v6 )
    {
      if ( hKey )
        RegCloseKey(hKey);
    }
    else
    {
      wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        (wil::details::registry_watcher_state **)&v12,
        &hKey,
        1,
        (__int64)v16);
      if ( hKey )
        RegCloseKey(hKey);
      v3 = v12;
    }
    if ( v18 )
      ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v18)[3])(v18);
    if ( v3 )
    {
      winrt::WindowsUdk::UI::Shell::implementation::DynamicSearchBoxTelemetry::DynamicSearchBox_RegistryWatcherRegistered();
      wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
        &qword_1805EC8C0,
        v3);
      *(_QWORD *)&v12 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v12);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v13);
  }
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180009db0  mov     [rsp-8+arg_0], rbx
0x180009db5  mov     [rsp-8+arg_8], rsi
0x180009dba  push    rbp
0x180009dbb  lea     rbp, [rsp-20h]
0x180009dc0  sub     rsp, 120h
0x180009dc7  mov     rax, cs:__security_cookie
0x180009dce  xor     rax, rsp
0x180009dd1  mov     [rbp+20h+var_10], rax
0x180009dd5  lea     rsi, SRWLock
0x180009ddc  mov     rcx, rsi; SRWLock
0x180009ddf  call    cs:__imp_AcquireSRWLockExclusive
0x180009de5  mov     [rsp+120h+var_B0], rsi
0x180009dea  cmp     cs:qword_1805EC8C0, 0
0x180009df2  jnz     loc_180009EC4
0x180009df8  lea     rdx, aCurrent; "current"
0x180009dff  lea     rcx, [rsp+120h+hKey]; this
0x180009e04  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180009e09  nop
0x180009e0a  xorps   xmm0, xmm0
0x180009e0d  movups  xmmword ptr [rsp+120h+lpSubKey], xmm0
0x180009e12  xorps   xmm1, xmm1
0x180009e15  movdqu  [rbp+20h+var_98], xmm1
0x180009e1a  mov     r8d, 48h ; 'H'
0x180009e20  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009e27  lea     rcx, [rsp+120h+lpSubKey]
0x180009e2c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180009e31  nop
0x180009e32  lea     r8, [rsp+120h+hKey]; winrt::hstring *
0x180009e37  lea     rdx, [rsp+120h+lpSubKey]; lpSubKey
0x180009e3c  lea     rcx, [rsp+120h+var_B8]; this
0x180009e41  call    ?GetRegString@@YA?AUhstring@winrt@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU12@@Z; GetRegString(std::wstring const &,winrt::hstring const &)
0x180009e46  nop
0x180009e47  mov     rdx, qword ptr [rbp+20h+var_98+8]
0x180009e4b  cmp     rdx, 7
0x180009e4f  ja      loc_18000A09C
0x180009e55  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180009e5d  movdqu  [rbp+20h+var_98], xmm0
0x180009e62  xor     eax, eax
0x180009e64  mov     word ptr [rsp+120h+lpSubKey], ax
0x180009e69  lea     rcx, [rsp+120h+hKey]
0x180009e6e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180009e73  lea     rbx, String1
0x180009e7a  mov     rax, [rsp+120h+var_B8]
0x180009e7f  test    rax, rax
0x180009e82  jnz     short loc_180009EEE
0x180009e84  mov     rcx, rbx
0x180009e87  xor     edx, edx
0x180009e89  jmp     short loc_180009EF5
0x180009e8b  mov     rbx, qword ptr [rsp+120h+var_C8]
0x180009e90  mov     rcx, [rbp+20h+var_18]
0x180009e94  test    rcx, rcx
0x180009e97  jz      short loc_180009EA5
0x180009e99  mov     rax, [rcx]
0x180009e9c  mov     rax, [rax+18h]
0x180009ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea5  test    rbx, rbx
0x180009ea8  jnz     loc_18000A07A
0x180009eae  lea     rcx, [rsp+120h+var_C8]
0x180009eb3  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x180009eb8  nop
0x180009eb9  lea     rcx, [rsp+120h+var_B8]
0x180009ebe  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180009ec3  nop
0x180009ec4  mov     rcx, rsi; SRWLock
0x180009ec7  call    cs:__imp_ReleaseSRWLockExclusive
0x180009ecd  mov     rcx, [rbp+20h+var_10]
0x180009ed1  xor     rcx, rsp; StackCookie
0x180009ed4  call    __security_check_cookie
0x180009ed9  lea     r11, [rsp+120h+var_s0]
0x180009ee1  mov     rbx, [r11+10h]
0x180009ee5  mov     rsi, [r11+18h]
0x180009ee9  mov     rsp, r11
0x180009eec  pop     rbp
0x180009eed  retn
0x180009eee  mov     rcx, [rax+10h]
0x180009ef2  mov     edx, [rax+4]
0x180009ef5  xor     r9d, r9d
0x180009ef8  mov     r8, rbx
0x180009efb  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180009f00  test    al, al
0x180009f02  jnz     loc_180009F94
0x180009f08  call    ?StartExpiryTimer@SearchBoxPlaceholder@implementation@Shell@UI@WindowsUdk@winrt@@CAXXZ; winrt::WindowsUdk::UI::Shell::implementation::SearchBoxPlaceholder::StartExpiryTimer(void)
0x180009f0d  lea     rax, off_1804B6398
0x180009f14  mov     [rbp+20h+var_80], rax
0x180009f18  lea     rax, [rbp+20h+var_80]
0x180009f1c  mov     [rbp+20h+var_18], rax
0x180009f20  xor     ebx, ebx
0x180009f22  mov     qword ptr [rsp+120h+var_C8], rbx
0x180009f27  mov     [rsp+120h+hKey], rbx
0x180009f2c  lea     rcx, [rsp+120h+hKey]
0x180009f31  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180009f36  mov     [rsp+120h+lpdwDisposition], rbx; lpdwDisposition
0x180009f3b  mov     [rsp+120h+phkResult], rax; phkResult
0x180009f40  mov     [rsp+120h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180009f45  mov     [rsp+120h+samDesired], 10h; samDesired
0x180009f4d  mov     [rsp+120h+dwOptions], ebx; dwOptions
0x180009f51  xor     r9d, r9d; lpClass
0x180009f54  xor     r8d, r8d; Reserved
0x180009f57  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009f5e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009f65  call    cs:__imp_RegCreateKeyExW
0x180009f6b  test    eax, eax
0x180009f6d  jle     short loc_180009F79
0x180009f6f  movzx   eax, ax
0x180009f72  or      eax, 80070000h
0x180009f77  test    eax, eax
0x180009f79  jns     short loc_180009FE2
0x180009f7b  mov     rcx, [rsp+120h+hKey]; hKey
0x180009f80  test    rcx, rcx
0x180009f83  jz      loc_180009E90
0x180009f89  call    cs:__imp_RegCloseKey
0x180009f8f  jmp     loc_180009E90
0x180009f94  xorps   xmm0, xmm0
0x180009f97  movups  [rsp+120h+var_C8], xmm0
0x180009f9c  lea     rdx, [rsp+120h+var_C8]
0x180009fa1  lea     rcx, [rsp+120h+hKey]
0x180009fa6  call    ?to_hstring@winrt@@YA?AUhstring@1@AEBUguid@1@@Z; winrt::to_hstring(winrt::guid const &)
0x180009fab  nop
0x180009fac  xorps   xmm0, xmm0
0x180009faf  movups  xmmword ptr [rsp+120h+lpSubKey], xmm0
0x180009fb4  xorps   xmm1, xmm1
0x180009fb7  movdqu  [rbp+20h+var_98], xmm1
0x180009fbc  mov     r8d, 48h ; 'H'
0x180009fc2  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009fc9  lea     rcx, [rsp+120h+lpSubKey]
0x180009fce  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180009fd3  nop
0x180009fd4  mov     rax, [rsp+120h+hKey]
0x180009fd9  test    rax, rax
0x180009fdc  jnz     short loc_18000A011
0x180009fde  xor     ecx, ecx
0x180009fe0  jmp     short loc_18000A014
0x180009fe2  lea     r9, [rbp+20h+var_88]
0x180009fe6  mov     r8b, 1
0x180009fe9  lea     rdx, [rsp+120h+hKey]
0x180009fee  lea     rcx, [rsp+120h+var_C8]
0x180009ff3  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180009ff8  mov     rcx, [rsp+120h+hKey]; hKey
0x180009ffd  test    rcx, rcx
0x18000a000  jz      loc_180009E8B
0x18000a006  call    cs:__imp_RegCloseKey
0x18000a00c  jmp     loc_180009E8B
0x18000a011  mov     ecx, [rax+4]
0x18000a014  test    rax, rax
0x18000a017  jnz     short loc_18000A074
0x18000a019  lea     rdx, [rsp+120h+lpSubKey]
0x18000a01e  cmp     qword ptr [rbp+20h+var_98+8], 7
0x18000a023  cmova   rdx, [rsp+120h+lpSubKey]; lpSubKey
0x18000a029  lea     eax, ds:2[rcx*2]
0x18000a030  mov     [rsp+120h+samDesired], eax; cbData
0x18000a034  mov     qword ptr [rsp+120h+dwOptions], rbx; unsigned int
0x18000a039  mov     r9d, 2; dwType
0x18000a03f  lea     r8, aCurrent; "current"
0x18000a046  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000a04d  call    cs:__imp_RegSetKeyValueW
0x18000a053  mov     rcx, [rbp+28h]; this
0x18000a057  test    eax, eax
0x18000a059  jnz     short loc_18000A0B3
0x18000a05b  mov     rdx, qword ptr [rbp+20h+var_98+8]
0x18000a05f  cmp     rdx, 7
0x18000a063  ja      short loc_18000A0C8
0x18000a065  lea     rcx, [rsp+120h+hKey]
0x18000a06a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a06f  jmp     loc_180009F0D
0x18000a074  mov     rbx, [rax+10h]
0x18000a078  jmp     short loc_18000A019
0x18000a07a  call    ?DynamicSearchBox_RegistryWatcherRegistered@DynamicSearchBoxTelemetry@implementation@Shell@UI@WindowsUdk@winrt@@SAXXZ; winrt::WindowsUdk::UI::Shell::implementation::DynamicSearchBoxTelemetry::DynamicSearchBox_RegistryWatcherRegistered(void)
0x18000a07f  mov     rdx, rbx
0x18000a082  lea     rcx, qword_1805EC8C0
0x18000a089  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18000a08e  mov     qword ptr [rsp+120h+var_C8], 0
0x18000a097  jmp     loc_180009EAE
0x18000a09c  lea     rdx, ds:2[rdx*2]
0x18000a0a4  mov     rcx, [rsp+120h+lpSubKey]
0x18000a0a9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a0ae  jmp     loc_180009E55
0x18000a0b3  mov     r9d, eax; char *
0x18000a0b6  lea     r8, aShellcommonUnd_100; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18000a0bd  mov     edx, 73h ; 's'; void *
0x18000a0c2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a0c8  lea     rdx, ds:2[rdx*2]
0x18000a0d0  mov     rcx, [rsp+120h+lpSubKey]
0x18000a0d5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a0da  jmp     short loc_18000A065
```
