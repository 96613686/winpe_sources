# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::AppExtension::AddDependencyToProcessPackageGraphWithAliases(winrt::Windows::ApplicationModel::PackageSignatureKind,wchar_t const *,wchar_t const *,std::unordered_set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,bool,bool)

- ea: `0x18029b630`
- end: `0x18029c0bd`
- name: `?AddDependencyToProcessPackageGraphWithAliases@AppExtension@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@CAJW4PackageSignatureKind@4Windows@6@PEB_W1AEBV?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@_N3@Z`
- size: `2701`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `41`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a79c4`
- `0x18029b36c`
- `0x18029e77c`

## callees

- `0x18000460c`
- `0x180015344`
- `0x18002451c`
- `0x180025264`
- `0x18002547c`
- `0x180025c74`
- `0x180025d38`
- `0x180026860`
- `0x18003059c`
- `0x180030cc4`
- `0x180030d1c`
- `0x180035814`
- `0x180037500`
- `0x180037568`
- `0x1800483f4`
- `0x18006efd0`
- `0x18009b16c`
- `0x18009b194`
- `0x1800a08cc`
- `0x1800afccc`
- `0x1800ce1d4`
- `0x1800d97d0`
- `0x1800ea764`
- `0x1800ea94c`
- `0x1800ea988`
- `0x18010c438`
- `0x18010c460`
- `0x18010c4a4`
- `0x18011ed1c`
- `0x18015cb00`
- `0x18015d868`
- `0x180298f28`
- `0x180299000`
- `0x1802999b8`
- `0x180299b84`
- `0x18029ad38`
- `0x18029b020`
- `0x18029b184`
- `0x18029b630`
- `0x1802a036c`
- `0x1802a0914`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18029b70e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18029b70e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18029bfa4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18029bfa4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18029be07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18029be07`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!AddDependencyToProcessPackageGraph` at `0x18029b94e`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!AddDependencyToProcessPackageGraph` at `0x18029b94e`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!GetCurrentPackageInfo3` at `0x18029be9f`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!GetCurrentPackageInfo3` at `0x18029bf14`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!GetCurrentPackageInfo3` at `0x18029be9f`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!GetCurrentPackageInfo3` at `0x18029bf14`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x18029b6d7`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackageFamilyName` at `0x18029b6d7`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18029ba07`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18029ba07`
- `api-ms-win-appmodel-runtime-internal-l1-1-10!AddPackageNameAliasesByPackageFullName` at `0x18029bad1`
- `api-ms-win-appmodel-runtime-internal-l1-1-10!AddPackageNameAliasesByPackageFullName` at `0x18029bb33`
- `api-ms-win-appmodel-runtime-internal-l1-1-10!AddPackageNameAliasesByPackageFullName` at `0x18029bc61`
- `api-ms-win-appmodel-runtime-internal-l1-1-10!AddPackageNameAliasesByPackageFullName` at `0x18029bad1`
- `api-ms-win-appmodel-runtime-internal-l1-1-10!AddPackageNameAliasesByPackageFullName` at `0x18029bb33`
- `api-ms-win-appmodel-runtime-internal-l1-1-10!AddPackageNameAliasesByPackageFullName` at `0x18029bc61`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18029bb81`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18029bb81`
- `api-ms-win-appmodel-runtime-l1-1-7!AddPackageDependency2` at `0x18029bc04`
- `api-ms-win-appmodel-runtime-l1-1-7!AddPackageDependency2` at `0x18029bc04`

## string_xrefs

