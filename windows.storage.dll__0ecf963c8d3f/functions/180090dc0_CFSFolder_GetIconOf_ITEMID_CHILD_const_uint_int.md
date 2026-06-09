# CFSFolder::GetIconOf(_ITEMID_CHILD const *,uint,int *)

- ea: `0x180090dc0`
- end: `0x180091865`
- name: `?GetIconOf@CFSFolder@@UEAAJPEFBU_ITEMID_CHILD@@IPEAH@Z`
- size: `2725`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x1800144c4`
- `0x1800432f0`
- `0x180043320`
- `0x180090dc0`
- `0x180091870`
- `0x180093d60`
- `0x180093ef0`
- `0x180096e70`
- `0x1800970c0`
- `0x18009a290`
- `0x18009df20`
- `0x1800a00b0`
- `0x1800a017c`
- `0x1800a04c0`
- `0x1800a08d0`
- `0x1800a14d4`
- `0x1800a3080`
- `0x1800a5690`
- `0x1800a5ac0`
- `0x1800b72b0`
- `0x1800ba864`
- `0x1800c8bc0`
- `0x1800c9310`
- `0x1800d13a0`
- `0x1800d998c`
- `0x1801088e0`
- `0x18012dc90`
- `0x18012fa50`
- `0x180152670`
- `0x180155330`
- `0x180217900`
- `0x1802ec110`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803aee20`
- `0x18065a010`

## import_xrefs

