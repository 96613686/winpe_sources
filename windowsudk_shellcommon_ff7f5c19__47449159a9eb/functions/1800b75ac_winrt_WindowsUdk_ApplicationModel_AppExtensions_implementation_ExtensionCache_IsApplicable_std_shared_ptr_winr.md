# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::IsApplicable(std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheEnumerationOptions,std::function<bool (std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &)> &&)

- ea: `0x1800b75ac`
- end: `0x1800b8a65`
- name: `?IsApplicable@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAA_NAEBV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@W4CacheEnumerationOptions@23456@$$QEAV?$function@$$A6A_NAEBV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@Z@8@@Z`
- size: `5305`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802b2420`

## callees

- `0x180005a74`
- `0x1800083b0`
- `0x180021ae8`
- `0x180021b30`
- `0x180021b74`
- `0x180025348`
- `0x180025364`
- `0x180026860`
- `0x180027af0`
- `0x1800679d8`
- `0x180071b44`
- `0x18007f4d0`
- `0x18007f53c`
- `0x1800b5100`
- `0x1800b75ac`
- `0x1800b8a6c`
- `0x18015cb00`
- `0x18015d868`
- `0x1802a0330`
- `0x1802a036c`
- `0x1802a03e4`
- `0x1802a0d98`
- `0x1802ac4d0`
- `0x1802adce4`
- `0x1802add38`
- `0x1802add84`
- `0x1802b1ab8`
- `0x1802b4d24`
- `0x1802b6b34`
- `0x1802b6c6c`
- `0x1802b6dc8`
- `0x1802b7380`
- `0x1802b9524`
- `0x1802ba5f0`
- `0x1802ba62c`
- `0x1802ba668`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b7a53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b7bc3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b7a53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b7bc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b762c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b7670`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b76e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b762c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b7670`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b76e8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x1800b7a23`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x1800b7b93`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x1800b7a23`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x1800b7b93`

## string_xrefs

- `0x1800b8a53`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1800b87a3`: `ExtensionVelocityDisabled`
- `0x1800b8833`: `ExtensionVelocityDisabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
char __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::IsApplicable(
        __int64 a1,
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo **a2,
        char a3,
        _QWORD *a4)
{
  __int64 v7; // rax
  char v8; // r12
  int v9; // edi
  __int64 v10; // rax
  int v11; // ebx
  bool v12; // bl
  winrt::hstring *RetailPackageFamilyName; // rax
  const WCHAR *v14; // rdi
  __int64 v15; // rax
  int v16; // r13d
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  uf::UndockedFlightingActiveStateCache *v19; // rcx
  __int64 v20; // rax
  const wchar_t *v21; // rdi
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int8 v24; // cl
  const wchar_t *v25; // rbx
  __int64 v26; // rcx
  AppExtensionsLogging *v27; // rcx
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  char v31; // al
  _QWORD *v32; // rax
  int v33; // ebx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rax
  int v39; // ebx
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  char v42; // al
  bool v43; // zf
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *v44; // rax
  _QWORD *v45; // rax
  _QWORD *v46; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // rax
  _QWORD *v49; // rax
  _QWORD *v50; // rax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v51; // rcx
  int v52; // edx
  int v53; // edx
  int v54; // edx
  _QWORD *v55; // rax
  _QWORD *v56; // rax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // rax
  const wchar_t *v60; // rdi
  __int64 v61; // rax
  unsigned __int64 v62; // rdx
  unsigned __int8 v63; // cl
  const wchar_t *v64; // rbx
  __int64 v65; // rcx
  AppExtensionsLogging *v66; // rcx
  int v67; // edx
  _QWORD *v68; // rax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v69; // rcx
  _QWORD *v70; // rax
  _QWORD *v71; // rax
  _QWORD *v72; // rax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v73; // rcx
  int v74; // edx
  int v75; // edx
  int v76; // edx
  _QWORD *v77; // rax
  _QWORD *v78; // rax
  _QWORD *v79; // rax
  _QWORD *v80; // rax
  _QWORD *v81; // rax
  _QWORD *v82; // rax
  int v83; // edx
  int v84; // edx
  _QWORD *v85; // rax
  _QWORD *v86; // rax
  _QWORD *v87; // rax
  _QWORD *v88; // rax
  int v89; // ecx
  _QWORD *v90; // rax
  _QWORD *v91; // rax
  char IsEnabled; // al
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *v93; // rcx
  __int64 v94; // rcx
  _QWORD *v95; // rax
  _QWORD *v96; // rax
  _QWORD *v97; // rax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo *v98; // rax
  __int64 v99; // rax
  const wchar_t *v100; // rdi
  __int64 v101; // rax
  unsigned __int64 v102; // rdx
  unsigned __int8 v103; // cl
  const wchar_t *v104; // rbx
  __int64 v105; // rcx
  AppExtensionsLogging *v106; // rcx
  unsigned __int16 *v107; // r15
  unsigned __int16 *v108; // r13
  unsigned __int16 v109; // bx
  unsigned __int16 v110; // di
  _QWORD *v111; // rax
  _QWORD *v112; // rax
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo **v113; // rax
  _QWORD *v114; // rax
  const char *bIgnoreCase; // [rsp+20h] [rbp-188h]
  _QWORD *v116; // [rsp+30h] [rbp-178h] BYREF
  _QWORD *v117; // [rsp+38h] [rbp-170h] BYREF
  _BYTE v118[32]; // [rsp+40h] [rbp-168h] BYREF
  _BYTE v119[32]; // [rsp+60h] [rbp-148h] BYREF
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo **v120; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v121[32]; // [rsp+88h] [rbp-120h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+A8h] [rbp-100h] BYREF
  WCHAR packageFamilyName[88]; // [rsp+B0h] [rbp-F8h] BYREF
  char v124; // [rsp+160h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v117 = a4;
  v116 = (_QWORD *)a1;
  v120 = a2;
  v7 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PublisherId(*a2, v121);
  if ( *(_QWORD *)(v7 + 24) > 7u )
    v7 = *(_QWORD *)v7;
  v8 = 1;
  v9 = CompareStringOrdinal((LPCWCH)v7, -1, L"cw5n1h2txyewy", -1, 1);
  std::filesystem::path::~path((std::filesystem::path *)v121);
  v10 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PublisherId(*a2, v121);
  if ( *(_QWORD *)(v10 + 24) > 7u )
    v10 = *(_QWORD *)v10;
  v11 = CompareStringOrdinal((LPCWCH)v10, -1, L"8wekyb3d8bbwe", -1, 1);
  std::filesystem::path::~path((std::filesystem::path *)v121);
  v12 = v9 == 2 || (*(_BYTE *)(a1 + 24) & 2) != 0 && v11 == 2;
  RetailPackageFamilyName = (winrt::hstring *)GetRetailPackageFamilyName(packageFamilyNameLength);
  v14 = winrt::hstring::c_str(RetailPackageFamilyName);
  v15 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(*a2, v121);
  if ( *(_QWORD *)(v15 + 24) > 7u )
    v15 = *(_QWORD *)v15;
  v16 = CompareStringOrdinal((LPCWCH)v15, -1, v14, -1, 1);
  std::filesystem::path::~path((std::filesystem::path *)v121);
  winrt::handle_type<winrt::impl::hstring_traits>::close(packageFamilyNameLength);
  if ( winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::IsPackageEnabled(*a2) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59821427>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59821427>::GetImpl'::`2'::impl)
      && *((_BYTE *)*a2 + 523) )
    {
      if ( (a3 & 0x10) == 0 )
      {
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(*a2, v119);
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::TryGetUfPackageInfoForPackageFullName((uf::UfPackageInfo *)packageFamilyName);
        std::filesystem::path::~path((std::filesystem::path *)v119);
        if ( !v124
          || !uf::UndockedFlightingActiveStateCache::IsActive(v19, (const struct uf::UfPackageInfo *)packageFamilyName) )
        {
          v8 = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
          {
            v20 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                    *a2,
                    v118);
            v21 = (const wchar_t *)v20;
            if ( *(_QWORD *)(v20 + 24) > 7u )
              v21 = *(const wchar_t **)v20;
            v22 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(*a2, v121);
            v25 = (const wchar_t *)v22;
            if ( *(_QWORD *)(v22 + 24) > 7u )
              v25 = *(const wchar_t **)v22;
            if ( AppExtensionsLogging::IsEnabled(v24, v23) )
            {
              wil::details::static_lazy<AppExtensionsLogging>::get(
                v26,
                _lambda_5f7c601ff5b2a6c6ab6ed4a2a40d8ac0_::_lambda_invoker_cdecl_);
              AppExtensionsLogging::ExtensionFilteredOut_(v27, v25, v21, L"UndockedFlightingNotActive");
            }
            std::filesystem::path::~path((std::filesystem::path *)v121);
            std::filesystem::path::~path((std::filesystem::path *)v118);
          }
        }
        std::_Optional_destruct_base<uf::UfPackageInfo,0>::~_Optional_destruct_base<uf::UfPackageInfo,0>(packageFamilyName);
      }
      return v8;
    }
    switch ( *((_DWORD *)*a2 + 95) )
    {
      case 1:
        goto LABEL_234;
      case 2:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl'::`2'::impl)
          && (a3 & 0x20) != 0
          && *((_DWORD *)*a2 + 94) == 4 )
        {
          goto LABEL_234;
        }
        goto LABEL_164;
      case 3:
        if ( !v12 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
          {
            v49 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                              *a2,
                              v119);
            if ( v49[3] > 7u )
              v49 = (_QWORD *)*v49;
            v117 = v49;
            v50 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                              *a2,
                              v118);
            if ( v50[3] > 7u )
              v50 = (_QWORD *)*v50;
            v116 = v50;
            AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
              &v116,
              &v117,
              L"UnsupportedPublisher");
            std::filesystem::path::~path((std::filesystem::path *)v118);
            goto LABEL_290;
          }
          return 0;
        }
        LOBYTE(v51) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl);
        v52 = *((_DWORD *)*a2 + 94);
        if ( (_BYTE)v51 )
        {
          if ( v52 )
          {
            v53 = v52 - 1;
            if ( v53 )
            {
              v54 = v53 - 1;
              if ( v54 )
              {
                if ( (unsigned int)(v54 - 1) >= 2 )
                {
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                    return 0;
                  v55 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                    *a2,
                                    v119);
                  if ( v55[3] > 7u )
                    v55 = (_QWORD *)*v55;
                  v117 = v55;
                  v56 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                    *a2,
                                    v118);
                  if ( v56[3] > 7u )
                    v56 = (_QWORD *)*v56;
                  goto LABEL_213;
                }
              }
            }
            goto LABEL_234;
          }
          if ( !winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsDeveloperModeEnabled(v51)
            || !winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsInternalDeveloperModeEnabled(v57) )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              return 0;
            v59 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                    *a2,
                    v119);
            v60 = (const wchar_t *)v59;
            if ( *(_QWORD *)(v59 + 24) > 7u )
              v60 = *(const wchar_t **)v59;
            v61 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(*a2, v118);
            v64 = (const wchar_t *)v61;
            if ( *(_QWORD *)(v61 + 24) > 7u )
              v64 = *(const wchar_t **)v61;
            if ( AppExtensionsLogging::IsEnabled(v63, v62) )
            {
              wil::details::static_lazy<AppExtensionsLogging>::get(
                v65,
                _lambda_5f7c601ff5b2a6c6ab6ed4a2a40d8ac0_::_lambda_invoker_cdecl_);
              AppExtensionsLogging::ExtensionFilteredOut_(v66, v64, v60, L"InternalDeveloperModeRequired");
            }
            goto LABEL_136;
          }
          if ( (a3 & 4) == 0 )
          {
LABEL_234:
            v89 = *((_DWORD *)*a2 + 96);
            if ( (v89 & 0x204) == 0x204 )
              v89 &= 0xFFFFFDFB;
            if ( v89 && (v89 & 0x7FF) != 0 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              {
                v90 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                  *a2,
                                  v119);
                if ( v90[3] > 7u )
                  v90 = (_QWORD *)*v90;
                v117 = v90;
                v91 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                  *a2,
                                  v118);
                if ( v91[3] > 7u )
                  v91 = (_QWORD *)*v91;
                v116 = v91;
                AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
                  &v116,
                  &v117,
                  L"PackageBadState");
                std::filesystem::path::~path((std::filesystem::path *)v118);
                goto LABEL_290;
              }
              return 0;
            }
            if ( (a3 & 1) == 0 )
            {
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60689272>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60689272>::GetImpl'::`2'::impl);
              v93 = *a2;
              if ( IsEnabled )
              {
                v94 = *((_QWORD *)v93 + 50);
                if ( BYTE4(v94)
                  && !winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::IsVelocityIdEnabled(v94) )
                {
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                    return 0;
                  v95 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                    *a2,
                                    v119);
                  if ( v95[3] > 7u )
                    v95 = (_QWORD *)*v95;
                  v117 = v95;
                  v96 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                    *a2,
                                    v118);
                  if ( v96[3] > 7u )
                    v96 = (_QWORD *)*v96;
                  goto LABEL_253;
                }
              }
              else if ( *((_BYTE *)v93 + 396)
                     && !(unsigned __int8)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::IsVelocityEnabled(*(_QWORD *)((char *)v93 + 388)) )
              {
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                  return 0;
                v97 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                  *a2,
                                  v119);
                if ( v97[3] > 7u )
                  v97 = (_QWORD *)*v97;
                v117 = v97;
                v96 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                  *a2,
                                  v118);
                if ( v96[3] > 7u )
                  v96 = (_QWORD *)*v96;
