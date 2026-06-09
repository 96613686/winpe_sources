# RecoveryReportIndexRebuildEx_3

- ea: `0x180215da0`
- end: `0x180216152`
- name: `RecoveryReportIndexRebuildEx_3`
- size: `946`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180215d8c`

## callees

- `0x18002e6fc`
- `0x18002f914`
- `0x180043d18`
- `0x18006380c`
- `0x180075d8c`
- `0x180078410`
- `0x18008b084`
- `0x1800983c0`
- `0x18009e510`
- `0x18009e614`
- `0x1800f7bfc`
- `0x1801199cc`
- `0x18013edc0`
- `0x1801710e4`
- `0x18017791c`
- `0x180188d90`
- `0x18018e778`
- `0x18019b924`
- `0x1801a153c`
- `0x180215da0`
- `0x180294310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18021601c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180216104`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18021601c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180216104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216112`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180215e2c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180215e2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18021608a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18021608a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802160d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802160d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180215ed3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180215ed3`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180215f20`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1802160cb`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180215f20`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1802160cb`

## string_xrefs

- `0x180215ee8`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x180215f35`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x180215fd0`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x180215f12`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 RecoveryReportIndexRebuildEx_3()
{
  const wchar_t *v0; // rcx
  __int64 Catalog; // rax
  const wchar_t *v2; // rdi
  HKEY *phkResult; // rax
  const WCHAR *v4; // rdx
  unsigned int Key; // eax
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr10_8
  wchar_t *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  void *v16; // r11
  bool v18; // al
  wchar_t *v19; // rdx
  LSTATUS v20; // eax
  bool v21; // sf
  HANDLE v22; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-10B8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-10B8h]
  DWORD pvData; // [rsp+50h] [rbp-1088h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-1080h] BYREF
  HANDLE v27[2]; // [rsp+60h] [rbp-1078h] BYREF
  int v28; // [rsp+70h] [rbp-1068h] BYREF
  __int64 v29; // [rsp+78h] [rbp-1060h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-1058h] BYREF
  wchar_t v31[2048]; // [rsp+A0h] [rbp-1038h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10D8h] [rbp+0h]

  v28 = 0;
  v29 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v28);
  pvData = -1073473535;
  StringCchPrintfW(v31, 0x800u, L"%u", 4900);
  SearchIndexerTelemetry::IndexerCorruption<long &,wchar_t (&)[2048]>(&pvData, v31);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = PerUserCatalogNameForCorruption::GetCatalog();
    try
    {
      v2 = (const wchar_t *)Catalog;
      v27[0] = (HANDLE)Catalog;
      std::wstring::wstring(lpSubKey);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v4 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v4 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v4, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v6 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v6 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v6,
          dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      std::wstring::_Tidy_deallocate(lpSubKey);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        253,
        "onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h");
    }
    v7 = -1;
    do
      ++v7;
    while ( v2[v7] );
    v8 = v7 + 1;
    v10 = v7 + 1;
    v9 = 2 * (v7 + 1);
    if ( !is_mul_ok(v10, 2u) )
      v9 = -1;
    v11 = (wchar_t *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v11;
    if ( !v11 )
    {
      v12 = -2147024882;
      v13 = 2147942414LL;
      v14 = 257;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v13,
        dwOptionsa);
      SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v28);
      return v12;
    }
    v15 = StringCchCopyW(v11, v8, v2);
    v12 = v15;
    if ( v15 < 0 )
    {
      v13 = (unsigned int)v15;
      v14 = 259;
      goto LABEL_19;
    }
    hkey = 0;
    v27[0] = CreateThread(0, 0, ResetUserCatalog, v16, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v27);
    SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
  }
  else
  {
    hkey = 0;
    v18 = MapRegistryKeyPath(v0, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", v31);
    v19 = v31;
    if ( !v18 )
      v19 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
    v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0xF003Fu, &hkey);
    v21 = v20 < 0;
    if ( v20 > 0 )
      v21 = 1;
    if ( !v21 )
    {
      pvData = 3;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      pvData = 0;
      v22 = CreateThread(0, 0, ShutdownSelfThread, 0, 0, &pvData);
      if ( v22 )
        CloseHandle(v22);
      else
        GetLastScode();
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v28);
  return 0;
}