- `ntdll!RtlIsCloudFilesPlaceholder` at `0x180091044`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x180091044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091696`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800910ea`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800910ea`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800910ae`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800910ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18009120e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18009120e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180091091`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180091091`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180091676`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180091676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009110c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009140c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009148c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800914ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009110c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009140c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009148c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800914ae`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180091234`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180091234`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1800910a5`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x1800910a5`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupBackIconIndex` at `0x1800914ee`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupBackIconIndex` at `0x1800914ee`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupFrontIconIndex` at `0x18009134d`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupFrontIconIndex` at `0x18009134d`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_AddToFrontIconTable` at `0x1800915ef`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_AddToFrontIconTable` at `0x18009185a`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_AddToFrontIconTable` at `0x1800915ef`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_AddToFrontIconTable` at `0x18009185a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFSFolder::GetIconOf(CFSFolder *this, const struct _ITEMID_CHILD *a2, unsigned int a3, int *a4)
{
  int *v4; // rdi
  unsigned __int16 *v7; // r8
  const struct _ITEMID_CHILD *v8; // rsi
  const struct _ITEMID_CHILD *v9; // rbx
  const struct _HIDDENITEMID *HiddenID; // rcx
  unsigned __int16 *v11; // rdx
  char *v12; // r12
  _BYTE *v13; // rax
  unsigned __int64 v14; // rcx
  int v15; // r8d
  const struct _HIDDENITEMID *v17; // r9
  __int64 v18; // rcx
  struct CFSFolder *v19; // r13
  unsigned int v20; // r15d
  unsigned int ReparsePointTag; // ebx
  unsigned int FullFileAttributes; // eax
  int (__fastcall *v23)(char *, const struct _ITEMID_CHILD *, __int64, __int64); // rbx
  __int64 v24; // rax
  int DriveNumberW; // eax
  const WCHAR *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rbx
  int v29; // ebx
  unsigned __int16 v30; // dx
  __int16 *i; // rcx
  UINT v32; // ebx
  int CachedImageIndexW; // eax
  BOOL v34; // ebx
  unsigned int v35; // r12d
  const WCHAR *v36; // rdi
  LPWSTR ExtensionW; // rax
  const WCHAR *v38; // rbx
  LPWSTR *v39; // rax
  HRESULT v40; // eax
  bool IsEdpProtected; // r15
  int v42; // eax
  __int64 v43; // r8
  int v44; // ebx
  int v45; // edi
  int v46; // r8d
  enum SHSTOCKICONID v47; // r12d
  CMountPoint *v48; // rdi
  __int64 (__fastcall *v49)(char *, const struct _ITEMID_CHILD *, __int64, __int64); // rbx
  __int64 v50; // rax
  int v51; // eax
  unsigned int v52; // edi
  int v53; // eax
  int *v54; // rbx
  int v55; // ebx
  int v56; // eax
  int v57; // esi
  CMountPoint *v58; // rbx
  unsigned int v59; // edi
  int v60; // eax
  int *v61; // r13
  int v62; // eax
  const WCHAR *v63; // rax
  __int16 v64; // r11
  const unsigned __int16 *v65; // rax
  int StockImageIndex; // eax
  __int64 v67; // rdi
  int (__fastcall *v68)(__int64, __int64, GUID *, __int64); // rbx
  __int64 v69; // rax
  struct IShellItem2 *v70; // rdx
  int v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v73; // [rsp+34h] [rbp-CCh]
  int *v74; // [rsp+38h] [rbp-C8h]
  __int16 v75; // [rsp+40h] [rbp-C0h] BYREF
  int v76; // [rsp+44h] [rbp-BCh]
  __int16 v77; // [rsp+48h] [rbp-B8h]
  int v78; // [rsp+4Ch] [rbp-B4h]
  LPCWSTR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  CMountPoint *v80; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR v81[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v82[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v83[32]; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v84; // [rsp+A0h] [rbp-60h]
  __int64 v85; // [rsp+B8h] [rbp-48h]
  struct IDFOLDER *v86; // [rsp+C0h] [rbp-40h]
  __int64 v87; // [rsp+D0h] [rbp-30h]
  struct _SHSTOCKICONINFO v88; // [rsp+320h] [rbp+220h] BYREF
  WCHAR pszRoot[2]; // [rsp+5D0h] [rbp+4D0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+5E0h] [rbp+4E0h] BYREF
  WCHAR v91[264]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v92[264]; // [rsp+860h] [rbp+760h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AC8h] [rbp+9C8h]

  v4 = a4;
  v74 = a4;
  v73 = a3;
  v80 = this;
  *a4 = -1;
  if ( !(unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent() )
    return 1;
  v8 = 0;
  if ( a2 )
  {
    v18 = *(unsigned __int16 *)a2;
    if ( (unsigned int)v18 > 0xB )
    {
      if ( (*((_BYTE *)a2 + 2) & 0x70) == 0x30 )
      {
        v8 = a2;
        v9 = a2;
        goto LABEL_5;
      }
      if ( *(_DWORD *)((char *)a2 + 6) == 1179862595 )
      {
        if ( *((unsigned __int16 *)a2 + 2) > (unsigned __int64)(v18 - 4) )
          return 1;
        v8 = (const struct _ITEMID_CHILD *)((char *)a2 + 10);
        if ( !IDListContainerIsConsistent((LPCITEMIDLIST)((char *)a2 + 10), *((unsigned __int16 *)a2 + 2))
          || v64 != *(_WORD *)v8 + 6
          || (unsigned __int16)(*(_WORD *)v8 + 6) < *(_WORD *)v8 )
        {
          return 1;
        }
      }
    }
  }
  if ( !v8 )
    return 1;
  v9 = v8;
LABEL_5:
  if ( *(_WORD *)v8 < 0xEu )
    return 1;
  if ( a2
    && *(_WORD *)a2
    && (HiddenID = ILFindFirstHiddenID(a2), v11 = (unsigned __int16 *)((char *)a2 + *(unsigned __int16 *)a2), HiddenID) )
  {
    while ( *((_DWORD *)HiddenID + 1) != -1091633148 )
    {
      v17 = 0;
      if ( (char *)HiddenID + 8 <= (char *)v11 )
      {
        v7 = (unsigned __int16 *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
        if ( v7 == v11 )
          goto LABEL_27;
        if ( v7 <= v11 )
        {
          if ( v7 + 4 > v11
            || HIWORD(*((_DWORD *)v7 + 1)) != 0xBEEF
            || (unsigned __int16 *)((char *)v7 + *v7) > v11
            || v7 < (unsigned __int16 *)HiddenID + 4 )
          {
            goto LABEL_27;
          }
          v17 = (const struct _HIDDENITEMID *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
        }
      }
      HiddenID = v17;
      if ( !v17 )
        goto LABEL_27;
    }
    v12 = (char *)v9 + 2;
  }
  else
  {
LABEL_27:
    v12 = (char *)v8 + 2;
    if ( (*((_BYTE *)v8 + 2) & 0x34) == 0x34 )
    {
      v15 = UnalignedStringCbLengthW(
              (const unsigned __int16 *)v8 + 7,
              *(unsigned __int16 *)v8 - 14LL,
              (unsigned __int64 *)v7);
      goto LABEL_19;
    }
  }
  v13 = (char *)v8 + 14;
  if ( v8 == (const struct _ITEMID_CHILD *)-14LL || (v14 = *(unsigned __int16 *)v8 - 14LL, v14 > 0x7FFFFFFF) )
  {
    v15 = -2147024809;
  }
  else
  {
    if ( *(_WORD *)v8 != 14 )
    {
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v14;
      }
      while ( v14 );
    }
    v15 = -2147024809;
    if ( v14 )
      v15 = 0;
    v12 = (char *)v9 + 2;
  }
LABEL_19:
  if ( v15 < 0 )
    return 1;
  v19 = (CFSFolder *)((char *)this - 56);
  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v82, (CFSFolder *)((char *)this - 56), a2, v8);
  if ( (((*v12 & 0x37) - 49) & 0xFB) != 0 || *v12 < 0 )
  {
    *v4 = 0;
    v35 = CFileSysItemString::ClassFlags((CFileSysItemString *)v82);
    if ( CFileSysItemString::MayHaveFileExtension((CFileSysItemString *)v82) )
    {
      v36 = CFileSysItemString::FSName((CFileSysItemString *)v82);
      ExtensionW = PathFindExtensionW(v36);
      v38 = ExtensionW;
      if ( *ExtensionW )
      {
        v82[8] = ExtensionW == v36;
        v39 = (LPWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v83);
        v40 = SHStrDupW(v38, v39);
        if ( v40 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\fileext.h",
            (const char *)(unsigned int)v40,
            v71);
      }
      v4 = v74;
    }
    IsEdpProtected = 0;
    if ( (GetFullFileAttributes(v86) & 0x4000) != 0 )
    {
      v81[0] = 0;
      v67 = v85;
      v68 = *(int (__fastcall **)(__int64, __int64, GUID *, __int64))(*(_QWORD *)(v85 + 248) + 24LL);
      v69 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(v81);
      if ( v68(v67 + 248, v87, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v69) >= 0 )
        IsEdpProtected = EdpHelpers::IsEdpProtected((EdpHelpers *)v81[0], v70);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v81);
      v4 = v74;
    }
    v42 = IsFolder(v86);
    v44 = CFileExtension::_EnsureIconIndex(
            (CFileExtension *)v82,
            (v73 >> 5) & 1,
            v42,
            IsEdpProtected,
            *(_WORD *)(v43 + 12),
            v4);
    v45 = CFileSysItemString::ClassFlags((CFileSysItemString *)v82);
    if ( v35 != v45 && (!v84 || !*v84) )
    {
      v65 = CFileSysItemString::Class((CFileSysItemString *)v82);
      _SetFileClassInt(v65, 0, v45);
    }
    v46 = 0;
    if ( v44 >= 0 )
      v46 = v45;
    v72 = v46;
    if ( (v46 & 0x1000) == 0 )
      goto LABEL_90;
    *(_DWORD *)pszRoot = 0;
    v47 = SIID_FOLDER;
  }
  else
  {
    v92[0] = 0;
    v20 = 1;
    if ( (GetFullFileAttributes(v8) & 0x400) != 0 )
    {
      v72 = 0;
      CFileSysItemString::CFileSysItemString((CFileSysItemString *)&v88, v19, v8, v8);
      if ( CFileSysItemString::GetReparsePointTag((CFileSysItemString *)&v88) == -1610612724
        || (ReparsePointTag = CFileSysItemString::GetReparsePointTag((CFileSysItemString *)&v88),
            FullFileAttributes = GetFullFileAttributes(v8),
            (unsigned __int8)RtlIsCloudFilesPlaceholder(FullFileAttributes, ReparsePointTag)) )
      {
        v29 = v72;
      }
      else
      {
        pszPath = 0;
        v23 = *(int (__fastcall **)(char *, const struct _ITEMID_CHILD *, __int64, __int64))(*((_QWORD *)v19 + 39)
                                                                                           + 112LL);
        v24 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
        if ( v23((char *)v19 + 312, v8, 1, v24) < 0 )
          goto LABEL_47;
        DriveNumberW = PathGetDriveNumberW(pszPath);
        if ( DriveNumberW == -1 )
          goto LABEL_47;
        v26 = PathBuildRootW(pszRoot, DriveNumberW);
        if ( GetDriveTypeW(v26) == 4 )
          goto LABEL_47;
        v27 = -1;
        do
          ++v27;
        while ( pszPath[v27] );
        v28 = v27 + 1;
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          v81,
          pszPath,
          v27 + 1);
        PathCchAddBackslash(v81[0], v28 + 1);
        if ( !v81[0] )
        {
LABEL_47:
          v29 = v72;
        }
        else
        {
          if ( GetVolumeNameForVolumeMountPointW(v81[0], szVolumeName, 0x32u) )
            v29 = (int)StringCchCopyW(v92, 0x104u, v81[0]) >= 0;
          else
            v29 = v72;
          if ( v81[0] )
            LocalFree(v81[0]);
        }
        if ( pszPath )
          CoTaskMemFree((LPVOID)pszPath);
        v4 = v74;
      }
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)&v88);
      if ( v29 )
      {
        v72 = 0;
        v91[0] = 0;
        v80 = 0;
        if ( (int)CMountPoint::GetMountPoint(v92, 1, &v80) >= 0 )
        {
          v58 = v80;
          v59 = (*(__int64 (__fastcall **)(CMountPoint *, WCHAR *, __int64))(*(_QWORD *)v80 + 200LL))(v80, v91, 260);
          CMountPoint::Release(v58);
        }
        else
        {
          GetShellIconLocationParts(SIID_FOLDER, v91, 0x104u, &v72);
          v59 = v72;
        }
        if ( (v73 & 0x20) == 0 )
        {
          CachedImageIndexW = Shell_GetCachedImageIndexW(v91, v59, 0);
          *v74 = CachedImageIndexW;
LABEL_63:
          v34 = CachedImageIndexW == -1;
          CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v82);
          return v34;
        }
        v60 = SHELL32_LookupBackIconIndex(v91, v59, 0);
        v61 = v74;
        *v74 = v60;
        if ( v60 == -1 )
        {
          StockImageIndex = Shell_GetStockImageIndex(SIID_FOLDER);
          *v61 = StockImageIndex;
          if ( StockImageIndex != -1 )
            v20 = -2147483638;
          CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v82);
          return v20;
        }
LABEL_105:
        CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v82);
        return 0;
      }
    }
    if ( ((((*v12 & 0x37) - 49) & 0xFB) != 0 || *v12 < 0 || (*((_BYTE *)v8 + 12) & 5) == 0)
      && CFSFolder::_GetCSIDL(v19) == -1 )
    {
      v30 = GetFullFileAttributes(v8);
      v75 = 0x4000;
      v76 = 0x2000;
      v77 = 2048;
      v78 = 4096;
      for ( i = &v75; ; i += 4 )
      {
        if ( i == (__int16 *)&pszPath )
          goto LABEL_61;
        if ( ((unsigned __int16)*i & v30) != 0 )
          break;
      }
      v32 = *((_DWORD *)i + 1);
      if ( !v32 )
      {
LABEL_61:
        CachedImageIndexW = Shell_GetStockImageIndex(SIID_FOLDER);
LABEL_62:
        *v4 = CachedImageIndexW;
        goto LABEL_63;
      }
      *(_QWORD *)&v88.cbSize = 544;
      memset_0(&v88.hIcon, 0, 0x218u);
      if ( (int)GetShellIconLocation(SIID_FOLDER, &v88) >= 0 )
      {
        CachedImageIndexW = Shell_GetCachedImageIndexW(v88.szPath, v88.iIcon, v32);
        goto LABEL_62;
      }
      CachedImageIndexW = *v4;
      goto LABEL_63;
    }
    v47 = SIID_FOLDER;
    wcscpy(pszRoot, L"\x03");
    v72 = 4096;
  }
  LODWORD(pszPath) = ((*((unsigned __int16 *)v86 + 4) + 16 * *((unsigned __int16 *)v86 + 5)) << 8)
                   + *((_DWORD *)v86 + 1);
  if ( !(_DWORD)pszPath )
  {
    CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v82);
    return 1;
  }
  v81[0] = 0;
  v48 = v80;
  v49 = *(__int64 (__fastcall **)(char *, const struct _ITEMID_CHILD *, __int64, __int64))(*((_QWORD *)v80 + 32) + 112LL);
  v50 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v81);
  v51 = v49((char *)v48 + 256, a2, 3, v50);
  v44 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2900,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v51,
      v71);
LABEL_88:
    if ( v81[0] )
      CoTaskMemFree(v81[0]);
LABEL_90:
    CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v82);
    return (unsigned int)v44;
  }
  v52 = (unsigned int)pszPath;
  v53 = SHELL32_LookupFrontIconIndex(v81[0], (unsigned int)pszPath, v73);
  v54 = v74;
  *v74 = v53;
  if ( v53 != -1 )
  {
    if ( v81[0] )
      CoTaskMemFree(v81[0]);
    goto LABEL_105;
  }
  if ( (v73 & 0x4020) == 0 )
  {
    if ( !(unsigned int)IsSystemFolder(v8) || CFSFolder::_GetFolderIconPath(v19, a2, 0, v92, v71, 0) )
    {
      v80 = 0;
      v55 = (**(__int64 (__fastcall ***)(struct CFSFolder *, GUID *, CMountPoint **))v19)(
              v19,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &v80);
      if ( v55 >= 0 )
      {
        v55 = SHGetIconIndexFromPIDL((_DWORD)v80, 0, (_DWORD)a2, v73, v74);
        (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v80 + 16LL))(v80);
      }
      if ( *v74 != -1 && !v55 && (v72 & 0x20000) != 0 )
        SHELL32_AddToFrontIconTable(v81[0], v52, v73);
      v44 = *v74 == -1;
    }
    else
    {
      v62 = Shell_GetStockImageIndex(*(enum SHSTOCKICONID *)pszRoot);
      *v54 = v62;
      v44 = v62 == -1;
    }
    goto LABEL_88;
  }
  if ( !(unsigned int)IsFolder(v8) )
  {
    if ( (v72 & 0x20000) != 0 || (v63 = CFileSysItemString::FSName((CFileSysItemString *)v82), !PathIsExe(v63)) )
      v47 = SIID_DOCNOASSOC;
    else
      v47 = SIID_APPLICATION;
  }
  if ( (v73 & 0x4000) != 0 || v47 )
  {
    v56 = Shell_GetStockImageIndex(v47);
    *v74 = v56;
    v57 = -2147483638;
    if ( v56 == -1 )
      v57 = 1;
  }
  else
  {
    pszPath = 0;
    v57 = (**(__int64 (__fastcall ***)(struct CFSFolder *, GUID *, LPCWSTR *))v19)(
            v19,
            &GUID_000214e6_0000_0000_c000_000000000046,
            &pszPath);
    if ( v57 >= 0 )
    {
      v57 = SHGetIconIndexFromPIDL((_DWORD)pszPath, 0, (_DWORD)a2, v73, v74);
      if ( !v57 && *v74 != -1 && (v72 & 0x20000) != 0 )
        SHELL32_AddToFrontIconTable(v81[0], v52, v73);
      (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
    }
  }
  if ( v81[0] )
    CoTaskMemFree(v81[0]);
  CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v82);
  return (unsigned int)v57;
}

```

