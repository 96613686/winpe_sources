# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::AppExtension::AddExtensionPackagesToProcessPackageGraph(winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions)

- ea: `0x1800a79c4`
- end: `0x1800a83bc`
- name: `?AddExtensionPackagesToProcessPackageGraph@AppExtension@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SAXW4AppExtensionOptions@3456@@Z`
- size: `2552`
- prototype: ``
- caller_count: `5`
- callee_count: `50`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020464`
- `0x1800a79a0`
- `0x18029c0d0`
- `0x1802a74ac`
- `0x1802a77f4`

## callees

- `0x180005a74`
- `0x18000b428`
- `0x18000d23c`
- `0x180011e64`
- `0x180020a14`
- `0x180021ae8`
- `0x180021b30`
- `0x180021b74`
- `0x180021bbc`
- `0x180021cd0`
- `0x180023280`
- `0x180025348`
- `0x180025364`
- `0x1800260c0`
- `0x1800262dc`
- `0x180026860`
- `0x180027af0`
- `0x18002881c`
- `0x180028978`
- `0x18002a054`
- `0x1800304e8`
- `0x180030764`
- `0x180038f3c`
- `0x1800535d4`
- `0x180053b34`
- `0x180053be8`
- `0x180053f7c`
- `0x18005edb0`
- `0x1800702a8`
- `0x180072c50`
- `0x1800944d4`
- `0x1800a79c4`
- `0x1800d6d38`
- `0x1800ea764`
- `0x180102c20`
- `0x180108890`
- `0x18010aef4`
- `0x18010e284`
- `0x18015cb00`
- `0x18015d868`
- `0x18015d898`
- `0x180294f10`
- `0x180299a8c`
- `0x18029b130`
- `0x18029b630`
- `0x1802a0330`
- `0x1802a036c`
- `0x1802a03e4`
- `0x1802a0970`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7d69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7df5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7ed3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7d69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7df5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a7ed3`

## string_xrefs

- `0x1800a7b31`: `com.microsoft.windows.extensionpackage`
- `0x1800a7bad`: `com.microsoft.windows.extensionpackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::AppExtension::AddExtensionPackagesToProcessPackageGraph(
        unsigned int a1)
{
  unsigned int v1; // esi
  __int64 v2; // rdi
  int v3; // r13d
  bool v4; // zf
  unsigned int v5; // eax
  __int64 FilteredExtensionList; // rax
  __int64 v7; // r9
  _QWORD *v8; // rcx
  _QWORD *v9; // rdx
  __int64 v10; // rax
  _QWORD *v11; // r14
  __int64 v12; // rbx
  _QWORD *v13; // r15
  int v14; // esi
  int v15; // ecx
  char v16; // al
  __int64 v17; // rax
  int v18; // r14d
  winrt::hstring *RetailPackageFamilyName; // rax
  const WCHAR *v20; // rax
  const WCHAR *v21; // rcx
  int v22; // edi
  __int64 v23; // rcx
  __int64 v24; // rax
  char IsEnabled; // al
  int v26; // edx
  const WCHAR *v27; // rax
  const WCHAR *v28; // rcx
  const wchar_t *v29; // rax
  const WCHAR *v30; // r8
  _QWORD *v31; // rax
  void (__fastcall ***v32)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v33; // rax
  __int64 v34; // rdi
  __int64 v35; // r14
  const wchar_t *v36; // rax
  const WCHAR *v37; // r8
  const struct winrt::impl::slim_source_location *v39; // rax
  char v40; // [rsp+30h] [rbp-D0h]
  int v41; // [rsp+34h] [rbp-CCh]
  char v42; // [rsp+38h] [rbp-C8h]
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v46[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v47[24]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v48[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v50[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v51[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v52[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v53[16]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v54[7]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v55; // [rsp+118h] [rbp+18h]
  _QWORD v56[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v57; // [rsp+158h] [rbp+58h]
  _BYTE v58[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v59[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v60[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v61[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v62[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v63[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v64; // [rsp+200h] [rbp+100h] BYREF
  __int64 v65; // [rsp+208h] [rbp+108h] BYREF
  __int64 v66; // [rsp+210h] [rbp+110h] BYREF
  __int64 v67; // [rsp+218h] [rbp+118h] BYREF
  __int64 v68; // [rsp+220h] [rbp+120h] BYREF
  __int128 pExceptionObject; // [rsp+228h] [rbp+128h] BYREF
  __int64 v70; // [rsp+238h] [rbp+138h]
  void (__fastcall ***v71)(_QWORD, __int64 *, __int64 *); // [rsp+240h] [rbp+140h] BYREF
  __int64 v72; // [rsp+248h] [rbp+148h] BYREF
  __int64 v73; // [rsp+250h] [rbp+150h] BYREF
  unsigned int v74; // [rsp+258h] [rbp+158h]
  LPCWCH lpString1[3]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int64 v76; // [rsp+278h] [rbp+178h]
  _BYTE v77[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v78[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v79[16]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v80[8]; // [rsp+300h] [rbp+200h] BYREF
  __int64 v81; // [rsp+308h] [rbp+208h]

  v1 = a1;
  v42 = a1;
  v2 = 0;
  v3 = 0;
  LODWORD(v64) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl'::`2'::impl)
    && (v1 & 0x20) != 0 )
  {
    v39 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v47);
    winrt::hresult_invalid_argument::hresult_invalid_argument((winrt::hresult_invalid_argument *)&pExceptionObject, v39);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject;
  }
  v45 = 0;
  wil::AcquireSRWLockExclusive(&v45, &qword_1805EA2C0);
  if ( !byte_1805EA2BA )
  {
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    byte_1805EA2BA = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl'::`2'::impl) )
  {
    if ( !byte_1805EA2BB || !byte_1805EA2B8 && (v1 & 1) != 0 )
      goto LABEL_15;
    if ( byte_1805EA2B9 )
      return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v45);
    v4 = (v1 & 0x40) == 0;
    goto LABEL_14;
  }
  if ( byte_1805EA2B8 )
    return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v45);
  if ( byte_1805EA2BB )
  {
    v4 = (v1 & 1) == 0;
LABEL_14:
    if ( v4 )
      return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v45);
  }