- `0x18029b6eb`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029b964`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029b987`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029bab7`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029baf0`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029bb9b`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029bc1e`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029bc7b`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029bf2a`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\AppExtension.cpp`
- `0x18029bd8f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Shell\Update\Packages\`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::AppExtension::AddDependencyToProcessPackageGraphWithAliases(
        int a1,
        __int64 a2,
        const WCHAR *a3,
        int *a4,
        char a5,
        char a6)
{
  bool v10; // al
  LONG CurrentPackageFamilyName; // eax
  char v12; // cl
  int v13; // eax
  __int64 v14; // rcx
  bool v15; // bl
  __int64 v16; // r14
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  int *v22; // rbx
  __int64 v23; // r8
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation *v24; // rcx
  __int64 v25; // rsi
  __int64 size_of; // rax
  __int64 v27; // rbx
  _QWORD *v28; // r8
  _QWORD *v29; // rax
  _QWORD *v30; // rdx
  _QWORD *v31; // rcx
  int v32; // eax
  int v33; // edi
  LONG PackagesByPackageFamily; // eax
  signed int v35; // edi
  UINT32 v36; // ebx
  PWSTR v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // r8
  wil::details::in1diag3 *v40; // rcx
  __int64 v41; // rdx
  int v42; // esi
  int PackageDependency; // eax
  int v44; // eax
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // r8
  bool v48; // bl
  bool v49; // bl
  __int64 v50; // rbx
  __int64 v51; // rax
  const WCHAR *v52; // rdx
  LSTATUS ValueW; // eax
  bool v54; // sf
  __int64 v55; // rcx
  __int64 v56; // r8
  int CurrentPackageInfo3; // ebx
  char *v58; // rsi
  char *v59; // rax
  size_t v60; // rbx
  LPCWCH *v61; // r15
  __int64 v62; // rsi
  __int64 v63; // rcx
  __int64 v64; // r8
  int v65; // r8d
  int v66; // r9d
  int bufferLength; // [rsp+20h] [rbp-E0h]
  int bufferLengtha; // [rsp+20h] [rbp-E0h]
  UINT32 *bufferLengthb; // [rsp+20h] [rbp-E0h]
  char v70[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v71; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v72[32]; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR packageFullNames; // [rsp+70h] [rbp-90h] BYREF
  __int64 v74; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v75[2]; // [rsp+80h] [rbp-80h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v77; // [rsp+98h] [rbp-68h] BYREF
  UINT32 count; // [rsp+A0h] [rbp-60h] BYREF
  int *v79; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v80; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v81; // [rsp+C0h] [rbp-40h]
  void *v82[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v83; // [rsp+D8h] [rbp-28h]
  LPCWSTR lpSubKey[5]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v85[32]; // [rsp+110h] [rbp+10h] BYREF
  char v86[32]; // [rsp+130h] [rbp+30h] BYREF
  int v87; // [rsp+150h] [rbp+50h] BYREF
  char v88[8]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v89; // [rsp+160h] [rbp+60h]
  char v90; // [rsp+190h] [rbp+90h]
  _BYTE v91[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v92[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v75[0] = a3;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53393585>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53393585>::GetImpl'::`2'::impl) )
    goto LABEL_21;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl) )
  {
    v10 = a1 == 0;
    goto LABEL_6;
  }
  if ( a1 != 1 )
  {
    v10 = 0;
LABEL_6:
    if ( !v10 )
      goto LABEL_21;
  }
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength[0] = 65;
  CurrentPackageFamilyName = GetCurrentPackageFamilyName(packageFamilyNameLength, packageFamilyName);
  if ( CurrentPackageFamilyName >= 0 )
  {
    v13 = _o__wcsicmp(packageFamilyName, a3);
    v12 = a5;
    if ( !v13 )
      v12 = 1;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
      (const char *)(unsigned int)CurrentPackageFamilyName,
      bufferLength);
    v12 = a5;
  }
  if ( !v12 )
  {
    std::wstring::wstring(lpSubKey, a3);
    v15 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage>>,0>>::find(
                       v14,
                       v75,
                       lpSubKey) == qword_1805F0718;
    std::filesystem::path::~path((std::filesystem::path *)lpSubKey);
    if ( v15 )
    {
      winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage::DeveloperPackage((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage *)v85);
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(a2 + 2 * v17) );
      std::wstring::_Assign<wchar_t>(v85, a2, v17);
      do
        ++v16;
      while ( a3[v16] );
      std::wstring::_Assign<wchar_t>(v86, a3, v16);
      if ( &v87 != a4 )
      {
        v79 = &v87;
        v87 = *a4;
        std::list<std::wstring>::_Assign_cast<std::wstring &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
          v88,
          **((_QWORD **)a4 + 1),
          *((_QWORD *)a4 + 1));
        v18 = std::_Hash<std::_Umap_traits<unsigned __int64,winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::DisplayMonitorInfo>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::DisplayMonitorInfo>>>,0>>::_Desired_grow_bucket_count(
                &v87,
                v89);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
          &v87,
          v18);
        v79 = 0;
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(&v79);
      }
      v90 = 0;
      std::wstring::wstring(lpSubKey, a3);
      v20 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage>>,0>>::_Try_emplace<std::wstring,>(
                        v19,
                        v75,
                        lpSubKey);
      winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage::operator=(*v20 + 48LL, v85);
      std::filesystem::path::~path((std::filesystem::path *)lpSubKey);
      winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage::~DeveloperPackage((winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage *)v85);
    }
    return 0;
  }
