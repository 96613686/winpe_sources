# LibraryQueryFolder::Load(IPropertyBag *,IErrorLog *)

- ea: `0x180436dd0`
- end: `0x1804380be`
- name: `?Load@LibraryQueryFolder@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `4846`
- prototype: `int(LibraryQueryFolder *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180026890`
- `0x180038608`
- `0x18003d01c`
- `0x18006b6bc`
- `0x180095028`
- `0x18009be2c`
- `0x18009bfd8`
- `0x18009c7d0`
- `0x18009d460`
- `0x18009d974`
- `0x1800d0f88`
- `0x1800f1cf8`
- `0x180107920`
- `0x18011f798`
- `0x180186560`
- `0x1801affe0`
- `0x180249490`
- `0x18024a53c`
- `0x1802cbf64`
- `0x180357758`
- `0x18043404c`
- `0x180436dd0`
- `0x18043a110`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180437050`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180437050`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x18043729b`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x18043729b`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180437203`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180437203`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180437c6e`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180437c6e`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180437d25`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180437d25`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18043745c`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18043745c`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x180437342`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x1804373e1`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x180437342`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x1804373e1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436e8f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436ec2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436eef`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436f19`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436f40`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1804378db`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18043798a`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180437a3c`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180437aee`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436e8f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436ec2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436eef`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436f19`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180436f40`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1804378db`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18043798a`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180437a3c`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180437aee`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180436e32`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180436fef`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18043718c`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180436e32`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180436fef`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18043718c`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804375f5`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18043775a`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180437bb1`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180437eac`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804375f5`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18043775a`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180437bb1`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180437eac`
- `Windows.Storage!SHParseDisplayName` at `0x18043711e`
- `Windows.Storage!SHParseDisplayName` at `0x18043711e`

## string_xrefs

- `0x180436fe5`: `THIS.CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LibraryQueryFolder::Load(LibraryQueryFolder *this, struct IPropertyBag *a2, struct IErrorLog *a3)
{
  HRESULT v5; // eax
  HRESULT StrAlloc; // ebx
  HRESULT v7; // eax
  DWORD v8; // ecx
  HRESULT v9; // eax
  DWORD v10; // ebx
  DWORD v11; // ecx
  HRESULT v12; // eax
  DWORD v13; // ecx
  HRESULT v14; // eax
  DWORD v15; // ecx
  LibraryQueryFolder *v16; // rcx
  bool v17; // al
  HRESULT v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  HRESULT GUID; // eax
  __int64 v22; // rcx
  HRESULT v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  LibraryQueryFolder *v28; // rcx
  __int64 v29; // rax
  LibraryQueryFolder *v30; // rcx
  unsigned int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // rax
  HRESULT DWORD; // eax
  HRESULT v35; // eax
  HRESULT v36; // eax
  HRESULT v37; // eax
  int SingleVisibleInList; // eax
  int v39; // eax
  int DBFolderWithAutoList; // eax
  HRESULT v41; // ebx
  int psfgaoOut; // [rsp+20h] [rbp-E0h]
  int psfgaoOuta; // [rsp+20h] [rbp-E0h]
  int psfgaoOutb; // [rsp+20h] [rbp-E0h]
  struct ICondition *v46; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  char v48; // [rsp+40h] [rbp-C0h]
  HRESULT v49; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v50[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  GUID v52; // [rsp+60h] [rbp-A0h]
  DWORD v53; // [rsp+70h] [rbp-90h]
  int v54; // [rsp+74h] [rbp-8Ch]
  DWORD v55; // [rsp+7Ch] [rbp-84h]
  DWORD v56; // [rsp+80h] [rbp-80h]
  DWORD v57; // [rsp+84h] [rbp-7Ch]
  DWORD v58; // [rsp+88h] [rbp-78h]
  int v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+B0h] [rbp-50h]
  struct SORTCOLUMN *p_rclsid; // [rsp+B8h] [rbp-48h]
  _BYTE v62[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h]
  struct ICondition *v64; // [rsp+E0h] [rbp-20h]
  __int64 v65; // [rsp+E8h] [rbp-18h]
  __int64 v66; // [rsp+100h] [rbp+0h] BYREF
  __int64 v67; // [rsp+108h] [rbp+8h] BYREF
  LPOLESTR lpsz; // [rsp+110h] [rbp+10h] BYREF
  __int64 v69; // [rsp+118h] [rbp+18h] BYREF
  __int64 v70; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v71; // [rsp+128h] [rbp+28h] BYREF
  struct SORTCOLUMN *v72; // [rsp+130h] [rbp+30h] BYREF
  __int64 v73; // [rsp+138h] [rbp+38h]
  __int64 v74; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v75; // [rsp+148h] [rbp+48h] BYREF
  struct IAutoListDescription *v76; // [rsp+150h] [rbp+50h] BYREF
  DWORD v77; // [rsp+158h] [rbp+58h] BYREF
  DWORD v78; // [rsp+15Ch] [rbp+5Ch] BYREF
  DWORD v79; // [rsp+160h] [rbp+60h] BYREF
  DWORD v80; // [rsp+164h] [rbp+64h] BYREF
  unsigned __int16 *v81; // [rsp+168h] [rbp+68h] BYREF
  DWORD v82; // [rsp+170h] [rbp+70h] BYREF
  GUID value; // [rsp+178h] [rbp+78h] BYREF
  GUID rclsid; // [rsp+188h] [rbp+88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  LibraryQueryFolderTelemetry::LibraryQueryFolder_Load();
  memset_0(v50, 0, 0xB0u);
  value = 0;
  v5 = PSPropertyBag_ReadGUID(a2, L"FolderTypeId_46240254", &value);
  StrAlloc = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v5,
      psfgaoOut);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  v52 = value;
  v78 = 0;
  v7 = PSPropertyBag_ReadDWORD(a2, L"AutoListFlags", &v78);
  v8 = 0;
  if ( v7 >= 0 )
    v8 = v78;
  v53 = v8;
  v54 = 1073872896;
  v79 = 0;
  v9 = PSPropertyBag_ReadDWORD(a2, L"FirstChanceFolderLogicalViewMode", &v79);
  v10 = -1;
  v11 = -1;
  if ( v9 >= 0 )
    v11 = v79;
  v55 = v11;
  v77 = 0;
  v12 = PSPropertyBag_ReadDWORD(a2, L"FirstChanceIconSize", &v77);
  v13 = v56;
  if ( v12 >= 0 )
    v13 = v77;
  v56 = v13;
  v80 = 0;
  if ( PSPropertyBag_ReadDWORD(a2, L"FirstChanceFolderLogicalViewModeStack", &v80) >= 0 )
    v10 = v80;
  v57 = v10;
  v82 = 0;
  v14 = PSPropertyBag_ReadDWORD(a2, L"FirstChanceIconSizeStack", &v82);
  v15 = v58;
  if ( v14 >= 0 )
    v15 = v77;
  v58 = v15;
  v59 = 1;
  v72 = 0;
  v73 = 0;
  wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
  v46 = (struct ICondition *)&v72;
  LODWORD(ppidl) = 0;
  BYTE4(ppidl) = 1;
  v17 = LibraryQueryFolder::LoadSortColumns(v16, a2, (unsigned int *)&ppidl, &v72) >= 0;
  if ( BYTE4(ppidl) )
    v46[1].lpVtbl = (struct IConditionVtbl *)(unsigned int)ppidl;
  if ( v17 )
  {
    p_rclsid = v72;
    v60 = v73;
  }
  else
  {
    p_rclsid = (struct SORTCOLUMN *)&rclsid;
    v60 = 1;
  }
  rclsid = 0;
  v18 = PSPropertyBag_ReadGUID(a2, L"THIS.CLSID", &rclsid);
  StrAlloc = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v18,
      psfgaoOut);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v19 = StringFromCLSID(&rclsid, &lpsz);
  StrAlloc = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x228,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v19,
      psfgaoOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  v20 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (char *)this + 80,
          L"::%ws",
          lpsz);
  StrAlloc = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v20,
      psfgaoOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  v46 = (struct ICondition *)((char *)this + 72);
  ppidl = 0;
  v48 = 1;
  StrAlloc = SHParseDisplayName(*((PCWSTR *)this + 10), 0, &ppidl, 0, 0);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      psfgaoOuta);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  GUID = PSPropertyBag_ReadGUID(a2, L"FolderScope", (GUID *)((char *)this + 136));
  StrAlloc = GUID;
  if ( GUID < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)GUID,
      psfgaoOuta);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  v69 = 0;
  v46 = (struct ICondition *)&v69;
  ppidl = 0;
  v48 = 1;
  StrAlloc = SHGetKnownFolderIDList((const KNOWNFOLDERID *const)((char *)this + 136), 0x5000u, 0, &ppidl);
  wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      psfgaoOuta);
    wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v69, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  v22 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = SHGetKnownFolderItem(
          (const KNOWNFOLDERID *const)((char *)this + 136),
          KF_FLAG_NO_ALIAS|KF_FLAG_DONT_VERIFY,
          0,
          &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
          (void **)this + 11);
  StrAlloc = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v23,
      psfgaoOutb);
    wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v69, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
    ClearAutoListInit((struct AUTOLISTINIT *)v50);
    return (unsigned int)StrAlloc;
  }
  v66 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn>::GetImpl'::`2'::impl) )
  {
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    v24 = SHCreateScopeItemFromIDList(v69, 1, 1, 2048);
    StrAlloc = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23C,
        (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
        (const char *)(unsigned int)v24,
        (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
      if ( v66 )
        winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
LABEL_160:
      wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v69,
        0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
      wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
      ClearAutoListInit((struct AUTOLISTINIT *)v50);
      return (unsigned int)StrAlloc;
    }
  }
  else
  {
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    v25 = SHCreateScopeItemFromIDList(v69, 1, 1, 0);
    StrAlloc = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
        (const char *)(unsigned int)v25,
        (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
      if ( v66 )
        winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
      goto LABEL_160;
    }
  }
  v67 = 0;
  v26 = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &v67);
  StrAlloc = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x245,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v26,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 24LL))(v67, v66);
  StrAlloc = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v27,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v29 = v67;
  v67 = 0;
  v63 = v29;
  v46 = 0;
  StrAlloc = LibraryQueryFolder::CreateFilterCondition(v28, a2, &v46);
  v49 = StrAlloc;
  if ( StrAlloc < 0 )
  {
    LibraryQueryFolderTelemetry::LibraryQueryFolder_FailedToCreateFilterCondition<long const &>(&v49);
    if ( v46 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v46);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v64 = v46;
  v70 = 0;
  v46 = (struct ICondition *)&v70;
  ppidl = 0;
  v48 = 1;
  v31 = (unsigned int)LibraryQueryFolder::LoadPrefetchedProperties(v30, a2, (struct IPropertyKeyStore **)&ppidl) >> 31;
  wil::details::out_param_t<wil::com_ptr_t<IPropertyKeyStore,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IPropertyKeyStore,wil::err_returncode_policy>>(&v46);
  if ( (unsigned __int8)v31 != 1 )
  {
    v32 = v70;
    v70 = 0;
    v65 = v32;
  }
  v71 = 0;
  v46 = (struct ICondition *)&v71;
  ppidl = 0;
  v48 = 1;
  StrAlloc = PSPropertyBag_ReadStrAlloc(a2, L"DisplayName", (PWSTR *)&ppidl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v46 = (struct ICondition *)((char *)this + 96);
  ppidl = 0;
  v48 = 1;
  StrAlloc = LoadIndirectStringAlloc(v71, (unsigned __int16 **)&ppidl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25E,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v75 = 0;
  v46 = (struct ICondition *)&v75;
  ppidl = 0;
  v48 = 1;
  StrAlloc = PSPropertyBag_ReadStrAlloc(a2, L"SearchDisplayName", (PWSTR *)&ppidl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v74 = 0;
  v46 = (struct ICondition *)&v74;
  ppidl = 0;
  v48 = 1;
  StrAlloc = LoadIndirectStringAlloc(v75, (unsigned __int16 **)&ppidl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v33 = v74;
  v74 = 0;
  v51 = v33;
  DWORD = PSPropertyBag_ReadDWORD(a2, L"IndexerOffTitleStringIndex", (DWORD *)this + 30);
  StrAlloc = DWORD;
  if ( DWORD < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x268,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)DWORD,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v35 = PSPropertyBag_ReadDWORD(a2, L"IndexerOffDescriptionStringIndex", (DWORD *)this + 31);
  StrAlloc = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x269,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v35,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v36 = PSPropertyBag_ReadDWORD(a2, L"IndexerOffCFDTitleStringIndex", (DWORD *)this + 32);
  StrAlloc = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v36,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v37 = PSPropertyBag_ReadDWORD(a2, L"IndexerOffCFDDescriptionStringIndex", (DWORD *)this + 33);
  StrAlloc = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26C,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v37,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v46 = (struct ICondition *)((char *)this + 104);
  ppidl = 0;
  v48 = 1;
  StrAlloc = PSPropertyBag_ReadStrAlloc(a2, L"ToolTipProperties", (PWSTR *)&ppidl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( StrAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  SingleVisibleInList = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v62);
  StrAlloc = SingleVisibleInList;
  if ( SingleVisibleInList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)SingleVisibleInList,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v76 = 0;
  v39 = SHCreateAutoList(v50, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, &v76);
  StrAlloc = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v39,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    if ( v76 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v76);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  DBFolderWithAutoList = LibraryQueryFolder::LoadDBFolderWithAutoList((LibraryQueryFolder *)((char *)this - 128), v76);
  StrAlloc = DBFolderWithAutoList;
  if ( DBFolderWithAutoList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)DBFolderWithAutoList,
      (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
    if ( v76 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v76);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
    wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
    if ( v67 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
    if ( v66 )
      winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
    goto LABEL_160;
  }
  v81 = 0;
  v46 = (struct ICondition *)&v81;
  ppidl = 0;
  v48 = 1;
  v41 = PSPropertyBag_ReadStrAlloc(a2, L"DragOverFormatString", (PWSTR *)&ppidl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
  if ( v41 >= 0 )
  {
    v46 = (struct ICondition *)((char *)this + 112);
    ppidl = 0;
    v48 = 1;
    StrAlloc = LoadIndirectStringAlloc(v81, (unsigned __int16 **)&ppidl);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v46);
    if ( StrAlloc < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27B,
        (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
        (const char *)(unsigned int)StrAlloc,
        (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v81);
      if ( v76 )
        winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v76);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
      if ( v67 )
        winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
      if ( v66 )
        winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
      goto LABEL_160;
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v81);
  if ( v76 )
    winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v76);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v74);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v75);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v71);
  wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v70);
  if ( v67 )
    winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v67);
  if ( v66 )
    winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
  wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v69, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
  wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
  ClearAutoListInit((struct AUTOLISTINIT *)v50);
  return 0;
}

```

## disassembly

```asm
0x180436dd0  mov     [rsp-8+arg_10], rbx
0x180436dd5  push    rbp
0x180436dd6  push    rsi
0x180436dd7  push    rdi
0x180436dd8  push    r12
0x180436dda  push    r13
0x180436ddc  push    r14
0x180436dde  push    r15
0x180436de0  lea     rbp, [rsp-0B0h]
0x180436de8  sub     rsp, 1B0h
0x180436def  mov     rax, cs:__security_cookie
0x180436df6  xor     rax, rsp
0x180436df9  mov     [rbp+0E0h+var_40], rax
0x180436e00  mov     rdi, rdx
0x180436e03  mov     rsi, rcx
0x180436e06  call    ?LibraryQueryFolder_Load@LibraryQueryFolderTelemetry@@SAXXZ; LibraryQueryFolderTelemetry::LibraryQueryFolder_Load(void)
0x180436e0b  xor     edx, edx; Val
0x180436e0d  mov     r8d, 0B0h; Size
0x180436e13  lea     rcx, [rsp+1E0h+var_190]; void *
0x180436e18  call    memset_0
0x180436e1d  xorps   xmm0, xmm0
0x180436e20  movups  xmmword ptr [rbp+0E0h+value.Data1], xmm0
0x180436e24  lea     r8, [rbp+0E0h+value]; value
0x180436e28  lea     rdx, aFoldertypeid46; "FolderTypeId_46240254"
0x180436e2f  mov     rcx, rdi; propBag
0x180436e32  call    cs:__imp_PSPropertyBag_ReadGUID
0x180436e39  nop     dword ptr [rax+rax+00h]
0x180436e3e  mov     ebx, eax
0x180436e40  xor     r12d, r12d
0x180436e43  test    eax, eax
0x180436e45  jns     short loc_180436E73
0x180436e47  mov     rcx, [rbp+0E8h]; this
0x180436e4e  mov     r9d, eax; char *
0x180436e51  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180436e58  mov     edx, 1DEh; void *
0x180436e5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180436e62  nop
0x180436e63  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x180436e68  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180436e6d  nop
0x180436e6e  jmp     loc_180438091
0x180436e73  movups  xmm0, xmmword ptr [rbp+0E0h+value.Data1]
0x180436e77  movdqu  [rsp+1E0h+var_180], xmm0
0x180436e7d  mov     [rbp+0E0h+var_84], r12d
0x180436e81  lea     r8, [rbp+0E0h+var_84]; value
0x180436e85  lea     rdx, aAutolistflags; "AutoListFlags"
0x180436e8c  mov     rcx, rdi; propBag
0x180436e8f  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180436e96  nop     dword ptr [rax+rax+00h]
0x180436e9b  mov     ecx, r12d
0x180436e9e  test    eax, eax
0x180436ea0  cmovns  ecx, [rbp+0E0h+var_84]
0x180436ea4  mov     [rsp+1E0h+var_170], ecx
0x180436ea8  mov     [rsp+1E0h+var_16C], 40020000h
0x180436eb0  mov     [rbp+0E0h+var_80], r12d
0x180436eb4  lea     r8, [rbp+0E0h+var_80]; value
0x180436eb8  lea     rdx, aFirstchancefol; "FirstChanceFolderLogicalViewMode"
0x180436ebf  mov     rcx, rdi; propBag
0x180436ec2  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180436ec9  nop     dword ptr [rax+rax+00h]
0x180436ece  or      ebx, 0FFFFFFFFh
0x180436ed1  mov     ecx, ebx
0x180436ed3  test    eax, eax
0x180436ed5  cmovns  ecx, [rbp+0E0h+var_80]
0x180436ed9  mov     [rsp+1E0h+var_164], ecx
0x180436edd  mov     [rbp+0E0h+var_88], r12d
0x180436ee1  lea     r8, [rbp+0E0h+var_88]; value
0x180436ee5  lea     rdx, aFirstchanceico_0; "FirstChanceIconSize"
0x180436eec  mov     rcx, rdi; propBag
0x180436eef  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180436ef6  nop     dword ptr [rax+rax+00h]
0x180436efb  mov     ecx, [rbp+0E0h+var_160]
0x180436efe  test    eax, eax
0x180436f00  cmovns  ecx, [rbp+0E0h+var_88]
0x180436f04  mov     [rbp+0E0h+var_160], ecx
0x180436f07  mov     [rbp+0E0h+var_7C], r12d
0x180436f0b  lea     r8, [rbp+0E0h+var_7C]; value
0x180436f0f  lea     rdx, aFirstchancefol_0; "FirstChanceFolderLogicalViewModeStack"
0x180436f16  mov     rcx, rdi; propBag
0x180436f19  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180436f20  nop     dword ptr [rax+rax+00h]
0x180436f25  test    eax, eax
0x180436f27  cmovns  ebx, [rbp+0E0h+var_7C]
0x180436f2b  mov     [rbp+0E0h+var_15C], ebx
0x180436f2e  mov     [rbp+0E0h+var_70], r12d
0x180436f32  lea     r8, [rbp+0E0h+var_70]; value
0x180436f36  lea     rdx, aFirstchanceico; "FirstChanceIconSizeStack"
0x180436f3d  mov     rcx, rdi; propBag
0x180436f40  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180436f47  nop     dword ptr [rax+rax+00h]
0x180436f4c  mov     ecx, [rbp+0E0h+var_158]
0x180436f4f  test    eax, eax
0x180436f51  cmovns  ecx, [rbp+0E0h+var_88]
0x180436f55  mov     [rbp+0E0h+var_158], ecx
0x180436f58  mov     r13d, 1
0x180436f5e  mov     [rbp+0E0h+var_140], r13d
0x180436f62  mov     [rbp+0E0h+var_B0], r12
0x180436f66  mov     [rbp+0E0h+var_A8], r12
0x180436f6a  lea     rcx, [rbp+0E0h+var_B0]
0x180436f6e  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180436f73  lea     rax, [rbp+0E0h+var_B0]
0x180436f77  mov     [rsp+1E0h+var_1B0], rax
0x180436f7c  mov     dword ptr [rsp+1E0h+ppidl], r12d
0x180436f81  mov     byte ptr [rsp+1E0h+ppidl+4], r13b
0x180436f86  lea     r9, [rbp+0E0h+var_B0]; struct SORTCOLUMN **
0x180436f8a  lea     r8, [rsp+1E0h+ppidl]; unsigned int *
0x180436f8f  mov     rdx, rdi; struct IPropertyBag *
0x180436f92  call    ?LoadSortColumns@LibraryQueryFolder@@AEAAJPEAUIPropertyBag@@PEAIPEAPEAUSORTCOLUMN@@@Z; LibraryQueryFolder::LoadSortColumns(IPropertyBag *,uint *,SORTCOLUMN * *)
0x180436f97  shr     eax, 1Fh
0x180436f9a  xor     al, r13b
0x180436f9d  cmp     byte ptr [rsp+1E0h+ppidl+4], r12b
0x180436fa2  jz      short loc_180436FB1
0x180436fa4  mov     edx, dword ptr [rsp+1E0h+ppidl]
0x180436fa8  mov     rcx, [rsp+1E0h+var_1B0]
0x180436fad  mov     [rcx+8], rdx
0x180436fb1  test    al, al
0x180436fb3  jz      short loc_180436FC5
0x180436fb5  mov     rax, [rbp+0E0h+var_B0]
0x180436fb9  mov     [rbp+0E0h+var_128], rax
0x180436fbd  mov     eax, dword ptr [rbp+0E0h+var_A8]
0x180436fc0  mov     [rbp+0E0h+var_130], eax
0x180436fc3  jmp     short loc_180436FD4
0x180436fc5  lea     rax, [rbp+0E0h+rclsid]
0x180436fcc  mov     [rbp+0E0h+var_128], rax
0x180436fd0  mov     [rbp+0E0h+var_130], r13d
0x180436fd4  xorps   xmm0, xmm0
0x180436fd7  movups  xmmword ptr [rbp+0E0h+rclsid.Data1], xmm0
0x180436fde  lea     r8, [rbp+0E0h+rclsid]; value
0x180436fe5  lea     rdx, aThisClsid; "THIS.CLSID"
0x180436fec  mov     rcx, rdi; propBag
0x180436fef  call    cs:__imp_PSPropertyBag_ReadGUID
0x180436ff6  nop     dword ptr [rax+rax+00h]
0x180436ffb  mov     ebx, eax
0x180436ffd  test    eax, eax
0x180436fff  jns     short loc_180437036
0x180437001  mov     rcx, [rbp+0E8h]; this
0x180437008  mov     r9d, eax; char *
0x18043700b  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180437012  mov     edx, 226h; void *
0x180437017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18043701c  lea     rcx, [rbp+0E0h+var_B0]
0x180437020  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180437025  nop
0x180437026  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x18043702b  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180437030  nop
0x180437031  jmp     loc_180438091
0x180437036  mov     [rbp+0E0h+lpsz], r12
0x18043703a  xor     edx, edx
0x18043703c  lea     rcx, [rbp+0E0h+lpsz]
0x180437040  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180437045  lea     rdx, [rbp+0E0h+lpsz]; lplpsz
0x180437049  lea     rcx, [rbp+0E0h+rclsid]; rclsid
0x180437050  call    cs:__imp_StringFromCLSID
0x180437057  nop     dword ptr [rax+rax+00h]
0x18043705c  mov     ebx, eax
0x18043705e  test    eax, eax
0x180437060  jns     short loc_1804370A0
0x180437062  mov     rcx, [rbp+0E8h]; this
0x180437069  mov     r9d, eax; char *
0x18043706c  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180437073  mov     edx, 228h; void *
0x180437078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18043707d  lea     rcx, [rbp+0E0h+lpsz]; void *
0x180437081  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180437086  lea     rcx, [rbp+0E0h+var_B0]
0x18043708a  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18043708f  nop
0x180437090  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x180437095  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x18043709a  nop
0x18043709b  jmp     loc_180438091
0x1804370a0  lea     rcx, [rsi+50h]
0x1804370a4  mov     r8, [rbp+0E0h+lpsz]
0x1804370a8  lea     rdx, aWs_1; "::%ws"
0x1804370af  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1804370b4  mov     ebx, eax
0x1804370b6  test    eax, eax
0x1804370b8  jns     short loc_1804370F8
0x1804370ba  mov     rcx, [rbp+0E8h]; this
0x1804370c1  mov     r9d, eax; char *
0x1804370c4  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x1804370cb  mov     edx, 229h; void *
0x1804370d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804370d5  lea     rcx, [rbp+0E0h+lpsz]; void *
0x1804370d9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1804370de  lea     rcx, [rbp+0E0h+var_B0]
0x1804370e2  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1804370e7  nop
0x1804370e8  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x1804370ed  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1804370f2  nop
0x1804370f3  jmp     loc_180438091
0x1804370f8  lea     rax, [rsi+48h]
0x1804370fc  mov     [rsp+1E0h+var_1B0], rax
0x180437101  mov     [rsp+1E0h+ppidl], r12
0x180437106  mov     [rsp+1E0h+var_1A0], r13b
0x18043710b  mov     [rsp+1E0h+psfgaoOut], r12; int
0x180437110  xor     r9d, r9d; sfgaoIn
0x180437113  lea     r8, [rsp+1E0h+ppidl]; ppidl
0x180437118  xor     edx, edx; pbc
0x18043711a  mov     rcx, [rsi+50h]; pszName
0x18043711e  call    cs:__imp_SHParseDisplayName
0x180437125  nop     dword ptr [rax+rax+00h]
0x18043712a  mov     ebx, eax
0x18043712c  lea     rcx, [rsp+1E0h+var_1B0]
0x180437131  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180437136  test    ebx, ebx
0x180437138  jns     short loc_180437178
0x18043713a  mov     rcx, [rbp+0E8h]; this
0x180437141  mov     r9d, ebx; char *
0x180437144  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18043714b  mov     edx, 22Ah; void *
0x180437150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180437155  lea     rcx, [rbp+0E0h+lpsz]; void *
0x180437159  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18043715e  lea     rcx, [rbp+0E0h+var_B0]
0x180437162  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180437167  nop
0x180437168  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x18043716d  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180437172  nop
0x180437173  jmp     loc_180438091
0x180437178  lea     r14, [rsi+88h]
0x18043717f  mov     r8, r14; value
0x180437182  lea     rdx, aFolderscope_0; "FolderScope"
0x180437189  mov     rcx, rdi; propBag
0x18043718c  call    cs:__imp_PSPropertyBag_ReadGUID
0x180437193  nop     dword ptr [rax+rax+00h]
0x180437198  mov     ebx, eax
0x18043719a  test    eax, eax
0x18043719c  jns     short loc_1804371DC
0x18043719e  mov     rcx, [rbp+0E8h]; this
0x1804371a5  mov     r9d, eax; char *
0x1804371a8  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x1804371af  mov     edx, 22Ch; void *
0x1804371b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804371b9  lea     rcx, [rbp+0E0h+lpsz]; void *
0x1804371bd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1804371c2  lea     rcx, [rbp+0E0h+var_B0]
0x1804371c6  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1804371cb  nop
0x1804371cc  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x1804371d1  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1804371d6  nop
0x1804371d7  jmp     loc_180438091
0x1804371dc  mov     [rbp+0E0h+var_C8], r12
0x1804371e0  lea     rax, [rbp+0E0h+var_C8]
0x1804371e4  mov     [rsp+1E0h+var_1B0], rax
0x1804371e9  mov     [rsp+1E0h+ppidl], r12
0x1804371ee  mov     [rsp+1E0h+var_1A0], r13b
0x1804371f3  lea     r9, [rsp+1E0h+ppidl]; ppidl
0x1804371f8  xor     r8d, r8d; hToken
0x1804371fb  mov     edx, 5000h; dwFlags
0x180437200  mov     rcx, r14; rfid
0x180437203  call    cs:__imp_SHGetKnownFolderIDList
0x18043720a  nop     dword ptr [rax+rax+00h]
0x18043720f  mov     ebx, eax
0x180437211  lea     rcx, [rsp+1E0h+var_1B0]
0x180437216  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18043721b  test    ebx, ebx
0x18043721d  jns     short loc_180437268
0x18043721f  mov     rcx, [rbp+0E8h]; this
0x180437226  mov     r9d, ebx; char *
0x180437229  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180437230  mov     edx, 230h; void *
0x180437235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18043723a  xor     edx, edx
0x18043723c  lea     rcx, [rbp+0E0h+var_C8]
0x180437240  call    ?reset@?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMID_CHILD@@@Z; wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMID_CHILD *)
0x180437245  lea     rcx, [rbp+0E0h+lpsz]; void *
0x180437249  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18043724e  lea     rcx, [rbp+0E0h+var_B0]
0x180437252  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180437257  nop
0x180437258  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x18043725d  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180437262  nop
0x180437263  jmp     loc_180438091
0x180437268  lea     rbx, [rsi+58h]
0x18043726c  mov     rcx, [rbx]
0x18043726f  mov     [rbx], r12
0x180437272  test    rcx, rcx
0x180437275  jz      short loc_180437284
0x180437277  mov     rax, [rcx]
0x18043727a  mov     rax, [rax+10h]
0x18043727e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180437283  nop
0x180437284  mov     [rsp+1E0h+psfgaoOut], rbx; int
0x180437289  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180437290  xor     r8d, r8d; hToken
0x180437293  mov     edx, 5000h; flags
0x180437298  mov     rcx, r14; rfid
0x18043729b  call    cs:__imp_SHGetKnownFolderItem
0x1804372a2  nop     dword ptr [rax+rax+00h]
0x1804372a7  mov     ebx, eax
0x1804372a9  test    eax, eax
0x1804372ab  jns     short loc_1804372F6
0x1804372ad  mov     rcx, [rbp+0E8h]; this
0x1804372b4  mov     r9d, eax; char *
  ... truncated ...
```