LABEL_253:
                v116 = v96;
                AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
                  &v116,
                  &v117,
                  L"ExtensionVelocityDisabled");
                std::filesystem::path::~path((std::filesystem::path *)v118);
                goto LABEL_290;
              }
              v98 = *a2;
              if ( !*((_BYTE *)*a2 + 521) )
              {
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                  return 0;
                v99 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                        *a2,
                        v119);
                v100 = (const wchar_t *)v99;
                if ( *(_QWORD *)(v99 + 24) > 7u )
                  v100 = *(const wchar_t **)v99;
                v101 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                         *a2,
                         v118);
                v104 = (const wchar_t *)v101;
                if ( *(_QWORD *)(v101 + 24) > 7u )
                  v104 = *(const wchar_t **)v101;
                if ( AppExtensionsLogging::IsEnabled(v103, v102) )
                {
                  wil::details::static_lazy<AppExtensionsLogging>::get(
                    v105,
                    _lambda_5f7c601ff5b2a6c6ab6ed4a2a40d8ac0_::_lambda_invoker_cdecl_);
                  AppExtensionsLogging::ExtensionFilteredOut_(v106, v104, v100, L"MdmPolicyDisabled");
                }
LABEL_136:
                std::filesystem::path::~path((std::filesystem::path *)v118);
                goto LABEL_290;
              }
              v107 = (unsigned __int16 *)*((_QWORD *)v98 + 51);
              v108 = (unsigned __int16 *)*((_QWORD *)v98 + 52);
              while ( v107 != v108 )
              {
                v109 = *v107;
                v110 = v107[1];
                winrt::param::hstring::hstring(v118, v107 + 4);
                if ( !winrt::WindowsUdk::Foundation::Metadata::implementation::ApiInformation::IsApiContractPresent(
                        (const struct winrt::hstring *)v118,
                        v110,
                        v109) )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                  {
                    v111 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                       *a2,
                                       v119);
                    if ( v111[3] > 7u )
                      v111 = (_QWORD *)*v111;
                    v117 = v111;
                    v112 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                       *a2,
                                       v118);
                    if ( v112[3] > 7u )
                      v112 = (_QWORD *)*v112;
                    v116 = v112;
                    AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[24]>(
                      &v116,
                      &v117);
                    std::filesystem::path::~path((std::filesystem::path *)v118);
                    std::filesystem::path::~path((std::filesystem::path *)v119);
                  }
                  return 0;
                }
                v107 += 20;
              }
            }
            if ( !(unsigned __int8)std::_Func_class<void,winrt::WindowsUdk::UI::MenuItem const &,winrt::WindowsUdk::UI::MenuItemInvokedArgs const &>::operator()(
                                     v117,
                                     a2) )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              {
                v113 = (winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo **)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(*a2, v119);
                if ( (unsigned __int64)v113[3] > 7 )
                  v113 = (winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo **)*v113;
                v120 = v113;
                v114 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                   *a2,
                                   v118);
                if ( v114[3] > 7u )
                  v114 = (_QWORD *)*v114;
                v117 = v114;
                AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
                  &v117,
                  &v120,
                  L"CustomFilterRejected");
                std::filesystem::path::~path((std::filesystem::path *)v118);
                goto LABEL_290;
              }
              return 0;
            }
            return v8;
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
            return 0;
          v58 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                            *a2,
                            v119);
          if ( v58[3] > 7u )
            v58 = (_QWORD *)*v58;
          v117 = v58;
          v46 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                            *a2,
                            v118);
          if ( v46[3] > 7u )
            v46 = (_QWORD *)*v46;
          goto LABEL_203;
        }
        if ( v52 )
        {
          v67 = v52 - 1;
          if ( v67 )
          {
            if ( v67 != 2 )
            {
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                return 0;
              v68 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                *a2,
                                v119);
              if ( v68[3] > 7u )
                v68 = (_QWORD *)*v68;
              v117 = v68;
              v56 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                *a2,
                                v118);
              if ( v56[3] > 7u )
                v56 = (_QWORD *)*v56;
              goto LABEL_213;
            }
            goto LABEL_234;
          }
        }
        if ( !winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsDeveloperModeEnabled(v51)
          || !winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsInternalDeveloperModeEnabled(v69) )
        {
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
            return 0;
          v71 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                            *a2,
                            v119);
          if ( v71[3] > 7u )
            v71 = (_QWORD *)*v71;
          v117 = v71;
          v72 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                            *a2,
                            v118);
          if ( v72[3] > 7u )
            v72 = (_QWORD *)*v72;
          goto LABEL_160;
        }
        if ( (a3 & 4) == 0 )
          goto LABEL_234;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
          return 0;
        v70 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                          *a2,
                          v119);
        if ( v70[3] > 7u )
          v70 = (_QWORD *)*v70;
        v117 = v70;
        v48 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                          *a2,
                          v118);
        if ( v48[3] > 7u )
          v48 = (_QWORD *)*v48;
        goto LABEL_227;
    }
    if ( *((_DWORD *)*a2 + 95) != 4 )
    {
      if ( *((_DWORD *)*a2 + 95) != 5 )
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x98D,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
          "Unexpected PackageType encountered",
          bIgnoreCase);
