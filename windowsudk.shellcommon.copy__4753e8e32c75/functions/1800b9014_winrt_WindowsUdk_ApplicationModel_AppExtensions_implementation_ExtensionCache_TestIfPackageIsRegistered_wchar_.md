# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::TestIfPackageIsRegistered(wchar_t const *)

- ea: `0x1800b9014`
- end: `0x1800b94aa`
- name: `?TestIfPackageIsRegistered@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAAXPEB_W@Z`
- size: `1174`
- prototype: `void __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b73bc`

## callees

- `0x1800045c8`
- `0x18000460c`
- `0x180004b40`
- `0x18000fea0`
- `0x180010940`
- `0x180015344`
- `0x180025264`
- `0x180026860`
- `0x180035814`
- `0x180036ef8`
- `0x180036f98`
- `0x180036fd0`
- `0x1800375a4`
- `0x180038008`
- `0x180054098`
- `0x18007795c`
- `0x1800779c4`
- `0x1800819d8`
- `0x18008c938`
- `0x1800afc4c`
- `0x1800b9014`
- `0x1800d97d0`
- `0x18015cb00`
- `0x18015d868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b90fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b90fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b9214`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b9214`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b924f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b924f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800b9145`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800b9145`
- `USERENV!GetProfileType` at `0x1800b90f4`
- `USERENV!GetProfileType` at `0x1800b90f4`

## string_xrefs

- `0x1800b92ce`: `%SystemRoot%\ProgramData\Microsoft\Windows\AppRepository\Packages`
- `0x1800b918c`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::TestIfPackageIsRegistered(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache *this,
        const wchar_t *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rax
  const wchar_t *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // r8
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v8; // rcx
  signed int LastError; // eax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v10; // rcx
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  HKEY *phkResult; // rax
  const WCHAR *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  std::filesystem *v20; // rax
  const struct std::filesystem::path *v21; // rdx
  bool v22; // bl
  std::filesystem *v23; // rax
  const struct std::filesystem::path *v24; // rdx
  bool v25; // bl
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[40]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v34; // [rsp+110h] [rbp+10h] BYREF
  __int64 v35; // [rsp+118h] [rbp+18h]
  DWORD dwFlags; // [rsp+120h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+124h] [rbp+24h] BYREF
  HKEY hkey; // [rsp+128h] [rbp+28h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v40[32]; // [rsp+150h] [rbp+50h] BYREF
  void **v41; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v42[48]; // [rsp+178h] [rbp+78h] BYREF
  LPVOID v43; // [rsp+1A8h] [rbp+A8h]
  _WORD pvData[128]; // [rsp+1B0h] [rbp+B0h] BYREF

  pv = 0;
  memset_0(&v41, 0, 0x40u);
  v3 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v3 + 8LL, &v28);
  v41 = &tip2::test_watcher<tip2::details::merged_data<_tip_ExtensionFactoryTest,_tip_ExtensionFactoryTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v42,
    (struct wil::details::IFailureCallback *)&v41,
    0,
    1);
  v43 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 88);
  v34 = 0;
  v4 = tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::ensure_data(&pv);
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(
    &v34,
    v4);
  v5 = v34;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  std::wstring::_Assign<wchar_t>(v34 + 136, a2, v7);
  dwFlags = 0;
  if ( !GetProfileType(&dwFlags) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *((_DWORD *)v5 + 87) = LastError;
  }
  *((_DWORD *)v5 + 86) = dwFlags;
  *((_BYTE *)v5 + 342) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsTempProfilePBReminderSet(v8);
  *((_BYTE *)v5 + 339) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsRunningOnLocalSystem(v10);
  *((_BYTE *)v5 + 340) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsAuditMode(v11);
  *((_BYTE *)v5 + 341) = GetSystemMetrics(67) != 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(&v34);
  pcbData = 256;
  hkey = 0;
  v12 = std::wstring::wstring(v30, a2);
  v13 = std::wstring::wstring(v33, L"\\Packages\\");
  v14 = std::wstring::wstring(&v28, L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update");
  v15 = std::operator+<wchar_t>(v27, v14, v13);
  std::operator+<wchar_t>(lpSubKey, v15, v12);
  std::filesystem::path::~path((std::filesystem::path *)v27);
  std::filesystem::path::~path((std::filesystem::path *)&v28);
  std::filesystem::path::~path((std::filesystem::path *)v33);
  std::filesystem::path::~path((std::filesystem::path *)v30);
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  v17 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v17 = lpSubKey[0];
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 1u, phkResult)
    || RegGetValueW(hkey, 0, L"PackageFullName", 2u, 0, pvData, &pcbData) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(
                            &pv,
                            &v34)
             + 336LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(&v34);
    if ( pv )
      tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
  }
  else
  {
    v18 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(
                       &pv,
                       &v34)
        + 304LL;
    v19 = -1;
    do
      ++v19;
    while ( pvData[v19] );
    std::wstring::_Assign<wchar_t>(v18, pvData, v19);
    tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(&v34);
    do
      ++v6;
    while ( pvData[v6] );
    v34 = pvData;
    v35 = v6;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v32, &v34);
    v34 = L"%SystemRoot%\\ProgramData\\Microsoft\\Windows\\AppRepository\\Packages";
    v35 = 65;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v31, &v34);
    std::filesystem::operator/(v40, v31, v32);
    std::filesystem::path::~path((std::filesystem::path *)v31);
    std::filesystem::path::~path((std::filesystem::path *)v32);
    v28 = L"ActivationStore.dat";
    v29 = 19;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v27, &v28);
    v20 = (std::filesystem *)std::filesystem::operator/(v30, v40, v27);
    v22 = std::filesystem::exists(v20, v21);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(
                            &pv,
                            &v34)
             + 337LL) = v22;
    tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(&v34);
    std::filesystem::path::~path((std::filesystem::path *)v30);
    std::filesystem::path::~path((std::filesystem::path *)v27);
    v28 = L"machine.pckgdep";
    v29 = 15;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v27, &v28);
    v23 = (std::filesystem *)std::filesystem::operator/(v30, v40, v27);
    v25 = std::filesystem::exists(v23, v24);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(
                            &pv,
                            &v34)
             + 338LL) = v25;
    tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(&v34);
    std::filesystem::path::~path((std::filesystem::path *)v30);
    std::filesystem::path::~path((std::filesystem::path *)v27);
    if ( pv )
      tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
    std::filesystem::path::~path((std::filesystem::path *)v40);
  }
  std::filesystem::path::~path((std::filesystem::path *)lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  tip2::test_watcher<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_watcher<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(&v41);
  if ( pv )
    tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>::Release(pv);
}

```

