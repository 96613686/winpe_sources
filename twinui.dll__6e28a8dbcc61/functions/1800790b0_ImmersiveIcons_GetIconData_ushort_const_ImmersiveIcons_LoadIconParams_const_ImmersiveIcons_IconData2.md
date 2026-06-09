# ImmersiveIcons::GetIconData(ushort const *,ImmersiveIcons::LoadIconParams const &,ImmersiveIcons::IconData2 *)

- ea: `0x1800790b0`
- end: `0x18007a1de`
- name: `?GetIconData@ImmersiveIcons@@YAJPEBGAEBULoadIconParams@1@PEAUIconData2@1@@Z`
- size: `4398`
- prototype: `__int64 __fastcall(PCWSTR pszItem, const unsigned __int16 *, const struct ImmersiveIcons::LoadIconParams *, struct ImmersiveIcons::IconData2 *)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18035fc18`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000e028`
- `0x18001f3c0`
- `0x180027ee4`
- `0x180036250`
- `0x18003c5e4`
- `0x18003c898`
- `0x180058a44`
- `0x1800790b0`
- `0x18007aa28`
- `0x18007aaf4`
- `0x18007abd0`
- `0x18008c4b0`
- `0x1800b5e48`
- `0x1800eb4a4`
- `0x1800eb500`
- `0x1800f37d8`
- `0x1800f4070`
- `0x1800fa498`
- `0x1800ffe5c`
- `0x180100d84`
- `0x1801057fc`
- `0x180105850`
- `0x18011f004`
- `0x18013d330`
- `0x180151ef0`
- `0x18016386c`
- `0x18031ec90`
- `0x18031ece4`
- `0x1803203e0`
- `0x180324838`
- `0x18035eba4`
- `0x18035ed1c`
- `0x18035f6d0`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007928e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007928e`
- `SHELL32!SHCreateItemInKnownFolder` at `0x180079119`
- `SHELL32!SHCreateItemInKnownFolder` at `0x180079119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a02d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a02d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079f5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007927a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007927a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800792be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800792be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079c9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079347`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800794de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079347`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800794de`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180079f40`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180079f40`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18007947e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18007947e`

## pseudocode

```c
__int64 __fastcall ImmersiveIcons::GetIconData(
        WCHAR *pszItem,
        ImmersiveIcons *a2,
        const struct ImmersiveIcons::LoadIconParams *a3,
        struct ImmersiveIcons::IconData2 *a4)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int As; // eax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rbx
  WCHAR *v12; // r14
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  HSTRING v16; // rdx
  HSTRING v17; // rdx
  unsigned __int16 **v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  HRESULT v21; // eax
  int PackageFullNameForAppsFolderItem; // eax
  __int64 v23; // rdx
  LPVOID v24; // rdi
  __int64 (__fastcall *v25)(LPVOID, WCHAR *, _QWORD, _QWORD); // rbx
  HRESULT Instance; // eax
  int v27; // eax
  __int64 v28; // rdx
  HSTRING v29; // rdi
  __int64 (__fastcall *v30)(HSTRING, GUID *, _QWORD); // rbx
  int v31; // eax
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v33)(_QWORD, GUID *, __int64 *); // rdi
  int v34; // eax
  HSTRING v35; // rdx
  HSTRING v36; // rdx
  unsigned __int16 **v37; // r8
  int v38; // eax
  __int64 v39; // rdx
  HSTRING v40; // rdi
  __int64 (__fastcall *v41)(HSTRING, GUID *, struct ImmersiveIcons::LoadIconParams **); // rbx
  int v42; // eax
  __int64 v43; // rdx
  int v44; // r12d
  int v45; // r15d
  struct IResourceContext *v46; // r8
  ImmersiveIcons *v47; // rcx
  void *v48; // r13
  int inited; // eax
  __int64 v50; // rdi
  int (__fastcall *v51)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  int v52; // eax
  __int64 *v53; // rcx
  __int64 v54; // rdi
  int (__fastcall *v55)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v56; // rbx
  __int64 v57; // rax
  int v58; // eax
  __int64 v59; // rdi
  int (__fastcall *v60)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *); // rbx
  int v61; // eax
  __int64 v62; // rdi
  __int64 (__fastcall *v63)(__int64, const wchar_t *, __int64 *); // rbx
  int v64; // r12d
  ImmersiveIcons *v65; // rbx
  int ContrastForParams; // eax
  __int64 v67; // rdx
  __int64 v68; // rdx
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rdi
  __int64 (__fastcall *v72)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, ImmersiveIcons **); // rbx
  ImmersiveIcons *v73; // rbx
  __int64 (__fastcall *v74)(ImmersiveIcons *, GUID *, __int64 *); // rdi
  int v75; // eax
  ImmersiveIcons *v76; // rcx
  struct ImmersiveIcons::LoadIconParams *v77; // rcx
  __int64 v78; // rcx
  __int64 (__fastcall ***v79)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING v80; // rcx
  void *v81; // rcx
  __int64 v82; // rdi
  __int64 (__fastcall *v83)(__int64, const wchar_t *, __int64 *); // rbx
  int v84; // r12d
  __int64 v85; // rdi
  int (__fastcall *v86)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v87; // rdi
  int (__fastcall *v88)(__int64, const wchar_t *, HSTRING_HEADER *); // rbx
  char v89; // r14
  __int64 v90; // rdi
  __int64 (__fastcall *v91)(__int64, LPVOID *); // rbx
  int v92; // eax
  __int64 v93; // rdx
  HSTRING v94; // rbx
  __int64 v95; // rax
  int v96; // eax
  __int64 v97; // rdx
  const WCHAR *StringRawBuffer; // rax
  __int64 v99; // r9
  const unsigned __int16 *v100; // rax
  HSTRING v102; // rcx
  __int64 v103; // rdx
  HSTRING_HEADER *v104; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  void **ppva; // [rsp+20h] [rbp-E0h]
  void **ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  __int64 v109; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v110; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v111; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v112; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v113)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  struct ImmersiveIcons::LoadIconParams *v114; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v116; // [rsp+68h] [rbp-98h]
  __int64 v117; // [rsp+70h] [rbp-90h]
  HSTRING__ v118[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v119; // [rsp+80h] [rbp-80h]
  __int64 v120; // [rsp+88h] [rbp-78h]
  HSTRING v121; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR sourceString; // [rsp+98h] [rbp-68h] BYREF
  UINT32 length[2]; // [rsp+A0h] [rbp-60h]
  __int64 v124; // [rsp+A8h] [rbp-58h]
  PCWSTR v125[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v126; // [rsp+C0h] [rbp-40h]
  ImmersiveIcons *v127; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v128; // [rsp+D8h] [rbp-28h] BYREF
  void *v129; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v130; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v131; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v132; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v133; // [rsp+100h] [rbp+0h] BYREF
  __int64 v134; // [rsp+108h] [rbp+8h]
  __int64 v135; // [rsp+110h] [rbp+10h]
  __int64 v136; // [rsp+118h] [rbp+18h] BYREF
  __int64 v137; // [rsp+120h] [rbp+20h]
  __int64 v138; // [rsp+128h] [rbp+28h]
  __int64 v139; // [rsp+130h] [rbp+30h] BYREF
  __int64 v140; // [rsp+138h] [rbp+38h]
  __int64 v141; // [rsp+140h] [rbp+40h]
  _QWORD v142[5]; // [rsp+148h] [rbp+48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+170h] [rbp+70h] BYREF
  HSTRING string; // [rsp+188h] [rbp+88h] BYREF
  HSTRING_HEADER v145; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v127 = a2;
  v129 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v129);
  v6 = SHCreateItemInKnownFolder(
         &FOLDERID_AppsFolder,
         0x4000u,
         pszItem,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v129);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_158:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v129);
    return v7;
  }
  v109 = 0;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v109);
  As = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(
         (unsigned int)&v109,
         (_DWORD)v129,
         1,
         (unsigned int)qword_1803F8EF0,
         4);
  v7 = As;
  if ( As < 0 )
  {
    v9 = 237;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)As,
      (int)ppva);