LABEL_164:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl'::`2'::impl) )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
          return 0;
        v88 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                          *a2,
                          v119);
        if ( v88[3] > 7u )
          v88 = (_QWORD *)*v88;
        v117 = v88;
        v79 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                          *a2,
                          v118);
        if ( v79[3] > 7u )
          v79 = (_QWORD *)*v79;
        goto LABEL_233;
      }
      LOBYTE(v73) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl);
      v74 = *((_DWORD *)*a2 + 94);
      if ( (_BYTE)v73 )
      {
        if ( v74 )
        {
          v75 = v74 - 1;
          if ( v75 )
          {
            v76 = v75 - 1;
            if ( v76 )
            {
              if ( (unsigned int)(v76 - 1) >= 2 )
              {
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                  return 0;
                v77 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                  *a2,
                                  v119);
                if ( v77[3] > 7u )
                  v77 = (_QWORD *)*v77;
                v117 = v77;
                v56 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                  *a2,
                                  v118);
                if ( v56[3] > 7u )
                  v56 = (_QWORD *)*v56;
                goto LABEL_213;
              }
            }
          }
          if ( (a3 & 8) == 0 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              return 0;
            v78 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                              *a2,
                              v119);
            if ( v78[3] > 7u )
              v78 = (_QWORD *)*v78;
            v117 = v78;
            v79 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                              *a2,
                              v118);
            if ( v79[3] > 7u )
              v79 = (_QWORD *)*v79;
            goto LABEL_233;
          }
          goto LABEL_234;
        }
        if ( (a3 & 8) == 0 )
        {
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
            return 0;
          v80 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                            *a2,
                            v119);
          if ( v80[3] > 7u )
            v80 = (_QWORD *)*v80;
          v117 = v80;
          v79 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                            *a2,
                            v118);
          if ( v79[3] > 7u )
            v79 = (_QWORD *)*v79;
          goto LABEL_233;
        }
        if ( !winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsDeveloperModeEnabled(v73) )
        {
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
            return 0;
          v81 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                            *a2,
                            v119);
          if ( v81[3] > 7u )
            v81 = (_QWORD *)*v81;
          v117 = v81;
          v72 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                            *a2,
                            v118);
          if ( v72[3] > 7u )
            v72 = (_QWORD *)*v72;
