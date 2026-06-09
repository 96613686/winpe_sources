# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DetermineIfIsUndockedFlightingPackage(wchar_t const *)

- ea: `0x1802b3bcc`
- end: `0x1802b4191`
- name: `?DetermineIfIsUndockedFlightingPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA?AVUndockedFlightingPackageData@12345@PEB_W@Z`
- size: `1477`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006df80`

## callees

- `0x180025264`
- `0x180026860`
- `0x180033198`
- `0x180038f3c`
- `0x1800702a8`
- `0x1800e34bc`
- `0x1800e488c`
- `0x18015cb00`
- `0x1802ae74c`
- `0x1802aeb28`
- `0x1802b1c24`
- `0x1802b1d40`
- `0x1802b1f60`
- `0x1802b1fd4`
- `0x1802b28a8`
- `0x1802b3bcc`
- `0x1802b4e88`
- `0x1802b54f0`
- `0x1802b63b8`
- `0x1802b66ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b3f65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b3f65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1802b3fcc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1802b40c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1802b3fcc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1802b40c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b3fb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b40a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b3fb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b40a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802b3c8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802b3c8b`

## string_xrefs

- `0x1802b3df4`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b3ec6`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4123`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4138`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b414d`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b417e`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b3cac`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1802b3cfb`: `com.microsoft.windows.undockedflighting`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=2
__int64 __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DetermineIfIsUndockedFlightingPackage(
        const WCHAR *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdi
  int v7; // edi
  int v8; // eax
  int v9; // eax
  int Extension; // eax
  int Package; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-1C8h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-1C8h]
  bool v23; // [rsp+40h] [rbp-1A8h] BYREF
  _BYTE v24[7]; // [rsp+41h] [rbp-1A7h] BYREF
  __int64 v25; // [rsp+48h] [rbp-1A0h] BYREF
  __int64 *v26; // [rsp+50h] [rbp-198h] BYREF
  __int64 v27; // [rsp+58h] [rbp-190h] BYREF
  char v28; // [rsp+60h] [rbp-188h]
  const WCHAR *v29; // [rsp+70h] [rbp-178h]
  _BYTE v30[32]; // [rsp+78h] [rbp-170h] BYREF
  __int64 v31; // [rsp+98h] [rbp-150h] BYREF
  _QWORD v32[2]; // [rsp+A0h] [rbp-148h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-128h]
  LPCWCH lpString2[2]; // [rsp+D0h] [rbp-118h] BYREF
  __int64 v36; // [rsp+E0h] [rbp-108h]
  __int64 v37; // [rsp+E8h] [rbp-100h]
  __int64 v38; // [rsp+F0h] [rbp-F8h]
  __int64 v39; // [rsp+F8h] [rbp-F0h]
  __int64 v40; // [rsp+100h] [rbp-E8h]
  __int64 v41; // [rsp+108h] [rbp-E0h]
  __int128 v42; // [rsp+110h] [rbp-D8h]
  int v43; // [rsp+120h] [rbp-C8h]
  __int64 v44; // [rsp+128h] [rbp-C0h]
  __int64 v45; // [rsp+130h] [rbp-B8h]
  char *v46[2]; // [rsp+140h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+150h] [rbp-98h]
  __int64 v48; // [rsp+158h] [rbp-90h]
  __int128 v49; // [rsp+160h] [rbp-88h]
  __int128 v50; // [rsp+170h] [rbp-78h]
  _OWORD v51[4]; // [rsp+180h] [rbp-68h] BYREF
  int v52; // [rsp+1C0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v29 = a1;
  v25 = 0;
  wil::AcquireSRWLockExclusive(
    &v25,
    &winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_srwUndockedFlightingPackageMapLock);
  std::wstring::wstring(&v26, a1);
  v3 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash::operator()(v2, &v26);
  v5 = std::_Hash<std::_Umap_traits<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData,std::_Uhash_compare<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveEqual>,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData>>,0>>::_Find_last<std::wstring>(
         v4,
         v32,
         &v26,
         v3);
  v6 = qword_1805EC6A8;
  if ( *(_QWORD *)(v5 + 8) )
    v6 = *(_QWORD *)(v5 + 8);
  std::filesystem::path::~path((std::filesystem::path *)&v26);
  if ( v6 == qword_1805EC6A8 )
  {
    v31 = 0;
    v26 = &v31;
    v27 = 0;
    v28 = 1;
    v7 = SRCacheManager_Open(0, &v27);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v26);
    if ( v7 >= 0 )
      v7 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (const char *)(unsigned int)v7,
        bIgnoreCase);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v7,
        bIgnoreCase);
    v33 = 0u;
    v34 = 0;
    v8 = StateRepository::Cache::Entity::PkgExtension_NoThrow::FindByName(
           (struct StateRepository::Cache::Manager_NoThrow *)&v31,
           L"com.microsoft.windows.undockedflighting",
           (struct StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *)&v33);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
    v24[0] = 0;
    memset(v51, 0, sizeof(v51));
    v52 = 0;
    v9 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(&v33, 0, v51, v24);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
    while ( v24[0] )
    {
      v23 = 0;
      *(_OWORD *)v46 = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 0;
      Extension = StateRepository::Cache::Entity::PkgExtension_NoThrow::GetExtension(
                    (StateRepository::Cache::Entity::PkgExtension_NoThrow *)v51,
                    (struct StateRepository::Cache::Manager_NoThrow *)&v31,
                    (struct StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46,
                    &v23);
      if ( Extension < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E9,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
          (const char *)(unsigned int)Extension,
          bIgnoreCase);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1EA,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)0x8000FFFFLL,
        !v23,
        (bool)"%lld",
        v46[0]);
      *(_OWORD *)lpString2 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      Package = StateRepository::Cache::Entity::PackageExtension_NoThrow::GetPackage(
                  (StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46,
                  (struct StateRepository::Cache::Manager_NoThrow *)&v31,
                  (struct StateRepository::Cache::Entity::Package_NoThrow *)lpString2,
                  &v23);
      if ( Package < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1EE,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
          (const char *)(unsigned int)Package,
          bIgnoreCasea);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)0x8000FFFFLL,
        !v23,
        (bool)"%lld",
        (const char *)lpString2[0]);
      v32[0] = 1;
      std::wstring::wstring(v30, lpString2[1]);
      std::unordered_map<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveEqual,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData>>>::_Insert_or_assign<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData &>(
        v12,
        &v26,
        v30,
        v32);
      std::filesystem::path::~path((std::filesystem::path *)v30);
      if ( CompareStringOrdinal(a1, -1, lpString2[1], -1, 1) == 2 )
      {
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)lpString2);
        StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46);
        StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v51);
        v13 = v33;
        *(_QWORD *)&v33 = 0;
        if ( v13 )
          SRCacheContext_Close();
        v14 = v31;
        v31 = 0;
        if ( v14 )
          SRCacheManager_Close();
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
        return v32[0];
      }
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)lpString2);
      StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46);
      ++DWORD2(v33);
      v16 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(&v33, 0, v51, v24);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x213,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
          (const char *)(unsigned int)v16,
          bIgnoreCase);
    }
    v32[0] = 0;
    std::wstring::wstring(v30, a1);
    std::unordered_map<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveEqual,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData>>>::_Insert_or_assign<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData &>(
      v17,
      &v26,
      v30,
      v32);
    std::filesystem::path::~path((std::filesystem::path *)v30);
    StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v51);
    v18 = v33;
    *(_QWORD *)&v33 = 0;
    if ( v18 )
      SRCacheContext_Close();
    v19 = v31;
    v31 = 0;
    if ( v19 )
      SRCacheManager_Close();
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
    v32[0] = 0;
    return 0;
  }
  else
  {
    v20 = *(_QWORD *)(v6 + 48);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
    return v20;
  }
}