LABEL_157:
    Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v109);
    goto LABEL_158;
  }
  LODWORD(v126) = 4;
  *(_OWORD *)v125 = PKEY_Tile_Background;
  As = wil::PropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(&v109, v125, (char *)a3 + 12);
  v7 = As;
  if ( As < 0 )
  {
    v9 = 239;
    goto LABEL_5;
  }
  sourceString = 0;
  *(_OWORD *)v125 = PKEY_Tile_SmallLogoPath;
  *(_QWORD *)length = -1;
  v124 = -1;
  LODWORD(v126) = 2;
  v10 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v109, v125, &sourceString);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
      (const char *)(unsigned int)v10,
      (int)ppva);
LABEL_156:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    goto LABEL_157;
  }
  LODWORD(v11) = length[0];
  v12 = (WCHAR *)sourceString;
  if ( *(_QWORD *)length == -1 )
  {
    if ( sourceString )
    {
      v11 = -1;
      do
        ++v11;
      while ( sourceString[v11] );
    }
    else
    {
      v11 = 0;
    }
    *(_QWORD *)length = v11;
  }
  string = 0;
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v14 = v13 - 1;
  if ( (unsigned int)v11 < v13 )
    v14 = v11;
  v15 = WindowsCreateStringReference(v12, v14, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    RaiseException(v15, 1u, 0, 0);
    __debugbreak();
  }
  pv = 0;
  v116 = 0;
  v117 = 0;
  if ( ShellMRTHelper::Common::HasFileUriScheme((ShellMRTHelper::Common *)string, v16) )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v116 = -1;
    v117 = -1;
    v19 = TileUtils::ConvertFileUriToFilePath(v12, (const unsigned __int16 *)&pv, v18);
    v7 = v19;
    if ( v19 < 0 )
    {
      v20 = 260;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v19,
        (int)ppva);