LABEL_15:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56189266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56189266>::GetImpl'::`2'::impl) )
  {
    v1 |= 8u;
    v42 = v1;
    v5 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheOptionsFromAppExtensionOptions(v1);
  }
  else
  {
    v5 = 2 * (v1 & 1 | 2);
  }
  *(_OWORD *)v46 = 0;
  winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetExtensionCache(v46, v5);
  pExceptionObject = 0;
  v70 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl'::`2'::impl) )
  {
    v54[0] = off_1804C75C8;
    v55 = v54;
    winrt::hstring::hstring((winrt::hstring *)&v66, L"com.microsoft.windows.extensionpackage");
    FilteredExtensionList = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetFilteredExtensionList(
                              v46[0],
                              (unsigned int)v47,
                              (unsigned int)&v66,
                              (v1 & 0x40 | 6) >> 1,
                              (__int64)v54);
    std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::operator=(
      &pExceptionObject,
      FilteredExtensionList);
    std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(v47);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v66);
    v8 = v55;
    if ( v55 )
    {
      v9 = v54;
LABEL_23:
      LOBYTE(v9) = v8 != v9;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v9);
    }
  }
  else
  {
    v56[0] = off_1804C75C8;
    v57 = v56;
    winrt::hstring::hstring((winrt::hstring *)&v66, L"com.microsoft.windows.extensionpackage");
    v10 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetFilteredExtensionList(
            v46[0],
            (unsigned int)v47,
            (unsigned int)&v66,
            3,
            (__int64)v56);
    std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::operator=(
      &pExceptionObject,
      v10);
    std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(v47);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v66);
    v8 = v57;
    if ( v57 )
    {
      v9 = v56;
      goto LABEL_23;
    }
  }
  v11 = (_QWORD *)*((_QWORD *)&pExceptionObject + 1);
  LOBYTE(v7) = v40;
  std::_Sort_unchecked_std::shared_ptr_winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo_____lambda_6efb020e1f710d93d10b2ba822f4bb78___(
    pExceptionObject,
    *((_QWORD *)&pExceptionObject + 1),
    (__int64)(*((_QWORD *)&pExceptionObject + 1) - pExceptionObject) >> 4,
    v7);
  memset_0(v80, 0, 0x40u);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v80);
  memset_0(v79, 0, sizeof(v79));
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v79);
  v49 = 0;
  v68 = 0;
  v12 = 0;
  v67 = 0;
  if ( v11 == (_QWORD *)pExceptionObject )
    goto LABEL_102;
  v41 = 0;
  v13 = (_QWORD *)pExceptionObject;
  v14 = v1 & 0x11;
  do
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl'::`2'::impl) )
    {
      v15 = *(_DWORD *)(*v13 + 380LL);
      if ( v15 == 1 || (v16 = 0, v15 == 4) )
        v16 = 1;
      if ( (!byte_1805EA2B8 || v15 != 3) && (!byte_1805EA2B9 || v15 != 2) && (!byte_1805EA2BB || !v16) )
        goto LABEL_46;
    }
    else
    {
      if ( byte_1805EA2BB )
      {
        v17 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PublisherId(*v13, v52);
        v3 |= 1u;
        if ( *(_QWORD *)(v17 + 24) > 7u )
          v17 = *(_QWORD *)v17;
        if ( CompareStringOrdinal((LPCWCH)v17, -1, L"cw5n1h2txyewy", -1, 1) == 2 )
          LOBYTE(v2) = 1;
      }
      if ( (v3 & 1) != 0 )
      {
        v3 &= ~1u;
        std::filesystem::path::~path((std::filesystem::path *)v52);
      }
      if ( !(_BYTE)v2 )
      {
        v2 = 0;
LABEL_46:
        v18 = *(_DWORD *)(*v13 + 376LL);
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(
          *v13,
          lpString1);
        if ( !v14 && v18 == 3 )
        {
          RetailPackageFamilyName = (winrt::hstring *)GetRetailPackageFamilyName(v48);
          v20 = winrt::hstring::c_str(RetailPackageFamilyName);
          v21 = (const WCHAR *)lpString1;
          if ( v76 > 7 )
            v21 = lpString1[0];
          v22 = CompareStringOrdinal(v21, -1, v20, -1, 1);
          winrt::handle_type<winrt::impl::hstring_traits>::close(v48);
          if ( v22 == 2 )
          {
            v2 = 0;
            goto LABEL_52;
          }
LABEL_95:
          std::filesystem::path::~path((std::filesystem::path *)lpString1);
          v11 = (_QWORD *)*((_QWORD *)&pExceptionObject + 1);
          goto LABEL_96;
        }
LABEL_52:
        v23 = *v13;
        if ( *(_DWORD *)(*v13 + 376LL) == 3 )
        {
          winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_storePackageLoaded = 1;
          if ( !qword_1805EC5F8 )
          {
            v24 = winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(
                    v23,
                    v60);
            std::wstring::operator=(
              winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_storePackageFullName,
              v24);
            std::filesystem::path::~path((std::filesystem::path *)v60);
          }
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53393585>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53393585>::GetImpl'::`2'::impl) )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl'::`2'::impl);
          v26 = *(_DWORD *)(*v13 + 376LL);
          if ( IsEnabled )
          {
            if ( v26 )
              goto LABEL_61;
LABEL_60:
            winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackageLoaded = 1;
          }
          else if ( v26 == 1 )
          {
            goto LABEL_60;
          }
        }