```

## disassembly

```asm
0x1802b3bcc  mov     [rsp+arg_8], rbx
0x1802b3bd1  mov     [rsp+arg_10], rsi
0x1802b3bd6  push    rdi
0x1802b3bd7  sub     rsp, 1E0h
0x1802b3bde  mov     rax, cs:__security_cookie
0x1802b3be5  xor     rax, rsp
0x1802b3be8  mov     [rsp+1E8h+var_18], rax
0x1802b3bf0  mov     rsi, rcx
0x1802b3bf3  mov     [rsp+1E8h+var_178], rcx
0x1802b3bf8  xor     ebx, ebx
0x1802b3bfa  mov     [rsp+1E8h+var_1A0], rbx
0x1802b3bff  lea     rdx, ?g_srwUndockedFlightingPackageMapLock@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3Vsrwlock@wil@@A; wil::srwlock winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_srwUndockedFlightingPackageMapLock
0x1802b3c06  lea     rcx, [rsp+1E8h+var_1A0]
0x1802b3c0b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1802b3c10  nop
0x1802b3c11  mov     rdx, rsi
0x1802b3c14  lea     rcx, [rsp+1E8h+var_198]
0x1802b3c19  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802b3c1e  nop
0x1802b3c1f  lea     rdx, [rsp+1E8h+var_198]
0x1802b3c24  call    ??RCaseInsensitiveHash@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash::operator()(std::wstring const &)
0x1802b3c29  mov     r9, rax
0x1802b3c2c  lea     r8, [rsp+1E8h+var_198]
0x1802b3c31  lea     rdx, [rsp+1E8h+var_148]
0x1802b3c39  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveHash@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UCaseInsensitiveEqual@45678@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData,std::_Uhash_compare<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveEqual>,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1802b3c3e  mov     rdi, cs:qword_1805EC6A8
0x1802b3c45  cmp     [rax+8], rbx
0x1802b3c49  cmovnz  rdi, [rax+8]
0x1802b3c4e  lea     rcx, [rsp+1E8h+var_198]; this
0x1802b3c53  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b3c58  cmp     rdi, cs:qword_1805EC6A8
0x1802b3c5f  jnz     loc_1802B410D
0x1802b3c65  mov     [rsp+1E8h+var_150], rbx
0x1802b3c6d  lea     rax, [rsp+1E8h+var_150]
0x1802b3c75  mov     [rsp+1E8h+var_198], rax
0x1802b3c7a  mov     [rsp+1E8h+var_190], rbx
0x1802b3c7f  mov     [rsp+1E8h+var_188], 1
0x1802b3c84  lea     rdx, [rsp+1E8h+var_190]
0x1802b3c89  xor     ecx, ecx
0x1802b3c8b  call    cs:__imp_SRCacheManager_Open
0x1802b3c91  mov     edi, eax
0x1802b3c93  lea     rcx, [rsp+1E8h+var_198]
0x1802b3c98  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1802b3c9d  test    edi, edi
0x1802b3c9f  jns     short loc_1802B3CBF
0x1802b3ca1  mov     rcx, [rsp+1E8h]; this
0x1802b3ca9  mov     r9d, edi; char *
0x1802b3cac  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b3cb3  mov     edx, 0A5h; void *
0x1802b3cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b3cbd  jmp     short loc_1802B3CC1
0x1802b3cbf  mov     edi, ebx
0x1802b3cc1  mov     rcx, [rsp+1E8h]; this
0x1802b3cc9  test    edi, edi
0x1802b3ccb  js      loc_1802B4120
0x1802b3cd1  xorps   xmm0, xmm0
0x1802b3cd4  movups  [rsp+1E8h+var_138], xmm0
0x1802b3cdc  mov     qword ptr [rsp+1E8h+var_138], rbx
0x1802b3ce4  mov     dword ptr [rsp+1E8h+var_138+8], ebx
0x1802b3ceb  mov     [rsp+1E8h+var_128], rbx
0x1802b3cf3  lea     r8, [rsp+1E8h+var_138]; struct StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *
0x1802b3cfb  lea     rdx, aComMicrosoftWi_9; "com.microsoft.windows.undockedflighting"
0x1802b3d02  lea     rcx, [rsp+1E8h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b3d0a  call    ?FindByName@PkgExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEB_WAEAVPkgExtensionIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::FindByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow &)
0x1802b3d0f  mov     rcx, [rsp+1E8h]; this
0x1802b3d17  test    eax, eax
0x1802b3d19  js      loc_1802B4135
0x1802b3d1f  mov     [rsp+1E8h+var_1A7], bl
0x1802b3d23  xorps   xmm0, xmm0
0x1802b3d26  movdqa  [rsp+1E8h+var_68], xmm0
0x1802b3d2f  xorps   xmm1, xmm1
0x1802b3d32  movdqa  [rsp+1E8h+var_58], xmm1
0x1802b3d3b  movdqa  [rsp+1E8h+var_48], xmm0
0x1802b3d44  movdqa  [rsp+1E8h+var_38], xmm1
0x1802b3d4d  mov     [rsp+1E8h+var_28], ebx
0x1802b3d54  lea     r9, [rsp+1E8h+var_1A7]
0x1802b3d59  lea     r8, [rsp+1E8h+var_68]
0x1802b3d61  xor     edx, edx
0x1802b3d63  lea     rcx, [rsp+1E8h+var_138]
0x1802b3d6b  call    ?Get@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x1802b3d70  mov     rcx, [rsp+1E8h]; this
0x1802b3d78  test    eax, eax
0x1802b3d7a  js      loc_1802B414A
0x1802b3d80  lea     rdi, aLld; "%lld"
0x1802b3d87  cmp     [rsp+1E8h+var_1A7], bl
0x1802b3d8b  jz      loc_1802B4046
0x1802b3d91  mov     [rsp+1E8h+var_1A8], bl
0x1802b3d95  xorps   xmm0, xmm0
0x1802b3d98  movdqa  xmmword ptr [rsp+1E8h+var_A8], xmm0
0x1802b3da1  mov     [rsp+1E8h+var_98], 0
0x1802b3dad  mov     [rsp+1E8h+var_90], rbx
0x1802b3db5  movdqa  [rsp+1E8h+var_88], xmm0
0x1802b3dbe  xorps   xmm1, xmm1
0x1802b3dc1  movdqa  [rsp+1E8h+var_78], xmm1
0x1802b3dca  lea     r9, [rsp+1E8h+var_1A8]; bool *
0x1802b3dcf  lea     r8, [rsp+1E8h+var_A8]; struct StateRepository::Cache::Entity::PackageExtension_NoThrow *
0x1802b3dd7  lea     rdx, [rsp+1E8h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b3ddf  lea     rcx, [rsp+1E8h+var_68]; this
0x1802b3de7  call    ?GetExtension@PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackageExtension_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::GetExtension(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x1802b3dec  mov     rcx, [rsp+1E8h]; this
0x1802b3df4  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802b3dfb  test    eax, eax
0x1802b3dfd  js      loc_1802B415F
0x1802b3e03  mov     rax, [rsp+1E8h+var_A8]
0x1802b3e0b  cmp     [rsp+1E8h+var_1A8], bl
0x1802b3e0f  setz    dl
0x1802b3e12  mov     rcx, [rsp+1E8h]; this
0x1802b3e1a  mov     [rsp+1E8h+var_1B8], rax; char *
0x1802b3e1f  mov     qword ptr [rsp+1E8h+var_1C0], rdi; bool
0x1802b3e24  mov     byte ptr [rsp+1E8h+bIgnoreCase], dl; int
0x1802b3e28  mov     r9d, 8000FFFFh; char *
0x1802b3e2e  mov     edx, 1EAh; void *
0x1802b3e33  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1802b3e38  xorps   xmm0, xmm0
0x1802b3e3b  movdqa  xmmword ptr [rsp+1E8h+lpString2], xmm0
0x1802b3e44  mov     [rsp+1E8h+var_108], rbx
0x1802b3e4c  mov     [rsp+1E8h+var_100], 0
0x1802b3e58  mov     [rsp+1E8h+var_F8], 0
0x1802b3e64  mov     [rsp+1E8h+var_F0], rbx
0x1802b3e6c  mov     [rsp+1E8h+var_E8], rbx
0x1802b3e74  mov     [rsp+1E8h+var_E0], rbx
0x1802b3e7c  movdqa  [rsp+1E8h+var_D8], xmm0
0x1802b3e85  mov     [rsp+1E8h+var_C8], ebx
0x1802b3e8c  mov     [rsp+1E8h+var_C0], rbx
0x1802b3e94  mov     [rsp+1E8h+var_B8], rbx
0x1802b3e9c  lea     r9, [rsp+1E8h+var_1A8]; bool *
0x1802b3ea1  lea     r8, [rsp+1E8h+lpString2]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x1802b3ea9  lea     rdx, [rsp+1E8h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b3eb1  lea     rcx, [rsp+1E8h+var_A8]; this
0x1802b3eb9  call    ?GetPackage@PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1802b3ebe  mov     rcx, [rsp+1E8h]; this
0x1802b3ec6  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802b3ecd  test    eax, eax
0x1802b3ecf  js      loc_1802B416D
0x1802b3ed5  mov     rax, [rsp+1E8h+lpString2]
0x1802b3edd  cmp     [rsp+1E8h+var_1A8], bl
0x1802b3ee1  setz    dl
0x1802b3ee4  mov     rcx, [rsp+1E8h]; this
0x1802b3eec  mov     [rsp+1E8h+var_1B8], rax; char *
0x1802b3ef1  mov     qword ptr [rsp+1E8h+var_1C0], rdi; bool
0x1802b3ef6  mov     byte ptr [rsp+1E8h+bIgnoreCase], dl; char
0x1802b3efa  mov     r9d, 8000FFFFh; char *
0x1802b3f00  mov     edx, 1EFh; void *
0x1802b3f05  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1802b3f0a  mov     [rsp+1E8h+var_148], 1
0x1802b3f16  mov     rdx, [rsp+1E8h+lpString2+8]
0x1802b3f1e  lea     rcx, [rsp+1E8h+var_170]
0x1802b3f23  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802b3f28  nop
0x1802b3f29  lea     r9, [rsp+1E8h+var_148]
0x1802b3f31  lea     r8, [rsp+1E8h+var_170]
0x1802b3f36  lea     rdx, [rsp+1E8h+var_198]
0x1802b3f3b  call    ??$_Insert_or_assign@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UCaseInsensitiveHash@45678@UCaseInsensitiveEqual@45678@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAVUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; std::unordered_map<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveEqual,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData>>>::_Insert_or_assign<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData &>(std::wstring &&,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData &)
0x1802b3f40  nop
0x1802b3f41  lea     rcx, [rsp+1E8h+var_170]; this
0x1802b3f46  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b3f4b  mov     [rsp+1E8h+bIgnoreCase], 1; bIgnoreCase
0x1802b3f53  or      r9d, 0FFFFFFFFh; cchCount2
0x1802b3f57  mov     r8, [rsp+1E8h+lpString2+8]; lpString2
0x1802b3f5f  or      edx, r9d; cchCount1
0x1802b3f62  mov     rcx, rsi; lpString1
0x1802b3f65  call    cs:__imp_CompareStringOrdinal
0x1802b3f6b  nop
0x1802b3f6c  lea     rcx, [rsp+1E8h+lpString2]; this
0x1802b3f74  cmp     eax, 2
0x1802b3f77  jnz     short loc_1802B3FEA
0x1802b3f79  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1802b3f7e  nop
0x1802b3f7f  lea     rcx, [rsp+1E8h+var_A8]; this
0x1802b3f87  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1802b3f8c  nop
0x1802b3f8d  lea     rcx, [rsp+1E8h+var_68]; this
0x1802b3f95  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x1802b3f9a  nop
0x1802b3f9b  mov     rcx, qword ptr [rsp+1E8h+var_138]
0x1802b3fa3  mov     qword ptr [rsp+1E8h+var_138], rbx
0x1802b3fab  test    rcx, rcx
0x1802b3fae  jz      short loc_1802B3FB7
0x1802b3fb0  call    cs:__imp_SRCacheContext_Close
0x1802b3fb6  nop
0x1802b3fb7  mov     rcx, [rsp+1E8h+var_150]
0x1802b3fbf  mov     [rsp+1E8h+var_150], rbx
0x1802b3fc7  test    rcx, rcx
0x1802b3fca  jz      short loc_1802B3FD3
0x1802b3fcc  call    cs:__imp_SRCacheManager_Close
0x1802b3fd2  nop
0x1802b3fd3  lea     rcx, [rsp+1E8h+var_1A0]
0x1802b3fd8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1802b3fdd  mov     rax, [rsp+1E8h+var_148]
0x1802b3fe5  jmp     loc_1802B40E8
0x1802b3fea  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1802b3fef  nop
0x1802b3ff0  lea     rcx, [rsp+1E8h+var_A8]; this
0x1802b3ff8  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1802b3ffd  nop
0x1802b3ffe  jmp     short loc_1802B400E
0x1802b4000  xor     ebx, ebx
0x1802b4002  lea     rdi, aLld; "%lld"
0x1802b4009  mov     rsi, [rsp+1E8h+var_178]
0x1802b400e  inc     dword ptr [rsp+1E8h+var_138+8]
0x1802b4015  lea     r9, [rsp+1E8h+var_1A7]
0x1802b401a  lea     r8, [rsp+1E8h+var_68]
0x1802b4022  xor     edx, edx
0x1802b4024  lea     rcx, [rsp+1E8h+var_138]
0x1802b402c  call    ?Get@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x1802b4031  mov     rcx, [rsp+1E8h]; this
0x1802b4039  test    eax, eax
0x1802b403b  js      loc_1802B417B
0x1802b4041  jmp     loc_1802B3D87
0x1802b4046  mov     [rsp+1E8h+var_148], 0
0x1802b4052  mov     rdx, rsi
0x1802b4055  lea     rcx, [rsp+1E8h+var_170]
0x1802b405a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802b405f  nop
0x1802b4060  lea     r9, [rsp+1E8h+var_148]
0x1802b4068  lea     r8, [rsp+1E8h+var_170]
0x1802b406d  lea     rdx, [rsp+1E8h+var_198]
0x1802b4072  call    ??$_Insert_or_assign@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UCaseInsensitiveHash@45678@UCaseInsensitiveEqual@45678@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAVUndockedFlightingPackageData@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; std::unordered_map<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveHash,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CaseInsensitiveEqual,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData>>>::_Insert_or_assign<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData &>(std::wstring &&,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::UndockedFlightingPackageData &)
0x1802b4077  nop
0x1802b4078  lea     rcx, [rsp+1E8h+var_170]; this
0x1802b407d  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1802b4082  nop
0x1802b4083  lea     rcx, [rsp+1E8h+var_68]; this
0x1802b408b  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x1802b4090  nop
0x1802b4091  mov     rcx, qword ptr [rsp+1E8h+var_138]
0x1802b4099  mov     qword ptr [rsp+1E8h+var_138], rbx
0x1802b40a1  test    rcx, rcx
0x1802b40a4  jz      short loc_1802B40AD
0x1802b40a6  call    cs:__imp_SRCacheContext_Close
0x1802b40ac  nop
0x1802b40ad  mov     rcx, [rsp+1E8h+var_150]
0x1802b40b5  mov     [rsp+1E8h+var_150], rbx
0x1802b40bd  test    rcx, rcx
0x1802b40c0  jz      short loc_1802B40C9
0x1802b40c2  call    cs:__imp_SRCacheManager_Close
0x1802b40c8  nop
0x1802b40c9  lea     rcx, [rsp+1E8h+var_1A0]
0x1802b40ce  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1802b40d3  nop
0x1802b40d4  mov     [rsp+1E8h+var_148], 0
0x1802b40e0  mov     rax, [rsp+1E8h+var_148]
0x1802b40e8  mov     rcx, [rsp+1E8h+var_18]
0x1802b40f0  xor     rcx, rsp; StackCookie
0x1802b40f3  call    __security_check_cookie
0x1802b40f8  lea     r11, [rsp+1E8h+var_8]
0x1802b4100  mov     rbx, [r11+18h]
0x1802b4104  mov     rsi, [r11+20h]
0x1802b4108  mov     rsp, r11
0x1802b410b  pop     rdi
0x1802b410c  retn
0x1802b410d  mov     rbx, [rdi+30h]
0x1802b4111  lea     rcx, [rsp+1E8h+var_1A0]
0x1802b4116  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1802b411b  mov     rax, rbx
0x1802b411e  jmp     short loc_1802B40E8
0x1802b4120  mov     r9d, edi; char *
0x1802b4123  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802b412a  mov     edx, 1D4h; void *
0x1802b412f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802b4135  mov     r9d, eax; char *
0x1802b4138  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802b413f  mov     edx, 1DCh; void *
0x1802b4144  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802b414a  mov     r9d, eax; char *
0x1802b414d  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802b4154  mov     edx, 1E0h; void *
0x1802b4159  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802b415f  mov     r9d, eax; char *
0x1802b4162  mov     edx, 1E9h; void *
0x1802b4167  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802b416d  mov     r9d, eax; char *
0x1802b4170  mov     edx, 1EEh; void *
0x1802b4175  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802b417b  mov     r9d, eax; char *
0x1802b417e  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802b4185  mov     edx, 213h; void *
0x1802b418a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