## disassembly

```asm
0x1800b9014  mov     [rsp-8+arg_0], rbx
0x1800b9019  mov     [rsp-8+arg_10], rsi
0x1800b901e  push    rbp
0x1800b901f  push    rdi
0x1800b9020  push    r14
0x1800b9022  lea     rbp, [rsp-1C0h]
0x1800b902a  sub     rsp, 2C0h
0x1800b9031  mov     rax, cs:__security_cookie
0x1800b9038  xor     rax, rsp
0x1800b903b  mov     [rbp+1D0h+var_20], rax
0x1800b9042  mov     rdi, rdx
0x1800b9045  xor     r14d, r14d
0x1800b9048  mov     [rsp+2D0h+pv], r14
0x1800b904d  xor     edx, edx; Val
0x1800b904f  lea     r8d, [r14+40h]; Size
0x1800b9053  lea     rcx, [rbp+1D0h+var_160]; void *
0x1800b9057  call    memset_0
0x1800b905c  lea     rcx, [rsp+2D0h+pv]
0x1800b9061  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::ensure_data(void)
0x1800b9066  mov     rcx, [rax]
0x1800b9069  add     rcx, 8
0x1800b906d  lea     rdx, [rsp+2D0h+var_260]
0x1800b9072  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800b9077  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_ExtensionFactoryTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_ExtensionFactoryTest,_tip_ExtensionFactoryTest>>::`vftable'
0x1800b907e  mov     [rbp+1D0h+var_160], rax
0x1800b9082  mov     r9b, 1; bool
0x1800b9085  xor     r8d, r8d; struct wil::CallContextInfo *
0x1800b9088  lea     rdx, [rbp+1D0h+var_160]; struct wil::details::IFailureCallback *
0x1800b908c  lea     rcx, [rbp+1D0h+var_158]; this
0x1800b9090  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800b9095  mov     rax, [rsp+2D0h+pv]
0x1800b909a  mov     [rbp+1D0h+var_128], rax
0x1800b90a1  test    rax, rax
0x1800b90a4  jz      short loc_1800B90AD
0x1800b90a6  lock inc dword ptr [rax+160h]
0x1800b90ad  mov     [rbp+1D0h+var_1C0], r14
0x1800b90b1  lea     rcx, [rsp+2D0h+pv]
0x1800b90b6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::ensure_data(void)
0x1800b90bb  mov     rdx, rax
0x1800b90be  lea     rcx, [rbp+1D0h+var_1C0]
0x1800b90c2  call    ??0?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>,wil::err_returncode_policy> const &)
0x1800b90c7  nop
0x1800b90c8  mov     rbx, [rbp+1D0h+var_1C0]
0x1800b90cc  lea     rcx, [rbx+110h]
0x1800b90d3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b90d7  mov     r8, rsi
0x1800b90da  inc     r8
0x1800b90dd  cmp     [rdi+r8*2], r14w
0x1800b90e2  jnz     short loc_1800B90DA
0x1800b90e4  mov     rdx, rdi
0x1800b90e7  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800b90ec  mov     [rbp+1D0h+dwFlags], r14d
0x1800b90f0  lea     rcx, [rbp+1D0h+dwFlags]; dwFlags
0x1800b90f4  call    cs:__imp_GetProfileType
0x1800b90fa  test    eax, eax
0x1800b90fc  jnz     short loc_1800B9116
0x1800b90fe  call    cs:__imp_GetLastError
0x1800b9104  test    eax, eax
0x1800b9106  jle     short loc_1800B9110
0x1800b9108  movzx   eax, ax
0x1800b910b  or      eax, 80070000h
0x1800b9110  mov     [rbx+15Ch], eax
0x1800b9116  mov     eax, [rbp+1D0h+dwFlags]
0x1800b9119  mov     [rbx+158h], eax
0x1800b911f  call    ?IsTempProfilePBReminderSet@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA_NXZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsTempProfilePBReminderSet(void)
0x1800b9124  mov     [rbx+156h], al
0x1800b912a  call    ?IsRunningOnLocalSystem@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA_NXZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsRunningOnLocalSystem(void)
0x1800b912f  mov     [rbx+153h], al
0x1800b9135  call    ?IsAuditMode@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA_NXZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsAuditMode(void)
0x1800b913a  mov     [rbx+154h], al
0x1800b9140  mov     ecx, 43h ; 'C'; nIndex
0x1800b9145  call    cs:__imp_GetSystemMetrics
0x1800b914b  test    eax, eax
0x1800b914d  setnz   al
0x1800b9150  mov     [rbx+155h], al
0x1800b9156  lea     rcx, [rbp+1D0h+var_1C0]
0x1800b915a  call    ??1?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(void)
0x1800b915f  mov     [rbp+1D0h+var_1AC], 100h
0x1800b9166  mov     [rbp+1D0h+hkey], r14
0x1800b916a  mov     rdx, rdi
0x1800b916d  lea     rcx, [rbp+1D0h+var_240]
0x1800b9171  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800b9176  mov     rdi, rax
0x1800b9179  lea     rdx, aPackages; "\\Packages\\"
0x1800b9180  lea     rcx, [rbp+1D0h+var_1E0]
0x1800b9184  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800b9189  mov     rbx, rax
0x1800b918c  lea     rdx, ?c_shellUpdateRegKey@Update@Shell@Internal@Windows@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b9193  lea     rcx, [rsp+2D0h+var_260]
0x1800b9198  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800b919d  nop
0x1800b919e  mov     r8, rbx
0x1800b91a1  mov     rdx, rax
0x1800b91a4  lea     rcx, [rsp+2D0h+var_288]
0x1800b91a9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800b91ae  nop
0x1800b91af  mov     r8, rdi
0x1800b91b2  mov     rdx, rax
0x1800b91b5  lea     rcx, [rbp+1D0h+lpSubKey]
0x1800b91b9  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@0@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring &&)
0x1800b91be  nop
0x1800b91bf  lea     rcx, [rsp+2D0h+var_288]; this
0x1800b91c4  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b91c9  nop
0x1800b91ca  lea     rcx, [rsp+2D0h+var_260]; this
0x1800b91cf  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b91d4  nop
0x1800b91d5  lea     rcx, [rbp+1D0h+var_1E0]; this
0x1800b91d9  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b91de  nop
0x1800b91df  lea     rcx, [rbp+1D0h+var_240]; this
0x1800b91e3  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b91e8  lea     rcx, [rbp+1D0h+hkey]
0x1800b91ec  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800b91f1  lea     rdx, [rbp+1D0h+lpSubKey]
0x1800b91f5  cmp     [rbp+1D0h+var_188], 7
0x1800b91fa  cmova   rdx, [rbp+1D0h+lpSubKey]; lpSubKey
0x1800b91ff  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800b9204  mov     r9d, 1; samDesired
0x1800b920a  xor     r8d, r8d; ulOptions
0x1800b920d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b9214  call    cs:__imp_RegOpenKeyExW
0x1800b921a  test    eax, eax
0x1800b921c  jnz     loc_1800B9421
0x1800b9222  lea     rax, [rbp+1D0h+var_1AC]
0x1800b9226  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800b922b  lea     rax, [rbp+1D0h+var_120]
0x1800b9232  mov     [rsp+2D0h+pvData], rax; pvData
0x1800b9237  mov     [rsp+2D0h+phkResult], r14; pdwType
0x1800b923c  mov     r9d, 2; dwFlags
0x1800b9242  lea     r8, aPackagefullnam_0; "PackageFullName"
0x1800b9249  xor     edx, edx; lpSubKey
0x1800b924b  mov     rcx, [rbp+1D0h+hkey]; hkey
0x1800b924f  call    cs:__imp_RegGetValueW
0x1800b9255  test    eax, eax
0x1800b9257  jnz     loc_1800B9421
0x1800b925d  lea     rdx, [rbp+1D0h+var_1C0]
0x1800b9261  lea     rcx, [rsp+2D0h+pv]
0x1800b9266  call    ??C?$tip_test@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(void)
0x1800b926b  nop
0x1800b926c  mov     rcx, [rax]
0x1800b926f  add     rcx, 130h
0x1800b9276  lea     rax, [rbp+1D0h+var_120]
0x1800b927d  mov     r8, rsi
0x1800b9280  inc     r8
0x1800b9283  cmp     [rax+r8*2], r14w
0x1800b9288  jnz     short loc_1800B9280
0x1800b928a  lea     rdx, [rbp+1D0h+var_120]
0x1800b9291  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800b9296  nop
0x1800b9297  lea     rcx, [rbp+1D0h+var_1C0]
0x1800b929b  call    ??1?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(void)
0x1800b92a0  lea     rax, [rbp+1D0h+var_120]
0x1800b92a7  inc     rsi
0x1800b92aa  cmp     [rax+rsi*2], r14w
0x1800b92af  jnz     short loc_1800B92A7
0x1800b92b1  lea     rax, [rbp+1D0h+var_120]
0x1800b92b8  mov     [rbp+1D0h+var_1C0], rax
0x1800b92bc  mov     [rbp+1D0h+var_1B8], rsi
0x1800b92c0  lea     rdx, [rbp+1D0h+var_1C0]
0x1800b92c4  lea     rcx, [rbp+1D0h+var_200]
0x1800b92c8  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800b92cd  nop
0x1800b92ce  lea     rax, aSystemrootProg; "%SystemRoot%\\ProgramData\\Microsoft\\W"...
0x1800b92d5  mov     [rbp+1D0h+var_1C0], rax
0x1800b92d9  mov     [rbp+1D0h+var_1B8], 41h ; 'A'
0x1800b92e1  lea     rdx, [rbp+1D0h+var_1C0]
0x1800b92e5  lea     rcx, [rbp+1D0h+var_220]
0x1800b92e9  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800b92ee  nop
0x1800b92ef  lea     r8, [rbp+1D0h+var_200]
0x1800b92f3  lea     rdx, [rbp+1D0h+var_220]
0x1800b92f7  lea     rcx, [rbp+1D0h+var_180]
0x1800b92fb  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800b9300  nop
0x1800b9301  lea     rcx, [rbp+1D0h+var_220]; this
0x1800b9305  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b930a  nop
0x1800b930b  lea     rcx, [rbp+1D0h+var_200]; this
0x1800b930f  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b9314  lea     rax, aActivationstor_0; "ActivationStore.dat"
0x1800b931b  mov     [rsp+2D0h+var_260], rax
0x1800b9320  mov     [rsp+2D0h+var_258], 13h
0x1800b9329  lea     rdx, [rsp+2D0h+var_260]
0x1800b932e  lea     rcx, [rsp+2D0h+var_288]
0x1800b9333  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800b9338  nop
0x1800b9339  lea     r8, [rsp+2D0h+var_288]
0x1800b933e  lea     rdx, [rbp+1D0h+var_180]
0x1800b9342  lea     rcx, [rbp+1D0h+var_240]
0x1800b9346  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800b934b  nop
0x1800b934c  mov     rcx, rax; this
0x1800b934f  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800b9354  mov     bl, al
0x1800b9356  lea     rdx, [rbp+1D0h+var_1C0]
0x1800b935a  lea     rcx, [rsp+2D0h+pv]
0x1800b935f  call    ??C?$tip_test@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(void)
0x1800b9364  mov     rcx, [rax]
0x1800b9367  mov     [rcx+151h], bl
0x1800b936d  lea     rcx, [rbp+1D0h+var_1C0]
0x1800b9371  call    ??1?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(void)
0x1800b9376  nop
0x1800b9377  lea     rcx, [rbp+1D0h+var_240]; this
0x1800b937b  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b9380  nop
0x1800b9381  lea     rcx, [rsp+2D0h+var_288]; this
0x1800b9386  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b938b  lea     rax, aMachinePckgdep; "machine.pckgdep"
0x1800b9392  mov     [rsp+2D0h+var_260], rax
0x1800b9397  mov     [rsp+2D0h+var_258], 0Fh
0x1800b93a0  lea     rdx, [rsp+2D0h+var_260]
0x1800b93a5  lea     rcx, [rsp+2D0h+var_288]
0x1800b93aa  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800b93af  nop
0x1800b93b0  lea     r8, [rsp+2D0h+var_288]
0x1800b93b5  lea     rdx, [rbp+1D0h+var_180]
0x1800b93b9  lea     rcx, [rbp+1D0h+var_240]
0x1800b93bd  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800b93c2  nop
0x1800b93c3  mov     rcx, rax; this
0x1800b93c6  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800b93cb  mov     bl, al
0x1800b93cd  lea     rdx, [rbp+1D0h+var_1C0]
0x1800b93d1  lea     rcx, [rsp+2D0h+pv]
0x1800b93d6  call    ??C?$tip_test@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(void)
0x1800b93db  mov     rcx, [rax]
0x1800b93de  mov     [rcx+152h], bl
0x1800b93e4  lea     rcx, [rbp+1D0h+var_1C0]
0x1800b93e8  call    ??1?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(void)
0x1800b93ed  nop
0x1800b93ee  lea     rcx, [rbp+1D0h+var_240]; this
0x1800b93f2  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b93f7  nop
0x1800b93f8  lea     rcx, [rsp+2D0h+var_288]; this
0x1800b93fd  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b9402  mov     rcx, [rsp+2D0h+pv]
0x1800b9407  test    rcx, rcx
0x1800b940a  jz      short loc_1800B9416
0x1800b940c  add     rcx, 8
0x1800b9410  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1800b9415  nop
0x1800b9416  lea     rcx, [rbp+1D0h+var_180]; this
0x1800b941a  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b941f  jmp     short loc_1800B9456
0x1800b9421  lea     rdx, [rbp+1D0h+var_1C0]
0x1800b9425  lea     rcx, [rsp+2D0h+pv]
0x1800b942a  call    ??C?$tip_test@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::operator->(void)
0x1800b942f  mov     rcx, [rax]
0x1800b9432  mov     byte ptr [rcx+150h], 1
0x1800b9439  lea     rcx, [rbp+1D0h+var_1C0]
0x1800b943d  call    ??1?$test_data_control@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_data_control<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(void)
0x1800b9442  mov     rcx, [rsp+2D0h+pv]
0x1800b9447  test    rcx, rcx
0x1800b944a  jz      short loc_1800B9456
0x1800b944c  add     rcx, 8
0x1800b9450  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1800b9455  nop
0x1800b9456  lea     rcx, [rbp+1D0h+lpSubKey]; this
0x1800b945a  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b945f  nop
0x1800b9460  lea     rcx, [rbp+1D0h+hkey]
0x1800b9464  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b9469  nop
0x1800b946a  lea     rcx, [rbp+1D0h+var_160]
0x1800b946e  call    ??1?$test_watcher@V?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>::~test_watcher<tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>>(void)
0x1800b9473  nop
0x1800b9474  mov     rcx, [rsp+2D0h+pv]; pv
0x1800b9479  test    rcx, rcx
0x1800b947c  jz      short loc_1800B9483
0x1800b947e  call    ?Release@?$merged_data@U_tip_ExtensionCacheTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ExtensionCacheTest,_tip_ExtensionCacheTest>::Release(void)
0x1800b9483  mov     rcx, [rbp+1D0h+var_20]
0x1800b948a  xor     rcx, rsp; StackCookie
0x1800b948d  call    __security_check_cookie
0x1800b9492  lea     r11, [rsp+2D0h+var_10]
0x1800b949a  mov     rbx, [r11+20h]
0x1800b949e  mov     rsi, [r11+30h]
0x1800b94a2  mov     rsp, r11
0x1800b94a5  pop     r14
0x1800b94a7  pop     rdi
0x1800b94a8  pop     rbp
0x1800b94a9  retn
```