```

## disassembly

```asm
0x180215da0  push    rbx
0x180215da2  push    rsi
0x180215da3  push    rdi
0x180215da4  push    r14
0x180215da6  mov     eax, 10B8h
0x180215dab  call    _alloca_probe
0x180215db0  sub     rsp, rax
0x180215db3  mov     rax, cs:__security_cookie
0x180215dba  xor     rax, rsp
0x180215dbd  mov     [rsp+10D8h+var_38], rax
0x180215dc5  xor     ebx, ebx
0x180215dc7  mov     [rsp+10D8h+var_1068], ebx
0x180215dcb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180215dcf  mov     [rsp+10D8h+var_1060], rsi
0x180215dd4  lea     rcx, [rsp+10D8h+var_1068]; this
0x180215dd9  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x180215dde  nop
0x180215ddf  mov     [rsp+10D8h+pvData], 0C0041801h
0x180215de7  mov     r9d, 1324h
0x180215ded  lea     r8, aU_0; "%u"
0x180215df4  mov     edx, 800h; unsigned __int64
0x180215df9  lea     rcx, [rsp+10D8h+var_1038]; wchar_t *
0x180215e01  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180215e06  lea     rdx, [rsp+10D8h+var_1038]
0x180215e0e  lea     rcx, [rsp+10D8h+pvData]
0x180215e13  call    ??$IndexerCorruption@AEAJAEAY0IAA@_W@SearchIndexerTelemetry@@SAXAEAJAEAY0IAA@_W@Z; SearchIndexerTelemetry::IndexerCorruption<long &,wchar_t (&)[2048]>(long &,wchar_t (&)[2048])
0x180215e18  xor     r9d, r9d; Context
0x180215e1b  xor     r8d, r8d; Parameter
0x180215e1e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180215e25  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180215e2c  call    cs:__imp_InitOnceExecuteOnce
0x180215e32  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180215e38  jz      loc_180216040
0x180215e3e  call    PerUserCatalogNameForCorruption__GetCatalog
0x180215e43  test    rax, rax
0x180215e46  jz      loc_180216040
0x180215e4c  call    PerUserCatalogNameForCorruption__GetCatalog
0x180215e51  mov     rdi, rax
0x180215e54  mov     [rsp+10D8h+var_1078], rax
0x180215e59  mov     rdx, rax
0x180215e5c  lea     rcx, [rsp+10D8h+lpSubKey]
0x180215e64  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180215e69  nop
0x180215e6a  lea     r8d, [rbx+22h]
0x180215e6e  lea     rdx, aSoftwareMicros_7; "\\SOFTWARE\\Microsoft\\Windows Search"
0x180215e75  lea     rcx, [rsp+10D8h+lpSubKey]; Src
0x180215e7d  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180215e82  mov     [rsp+10D8h+hkey], rbx
0x180215e87  lea     rcx, [rsp+10D8h+hkey]
0x180215e8c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180215e91  lea     rdx, [rsp+10D8h+lpSubKey]
0x180215e99  cmp     [rsp+10D8h+var_1040], 7
0x180215ea2  cmova   rdx, [rsp+10D8h+lpSubKey]; lpSubKey
0x180215eab  mov     [rsp+10D8h+lpdwDisposition], rbx; lpdwDisposition
0x180215eb0  mov     [rsp+10D8h+phkResult], rax; phkResult
0x180215eb5  mov     [rsp+10D8h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180215eba  mov     [rsp+10D8h+samDesired], 0F003Fh; samDesired
0x180215ec2  mov     [rsp+10D8h+dwOptions], ebx; unsigned int
0x180215ec6  xor     r9d, r9d; lpClass
0x180215ec9  xor     r8d, r8d; Reserved
0x180215ecc  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180215ed3  call    cs:__imp_RegCreateKeyExW
0x180215ed9  mov     rcx, [rsp+10D8h]; this
0x180215ee1  test    eax, eax
0x180215ee3  jz      short loc_180215EF9
0x180215ee5  mov     r9d, eax; char *
0x180215ee8  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180215eef  mov     edx, 0F7h; void *
0x180215ef4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180215ef9  mov     [rsp+10D8h+pvData], ebx
0x180215efd  mov     r9d, 4; dwType
0x180215f03  mov     [rsp+10D8h+samDesired], r9d; cbData
0x180215f08  lea     rax, [rsp+10D8h+pvData]
0x180215f0d  mov     qword ptr [rsp+10D8h+dwOptions], rax; unsigned int
0x180215f12  lea     r8, aSetupcompleted; "SetupCompletedSuccessfully"
0x180215f19  xor     edx, edx; pszSubKey
0x180215f1b  mov     rcx, [rsp+10D8h+hkey]; hkey
0x180215f20  call    cs:__imp_SHSetValueW
0x180215f26  mov     rcx, [rsp+10D8h]; this
0x180215f2e  test    eax, eax
0x180215f30  jz      short loc_180215F47
0x180215f32  mov     r9d, eax; char *
0x180215f35  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180215f3c  mov     edx, 0FBh; void *
0x180215f41  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180215f47  lea     rcx, [rsp+10D8h+hkey]
0x180215f4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180215f51  nop
0x180215f52  lea     rcx, [rsp+10D8h+lpSubKey]
0x180215f5a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180215f5f  nop
0x180215f60  jmp     short loc_180215F6D
0x180215f62  xor     ebx, ebx
0x180215f64  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180215f68  mov     rdi, [rsp+10D8h+var_1078]
0x180215f6d  mov     rax, rsi
0x180215f70  inc     rax
0x180215f73  cmp     [rdi+rax*2], bx
0x180215f77  jnz     short loc_180215F70
0x180215f79  lea     r14, [rax+1]
0x180215f7d  mov     eax, 2
0x180215f82  mul     r14
0x180215f85  cmovb   rax, rsi
0x180215f89  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180215f90  mov     rcx, rax; unsigned __int64
0x180215f93  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180215f98  mov     r11, rax
0x180215f9b  mov     [rsp+10D8h+hkey], rax
0x180215fa0  test    rax, rax
0x180215fa3  jnz     short loc_180215FB4
0x180215fa5  mov     edi, 8007000Eh
0x180215faa  mov     r9d, edi
0x180215fad  mov     edx, 101h
0x180215fb2  jmp     short loc_180215FD0
0x180215fb4  mov     r8, rdi; wchar_t *
0x180215fb7  mov     rdx, r14; unsigned __int64
0x180215fba  mov     rcx, r11; wchar_t *
0x180215fbd  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180215fc2  mov     edi, eax
0x180215fc4  test    eax, eax
0x180215fc6  jns     short loc_180216000
0x180215fc8  mov     r9d, eax; char *
0x180215fcb  mov     edx, 103h; void *
0x180215fd0  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180215fd7  mov     rcx, [rsp+10D8h]; this
0x180215fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180215fe4  lea     rcx, [rsp+10D8h+hkey]; this
0x180215fe9  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x180215fee  nop
0x180215fef  lea     rcx, [rsp+10D8h+var_1068]; this
0x180215ff4  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x180215ff9  mov     eax, edi
0x180215ffb  jmp     loc_180216135
0x180216000  mov     [rsp+10D8h+hkey], rbx
0x180216005  mov     qword ptr [rsp+10D8h+samDesired], rbx; lpThreadId
0x18021600a  mov     [rsp+10D8h+dwOptions], ebx; dwCreationFlags
0x18021600e  mov     r9, r11; lpParameter
0x180216011  lea     r8, ResetUserCatalog; lpStartAddress
0x180216018  xor     edx, edx; dwStackSize
0x18021601a  xor     ecx, ecx; lpThreadAttributes
0x18021601c  call    cs:__imp_CreateThread
0x180216022  mov     [rsp+10D8h+var_1078], rax
0x180216027  lea     rcx, [rsp+10D8h+var_1078]
0x18021602c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180216031  lea     rcx, [rsp+10D8h+hkey]; this
0x180216036  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x18021603b  jmp     loc_180216129
0x180216040  mov     [rsp+10D8h+hkey], rbx
0x180216045  lea     r9, [rsp+10D8h+var_1038]; wchar_t *
0x18021604d  lea     rdi, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search"
0x180216054  mov     r8, rdi; wchar_t *
0x180216057  mov     rsi, 0FFFFFFFF80000002h
0x18021605e  mov     rdx, rsi; HKEY
0x180216061  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x180216066  lea     rdx, [rsp+10D8h+var_1038]
0x18021606e  test    al, al
0x180216070  cmovz   rdx, rdi; lpSubKey
0x180216074  lea     rax, [rsp+10D8h+hkey]
0x180216079  mov     qword ptr [rsp+10D8h+dwOptions], rax; phkResult
0x18021607e  mov     r9d, 0F003Fh; samDesired
0x180216084  xor     r8d, r8d; ulOptions
0x180216087  mov     rcx, rsi; hKey
0x18021608a  call    cs:__imp_RegOpenKeyExW
0x180216090  test    eax, eax
0x180216092  jle     short loc_18021609E
0x180216094  movzx   eax, ax
0x180216097  or      eax, 80070000h
0x18021609c  test    eax, eax
0x18021609e  js      short loc_1802160DC
0x1802160a0  mov     [rsp+10D8h+pvData], 3
0x1802160a8  mov     r9d, 4; dwType
0x1802160ae  mov     [rsp+10D8h+samDesired], r9d; cbData
0x1802160b3  lea     rax, [rsp+10D8h+pvData]
0x1802160b8  mov     qword ptr [rsp+10D8h+dwOptions], rax; pvData
0x1802160bd  lea     r8, aRebuildindex; "RebuildIndex"
0x1802160c4  xor     edx, edx; pszSubKey
0x1802160c6  mov     rcx, [rsp+10D8h+hkey]; hkey
0x1802160cb  call    cs:__imp_SHSetValueW
0x1802160d1  mov     rcx, [rsp+10D8h+hkey]; hKey
0x1802160d6  call    cs:__imp_RegCloseKey
0x1802160dc  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1802160e2  jnz     short loc_180216129
0x1802160e4  mov     [rsp+10D8h+pvData], ebx
0x1802160e8  lea     rax, [rsp+10D8h+pvData]
0x1802160ed  mov     qword ptr [rsp+10D8h+samDesired], rax; lpThreadId
0x1802160f2  mov     [rsp+10D8h+dwOptions], ebx; dwCreationFlags
0x1802160f6  xor     r9d, r9d; lpParameter
0x1802160f9  lea     r8, ShutdownSelfThread; lpStartAddress
0x180216100  xor     edx, edx; dwStackSize
0x180216102  xor     ecx, ecx; lpThreadAttributes
0x180216104  call    cs:__imp_CreateThread
0x18021610a  test    rax, rax
0x18021610d  jz      short loc_18021611A
0x18021610f  mov     rcx, rax; hObject
0x180216112  call    cs:__imp_CloseHandle
0x180216118  jmp     short loc_18021611F
0x18021611a  call    ?GetLastScode@@YAJXZ; GetLastScode(void)
0x18021611f  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x180216129  lea     rcx, [rsp+10D8h+var_1068]; this
0x18021612e  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x180216133  xor     eax, eax
0x180216135  mov     rcx, [rsp+10D8h+var_38]
0x18021613d  xor     rcx, rsp; StackCookie
0x180216140  call    __security_check_cookie
0x180216145  add     rsp, 10B8h
0x18021614c  pop     r14
0x18021614e  pop     rdi
0x18021614f  pop     rsi
0x180216150  pop     rbx
0x180216151  retn
```