LABEL_155:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      string = 0;
      goto LABEL_156;
    }
  }
  else
  {
    if ( ShellMRTHelper::Common::HasMsAppDataUriScheme((ShellMRTHelper::Common *)string, v17) )
    {
      v128 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
      v21 = CoCreateInstance(
              &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
              0,
              1u,
              &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
              &v128);
      v7 = v21;
      if ( v21 >= 0 )
      {
        *(_QWORD *)&v118[0].unused = 0;
        v119 = 0;
        v120 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
        v119 = -1;
        v120 = -1;
        PackageFullNameForAppsFolderItem = ImmersiveIcons::GetPackageFullNameForAppsFolderItem((CallerIdentity *)pszItem);
        v7 = PackageFullNameForAppsFolderItem;
        if ( PackageFullNameForAppsFolderItem >= 0 )
        {
          v24 = v128;
          v25 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, _QWORD, _QWORD))(*(_QWORD *)v128 + 48LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          ppva = &pv;
          v116 = -1;
          v117 = -1;
          PackageFullNameForAppsFolderItem = v25(v24, v12, *(_QWORD *)&v118[0].unused, 0);
          v7 = PackageFullNameForAppsFolderItem;
          if ( PackageFullNameForAppsFolderItem >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
            goto LABEL_37;
          }
          v23 = 270;
        }
        else
        {
          v23 = 268;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)PackageFullNameForAppsFolderItem,
          (int)ppva);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v21,
          (int)ppva);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v128);
      goto LABEL_155;
    }
    if ( !PathIsRelativeW(v12) )
    {
      v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              &pv,
              &sourceString);
      v7 = v19;
      if ( v19 < 0 )
      {
        v20 = 276;
        goto LABEL_26;
      }
    }
  }
LABEL_37:
  if ( !pv || !*(_WORD *)pv )
  {
    v110 = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v110);
    Instance = CoCreateInstance(
                 &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
                 0,
                 1u,
                 &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                 (LPVOID *)&v110);
    v7 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)Instance,
        (int)ppvb);
LABEL_154:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v110);
      goto LABEL_155;
    }
    v125[0] = 0;
    v125[1] = (PCWSTR)-1LL;
    v126 = -1;
    v27 = ImmersiveIcons::GetPackageFullNameForAppsFolderItem((CallerIdentity *)pszItem);
    v7 = v27;
    if ( v27 < 0 )
    {
      v28 = 288;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v27,
        (int)ppvb);
LABEL_153:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v125);
      goto LABEL_154;
    }
    v27 = (*(__int64 (__fastcall **)(HSTRING, PCWSTR))(*(_QWORD *)v110 + 40LL))(v110, v125[0]);
    v7 = v27;
    if ( v27 < 0 )
    {
      v28 = 290;
      goto LABEL_49;
    }
    v29 = v110;
    v113 = 0;
    v30 = *(__int64 (__fastcall **)(HSTRING, GUID *, _QWORD))(*(_QWORD *)v110 + 56LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
    v31 = v30(v29, &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, &v113);
    v7 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v31,
        (int)ppvb);
LABEL_152:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
      goto LABEL_153;
    }
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
    v112 = 0;
    v33 = **v113;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v112);
    v34 = v33(v32, &GUID_2fe6ec6e_da7e_4b2a_a8f9_90b289061f20, &v112);
    v7 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v34,
        (int)ppvb);
LABEL_151:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v112);
      goto LABEL_152;
    }
    *(_QWORD *)&v118[0].unused = 0;
    v119 = 0;
    v120 = 0;
    if ( ShellMRTHelper::Common::HasMsAppXUriScheme((ShellMRTHelper::Common *)string, v35) )
    {
      v119 = -1;
      v120 = -1;
      v38 = ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri((ShellMRTHelper::Common *)string, v118, v37);
      v7 = v38;
      if ( v38 < 0 )
      {
        v39 = 303;
LABEL_59:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v38,
          (int)ppvb);
LABEL_150:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
        goto LABEL_151;
      }
    }
    else if ( ShellMRTHelper::Common::HasMsResourceUriScheme((ShellMRTHelper::Common *)string, v36) )
    {
      v38 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
              v118,
              &sourceString);
      v7 = v38;
      if ( v38 < 0 )
      {
        v39 = 310;
        goto LABEL_59;
      }
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
      v38 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v118,
              L"Files\\",
              *(_QWORD *)length + 7LL);
      v7 = v38;
      if ( v38 < 0 )
      {
        v39 = 317;
        goto LABEL_59;
      }
      v38 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
              v118,
              &sourceString);
      v7 = v38;
      if ( v38 < 0 )
      {
        v39 = 318;
        goto LABEL_59;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(v118);
      v12 = (WCHAR *)sourceString;
    }
    v40 = v110;
    v114 = 0;
    v41 = *(__int64 (__fastcall **)(HSTRING, GUID *, struct ImmersiveIcons::LoadIconParams **))(*(_QWORD *)v110 + 72LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
    v42 = v41(v40, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, &v114);
    v7 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v42,
        (int)ppvb);
