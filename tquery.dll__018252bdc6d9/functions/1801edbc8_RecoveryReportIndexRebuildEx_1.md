# RecoveryReportIndexRebuildEx_1

- ea: `0x1801edbc8`
- end: `0x1801edfc6`
- name: `RecoveryReportIndexRebuildEx_1`
- size: `1022`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801e9e70`

## callees

- `0x18002e6fc`
- `0x180043d18`
- `0x18006380c`
- `0x180075d8c`
- `0x180078410`
- `0x18008b084`
- `0x18008facc`
- `0x1800983c0`
- `0x18009e510`
- `0x18009e614`
- `0x1800f7bfc`
- `0x1801199cc`
- `0x18013edc0`
- `0x1801710e4`
- `0x180188d90`
- `0x18018e778`
- `0x18019b924`
- `0x1801a40f0`
- `0x1801a444c`
- `0x1801a8e38`
- `0x1801ec8fc`
- `0x1801edbc8`
- `0x1801eec00`
- `0x1801f9f0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801edea4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801edea4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801edc35`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801edc35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801edf13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801edf13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801edf5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801edf5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801edd5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801edd5e`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801eddab`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801edf54`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801eddab`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1801edf54`

## string_xrefs

- `0x1801edd73`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801eddc0`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801ede58`: `onecoreuap\base\appmodel\Search\common\include\recovery.h`
- `0x1801edd9d`: `SetupCompletedSuccessfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecoveryReportIndexRebuildEx_1(__int64 a1, struct CEventLog *a2, __int64 a3, const OLECHAR *a4)
{
  const wchar_t *v7; // rcx
  const wchar_t *Catalog; // rdi
  const OLECHAR *v9; // rdx
  HKEY *phkResult; // rax
  const WCHAR *v11; // rdx
  unsigned int Key; // eax
  unsigned int v13; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // kr10_8
  wchar_t *v18; // rax
  unsigned int v19; // edi
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  void *v23; // r11
  bool v25; // al
  wchar_t *v26; // rdx
  LSTATUS v27; // eax
  bool v28; // sf
  unsigned int dwOptions; // [rsp+20h] [rbp-A18h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-A18h]
  HKEY hkey; // [rsp+50h] [rbp-9E8h] BYREF
  int pvData; // [rsp+58h] [rbp-9E0h] BYREF
  HANDLE Thread; // [rsp+60h] [rbp-9D8h] BYREF
  int v34; // [rsp+68h] [rbp-9D0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-9C8h]
  LPCWSTR lpSubKey[5]; // [rsp+78h] [rbp-9C0h] BYREF
  wchar_t v37; // [rsp+A0h] [rbp-998h] BYREF
  _BYTE v38[160]; // [rsp+A8h] [rbp-990h] BYREF
  _BYTE v39[2248]; // [rsp+148h] [rbp-8F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A38h] [rbp+0h]

  v34 = 0;
  v35 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v34);
  LogIndexCorruptionEx_0(a2, a3, a4);
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled && PerUserCatalogNameForCorruption::GetCatalog() )
  {
    Catalog = (const wchar_t *)PerUserCatalogNameForCorruption::GetCatalog();
    Thread = (HANDLE)Catalog;
    if ( a2 )
    {
      CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)&v37, a2);
      v9 = &psz;
      if ( Catalog )
        v9 = Catalog;
      CLMString::operator=(v38, v9);
      if ( !a4 )
        a4 = &psz;
      CLMString::operator=(v39, a4);
      CSearchEventEntry::SetError((CSearchEventEntry *)&v37, -1073473535);
      CSearchEventEntry::ReportError((CSearchEventEntry *)&v37, 0xC0001B80, L"The catalog is corrupt", 0);
      CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)&v37);
    }
    try
    {
      std::wstring::wstring(lpSubKey);
      std::wstring::_Append<wchar_t>(lpSubKey);
      hkey = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
      v11 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v11 = lpSubKey[0];
      Key = RegCreateKeyExW(HKEY_USERS, v11, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
      if ( Key )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)Key,
          dwOptions);
      pvData = 0;
      v13 = SHSetValueW(hkey, 0, L"SetupCompletedSuccessfully", 4u, &pvData, 4u);
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
          (const char *)v13,
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
    v14 = -1;
    do
      ++v14;
    while ( Catalog[v14] );
    v15 = v14 + 1;
    v17 = v14 + 1;
    v16 = 2 * (v14 + 1);
    if ( !is_mul_ok(v17, 2u) )
      v16 = -1;
    v18 = (wchar_t *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    hkey = (HKEY)v18;
    if ( !v18 )
    {
      v19 = -2147024882;
      v20 = 2147942414LL;
      v21 = 257;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\recovery.h",
        (const char *)v20,
        dwOptionsa);
      SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
      CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v34);
      return v19;
    }
    v22 = StringCchCopyW(v18, v15, Catalog);
    v19 = v22;
    if ( v22 < 0 )
    {
      v20 = (unsigned int)v22;
      v21 = 259;
      goto LABEL_24;
    }
    hkey = 0;
    Thread = CreateThread(0, 0, ResetUserCatalog, v23, 0, 0);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Thread);
    SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&hkey);
  }
  else
  {
    hkey = 0;
    v25 = MapRegistryKeyPath(v7, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", &v37);
    v26 = &v37;
    if ( !v25 )
      v26 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
    v27 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v26, 0, 0xF003Fu, &hkey);
    v28 = v27 < 0;
    if ( v27 > 0 )
      v28 = 1;
    if ( !v28 )
    {
      pvData = 3;
      SHSetValueW(hkey, 0, L"RebuildIndex", 4u, &pvData, 4u);
      RegCloseKey(hkey);
    }
    if ( !g_fStopLogged )
    {
      ShutdownSelf_0(a2, (__int64)L"The catalog is corrupt");
      g_fStopLogged = 1;
    }
  }
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v34);
  return 0;
}

```

