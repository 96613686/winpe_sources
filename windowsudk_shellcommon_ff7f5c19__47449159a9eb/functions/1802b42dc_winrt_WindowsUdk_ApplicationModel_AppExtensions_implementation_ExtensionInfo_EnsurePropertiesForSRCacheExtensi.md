# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::EnsurePropertiesForSRCacheExtension(void)

- ea: `0x1802b42dc`
- end: `0x1802b4b0f`
- name: `?EnsurePropertiesForSRCacheExtension@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAAXXZ`
- size: `2099`
- prototype: `void __fastcall(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802b4198`
- `0x1802b894c`
- `0x1802b8b8c`

## callees

- `0x180038f3c`
- `0x180062294`
- `0x1800702a8`
- `0x1800e34bc`
- `0x1800e488c`
- `0x18012a5f0`
- `0x18015cb00`
- `0x1802b1c24`
- `0x1802b1d40`
- `0x1802b1de0`
- `0x1802b1e68`
- `0x1802b1f60`
- `0x1802b1fd4`
- `0x1802b24cc`
- `0x1802b42dc`
- `0x1802b4b18`
- `0x1802b4e88`
- `0x1802b4ed0`
- `0x1802b50a4`
- `0x1802b5198`
- `0x1802b53fc`
- `0x1802b54f0`
- `0x1802b63b8`
- `0x1802b66ec`
- `0x1802b83ac`
- `0x1802b92ac`
- `0x1802ba7cc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b453d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b453d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1802b45cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1802b45cd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b45b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b49dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b45b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802b49dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802b436e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1802b436e`

## string_xrefs