LABEL_149:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
      goto LABEL_150;
    }
    v111 = 0;
    v44 = 0;
    v45 = 0;
    LOBYTE(v43) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
      v43);
    v47 = v127;
    v48 = *(void **)&v118[0].unused;
    if ( *((_DWORD *)v127 + 11) == 1 && *((_DWORD *)v127 + 10) != 1 && *((_DWORD *)v127 + 9) != 2 )
    {
      inited = ImmersiveIcons::InitResourceContextForLightTheme(v127, v114, v46);
      v7 = inited;
      if ( inited < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)inited,
          (int)ppvb);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v125);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v110);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        string = 0;
        goto LABEL_156;
      }
      v50 = v112;
      v132 = 0;
      v51 = *(int (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v112 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v132);
      if ( v51(v50, v114, v48, &v132) >= 0 )
      {
        v131 = 0;
        v52 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v132, &v131);
        v7 = v52;
        if ( v52 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15F,
            (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
            (const char *)(unsigned int)v52,
            (int)ppvb);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v131);
          v53 = &v132;
LABEL_78:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v53);
LABEL_79:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v112);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v125);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v110);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          string = 0;
          goto LABEL_156;
        }
        v136 = 0;
        v137 = 0;
        v138 = 0;
        v54 = v131;
        v55 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v131 + 64LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v136);
        v137 = -1;
        v138 = -1;
        if ( v55(v54, L"AlternateForm", &v136) >= 0
          && (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                             &v136,
                             L"lightunplated",
                             -1) == 2 )
        {
          v56 = v131;
          v45 = 1;
          v44 = 2;
          v57 = v111;
          if ( v111 != v131 )
          {
            if ( v131 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 8LL))(v131);
              v57 = v111;
            }
            v130 = v57;
            v111 = v56;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v130);
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v136);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v131);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v132);
      v47 = v127;
    }
    if ( v111 )
      goto LABEL_96;
    v58 = ImmersiveIcons::InitResourceContextForAllThemes(v47, v114, v46);
    v7 = v58;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v58,
        (int)ppvb);
      goto LABEL_79;
    }
    v130 = 0;
    v59 = v112;
    v60 = *(int (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, __int64 *))(*(_QWORD *)v112 + 48LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v130);
    if ( v60(v59, v114, v48, &v130) >= 0 )
    {
      v61 = Microsoft::WRL::ComPtr<IResourceCandidate2>::As<IResourceCandidate>(&v130, &v111);
      v7 = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v61,
          (int)ppvb);
        v53 = &v130;
        goto LABEL_78;
      }
      v139 = 0;
      v140 = 0;
      v141 = 0;
      v62 = v111;
      v63 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v111 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v139);
      v140 = -1;
      v141 = -1;
      v64 = v63(v62, L"AlternateForm", &v139);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v139);
      v44 = (v64 >> 31) + 2;
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v130);
    if ( v111 )
    {
LABEL_96:
      v65 = v127;
      ContrastForParams = ImmersiveIcons::GetContrastForParams(v127);
      LODWORD(v121) = ContrastForParams;
      if ( v44 != 1 || ContrastForParams )
        goto LABEL_126;
      v68 = *((unsigned __int16 *)v65 + 8);
      v127 = 0;
      v69 = (*(__int64 (__fastcall **)(struct ImmersiveIcons::LoadIconParams *, __int64))(*(_QWORD *)v114 + 112LL))(
              v114,
              v68);
      if ( v69 >= 0 )
      {
        v71 = v112;
        v72 = *(__int64 (__fastcall **)(__int64, struct ImmersiveIcons::LoadIconParams *, void *, ImmersiveIcons **))(*(_QWORD *)v112 + 48LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v127);
        v69 = v72(v71, v114, v48, &v127);
        if ( v69 >= 0 )
        {
          v73 = v127;
          v74 = **(__int64 (__fastcall ***)(ImmersiveIcons *, GUID *, __int64 *))v127;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
          v75 = v74(v73, &GUID_f98ce1cb_901b_41f4_bf42_83d51895e1e2, &v111);
          v7 = v75;
          if ( v75 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x187,
              (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
              (const char *)(unsigned int)v75,
              (int)ppvb);
            v76 = v127;
            if ( v127 )
            {
              v127 = 0;
              (*(void (__fastcall **)(ImmersiveIcons *))(*(_QWORD *)v76 + 16LL))(v76);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
            v77 = v114;
            if ( v114 )
            {
              v114 = 0;
              (*(void (__fastcall **)(struct ImmersiveIcons::LoadIconParams *))(*(_QWORD *)v77 + 16LL))(v77);
            }
            if ( v48 )
              CoTaskMemFree(v48);
            v78 = v112;
            if ( v112 )
            {
              v112 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
            }
            v79 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v113;
            if ( v113 )
            {
              v113 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v79)[2])(v79);
            }
            if ( v125[0] )
              CoTaskMemFree((LPVOID)v125[0]);
            v80 = v110;
            if ( v110 )
            {
              v110 = 0;
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v80 + 16LL))(v80);
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            v116 = 0;
            v117 = 0;
            string = 0;
            if ( v12 )
              CoTaskMemFree(v12);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v109);
            v81 = v129;
            if ( v129 )
            {
              v129 = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v81 + 16LL))(v81);
            }
            return v7;
          }
          v133 = 0;
          v134 = 0;
          v135 = 0;
          v82 = v111;
          v83 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v111 + 64LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v133);
          v134 = -1;
          v135 = -1;
          v84 = v83(v82, L"AlternateForm", &v133);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v133);
          v44 = (v84 >> 31) + 2;
          goto LABEL_125;
        }
        v70 = 389;
      }
      else
      {
        v70 = 388;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v70,
        (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
        (const char *)(unsigned int)v69,
        (int)ppvb);
LABEL_125:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v127);
LABEL_126:
      LOBYTE(v67) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl,
        v67);
      v85 = v111;
      v133 = 0;
      v134 = 0;
      v135 = 0;
      v86 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v111 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v133);
      v134 = -1;
      v135 = -1;
      if ( v86(v85, L"Theme", &v133) >= 0 )
      {
        if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                             &v133,
                             L"dark",
                             -1) == 2 )
        {
          v45 = 2;
        }
        else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                                  &v133,
                                  L"light",
                                  -1) == 2 )
        {
          v45 = 1;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v133);
      memset(&v145, 0, sizeof(v145));
      if ( !(_DWORD)v121
        || (v87 = v111,
            v88 = *(int (__fastcall **)(__int64, const wchar_t *, HSTRING_HEADER *))(*(_QWORD *)v111 + 64LL),
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v145),
            *(_QWORD *)&v145.Reserved.Reserved2[8] = -1,
            *(_QWORD *)&v145.Reserved.Reserved2[16] = -1,
            v89 = 1,
            v88(v87, L"Contrast", &v145) < 0) )
      {
        v89 = 0;
      }
      v90 = v111;
      v91 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v111 + 32LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      v116 = -1;
      v117 = -1;
      v92 = v91(v90, &pv);
      v7 = v92;
      if ( v92 < 0 )
      {
        v93 = 417;
LABEL_136:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v93,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)(unsigned int)v92,
          (int)ppvb);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v145);