LABEL_61:
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(*v13, v78);
        v27 = winrt::hstring::c_str((winrt::hstring *)&v68);
        v28 = (const WCHAR *)lpString1;
        if ( v76 > 7 )
          v28 = lpString1[0];
        if ( CompareStringOrdinal(v28, -1, v27, -1, 1) != 2 )
        {
          if ( v12 )
          {
            winrt::hstring::c_str((winrt::hstring *)&v68);
            v29 = winrt::hstring::c_str((winrt::hstring *)&v67);
            winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::AppExtension::AddDependencyToProcessPackageGraphWithAliases(
              v41,
              (__int64)v29,
              v30,
              v79,
              0,
              0);
          }
          v41 = v18;
          std::wstring::operator std::wstring_view(lpString1, v50);
          winrt::hstring::operator=(&v68, v50);
          std::wstring::operator std::wstring_view(v78, v51);
          winrt::hstring::operator=(&v67, v51);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear(v79);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear(v80);
          v12 = v67;
        }
        winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::Id(*v13, v77);
        v31 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                          v80,
                          v53,
                          v77);
        if ( *v31 == v81 )
        {
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
            v80,
            v59,
            v77);
          winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::GetExtensionProperties(
            *v13,
            &v43);
          if ( v43 )
          {
            winrt::param::hstring::hstring((winrt::param::hstring *)v61, L"PackageAliases");
            if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                                    &v43,
                                    v61) )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)v52, L"PackageAliases");
              v32 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64 *))winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                                                                             &v43,
                                                                             &v44,
                                                                             v52);
              v65 = 0;
              if ( v32 )
              {
                (**v32)(v32, &winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IPropertySet>, &v65);
                v2 = v65;
              }
              if ( v44 )
                winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v44);
              if ( v2 )
              {
                winrt::param::hstring::hstring((winrt::param::hstring *)v62, L"PackageAlias");
                if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                                        &v65,
                                        v62) )
                {
                  winrt::param::hstring::hstring((winrt::param::hstring *)v63, L"PackageAlias");
                  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                    &v65,
                    &v71,
                    v63);
                  v64 = 0;
                  if ( v71 )
                  {
                    (**v71)(v71, &winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v64);
                    v33 = v64;
                  }
                  else
                  {
                    v33 = 0;
                  }
                  if ( v33
                    && (unsigned int)winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::Type(&v64) == 1037 )
                  {
                    v73 = 0;
                    v74 = 0;
                    winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetInspectableArray(
                      &v64,
                      &v73);
                    v34 = v73;
                    v35 = v73 + 8LL * v74;
                    while ( v34 != v35 )
                    {
                      winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtractTextContentFromXmlPropertySet(
                        &v72,
                        v34);
                      if ( v72 )
                        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<winrt::hstring &>(
                          v79,
                          v58,
                          &v72);
                      winrt::handle_type<winrt::impl::hstring_traits>::close(&v72);
                      v34 += 8;
                    }
                    winrt::com_array<winrt::Windows::Foundation::IInspectable>::clear(&v73);
                  }
                  else
                  {
                    winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtractTextContentFromXmlPropertySet(
                      &v66,
                      &v71);
                    if ( v66 )
                      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<winrt::hstring &>(
                        v79,
                        v47,
                        &v66);
                    winrt::handle_type<winrt::impl::hstring_traits>::close(&v66);
                  }
                  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v64);
                  if ( v71 )
                    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v71);
                }
              }
              winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v65);
            }
          }
          winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v43);
        }
        std::filesystem::path::~path((std::filesystem::path *)v77);
        std::filesystem::path::~path((std::filesystem::path *)v78);
        goto LABEL_95;
      }
    }