- `0x1802b49ea`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4a40`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4a55`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4a6a`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4a7f`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4a94`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4aa9`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4abe`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4ad3`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4ae8`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b4afd`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1802b438e`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x1802b483b`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1802b47ad`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1802b4620`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b4713`: `OneCore\Internal\Base\Inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1802b4a34`: `SRCache extension or corresponding package for name '%ls' not found for package '%ls'`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::EnsurePropertiesForSRCacheExtension(
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *this)
{
  int v2; // ebx
  const wchar_t **v3; // rsi
  const wchar_t *v4; // rdx
  int v5; // eax
  int Extension; // eax
  int Package; // eax
  const WCHAR *v8; // r8
  bool v9; // zf
  __int64 v10; // rcx
  const wchar_t *v11; // r8
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  int v18; // ebx
  int v19; // eax
  __int64 v20; // r8
  int v21; // ebx
  int v22; // eax
  int v23; // ebx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  char v27; // bl
  _QWORD *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  char v31; // al
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // eax
  const char *v36; // rdx
  __int64 v37; // r8
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  bool *bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  bool v40[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v42[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v43; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  char v45; // [rsp+70h] [rbp-90h]
  _QWORD v46[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v47[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v48[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-38h]
  __int128 v52; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v53; // [rsp+E0h] [rbp-20h]
  LPCWCH lpString1[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v55; // [rsp+100h] [rbp+0h]
  __int128 v56; // [rsp+108h] [rbp+8h]
  __int64 v57; // [rsp+118h] [rbp+18h]
  __int64 v58; // [rsp+120h] [rbp+20h]
  __int64 v59; // [rsp+128h] [rbp+28h]
  __int128 v60; // [rsp+130h] [rbp+30h]
  int v61; // [rsp+140h] [rbp+40h]
  __int64 v62; // [rsp+148h] [rbp+48h]
  __int64 v63; // [rsp+150h] [rbp+50h]
  __int128 v64; // [rsp+160h] [rbp+60h] BYREF
  __int128 v65; // [rsp+170h] [rbp+70h]
  __int128 v66; // [rsp+180h] [rbp+80h]
  __int128 v67; // [rsp+190h] [rbp+90h]
  __int64 v68; // [rsp+1A0h] [rbp+A0h]
  int v69; // [rsp+1A8h] [rbp+A8h]
  __int128 v70; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v71; // [rsp+1C0h] [rbp+C0h]
  __int64 v72; // [rsp+1C8h] [rbp+C8h]
  __int128 v73; // [rsp+1D0h] [rbp+D0h]
  __int128 v74; // [rsp+1E0h] [rbp+E0h]
  __int128 v75; // [rsp+1F0h] [rbp+F0h]
  __int128 v76; // [rsp+200h] [rbp+100h]
  __int128 v77; // [rsp+210h] [rbp+110h] BYREF
  __int128 v78; // [rsp+220h] [rbp+120h]
  __int128 v79; // [rsp+230h] [rbp+130h]
  __int128 v80; // [rsp+240h] [rbp+140h]
  int v81; // [rsp+250h] [rbp+150h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v41 = 0;
  wil::AcquireSRWLockExclusive(&v41, this);
  if ( *((_BYTE *)this + 524) )
    goto LABEL_2;
  v49 = 0;
  v43 = &v49;
  v44 = 0;
  v45 = 1;
  v2 = SRCacheManager_Open(0, &v44);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v43);
  if ( v2 >= 0 )
    v2 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v2,
      bIgnoreCase);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x492,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v2,
      bIgnoreCase);
  v42[0] = this;
  v52 = 0u;
  v53 = 0;
  v3 = (const wchar_t **)((char *)this + 8);
  if ( *((_QWORD *)this + 4) <= 7u )
    v4 = (const wchar_t *)((char *)this + 8);
  else
    v4 = *v3;
  if ( StateRepository::Cache::Entity::PkgExtension_NoThrow::FindByName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v49,
         v4,
         (struct StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *)&v52) >= 0 )
  {
    v40[1] = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    LODWORD(v68) = 0;
    v5 = StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(&v52, 40, &v64, &v40[1]);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4AB,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v5,
        bIgnoreCase);
    if ( v40[1] )
    {
      while ( 1 )
      {
        v40[0] = 0;
        v70 = 0;
        v71 = 0;
        v72 = 0;
        v73 = 0;
        v74 = 0;
        Extension = StateRepository::Cache::Entity::PkgExtension_NoThrow::GetExtension(
                      (StateRepository::Cache::Entity::PkgExtension_NoThrow *)&v64,
                      (struct StateRepository::Cache::Manager_NoThrow *)&v49,
                      (struct StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v70,
                      v40);
        if ( Extension < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4B0,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
            (const char *)(unsigned int)Extension,
            bIgnoreCase);
        if ( v40[0] )
        {
          *(_OWORD *)lpString1 = 0;
          v55 = 0;
          v56 = 0;
          v57 = 0;
          v58 = 0;
          v59 = 0;
          v60 = 0;
          v61 = 0;
          v62 = 0;
          v63 = 0;
          Package = StateRepository::Cache::Entity::PackageExtension_NoThrow::GetPackage(
                      (StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v70,
                      (struct StateRepository::Cache::Manager_NoThrow *)&v49,
                      (struct StateRepository::Cache::Entity::Package_NoThrow *)lpString1,
                      v40);
          if ( Package < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4B4,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
              (const char *)(unsigned int)Package,
              bIgnoreCase);
          if ( v40[0] )
          {
            v8 = (const WCHAR *)((char *)this + 168);
            if ( *((_QWORD *)this + 24) > 7u )
              v8 = *(const WCHAR **)v8;
            if ( CompareStringOrdinal(lpString1[1], -1, v8, -1, 1) == 2 )
            {
              lambda_b14e5a41598cd1bc1c8a106326625b39_::operator()(v42, v66);
              winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::EnsurePropertiesForSRCachePackage(
                this,
                lpString1);
              *((_BYTE *)this + 524) = 1;
              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)lpString1);
              StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v70);
              StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)&v64);
              goto LABEL_23;
            }
          }
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)lpString1);
        }
        StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v70);
      }
    }
    StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)&v64);
  }
  v50 = 0u;
  v51 = 0;
  if ( *((_QWORD *)this + 4) <= 7u )
    v11 = (const wchar_t *)((char *)this + 8);
  else
    v11 = *v3;
  v12 = StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(
          (StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow *)&v50,
          (struct StateRepository::Cache::Manager_NoThrow *)&v49,
          v11);
  v13 = v12;
  if ( v12 >= 0 )
    v13 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C2,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4CC,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
  v40[1] = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v14 = StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::Get(&v50, 42, &v77, &v40[1]);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D0,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
  if ( !v40[1] )
  {
LABEL_77:
    std::wstring::c_str((char *)this + 168);
    v34 = std::wstring::c_str((char *)this + 8);
    v35 = wil::verify_hresult<long>(2147549183LL, v34);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x4F4,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)v35,
      (int)"SRCache extension or corresponding package for name '%ls' not found for package '%ls'",
      v36,
      v37);
  }
  while ( 1 )
  {
    v40[0] = 0;
    v64 = 0;
    v65 = 0u;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    bIgnoreCasea = v40;
    v16 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(&v49, v80, v15, &v64);
    v18 = v16;
    if ( v16 >= 0 )
      v18 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29E,
        (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppExtension.hpp",
        (const char *)(unsigned int)v16,
        (int)v40);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D6,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v18,
        (int)bIgnoreCasea);
    if ( !v40[0] )
      goto LABEL_71;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    bIgnoreCasea = v40;
    v19 = StateRepository::Cache::Entity::Application_NoThrow::Get(&v49, *((_QWORD *)&v64 + 1), v17, &v70);
    v21 = v19;
    if ( v19 >= 0 )
      v21 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
        (const char *)(unsigned int)v19,
        (int)v40);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DA,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v21,
        (int)bIgnoreCasea);
    if ( v40[0] )
      break;
LABEL_70:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v70);
LABEL_71:
    ++DWORD2(v50);
    v32 = StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::Get(&v50, 0, &v77, &v40[1]);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        (const char *)(unsigned int)v32,
        (int)bIgnoreCasea);
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v64);
    if ( !v40[1] )
      goto LABEL_77;
  }
  *(_OWORD *)lpString1 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  bIgnoreCasea = v40;
  v22 = StateRepository::Cache::Entity::Package_NoThrow::Get(&v49, *((_QWORD *)&v70 + 1), v20, lpString1);
  v23 = v22;
  if ( v22 >= 0 )
    v23 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44C,
      (unsigned int)"OneCore\\Internal\\Base\\Inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v22,
      (int)v40);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4DE,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v23,
      (int)bIgnoreCasea);
  if ( !v40[0] )
    goto LABEL_69;
  v24 = (_QWORD *)((char *)this + 168);
  if ( *((_QWORD *)this + 24) > 7u )
    v24 = (_QWORD *)*v24;
  v25 = -1;
  do
    ++v25;
  while ( *((_WORD *)v24 + v25) );
  v26 = -1;
  do
    ++v26;
  while ( lpString1[1][v26] );
  v46[0] = v24;
  v46[1] = v25;
  v47[0] = lpString1[1];
  v47[1] = v26;
  v27 = wil::compare_string_ordinal(v47, v46);
  if ( !(_QWORD)v78 )
    goto LABEL_66;
  v28 = (_QWORD *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) > 7u )
    v28 = (_QWORD *)*v28;
  v29 = -1;
  do
    ++v29;
  while ( *((_WORD *)v28 + v29) );
  v30 = -1;
  do
    ++v30;
  while ( *(_WORD *)(v78 + 2 * v30) );
  v48[0] = v28;
  v48[1] = v29;
  v43 = (__int64 *)v78;
  v44 = v30;
  v9 = (unsigned __int8)wil::compare_string_ordinal(&v43, v48) == 0;
  v31 = 1;
  if ( !v9 )
LABEL_66:
    v31 = 0;
  if ( v27 || !v31 )
  {
LABEL_69:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)lpString1);
    goto LABEL_70;
  }
  lambda_b14e5a41598cd1bc1c8a106326625b39_::operator()(v42, v79);
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::EnsurePropertiesForSRCachePackage(
    this,
    lpString1);
  *((_BYTE *)this + 524) = 1;
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)lpString1);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v70);
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v64);
  StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)&v77);
  v33 = v50;
  *(_QWORD *)&v50 = 0;
  if ( v33 )
    SRCacheContext_Close();
LABEL_23:
  v9 = (_QWORD)v52 == 0;
  *(_QWORD *)&v52 = 0;
  if ( !v9 )
    SRCacheContext_Close();
  v10 = v49;
  v49 = 0;
  if ( v10 )
    SRCacheManager_Close();
LABEL_2:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v41);
}

```