## disassembly

```asm
0x180090dc0  push    rbp
0x180090dc2  push    rbx
0x180090dc3  push    rsi
0x180090dc4  push    rdi
0x180090dc5  push    r12
0x180090dc7  push    r13
0x180090dc9  push    r14
0x180090dcb  push    r15
0x180090dcd  lea     rbp, [rsp-988h]
0x180090dd5  sub     rsp, 0A88h
0x180090ddc  mov     rax, cs:__security_cookie
0x180090de3  xor     rax, rsp
0x180090de6  mov     [rbp+9C0h+var_50], rax
0x180090ded  mov     rdi, r9
0x180090df0  mov     [rsp+0AC0h+var_A88], r9
0x180090df5  mov     [rsp+0AC0h+var_A8C], r8d
0x180090dfa  mov     r14, rdx
0x180090dfd  mov     r15, rcx
0x180090e00  mov     [rsp+0AC0h+var_A68], rcx
0x180090e05  mov     dword ptr [r9], 0FFFFFFFFh
0x180090e0c  call    IsSHELL32_SHIsVirtualDevicePresent
0x180090e11  test    al, al
0x180090e13  jz      loc_180090ED0
0x180090e19  xor     esi, esi
0x180090e1b  test    r14, r14
0x180090e1e  jnz     loc_180090F5A
0x180090e24  test    rsi, rsi
0x180090e27  jz      loc_180090ED0
0x180090e2d  mov     rbx, rsi
0x180090e30  cmp     word ptr [rsi], 0Eh
0x180090e34  jb      loc_180090ED0
0x180090e3a  test    r14, r14
0x180090e3d  jz      loc_180090F2F
0x180090e43  cmp     word ptr [r14], 0
0x180090e48  jz      loc_180090F2F
0x180090e4e  mov     rcx, r14; struct _ITEMIDLIST_RELATIVE *
0x180090e51  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x180090e56  mov     rcx, rax
0x180090e59  movzx   edx, word ptr [r14]
0x180090e5d  add     rdx, r14
0x180090e60  test    rax, rax
0x180090e63  jz      loc_180090F2F
0x180090e69  mov     r11d, 0BEEFh
0x180090e6f  cmp     dword ptr [rcx+4], 0BEEF0004h
0x180090e76  jnz     loc_180090F81
0x180090e7c  lea     r12, [rbx+2]
0x180090e80  lea     rax, [rsi+0Eh]
0x180090e84  test    rax, rax
0x180090e87  jz      loc_1800917C1
0x180090e8d  movzx   ecx, word ptr [rsi]
0x180090e90  add     rcx, 0FFFFFFFFFFFFFFF2h
0x180090e94  cmp     rcx, 7FFFFFFFh
0x180090e9b  ja      loc_1800917C1
0x180090ea1  test    rcx, rcx
0x180090ea4  jz      short loc_180090EB4
0x180090ea6  cmp     byte ptr [rax], 0
0x180090ea9  jz      short loc_180090EB4
0x180090eab  inc     rax
0x180090eae  sub     rcx, 1
0x180090eb2  jnz     short loc_180090EA6
0x180090eb4  xor     eax, eax
0x180090eb6  mov     r8d, 80070057h
0x180090ebc  test    rcx, rcx
0x180090ebf  cmovnz  r8d, eax
0x180090ec3  lea     r12, [rbx+2]
0x180090ec7  test    r8d, r8d
0x180090eca  jns     loc_180090FA0
0x180090ed0  mov     eax, 1
0x180090ed5  mov     rcx, [rbp+9C0h+var_50]
0x180090edc  xor     rcx, rsp; StackCookie
0x180090edf  call    __security_check_cookie
0x180090ee4  add     rsp, 0A88h
0x180090eeb  pop     r15
0x180090eed  pop     r14
0x180090eef  pop     r13
0x180090ef1  pop     r12
0x180090ef3  pop     rdi
0x180090ef4  pop     rsi
0x180090ef5  pop     rbx
0x180090ef6  pop     rbp
0x180090ef7  retn
0x180090ef8  lea     rax, [r8+8]
0x180090efc  cmp     rax, rdx
0x180090eff  ja      short loc_180090F2F
0x180090f01  mov     eax, [r8+4]
0x180090f05  shr     rax, 10h
0x180090f09  cmp     ax, r11w
0x180090f0d  jnz     short loc_180090F2F
0x180090f0f  movzx   eax, word ptr [r8]
0x180090f13  add     rax, r8
0x180090f16  cmp     rax, rdx
0x180090f19  ja      short loc_180090F2F
0x180090f1b  cmp     r8, r10
0x180090f1e  jb      short loc_180090F2F
0x180090f20  mov     r9, r8
0x180090f23  mov     rcx, r9
0x180090f26  test    r9, r9
0x180090f29  jnz     loc_180090E6F
0x180090f2f  lea     r12, [rsi+2]
0x180090f33  movzx   eax, byte ptr [r12]
0x180090f38  and     al, 34h
0x180090f3a  cmp     al, 34h ; '4'
0x180090f3c  jnz     loc_180090E80
0x180090f42  movzx   edx, word ptr [rsi]
0x180090f45  sub     rdx, 0Eh; unsigned __int64
0x180090f49  lea     rcx, [rsi+0Eh]; unsigned __int16 *
0x180090f4d  call    ?UnalignedStringCbLengthW@@YAJPEFBG_KPEA_K@Z; UnalignedStringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180090f52  mov     r8d, eax
0x180090f55  jmp     loc_180090EC7
0x180090f5a  movzx   ecx, word ptr [r14]
0x180090f5e  cmp     ecx, 0Bh
0x180090f61  jbe     loc_180090E24
0x180090f67  movzx   eax, byte ptr [r14+2]
0x180090f6c  and     al, 70h
0x180090f6e  cmp     al, 30h ; '0'
0x180090f70  jnz     loc_180091722
0x180090f76  mov     rsi, r14
0x180090f79  mov     rbx, r14
0x180090f7c  jmp     loc_180090E30
0x180090f81  xor     r9d, r9d
0x180090f84  lea     r10, [rcx+8]
0x180090f88  cmp     r10, rdx
0x180090f8b  ja      short loc_180090F23
0x180090f8d  movzx   r8d, word ptr [rcx]
0x180090f91  add     r8, rcx; unsigned __int64 *
0x180090f94  cmp     r8, rdx
0x180090f97  jz      short loc_180090F2F
0x180090f99  ja      short loc_180090F23
0x180090f9b  jmp     loc_180090EF8
0x180090fa0  lea     r13, [r15-38h]
0x180090fa4  mov     r9, rsi; struct IDFOLDER *
0x180090fa7  mov     r8, r14; struct _ITEMIDLIST_RELATIVE *
0x180090faa  mov     rdx, r13; struct CFSFolder *
0x180090fad  lea     rcx, [rsp+0AC0h+var_A50]; this
0x180090fb2  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180090fb7  nop
0x180090fb8  movzx   ecx, byte ptr [r12]
0x180090fbd  movzx   eax, cl
0x180090fc0  and     al, 37h
0x180090fc2  sub     al, 31h ; '1'
0x180090fc4  test    al, 0FBh
0x180090fc6  jnz     loc_1800911DD
0x180090fcc  test    cl, cl
0x180090fce  js      loc_1800911DD
0x180090fd4  xor     eax, eax
0x180090fd6  mov     [rbp+9C0h+var_260], ax
0x180090fdd  mov     rcx, rsi; struct IDFOLDER *
0x180090fe0  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x180090fe5  mov     r15d, 1
0x180090feb  bt      eax, 0Ah
0x180090fef  jnb     loc_18009112B
0x180090ff5  mov     [rsp+0AC0h+var_A90], 0
0x180090ffd  mov     r9, rsi; struct IDFOLDER *
0x180091000  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x180091003  mov     rdx, r13; struct CFSFolder *
0x180091006  lea     rcx, [rbp+9C0h+var_7A0]; this
0x18009100d  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x180091012  nop
0x180091013  lea     rcx, [rbp+9C0h+var_7A0]; this
0x18009101a  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x18009101f  cmp     eax, 0A000000Ch
0x180091024  jz      loc_1800911D4
0x18009102a  lea     rcx, [rbp+9C0h+var_7A0]; this
0x180091031  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x180091036  mov     ebx, eax
0x180091038  mov     rcx, rsi; struct IDFOLDER *
0x18009103b  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x180091040  mov     edx, ebx
0x180091042  mov     ecx, eax
0x180091044  call    cs:__imp_RtlIsCloudFilesPlaceholder
0x18009104a  test    al, al
0x18009104c  jnz     loc_1800911D4
0x180091052  mov     [rsp+0AC0h+pszPath], 0
0x18009105b  mov     rax, [r13+138h]
0x180091062  mov     rbx, [rax+70h]
0x180091066  lea     rcx, [rsp+0AC0h+pszPath]
0x18009106b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180091070  mov     r9, rax
0x180091073  mov     r8d, r15d
0x180091076  mov     rdx, rsi
0x180091079  lea     rcx, [r13+138h]
0x180091080  mov     rax, rbx
0x180091083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091088  test    eax, eax
0x18009108a  js      short loc_1800910FE
0x18009108c  mov     rcx, [rsp+0AC0h+pszPath]; pszPath
0x180091091  call    cs:__imp_PathGetDriveNumberW
0x180091097  cmp     eax, 0FFFFFFFFh
0x18009109a  jz      short loc_1800910FE
0x18009109c  mov     edx, eax; iDrive
0x18009109e  lea     rcx, [rbp+9C0h+pszRoot]; pszRoot
0x1800910a5  call    cs:__imp_PathBuildRootW
0x1800910ab  mov     rcx, rax; lpRootPathName
0x1800910ae  call    cs:__imp_GetDriveTypeW
0x1800910b4  cmp     eax, 4
0x1800910b7  jz      short loc_1800910FE
0x1800910b9  mov     rdx, [rsp+0AC0h+pszPath]
0x1800910be  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800910c5  lea     rax, [rax+1]
0x1800910c9  cmp     word ptr [rdx+rax*2], 0
0x1800910ce  jnz     short loc_1800910C5
0x1800910d0  lea     rbx, [rax+1]
0x1800910d4  mov     r8, rbx
0x1800910d7  lea     rcx, [rsp+0AC0h+var_A60]
0x1800910dc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800910e1  lea     rdx, [rbx+1]; cchPath
0x1800910e5  mov     rcx, [rsp+0AC0h+var_A60]; pszPath
0x1800910ea  call    cs:__imp_PathCchAddBackslash
0x1800910f0  mov     rcx, [rsp+0AC0h+var_A60]; lpszVolumeMountPoint
0x1800910f5  test    rcx, rcx
0x1800910f8  jnz     loc_180091669
0x1800910fe  mov     ebx, [rsp+0AC0h+var_A90]
0x180091102  mov     rcx, [rsp+0AC0h+pszPath]; pv
0x180091107  test    rcx, rcx
0x18009110a  jz      short loc_180091112
0x18009110c  call    cs:__imp_CoTaskMemFree
0x180091112  mov     rdi, [rsp+0AC0h+var_A88]
0x180091117  lea     rcx, [rbp+9C0h+var_7A0]; this
0x18009111e  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x180091123  test    ebx, ebx
0x180091125  jnz     loc_180091517
0x18009112b  movzx   ecx, byte ptr [r12]
0x180091130  movzx   eax, cl
0x180091133  and     al, 37h
0x180091135  sub     al, 31h ; '1'
0x180091137  test    al, 0FBh
0x180091139  jnz     short loc_180091149
0x18009113b  test    cl, cl
0x18009113d  js      short loc_180091149
0x18009113f  test    byte ptr [rsi+0Ch], 5
0x180091143  jnz     loc_180091424
0x180091149  mov     rcx, r13; this
0x18009114c  call    ?_GetCSIDL@CFSFolder@@IEAAIXZ; CFSFolder::_GetCSIDL(void)
0x180091151  cmp     eax, 0FFFFFFFFh
0x180091154  jnz     loc_180091424
0x18009115a  mov     rcx, rsi; struct IDFOLDER *
0x18009115d  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x180091162  mov     edx, eax
0x180091164  mov     eax, 4000h
0x180091169  mov     [rsp+0AC0h+var_A80], ax
0x18009116e  mov     [rsp+0AC0h+var_A7C], 2000h
0x180091176  mov     eax, 800h
0x18009117b  mov     [rsp+0AC0h+var_A78], ax
0x180091180  mov     [rsp+0AC0h+var_A74], 1000h
0x180091188  lea     rcx, [rsp+0AC0h+var_A80]
0x18009118d  lea     rax, [rsp+0AC0h+pszPath]
0x180091192  cmp     rcx, rax
0x180091195  jz      short loc_1800911AF
0x180091197  movzx   eax, word ptr [rcx]
0x18009119a  test    edx, eax
0x18009119c  jnz     short loc_1800911A4
0x18009119e  add     rcx, 8
0x1800911a2  jmp     short loc_18009118D
0x1800911a4  mov     ebx, [rcx+4]
0x1800911a7  test    ebx, ebx
0x1800911a9  jnz     loc_1800916AF
0x1800911af  mov     ecx, 3; enum SHSTOCKICONID
0x1800911b4  call    ?Shell_GetStockImageIndex@@YAHW4SHSTOCKICONID@@@Z; Shell_GetStockImageIndex(SHSTOCKICONID)
0x1800911b9  mov     [rdi], eax
0x1800911bb  xor     ebx, ebx
0x1800911bd  cmp     eax, 0FFFFFFFFh
0x1800911c0  setz    bl
0x1800911c3  lea     rcx, [rsp+0AC0h+var_A50]; this
0x1800911c8  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x1800911cd  mov     eax, ebx
0x1800911cf  jmp     loc_180090ED5
0x1800911d4  mov     ebx, [rsp+0AC0h+var_A90]
0x1800911d8  jmp     loc_180091117
0x1800911dd  mov     dword ptr [rdi], 0
0x1800911e3  lea     rcx, [rsp+0AC0h+var_A50]; this
0x1800911e8  call    ?ClassFlags@CFileSysItemString@@UEAAKXZ; CFileSysItemString::ClassFlags(void)
0x1800911ed  mov     r12d, eax
0x1800911f0  lea     rcx, [rsp+0AC0h+var_A50]; this
0x1800911f5  call    ?MayHaveFileExtension@CFileSysItemString@@IEAA_NXZ; CFileSysItemString::MayHaveFileExtension(void)
0x1800911fa  test    al, al
0x1800911fc  jz      short loc_180091247
0x1800911fe  lea     rcx, [rsp+0AC0h+var_A50]; this
0x180091203  call    ?FSName@CFileSysItemString@@QEAAPEBGXZ; CFileSysItemString::FSName(void)
0x180091208  mov     rdi, rax
0x18009120b  mov     rcx, rax; pszPath
0x18009120e  call    cs:__imp_PathFindExtensionW
0x180091214  mov     rbx, rax
0x180091217  cmp     word ptr [rax], 0
0x18009121b  jz      short loc_180091242
0x18009121d  cmp     rax, rdi
0x180091220  setz    [rsp+0AC0h+var_A48]
0x180091225  lea     rcx, [rbp+9C0h+var_A40]
0x180091229  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18009122e  mov     rdx, rax; ppwsz
0x180091231  mov     rcx, rbx; psz
0x180091234  call    cs:__imp_SHStrDupW
0x18009123a  test    eax, eax
0x18009123c  js      loc_180091818
0x180091242  mov     rdi, [rsp+0AC0h+var_A88]
0x180091247  xor     r15b, r15b
0x18009124a  mov     rcx, [rbp+9C0h+var_A00]; struct IDFOLDER *
0x18009124e  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x180091253  bt      eax, 0Eh
0x180091257  jb      loc_180641E5A
0x18009125d  mov     r8, [rbp+9C0h+var_A00]
  ... truncated ...
```
