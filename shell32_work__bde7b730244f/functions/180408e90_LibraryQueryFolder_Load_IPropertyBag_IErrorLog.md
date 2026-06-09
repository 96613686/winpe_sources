# LibraryQueryFolder::Load(IPropertyBag *,IErrorLog *)

- ea: `0x180408e90`
- end: `0x18040a0e7`
- name: `?Load@LibraryQueryFolder@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `4695`
- prototype: `int(LibraryQueryFolder *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800181e0`
- `0x18002b9a8`
- `0x18003cd64`
- `0x1800415dc`
- `0x1800523b0`
- `0x180052540`
- `0x1800526dc`
- `0x180053708`
- `0x180054320`
- `0x1800cad60`
- `0x1800e1b18`
- `0x1800ff4dc`
- `0x1800ffb30`
- `0x180112514`
- `0x180177e50`
- `0x18019be50`
- `0x180233280`
- `0x1802342fc`
- `0x1802b080c`
- `0x1803362ec`
- `0x1804067a8`
- `0x180408e90`
- `0x18040b714`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1804090e6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1804090e6`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x180409319`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderItem` at `0x180409319`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180409287`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180409287`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180409d5b`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180409d5b`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180409caa`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180409caa`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x1804094c8`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x1804094c8`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x1804093ba`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x180409453`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x1804093ba`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x180409453`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408f49`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408f76`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408f9d`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408fc1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408fe2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180409935`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1804099de`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180409a8a`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180409b36`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408f49`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408f76`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408f9d`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408fc1`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180408fe2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180409935`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1804099de`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180409a8a`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180409b36`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180408ef2`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18040908b`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180409216`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180408ef2`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18040908b`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180409216`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18040965b`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804097ba`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180409bf3`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180409edc`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18040965b`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1804097ba`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180409bf3`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x180409edc`
- `Windows.Storage!SHParseDisplayName` at `0x1804091ae`
- `Windows.Storage!SHParseDisplayName` at `0x1804091ae`

## string_xrefs

- `0x180409081`: `THIS.CLSID`

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
      (void *)0x1D6,
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
      (void *)0x21E,
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
      (void *)0x220,
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
      (void *)0x221,
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
      (void *)0x222,
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
      (void *)0x224,
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
      (void *)0x228,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)StrAlloc,
      psfgaoOuta);
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v69,
      0);
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
      (void *)0x22C,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v23,
      psfgaoOutb);
    wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v69,
      0);
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
        (void *)0x234,
        (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
        (const char *)(unsigned int)v24,
        (int)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0);
      if ( v66 )
        winrt::com_ptr<IPropertyDescriptionList>::unconditional_release_ref(&v66);
LABEL_160:
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
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
        (void *)0x239,
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
      (void *)0x23D,
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
      (void *)0x23E,
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
      (void *)0x254,
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
      (void *)0x256,
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
      (void *)0x25A,
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
      (void *)0x25D,
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
      (void *)0x260,
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
      (void *)0x261,
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
      (void *)0x263,
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
      (void *)0x264,
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
      (void *)0x266,
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
      (void *)0x268,
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
      (void *)0x26B,
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
      (void *)0x26D,
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
        (void *)0x273,
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
  wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v69,
    0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpsz);
  wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v72);
  ClearAutoListInit((struct AUTOLISTINIT *)v50);
  return 0;
}

```

## disassembly

```asm
0x180408e90  mov     [rsp-8+arg_10], rbx
0x180408e95  push    rbp
0x180408e96  push    rsi
0x180408e97  push    rdi
0x180408e98  push    r12
0x180408e9a  push    r13
0x180408e9c  push    r14
0x180408e9e  push    r15
0x180408ea0  lea     rbp, [rsp-0B0h]
0x180408ea8  sub     rsp, 1B0h
0x180408eaf  mov     rax, cs:__security_cookie
0x180408eb6  xor     rax, rsp
0x180408eb9  mov     [rbp+0E0h+var_40], rax
0x180408ec0  mov     rdi, rdx
0x180408ec3  mov     rsi, rcx
0x180408ec6  call    ?LibraryQueryFolder_Load@LibraryQueryFolderTelemetry@@SAXXZ; LibraryQueryFolderTelemetry::LibraryQueryFolder_Load(void)
0x180408ecb  xor     edx, edx; Val
0x180408ecd  mov     r8d, 0B0h; Size
0x180408ed3  lea     rcx, [rsp+1E0h+var_190]; void *
0x180408ed8  call    memset_0
0x180408edd  xorps   xmm0, xmm0
0x180408ee0  movups  xmmword ptr [rbp+0E0h+value.Data1], xmm0
0x180408ee4  lea     r8, [rbp+0E0h+value]; value
0x180408ee8  lea     rdx, aFoldertypeid46; "FolderTypeId_46240254"
0x180408eef  mov     rcx, rdi; propBag
0x180408ef2  call    cs:__imp_PSPropertyBag_ReadGUID
0x180408ef8  mov     ebx, eax
0x180408efa  xor     r12d, r12d
0x180408efd  test    eax, eax
0x180408eff  jns     short loc_180408F2D
0x180408f01  mov     rcx, [rbp+0E8h]; this
0x180408f08  mov     r9d, eax; char *
0x180408f0b  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180408f12  mov     edx, 1D6h; void *
0x180408f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180408f1c  nop
0x180408f1d  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x180408f22  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180408f27  nop
0x180408f28  jmp     loc_18040A0BB
0x180408f2d  movups  xmm0, xmmword ptr [rbp+0E0h+value.Data1]
0x180408f31  movdqu  [rsp+1E0h+var_180], xmm0
0x180408f37  mov     [rbp+0E0h+var_84], r12d
0x180408f3b  lea     r8, [rbp+0E0h+var_84]; value
0x180408f3f  lea     rdx, aAutolistflags; "AutoListFlags"
0x180408f46  mov     rcx, rdi; propBag
0x180408f49  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180408f4f  mov     ecx, r12d
0x180408f52  test    eax, eax
0x180408f54  cmovns  ecx, [rbp+0E0h+var_84]
0x180408f58  mov     [rsp+1E0h+var_170], ecx
0x180408f5c  mov     [rsp+1E0h+var_16C], 40020000h
0x180408f64  mov     [rbp+0E0h+var_80], r12d
0x180408f68  lea     r8, [rbp+0E0h+var_80]; value
0x180408f6c  lea     rdx, aFirstchancefol; "FirstChanceFolderLogicalViewMode"
0x180408f73  mov     rcx, rdi; propBag
0x180408f76  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180408f7c  or      ebx, 0FFFFFFFFh
0x180408f7f  mov     ecx, ebx
0x180408f81  test    eax, eax
0x180408f83  cmovns  ecx, [rbp+0E0h+var_80]
0x180408f87  mov     [rsp+1E0h+var_164], ecx
0x180408f8b  mov     [rbp+0E0h+var_88], r12d
0x180408f8f  lea     r8, [rbp+0E0h+var_88]; value
0x180408f93  lea     rdx, aFirstchanceico_0; "FirstChanceIconSize"
0x180408f9a  mov     rcx, rdi; propBag
0x180408f9d  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180408fa3  mov     ecx, [rbp+0E0h+var_160]
0x180408fa6  test    eax, eax
0x180408fa8  cmovns  ecx, [rbp+0E0h+var_88]
0x180408fac  mov     [rbp+0E0h+var_160], ecx
0x180408faf  mov     [rbp+0E0h+var_7C], r12d
0x180408fb3  lea     r8, [rbp+0E0h+var_7C]; value
0x180408fb7  lea     rdx, aFirstchancefol_0; "FirstChanceFolderLogicalViewModeStack"
0x180408fbe  mov     rcx, rdi; propBag
0x180408fc1  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180408fc7  test    eax, eax
0x180408fc9  cmovns  ebx, [rbp+0E0h+var_7C]
0x180408fcd  mov     [rbp+0E0h+var_15C], ebx
0x180408fd0  mov     [rbp+0E0h+var_70], r12d
0x180408fd4  lea     r8, [rbp+0E0h+var_70]; value
0x180408fd8  lea     rdx, aFirstchanceico; "FirstChanceIconSizeStack"
0x180408fdf  mov     rcx, rdi; propBag
0x180408fe2  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180408fe8  mov     ecx, [rbp+0E0h+var_158]
0x180408feb  test    eax, eax
0x180408fed  cmovns  ecx, [rbp+0E0h+var_88]
0x180408ff1  mov     [rbp+0E0h+var_158], ecx
0x180408ff4  mov     r13d, 1
0x180408ffa  mov     [rbp+0E0h+var_140], r13d
0x180408ffe  mov     [rbp+0E0h+var_B0], r12
0x180409002  mov     [rbp+0E0h+var_A8], r12
0x180409006  lea     rcx, [rbp+0E0h+var_B0]
0x18040900a  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18040900f  lea     rax, [rbp+0E0h+var_B0]
0x180409013  mov     [rsp+1E0h+var_1B0], rax
0x180409018  mov     dword ptr [rsp+1E0h+ppidl], r12d
0x18040901d  mov     byte ptr [rsp+1E0h+ppidl+4], r13b
0x180409022  lea     r9, [rbp+0E0h+var_B0]; struct SORTCOLUMN **
0x180409026  lea     r8, [rsp+1E0h+ppidl]; unsigned int *
0x18040902b  mov     rdx, rdi; struct IPropertyBag *
0x18040902e  call    ?LoadSortColumns@LibraryQueryFolder@@AEAAJPEAUIPropertyBag@@PEAIPEAPEAUSORTCOLUMN@@@Z; LibraryQueryFolder::LoadSortColumns(IPropertyBag *,uint *,SORTCOLUMN * *)
0x180409033  shr     eax, 1Fh
0x180409036  xor     al, r13b
0x180409039  cmp     byte ptr [rsp+1E0h+ppidl+4], r12b
0x18040903e  jz      short loc_18040904D
0x180409040  mov     edx, dword ptr [rsp+1E0h+ppidl]
0x180409044  mov     rcx, [rsp+1E0h+var_1B0]
0x180409049  mov     [rcx+8], rdx
0x18040904d  test    al, al
0x18040904f  jz      short loc_180409061
0x180409051  mov     rax, [rbp+0E0h+var_B0]
0x180409055  mov     [rbp+0E0h+var_128], rax
0x180409059  mov     eax, dword ptr [rbp+0E0h+var_A8]
0x18040905c  mov     [rbp+0E0h+var_130], eax
0x18040905f  jmp     short loc_180409070
0x180409061  lea     rax, [rbp+0E0h+rclsid]
0x180409068  mov     [rbp+0E0h+var_128], rax
0x18040906c  mov     [rbp+0E0h+var_130], r13d
0x180409070  xorps   xmm0, xmm0
0x180409073  movups  xmmword ptr [rbp+0E0h+rclsid.Data1], xmm0
0x18040907a  lea     r8, [rbp+0E0h+rclsid]; value
0x180409081  lea     rdx, aThisClsid; "THIS.CLSID"
0x180409088  mov     rcx, rdi; propBag
0x18040908b  call    cs:__imp_PSPropertyBag_ReadGUID
0x180409091  mov     ebx, eax
0x180409093  test    eax, eax
0x180409095  jns     short loc_1804090CC
0x180409097  mov     rcx, [rbp+0E8h]; this
0x18040909e  mov     r9d, eax; char *
0x1804090a1  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x1804090a8  mov     edx, 21Eh; void *
0x1804090ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804090b2  lea     rcx, [rbp+0E0h+var_B0]
0x1804090b6  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1804090bb  nop
0x1804090bc  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x1804090c1  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1804090c6  nop
0x1804090c7  jmp     loc_18040A0BB
0x1804090cc  mov     [rbp+0E0h+lpsz], r12
0x1804090d0  xor     edx, edx
0x1804090d2  lea     rcx, [rbp+0E0h+lpsz]
0x1804090d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1804090db  lea     rdx, [rbp+0E0h+lpsz]; lplpsz
0x1804090df  lea     rcx, [rbp+0E0h+rclsid]; rclsid
0x1804090e6  call    cs:__imp_StringFromCLSID
0x1804090ec  mov     ebx, eax
0x1804090ee  test    eax, eax
0x1804090f0  jns     short loc_180409130
0x1804090f2  mov     rcx, [rbp+0E8h]; this
0x1804090f9  mov     r9d, eax; char *
0x1804090fc  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180409103  mov     edx, 220h; void *
0x180409108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18040910d  lea     rcx, [rbp+0E0h+lpsz]; void *
0x180409111  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180409116  lea     rcx, [rbp+0E0h+var_B0]
0x18040911a  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18040911f  nop
0x180409120  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x180409125  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x18040912a  nop
0x18040912b  jmp     loc_18040A0BB
0x180409130  lea     rcx, [rsi+50h]
0x180409134  mov     r8, [rbp+0E0h+lpsz]
0x180409138  lea     rdx, aWs_0; "::%ws"
0x18040913f  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180409144  mov     ebx, eax
0x180409146  test    eax, eax
0x180409148  jns     short loc_180409188
0x18040914a  mov     rcx, [rbp+0E8h]; this
0x180409151  mov     r9d, eax; char *
0x180409154  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18040915b  mov     edx, 221h; void *
0x180409160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180409165  lea     rcx, [rbp+0E0h+lpsz]; void *
0x180409169  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18040916e  lea     rcx, [rbp+0E0h+var_B0]
0x180409172  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180409177  nop
0x180409178  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x18040917d  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180409182  nop
0x180409183  jmp     loc_18040A0BB
0x180409188  lea     rax, [rsi+48h]
0x18040918c  mov     [rsp+1E0h+var_1B0], rax
0x180409191  mov     [rsp+1E0h+ppidl], r12
0x180409196  mov     [rsp+1E0h+var_1A0], r13b
0x18040919b  mov     [rsp+1E0h+psfgaoOut], r12; int
0x1804091a0  xor     r9d, r9d; sfgaoIn
0x1804091a3  lea     r8, [rsp+1E0h+ppidl]; ppidl
0x1804091a8  xor     edx, edx; pbc
0x1804091aa  mov     rcx, [rsi+50h]; pszName
0x1804091ae  call    cs:__imp_SHParseDisplayName
0x1804091b4  mov     ebx, eax
0x1804091b6  lea     rcx, [rsp+1E0h+var_1B0]
0x1804091bb  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1804091c0  test    ebx, ebx
0x1804091c2  jns     short loc_180409202
0x1804091c4  mov     rcx, [rbp+0E8h]; this
0x1804091cb  mov     r9d, ebx; char *
0x1804091ce  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x1804091d5  mov     edx, 222h; void *
0x1804091da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804091df  lea     rcx, [rbp+0E0h+lpsz]; void *
0x1804091e3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1804091e8  lea     rcx, [rbp+0E0h+var_B0]
0x1804091ec  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1804091f1  nop
0x1804091f2  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x1804091f7  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1804091fc  nop
0x1804091fd  jmp     loc_18040A0BB
0x180409202  lea     r14, [rsi+88h]
0x180409209  mov     r8, r14; value
0x18040920c  lea     rdx, aFolderscope_0; "FolderScope"
0x180409213  mov     rcx, rdi; propBag
0x180409216  call    cs:__imp_PSPropertyBag_ReadGUID
0x18040921c  mov     ebx, eax
0x18040921e  test    eax, eax
0x180409220  jns     short loc_180409260
0x180409222  mov     rcx, [rbp+0E8h]; this
0x180409229  mov     r9d, eax; char *
0x18040922c  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180409233  mov     edx, 224h; void *
0x180409238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18040923d  lea     rcx, [rbp+0E0h+lpsz]; void *
0x180409241  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180409246  lea     rcx, [rbp+0E0h+var_B0]
0x18040924a  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18040924f  nop
0x180409250  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x180409255  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x18040925a  nop
0x18040925b  jmp     loc_18040A0BB
0x180409260  mov     [rbp+0E0h+var_C8], r12
0x180409264  lea     rax, [rbp+0E0h+var_C8]
0x180409268  mov     [rsp+1E0h+var_1B0], rax
0x18040926d  mov     [rsp+1E0h+ppidl], r12
0x180409272  mov     [rsp+1E0h+var_1A0], r13b
0x180409277  lea     r9, [rsp+1E0h+ppidl]; ppidl
0x18040927c  xor     r8d, r8d; hToken
0x18040927f  mov     edx, 5000h; dwFlags
0x180409284  mov     rcx, r14; rfid
0x180409287  call    cs:__imp_SHGetKnownFolderIDList
0x18040928d  mov     ebx, eax
0x18040928f  lea     rcx, [rsp+1E0h+var_1B0]
0x180409294  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180409299  test    ebx, ebx
0x18040929b  jns     short loc_1804092E6
0x18040929d  mov     rcx, [rbp+0E8h]; this
0x1804092a4  mov     r9d, ebx; char *
0x1804092a7  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x1804092ae  mov     edx, 228h; void *
0x1804092b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1804092b8  xor     edx, edx
0x1804092ba  lea     rcx, [rbp+0E0h+var_C8]
0x1804092be  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1804092c3  lea     rcx, [rbp+0E0h+lpsz]; void *
0x1804092c7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1804092cc  lea     rcx, [rbp+0E0h+var_B0]
0x1804092d0  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1804092d5  nop
0x1804092d6  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
0x1804092db  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1804092e0  nop
0x1804092e1  jmp     loc_18040A0BB
0x1804092e6  lea     rbx, [rsi+58h]
0x1804092ea  mov     rcx, [rbx]
0x1804092ed  mov     [rbx], r12
0x1804092f0  test    rcx, rcx
0x1804092f3  jz      short loc_180409302
0x1804092f5  mov     rax, [rcx]
0x1804092f8  mov     rax, [rax+10h]
0x1804092fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180409301  nop
0x180409302  mov     [rsp+1E0h+psfgaoOut], rbx; int
0x180409307  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18040930e  xor     r8d, r8d; hToken
0x180409311  mov     edx, 5000h; flags
0x180409316  mov     rcx, r14; rfid
0x180409319  call    cs:__imp_SHGetKnownFolderItem
0x18040931f  mov     ebx, eax
0x180409321  test    eax, eax
0x180409323  jns     short loc_18040936E
0x180409325  mov     rcx, [rbp+0E8h]; this
0x18040932c  mov     r9d, eax; char *
0x18040932f  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x180409336  mov     edx, 22Ch; void *
0x18040933b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180409340  xor     edx, edx
0x180409342  lea     rcx, [rbp+0E0h+var_C8]
0x180409346  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18040934b  lea     rcx, [rbp+0E0h+lpsz]; void *
0x18040934f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180409354  lea     rcx, [rbp+0E0h+var_B0]
0x180409358  call    ?reset@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18040935d  nop
0x18040935e  lea     rcx, [rsp+1E0h+var_190]; struct AUTOLISTINIT *
  ... truncated ...
```