## disassembly

```asm
0x1802b42dc  push    rbp
0x1802b42de  push    rbx
0x1802b42df  push    rsi
0x1802b42e0  push    rdi
0x1802b42e1  push    r14
0x1802b42e3  push    r15
0x1802b42e5  lea     rbp, [rsp-178h]
0x1802b42ed  sub     rsp, 278h
0x1802b42f4  mov     rax, cs:__security_cookie
0x1802b42fb  xor     rax, rsp
0x1802b42fe  mov     [rbp+1A0h+var_40], rax
0x1802b4305  mov     rdi, rcx
0x1802b4308  xor     r15d, r15d
0x1802b430b  mov     [rsp+2A0h+var_258], r15
0x1802b4310  mov     rdx, rcx
0x1802b4313  lea     rcx, [rsp+2A0h+var_258]
0x1802b4318  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1802b431d  nop
0x1802b431e  cmp     [rdi+20Ch], r15b
0x1802b4325  jz      short loc_1802B4350
0x1802b4327  lea     rcx, [rsp+2A0h+var_258]
0x1802b432c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1802b4331  mov     rcx, [rbp+1A0h+var_40]
0x1802b4338  xor     rcx, rsp; StackCookie
0x1802b433b  call    __security_check_cookie
0x1802b4340  add     rsp, 278h
0x1802b4347  pop     r15
0x1802b4349  pop     r14
0x1802b434b  pop     rdi
0x1802b434c  pop     rsi
0x1802b434d  pop     rbx
0x1802b434e  pop     rbp
0x1802b434f  retn
0x1802b4350  mov     [rbp+1A0h+var_1F0], r15
0x1802b4354  lea     rax, [rbp+1A0h+var_1F0]
0x1802b4358  mov     [rsp+2A0h+var_240], rax
0x1802b435d  mov     [rsp+2A0h+var_238], r15
0x1802b4362  mov     [rsp+2A0h+var_230], 1
0x1802b4367  lea     rdx, [rsp+2A0h+var_238]
0x1802b436c  xor     ecx, ecx
0x1802b436e  call    cs:__imp_SRCacheManager_Open
0x1802b4374  mov     ebx, eax
0x1802b4376  lea     rcx, [rsp+2A0h+var_240]
0x1802b437b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1802b4380  test    ebx, ebx
0x1802b4382  jns     short loc_1802B43A1
0x1802b4384  mov     rcx, [rbp+1A8h]; this
0x1802b438b  mov     r9d, ebx; char *
0x1802b438e  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b4395  mov     edx, 0A5h; void *
0x1802b439a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b439f  jmp     short loc_1802B43A4
0x1802b43a1  mov     ebx, r15d
0x1802b43a4  mov     rcx, [rbp+1A8h]; this
0x1802b43ab  test    ebx, ebx
0x1802b43ad  js      loc_1802B4A67
0x1802b43b3  mov     [rsp+2A0h+var_250], rdi
0x1802b43b8  xorps   xmm0, xmm0
0x1802b43bb  movups  [rbp+1A0h+var_1D0], xmm0
0x1802b43bf  mov     qword ptr [rbp+1A0h+var_1D0], r15
0x1802b43c3  mov     dword ptr [rbp+1A0h+var_1D0+8], r15d
0x1802b43c7  mov     [rbp+1A0h+var_1C0], r15
0x1802b43cb  lea     rsi, [rdi+8]
0x1802b43cf  cmp     qword ptr [rsi+18h], 7
0x1802b43d4  jbe     short loc_1802B43DB
0x1802b43d6  mov     rdx, [rsi]
0x1802b43d9  jmp     short loc_1802B43DE
0x1802b43db  mov     rdx, rsi; wchar_t *
0x1802b43de  lea     r8, [rbp+1A0h+var_1D0]; struct StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow *
0x1802b43e2  lea     rcx, [rbp+1A0h+var_1F0]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b43e6  call    ?FindByName@PkgExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEB_WAEAVPkgExtensionIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::FindByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow &)
0x1802b43eb  test    eax, eax
0x1802b43ed  js      loc_1802B45E1
0x1802b43f3  mov     [rsp+2A0h+var_260+1], r15b
0x1802b43f8  xorps   xmm0, xmm0
0x1802b43fb  movdqa  [rbp+1A0h+var_140], xmm0
0x1802b4400  xorps   xmm1, xmm1
0x1802b4403  movdqa  [rbp+1A0h+var_130], xmm1
0x1802b4408  movdqa  [rbp+1A0h+var_120], xmm0
0x1802b4410  movdqa  [rbp+1A0h+var_110], xmm1
0x1802b4418  mov     dword ptr [rbp+1A0h+var_100], r15d
0x1802b441f  lea     r9, [rsp+2A0h+var_260+1]
0x1802b4424  lea     r8, [rbp+1A0h+var_140]
0x1802b4428  mov     edx, 28h ; '('
0x1802b442d  lea     rcx, [rbp+1A0h+var_1D0]
0x1802b4431  call    ?Get@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x1802b4436  mov     rcx, [rbp+1A8h]; this
0x1802b443d  test    eax, eax
0x1802b443f  js      loc_1802B4A7C
0x1802b4445  cmp     [rsp+2A0h+var_260+1], r15b
0x1802b444a  jz      loc_1802B45D8
0x1802b4450  or      r14, 0FFFFFFFFFFFFFFFFh
0x1802b4454  mov     [rsp+2A0h+var_260], r15b
0x1802b4459  xorps   xmm0, xmm0
0x1802b445c  movdqa  [rbp+1A0h+var_F0], xmm0
0x1802b4464  mov     [rbp+1A0h+var_E0], r15
0x1802b446b  mov     [rbp+1A0h+var_D8], r15
0x1802b4472  movdqa  [rbp+1A0h+var_D0], xmm0
0x1802b447a  xorps   xmm1, xmm1
0x1802b447d  movdqa  [rbp+1A0h+var_C0], xmm1
0x1802b4485  lea     r9, [rsp+2A0h+var_260]; bool *
0x1802b448a  lea     r8, [rbp+1A0h+var_F0]; struct StateRepository::Cache::Entity::PackageExtension_NoThrow *
0x1802b4491  lea     rdx, [rbp+1A0h+var_1F0]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b4495  lea     rcx, [rbp+1A0h+var_140]; this
0x1802b4499  call    ?GetExtension@PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackageExtension_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::GetExtension(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x1802b449e  mov     rcx, [rbp+1A8h]; this
0x1802b44a5  test    eax, eax
0x1802b44a7  js      loc_1802B4AA6
0x1802b44ad  cmp     [rsp+2A0h+var_260], r15b
0x1802b44b2  jz      loc_1802B4552
0x1802b44b8  xorps   xmm0, xmm0
0x1802b44bb  movdqa  xmmword ptr [rbp+1A0h+lpString1], xmm0
0x1802b44c0  mov     [rbp+1A0h+var_1A0], r15
0x1802b44c4  xorps   xmm1, xmm1
0x1802b44c7  movups  [rbp+1A0h+var_198], xmm1
0x1802b44cb  mov     [rbp+1A0h+var_188], r15
0x1802b44cf  mov     [rbp+1A0h+var_180], r15
0x1802b44d3  mov     [rbp+1A0h+var_178], r15
0x1802b44d7  movdqa  [rbp+1A0h+var_170], xmm0
0x1802b44dc  mov     [rbp+1A0h+var_160], r15d
0x1802b44e0  mov     [rbp+1A0h+var_158], r15
0x1802b44e4  mov     [rbp+1A0h+var_150], r15
0x1802b44e8  lea     r9, [rsp+2A0h+var_260]; bool *
0x1802b44ed  lea     r8, [rbp+1A0h+lpString1]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x1802b44f1  lea     rdx, [rbp+1A0h+var_1F0]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b44f5  lea     rcx, [rbp+1A0h+var_F0]; this
0x1802b44fc  call    ?GetPackage@PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVPackage_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::GetPackage(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1802b4501  mov     rcx, [rbp+1A8h]; this
0x1802b4508  test    eax, eax
0x1802b450a  js      loc_1802B4A91
0x1802b4510  cmp     [rsp+2A0h+var_260], r15b
0x1802b4515  jz      short loc_1802B4548
0x1802b4517  lea     r8, [rdi+0A8h]
0x1802b451e  cmp     qword ptr [rdi+0C0h], 7
0x1802b4526  jbe     short loc_1802B452B
0x1802b4528  mov     r8, [r8]; lpString2
0x1802b452b  mov     [rsp+2A0h+bIgnoreCase], 1; bIgnoreCase
0x1802b4533  mov     r9d, r14d; cchCount2
0x1802b4536  mov     edx, r14d; cchCount1
0x1802b4539  mov     rcx, [rbp+1A0h+lpString1+8]; lpString1
0x1802b453d  call    cs:__imp_CompareStringOrdinal
0x1802b4543  cmp     eax, 2
0x1802b4546  jz      short loc_1802B4563
0x1802b4548  lea     rcx, [rbp+1A0h+lpString1]; this
0x1802b454c  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1802b4551  nop
0x1802b4552  lea     rcx, [rbp+1A0h+var_F0]; this
0x1802b4559  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1802b455e  jmp     loc_1802B4454
0x1802b4563  mov     rdx, qword ptr [rbp+1A0h+var_120]
0x1802b456a  lea     rcx, [rsp+2A0h+var_250]
0x1802b456f  call    _lambda_b14e5a41598cd1bc1c8a106326625b39___operator__
0x1802b4574  lea     rdx, [rbp+1A0h+lpString1]
0x1802b4578  mov     rcx, rdi
0x1802b457b  call    ?EnsurePropertiesForSRCachePackage@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAAXAEBVPackage_NoThrow@Entity@Cache@StateRepository@@Uwrite_lock_required@wil@@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::EnsurePropertiesForSRCachePackage(StateRepository::Cache::Entity::Package_NoThrow const &,wil::write_lock_required)
0x1802b4580  mov     byte ptr [rdi+20Ch], 1
0x1802b4587  lea     rcx, [rbp+1A0h+lpString1]; this
0x1802b458b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1802b4590  nop
0x1802b4591  lea     rcx, [rbp+1A0h+var_F0]; this
0x1802b4598  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x1802b459d  nop
0x1802b459e  lea     rcx, [rbp+1A0h+var_140]; this
0x1802b45a2  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x1802b45a7  nop
0x1802b45a8  mov     rcx, qword ptr [rbp+1A0h+var_1D0]
0x1802b45ac  test    rcx, rcx
0x1802b45af  mov     qword ptr [rbp+1A0h+var_1D0], r15
0x1802b45b3  jz      short loc_1802B45BC
0x1802b45b5  call    cs:__imp_SRCacheContext_Close
0x1802b45bb  nop
0x1802b45bc  mov     rcx, [rbp+1A0h+var_1F0]
0x1802b45c0  mov     [rbp+1A0h+var_1F0], r15
0x1802b45c4  test    rcx, rcx
0x1802b45c7  jz      loc_1802B4327
0x1802b45cd  call    cs:__imp_SRCacheManager_Close
0x1802b45d3  jmp     loc_1802B4327
0x1802b45d8  lea     rcx, [rbp+1A0h+var_140]; this
0x1802b45dc  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x1802b45e1  xorps   xmm0, xmm0
0x1802b45e4  movups  [rbp+1A0h+var_1E8], xmm0
0x1802b45e8  mov     qword ptr [rbp+1A0h+var_1E8], r15
0x1802b45ec  mov     dword ptr [rbp+1A0h+var_1E8+8], r15d
0x1802b45f0  mov     [rbp+1A0h+var_1D8], r15
0x1802b45f4  cmp     qword ptr [rsi+18h], 7
0x1802b45f9  jbe     short loc_1802B4600
0x1802b45fb  mov     r8, [rsi]
0x1802b45fe  jmp     short loc_1802B4603
0x1802b4600  mov     r8, rsi; wchar_t *
0x1802b4603  lea     rdx, [rbp+1A0h+var_1F0]; struct StateRepository::Cache::Manager_NoThrow *
0x1802b4607  lea     rcx, [rbp+1A0h+var_1E8]; this
0x1802b460b  call    ?OpenByName@AppExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEB_W@Z; StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::OpenByName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *)
0x1802b4610  mov     ebx, eax
0x1802b4612  test    eax, eax
0x1802b4614  jns     short loc_1802B4633
0x1802b4616  mov     rcx, [rbp+1A8h]; this
0x1802b461d  mov     r9d, eax; char *
0x1802b4620  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b4627  mov     edx, 2C2h; void *
0x1802b462c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4631  jmp     short loc_1802B4636
0x1802b4633  mov     ebx, r15d
0x1802b4636  mov     rcx, [rbp+1A8h]; this
0x1802b463d  test    ebx, ebx
0x1802b463f  js      loc_1802B4ABB
0x1802b4645  mov     [rsp+2A0h+var_260+1], r15b
0x1802b464a  xorps   xmm0, xmm0
0x1802b464d  movdqa  [rbp+1A0h+var_90], xmm0
0x1802b4655  xorps   xmm1, xmm1
0x1802b4658  movdqa  [rbp+1A0h+var_80], xmm1
0x1802b4660  movdqa  [rbp+1A0h+var_70], xmm0
0x1802b4668  movdqa  [rbp+1A0h+var_60], xmm1
0x1802b4670  mov     [rbp+1A0h+var_50], r15d
0x1802b4677  lea     r9, [rsp+2A0h+var_260+1]
0x1802b467c  lea     r8, [rbp+1A0h+var_90]
0x1802b4683  mov     edx, 2Ah ; '*'
0x1802b4688  lea     rcx, [rbp+1A0h+var_1E8]
0x1802b468c  call    ?Get@AppExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)
0x1802b4691  mov     rcx, [rbp+1A8h]; this
0x1802b4698  test    eax, eax
0x1802b469a  js      loc_1802B4AD0
0x1802b46a0  cmp     [rsp+2A0h+var_260+1], r15b
0x1802b46a5  jz      loc_1802B49FC
0x1802b46ab  or      r14, 0FFFFFFFFFFFFFFFFh
0x1802b46af  mov     [rsp+2A0h+var_260], r15b
0x1802b46b4  xorps   xmm0, xmm0
0x1802b46b7  movdqa  [rbp+1A0h+var_140], xmm0
0x1802b46bc  mov     qword ptr [rbp+1A0h+var_130], r15
0x1802b46c0  mov     qword ptr [rbp+1A0h+var_130+8], r15
0x1802b46c4  movdqa  [rbp+1A0h+var_120], xmm0
0x1802b46cc  xorps   xmm1, xmm1
0x1802b46cf  movdqa  [rbp+1A0h+var_110], xmm1
0x1802b46d7  mov     [rbp+1A0h+var_100], r15
0x1802b46de  mov     [rbp+1A0h+var_F8], r15d
0x1802b46e5  lea     rax, [rsp+2A0h+var_260]
0x1802b46ea  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax; int
0x1802b46ef  lea     r9, [rbp+1A0h+var_140]
0x1802b46f3  mov     rdx, qword ptr [rbp+1A0h+var_60]
0x1802b46fa  lea     rcx, [rbp+1A0h+var_1F0]
0x1802b46fe  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1802b4703  mov     ebx, eax
0x1802b4705  test    eax, eax
0x1802b4707  jns     short loc_1802B4726
0x1802b4709  mov     rcx, [rbp+1A8h]; this
0x1802b4710  mov     r9d, eax; char *
0x1802b4713  lea     r8, aOnecoreInterna_16; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b471a  mov     edx, 29Eh; void *
0x1802b471f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b4724  jmp     short loc_1802B4729
0x1802b4726  mov     ebx, r15d
0x1802b4729  mov     rcx, [rbp+1A8h]; this
0x1802b4730  test    ebx, ebx
0x1802b4732  js      loc_1802B4A52
0x1802b4738  cmp     [rsp+2A0h+var_260], r15b
0x1802b473d  jz      loc_1802B4937
0x1802b4743  xorps   xmm0, xmm0
0x1802b4746  movdqa  [rbp+1A0h+var_F0], xmm0
0x1802b474e  mov     [rbp+1A0h+var_E0], r15
0x1802b4755  mov     [rbp+1A0h+var_D8], r15
0x1802b475c  movdqa  [rbp+1A0h+var_D0], xmm0
0x1802b4764  xorps   xmm1, xmm1
0x1802b4767  movdqa  [rbp+1A0h+var_C0], xmm1
0x1802b476f  movdqa  [rbp+1A0h+var_B0], xmm0
0x1802b4777  movdqa  [rbp+1A0h+var_A0], xmm1
0x1802b477f  lea     rax, [rsp+2A0h+var_260]
0x1802b4784  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax; int
0x1802b4789  lea     r9, [rbp+1A0h+var_F0]
0x1802b4790  mov     rdx, qword ptr [rbp+1A0h+var_140+8]
0x1802b4794  lea     rcx, [rbp+1A0h+var_1F0]
0x1802b4798  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x1802b479d  mov     ebx, eax
0x1802b479f  test    eax, eax
0x1802b47a1  jns     short loc_1802B47C0
0x1802b47a3  mov     rcx, [rbp+1A8h]; this
0x1802b47aa  mov     r9d, eax; char *
0x1802b47ad  lea     r8, aOnecoreInterna_8; "OneCore\\Internal\\Base\\Inc\\appmodel"...
0x1802b47b4  mov     edx, 357h; void *
0x1802b47b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802b47be  jmp     short loc_1802B47C3
0x1802b47c0  mov     ebx, r15d
0x1802b47c3  mov     rcx, [rbp+1A8h]; this
0x1802b47ca  test    ebx, ebx
0x1802b47cc  js      loc_1802B4AFA
0x1802b47d2  cmp     [rsp+2A0h+var_260], r15b
0x1802b47d7  jz      loc_1802B492B
0x1802b47dd  xorps   xmm0, xmm0
0x1802b47e0  movdqa  xmmword ptr [rbp+1A0h+lpString1], xmm0
0x1802b47e5  mov     [rbp+1A0h+var_1A0], r15
0x1802b47e9  xorps   xmm1, xmm1
0x1802b47ec  movups  [rbp+1A0h+var_198], xmm1
0x1802b47f0  mov     [rbp+1A0h+var_188], r15
0x1802b47f4  mov     [rbp+1A0h+var_180], r15
0x1802b47f8  mov     [rbp+1A0h+var_178], r15
0x1802b47fc  movdqa  [rbp+1A0h+var_170], xmm0
0x1802b4801  mov     [rbp+1A0h+var_160], r15d
0x1802b4805  mov     [rbp+1A0h+var_158], r15
0x1802b4809  mov     [rbp+1A0h+var_150], r15
0x1802b480d  lea     rax, [rsp+2A0h+var_260]
0x1802b4812  mov     qword ptr [rsp+2A0h+bIgnoreCase], rax; int
0x1802b4817  lea     r9, [rbp+1A0h+lpString1]
  ... truncated ...
```
