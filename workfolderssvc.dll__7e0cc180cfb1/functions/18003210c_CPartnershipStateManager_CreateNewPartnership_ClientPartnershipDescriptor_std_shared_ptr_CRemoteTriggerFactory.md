# CPartnershipStateManager::CreateNewPartnership(ClientPartnershipDescriptor &,std::shared_ptr<CRemoteTriggerFactory> &,std::shared_ptr<ILocalChangeWatcherFactory> &,std::shared_ptr<void> &,std::shared_ptr<IPartnershipPersister> &,std::shared_ptr<CSyncEngineRunner> &,IFileDownloadManager *,IUserCredentialProvider *,IDiscoveryProvider *,ISyncShareManagerProgressCallback *)

- ea: `0x18003210c`
- end: `0x180032f6a`
- name: `?CreateNewPartnership@CPartnershipStateManager@@SAPEAV1@AEAVClientPartnershipDescriptor@@AEAV?$shared_ptr@VCRemoteTriggerFactory@@@std@@AEAV?$shared_ptr@VILocalChangeWatcherFactory@@@4@AEAV?$shared_ptr@X@4@AEAV?$shared_ptr@VIPartnershipPersister@@@4@AEAV?$shared_ptr@VCSyncEngineRunner@@@4@PEAUIFileDownloadManager@@PEAVIUserCredentialProvider@@PEAVIDiscoveryProvider@@PEAUISyncShareManagerProgressCallback@@@Z`
- size: `3678`
- prototype: `__int64 __fastcall(struct ClientPartnershipDescriptor *, _QWORD *, _QWORD *, HANDLE *, _QWORD *, CSyncEngineRunner **, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037710`

## callees

