# CPersistedTableRegistryStore::SaveItemInfo(ushort const *,IShellItem *,ushort const *,ushort const *,ulong,Windows::Storage::AccessCache::RecentStorageItemVisibility)

- ea: `0x1801bbc30`
- end: `0x1801bc4cb`
- name: `?SaveItemInfo@CPersistedTableRegistryStore@@UEAAJPEBGPEAUIShellItem@@00KW4RecentStorageItemVisibility@AccessCache@Storage@Windows@@@Z`
- size: `2203`
- prototype: `int __high(const unsigned __int16 *, struct IShellItem *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum Windows::Storage::AccessCache::RecentStorageItemVisibility)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1804a6090`

## callees

- `0x180009fc0`
- `0x1800304e0`
- `0x180038f50`
- `0x18007bbf0`
- `0x18007c1c0`
- `0x18007dcf0`
- `0x1800899a4`
- `0x1800b5d60`
- `0x1800d2374`
- `0x180103290`
- `0x180165124`
- `0x180166ce8`
- `0x1801bbc30`
- `0x1801bc4d4`
- `0x1801bcb80`
- `0x1801bd2a8`
- `0x1801bdab8`
- `0x1801bdfd4`
- `0x1801bdff4`
- `0x1801be7cc`
- `0x1801bebdc`
- `0x1801ff4d0`
- `0x180224bf0`
- `0x180243eb0`
- `0x1802f3df4`
- `0x180311b3c`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bc2c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801bc2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbf64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bc06e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bbf64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bc06e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbe9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbeee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbf05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc00d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbe9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbeee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbf05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bbff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc00d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc160`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801bc475`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801bc475`

## string_xrefs

- `0x1801bc367`: `FilePath`
- `0x1801bbfbd`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bbfda`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc144`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc1db`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc1fb`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc300`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc394`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc3ac`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc3f9`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc411`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc49b`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`
- `0x1801bc4b4`: `onecoreuap\shell\windows.storage\persistedtableregistrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CPersistedTableRegistryStore::SaveItemInfo(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        int a7)
{
  int TableRegKey; // eax
  unsigned int v12; // ebx
  void *v13; // rax
  int LinkFromShellItemWithConditionalLinkTracking; // eax
  __int64 v15; // rax
  __int64 v16; // r8
  void *v17; // rdx
  int ItemStream; // eax
  void *v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int UnaliasedIDList; // eax
  void *v24; // rcx
  int v25; // eax
  ITEMIDLIST *v26; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v27; // rcx
  void *v28; // rdx
  struct IStream *v29; // rcx
  struct IUnknown *v30; // rcx
  int v32; // eax
  ITEMIDLIST *v33; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v34; // rcx
  void *v35; // rdx
  struct IStream *v36; // rcx
  struct IUnknown *v37; // rcx
  int v38; // eax
  __int64 v39; // rdi
  int (__fastcall *v40)(__int64, LPVOID, LPVOID *, _QWORD); // rbx
  LPVOID v41; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v42; // rcx
  void *v43; // rdx
  struct IStream *v44; // rcx
  struct IUnknown *v45; // rcx
  void *v46; // rdx
  struct IStream *v47; // rcx
  struct IUnknown *v48; // rcx
  LPVOID v49; // rdi
  __int64 (__fastcall *v50)(LPVOID, LPCWCH *); // rbx
  int v51; // eax
  wil::details::in1diag3 *v52; // rcx
  __int64 v53; // rdx
  HRESULT v54; // eax
  __int64 v55; // rdx
  __int64 v56; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  struct IStream *pstm; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v62; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v64; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp-98h] BYREF
  __int64 v67; // [rsp+70h] [rbp-90h]
  __int64 v68; // [rsp+78h] [rbp-88h]
  LPVOID v69[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v70[192]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  WinRTStorageTelemetry::WatchCurrentThread(v70, "SaveItemInfo", 0);
  if ( (unsigned int)IsEffectiveLowIL() != 1 )
  {
    v32 = CheckAndReportError(-2147024891);
    v12 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
        (const char *)(unsigned int)v32,
        bIgnoreCase);
      goto LABEL_31;
    }
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  TableRegKey = CPersistedTableRegistryStore::_GetTableRegKey((CPersistedTableRegistryStore *)a1, 0x20006u, &hKey);
  v12 = TableRegKey;
  if ( TableRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)TableRegKey,
      bIgnoreCase);
LABEL_77:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_31;
  }
  v62 = 0;
  pv = (LPVOID)-1LL;
  v13 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 120LL))(*(_QWORD *)(a1 + 24));
  LinkFromShellItemWithConditionalLinkTracking = wil::impersonate_token_nothrow(v13);
  v12 = LinkFromShellItemWithConditionalLinkTracking;
  if ( LinkFromShellItemWithConditionalLinkTracking < 0 )
  {
    v55 = 300;
LABEL_75:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)LinkFromShellItemWithConditionalLinkTracking,
      bIgnoreCase);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&pv);
LABEL_76:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    goto LABEL_77;
  }
  v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v62);
  LinkFromShellItemWithConditionalLinkTracking = _CreateLinkFromShellItemWithConditionalLinkTracking(0, a3, v16, v15);
  v12 = LinkFromShellItemWithConditionalLinkTracking;
  if ( LinkFromShellItemWithConditionalLinkTracking < 0 )
  {
    v55 = 302;
    goto LABEL_75;
  }
  if ( pv != (LPVOID)-1LL )
    wil::details::RevertImpersonateToken(pv, v17);
  pstm = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
  ItemStream = CPersistedTableRegistryStore::GetItemStream(
                 (CPersistedTableRegistryStore *)a1,
                 a2,
                 *(_BYTE *)(a1 + 40) == 0,
                 1u,
                 &pstm);
  v12 = ItemStream;
  if ( ItemStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)ItemStream,
      bIgnoreCasea);
LABEL_82:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pstm);
    goto LABEL_76;
  }
  Token = (HANDLE)-1LL;
  v19 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 120LL))(*(_QWORD *)(a1 + 24));
  v20 = wil::impersonate_token_nothrow(v19);
  v12 = v20;
  if ( v20 < 0 )
  {
    v56 = 314;
LABEL_81:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v56,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCasea);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&Token);
    goto LABEL_82;
  }
  v20 = IUnknown_SaveKnownImplToStream(pstm, (const struct _GUID *const *)&off_180699CC0, 1u, v62);
  v12 = v20;
  if ( v20 < 0 )
  {
    v56 = 316;
    goto LABEL_81;
  }
  v20 = SHRegSetString(hKey, a2, L"Metadata", a4);
  v12 = v20;
  if ( v20 < 0 )
  {
    v56 = 318;
    goto LABEL_81;
  }
  if ( a5 )
  {
    v20 = SHRegSetString(hKey, a2, L"PackageFamilyName", a5);
    v12 = v20;
    if ( v20 < 0 )
    {
      v56 = 319;
      goto LABEL_81;
    }
  }
  v21 = SHRegSetDWORD(hKey, a2, L"Flags", a6);
  v12 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCasea);
    if ( Token != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(Token, v46);
    v47 = pstm;
    if ( pstm )
    {
      pstm = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(struct IUnknown *))v48->lpVtbl->Release)(v48);
    }
    goto LABEL_40;
  }
  v64 = 0;
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, struct _ITEMIDLIST_ABSOLUTE **))v62->lpVtbl[1].AddRef)(v62, &v64);
  v12 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)v22,
      bIgnoreCasea);
    v42 = v64;
    v64 = 0;
    CoTaskMemFree(v42);
    if ( Token != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(Token, v43);
    v44 = pstm;
    if ( pstm )
    {
      pstm = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(struct IUnknown *))v45->lpVtbl->Release)(v45);
    }
    goto LABEL_40;
  }
  if ( !*(_BYTE *)(a1 + 40) )
  {
    v69[0] = 0;
    v69[1] = (LPVOID)-1LL;
    v69[2] = (LPVOID)-1LL;
    v38 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a3 + 40LL))(a3, 2147647488LL, v69);
    if ( v38 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
        (const char *)(unsigned int)v38,
        bIgnoreCasea);
    }
    else if ( *(_QWORD *)(a1 + 32)
           || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 32),
               CoCreateInstance(
                 &CLSID_SyncRootManager,
                 0,
                 1u,
                 &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
                 (LPVOID *)(a1 + 32)) >= 0) )
    {
      pv = 0;
      v39 = *(_QWORD *)(a1 + 32);
      v40 = *(int (__fastcall **)(__int64, LPVOID, LPVOID *, _QWORD))(*(_QWORD *)v39 + 32LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
      bIgnoreCasea = 0;
      if ( v40(v39, v69[0], &pv, 0) < 0 )
        goto LABEL_45;
      lpString1 = 0;
      v67 = 0;
      v68 = 0;
      v49 = pv;
      v50 = *(__int64 (__fastcall **)(LPVOID, LPCWCH *))(*(_QWORD *)pv + 40LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      v67 = -1;
      v68 = -1;
      v51 = v50(v49, &lpString1);
      v52 = retaddr;
      if ( v51 < 0 )
      {
        v53 = 340;
      }
      else
      {
        if ( CompareStringOrdinal(lpString1, -1, L"SkyDrive", -1, 1) != 2 )
          goto LABEL_69;
        v51 = SHRegSetBOOL(hKey, a2, L"Roamable", 1);
        v52 = retaddr;
        if ( v51 >= 0 )
          goto LABEL_69;
        v53 = 341;
      }
      wil::details::in1diag3::_Log_Hr(
        v52,
        (void *)v53,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
        (const char *)(unsigned int)v51,
        bIgnoreCasea);
LABEL_69:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
LABEL_45:
      v41 = pv;
      if ( pv )
      {
        pv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
      }
    }
    if ( v69[0] )
      CoTaskMemFree(v69[0]);
  }
  pidl = 0;
  UnaliasedIDList = GetUnaliasedIDList(v64, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
  if ( UnaliasedIDList < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
      (const char *)(unsigned int)UnaliasedIDList,
      bIgnoreCasea);
  }
  else
  {
    pv = 0;
    if ( (int)RebaseOnVolumeID(pidl, (LPITEMIDLIST *)&pv) >= 0 )
    {
      lpString1 = 0;
      v67 = 0;
      v68 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      v67 = -1;
      v68 = -1;
      v54 = SHGetNameFromIDList((LPCITEMIDLIST)pv, SIGDN_FILESYSPATH, (PWSTR *)&lpString1);
      if ( v54 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
          (const char *)(unsigned int)v54,
          bIgnoreCasea);
      else
        SHRegSetString(hKey, a2, L"FilePath", lpString1);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    }
    v24 = pv;
    pv = 0;
    CoTaskMemFree(v24);
  }
  v25 = SHRegSetBOOL(hKey, a2, L"SystemVisible", a7 == 1);
  v12 = v25;
  if ( v25 >= 0 )
  {
    if ( a7 == 1 )
      CPersistedTableRegistryStore::AddToSystemRecentDocs((CPersistedTableRegistryStore *)a1, v64);
    v26 = (ITEMIDLIST *)pidl;
    pidl = 0;
    CoTaskMemFree(v26);
    v27 = v64;
    v64 = 0;
    CoTaskMemFree(v27);
    if ( Token != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(Token, v28);
    v29 = pstm;
    if ( pstm )
    {
      pstm = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
    }
    if ( hKey )
      RegCloseKey(hKey);
    v12 = 0;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16F,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\persistedtableregistrystore.cpp",
    (const char *)(unsigned int)v25,
    bIgnoreCasea);
  v33 = (ITEMIDLIST *)pidl;
  pidl = 0;
  CoTaskMemFree(v33);
  v34 = v64;
  v64 = 0;
  CoTaskMemFree(v34);
  if ( Token != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(Token, v35);
  v36 = pstm;
  if ( pstm )
  {
    pstm = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v62;
  if ( v62 )
  {
    v62 = 0;
    ((void (__fastcall *)(struct IUnknown *))v37->lpVtbl->Release)(v37);
  }
LABEL_40:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_31:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v70);
  return v12;
}

```