LABEL_21:
  v77 = 0;
  memset_0(v92, 0, sizeof(v92));
  tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::start_and_watch_errors(
    &v77,
    v92);
  v79 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
    &v77,
    &v79);
  v22 = v79;
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)(a2 + 2 * v23) );
  std::wstring::_Assign<wchar_t>(v79 + 90, a2, v23);
  *((_BYTE *)v22 + 292) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsRunningOnLocalSystem(v24);
  *((_BYTE *)v22 + 293) = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent;
  tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::close(&v79);
  v25 = (unsigned int)a4[4];
  v80 = 0;
  v81 = 0;
  if ( (_DWORD)v25 )
  {
    size_of = std::_Get_size_of_n<8>((unsigned int)v25);
    *(_QWORD *)&v80 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v27 = v80 + 8 * v25;
    v81 = v27;
    memset_0((void *)v80, 0, 8 * v25);
    *((_QWORD *)&v80 + 1) = v27;
    packageFullNames = 0;
    std::_Tidy_guard<std::vector<wchar_t const *>>::~_Tidy_guard<std::vector<wchar_t const *>>(&packageFullNames);
  }
  v28 = (_QWORD *)*((_QWORD *)a4 + 1);
  v29 = (_QWORD *)*v28;
  v30 = (_QWORD *)v80;
  while ( v29 != v28 )
  {
    v31 = v29 + 2;
    if ( v29[5] > 7u )
      v31 = (_QWORD *)*v31;
    *v30 = v31;
    v29 = (_QWORD *)*v29;
    ++v30;
  }
  if ( !a6 )
  {
    v32 = AddDependencyToProcessPackageGraph(a3, 0, 0, 3);
    v33 = v32;
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
        (const char *)(unsigned int)v32,
        bufferLength);
    v71 = v33;
    if ( v33 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
        (const char *)(unsigned int)v33,
        bufferLength);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                             &v77,
                             &packageFullNames)
              + 280LL) = v33;
    tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&packageFullNames);
    if ( v33 < 0 || !(_DWORD)v25 )
      goto LABEL_49;
    count = 1;
    packageFullNames = 0;
    packageFamilyNameLength[0] = 128;
    PackagesByPackageFamily = FindPackagesByPackageFamily(
                                a3,
                                0x10u,
                                &count,
                                &packageFullNames,
                                packageFamilyNameLength,
                                packageFamilyName,
                                0);
    v35 = PackagesByPackageFamily;
    if ( PackagesByPackageFamily > 0 )
      v35 = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                             &v77,
                             &v71)
              + 288LL) = v35;
    tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&v71);
    v36 = count;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                             &v77,
                             &v71)
              + 424LL) = v36;
    tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&v71);
    v37 = packageFullNames;
    if ( packageFullNames )
    {
      v38 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                         &v77,
                         &v71)
          + 392LL;
      v39 = -1;
      do
        ++v39;
      while ( v37[v39] );
      std::wstring::_Assign<wchar_t>(v38, v37, v39);
      tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&v71);
      v37 = packageFullNames;
    }
    if ( v35 >= 0 )
    {
      if ( count == 1 )
      {
        v33 = AddPackageNameAliasesByPackageFullName(v37, (unsigned int)v25, v80);
        v71 = v33;
        v40 = retaddr;
        if ( v33 >= 0 )
          goto LABEL_48;
        v41 = 493;
        goto LABEL_47;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1EA,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
        (const char *)(unsigned int)v35,
        bufferLengtha);
    }
    v33 = AddPackageNameAliasesByPackageFullName(a2, (unsigned int)v25, v80);
    v71 = v33;
    v40 = retaddr;
    if ( v33 >= 0 )
    {
LABEL_48:
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                               &v77,
                               &v74)
                + 284LL) = v33;
      tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&v74);
LABEL_49:
      v42 = v33;
      goto LABEL_66;
    }
    v41 = 502;