LABEL_160:
          v116 = v72;
          AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
            &v116,
            &v117,
            L"DeveloperModeRequired");
          std::filesystem::path::~path((std::filesystem::path *)v118);
          goto LABEL_290;
        }
        if ( (a3 & 4) == 0 )
          goto LABEL_234;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
          return 0;
        v82 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                          *a2,
                          v119);
        if ( v82[3] > 7u )
          v82 = (_QWORD *)*v82;
        v117 = v82;
        v46 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                          *a2,
                          v118);
        if ( v46[3] > 7u )
          v46 = (_QWORD *)*v46;
LABEL_203:
        v116 = v46;
        AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[19]>(&v116, &v117);
        std::filesystem::path::~path((std::filesystem::path *)v118);
        goto LABEL_290;
      }
      if ( v74 )
      {
        v83 = v74 - 1;
        if ( v83 )
        {
          v84 = v83 - 1;
          if ( v84 && (unsigned int)(v84 - 1) >= 2 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              return 0;
            v85 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                              *a2,
                              v119);
            if ( v85[3] > 7u )
              v85 = (_QWORD *)*v85;
            v117 = v85;
            v56 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                              *a2,
                              v118);
            if ( v56[3] > 7u )
              v56 = (_QWORD *)*v56;
LABEL_213:
            v116 = v56;
            AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
              &v116,
              &v117,
              L"UnsupportedSignatureKind");
            std::filesystem::path::~path((std::filesystem::path *)v118);
            goto LABEL_290;
          }
          if ( (a3 & 8) != 0 )
            goto LABEL_234;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
            return 0;
          v86 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                            *a2,
                            v119);
          if ( v86[3] > 7u )
            v86 = (_QWORD *)*v86;
          v117 = v86;
          v79 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                            *a2,
                            v118);
          if ( v79[3] > 7u )
            v79 = (_QWORD *)*v79;
LABEL_233:
          v116 = v79;
          AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
            &v116,
            &v117,
            L"ThirdPartyNotAllowed");
          std::filesystem::path::~path((std::filesystem::path *)v118);
          goto LABEL_290;
        }
      }
      if ( (a3 & 4) == 0 )
        goto LABEL_234;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
        return 0;
      v87 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                        *a2,
                        v119);
      if ( v87[3] > 7u )
        v87 = (_QWORD *)*v87;
      v117 = v87;
      v48 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(*a2, v118);
      if ( v48[3] > 7u )
        v48 = (_QWORD *)*v48;