LABEL_148:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
        goto LABEL_149;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(&pv);
      v92 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, (const unsigned __int16 *)pv);
      v7 = v92;
      if ( v92 < 0 )
      {
        v93 = 421;
        goto LABEL_136;
      }
      *(_DWORD *)a3 = v44;
      *((_DWORD *)a3 + 1) = v45;
      *((_BYTE *)a3 + 8) = v89;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v145);
LABEL_161:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v111);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v114);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v112);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v113);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v125);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v110);
      goto LABEL_162;
    }
    v121 = 0;
    WindowsDeleteString(0);
    v94 = string;
    v121 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(v125);
    v95 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v145, v125[0], (unsigned int)v125[1]);
    v96 = ShellMRTHelper::Common::TryFallbackToFilePath(0, *(HSTRING *)(v95 + 24), v94, (HSTRING)&v121, (HSTRING *)ppvb);
    v7 = v96;
    if ( v96 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v121, 0);
      if ( !PathFileExistsW(StringRawBuffer) )
      {
        v7 = -2147024893;
        v97 = 436;
        v99 = 2147942403LL;
LABEL_147:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v97,
          (unsigned int)"shell\\lib\\immersiveapphelpers\\immersiveappiconhelpers.cpp",
          (const char *)v99,
          ppvc);
        WindowsDeleteString(v121);
        v121 = 0;
        goto LABEL_148;
      }
      v100 = WindowsGetStringRawBuffer(v121, 0);
      v96 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, v100);
      v7 = v96;
      if ( v96 >= 0 )
      {
        v102 = v121;
        *(_QWORD *)a3 = 0;
        *((_BYTE *)a3 + 8) = 0;
        WindowsDeleteString(v102);
        goto LABEL_161;
      }
      v97 = 437;
    }
    else
    {
      v97 = 435;
    }
    v99 = (unsigned int)v96;
    goto LABEL_147;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ReplaceChars(&pv);
  v19 = StringCchCopyW((unsigned __int16 *)a3 + 8, 0x104u, (const unsigned __int16 *)pv);
  v7 = v19;
  if ( v19 < 0 )
  {
    v20 = 452;
    goto LABEL_26;
  }
  *(_QWORD *)a3 = 0;
  *((_BYTE *)a3 + 8) = 0;
LABEL_162:
  if ( !*(_DWORD *)a3 )
  {
    *(_QWORD *)&v118[0].unused = 0;
    v119 = 0;
    v120 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
    v119 = -1;
    *(_OWORD *)v125 = PKEY_AppUserModel_ParentID;
    v120 = -1;
    LODWORD(v126) = 19;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v109, v125, v118) >= 0 )
    {
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           v118,
                           L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge",
                           -1) == 2 )
      {
LABEL_169:
        *(_DWORD *)a3 = 3;
      }
      else
      {
        LOBYTE(v103) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_UnplateMicrosoftEdgeTiles_25482738>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_Servicing_UnplateMicrosoftEdgeTiles_25482738>::GetImpl'::`2'::impl,
          v103);
        v142[0] = L"Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!App";
        v104 = (HSTRING_HEADER *)v142;
        v142[1] = L"Microsoft.MicrosoftEdge.Beta_8wekyb3d8bbwe!App";
        v142[2] = L"Microsoft.MicrosoftEdge.Dev_8wekyb3d8bbwe!App";
        v142[3] = L"Microsoft.MicrosoftEdge.Canary_8wekyb3d8bbwe!App";
        v142[4] = L"Microsoft.MicrosoftEdge.Internal_8wekyb3d8bbwe!App";
        while ( v104 != &hstringHeader )
        {
          if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                               v118,
                               v104->Reserved.Reserved1,
                               -1) == 2 )
            goto LABEL_169;
          v104 = (HSTRING_HEADER *)((char *)v104 + 8);
        }
      }
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           v118,
                           L"Microsoft.YourPhone_8wekyb3d8bbwe!App",
                           -1) == 2 )
        *(_DWORD *)a3 = 3;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v118);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  string = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>::~ComPtr<Windows::Foundation::IUriRuntimeClass>(&v109);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v129);
  return 0;
}