- `0x180002ab0`
- `0x180002fa4`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180010f40`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180014a94`
- `0x1800158d4`
- `0x180023c90`
- `0x180027bf4`
- `0x18002dad0`
- `0x180030f44`
- `0x18003191c`
- `0x18003210c`
- `0x180033a2c`
- `0x18004100c`
- `0x180041738`
- `0x1800431d8`
- `0x18004369c`
- `0x1800c71d8`
- `0x1800c72b4`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032c40`
- `KERNEL32!GetLastError` at `0x180032c40`
- `ADVAPI32!DecryptFileW` at `0x180032c1e`
- `ADVAPI32!DecryptFileW` at `0x180032c1e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003250d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003250d`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800323f5`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800323f5`

## string_xrefs

- `0x180032234`: `CPartnershipStateManager::CreateNewPartnership`

## pseudocode

```c
__int64 __fastcall CPartnershipStateManager::CreateNewPartnership(
        struct ClientPartnershipDescriptor *a1,
        _QWORD *a2,
        _QWORD *a3,
        HANDLE *a4,
        _QWORD *a5,
        CSyncEngineRunner **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  struct ClientPartnershipDescriptor *v12; // r14
  _BYTE *v13; // rax
  char v14; // al
  _QWORD *v15; // r13
  const WCHAR *v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 StagingLocation; // rax
  __int64 v20; // r8
  __int64 StagingDownloadLocation; // rax
  HRESULT Guid; // eax
  __int64 v23; // r10
  void (__fastcall *v24)(__int64, _QWORD *, char *, WCHAR *, const wchar_t *, HANDLE *, char *, char *); // r11
  _QWORD *v25; // r15
  _QWORD *v26; // rdx
  _QWORD *v27; // rdx
  int v28; // r12d
  __int64 v29; // r13
  _QWORD *v30; // rax
  __int64 v31; // rdi
  __int64; // rax
  char v33; // si
  _QWORD *v34; // rdx
  _QWORD *v35; // r9
  const unsigned __int16 *v36; // r14
  const WCHAR *v37; // rcx
  PVOID *v38; // rcx
  char LastError; // al
  const WCHAR *v40; // r9
  const unsigned __int16 *v41; // rdx
  int v42; // [rsp+60h] [rbp-3D8h] BYREF
  int v43; // [rsp+64h] [rbp-3D4h]
  char v44; // [rsp+68h] [rbp-3D0h]
  const char *v45; // [rsp+70h] [rbp-3C8h]
  __int64 v46; // [rsp+78h] [rbp-3C0h]
  char v47; // [rsp+80h] [rbp-3B8h]
  char v48; // [rsp+81h] [rbp-3B7h]
  char v49; // [rsp+82h] [rbp-3B6h]
  char v50; // [rsp+83h] [rbp-3B5h]
  char v51; // [rsp+84h] [rbp-3B4h]
  struct ClientPartnershipDescriptor *v52; // [rsp+90h] [rbp-3A8h]
  HANDLE *v53; // [rsp+A0h] [rbp-398h]
  _QWORD *v54; // [rsp+A8h] [rbp-390h]
  CSyncEngineRunner **v55; // [rsp+B0h] [rbp-388h]
  _QWORD *v56; // [rsp+B8h] [rbp-380h]
  _QWORD *v57; // [rsp+C0h] [rbp-378h]
  int pExceptionObject; // [rsp+C8h] [rbp-370h] BYREF
  int v59; // [rsp+CCh] [rbp-36Ch] BYREF
  int v60; // [rsp+D0h] [rbp-368h] BYREF
  int v61; // [rsp+D4h] [rbp-364h] BYREF
  int v62; // [rsp+D8h] [rbp-360h] BYREF
  int v63; // [rsp+DCh] [rbp-35Ch] BYREF
  int v64; // [rsp+E0h] [rbp-358h] BYREF
  int v65; // [rsp+E4h] [rbp-354h] BYREF
  int LastFailureAsHRESULT; // [rsp+E8h] [rbp-350h] BYREF
  HRESULT v67; // [rsp+ECh] [rbp-34Ch] BYREF
  int v68; // [rsp+F0h] [rbp-348h] BYREF
  __int64 v69; // [rsp+F8h] [rbp-340h] BYREF
  HANDLE *v70; // [rsp+100h] [rbp-338h]
  __int64 v71; // [rsp+108h] [rbp-330h]
  __int64 v72; // [rsp+110h] [rbp-328h]
  _QWORD *v73; // [rsp+118h] [rbp-320h]
  _QWORD *v74; // [rsp+120h] [rbp-318h]
  int v75; // [rsp+128h] [rbp-310h] BYREF
  int v76; // [rsp+12Ch] [rbp-30Ch] BYREF
  int v77; // [rsp+130h] [rbp-308h] BYREF
  int v78; // [rsp+134h] [rbp-304h] BYREF
  int v79; // [rsp+138h] [rbp-300h] BYREF
  int v80; // [rsp+13Ch] [rbp-2FCh] BYREF
  _QWORD *v81; // [rsp+140h] [rbp-2F8h]
  __int64 v82; // [rsp+148h] [rbp-2F0h]
  __int64 v83; // [rsp+150h] [rbp-2E8h]
  int v84; // [rsp+158h] [rbp-2E0h] BYREF
  const ATL::CAtlException *v85; // [rsp+160h] [rbp-2D8h] BYREF
  const ATL::CAtlException *v86; // [rsp+168h] [rbp-2D0h] BYREF
  const ATL::CAtlException *v87; // [rsp+170h] [rbp-2C8h] BYREF
  const ATL::CAtlException *v88; // [rsp+178h] [rbp-2C0h] BYREF
  const ATL::CAtlException *v89; // [rsp+180h] [rbp-2B8h] BYREF
  const ATL::CAtlException *v90; // [rsp+188h] [rbp-2B0h] BYREF
  const ATL::CAtlException *v91; // [rsp+190h] [rbp-2A8h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+198h] [rbp-2A0h] BYREF
  __int64 v93; // [rsp+1A8h] [rbp-290h]
  unsigned __int64 v94; // [rsp+1B0h] [rbp-288h]
  _BYTE v95[40]; // [rsp+1B8h] [rbp-280h] BYREF
  WCHAR Dest; // [rsp+1E0h] [rbp-258h] BYREF
  _BYTE v97[526]; // [rsp+1E2h] [rbp-256h] BYREF

  v70 = a4;
  v74 = a3;
  v12 = a1;
  v52 = a1;
  v73 = a2;
  v54 = a3;
  v53 = a4;
  v56 = a5;
  v55 = a6;
  v72 = a7;
  v83 = a8;
  v71 = a9;
  v82 = a10;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
  }
  if ( (v13[68] & 8) != 0 && v13[65] >= 6u )
  {
    v14 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v14 = 0;
LABEL_9:
  v42 = 0;
  v43 = 216;
  v44 = v14;
  v45 = "CPartnershipStateManager::CreateNewPartnership";
  v46 = 0;
  if ( !*v73 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 218;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v43) = 218;
  v42 = 0;
  if ( !*a3 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 219;
    v59 = -2147024809;
    throw (long *)&v59;
  }
  LOWORD(v43) = 219;
  v42 = 0;
  if ( !*a4 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 220;
    v60 = -2147024809;
    throw (long *)&v60;
  }
  LOWORD(v43) = 220;
  v42 = 0;
  if ( !*v56 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 221;
    v61 = -2147024809;
    throw (long *)&v61;
  }
  LOWORD(v43) = 221;
  v42 = 0;
  if ( !*v55 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 222;
    v62 = -2147024809;
    throw (long *)&v62;
  }
  LOWORD(v43) = 222;
  v42 = 0;
  if ( !v72 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 223;
    v63 = -2147024809;
    throw (long *)&v63;
  }
  LOWORD(v43) = 223;
  v42 = 0;
  if ( !v71 )
  {
    v42 = -2147024809;
    HIWORD(v43) = 224;
    v64 = -2147024809;
    throw (long *)&v64;
  }
  v42 = 0;
  LOWORD(v43) = 224;
  if ( *((_DWORD *)v12 + 90) != 1 )
  {
    v42 = -2147467263;
    HIWORD(v43) = 229;
    v65 = -2147467263;
    throw (long *)&v65;
  }
  v51 = 0;
  v49 = 0;
  v48 = 0;
  v50 = 0;
  v47 = 0;
  *(_OWORD *)lpSrc = 0;
  v93 = 0;
  v94 = 7;
  LOWORD(lpSrc[0]) = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v15 = (_QWORD *)((char *)v12 + 40);
    std::wstring::operator=(lpSrc, (char *)v12 + 40);
    Dest = 0;
    memset_0(v97, 0, 0x206u);
    v16 = (const WCHAR *)lpSrc;
    if ( v94 > 7 )
      v16 = lpSrc[0];
    if ( !ExpandEnvironmentStringsForUserW(*a4, v16, &Dest, 0x104u) )
    {
      HIWORD(v43) = 252;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    v42 = 0;
    LOWORD(v43) = 252;
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)&v97[2 * v17 - 2] );
    std::wstring::_Assign<unsigned short>((char *)v12 + 40, &Dest);
    LOBYTE(v18) = 1;
    StagingLocation = CStagingLocationConfig::GetStagingLocation(v95, &Dest, v18);
    std::wstring::operator=((char *)v12 + 72, StagingLocation);
    std::wstring::_Tidy_deallocate(v95);
    LOBYTE(v20) = 1;
    StagingDownloadLocation = CStagingLocationConfig::GetStagingDownloadLocation(v95, &Dest, v20);
    std::wstring::operator=((char *)v12 + 104, StagingDownloadLocation);
    std::wstring::_Tidy_deallocate(v95);
    CSyncStateManager::ValidateSyncFolder(&Dest, *(_ULARGE_INTEGER *)((char *)v12 + 408), *((_BYTE *)v12 + 380), 0);
    CSyncEngineRunner::CreatePartnership(*v55, v12);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
    }
    v51 = 1;
    Guid = CoCreateGuid((GUID *)((char *)v12 + 328));
    v42 = Guid;
    if ( Guid < 0 )
    {
      HIWORD(v43) = 275;
      v67 = Guid;
      throw (long *)&v67;
    }
    LOWORD(v43) = 275;
    v23 = *a3;
    v24 = *(void (__fastcall **)(__int64, _QWORD *, char *, WCHAR *, const wchar_t *, HANDLE *, char *, char *))(*(_QWORD *)*a3 + 16LL);
    v25 = (_QWORD *)((char *)v12 + 416);
    v57 = (_QWORD *)((char *)v12 + 416);
    v81 = (_QWORD *)((char *)v12 + 440);
    if ( *((_QWORD *)v12 + 55) <= 7u )
      v26 = (_QWORD *)((char *)v12 + 416);
    else
      v26 = (_QWORD *)*v25;
    v24(
      v23,
      v26,
      (char *)v12 + 328,
      &Dest,
      L"\\\\desktop.ini$|\\\\thumbs.db$|\\\\ehthumbs.db$|\\\\~\\$[^\\\\]*$|\\.laccdb$|\\.tmp$|\\\\635D02A9D91C401B97884B82"
       "B3BCDAEA\\.[^\\\\]*$",
      v70,
      (char *)v12 + 384,
      (char *)v12 + 394);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
    }
    v49 = 1;
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      v27 = (_QWORD *)((char *)v12 + 40);
      if ( *((_QWORD *)v12 + 8) > 7u )
        v27 = (_QWORD *)*v15;
      v28 = (int)v74;
      (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v74 + 32LL))(*v74, v27);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        if ( *((_QWORD *)v12 + 8) > 7u )
          v15 = (_QWORD *)*v15;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids, v15);
      }
      v50 = 1;
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &long `RTTI Type Descriptor', (long *)&v84) )
      {
        v42 = v84;
        v25 = v57;
        v29 = (__int64)v53;
        v28 = (int)v54;
        v12 = v52;
        __eh34_try_continuation(1, &long `RTTI Type Descriptor', &loc_180032665);
        goto LABEL_46;
      }
      if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        HIWORD(v43) = 294;
        v42 = -2147024882;
        v25 = v57;
        v29 = (__int64)v53;
        v28 = (int)v54;
        v12 = v52;
        __eh34_try_continuation(1, &std::bad_alloc `RTTI Type Descriptor', &loc_18003289C);
        goto LABEL_46;
      }
      if ( __eh34_catch_type(1, &std::exception `RTTI Type Descriptor', 0) )
      {
        HIWORD(v43) = 294;
        v42 = -2147418113;
        v25 = v57;
        v29 = (__int64)v53;
        v28 = (int)v54;
        v12 = v52;
        __eh34_try_continuation(1, &std::exception `RTTI Type Descriptor', &loc_1800328A1);
        goto LABEL_46;
      }
      if ( __eh34_catch_type(1, &ATL::CAtlException `RTTI Type Descriptor', &v85) )
      {
        HIWORD(v43) = 294;
        v42 = *(_DWORD *)v85;
        v25 = v57;
        v29 = (__int64)v53;
        v28 = (int)v54;
        v12 = v52;
        __eh34_try_continuation(1, &ATL::CAtlException `RTTI Type Descriptor', &loc_180032665);
        goto LABEL_46;
      }
    }
    v29 = (__int64)v70;
LABEL_46:
    if ( v42 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
      }
      v42 = 0;
    }
    (**(void (__fastcall ***)(_QWORD, struct ClientPartnershipDescriptor *))*v56)(*v56, v12);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
    }
    v48 = 1;
    CCloudFilesManager::RegisterSyncRoot(v12);
    v47 = 1;
    v30 = operator new(0x120u);
    v74 = v30;
    if ( *v81 > 7u )
      v25 = (_QWORD *)*v25;
    v69 = CPartnershipStateManager::CPartnershipStateManager(
            (int)v30,
            (int)v25,
            (int)v73,
            v28,
            v29,
            (__int64)v56,
            (__int64)v55,
            v72,
            v83,
            v71,
            v82);
    CPartnershipStateManager::LogPartnershipTelemetry(v12, 1u);
    v31 = v69;
    v69 = 0;
    std::unique_ptr<CPartnershipStateManager>::~unique_ptr<CPartnershipStateManager>(&v69);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v76) )
    {
      v42 = v76;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18003280A);
LABEL_60:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
      }
      LODWORD(v53) = v42;
      v42 = 0;
      if ( __eh34_try(-1, 4) )
      {
        __eh34_scope_strut(4);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        CCloudFilesManager::UnregisterSyncRoot(v52);
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_type(4, &long `RTTI Type Descriptor', (long *)&v75) )
        {
          v42 = v75;
          __eh34_try_continuation(4, &long `RTTI Type Descriptor', &loc_1800328B0);
          goto LABEL_70;
        }
        if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 342;
          v42 = -2147024882;
          __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_18003294E);
          goto LABEL_70;
        }
        if ( __eh34_catch_type(4, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 342;
          v42 = -2147418113;
          __eh34_try_continuation(4, &std::exception `RTTI Type Descriptor', &loc_180032953);
          goto LABEL_70;
        }
        if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', &v87) )
        {
          HIWORD(v43) = 342;
          v42 = *(_DWORD *)v87;
          __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800328B0);
        }
      }
LABEL_70:
      if ( v42 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v42 = 0;
      }
      if ( __eh34_try(-1, 6) )
      {
        __eh34_scope_strut(6);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v33 = 1;
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v56 + 8LL))(*v56);
      }
      if ( __eh34_catch(6) )
      {
        if ( __eh34_catch_type(6, &long `RTTI Type Descriptor', (long *)&v80) )
        {
          v42 = v80;
          v33 = 1;
          __eh34_try_continuation(6, &long `RTTI Type Descriptor', &loc_180032980);
          goto LABEL_81;
        }
        if ( __eh34_catch_type(6, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 358;
          v42 = -2147024882;
          v33 = 1;
          __eh34_try_continuation(6, &std::bad_alloc `RTTI Type Descriptor', &loc_1800329C9);
          goto LABEL_81;
        }
        if ( __eh34_catch_type(6, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 358;
          v42 = -2147418113;
          v33 = 1;
          __eh34_try_continuation(6, &std::exception `RTTI Type Descriptor', &loc_1800329CB);
          goto LABEL_81;
        }
        if ( __eh34_catch_type(6, &ATL::CAtlException `RTTI Type Descriptor', &v88) )
        {
          HIWORD(v43) = 358;
          v42 = *(_DWORD *)v88;
          v33 = 1;
          __eh34_try_continuation(6, &ATL::CAtlException `RTTI Type Descriptor', &loc_180032980);
        }
      }
LABEL_81:
      if ( v42 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v42 = 0;
      }
      if ( __eh34_try(-1, 8) )
      {
        __eh34_scope_strut(8);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v34 = (_QWORD *)((char *)v52 + 416);
        if ( *((_QWORD *)v52 + 55) > 7u )
          v34 = (_QWORD *)*v34;
        (*(void (__fastcall **)(_QWORD, _QWORD *, char *))(*(_QWORD *)*v54 + 24LL))(*v54, v34, (char *)v52 + 328);
      }
      if ( __eh34_catch(8) )
      {
        if ( __eh34_catch_type(8, &long `RTTI Type Descriptor', (long *)&v79) )
        {
          v42 = v79;
          v33 = 1;
          __eh34_try_continuation(8, &long `RTTI Type Descriptor', &loc_180032A86);
          goto LABEL_94;
        }
        if ( __eh34_catch_type(8, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 378;
          v42 = -2147024882;
          v33 = 1;
          __eh34_try_continuation(8, &std::bad_alloc `RTTI Type Descriptor', &loc_180032B0A);
          goto LABEL_94;
        }
        if ( __eh34_catch_type(8, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 378;
          v42 = -2147418113;
          v33 = 1;
          __eh34_try_continuation(8, &std::exception `RTTI Type Descriptor', &loc_180032B0F);
          goto LABEL_94;
        }
        if ( __eh34_catch_type(8, &ATL::CAtlException `RTTI Type Descriptor', &v89) )
        {
          HIWORD(v43) = 378;
          v42 = *(_DWORD *)v89;
          v33 = 1;
          __eh34_try_continuation(8, &ATL::CAtlException `RTTI Type Descriptor', &loc_180032A86);
        }
      }
LABEL_94:
      if ( v42 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v42 = 0;
      }
      if ( __eh34_try(-1, 10) )
      {
        __eh34_scope_strut(10);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          v35 = (_QWORD *)((char *)v52 + 40);
          if ( *((_QWORD *)v52 + 8) > 7u )
            v35 = (_QWORD *)*v35;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids, v35);
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v54 + 40LL))(*v54);
      }
      if ( __eh34_catch(10) )
      {
        if ( __eh34_catch_type(10, &long `RTTI Type Descriptor', (long *)&v78) )
        {
          v42 = v78;
          v33 = 1;
          __eh34_try_continuation(10, &long `RTTI Type Descriptor', &loc_180032B6D);
          goto LABEL_107;
        }
        if ( __eh34_catch_type(10, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 397;
          v42 = -2147024882;
          v33 = 1;
          __eh34_try_continuation(10, &std::bad_alloc `RTTI Type Descriptor', &loc_180032C06);
          goto LABEL_107;
        }
        if ( __eh34_catch_type(10, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 397;
          v42 = -2147418113;
          v33 = 1;
          __eh34_try_continuation(10, &std::exception `RTTI Type Descriptor', &loc_180032C0B);
          goto LABEL_107;
        }
        if ( __eh34_catch_type(10, &ATL::CAtlException `RTTI Type Descriptor', &v90) )
        {
          HIWORD(v43) = 397;
          v42 = *(_DWORD *)v90;
          v33 = 1;
          __eh34_try_continuation(10, &ATL::CAtlException `RTTI Type Descriptor', &loc_180032B6D);
        }
      }
LABEL_107:
      if ( v42 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v42 = 0;
      }
      if ( __eh34_try(-1, 12) )
      {
        __eh34_scope_strut(12);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v36 = (const unsigned __int16 *)((char *)v52 + 40);
        v37 = (const WCHAR *)((char *)v52 + 40);
        if ( *((_QWORD *)v52 + 8) > 7u )
          v37 = *(const WCHAR **)v36;
        if ( !DecryptFileW(v37, 0) )
        {
          v38 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          {
LABEL_131:
            if ( *((_QWORD *)v52 + 8) > 7u )
              v36 = *(const unsigned __int16 **)v36;
            v41 = (const unsigned __int16 *)((char *)v52 + 416);
            if ( *((_QWORD *)v52 + 55) <= 7u )
              v33 = 0;
            if ( v33 )
              v41 = *(const unsigned __int16 **)v41;
            CSyncEngineRunner::DeletePartnership(*v55, v41, v36);
            goto LABEL_225;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
          {
LABEL_127:
            if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 68) & 8) != 0 && *((_BYTE *)v38 + 65) >= 4u )
              WPP_SF_(v38[7], 34, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
            goto LABEL_131;
          }
          LastError = GetLastError();
          LODWORD(v40) = (_DWORD)v52 + 40;
          if ( *((_QWORD *)v52 + 8) > 7u )
            v40 = *(const WCHAR **)v36;
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            33,
            (unsigned int)WPP_c50e88cd26c039949ea149514aeada6d_Traceguids,
            (_DWORD)v40,
            LastError);
        }
        v38 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_127;
      }
      if ( __eh34_catch(12) )
      {
        if ( __eh34_catch_type(12, &long `RTTI Type Descriptor', (long *)&v77) )
        {
          v42 = v77;
          __eh34_try_continuation(12, &long `RTTI Type Descriptor', &loc_180032CF9);
          goto LABEL_225;
        }
        if ( __eh34_catch_type(12, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 426;
          v42 = -2147024882;
          __eh34_try_continuation(12, &std::bad_alloc `RTTI Type Descriptor', &loc_180032D5B);
          goto LABEL_225;
        }
        if ( __eh34_catch_type(12, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 426;
          v42 = -2147418113;
          __eh34_try_continuation(12, &std::exception `RTTI Type Descriptor', &loc_180032D5D);
          goto LABEL_225;
        }
        if ( __eh34_catch_type(12, &ATL::CAtlException `RTTI Type Descriptor', &v91) )
        {
          HIWORD(v43) = 426;
          v42 = *(_DWORD *)v91;
          __eh34_try_continuation(12, &ATL::CAtlException `RTTI Type Descriptor', &loc_180032CF9);
        }
      }
LABEL_225:
      if ( v42 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids);
        }
        v42 = 0;
      }
      v42 = (int)v53;
      if ( (int)v53 < 0 )
      {
        HIWORD(v43) = 438;
        v68 = (int)v53;
        throw (long *)&v68;
      }
      LOWORD(v43) = 438;
      std::wstring::_Tidy_deallocate(lpSrc);
      CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v42);
       = 0;
LABEL_234:
      ;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      HIWORD(v43) = 328;
      v42 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800328A6);
      goto LABEL_60;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
    {
      HIWORD(v43) = 328;
      v42 = -2147418113;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_1800328AB);
      goto LABEL_60;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v86) )
    {
      HIWORD(v43) = 328;
      v42 = *(_DWORD *)v86;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18003280A);
      goto LABEL_60;
    }
  }
  std::wstring::_Tidy_deallocate(lpSrc);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v42);
   = v31;
  goto LABEL_234;
}

```

## disassembly

```asm
0x18003210c  push    rbx
0x18003210e  push    rsi
0x18003210f  push    rdi
0x180032110  push    r12
0x180032112  push    r13
0x180032114  push    r14
0x180032116  push    r15
0x180032118  sub     rsp, 400h
0x18003211f  mov     rax, cs:__security_cookie
0x180032126  xor     rax, rsp
0x180032129  mov     [rsp+438h+var_48], rax
0x180032131  mov     r12, r9
0x180032134  mov     [rsp+438h+var_338], r9
0x18003213c  mov     r15, r8
0x18003213f  mov     [rsp+438h+var_318], r8
0x180032147  mov     r14, rcx
0x18003214a  mov     [rsp+438h+var_3A8], rcx
0x180032152  mov     [rsp+438h+var_320], rdx
0x18003215a  mov     [rsp+438h+var_390], r8
0x180032162  mov     [rsp+438h+var_398], r9
0x18003216a  mov     rax, [rsp+438h+arg_20]
0x180032172  mov     [rsp+438h+var_380], rax
0x18003217a  mov     rax, [rsp+438h+arg_28]
0x180032182  mov     [rsp+438h+var_388], rax
0x18003218a  mov     rax, [rsp+438h+arg_30]
0x180032192  mov     [rsp+438h+var_328], rax
0x18003219a  mov     rax, [rsp+438h+arg_38]
0x1800321a2  mov     [rsp+438h+var_2E8], rax
0x1800321aa  mov     rax, [rsp+438h+arg_40]
0x1800321b2  mov     [rsp+438h+var_330], rax
0x1800321ba  mov     rax, [rsp+438h+arg_48]
0x1800321c2  mov     [rsp+438h+var_2F0], rax
0x1800321ca  lea     rdi, WPP_GLOBAL_Control
0x1800321d1  mov     rax, cs:WPP_GLOBAL_Control
0x1800321d8  cmp     rax, rdi
0x1800321db  jz      short loc_180032205
0x1800321dd  test    byte ptr [rax+44h], 8
0x1800321e1  jz      short loc_18003221D
0x1800321e3  cmp     byte ptr [rax+41h], 6
0x1800321e7  jb      short loc_180032205
0x1800321e9  mov     edx, 11h
0x1800321ee  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x1800321f5  mov     rcx, [rax+38h]
0x1800321f9  call    WPP_SF_
0x1800321fe  mov     rax, cs:WPP_GLOBAL_Control
0x180032205  test    byte ptr [rax+44h], 8
0x180032209  jz      short loc_18003221D
0x18003220b  cmp     byte ptr [rax+41h], 6
0x18003220f  jb      short loc_18003221D
0x180032211  mov     esi, 1
0x180032216  mov     al, sil
0x180032219  xor     ebx, ebx
0x18003221b  jmp     short loc_180032224
0x18003221d  xor     ebx, ebx
0x18003221f  mov     al, bl
0x180032221  lea     esi, [rbx+1]
0x180032224  mov     [rsp+438h+var_3D8], ebx
0x180032228  mov     [rsp+438h+var_3D4], 0D8h
0x180032230  mov     [rsp+438h+var_3D0], al
0x180032234  lea     rax, aCpartnershipst_18; "CPartnershipStateManager::CreateNewPart"...
0x18003223b  mov     [rsp+438h+var_3C8], rax
0x180032240  mov     [rsp+438h+var_3C0], rbx
0x180032245  mov     eax, [rsp+438h+var_3D8]
0x180032249  mov     [rsp+438h+var_3D8], eax
0x18003224d  mov     rax, [rsp+438h+var_320]
0x180032255  mov     ecx, 0DAh
0x18003225a  cmp     [rax], rbx
0x18003225d  jz      loc_180032DA1
0x180032263  mov     [rsp+438h+var_3D8], ebx
0x180032267  mov     word ptr [rsp+438h+var_3D4], cx
0x18003226c  mov     [rsp+438h+var_3D8], ebx
0x180032270  mov     ecx, 0DBh
0x180032275  cmp     [r15], rbx
0x180032278  jz      loc_180032DCB
0x18003227e  mov     [rsp+438h+var_3D8], ebx
0x180032282  mov     word ptr [rsp+438h+var_3D4], cx
0x180032287  mov     [rsp+438h+var_3D8], ebx
0x18003228b  mov     ecx, 0DCh
0x180032290  cmp     [r12], rbx
0x180032294  jz      loc_180032DF5
0x18003229a  mov     [rsp+438h+var_3D8], ebx
0x18003229e  mov     word ptr [rsp+438h+var_3D4], cx
0x1800322a3  mov     [rsp+438h+var_3D8], ebx
0x1800322a7  mov     rax, [rsp+438h+var_380]
0x1800322af  mov     ecx, 0DDh
0x1800322b4  cmp     [rax], rbx
0x1800322b7  jz      loc_180032E1F
0x1800322bd  mov     [rsp+438h+var_3D8], ebx
0x1800322c1  mov     word ptr [rsp+438h+var_3D4], cx
0x1800322c6  mov     [rsp+438h+var_3D8], ebx
0x1800322ca  mov     rax, [rsp+438h+var_388]
0x1800322d2  mov     ecx, 0DEh
0x1800322d7  cmp     [rax], rbx
0x1800322da  jz      loc_180032E49
0x1800322e0  mov     [rsp+438h+var_3D8], ebx
0x1800322e4  mov     word ptr [rsp+438h+var_3D4], cx
0x1800322e9  mov     [rsp+438h+var_3D8], ebx
0x1800322ed  mov     ecx, 0DFh
0x1800322f2  cmp     [rsp+438h+var_328], rbx
0x1800322fa  jz      loc_180032E73
0x180032300  mov     [rsp+438h+var_3D8], ebx
0x180032304  mov     word ptr [rsp+438h+var_3D4], cx
0x180032309  mov     [rsp+438h+var_3D8], ebx
0x18003230d  mov     ecx, 0E0h
0x180032312  cmp     [rsp+438h+var_330], rbx
0x18003231a  jz      loc_180032E9D
0x180032320  mov     [rsp+438h+var_3D8], ebx
0x180032324  mov     word ptr [rsp+438h+var_3D4], cx
0x180032329  cmp     [r14+168h], esi
0x180032330  jnz     loc_180032EC7
0x180032336  mov     [rsp+438h+var_3B4], bl
0x18003233d  mov     [rsp+438h+var_3B6], bl
0x180032344  mov     [rsp+438h+var_3B7], bl
0x18003234b  mov     [rsp+438h+var_3B5], bl
0x180032352  mov     [rsp+438h+var_3B8], bl
0x180032359  xorps   xmm0, xmm0
0x18003235c  movups  xmmword ptr [rsp+438h+lpSrc], xmm0
0x180032364  mov     [rsp+438h+var_290], rbx
0x18003236c  mov     [rsp+438h+var_288], rbx
0x180032374  mov     [rsp+438h+var_290], rbx
0x18003237c  mov     [rsp+438h+var_288], 7
0x180032388  mov     word ptr [rsp+438h+lpSrc], bx
0x180032390  lea     r13, [r14+28h]
0x180032394  mov     rdx, r13
0x180032397  lea     rcx, [rsp+438h+lpSrc]
0x18003239f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800323a4  mov     [rsp+438h+Dest], bx
0x1800323ac  xor     edx, edx; Val
0x1800323ae  mov     r8d, 206h; Size
0x1800323b4  lea     rcx, [rsp+438h+var_256]; void *
0x1800323bc  call    memset_0
0x1800323c1  mov     eax, [rsp+438h+var_3D8]
0x1800323c5  mov     [rsp+438h+var_3D8], eax
0x1800323c9  lea     rdx, [rsp+438h+lpSrc]
0x1800323d1  cmp     [rsp+438h+var_288], 7
0x1800323da  cmova   rdx, [rsp+438h+lpSrc]; lpSrc
0x1800323e3  mov     r9d, 104h; dwSize
0x1800323e9  lea     r8, [rsp+438h+Dest]; lpDest
0x1800323f1  mov     rcx, [r12]; hToken
0x1800323f5  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x1800323fb  test    eax, eax
0x1800323fd  jz      loc_180032EFA
0x180032403  mov     [rsp+438h+var_3D8], ebx
0x180032407  mov     ecx, 0FCh
0x18003240c  mov     word ptr [rsp+438h+var_3D4], cx
0x180032411  lea     rax, [rsp+438h+Dest]
0x180032419  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003241d  inc     r8
0x180032420  cmp     [rax+r8*2], bx
0x180032425  jnz     short loc_18003241D
0x180032427  lea     rdx, [rsp+438h+Dest]
0x18003242f  mov     rcx, r13
0x180032432  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180032437  mov     r8b, sil
0x18003243a  lea     rdx, [rsp+438h+Dest]
0x180032442  lea     rcx, [rsp+438h+var_280]
0x18003244a  call    ?GetStagingLocation@CStagingLocationConfig@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z; CStagingLocationConfig::GetStagingLocation(ushort const *,bool)
0x18003244f  nop
0x180032450  lea     rcx, [r14+48h]
0x180032454  mov     rdx, rax
0x180032457  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003245c  nop
0x18003245d  lea     rcx, [rsp+438h+var_280]
0x180032465  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003246a  mov     r8b, sil
0x18003246d  lea     rdx, [rsp+438h+Dest]
0x180032475  lea     rcx, [rsp+438h+var_280]
0x18003247d  call    ?GetStagingDownloadLocation@CStagingLocationConfig@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_N@Z; CStagingLocationConfig::GetStagingDownloadLocation(ushort const *,bool)
0x180032482  nop
0x180032483  lea     rcx, [r14+68h]
0x180032487  mov     rdx, rax
0x18003248a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003248f  nop
0x180032490  lea     rcx, [rsp+438h+var_280]
0x180032498  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003249d  xor     r9d, r9d; unsigned __int64 *
0x1800324a0  mov     r8b, [r14+17Ch]; bool
0x1800324a7  mov     rdx, [r14+198h]; unsigned __int64
0x1800324ae  lea     rcx, [rsp+438h+Dest]; unsigned __int16 *
0x1800324b6  call    ?ValidateSyncFolder@CSyncStateManager@@SAXPEBG_K_NPEA_K@Z; CSyncStateManager::ValidateSyncFolder(ushort const *,unsigned __int64,bool,unsigned __int64 *)
0x1800324bb  mov     rdx, r14; struct ClientPartnershipDescriptor *
0x1800324be  mov     rcx, [rsp+438h+var_388]
0x1800324c6  mov     rcx, [rcx]; this
0x1800324c9  call    ?CreatePartnership@CSyncEngineRunner@@QEAAXAEAVClientPartnershipDescriptor@@@Z; CSyncEngineRunner::CreatePartnership(ClientPartnershipDescriptor &)
0x1800324ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324d5  cmp     rcx, rdi
0x1800324d8  jz      short loc_1800324FB
0x1800324da  test    byte ptr [rcx+44h], 8
0x1800324de  jz      short loc_1800324FB
0x1800324e0  cmp     byte ptr [rcx+41h], 4
0x1800324e4  jb      short loc_1800324FB
0x1800324e6  mov     edx, 12h
0x1800324eb  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x1800324f2  mov     rcx, [rcx+38h]
0x1800324f6  call    WPP_SF_
0x1800324fb  mov     [rsp+438h+var_3B4], sil
0x180032503  lea     r12, [r14+148h]
0x18003250a  mov     rcx, r12; pguid
0x18003250d  call    cs:__imp_CoCreateGuid
0x180032513  mov     [rsp+438h+var_3D8], eax
0x180032517  mov     [rsp+438h+var_3D8], eax
0x18003251b  mov     ecx, 113h
0x180032520  test    eax, eax
0x180032522  js      loc_180032F28
0x180032528  mov     word ptr [rsp+438h+var_3D4], cx
0x18003252d  mov     r10, [r15]
0x180032530  mov     rax, [r10]
0x180032533  mov     r11, [rax+10h]
0x180032537  lea     r15, [r14+1A0h]
0x18003253e  mov     [rsp+438h+var_378], r15
0x180032546  lea     rax, [r15+18h]
0x18003254a  mov     [rsp+438h+var_2F8], rax
0x180032552  cmp     qword ptr [rax], 7
0x180032556  jbe     short loc_18003255D
0x180032558  mov     rdx, [r15]
0x18003255b  jmp     short loc_180032560
0x18003255d  mov     rdx, r15
0x180032560  lea     rcx, [r14+18Ah]
0x180032567  lea     r8, [r14+180h]
0x18003256e  mov     [rsp+438h+var_400], rcx
0x180032573  mov     [rsp+438h+var_408], r8
0x180032578  mov     rax, [rsp+438h+var_338]
0x180032580  mov     [rsp+438h+var_410], rax
0x180032585  lea     rax, aDesktopIniThum; "\\\\desktop.ini$|\\\\thumbs.db$|\\\\eht"...
0x18003258c  mov     [rsp+438h+var_418], rax
0x180032591  lea     r9, [rsp+438h+Dest]
0x180032599  mov     r8, r12
0x18003259c  mov     rcx, r10
0x18003259f  mov     rax, r11
0x1800325a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325ae  cmp     rcx, rdi
0x1800325b1  jz      short loc_1800325D4
0x1800325b3  test    byte ptr [rcx+44h], 8
0x1800325b7  jz      short loc_1800325D4
0x1800325b9  cmp     byte ptr [rcx+41h], 4
0x1800325bd  jb      short loc_1800325D4
0x1800325bf  mov     edx, 13h
0x1800325c4  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x1800325cb  mov     rcx, [rcx+38h]
0x1800325cf  call    WPP_SF_
0x1800325d4  mov     [rsp+438h+var_3B6], sil
0x1800325dc  cmp     qword ptr [r13+18h], 7
0x1800325e1  jbe     short loc_1800325E8
0x1800325e3  mov     al, sil
0x1800325e6  jmp     short loc_1800325EA
0x1800325e8  mov     al, bl
0x1800325ea  mov     rdx, r13
0x1800325ed  test    al, al
0x1800325ef  jz      short loc_1800325F5
0x1800325f1  mov     rdx, [r13+0]
0x1800325f5  mov     r12, [rsp+438h+var_318]
0x1800325fd  mov     rcx, [r12]
0x180032601  mov     rax, [rcx]
0x180032604  mov     rax, [rax+20h]
0x180032608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003260d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032614  cmp     rcx, rdi
0x180032617  jz      short loc_180032653
0x180032619  test    byte ptr [rcx+44h], 8
0x18003261d  jz      short loc_180032653
0x18003261f  cmp     byte ptr [rcx+41h], 4
0x180032623  jb      short loc_180032653
0x180032625  cmp     qword ptr [r13+18h], 7
0x18003262a  jbe     short loc_180032631
0x18003262c  mov     al, sil
0x18003262f  jmp     short loc_180032633
0x180032631  mov     al, bl
0x180032633  test    al, al
0x180032635  jz      short loc_18003263B
0x180032637  mov     r13, [r13+0]
0x18003263b  mov     edx, 14h
0x180032640  mov     r9, r13
0x180032643  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x18003264a  mov     rcx, [rcx+38h]
0x18003264e  call    WPP_SF_S
0x180032653  mov     [rsp+438h+var_3B5], sil
0x18003265b  mov     r13, [rsp+438h+var_338]
0x180032663  jmp     short loc_180032691
0x180032665  mov     r15, [rsp+438h+var_378]
0x18003266d  mov     r13, [rsp+438h+var_398]
0x180032675  mov     r12, [rsp+438h+var_390]
0x18003267d  mov     r14, [rsp+438h+var_3A8]
0x180032685  xor     ebx, ebx
0x180032687  lea     esi, [rbx+1]
0x18003268a  lea     rdi, WPP_GLOBAL_Control
0x180032691  mov     r9d, [rsp+438h+var_3D8]
0x180032696  test    r9d, r9d
0x180032699  jns     short loc_1800326CC
0x18003269b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326a2  cmp     rcx, rdi
0x1800326a5  jz      short loc_1800326C8
0x1800326a7  test    byte ptr [rcx+44h], 8
0x1800326ab  jz      short loc_1800326C8
0x1800326ad  cmp     byte ptr [rcx+41h], 2
0x1800326b1  jb      short loc_1800326C8
0x1800326b3  mov     edx, 15h
0x1800326b8  lea     r8, WPP_c50e88cd26c039949ea149514aeada6d_Traceguids
0x1800326bf  mov     rcx, [rcx+38h]
0x1800326c3  call    WPP_SF_d
  ... truncated ...
```