LABEL_227:
      v116 = v48;
      AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
        &v116,
        &v117,
        L"DeveloperSignedNotAllowed");
      std::filesystem::path::~path((std::filesystem::path *)v118);
      goto LABEL_290;
    }
    if ( v16 == 2 && *((_WORD *)*a2 + 187) < 0x209u )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
      {
        v29 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                          *a2,
                          v119);
        if ( v29[3] > 7u )
          v29 = (_QWORD *)*v29;
        v116 = v29;
        v30 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                          *a2,
                          v118);
        if ( v30[3] > 7u )
          v30 = (_QWORD *)*v30;
        *(_QWORD *)packageFamilyNameLength = v30;
        AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
          packageFamilyNameLength,
          &v116,
          L"StaleOverridePackage");
        std::filesystem::path::~path((std::filesystem::path *)v118);
        goto LABEL_290;
      }
      return 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56189266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56189266>::GetImpl'::`2'::impl) )
    {
      v31 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl);
      if ( (v116[3] & 0xA) == 0 )
      {
        if ( v31 )
        {
          if ( *((_DWORD *)*a2 + 94) == 1 || (unsigned int)(*((_DWORD *)*a2 + 94) - 2) <= 1 )
          {
            memset_0(packageFamilyName, 0, 0x82u);
            packageFamilyNameLength[0] = 65;
            if ( GetCurrentPackageFamilyName(packageFamilyNameLength, packageFamilyName) >= 0 )
            {
              v32 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(
                                *a2,
                                v118);
              if ( v32[3] > 7u )
                v32 = (_QWORD *)*v32;
              v33 = _o__wcsicmp(packageFamilyName, v32);
              std::filesystem::path::~path((std::filesystem::path *)v118);
              if ( v33 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
                {
                  v34 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                                    *a2,
                                    v119);
                  if ( v34[3] > 7u )
                    v34 = (_QWORD *)*v34;
                  v116 = v34;
                  v35 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                                    *a2,
                                    v118);
                  if ( v35[3] > 7u )
                    v35 = (_QWORD *)*v35;
                  v117 = v35;
                  AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
                    &v117,
                    &v116,
                    L"StoreDeliveredNotAllowed");
                  std::filesystem::path::~path((std::filesystem::path *)v118);
                  goto LABEL_290;
                }
                return 0;
              }
              goto LABEL_86;
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              return 0;
            v36 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                              *a2,
                              v119);
            if ( v36[3] > 7u )
              v36 = (_QWORD *)*v36;
            v117 = v36;
            v37 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                              *a2,
                              v118);
            if ( v37[3] > 7u )
              v37 = (_QWORD *)*v37;
LABEL_85:
            v116 = v37;
            AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
              &v116,
              &v117,
              L"StoreDeliveredNotAllowed");
            std::filesystem::path::~path((std::filesystem::path *)v118);
LABEL_290:
            std::filesystem::path::~path((std::filesystem::path *)v119);
            return 0;
          }
        }
        else if ( *((_DWORD *)*a2 + 94) == 3 )
        {
          memset_0(packageFamilyName, 0, 0x82u);
          packageFamilyNameLength[0] = 65;
          if ( GetCurrentPackageFamilyName(packageFamilyNameLength, packageFamilyName) < 0 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              return 0;
            v41 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                              *a2,
                              v119);
            if ( v41[3] > 7u )
              v41 = (_QWORD *)*v41;
            v117 = v41;
            v37 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                              *a2,
                              v118);
            if ( v37[3] > 7u )
              v37 = (_QWORD *)*v37;
            goto LABEL_85;
          }
          v38 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(
                            *a2,
                            v118);
          if ( v38[3] > 7u )
            v38 = (_QWORD *)*v38;
          v39 = _o__wcsicmp(packageFamilyName, v38);
          std::filesystem::path::~path((std::filesystem::path *)v118);
          if ( v39 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
              return 0;
            v40 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                              *a2,
                              v119);
            if ( v40[3] > 7u )
              v40 = (_QWORD *)*v40;
            v117 = v40;
            v37 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(
                              *a2,
                              v118);
            if ( v37[3] > 7u )
              v37 = (_QWORD *)*v37;
            goto LABEL_85;
          }
        }
      }
    }
LABEL_86:
    v42 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl);
    if ( (a3 & 4) == 0 )
      goto LABEL_234;
    v43 = v42 == 0;
    v44 = *a2;
    if ( !v43 )
    {
      if ( *((_DWORD *)v44 + 94) )
        goto LABEL_234;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
        return 0;
      v45 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                        *a2,
                        v119);
      if ( v45[3] > 7u )
        v45 = (_QWORD *)*v45;
      v117 = v45;
      v46 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(*a2, v118);
      if ( v46[3] > 7u )
        v46 = (_QWORD *)*v46;
      goto LABEL_203;
    }
    if ( *((_DWORD *)v44 + 94) != 1 )
      goto LABEL_234;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
      return 0;
    v47 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                      *a2,
                      v119);
    if ( v47[3] > 7u )
      v47 = (_QWORD *)*v47;
    v117 = v47;
    v48 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(*a2, v118);
    if ( v48[3] > 7u )
      v48 = (_QWORD *)*v48;
    goto LABEL_227;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl'::`2'::impl) )
  {
    v17 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                      *a2,
                      v119);
    if ( v17[3] > 7u )
      v17 = (_QWORD *)*v17;
    *(_QWORD *)packageFamilyNameLength = v17;
    v18 = (_QWORD *)winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(*a2, v121);
    if ( v18[3] > 7u )
      v18 = (_QWORD *)*v18;
    v116 = v18;
    AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(
      &v116,
      packageFamilyNameLength,
      L"PackageDisabled");
    std::filesystem::path::~path((std::filesystem::path *)v121);
    goto LABEL_290;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b75ac  mov     [rsp+arg_0], rbx