LABEL_96:
    v13 += 2;
    v2 = 0;
  }
  while ( v13 != v11 );
  if ( v12 )
  {
    winrt::hstring::c_str((winrt::hstring *)&v68);
    v36 = winrt::hstring::c_str((winrt::hstring *)&v67);
    winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::AppExtension::AddDependencyToProcessPackageGraphWithAliases(
      v41,
      (__int64)v36,
      v37,
      v79,
      0,
      0);
  }
  if ( v11 != (_QWORD *)pExceptionObject )
  {
    byte_1805EA2BB = 1;
    byte_1805EA2B8 = v42 & 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl'::`2'::impl) )
      byte_1805EA2B9 = (v42 & 0x40) != 0;
  }
LABEL_102:
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v67);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v68);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v49);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v79);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v80);
  std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(&pExceptionObject);
  if ( v46[1] )
    std::_Ref_count_base::_Decref(v46[1]);
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v45);
}

```

## disassembly

```asm
0x1800a79c4  push    rbp
0x1800a79c6  push    rbx
0x1800a79c7  push    rsi
0x1800a79c8  push    rdi
0x1800a79c9  push    r12
0x1800a79cb  push    r13
0x1800a79cd  push    r14
0x1800a79cf  push    r15
0x1800a79d1  lea     rbp, [rsp-258h]
0x1800a79d9  sub     rsp, 358h
0x1800a79e0  mov     rax, cs:__security_cookie
0x1800a79e7  xor     rax, rsp
0x1800a79ea  mov     [rbp+290h+var_50], rax
0x1800a79f1  mov     esi, ecx
0x1800a79f3  mov     dword ptr [rsp+390h+var_358], ecx
0x1800a79f7  xor     edi, edi
0x1800a79f9  mov     r13d, edi
0x1800a79fc  mov     dword ptr [rbp+290h+var_190], edi
0x1800a7a02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40979072@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072> `wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl(void)'::`2'::impl
0x1800a7a09  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(void)
0x1800a7a0e  test    al, al
0x1800a7a10  jz      short loc_1800A7A1C
0x1800a7a12  test    sil, 20h
0x1800a7a16  jnz     loc_1800A838F
0x1800a7a1c  mov     [rsp+390h+var_340], rdi
0x1800a7a21  lea     rdx, qword_1805EA2C0
0x1800a7a28  lea     rcx, [rsp+390h+var_340]
0x1800a7a2d  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800a7a32  nop
0x1800a7a33  cmp     cs:byte_1805EA2BA, dil
0x1800a7a3a  jnz     short loc_1800A7A4A
0x1800a7a3c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800a7a43  mov     cs:byte_1805EA2BA, 1
0x1800a7a4a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages> `wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl(void)'::`2'::impl
0x1800a7a51  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(void)
0x1800a7a56  mov     r15d, 40h ; '@'
0x1800a7a5c  test    al, al
0x1800a7a5e  jz      short loc_1800A7A8D
0x1800a7a60  cmp     cs:byte_1805EA2BB, dil
0x1800a7a67  jz      short loc_1800A7AAD
0x1800a7a69  cmp     cs:byte_1805EA2B8, dil
0x1800a7a70  jnz     short loc_1800A7A7B
0x1800a7a72  mov     al, sil
0x1800a7a75  not     al
0x1800a7a77  test    al, 1
0x1800a7a79  jz      short loc_1800A7AAD
0x1800a7a7b  cmp     cs:byte_1805EA2B9, dil
0x1800a7a82  jnz     loc_1800A8362
0x1800a7a88  test    r15b, sil
0x1800a7a8b  jmp     short loc_1800A7AA7
0x1800a7a8d  cmp     cs:byte_1805EA2B8, dil
0x1800a7a94  jnz     loc_1800A8362
0x1800a7a9a  cmp     cs:byte_1805EA2BB, dil
0x1800a7aa1  jz      short loc_1800A7AAD
0x1800a7aa3  test    sil, 1
0x1800a7aa7  jz      loc_1800A8362
0x1800a7aad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56189266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56189266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56189266> `wil::Feature<__WilFeatureTraits_Feature_56189266>::GetImpl(void)'::`2'::impl
0x1800a7ab4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56189266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56189266>::__private_IsEnabled(void)
0x1800a7ab9  test    al, al
0x1800a7abb  jz      short loc_1800A7ACD
0x1800a7abd  or      esi, 8
0x1800a7ac0  mov     dword ptr [rsp+390h+var_358], esi
0x1800a7ac4  mov     ecx, esi
0x1800a7ac6  call    ?CacheOptionsFromAppExtensionOptions@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@YA?AW4CacheOptions@12345@W4AppExtensionOptions@2345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheOptionsFromAppExtensionOptions(winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions)
0x1800a7acb  jmp     short loc_1800A7AD9
0x1800a7acd  movzx   eax, sil
0x1800a7ad1  and     eax, 1
0x1800a7ad4  or      eax, 2
0x1800a7ad7  add     eax, eax
0x1800a7ad9  xorps   xmm0, xmm0
0x1800a7adc  movups  xmmword ptr [rsp+390h+var_338], xmm0
0x1800a7ae1  mov     edx, eax
0x1800a7ae3  lea     rcx, [rsp+390h+var_338]
0x1800a7ae8  call    ?GetExtensionCache@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA?AV?$shared_ptr@VExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@W4CacheOptions@23456@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetExtensionCache(winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheOptions)
0x1800a7aed  nop
0x1800a7aee  xorps   xmm1, xmm1
0x1800a7af1  movdqu  [rbp+290h+pExceptionObject], xmm1
0x1800a7af9  mov     [rbp+290h+var_158], rdi
0x1800a7b00  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages> `wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl(void)'::`2'::impl
0x1800a7b07  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(void)
0x1800a7b0c  test    al, al
0x1800a7b0e  lea     rax, off_1804C75C8
0x1800a7b15  jz      loc_1800A7BA1
0x1800a7b1b  mov     ebx, esi
0x1800a7b1d  and     ebx, r15d
0x1800a7b20  or      ebx, 6
0x1800a7b23  shr     ebx, 1
0x1800a7b25  mov     [rbp+290h+var_2B0], rax
0x1800a7b29  lea     rax, [rbp+290h+var_2B0]
0x1800a7b2d  mov     [rbp+290h+var_278], rax
0x1800a7b31  lea     rdx, aComMicrosoftWi_5; "com.microsoft.windows.extensionpackage"
0x1800a7b38  lea     rcx, [rbp+290h+var_180]; this
0x1800a7b3f  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800a7b44  nop
0x1800a7b45  lea     rax, [rbp+290h+var_2B0]
0x1800a7b49  mov     qword ptr [rsp+390h+bIgnoreCase], rax
0x1800a7b4e  mov     r9d, ebx
0x1800a7b51  lea     r8, [rbp+290h+var_180]
0x1800a7b58  lea     rdx, [rsp+390h+var_328]
0x1800a7b5d  mov     rcx, [rsp+390h+var_338]
0x1800a7b62  call    ?GetFilteredExtensionList@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEBUhstring@6@W4CacheEnumerationOptions@23456@$$QEAV?$function@$$A6A_NAEBV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@Z@8@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetFilteredExtensionList(winrt::hstring const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheEnumerationOptions,std::function<bool (std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &)> &&)
0x1800a7b67  mov     rdx, rax
0x1800a7b6a  lea     rcx, [rbp+290h+pExceptionObject]
0x1800a7b71  call    ??4?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::operator=(std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>> &&)
0x1800a7b76  lea     rcx, [rsp+390h+var_328]
0x1800a7b7b  call    ?_Tidy@?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(void)
0x1800a7b80  nop
0x1800a7b81  lea     rcx, [rbp+290h+var_180]
0x1800a7b88  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a7b8d  nop
0x1800a7b8e  mov     rcx, [rbp+290h+var_278]
0x1800a7b92  test    rcx, rcx
0x1800a7b95  jz      loc_1800A7C2C
0x1800a7b9b  lea     rdx, [rbp+290h+var_2B0]
0x1800a7b9f  jmp     short loc_1800A7C1A
0x1800a7ba1  mov     [rbp+290h+var_270], rax
0x1800a7ba5  lea     rax, [rbp+290h+var_270]
0x1800a7ba9  mov     [rbp+290h+var_238], rax
0x1800a7bad  lea     rdx, aComMicrosoftWi_5; "com.microsoft.windows.extensionpackage"
0x1800a7bb4  lea     rcx, [rbp+290h+var_180]; this
0x1800a7bbb  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800a7bc0  nop
0x1800a7bc1  lea     rax, [rbp+290h+var_270]
0x1800a7bc5  mov     qword ptr [rsp+390h+bIgnoreCase], rax
0x1800a7bca  mov     r9d, 3
0x1800a7bd0  lea     r8, [rbp+290h+var_180]
0x1800a7bd7  lea     rdx, [rsp+390h+var_328]
0x1800a7bdc  mov     rcx, [rsp+390h+var_338]
0x1800a7be1  call    ?GetFilteredExtensionList@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEBUhstring@6@W4CacheEnumerationOptions@23456@$$QEAV?$function@$$A6A_NAEBV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@Z@8@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::GetFilteredExtensionList(winrt::hstring const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::CacheEnumerationOptions,std::function<bool (std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> const &)> &&)
0x1800a7be6  mov     rdx, rax
0x1800a7be9  lea     rcx, [rbp+290h+pExceptionObject]
0x1800a7bf0  call    ??4?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::operator=(std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>> &&)
0x1800a7bf5  lea     rcx, [rsp+390h+var_328]
0x1800a7bfa  call    ?_Tidy@?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::_Tidy(void)
0x1800a7bff  nop
0x1800a7c00  lea     rcx, [rbp+290h+var_180]
0x1800a7c07  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a7c0c  nop
0x1800a7c0d  mov     rcx, [rbp+290h+var_238]
0x1800a7c11  test    rcx, rcx
0x1800a7c14  jz      short loc_1800A7C2C
0x1800a7c16  lea     rdx, [rbp+290h+var_270]
0x1800a7c1a  cmp     rcx, rdx
0x1800a7c1d  mov     rax, [rcx]
0x1800a7c20  setnz   dl
0x1800a7c23  mov     rax, [rax+20h]
0x1800a7c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7c2c  mov     r14, qword ptr [rbp+290h+pExceptionObject+8]
0x1800a7c33  mov     r8, r14
0x1800a7c36  sub     r8, qword ptr [rbp+290h+pExceptionObject]
0x1800a7c3d  sar     r8, 4
0x1800a7c41  mov     r9b, [rsp+390h+var_360]
0x1800a7c46  mov     rdx, r14
0x1800a7c49  mov     rcx, qword ptr [rbp+290h+pExceptionObject]
0x1800a7c50  call    std___Sort_unchecked_std__shared_ptr_winrt__WindowsUdk__ApplicationModel__AppExtensions__implementation__ExtensionInfo_____lambda_6efb020e1f710d93d10b2ba822f4bb78___
0x1800a7c55  mov     r8, r15; Size
0x1800a7c58  xor     edx, edx; Val
0x1800a7c5a  lea     rcx, [rbp+290h+var_90]; void *
0x1800a7c61  call    memset_0
0x1800a7c66  lea     rcx, [rbp+290h+var_90]
0x1800a7c6d  call    ??0?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x1800a7c72  nop
0x1800a7c73  mov     r8, r15; Size
0x1800a7c76  xor     edx, edx; Val
0x1800a7c78  lea     rcx, [rbp+290h+var_D0]; void *
0x1800a7c7f  call    memset_0
0x1800a7c84  lea     rcx, [rbp+290h+var_D0]
0x1800a7c8b  call    ??0?$unordered_set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x1800a7c90  nop
0x1800a7c91  mov     [rbp+290h+var_308], rdi
0x1800a7c95  mov     [rbp+290h+var_170], rdi
0x1800a7c9c  mov     rbx, rdi
0x1800a7c9f  mov     [rbp+290h+var_178], rbx
0x1800a7ca6  cmp     r14, qword ptr [rbp+290h+pExceptionObject]
0x1800a7cad  jz      loc_1800A8307
0x1800a7cb3  mov     eax, esi
0x1800a7cb5  and     eax, 11h
0x1800a7cb8  mov     [rsp+390h+var_35C], edi
0x1800a7cbc  mov     r15, qword ptr [rbp+290h+pExceptionObject]
0x1800a7cc3  mov     esi, eax
0x1800a7cc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages> `wil::Feature<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::GetImpl(void)'::`2'::impl
0x1800a7ccc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppExtensions_CacheFiltering_AllowDockedSystemAppPackages>::__private_IsEnabled(void)
0x1800a7cd1  test    al, al
0x1800a7cd3  jz      short loc_1800A7D2D
0x1800a7cd5  mov     rax, [r15]
0x1800a7cd8  mov     ecx, [rax+17Ch]
0x1800a7cde  cmp     ecx, 1
0x1800a7ce1  jz      short loc_1800A7CEB
0x1800a7ce3  cmp     ecx, 4
0x1800a7ce6  mov     al, dil
0x1800a7ce9  jnz     short loc_1800A7CED
0x1800a7ceb  mov     al, 1
0x1800a7ced  cmp     cs:byte_1805EA2B8, dil
0x1800a7cf4  jz      short loc_1800A7D02
0x1800a7cf6  mov     r12b, dil
0x1800a7cf9  cmp     ecx, 3
0x1800a7cfc  jz      loc_1800A827B
0x1800a7d02  cmp     cs:byte_1805EA2B9, dil
0x1800a7d09  jz      short loc_1800A7D17
0x1800a7d0b  mov     r12b, dil
0x1800a7d0e  cmp     ecx, 2
0x1800a7d11  jz      loc_1800A827B
0x1800a7d17  cmp     cs:byte_1805EA2BB, dil
0x1800a7d1e  jz      short loc_1800A7D98
0x1800a7d20  mov     r12b, dil
0x1800a7d23  test    al, al
0x1800a7d25  jnz     loc_1800A827B
0x1800a7d2b  jmp     short loc_1800A7D98
0x1800a7d2d  cmp     cs:byte_1805EA2BB, dil
0x1800a7d34  jz      short loc_1800A7D77
0x1800a7d36  lea     rdx, [rbp+290h+var_2E0]
0x1800a7d3a  mov     rcx, [r15]
0x1800a7d3d  call    ?PublisherId@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PublisherId(void)
0x1800a7d42  or      r13d, 1
0x1800a7d46  cmp     qword ptr [rax+18h], 7
0x1800a7d4b  jbe     short loc_1800A7D50
0x1800a7d4d  mov     rax, [rax]
0x1800a7d50  mov     [rsp+390h+bIgnoreCase], 1; bIgnoreCase
0x1800a7d58  or      r9d, 0FFFFFFFFh; cchCount2
0x1800a7d5c  lea     r8, String2; "cw5n1h2txyewy"
0x1800a7d63  or      edx, r9d; cchCount1
0x1800a7d66  mov     rcx, rax; lpString1
0x1800a7d69  call    cs:__imp_CompareStringOrdinal
0x1800a7d6f  cmp     eax, 2
0x1800a7d72  jnz     short loc_1800A7D77
0x1800a7d74  mov     dil, 1
0x1800a7d77  test    r13b, 1
0x1800a7d7b  jz      short loc_1800A7D8A
0x1800a7d7d  and     r13d, 0FFFFFFFEh
0x1800a7d81  lea     rcx, [rbp+290h+var_2E0]; this
0x1800a7d85  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800a7d8a  xor     r12b, r12b
0x1800a7d8d  test    dil, dil
0x1800a7d90  jnz     loc_1800A827B
0x1800a7d96  xor     edi, edi
0x1800a7d98  mov     rcx, [r15]
0x1800a7d9b  mov     r14d, [rcx+178h]
0x1800a7da2  lea     rdx, [rbp+290h+lpString1]
0x1800a7da9  call    ?PackageFamilyName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFamilyName(void)
0x1800a7dae  nop
0x1800a7daf  mov     r12b, dil
0x1800a7db2  test    esi, esi
0x1800a7db4  jnz     short loc_1800A7E11
0x1800a7db6  cmp     r14d, 3
0x1800a7dba  jnz     short loc_1800A7E11
0x1800a7dbc  lea     rcx, [rbp+290h+var_310]
0x1800a7dc0  call    ?GetRetailPackageFamilyName@@YA?AUhstring@winrt@@XZ; GetRetailPackageFamilyName(void)
0x1800a7dc5  mov     rcx, rax; this
0x1800a7dc8  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800a7dcd  lea     rcx, [rbp+290h+lpString1]
0x1800a7dd4  cmp     [rbp+290h+var_118], 7
0x1800a7ddc  cmova   rcx, [rbp+290h+lpString1]; lpString1
0x1800a7de4  mov     [rsp+390h+bIgnoreCase], 1; bIgnoreCase
0x1800a7dec  or      edx, 0FFFFFFFFh; cchCount1
0x1800a7def  mov     r9d, edx; cchCount2
0x1800a7df2  mov     r8, rax; lpString2
0x1800a7df5  call    cs:__imp_CompareStringOrdinal
0x1800a7dfb  mov     edi, eax
0x1800a7dfd  lea     rcx, [rbp+290h+var_310]
0x1800a7e01  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a7e06  cmp     edi, 2
0x1800a7e09  jnz     loc_1800A8268
0x1800a7e0f  xor     edi, edi
0x1800a7e11  mov     rcx, [r15]
0x1800a7e14  cmp     dword ptr [rcx+178h], 3
0x1800a7e1b  jnz     short loc_1800A7E54
0x1800a7e1d  mov     cs:?g_storePackageLoaded@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3_NA, 1; bool winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_storePackageLoaded
0x1800a7e24  cmp     cs:qword_1805EC5F8, rdi
0x1800a7e2b  jnz     short loc_1800A7E54
0x1800a7e2d  lea     rdx, [rbp+290h+var_210]
0x1800a7e34  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800a7e39  mov     rdx, rax
0x1800a7e3c  lea     rcx, ?g_storePackageFullName@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_storePackageFullName
0x1800a7e43  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a7e48  lea     rcx, [rbp+290h+var_210]; this
0x1800a7e4f  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1800a7e54  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53393585@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53393585@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53393585> `wil::Feature<__WilFeatureTraits_Feature_53393585>::GetImpl(void)'::`2'::impl
0x1800a7e5b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53393585@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53393585>::__private_IsEnabled(void)
0x1800a7e60  test    al, al
0x1800a7e62  jnz     short loc_1800A7E8F
0x1800a7e64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61119654@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654> `wil::Feature<__WilFeatureTraits_Feature_61119654>::GetImpl(void)'::`2'::impl
0x1800a7e6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61119654@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61119654>::__private_IsEnabled(void)
0x1800a7e70  mov     rcx, [r15]
0x1800a7e73  mov     edx, [rcx+178h]
0x1800a7e79  test    al, al
0x1800a7e7b  jz      short loc_1800A7E83
0x1800a7e7d  test    edx, edx
0x1800a7e7f  jz      short loc_1800A7E88
0x1800a7e81  jmp     short loc_1800A7E8F
0x1800a7e83  cmp     edx, 1
0x1800a7e86  jnz     short loc_1800A7E8F
0x1800a7e88  mov     cs:?g_unsignedPackageLoaded@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@3_NA, 1; bool winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::g_unsignedPackageLoaded
0x1800a7e8f  lea     rdx, [rbp+290h+var_F0]
0x1800a7e96  mov     rcx, [r15]
0x1800a7e99  call    ?PackageFullName@ExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo::PackageFullName(void)
0x1800a7e9e  nop
0x1800a7e9f  lea     rcx, [rbp+290h+var_170]; this
0x1800a7ea6  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800a7eab  lea     rcx, [rbp+290h+lpString1]
0x1800a7eb2  cmp     [rbp+290h+var_118], 7
  ... truncated ...
```