LABEL_47:
    wil::details::in1diag3::_Log_Hr(
      v40,
      (void *)v41,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
      (const char *)(unsigned int)v33,
      bufferLengtha);
    goto LABEL_48;
  }
  *(_QWORD *)packageFamilyNameLength = 0;
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    packageFamilyNameLength,
    0);
  PackageDependency = TryCreatePackageDependency(0, a3, 0, 0);
  v33 = PackageDependency;
  v71 = PackageDependency;
  if ( PackageDependency < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
      (const char *)(unsigned int)PackageDependency,
      0);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                           &v77,
                           &v74)
            + 276LL) = v33;
  tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&v74);
  if ( v33 < 0 )
  {
    v42 = v33;
  }
  else
  {
    packageFullNames = 0;
    v74 = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      &packageFullNames,
      0);
    bufferLengthb = (UINT32 *)&packageFullNames;
    v44 = AddPackageDependency2(*(_QWORD *)packageFamilyNameLength, 0, 3, &v74);
    v33 = v44;
    v71 = v44;
    if ( v44 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x217,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
        (const char *)(unsigned int)v44,
        (int)&packageFullNames);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                             &v77,
                             &count)
              + 280LL) = v33;
    tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&count);
    if ( v33 >= 0 && (_DWORD)v25 )
    {
      v45 = AddPackageNameAliasesByPackageFullName(packageFullNames, (unsigned int)v25, v80);
      v33 = v45;
      v71 = v45;
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x21C,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
          (const char *)(unsigned int)v45,
          (int)bufferLengthb);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(
                               &v77,
                               &count)
                + 284LL) = v33;
      tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&count);
    }
    v42 = v33;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&packageFullNames);
  }
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(packageFamilyNameLength);
LABEL_66:
  packageFullNames = 0;
  v46 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                     &packageFullNames,
                     &v74)
      + 280LL;
  v47 = -1;
  do
    ++v47;
  while ( *(_WORD *)(a2 + 2 * v47) );
  std::wstring::_Assign<wchar_t>(v46, a2, v47);
  tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
  v48 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                          &packageFullNames,
                          &v74)
           + 272LL) = v48;
  tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
  v49 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_storePackageLoaded;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                          &packageFullNames,
                          &v74)
           + 273LL) = v49;
  tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
  memset_0(v91, 0, sizeof(v91));
  tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::start_and_watch_errors(
    &packageFullNames,
    v91);
  if ( v42 < 0 )
    goto LABEL_95;
  v50 = std::wstring::wstring(v72, a3);
  v51 = std::wstring::wstring(v82, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Packages\\");
  std::operator+<wchar_t>(lpSubKey, v51, v50);
  std::filesystem::path::~path((std::filesystem::path *)v82);
  std::filesystem::path::~path((std::filesystem::path *)v72);
  v52 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v52 = lpSubKey[0];
  packageFamilyNameLength[0] = 254;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v52, L"PackageFullName", 2u, 0, packageFamilyName, packageFamilyNameLength);
  v54 = ValueW < 0;
  if ( ValueW )
  {
    packageFamilyName[0] = 0;
    if ( ValueW > 0 )
      v54 = 1;
  }
  if ( !v54 )
  {
    v55 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                       &packageFullNames,
                       &v74)
        + 344LL;
    v56 = -1;
    do
      ++v56;
    while ( packageFamilyName[v56] );
    std::wstring::_Assign<wchar_t>(v55, packageFamilyName, v56);
    tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
    *(_OWORD *)v82 = 0;
    v83 = 0;
    count = 0;
    packageFamilyNameLength[0] = 0;
    CurrentPackageInfo3 = GetCurrentPackageInfo3(1048624, 0, &count, 0);
    if ( CurrentPackageInfo3 != -2147024774 )
      goto LABEL_86;
    v58 = (char *)v82[1];
    if ( (void *)count < (void *)((char *)v82[1] - (char *)v82[0]) )
    {
      v59 = (char *)v82[0] + count;
LABEL_84:
      v82[1] = v59;
      goto LABEL_85;
    }
    if ( (void *)count > (void *)((char *)v82[1] - (char *)v82[0]) )
    {
      if ( count <= v83 - (unsigned __int64)v82[0] )
      {
        v60 = count - (unsigned __int64)((char *)v82[1] - (char *)v82[0]);
        memset_0(v82[1], 0, v60);
        v59 = &v58[v60];
        goto LABEL_84;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v82, count);
    }
LABEL_85:
    CurrentPackageInfo3 = GetCurrentPackageInfo3(1048624, 0, &count, v82[0]);
LABEL_86:
    if ( CurrentPackageInfo3 >= 0 )
    {
      v61 = (LPCWCH *)v82[0];
      v62 = *((_QWORD *)v82[0] + 2);
      if ( v62 )
      {
        v63 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                           &packageFullNames,
                           &v74)
            + 312LL;
        v64 = -1;
        do
          ++v64;
        while ( *(_WORD *)(v62 + 2 * v64) );
        std::wstring::_Assign<wchar_t>(v63, v62, v64);
        tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
        if ( CompareStringOrdinal(v61[2], -1, packageFamilyName, -1, 1) != 2 )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                                  &packageFullNames,
                                  &v74)
                   + 274LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x251,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\AppExtension.cpp",
        (const char *)(unsigned int)CurrentPackageInfo3,
        (int)packageFamilyNameLength);
    }
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::operator->(
                             &packageFullNames,
                             &v74)
              + 276LL) = CurrentPackageInfo3;
    tip2::test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(&v74);
    std::vector<unsigned char>::_Tidy(v82);
  }
  std::filesystem::path::~path((std::filesystem::path *)lpSubKey);