## disassembly

```asm
0x1801edbc8  mov     [rsp+arg_0], rbx
0x1801edbcd  mov     [rsp+arg_8], rsi
0x1801edbd2  push    rdi
0x1801edbd3  push    r14
0x1801edbd5  push    r15
0x1801edbd7  sub     rsp, 0A20h
0x1801edbde  mov     rax, cs:__security_cookie
0x1801edbe5  xor     rax, rsp
0x1801edbe8  mov     [rsp+0A38h+var_28], rax
0x1801edbf0  mov     r15, r9
0x1801edbf3  mov     rdi, r8
0x1801edbf6  mov     r14, rdx
0x1801edbf9  xor     ebx, ebx
0x1801edbfb  mov     [rsp+0A38h+var_9D0], ebx
0x1801edbff  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801edc03  mov     [rsp+0A38h+var_9C8], rsi
0x1801edc08  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1801edc0d  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x1801edc12  nop
0x1801edc13  mov     r8, r15
0x1801edc16  mov     rdx, rdi
0x1801edc19  mov     rcx, r14
0x1801edc1c  call    LogIndexCorruptionEx_0
0x1801edc21  xor     r9d, r9d; Context
0x1801edc24  xor     r8d, r8d; Parameter
0x1801edc27  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801edc2e  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1801edc35  call    cs:__imp_InitOnceExecuteOnce
0x1801edc3b  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1801edc41  jz      loc_1801EDEC8
0x1801edc47  call    PerUserCatalogNameForCorruption__GetCatalog
0x1801edc4c  test    rax, rax
0x1801edc4f  jz      loc_1801EDEC8
0x1801edc55  call    PerUserCatalogNameForCorruption__GetCatalog
0x1801edc5a  mov     rdi, rax
0x1801edc5d  mov     [rsp+0A38h+var_9D8], rax
0x1801edc62  test    r14, r14
0x1801edc65  jz      loc_1801EDCEE
0x1801edc6b  mov     rdx, r14; struct CEventLog *
0x1801edc6e  lea     rcx, [rsp+0A38h+var_998]; this
0x1801edc76  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1801edc7b  nop
0x1801edc7c  lea     r14, psz
0x1801edc83  mov     rdx, r14
0x1801edc86  test    rdi, rdi
0x1801edc89  cmovnz  rdx, rdi
0x1801edc8d  lea     rcx, [rsp+0A38h+var_990]
0x1801edc95  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801edc9a  test    r15, r15
0x1801edc9d  cmovz   r15, r14
0x1801edca1  mov     rdx, r15
0x1801edca4  lea     rcx, [rsp+0A38h+var_8F0]
0x1801edcac  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1801edcb1  mov     edx, 0C0041801h; int
0x1801edcb6  lea     rcx, [rsp+0A38h+var_998]; this
0x1801edcbe  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1801edcc3  xor     r9d, r9d
0x1801edcc6  lea     r8, aTheCatalogIsCo; "The catalog is corrupt"
0x1801edccd  mov     edx, 0C0001B80h; unsigned int
0x1801edcd2  lea     rcx, [rsp+0A38h+var_998]; this
0x1801edcda  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1801edcdf  nop
0x1801edce0  lea     rcx, [rsp+0A38h+var_998]; this
0x1801edce8  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1801edced  nop
0x1801edcee  mov     rdx, rdi
0x1801edcf1  lea     rcx, [rsp+0A38h+lpSubKey]
0x1801edcf6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801edcfb  nop
0x1801edcfc  mov     r8d, 22h ; '"'
0x1801edd02  lea     rdx, aSoftwareMicros_7; "\\SOFTWARE\\Microsoft\\Windows Search"
0x1801edd09  lea     rcx, [rsp+0A38h+lpSubKey]; Src
0x1801edd0e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801edd13  mov     [rsp+0A38h+hkey], rbx
0x1801edd18  lea     rcx, [rsp+0A38h+hkey]
0x1801edd1d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801edd22  lea     rdx, [rsp+0A38h+lpSubKey]
0x1801edd27  cmp     [rsp+0A38h+var_9A8], 7
0x1801edd30  cmova   rdx, [rsp+0A38h+lpSubKey]; lpSubKey
0x1801edd36  mov     [rsp+0A38h+lpdwDisposition], rbx; lpdwDisposition
0x1801edd3b  mov     [rsp+0A38h+phkResult], rax; phkResult
0x1801edd40  mov     [rsp+0A38h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1801edd45  mov     [rsp+0A38h+samDesired], 0F003Fh; samDesired
0x1801edd4d  mov     [rsp+0A38h+dwOptions], ebx; unsigned int
0x1801edd51  xor     r9d, r9d; lpClass
0x1801edd54  xor     r8d, r8d; Reserved
0x1801edd57  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1801edd5e  call    cs:__imp_RegCreateKeyExW
0x1801edd64  mov     rcx, [rsp+0A38h]; this
0x1801edd6c  test    eax, eax
0x1801edd6e  jz      short loc_1801EDD84
0x1801edd70  mov     r9d, eax; char *
0x1801edd73  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801edd7a  mov     edx, 0F7h; void *
0x1801edd7f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801edd84  mov     [rsp+0A38h+pvData], ebx
0x1801edd88  mov     r9d, 4; dwType
0x1801edd8e  mov     [rsp+0A38h+samDesired], r9d; cbData
0x1801edd93  lea     rax, [rsp+0A38h+pvData]
0x1801edd98  mov     qword ptr [rsp+0A38h+dwOptions], rax; unsigned int
0x1801edd9d  lea     r8, aSetupcompleted; "SetupCompletedSuccessfully"
0x1801edda4  xor     edx, edx; pszSubKey
0x1801edda6  mov     rcx, [rsp+0A38h+hkey]; hkey
0x1801eddab  call    cs:__imp_SHSetValueW
0x1801eddb1  mov     rcx, [rsp+0A38h]; this
0x1801eddb9  test    eax, eax
0x1801eddbb  jz      short loc_1801EDDD2
0x1801eddbd  mov     r9d, eax; char *
0x1801eddc0  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801eddc7  mov     edx, 0FBh; void *
0x1801eddcc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801eddd2  lea     rcx, [rsp+0A38h+hkey]
0x1801eddd7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801edddc  nop
0x1801edddd  lea     rcx, [rsp+0A38h+lpSubKey]
0x1801edde2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801edde7  nop
0x1801edde8  jmp     short loc_1801EDDF5
0x1801eddea  xor     ebx, ebx
0x1801eddec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801eddf0  mov     rdi, [rsp+0A38h+var_9D8]
0x1801eddf5  mov     rax, rsi
0x1801eddf8  inc     rax
0x1801eddfb  cmp     [rdi+rax*2], bx
0x1801eddff  jnz     short loc_1801EDDF8
0x1801ede01  lea     r14, [rax+1]
0x1801ede05  mov     eax, 2
0x1801ede0a  mul     r14
0x1801ede0d  cmovb   rax, rsi
0x1801ede11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801ede18  mov     rcx, rax; unsigned __int64
0x1801ede1b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801ede20  mov     r11, rax
0x1801ede23  mov     [rsp+0A38h+hkey], rax
0x1801ede28  test    rax, rax
0x1801ede2b  jnz     short loc_1801EDE3C
0x1801ede2d  mov     edi, 8007000Eh
0x1801ede32  mov     r9d, edi
0x1801ede35  mov     edx, 101h
0x1801ede3a  jmp     short loc_1801EDE58
0x1801ede3c  mov     r8, rdi; wchar_t *
0x1801ede3f  mov     rdx, r14; unsigned __int64
0x1801ede42  mov     rcx, r11; wchar_t *
0x1801ede45  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1801ede4a  mov     edi, eax
0x1801ede4c  test    eax, eax
0x1801ede4e  jns     short loc_1801EDE88
0x1801ede50  mov     r9d, eax; char *
0x1801ede53  mov     edx, 103h; void *
0x1801ede58  lea     r8, aOnecoreuapBase_196; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801ede5f  mov     rcx, [rsp+0A38h]; this
0x1801ede67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ede6c  lea     rcx, [rsp+0A38h+hkey]; this
0x1801ede71  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801ede76  nop
0x1801ede77  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1801ede7c  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801ede81  mov     eax, edi
0x1801ede83  jmp     loc_1801EDF9D
0x1801ede88  mov     [rsp+0A38h+hkey], rbx
0x1801ede8d  mov     qword ptr [rsp+0A38h+samDesired], rbx; lpThreadId
0x1801ede92  mov     [rsp+0A38h+dwOptions], ebx; dwCreationFlags
0x1801ede96  mov     r9, r11; lpParameter
0x1801ede99  lea     r8, ResetUserCatalog; lpStartAddress
0x1801edea0  xor     edx, edx; dwStackSize
0x1801edea2  xor     ecx, ecx; lpThreadAttributes
0x1801edea4  call    cs:__imp_CreateThread
0x1801edeaa  mov     [rsp+0A38h+var_9D8], rax
0x1801edeaf  lea     rcx, [rsp+0A38h+var_9D8]
0x1801edeb4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801edeb9  lea     rcx, [rsp+0A38h+hkey]; this
0x1801edebe  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801edec3  jmp     loc_1801EDF91
0x1801edec8  mov     [rsp+0A38h+hkey], rbx
0x1801edecd  lea     r9, [rsp+0A38h+var_998]; wchar_t *
0x1801eded5  lea     rsi, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search"
0x1801ededc  mov     r8, rsi; wchar_t *
0x1801ededf  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1801edee6  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x1801edeeb  lea     rdx, [rsp+0A38h+var_998]
0x1801edef3  test    al, al
0x1801edef5  cmovz   rdx, rsi; lpSubKey
0x1801edef9  lea     rax, [rsp+0A38h+hkey]
0x1801edefe  mov     qword ptr [rsp+0A38h+dwOptions], rax; phkResult
0x1801edf03  mov     r9d, 0F003Fh; samDesired
0x1801edf09  xor     r8d, r8d; ulOptions
0x1801edf0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801edf13  call    cs:__imp_RegOpenKeyExW
0x1801edf19  test    eax, eax
0x1801edf1b  jle     short loc_1801EDF27
0x1801edf1d  movzx   eax, ax
0x1801edf20  or      eax, 80070000h
0x1801edf25  test    eax, eax
0x1801edf27  js      short loc_1801EDF65
0x1801edf29  mov     [rsp+0A38h+pvData], 3
0x1801edf31  mov     r9d, 4; dwType
0x1801edf37  mov     [rsp+0A38h+samDesired], r9d; cbData
0x1801edf3c  lea     rax, [rsp+0A38h+pvData]
0x1801edf41  mov     qword ptr [rsp+0A38h+dwOptions], rax; pvData
0x1801edf46  lea     r8, aRebuildindex; "RebuildIndex"
0x1801edf4d  xor     edx, edx; pszSubKey
0x1801edf4f  mov     rcx, [rsp+0A38h+hkey]; hkey
0x1801edf54  call    cs:__imp_SHSetValueW
0x1801edf5a  mov     rcx, [rsp+0A38h+hkey]; hKey
0x1801edf5f  call    cs:__imp_RegCloseKey
0x1801edf65  cmp     cs:?g_fStopLogged@@3HA, ebx; int g_fStopLogged
0x1801edf6b  jnz     short loc_1801EDF91
0x1801edf6d  lea     rax, aTheCatalogIsCo; "The catalog is corrupt"
0x1801edf74  mov     qword ptr [rsp+0A38h+dwOptions], rax; __int64
0x1801edf79  mov     r8, r15
0x1801edf7c  mov     rdx, rdi
0x1801edf7f  mov     rcx, r14; struct CEventLog *
0x1801edf82  call    ShutdownSelf_0
0x1801edf87  mov     cs:?g_fStopLogged@@3HA, 1; int g_fStopLogged
0x1801edf91  lea     rcx, [rsp+0A38h+var_9D0]; this
0x1801edf96  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x1801edf9b  xor     eax, eax
0x1801edf9d  mov     rcx, [rsp+0A38h+var_28]
0x1801edfa5  xor     rcx, rsp; StackCookie
0x1801edfa8  call    __security_check_cookie
0x1801edfad  lea     r11, [rsp+0A38h+var_18]
0x1801edfb5  mov     rbx, [r11+20h]
0x1801edfb9  mov     rsi, [r11+28h]
0x1801edfbd  mov     rsp, r11
0x1801edfc0  pop     r15
0x1801edfc2  pop     r14
0x1801edfc4  pop     rdi
0x1801edfc5  retn
```