## disassembly

```asm
0x1801bbc30  push    rbp
0x1801bbc32  push    rbx
0x1801bbc33  push    rsi
0x1801bbc34  push    rdi
0x1801bbc35  push    r12
0x1801bbc37  push    r13
0x1801bbc39  push    r14
0x1801bbc3b  push    r15
0x1801bbc3d  lea     rbp, [rsp-78h]
0x1801bbc42  sub     rsp, 178h
0x1801bbc49  mov     rax, cs:__security_cookie
0x1801bbc50  xor     rax, rsp
0x1801bbc53  mov     [rbp+0B0h+var_50], rax
0x1801bbc57  mov     r12, r9
0x1801bbc5a  mov     r15, r8
0x1801bbc5d  mov     r14, rdx
0x1801bbc60  mov     rsi, rcx
0x1801bbc63  mov     rdi, [rbp+0B0h+arg_20]
0x1801bbc6a  xor     r8d, r8d
0x1801bbc6d  lea     rdx, aSaveiteminfo; "SaveItemInfo"
0x1801bbc74  lea     rcx, [rbp+0B0h+var_110]
0x1801bbc78  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_N@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool)
0x1801bbc7d  nop
0x1801bbc7e  call    ?IsEffectiveLowIL@@YAJXZ; IsEffectiveLowIL(void)
0x1801bbc83  xor     r13d, r13d
0x1801bbc86  cmp     eax, 1
0x1801bbc89  jnz     loc_1801BBF9F
0x1801bbc8f  mov     [rsp+1B0h+hKey], r13
0x1801bbc94  xor     edx, edx
0x1801bbc96  lea     rcx, [rsp+1B0h+hKey]
0x1801bbc9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801bbca0  lea     r8, [rsp+1B0h+hKey]; HKEY *
0x1801bbca5  mov     edx, 20006h; unsigned int
0x1801bbcaa  mov     rcx, rsi; this
0x1801bbcad  call    ?_GetTableRegKey@CPersistedTableRegistryStore@@AEAAJKPEAPEAUHKEY__@@@Z; CPersistedTableRegistryStore::_GetTableRegKey(ulong,HKEY__ * *)
0x1801bbcb2  mov     ebx, eax
0x1801bbcb4  test    eax, eax
0x1801bbcb6  js      loc_1801BC38A
0x1801bbcbc  mov     [rsp+1B0h+var_168], r13
0x1801bbcc1  mov     [rsp+1B0h+pv], 0FFFFFFFFFFFFFFFFh
0x1801bbcca  mov     rcx, [rsi+18h]
0x1801bbcce  mov     rax, [rcx]
0x1801bbcd1  mov     rax, [rax+78h]
0x1801bbcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbcda  mov     rcx, rax; Token
0x1801bbcdd  lea     rdx, [rsp+1B0h+pv]
0x1801bbce2  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1801bbce7  mov     ebx, eax
0x1801bbce9  test    eax, eax
0x1801bbceb  js      loc_1801BC3A7
0x1801bbcf1  lea     rcx, [rsp+1B0h+var_168]
0x1801bbcf6  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x1801bbcfb  mov     r9, rax
0x1801bbcfe  mov     rdx, r15
0x1801bbd01  xor     ecx, ecx
0x1801bbd03  call    ?_CreateLinkFromShellItemWithConditionalLinkTracking@@YAJW4CLFITFLAGS@@PEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; _CreateLinkFromShellItemWithConditionalLinkTracking(CLFITFLAGS,IShellItem *,_GUID const &,void * *)
0x1801bbd08  mov     ebx, eax
0x1801bbd0a  test    eax, eax
0x1801bbd0c  js      loc_1801BC3E8
0x1801bbd12  mov     rcx, [rsp+1B0h+pv]; Token
0x1801bbd17  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801bbd1b  jz      short loc_1801BBD22
0x1801bbd1d  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bbd22  mov     [rsp+1B0h+pstm], r13
0x1801bbd27  lea     rcx, [rsp+1B0h+pstm]
0x1801bbd2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bbd31  mov     r8d, r13d
0x1801bbd34  cmp     [rsi+28h], r13b
0x1801bbd38  setz    r8b; int
0x1801bbd3c  lea     rax, [rsp+1B0h+pstm]
0x1801bbd41  mov     qword ptr [rsp+1B0h+bIgnoreCase], rax; int
0x1801bbd46  mov     r9d, 1; unsigned int
0x1801bbd4c  mov     rdx, r14; unsigned __int16 *
0x1801bbd4f  mov     rcx, rsi; this
0x1801bbd52  call    ?GetItemStream@CPersistedTableRegistryStore@@UEAAJPEBGHKPEAPEAUIStream@@@Z; CPersistedTableRegistryStore::GetItemStream(ushort const *,int,ulong,IStream * *)
0x1801bbd57  mov     ebx, eax
0x1801bbd59  test    eax, eax
0x1801bbd5b  js      loc_1801BC3EF
0x1801bbd61  mov     [rsp+1B0h+Token], 0FFFFFFFFFFFFFFFFh
0x1801bbd6a  mov     rcx, [rsi+18h]
0x1801bbd6e  mov     rax, [rcx]
0x1801bbd71  mov     rax, [rax+78h]
0x1801bbd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbd7a  mov     rcx, rax; Token
0x1801bbd7d  lea     rdx, [rsp+1B0h+Token]
0x1801bbd82  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1801bbd87  mov     ebx, eax
0x1801bbd89  test    eax, eax
0x1801bbd8b  js      loc_1801BC40C
0x1801bbd91  mov     r9, [rsp+1B0h+var_168]; struct IUnknown *
0x1801bbd96  mov     r8d, 1; unsigned int
0x1801bbd9c  lea     rdx, off_180699CC0; struct _GUID **
0x1801bbda3  mov     rcx, [rsp+1B0h+pstm]; pstm
0x1801bbda8  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1801bbdad  mov     ebx, eax
0x1801bbdaf  test    eax, eax
0x1801bbdb1  js      loc_1801BC43F
0x1801bbdb7  mov     r9, r12; unsigned __int16 *
0x1801bbdba  lea     r8, aMetadata; "Metadata"
0x1801bbdc1  mov     rdx, r14; unsigned __int16 *
0x1801bbdc4  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801bbdc9  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801bbdce  mov     ebx, eax
0x1801bbdd0  test    eax, eax
0x1801bbdd2  js      loc_1801BC446
0x1801bbdd8  test    rdi, rdi
0x1801bbddb  jz      short loc_1801BBDFE
0x1801bbddd  mov     r9, rdi; unsigned __int16 *
0x1801bbde0  lea     r8, aPackagefamilyn_0; "PackageFamilyName"
0x1801bbde7  mov     rdx, r14; unsigned __int16 *
0x1801bbdea  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801bbdef  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801bbdf4  mov     ebx, eax
0x1801bbdf6  test    eax, eax
0x1801bbdf8  js      loc_1801BC44D
0x1801bbdfe  mov     r9d, [rbp+0B0h+arg_28]; unsigned int
0x1801bbe05  lea     r8, aFlags; "Flags"
0x1801bbe0c  mov     rdx, r14; unsigned __int16 *
0x1801bbe0f  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801bbe14  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801bbe19  mov     ebx, eax
0x1801bbe1b  test    eax, eax
0x1801bbe1d  js      loc_1801BC1F1
0x1801bbe23  mov     [rsp+1B0h+var_158], r13
0x1801bbe28  mov     rcx, [rsp+1B0h+var_168]
0x1801bbe2d  mov     rax, [rcx]
0x1801bbe30  lea     rdx, [rsp+1B0h+var_158]
0x1801bbe35  mov     rax, [rax+20h]
0x1801bbe39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbe3e  mov     ebx, eax
0x1801bbe40  test    eax, eax
0x1801bbe42  js      loc_1801BC13A
0x1801bbe48  cmp     [rsi+28h], r13b
0x1801bbe4c  jz      loc_1801BC07F
0x1801bbe52  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801bbe56  mov     [rsp+1B0h+pidl], r13
0x1801bbe5b  lea     rdx, [rsp+1B0h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1801bbe60  mov     rcx, [rsp+1B0h+var_158]; struct _ITEMIDLIST_ABSOLUTE *
0x1801bbe65  call    ?GetUnaliasedIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; GetUnaliasedIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1801bbe6a  mov     rcx, [rbp+0B8h]; this
0x1801bbe71  test    eax, eax
0x1801bbe73  js      loc_1801BC498
0x1801bbe79  mov     [rsp+1B0h+pv], r13
0x1801bbe7e  lea     rdx, [rsp+1B0h+pv]; ppidl
0x1801bbe83  mov     rcx, [rsp+1B0h+pidl]; pidl
0x1801bbe88  call    RebaseOnVolumeID
0x1801bbe8d  test    eax, eax
0x1801bbe8f  jns     loc_1801BC31C
0x1801bbe95  mov     rcx, [rsp+1B0h+pv]; pv
0x1801bbe9a  mov     [rsp+1B0h+pv], r13
0x1801bbe9f  call    cs:__imp_CoTaskMemFree
0x1801bbea6  nop     dword ptr [rax+rax+00h]
0x1801bbeab  mov     r9d, r13d
0x1801bbeae  cmp     [rbp+0B0h+arg_30], 1
0x1801bbeb5  setz    r9b; int
0x1801bbeb9  lea     r8, aSystemvisible; "SystemVisible"
0x1801bbec0  mov     rdx, r14; unsigned __int16 *
0x1801bbec3  mov     rcx, [rsp+1B0h+hKey]; HKEY
0x1801bbec8  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1801bbecd  mov     ebx, eax
0x1801bbecf  test    eax, eax
0x1801bbed1  js      loc_1801BBFD0
0x1801bbed7  cmp     [rbp+0B0h+arg_30], 1
0x1801bbede  jz      loc_1801BC1BF
0x1801bbee4  mov     rcx, [rsp+1B0h+pidl]; pv
0x1801bbee9  mov     [rsp+1B0h+pidl], r13
0x1801bbeee  call    cs:__imp_CoTaskMemFree
0x1801bbef5  nop     dword ptr [rax+rax+00h]
0x1801bbefa  nop
0x1801bbefb  mov     rcx, [rsp+1B0h+var_158]; pv
0x1801bbf00  mov     [rsp+1B0h+var_158], r13
0x1801bbf05  call    cs:__imp_CoTaskMemFree
0x1801bbf0c  nop     dword ptr [rax+rax+00h]
0x1801bbf11  nop
0x1801bbf12  mov     rcx, [rsp+1B0h+Token]; Token
0x1801bbf17  cmp     rcx, r12
0x1801bbf1a  jz      short loc_1801BBF22
0x1801bbf1c  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1801bbf21  nop
0x1801bbf22  mov     rcx, [rsp+1B0h+pstm]
0x1801bbf27  test    rcx, rcx
0x1801bbf2a  jz      short loc_1801BBF3E
0x1801bbf2c  mov     [rsp+1B0h+pstm], r13
0x1801bbf31  mov     rax, [rcx]
0x1801bbf34  mov     rax, [rax+10h]
0x1801bbf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbf3d  nop
0x1801bbf3e  mov     rcx, [rsp+1B0h+var_168]
0x1801bbf43  test    rcx, rcx
0x1801bbf46  jz      short loc_1801BBF5A
0x1801bbf48  mov     [rsp+1B0h+var_168], r13
0x1801bbf4d  mov     rax, [rcx]
0x1801bbf50  mov     rax, [rax+10h]
0x1801bbf54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbf59  nop
0x1801bbf5a  mov     rcx, [rsp+1B0h+hKey]; hKey
0x1801bbf5f  test    rcx, rcx
0x1801bbf62  jz      short loc_1801BBF70
0x1801bbf64  call    cs:__imp_RegCloseKey
0x1801bbf6b  nop     dword ptr [rax+rax+00h]
0x1801bbf70  mov     ebx, r13d
0x1801bbf73  lea     rcx, [rbp+0B0h+var_110]; this
0x1801bbf77  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x1801bbf7c  mov     eax, ebx
0x1801bbf7e  mov     rcx, [rbp+0B0h+var_50]
0x1801bbf82  xor     rcx, rsp; StackCookie
0x1801bbf85  call    __security_check_cookie
0x1801bbf8a  add     rsp, 178h
0x1801bbf91  pop     r15
0x1801bbf93  pop     r14
0x1801bbf95  pop     r13
0x1801bbf97  pop     r12
0x1801bbf99  pop     rdi
0x1801bbf9a  pop     rsi
0x1801bbf9b  pop     rbx
0x1801bbf9c  pop     rbp
0x1801bbf9d  retn
0x1801bbf9f  mov     ecx, 80070005h; int
0x1801bbfa4  call    ?CheckAndReportError@@YAJJ@Z; CheckAndReportError(long)
0x1801bbfa9  mov     ebx, eax
0x1801bbfab  test    eax, eax
0x1801bbfad  jns     loc_1801BBC8F
0x1801bbfb3  mov     rcx, [rbp+0B8h]; this
0x1801bbfba  mov     r9d, eax; char *
0x1801bbfbd  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bbfc4  mov     edx, 122h; void *
0x1801bbfc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bbfce  jmp     short loc_1801BBF73
0x1801bbfd0  mov     rcx, [rbp+0B8h]; this
0x1801bbfd7  mov     r9d, eax; char *
0x1801bbfda  lea     r8, aOnecoreuapShel_45; "onecoreuap\\shell\\windows.storage\\per"...
0x1801bbfe1  mov     edx, 16Fh; void *
0x1801bbfe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bbfeb  nop
0x1801bbfec  mov     rcx, [rsp+1B0h+pidl]; pv
0x1801bbff1  mov     [rsp+1B0h+pidl], r13
0x1801bbff6  call    cs:__imp_CoTaskMemFree
0x1801bbffd  nop     dword ptr [rax+rax+00h]
0x1801bc002  nop
0x1801bc003  mov     rcx, [rsp+1B0h+var_158]; pv
0x1801bc008  mov     [rsp+1B0h+var_158], r13
0x1801bc00d  call    cs:__imp_CoTaskMemFree
0x1801bc014  nop     dword ptr [rax+rax+00h]
0x1801bc019  nop
0x1801bc01a  mov     rcx, [rsp+1B0h+Token]; Token
0x1801bc01f  cmp     rcx, r12
0x1801bc022  jnz     loc_1801BC1B5
0x1801bc028  mov     rcx, [rsp+1B0h+pstm]
0x1801bc02d  test    rcx, rcx
0x1801bc030  jz      short loc_1801BC044
0x1801bc032  mov     [rsp+1B0h+pstm], r13
0x1801bc037  mov     rax, [rcx]
0x1801bc03a  mov     rax, [rax+10h]
0x1801bc03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc043  nop
0x1801bc044  mov     rcx, [rsp+1B0h+var_168]
0x1801bc049  test    rcx, rcx
0x1801bc04c  jz      short loc_1801BC060
0x1801bc04e  mov     [rsp+1B0h+var_168], r13
0x1801bc053  mov     rax, [rcx]
0x1801bc056  mov     rax, [rax+10h]
0x1801bc05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc05f  nop
0x1801bc060  mov     rcx, [rsp+1B0h+hKey]; hKey
0x1801bc065  test    rcx, rcx
0x1801bc068  jz      loc_1801BBF73
0x1801bc06e  call    cs:__imp_RegCloseKey
0x1801bc075  nop     dword ptr [rax+rax+00h]
0x1801bc07a  jmp     loc_1801BBF73
0x1801bc07f  mov     [rbp+0B0h+var_130], r13
0x1801bc083  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801bc087  mov     [rbp+0B0h+var_128], r12
0x1801bc08b  mov     [rbp+0B0h+var_120], r12
0x1801bc08f  mov     rax, [r15]
0x1801bc092  lea     r8, [rbp+0B0h+var_130]
0x1801bc096  mov     edx, 80028000h
0x1801bc09b  mov     rcx, r15
0x1801bc09e  mov     rax, [rax+28h]
0x1801bc0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc0a7  mov     rcx, [rbp+0B8h]; this
0x1801bc0ae  test    eax, eax
0x1801bc0b0  js      loc_1801BC1D8
0x1801bc0b6  lea     rdi, [rsi+20h]
0x1801bc0ba  cmp     [rdi], r13
0x1801bc0bd  jz      loc_1801BC454
0x1801bc0c3  mov     [rsp+1B0h+pv], r13
0x1801bc0c8  mov     rdi, [rdi]
0x1801bc0cb  mov     rax, [rdi]
0x1801bc0ce  mov     rbx, [rax+20h]
0x1801bc0d2  lea     rcx, [rsp+1B0h+pv]
0x1801bc0d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801bc0dc  mov     qword ptr [rsp+1B0h+bIgnoreCase], r13
0x1801bc0e1  xor     r9d, r9d
0x1801bc0e4  lea     r8, [rsp+1B0h+pv]
0x1801bc0e9  mov     rdx, [rbp+0B0h+var_130]
0x1801bc0ed  mov     rcx, rdi
0x1801bc0f0  mov     rax, rbx
0x1801bc0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc0f8  test    eax, eax
0x1801bc0fa  jns     loc_1801BC25C
  ... truncated ...
```