LABEL_95:
  if ( packageFullNames )
    tip2::details::shared_data<0,0,0>::complete_without_lock(packageFullNames + 4);
  tip2::test_watcher<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>::~test_watcher<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>>(v91);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PackageVersionTest,_tip_PackageVersionTest>,wil::err_returncode_policy>(&packageFullNames);
  if ( v77 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v77 + 8);
  if ( v33 < 0 )
  {
    v70[0] = 1;
    AppExtensionsLogging::AddDependencyToProcessPackageGraphError<long &,wchar_t const * &,wchar_t const (&)[1],wchar_t const (&)[1],bool>(
      (unsigned int)&v71,
      (unsigned int)v75,
      v65,
      v66,
      (__int64)v70);
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,bool>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,bool>>>>>>(&v80);
  tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(&v79);
  tip2::test_watcher<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_watcher<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(v92);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>,wil::err_returncode_policy>(&v77);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x18029b630  mov     [rsp-8+arg_0], rbx
0x18029b635  push    rbp
0x18029b636  push    rsi
0x18029b637  push    rdi
0x18029b638  push    r12
0x18029b63a  push    r13
0x18029b63c  push    r14
0x18029b63e  push    r15
0x18029b640  lea     rbp, [rsp-230h]
0x18029b648  sub     rsp, 330h
0x18029b64f  mov     rax, cs:__security_cookie
0x18029b656  xor     rax, rsp
0x18029b659  mov     [rbp+260h+var_40], rax
0x18029b660  mov     rdi, r9
0x18029b663  mov     r15, r8
0x18029b666  mov     r12, rdx
0x18029b669  mov     ebx, ecx
0x18029b66b  mov     [rbp+260h+var_2E0], r8
0x18029b66f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53393585@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53393585@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53393585> `wil::Feature<__WilFeatureTraits_Feature_53393585>::GetImpl(void)'::`2'::impl
0x18029b676  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53393585@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53393585>::__private_IsEnabled(void)
0x18029b67b  mov     esi, 1
0x18029b680  xor     r13d, r13d
0x18029b683  test    al, al
0x18029b685  jz      loc_18029B83A
0x18029b68b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61119654@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654> `wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl(void)'::`2'::impl
0x18029b692  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(void)
0x18029b697  test    al, al
0x18029b699  jz      short loc_18029B6A2
0x18029b69b  test    ebx, ebx
0x18029b69d  setz    al
0x18029b6a0  jmp     short loc_18029B6A9
0x18029b6a2  cmp     ebx, esi
0x18029b6a4  jz      short loc_18029B6B1
0x18029b6a6  mov     al, r13b
0x18029b6a9  test    al, al
0x18029b6ab  jz      loc_18029B83A
0x18029b6b1  xor     edx, edx; Val
0x18029b6b3  mov     r8d, 82h; Size
0x18029b6b9  lea     rcx, [rbp+260h+packageFamilyName]; void *
0x18029b6c0  call    memset_0
0x18029b6c5  mov     [rbp+260h+packageFamilyNameLength], 41h ; 'A'
0x18029b6cc  lea     rdx, [rbp+260h+packageFamilyName]; packageFamilyName
0x18029b6d3  lea     rcx, [rbp+260h+packageFamilyNameLength]; packageFamilyNameLength
0x18029b6d7  call    cs:__imp_GetCurrentPackageFamilyName
0x18029b6dd  mov     rcx, [rbp+268h]; this
0x18029b6e4  test    eax, eax
0x18029b6e6  jns     short loc_18029B704
0x18029b6e8  mov     r9d, eax; char *
0x18029b6eb  lea     r8, aShellcommonUnd_32; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18029b6f2  mov     edx, 186h; void *
0x18029b6f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029b6fc  mov     cl, [rbp+260h+arg_20]
0x18029b702  jmp     short loc_18029B720
0x18029b704  mov     rdx, r15
0x18029b707  lea     rcx, [rbp+260h+packageFamilyName]
0x18029b70e  call    cs:__imp__o__wcsicmp
0x18029b714  movzx   ecx, [rbp+260h+arg_20]
0x18029b71b  test    eax, eax
0x18029b71d  cmovz   ecx, esi
0x18029b720  test    cl, cl
0x18029b722  jnz     loc_18029B83A
0x18029b728  mov     rdx, r15
0x18029b72b  lea     rcx, [rbp+260h+lpSubKey]
0x18029b72f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18029b734  lea     r8, [rbp+260h+lpSubKey]
0x18029b738  lea     rdx, [rbp+260h+var_2E0]
0x18029b73c  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage>>,0>>::find(std::wstring const &)
0x18029b741  mov     rcx, cs:qword_1805F0718
0x18029b748  cmp     [rax], rcx
0x18029b74b  setz    bl
0x18029b74e  lea     rcx, [rbp+260h+lpSubKey]; this
0x18029b752  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18029b757  test    bl, bl
0x18029b759  jz      loc_18029B833
0x18029b75f  lea     rcx, [rbp+260h+var_250]; this
0x18029b763  call    ??0DeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage::DeveloperPackage(void)
0x18029b768  nop
0x18029b769  or      r14, 0FFFFFFFFFFFFFFFFh
0x18029b76d  mov     r8, r14
0x18029b770  inc     r8
0x18029b773  cmp     [r12+r8*2], r13w
0x18029b778  jnz     short loc_18029B770
0x18029b77a  mov     rdx, r12
0x18029b77d  lea     rcx, [rbp+260h+var_250]
0x18029b781  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18029b786  inc     r14
0x18029b789  cmp     [r15+r14*2], r13w
0x18029b78e  jnz     short loc_18029B786
0x18029b790  mov     r8, r14
0x18029b793  mov     rdx, r15
0x18029b796  lea     rcx, [rbp+260h+var_230]
0x18029b79a  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18029b79f  lea     rax, [rbp+260h+var_210]
0x18029b7a3  cmp     rax, rdi
0x18029b7a6  jz      short loc_18029B7EE
0x18029b7a8  lea     rax, [rbp+260h+var_210]
0x18029b7ac  mov     [rbp+260h+var_2B8], rax
0x18029b7b0  mov     eax, [rdi]
0x18029b7b2  mov     [rbp+260h+var_210], eax
0x18029b7b5  mov     rdx, [rdi+8]
0x18029b7b9  mov     r8, rdx
0x18029b7bc  mov     rdx, [rdx]
0x18029b7bf  lea     rcx, [rbp+260h+var_208]
0x18029b7c3  call    ??$_Assign_cast@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<std::wstring>::_Assign_cast<std::wstring &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18029b7c8  mov     rdx, [rbp+260h+var_200]
0x18029b7cc  lea     rcx, [rbp+260h+var_210]
0x18029b7d0  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@_KU?$com_ptr@UDisplayMonitorInfo@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KU?$com_ptr@UDisplayMonitorInfo@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@@std@@@4@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::DisplayMonitorInfo>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::DisplayMonitorInfo>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18029b7d5  mov     rdx, rax
0x18029b7d8  lea     rcx, [rbp+260h+var_210]
0x18029b7dc  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x18029b7e1  mov     [rbp+260h+var_2B8], r13
0x18029b7e5  lea     rcx, [rbp+260h+var_2B8]
0x18029b7e9  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(void)
0x18029b7ee  mov     [rbp+260h+var_1D0], r13b
0x18029b7f5  mov     rdx, r15
0x18029b7f8  lea     rcx, [rbp+260h+lpSubKey]
0x18029b7fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18029b801  nop
0x18029b802  lea     r8, [rbp+260h+lpSubKey]
0x18029b806  lea     rdx, [rbp+260h+var_2E0]
0x18029b80a  call    ??$_Try_emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18029b80f  mov     rcx, [rax]
0x18029b812  add     rcx, 30h ; '0'
0x18029b816  lea     rdx, [rbp+260h+var_250]
0x18029b81a  call    ??4DeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAAAEAU012345@AEBU012345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage::operator=(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage const &)
0x18029b81f  nop
0x18029b820  lea     rcx, [rbp+260h+lpSubKey]; this
0x18029b824  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18029b829  nop
0x18029b82a  lea     rcx, [rbp+260h+var_250]; this
0x18029b82e  call    ??1DeveloperPackage@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::DeveloperPackage::~DeveloperPackage(void)
0x18029b833  xor     eax, eax
0x18029b835  jmp     loc_18029C093
0x18029b83a  mov     [rbp+260h+var_2C8], r13
0x18029b83e  xor     edx, edx; Val
0x18029b840  lea     r8d, [rdx+40h]; Size
0x18029b844  lea     rcx, [rbp+260h+var_180]; void *
0x18029b84b  call    memset_0
0x18029b850  lea     rdx, [rbp+260h+var_180]
0x18029b857  lea     rcx, [rbp+260h+var_2C8]
0x18029b85b  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::start_and_watch_errors(void)
0x18029b860  nop
0x18029b861  mov     [rbp+260h+var_2B8], r13
0x18029b865  lea     rdx, [rbp+260h+var_2B8]
0x18029b869  lea     rcx, [rbp+260h+var_2C8]
0x18029b86d  call    ??C?$tip_test@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(void)
0x18029b872  nop
0x18029b873  mov     rbx, [rbp+260h+var_2B8]
0x18029b877  lea     rcx, [rbx+168h]
0x18029b87e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18029b882  mov     r8, r14
0x18029b885  inc     r8
0x18029b888  cmp     [r12+r8*2], r13w
0x18029b88d  jnz     short loc_18029B885
0x18029b88f  mov     rdx, r12
0x18029b892  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18029b897  call    ?IsRunningOnLocalSystem@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA_NXZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::IsRunningOnLocalSystem(void)
0x18029b89c  mov     [rbx+124h], al
0x18029b8a2  mov     al, cs:?g_unsignedPackagePresent@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3_NA; bool winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackagePresent
0x18029b8a8  mov     [rbx+125h], al
0x18029b8ae  lea     rcx, [rbp+260h+var_2B8]
0x18029b8b2  call    ?close@?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::close(void)
0x18029b8b7  mov     esi, [rdi+10h]
0x18029b8ba  xorps   xmm1, xmm1
0x18029b8bd  movdqu  [rbp+260h+var_2B0], xmm1
0x18029b8c2  mov     [rbp+260h+var_2A0], r13
0x18029b8c6  test    esi, esi
0x18029b8c8  jz      short loc_18029B90B
0x18029b8ca  mov     ecx, esi
0x18029b8cc  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18029b8d1  mov     rcx, rax
0x18029b8d4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18029b8d9  mov     qword ptr [rbp+260h+var_2B0], rax
0x18029b8dd  lea     r8, ds:0[rsi*8]; Size
0x18029b8e5  lea     rbx, [rax+r8]
0x18029b8e9  mov     [rbp+260h+var_2A0], rbx
0x18029b8ed  xor     edx, edx; Val
0x18029b8ef  mov     rcx, rax; void *
0x18029b8f2  call    memset_0
0x18029b8f7  mov     qword ptr [rbp+260h+var_2B0+8], rbx
0x18029b8fb  mov     [rsp+360h+packageFullNames], r13
0x18029b900  lea     rcx, [rsp+360h+packageFullNames]
0x18029b905  call    ??1?$_Tidy_guard@V?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<wchar_t const *>>::~_Tidy_guard<std::vector<wchar_t const *>>(void)
0x18029b90a  nop
0x18029b90b  mov     r8, [rdi+8]
0x18029b90f  mov     rax, [r8]
0x18029b912  mov     rdx, qword ptr [rbp+260h+var_2B0]
0x18029b916  cmp     rax, r8
0x18029b919  jz      short loc_18029B935
0x18029b91b  lea     rcx, [rax+10h]
0x18029b91f  cmp     qword ptr [rax+28h], 7
0x18029b924  jbe     short loc_18029B929
0x18029b926  mov     rcx, [rcx]
0x18029b929  mov     [rdx], rcx
0x18029b92c  mov     rax, [rax]
0x18029b92f  add     rdx, 8
0x18029b933  jmp     short loc_18029B916
0x18029b935  xor     edx, edx
0x18029b937  cmp     [rbp+260h+arg_28], r13b
0x18029b93e  jnz     loc_18029BB51
0x18029b944  lea     r9d, [rdx+3]
0x18029b948  xor     r8d, r8d
0x18029b94b  mov     rcx, r15
0x18029b94e  call    cs:__imp_AddDependencyToProcessPackageGraph
0x18029b954  mov     edi, eax
0x18029b956  mov     rcx, [rbp+268h]; this
0x18029b95d  test    eax, eax
0x18029b95f  jns     short loc_18029B975
0x18029b961  mov     r9d, eax; char *
0x18029b964  lea     r8, aShellcommonUnd_32; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18029b96b  mov     edx, 1D2h; void *
0x18029b970  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029b975  mov     [rsp+360h+var_318], edi
0x18029b979  mov     rcx, [rbp+268h]; this
0x18029b980  test    edi, edi
0x18029b982  jns     short loc_18029B998
0x18029b984  mov     r9d, edi; char *
0x18029b987  lea     r8, aShellcommonUnd_32; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18029b98e  mov     edx, 1D3h; void *
0x18029b993  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029b998  lea     rdx, [rsp+360h+packageFullNames]
0x18029b99d  lea     rcx, [rbp+260h+var_2C8]
0x18029b9a1  call    ??C?$tip_test@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(void)
0x18029b9a6  mov     rcx, [rax]
0x18029b9a9  mov     [rcx+118h], edi
0x18029b9af  lea     rcx, [rsp+360h+packageFullNames]
0x18029b9b4  call    ??1?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(void)
0x18029b9b9  test    edi, edi
0x18029b9bb  js      loc_18029BB1D
0x18029b9c1  test    esi, esi
0x18029b9c3  jz      loc_18029BB1D
0x18029b9c9  mov     [rbp+260h+count], 1
0x18029b9d0  mov     [rsp+360h+packageFullNames], r13
0x18029b9d5  mov     [rbp+260h+packageFamilyNameLength], 80h
0x18029b9dc  mov     [rsp+360h+packageProperties], r13; packageProperties
0x18029b9e1  lea     rax, [rbp+260h+packageFamilyName]
0x18029b9e8  mov     [rsp+360h+buffer], rax; buffer
0x18029b9ed  lea     rax, [rbp+260h+packageFamilyNameLength]
0x18029b9f1  mov     [rsp+360h+bufferLength], rax; int
0x18029b9f6  lea     r9, [rsp+360h+packageFullNames]; packageFullNames
0x18029b9fb  lea     r8, [rbp+260h+count]; count
0x18029b9ff  mov     edx, 10h; packageFilters
0x18029ba04  mov     rcx, r15; packageFamilyName
0x18029ba07  call    cs:__imp_FindPackagesByPackageFamily
0x18029ba0d  mov     edi, eax
0x18029ba0f  test    eax, eax
0x18029ba11  jle     short loc_18029BA1C
0x18029ba13  movzx   edi, ax
0x18029ba16  or      edi, 80070000h
0x18029ba1c  lea     rdx, [rsp+360h+var_318]
0x18029ba21  lea     rcx, [rbp+260h+var_2C8]
0x18029ba25  call    ??C?$tip_test@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(void)
0x18029ba2a  mov     rcx, [rax]
0x18029ba2d  mov     [rcx+120h], edi
0x18029ba33  lea     rcx, [rsp+360h+var_318]
0x18029ba38  call    ??1?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(void)
0x18029ba3d  mov     ebx, [rbp+260h+count]
0x18029ba40  lea     rdx, [rsp+360h+var_318]
0x18029ba45  lea     rcx, [rbp+260h+var_2C8]
0x18029ba49  call    ??C?$tip_test@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(void)
0x18029ba4e  mov     rcx, [rax]
0x18029ba51  mov     [rcx+1A8h], ebx
0x18029ba57  lea     rcx, [rsp+360h+var_318]
0x18029ba5c  call    ??1?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(void)
0x18029ba61  mov     rbx, [rsp+360h+packageFullNames]
0x18029ba66  test    rbx, rbx
0x18029ba69  jz      short loc_18029BAA9
0x18029ba6b  lea     rdx, [rsp+360h+var_318]
0x18029ba70  lea     rcx, [rbp+260h+var_2C8]
0x18029ba74  call    ??C?$tip_test@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::operator->(void)
0x18029ba79  nop
0x18029ba7a  mov     rcx, [rax]
0x18029ba7d  add     rcx, 188h
0x18029ba84  mov     r8, r14
0x18029ba87  inc     r8
0x18029ba8a  cmp     [rbx+r8*2], r13w
0x18029ba8f  jnz     short loc_18029BA87
0x18029ba91  mov     rdx, rbx
0x18029ba94  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18029ba99  nop
0x18029ba9a  lea     rcx, [rsp+360h+var_318]
0x18029ba9f  call    ??1?$test_data_control@V?$merged_data@U_tip_PackageDependenciesTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>::~test_data_control<tip2::details::merged_data<_tip_PackageDependenciesTest,_tip_PackageDependenciesTest>>(void)
0x18029baa4  mov     rbx, [rsp+360h+packageFullNames]
0x18029baa9  mov     rcx, [rbp+268h]; this
0x18029bab0  test    edi, edi
0x18029bab2  jns     short loc_18029BB24
0x18029bab4  mov     r9d, edi; char *
0x18029bab7  lea     r8, aShellcommonUnd_32; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18029babe  mov     edx, 1EAh; void *
0x18029bac3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029bac8  mov     r8, qword ptr [rbp+260h+var_2B0]
0x18029bacc  mov     edx, esi
0x18029bace  mov     rcx, r12
0x18029bad1  call    cs:__imp_AddPackageNameAliasesByPackageFullName
0x18029bad7  mov     edi, eax
0x18029bad9  mov     [rsp+360h+var_318], eax
0x18029badd  mov     rcx, [rbp+268h]; this
0x18029bae4  test    eax, eax
0x18029bae6  jns     short loc_18029BAFC
0x18029bae8  mov     edx, 1F6h; void *
  ... truncated ...
```