0x1800b75b1  mov     [rsp+arg_10], rsi
0x1800b75b6  push    rdi
0x1800b75b7  push    r12
0x1800b75b9  push    r13
0x1800b75bb  push    r14
0x1800b75bd  push    r15
0x1800b75bf  sub     rsp, 180h
0x1800b75c6  mov     rax, cs:__security_cookie
0x1800b75cd  xor     rax, rsp
0x1800b75d0  mov     [rsp+1A8h+var_38], rax
0x1800b75d8  mov     [rsp+1A8h+var_170], r9
0x1800b75dd  mov     r15d, r8d
0x1800b75e0  mov     rsi, rdx
0x1800b75e3  mov     r14, rcx
0x1800b75e6  mov     [rsp+1A8h+var_178], rcx
0x1800b75eb  mov     [rsp+1A8h+var_128], rdx
0x1800b75f3  lea     rdx, [rsp+1A8h+var_120]
0x1800b75fb  mov     rcx, [rsi]
0x1800b75fe  call    ?PublisherId@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PublisherId(void)
0x1800b7603  cmp     qword ptr [rax+18h], 7
0x1800b7608  jbe     short loc_1800B760D
0x1800b760a  mov     rax, [rax]
0x1800b760d  mov     r12d, 1
0x1800b7613  mov     [rsp+1A8h+bIgnoreCase], r12d; bIgnoreCase
0x1800b7618  or      r13d, 0FFFFFFFFh
0x1800b761c  mov     r9d, r13d; cchCount2
0x1800b761f  lea     r8, String2; "cw5n1h2txyewy"
0x1800b7626  mov     edx, r13d; cchCount1
0x1800b7629  mov     rcx, rax; lpString1
0x1800b762c  call    cs:__imp_CompareStringOrdinal
0x1800b7632  mov     edi, eax
0x1800b7634  lea     rcx, [rsp+1A8h+var_120]; this
0x1800b763c  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b7641  lea     rdx, [rsp+1A8h+var_120]
0x1800b7649  mov     rcx, [rsi]
0x1800b764c  call    ?PublisherId@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PublisherId(void)
0x1800b7651  cmp     qword ptr [rax+18h], 7
0x1800b7656  jbe     short loc_1800B765B
0x1800b7658  mov     rax, [rax]
0x1800b765b  mov     [rsp+1A8h+bIgnoreCase], r12d; bIgnoreCase
0x1800b7660  mov     r9d, r13d; cchCount2
0x1800b7663  lea     r8, a8wekyb3d8bbwe; "8wekyb3d8bbwe"
0x1800b766a  mov     edx, r13d; cchCount1
0x1800b766d  mov     rcx, rax; lpString1
0x1800b7670  call    cs:__imp_CompareStringOrdinal
0x1800b7676  mov     ebx, eax
0x1800b7678  lea     rcx, [rsp+1A8h+var_120]; this
0x1800b7680  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b7685  cmp     edi, 2
0x1800b7688  jz      short loc_1800B769E
0x1800b768a  test    byte ptr [r14+18h], 2
0x1800b768f  jz      short loc_1800B7696
0x1800b7691  cmp     ebx, 2
0x1800b7694  jz      short loc_1800B769E
0x1800b7696  xor     r14d, r14d
0x1800b7699  mov     bl, r14b
0x1800b769c  jmp     short loc_1800B76A4
0x1800b769e  mov     bl, r12b
0x1800b76a1  xor     r14d, r14d
0x1800b76a4  lea     rcx, [rsp+1A8h+packageFamilyNameLength]
0x1800b76ac  call    ?GetRetailPackageFamilyName@@YA?AUhstring@winrt@@XZ; GetRetailPackageFamilyName(void)
0x1800b76b1  nop
0x1800b76b2  mov     rcx, rax; this
0x1800b76b5  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b76ba  mov     rdi, rax
0x1800b76bd  lea     rdx, [rsp+1A8h+var_120]
0x1800b76c5  mov     rcx, [rsi]
0x1800b76c8  call    ?PackageFamilyName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(void)
0x1800b76cd  cmp     qword ptr [rax+18h], 7
0x1800b76d2  jbe     short loc_1800B76D7
0x1800b76d4  mov     rax, [rax]
0x1800b76d7  mov     [rsp+1A8h+bIgnoreCase], r12d; char *
0x1800b76dc  mov     r9d, r13d; cchCount2
0x1800b76df  mov     r8, rdi; lpString2
0x1800b76e2  mov     edx, r13d; cchCount1
0x1800b76e5  mov     rcx, rax; lpString1
0x1800b76e8  call    cs:__imp_CompareStringOrdinal
0x1800b76ee  mov     r13d, eax
0x1800b76f1  lea     rcx, [rsp+1A8h+var_120]; this
0x1800b76f9  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b76fe  nop
0x1800b76ff  lea     rcx, [rsp+1A8h+packageFamilyNameLength]
0x1800b7707  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800b770c  mov     rcx, [rsi]; this
0x1800b770f  call    ?IsPackageEnabled@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA_NXZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::IsPackageEnabled(void)
0x1800b7714  test    al, al
0x1800b7716  jnz     short loc_1800B7797
0x1800b7718  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60895122@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122> `wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl(void)'::`2'::impl
0x1800b771f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(void)
0x1800b7724  test    al, al
0x1800b7726  jz      loc_1800B89A9
0x1800b772c  lea     rdx, [rsp+1A8h+var_148]
0x1800b7731  mov     rcx, [rsi]
0x1800b7734  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800b7739  nop
0x1800b773a  cmp     qword ptr [rax+18h], 7
0x1800b773f  jbe     short loc_1800B7744
0x1800b7741  mov     rax, [rax]
0x1800b7744  mov     qword ptr [rsp+1A8h+packageFamilyNameLength], rax
0x1800b774c  lea     rdx, [rsp+1A8h+var_120]
0x1800b7754  mov     rcx, [rsi]
0x1800b7757  call    ?Name@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(void)
0x1800b775c  cmp     qword ptr [rax+18h], 7
0x1800b7761  jbe     short loc_1800B7766
0x1800b7763  mov     rax, [rax]
0x1800b7766  mov     [rsp+1A8h+var_178], rax
0x1800b776b  lea     r8, aPackagedisable; "PackageDisabled"
0x1800b7772  lea     rdx, [rsp+1A8h+packageFamilyNameLength]
0x1800b777a  lea     rcx, [rsp+1A8h+var_178]
0x1800b777f  call    ??$ExtensionFilteredOut@PEB_WPEB_WAEAY0BA@$$CB_W@AppExtensionsLogging@@SAX$$QEAPEB_W0AEAY0BA@$$CB_W@Z; AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(wchar_t const * &&,wchar_t const * &&,wchar_t const (&)[16])
0x1800b7784  lea     rcx, [rsp+1A8h+var_120]; this
0x1800b778c  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b7791  nop
0x1800b7792  jmp     loc_1800B8A35
0x1800b7797  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59821427@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59821427@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59821427> `wil::Feature<__WilFeatureTraits_Feature_59821427>::GetImpl(void)'::`2'::impl
0x1800b779e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59821427@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59821427>::__private_IsEnabled(void)
0x1800b77a3  test    al, al
0x1800b77a5  jz      loc_1800B78D2
0x1800b77ab  mov     rcx, [rsi]
0x1800b77ae  cmp     [rcx+20Bh], r14b
0x1800b77b5  jz      loc_1800B78D2
0x1800b77bb  test    r15b, 10h
0x1800b77bf  jnz     loc_1800B78A2
0x1800b77c5  lea     rdx, [rsp+1A8h+var_148]
0x1800b77ca  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800b77cf  nop
0x1800b77d0  mov     rdx, rax
0x1800b77d3  lea     rcx, [rsp+1A8h+packageFamilyName]; this
0x1800b77db  call    ?TryGetUfPackageInfoForPackageFullName@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA?AV?$optional@UUfPackageInfo@uf@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@7@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::TryGetUfPackageInfoForPackageFullName(std::wstring const &)
0x1800b77e0  nop
0x1800b77e1  lea     rcx, [rsp+1A8h+var_148]; this
0x1800b77e6  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b77eb  cmp     [rsp+1A8h+var_48], r14b
0x1800b77f3  jz      short loc_1800B780A
0x1800b77f5  lea     rdx, [rsp+1A8h+packageFamilyName]; struct uf::UfPackageInfo *
0x1800b77fd  call    ?IsActive@UndockedFlightingActiveStateCache@uf@@QEAA_NAEBUUfPackageInfo@2@@Z; uf::UndockedFlightingActiveStateCache::IsActive(uf::UfPackageInfo const &)
0x1800b7802  test    al, al
0x1800b7804  jnz     loc_1800B7895
0x1800b780a  mov     r12b, r14b
0x1800b780d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60895122@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122> `wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl(void)'::`2'::impl
0x1800b7814  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(void)
0x1800b7819  test    al, al
0x1800b781b  jz      short loc_1800B7895
0x1800b781d  lea     rdx, [rsp+1A8h+var_168]
0x1800b7822  mov     rcx, [rsi]
0x1800b7825  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800b782a  mov     rdi, rax
0x1800b782d  cmp     qword ptr [rax+18h], 7
0x1800b7832  jbe     short loc_1800B7837
0x1800b7834  mov     rdi, [rax]
0x1800b7837  lea     rdx, [rsp+1A8h+var_120]
0x1800b783f  mov     rcx, [rsi]
0x1800b7842  call    ?Name@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(void)
0x1800b7847  mov     rbx, rax
0x1800b784a  cmp     qword ptr [rax+18h], 7
0x1800b784f  jbe     short loc_1800B7854
0x1800b7851  mov     rbx, [rax]
0x1800b7854  call    ?IsEnabled@AppExtensionsLogging@@SA_NE_K@Z; AppExtensionsLogging::IsEnabled(uchar,unsigned __int64)
0x1800b7859  test    al, al
0x1800b785b  jz      short loc_1800B787C
0x1800b785d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f7c601ff5b2a6c6ab6ed4a2a40d8ac0_@@CA@XZ; _lambda_5f7c601ff5b2a6c6ab6ed4a2a40d8ac0_::_lambda_invoker_cdecl_(void)
0x1800b7864  call    ?get@?$static_lazy@VAppExtensionsLogging@@@details@wil@@QEAAPEAVAppExtensionsLogging@@P6AXXZ@Z; wil::details::static_lazy<AppExtensionsLogging>::get(void (*)(void))
0x1800b7869  lea     r9, aUndockedflight_3; "UndockedFlightingNotActive"
0x1800b7870  mov     r8, rdi; wchar_t *
0x1800b7873  mov     rdx, rbx; wchar_t *
0x1800b7876  call    ?ExtensionFilteredOut_@AppExtensionsLogging@@QEAAXPEB_W00@Z; AppExtensionsLogging::ExtensionFilteredOut_(wchar_t const *,wchar_t const *,wchar_t const *)
0x1800b787b  nop
0x1800b787c  lea     rcx, [rsp+1A8h+var_120]; this
0x1800b7884  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b7889  nop
0x1800b788a  lea     rcx, [rsp+1A8h+var_168]; this
0x1800b788f  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b7894  nop
0x1800b7895  lea     rcx, [rsp+1A8h+packageFamilyName]
0x1800b789d  call    ??1?$_Optional_destruct_base@UUfPackageInfo@uf@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<uf::UfPackageInfo,0>::~_Optional_destruct_base<uf::UfPackageInfo,0>(void)
0x1800b78a2  mov     al, r12b
0x1800b78a5  mov     rcx, [rsp+1A8h+var_38]
0x1800b78ad  xor     rcx, rsp; StackCookie
0x1800b78b0  call    __security_check_cookie
0x1800b78b5  lea     r11, [rsp+1A8h+var_28]
0x1800b78bd  mov     rbx, [r11+30h]
0x1800b78c1  mov     rsi, [r11+40h]
0x1800b78c5  mov     rsp, r11
0x1800b78c8  pop     r15
0x1800b78ca  pop     r14
0x1800b78cc  pop     r13
0x1800b78ce  pop     r12
0x1800b78d0  pop     rdi
0x1800b78d1  retn
0x1800b78d2  mov     edi, r15d
0x1800b78d5  and     edi, 4
0x1800b78d8  mov     rdx, [rsi]
0x1800b78db  mov     ecx, [rdx+17Ch]
0x1800b78e1  sub     ecx, 1
0x1800b78e4  jz      loc_1800B8678
0x1800b78ea  sub     ecx, 1
0x1800b78ed  jz      loc_1800B81A8
0x1800b78f3  sub     ecx, 1
0x1800b78f6  jz      loc_1800B7DD7
0x1800b78fc  sub     ecx, 1
0x1800b78ff  jz      short loc_1800B790F
0x1800b7901  cmp     ecx, 1
0x1800b7904  jnz     loc_1800B8A44
0x1800b790a  jmp     loc_1800B81CE
0x1800b790f  cmp     r13d, 2
0x1800b7913  jnz     loc_1800B79A0
0x1800b7919  mov     eax, 209h
0x1800b791e  cmp     [rdx+176h], ax
0x1800b7925  jnb     short loc_1800B79A0
0x1800b7927  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60895122@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122> `wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl(void)'::`2'::impl
0x1800b792e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(void)
0x1800b7933  test    al, al
0x1800b7935  jz      loc_1800B89A9
0x1800b793b  lea     rdx, [rsp+1A8h+var_148]
0x1800b7940  mov     rcx, [rsi]
0x1800b7943  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800b7948  nop
0x1800b7949  cmp     qword ptr [rax+18h], 7
0x1800b794e  jbe     short loc_1800B7953
0x1800b7950  mov     rax, [rax]
0x1800b7953  mov     [rsp+1A8h+var_178], rax
0x1800b7958  lea     rdx, [rsp+1A8h+var_168]
0x1800b795d  mov     rcx, [rsi]
0x1800b7960  call    ?Name@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(void)
0x1800b7965  cmp     qword ptr [rax+18h], 7
0x1800b796a  jbe     short loc_1800B796F
0x1800b796c  mov     rax, [rax]
0x1800b796f  mov     qword ptr [rsp+1A8h+packageFamilyNameLength], rax
0x1800b7977  lea     r8, aStaleoverridep; "StaleOverridePackage"
0x1800b797e  lea     rdx, [rsp+1A8h+var_178]
0x1800b7983  lea     rcx, [rsp+1A8h+packageFamilyNameLength]
0x1800b798b  call    ??$ExtensionFilteredOut@PEB_WPEB_WAEAY0BA@$$CB_W@AppExtensionsLogging@@SAX$$QEAPEB_W0AEAY0BA@$$CB_W@Z; AppExtensionsLogging::ExtensionFilteredOut<wchar_t const *,wchar_t const *,wchar_t const (&)[16]>(wchar_t const * &&,wchar_t const * &&,wchar_t const (&)[16])
0x1800b7990  lea     rcx, [rsp+1A8h+var_168]; this
0x1800b7995  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b799a  nop
0x1800b799b  jmp     loc_1800B8A35
0x1800b79a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56189266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56189266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56189266> `wil::Feature<__WilFeatureTraits_Feature_56189266>::GetImpl(void)'::`2'::impl
0x1800b79a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56189266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56189266>::__private_IsEnabled(void)
0x1800b79ac  test    al, al
0x1800b79ae  jz      loc_1800B7CC3
0x1800b79b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61119654@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654> `wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl(void)'::`2'::impl
0x1800b79bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(void)
0x1800b79c0  mov     rcx, [rsp+1A8h+var_178]
0x1800b79c5  test    byte ptr [rcx+18h], 0Ah
0x1800b79c9  jnz     loc_1800B7CC3
0x1800b79cf  test    al, al
0x1800b79d1  jz      loc_1800B7B53
0x1800b79d7  mov     rcx, [rsi]
0x1800b79da  mov     edx, [rcx+178h]
0x1800b79e0  sub     edx, 1
0x1800b79e3  jz      short loc_1800B79F3
0x1800b79e5  sub     edx, 1
0x1800b79e8  jz      short loc_1800B79F3
0x1800b79ea  cmp     edx, 1
0x1800b79ed  jnz     loc_1800B7CC3
0x1800b79f3  xor     edx, edx; Val
0x1800b79f5  mov     r8d, 82h; Size
0x1800b79fb  lea     rcx, [rsp+1A8h+packageFamilyName]; void *
0x1800b7a03  call    memset_0
0x1800b7a08  mov     [rsp+1A8h+packageFamilyNameLength], 41h ; 'A'
0x1800b7a13  lea     rdx, [rsp+1A8h+packageFamilyName]; packageFamilyName
0x1800b7a1b  lea     rcx, [rsp+1A8h+packageFamilyNameLength]; packageFamilyNameLength
0x1800b7a23  call    cs:__imp_GetCurrentPackageFamilyName
0x1800b7a29  test    eax, eax
0x1800b7a2b  js      loc_1800B7AE0
0x1800b7a31  lea     rdx, [rsp+1A8h+var_168]
0x1800b7a36  mov     rcx, [rsi]
0x1800b7a39  call    ?PackageFamilyName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(void)
0x1800b7a3e  cmp     qword ptr [rax+18h], 7
0x1800b7a43  jbe     short loc_1800B7A48
0x1800b7a45  mov     rax, [rax]
0x1800b7a48  mov     rdx, rax
0x1800b7a4b  lea     rcx, [rsp+1A8h+packageFamilyName]
0x1800b7a53  call    cs:__imp__o__wcsicmp
0x1800b7a59  mov     ebx, eax
0x1800b7a5b  lea     rcx, [rsp+1A8h+var_168]; this
0x1800b7a60  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800b7a65  test    ebx, ebx
0x1800b7a67  jz      loc_1800B7CC3
0x1800b7a6d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60895122@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122> `wil::Feature<__WilFeatureTraits_Feature_60895122>::GetImpl(void)'::`2'::impl
0x1800b7a74  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60895122@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60895122>::__private_IsEnabled(void)
0x1800b7a79  test    al, al
0x1800b7a7b  jz      loc_1800B89A9
0x1800b7a81  lea     rdx, [rsp+1A8h+var_148]
0x1800b7a86  mov     rcx, [rsi]
0x1800b7a89  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800b7a8e  nop
0x1800b7a8f  cmp     qword ptr [rax+18h], 7
0x1800b7a94  jbe     short loc_1800B7A99
0x1800b7a96  mov     rax, [rax]
0x1800b7a99  mov     [rsp+1A8h+var_178], rax
0x1800b7a9e  lea     rdx, [rsp+1A8h+var_168]
0x1800b7aa3  mov     rcx, [rsi]
0x1800b7aa6  call    ?Name@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Name(void)
0x1800b7aab  cmp     qword ptr [rax+18h], 7
0x1800b7ab0  jbe     short loc_1800B7AB5
0x1800b7ab2  mov     rax, [rax]
0x1800b7ab5  mov     [rsp+1A8h+var_170], rax
0x1800b7aba  lea     r8, aStoredelivered; "StoreDeliveredNotAllowed"
  ... truncated ...
```