```

## disassembly

```asm
0x1800790b0  mov     [rsp-8+arg_18], rbx
0x1800790b5  push    rbp
0x1800790b6  push    rsi
0x1800790b7  push    rdi
0x1800790b8  push    r12
0x1800790ba  push    r13
0x1800790bc  push    r14
0x1800790be  push    r15
0x1800790c0  lea     rbp, [rsp-0C0h]
0x1800790c8  sub     rsp, 1C0h
0x1800790cf  mov     rax, cs:__security_cookie
0x1800790d6  xor     rax, rsp
0x1800790d9  mov     [rbp+0F0h+var_40], rax
0x1800790e0  mov     r15, rcx
0x1800790e3  mov     [rbp+0F0h+var_120], rdx
0x1800790e7  xor     r13d, r13d
0x1800790ea  lea     rcx, [rbp+0F0h+var_110]
0x1800790ee  mov     [rbp+0F0h+var_110], r13
0x1800790f2  mov     rsi, r8
0x1800790f5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800790fa  lea     rax, [rbp+0F0h+var_110]
0x1800790fe  mov     r8, r15; pszItem
0x180079101  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180079108  mov     [rsp+1F0h+ppv], rax; int
0x18007910d  mov     edx, 4000h; dwKFFlags
0x180079112  lea     rcx, FOLDERID_AppsFolder; kfid
0x180079119  call    cs:__imp_SHCreateItemInKnownFolder
0x18007911f  mov     ebx, eax
0x180079121  test    eax, eax
0x180079123  jns     short loc_180079145
0x180079125  mov     rcx, [rbp+0F8h]; this
0x18007912c  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180079133  mov     r9d, eax; char *
0x180079136  mov     edx, 0DEh; void *
0x18007913b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079140  jmp     loc_18007A012
0x180079145  lea     rcx, [rsp+1F0h+var_1C0]
0x18007914a  mov     [rsp+1F0h+var_1C0], r13
0x18007914f  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x180079154  mov     rdx, [rbp+0F0h+var_110]
0x180079158  lea     r9, qword_1803F8EF0
0x18007915f  mov     edi, 1
0x180079164  mov     dword ptr [rsp+1F0h+ppv], 4; int
0x18007916c  mov     r8d, edi
0x18007916f  lea     rcx, [rsp+1F0h+var_1C0]
0x180079174  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180079179  mov     ebx, eax
0x18007917b  test    eax, eax
0x18007917d  jns     short loc_18007919F
0x18007917f  mov     edx, 0EDh; void *
0x180079184  mov     rcx, [rbp+0F8h]; this
0x18007918b  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180079192  mov     r9d, eax; char *
0x180079195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007919a  jmp     loc_18007A008
0x18007919f  movups  xmm0, cs:PKEY_Tile_Background
0x1800791a6  mov     eax, cs:dword_1803F8E88
0x1800791ac  lea     r8, [rsi+0Ch]
0x1800791b0  lea     rdx, [rbp+0F0h+var_140]
0x1800791b4  mov     dword ptr [rbp+0F0h+var_130], eax
0x1800791b7  lea     rcx, [rsp+1F0h+var_1C0]
0x1800791bc  movaps  xmmword ptr [rbp+0F0h+var_140], xmm0
0x1800791c0  call    ??$GetAsUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x1800791c5  mov     ebx, eax
0x1800791c7  test    eax, eax
0x1800791c9  jns     short loc_1800791D2
0x1800791cb  mov     edx, 0EFh
0x1800791d0  jmp     short loc_180079184
0x1800791d2  movups  xmm0, cs:PKEY_Tile_SmallLogoPath
0x1800791d9  mov     eax, cs:dword_1803F8EA0
0x1800791df  lea     r8, [rbp+0F0h+sourceString]
0x1800791e3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800791e7  mov     [rbp+0F0h+sourceString], r13
0x1800791eb  lea     rdx, [rbp+0F0h+var_140]
0x1800791ef  movaps  xmmword ptr [rbp+0F0h+var_140], xmm0
0x1800791f3  lea     rcx, [rsp+1F0h+var_1C0]
0x1800791f8  mov     qword ptr [rbp+0F0h+length], r12
0x1800791fc  mov     [rbp+0F0h+var_148], r12
0x180079200  mov     dword ptr [rbp+0F0h+var_130], eax
0x180079203  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180079208  mov     ebx, eax
0x18007920a  test    eax, eax
0x18007920c  jns     short loc_18007922E
0x18007920e  mov     rcx, [rbp+0F8h]; this
0x180079215  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x18007921c  mov     r9d, eax; char *
0x18007921f  mov     edx, 0F2h; void *
0x180079224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079229  jmp     loc_180079FFF
0x18007922e  mov     rbx, qword ptr [rbp+0F0h+length]
0x180079232  mov     r14, [rbp+0F0h+sourceString]
0x180079236  cmp     rbx, r12
0x180079239  jnz     short loc_180079256
0x18007923b  test    r14, r14
0x18007923e  jz      short loc_18007924F
0x180079240  mov     rbx, r12
0x180079243  inc     rbx
0x180079246  cmp     [r14+rbx*2], r13w
0x18007924b  jnz     short loc_180079243
0x18007924d  jmp     short loc_180079252
0x18007924f  mov     rbx, r13
0x180079252  mov     qword ptr [rbp+0F0h+length], rbx
0x180079256  mov     ecx, ebx; unsigned int
0x180079258  mov     [rbp+0F0h+string], r13
0x18007925f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180079264  cmp     ebx, eax
0x180079266  lea     r9, [rbp+0F0h+string]; string
0x18007926d  lea     r8, [rbp+0F0h+hstringHeader]; hstringHeader
0x180079271  mov     rcx, r14; sourceString
0x180079274  lea     edx, [rax-1]
0x180079277  cmovb   edx, ebx; length
0x18007927a  call    cs:__imp_WindowsCreateStringReference
0x180079280  test    eax, eax
0x180079282  jns     short loc_180079295
0x180079284  xor     r9d, r9d; lpArguments
0x180079287  xor     r8d, r8d; nNumberOfArguments
0x18007928a  mov     edx, edi; dwExceptionFlags
0x18007928c  mov     ecx, eax; dwExceptionCode
0x18007928e  call    cs:__imp_RaiseException
0x180079294  int     3; Trap to Debugger
0x180079295  mov     rcx, [rbp+0F0h+string]; this
0x18007929c  mov     [rsp+1F0h+pv], r13
0x1800792a1  mov     [rsp+1F0h+var_188], r13
0x1800792a6  mov     [rsp+1F0h+var_180], r13
0x1800792ab  call    ?HasFileUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasFileUriScheme(HSTRING__ *)
0x1800792b0  test    al, al
0x1800792b2  jz      short loc_18007930A
0x1800792b4  mov     rcx, [rsp+1F0h+pv]; pv
0x1800792b9  test    rcx, rcx
0x1800792bc  jz      short loc_1800792C9
0x1800792be  call    cs:__imp_CoTaskMemFree
0x1800792c4  mov     [rsp+1F0h+pv], r13
0x1800792c9  lea     rdx, [rsp+1F0h+pv]; unsigned __int16 *
0x1800792ce  mov     [rsp+1F0h+var_188], r12
0x1800792d3  mov     rcx, r14; pwzURI
0x1800792d6  mov     [rsp+1F0h+var_180], r12
0x1800792db  call    ?ConvertFileUriToFilePath@TileUtils@@YAJPEBGPEAPEAG@Z; TileUtils::ConvertFileUriToFilePath(ushort const *,ushort * *)
0x1800792e0  mov     ebx, eax
0x1800792e2  test    eax, eax
0x1800792e4  jns     loc_18007943E
0x1800792ea  mov     edx, 104h; void *
0x1800792ef  mov     rcx, [rbp+0F8h]; this
0x1800792f6  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800792fd  mov     r9d, eax; char *
0x180079300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079305  jmp     loc_180079FEE
0x18007930a  mov     rcx, [rbp+0F0h+string]; this
0x180079311  call    ?HasMsAppDataUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppDataUriScheme(HSTRING__ *)
0x180079316  test    al, al
0x180079318  jz      loc_18007947B
0x18007931e  lea     rcx, [rbp+0F0h+var_118]
0x180079322  mov     [rbp+0F0h+var_118], r13
0x180079326  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007932b  lea     rax, [rbp+0F0h+var_118]
0x18007932f  mov     r8d, edi; dwClsContext
0x180079332  lea     r9, _GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7; riid
0x180079339  mov     [rsp+1F0h+ppv], rax; int
0x18007933e  xor     edx, edx; pUnkOuter
0x180079340  lea     rcx, _GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169; rclsid
0x180079347  call    cs:__imp_CoCreateInstance
0x18007934d  mov     ebx, eax
0x18007934f  test    eax, eax
0x180079351  jns     short loc_18007937C
0x180079353  mov     rcx, [rbp+0F8h]; this
0x18007935a  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180079361  mov     r9d, eax; char *
0x180079364  mov     edx, 109h; void *
0x180079369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007936e  lea     rcx, [rbp+0F0h+var_118]
0x180079372  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079377  jmp     loc_180079FEE
0x18007937c  lea     rcx, [rsp+1F0h+var_178]
0x180079381  mov     qword ptr [rsp+1F0h+var_178.unused], r13
0x180079386  mov     [rbp+0F0h+var_170], r13
0x18007938a  mov     [rbp+0F0h+var_168], r13
0x18007938e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180079393  lea     r8, [rsp+1F0h+var_178]
0x180079398  mov     [rbp+0F0h+var_170], r12
0x18007939c  lea     rdx, [rsp+1F0h+var_1C0]
0x1800793a1  mov     [rbp+0F0h+var_168], r12
0x1800793a5  mov     rcx, r15; this
0x1800793a8  call    ImmersiveIcons__GetPackageFullNameForAppsFolderItem
0x1800793ad  mov     ebx, eax
0x1800793af  test    eax, eax
0x1800793b1  jns     short loc_1800793DA
0x1800793b3  mov     edx, 10Ch; void *
0x1800793b8  mov     rcx, [rbp+0F8h]; this
0x1800793bf  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800793c6  mov     r9d, eax; char *
0x1800793c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800793ce  lea     rcx, [rsp+1F0h+var_178]
0x1800793d3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800793d8  jmp     short loc_18007936E
0x1800793da  mov     rdi, [rbp+0F0h+var_118]
0x1800793de  lea     rcx, [rsp+1F0h+pv]
0x1800793e3  mov     rax, [rdi]
0x1800793e6  mov     rbx, [rax+30h]
0x1800793ea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800793ef  mov     r8, qword ptr [rsp+1F0h+var_178.unused]
0x1800793f4  lea     rax, [rsp+1F0h+pv]
0x1800793f9  mov     [rsp+1F0h+ppv], rax
0x1800793fe  xor     r9d, r9d
0x180079401  mov     rax, rbx
0x180079404  mov     [rsp+1F0h+var_188], r12
0x180079409  mov     rdx, r14
0x18007940c  mov     [rsp+1F0h+var_180], r12
0x180079411  mov     rcx, rdi
0x180079414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079419  mov     ebx, eax
0x18007941b  test    eax, eax
0x18007941d  jns     short loc_180079426
0x18007941f  mov     edx, 10Eh
0x180079424  jmp     short loc_1800793B8
0x180079426  lea     rcx, [rsp+1F0h+var_178]
0x18007942b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180079430  lea     rcx, [rbp+0F0h+var_118]
0x180079434  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079439  mov     edi, 1
0x18007943e  mov     rax, [rsp+1F0h+pv]
0x180079443  test    rax, rax
0x180079446  jz      short loc_1800794B2
0x180079448  cmp     [rax], r13w
0x18007944c  jz      short loc_1800794B2
0x18007944e  lea     rcx, [rsp+1F0h+pv]
0x180079453  call    ?ReplaceChars@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAXGG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ReplaceChars(ushort,ushort)
0x180079458  mov     r8, [rsp+1F0h+pv]; unsigned __int16 *
0x18007945d  lea     rcx, [rsi+10h]; unsigned __int16 *
0x180079461  mov     edx, 104h; unsigned __int64
0x180079466  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007946b  mov     ebx, eax
0x18007946d  test    eax, eax
0x18007946f  jns     short loc_1800794A6
0x180079471  mov     edx, 1C4h
0x180079476  jmp     loc_1800792EF
0x18007947b  mov     rcx, r14; pszPath
0x18007947e  call    cs:__imp_PathIsRelativeW
0x180079484  test    eax, eax
0x180079486  jnz     short loc_18007943E
0x180079488  lea     rdx, [rbp+0F0h+sourceString]
0x18007948c  lea     rcx, [rsp+1F0h+pv]
0x180079491  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x180079496  mov     ebx, eax
0x180079498  test    eax, eax
0x18007949a  jns     short loc_18007943E
0x18007949c  mov     edx, 114h
0x1800794a1  jmp     loc_1800792EF
0x1800794a6  mov     [rsi], r13
0x1800794a9  mov     [rsi+8], r13b
0x1800794ad  jmp     loc_18007A07C
0x1800794b2  lea     rcx, [rsp+1F0h+var_1B8]
0x1800794b7  mov     [rsp+1F0h+var_1B8], r13
0x1800794bc  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800794c1  lea     rax, [rsp+1F0h+var_1B8]
0x1800794c6  mov     r8d, edi; dwClsContext
0x1800794c9  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x1800794d0  mov     [rsp+1F0h+ppv], rax; int
0x1800794d5  xor     edx, edx; pUnkOuter
0x1800794d7  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x1800794de  call    cs:__imp_CoCreateInstance
0x1800794e4  mov     ebx, eax
0x1800794e6  test    eax, eax
0x1800794e8  jns     short loc_18007950A
0x1800794ea  mov     rcx, [rbp+0F8h]; this
0x1800794f1  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x1800794f8  mov     r9d, eax; char *
0x1800794fb  mov     edx, 11Dh; void *
0x180079500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079505  jmp     loc_180079FE4
0x18007950a  lea     r8, [rbp+0F0h+var_140]
0x18007950e  mov     [rbp+0F0h+var_140], r13
0x180079512  lea     rdx, [rsp+1F0h+var_1C0]
0x180079517  mov     [rbp+0F0h+var_140+8], r12
0x18007951b  mov     rcx, r15; this
0x18007951e  mov     [rbp+0F0h+var_130], r12
0x180079522  call    ImmersiveIcons__GetPackageFullNameForAppsFolderItem
0x180079527  mov     ebx, eax
0x180079529  test    eax, eax
0x18007952b  jns     short loc_18007954D
0x18007952d  mov     edx, 120h; void *
0x180079532  mov     rcx, [rbp+0F8h]; this
0x180079539  lea     r8, aShellLibImmers; "shell\\lib\\immersiveapphelpers\\immers"...
0x180079540  mov     r9d, eax; char *
0x180079543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079548  jmp     loc_180079FDB
0x18007954d  mov     rcx, [rsp+1F0h+var_1B8]
0x180079552  mov     rdx, [rbp+0F0h+var_140]
0x180079556  mov     rax, [rcx]
0x180079559  mov     rax, [rax+28h]
0x18007955d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079562  mov     ebx, eax
0x180079564  test    eax, eax
0x180079566  jns     short loc_18007956F
0x180079568  mov     edx, 122h
0x18007956d  jmp     short loc_180079532
0x18007956f  mov     rdi, [rsp+1F0h+var_1B8]
0x180079574  lea     rcx, [rsp+1F0h+var_1A0]
0x180079579  mov     [rsp+1F0h+var_1A0], r13
0x18007957e  mov     rax, [rdi]
0x180079581  mov     rbx, [rax+38h]
0x180079585  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
  ... truncated ...
```
