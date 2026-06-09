# CScmRot::Register(CProcess *,ushort const *,_MnkEqBuf const *,tagInterfaceData const *,tagInterfaceData const *,_FILETIME const *,ulong,ulong,_SCMREGKEY *,uint,HSTRING__ * const * const)

- ea: `0x180090a0c`
- end: `0x180091617`
- name: `?Register@CScmRot@@QEAAJPEAVCProcess@@PEBGPEBU_MnkEqBuf@@PEBUtagInterfaceData@@3PEBU_FILETIME@@KKPEAU_SCMREGKEY@@IQEBQEAUHSTRING__@@@Z`
- size: `3083`
- prototype: `__int64 __fastcall(CScmRot *this, struct CProcess *, unsigned __int16 *, const struct _MnkEqBuf *, const struct tagInterfaceData *, const struct tagInterfaceData *, const struct _FILETIME *, unsigned int, unsigned int, RTL_SRWLOCK *, unsigned int, HSTRING *const)`
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800908b0`

## callees

- `0x180005c40`
- `0x18000b310`
- `0x18000fe84`
- `0x1800219c0`
- `0x180025310`
- `0x180025398`
- `0x180026a50`
- `0x180028e94`
- `0x18002ba28`
- `0x18002f8cc`
- `0x18002fa6c`
- `0x180038700`
- `0x180039068`
- `0x180039088`
- `0x18003b07c`
- `0x1800418c0`
- `0x18004778c`
- `0x180053cf4`
- `0x180055a88`
- `0x180056270`
- `0x1800562e0`
- `0x1800563ac`
- `0x18005f130`
- `0x1800611d8`
- `0x180067390`
- `0x18006b274`
- `0x18006b2e4`
- `0x18006bb00`
- `0x18006e06c`
- `0x18006e7b0`
- `0x1800729e0`
- `0x18007ea58`
- `0x18007f690`
- `0x18008078c`
- `0x1800822d4`
- `0x180082ba8`
- `0x18008e98c`
- `0x180090a0c`
- `0x180091620`
- `0x1800920b4`
- `0x180098b54`
- `0x1800a20ec`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800f3974`
- `0x1800f3a8c`
- `0x18010a078`
- `0x18010a084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009150d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009150d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180091497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180091497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800912ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180091341`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180091378`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800913b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800913ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800912ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180091341`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180091378`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800913b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800913ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180090e97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180090e97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090d03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090e3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090d03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090e3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800915cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800915cd`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180090ebd`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180090ebd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180090bb2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180090bb2`

## string_xrefs

- `0x180090c1f`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180090c8e`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180090d19`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180090d82`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180090df5`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180090f36`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x18009107e`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x18009113f`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180091191`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`

## pseudocode

```c
__int64 __fastcall CScmRot::Register(
        CScmRot *this,
        struct CProcess *a2,
        unsigned __int16 *a3,
        const struct _MnkEqBuf *a4,
        const struct tagInterfaceData *a5,
        const struct tagInterfaceData *a6,
        const struct _FILETIME *a7,
        unsigned int a8,
        unsigned int a9,
        RTL_SRWLOCK *a10,
        unsigned int a11,
        HSTRING *const a12)
{
  const unsigned __int16 *v12; // rbx
  CMutexSem2 *v14; // rdi
  char v15; // bl
  unsigned int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  const unsigned __int16 *FileNameW; // rbx
  int v22; // ebx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  unsigned int v26; // eax
  HKEY v27; // rcx
  HKEY v28; // rdi
  __int64 v29; // rdx
  unsigned int v30; // eax
  __int64 v31; // rdx
  char v32; // bl
  unsigned int ValueW; // eax
  int PackageFullName; // eax
  unsigned int v35; // edi
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  unsigned int ClassicComActivationServerCatalogFlags; // eax
  struct _MnkEqBuf *v41; // r14
  unsigned int v42; // r8d
  HKEY v43; // rdi
  char *v44; // rcx
  LPVOID v45; // r14
  unsigned __int16 *v46; // r15
  struct _MnkEqBuf *v47; // r13
  void *v48; // r12
  unsigned __int16 *v49; // rax
  struct tagInterfaceData *v50; // rdi
  _DWORD *v51; // rax
  const void *v52; // rdx
  size_t v53; // r8
  _DWORD *v54; // rax
  char *v55; // rdx
  size_t v56; // r8
  _DWORD *v57; // rax
  const void *v58; // rdx
  size_t v59; // r8
  struct _MnkEqBuf *v60; // r9
  unsigned int v61; // r13d
  CMutexSem2 *v62; // rdi
  unsigned int v63; // edx
  unsigned int v64; // r9d
  const unsigned __int16 *v65; // rcx
  _QWORD *v66; // r15
  void *v67; // rax
  signed int LastError; // eax
  struct CToken *v69; // rdx
  struct CScmRotMgotEntryBase *RotMgotEntryFromTable; // rax
  CScmHashTable *v71; // rcx
  struct CScmRotMgotEntryBase *v72; // rdi
  PSRWLOCK v73; // rax
  struct CProcess *v74; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  struct tagInterfaceData *pcbData; // [rsp+30h] [rbp-D0h]
  bool v77; // [rsp+50h] [rbp-B0h] BYREF
  CToken *v78; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v79; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v80; // [rsp+68h] [rbp-98h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY v83; // [rsp+80h] [rbp-80h] BYREF
  CMutexSem2 *v84; // [rsp+88h] [rbp-78h]
  struct _MnkEqBuf *v85; // [rsp+90h] [rbp-70h]
  PSRWLOCK SRWLock; // [rsp+98h] [rbp-68h] BYREF
  struct CProcess *v87; // [rsp+A0h] [rbp-60h]
  const struct tagInterfaceData *v88; // [rsp+A8h] [rbp-58h]
  const struct tagInterfaceData *v89; // [rsp+B0h] [rbp-50h]
  GUID Buf1; // [rsp+B8h] [rbp-48h] BYREF
  GUID iid; // [rsp+C8h] [rbp-38h] BYREF
  OLECHAR v92[40]; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz[40]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR SubKey[7]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v95[514]; // [rsp+18Eh] [rbp+8Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  v12 = a3;
  v14 = (CMutexSem2 *)gpscmrot;
  SRWLock = a10;
  v78 = (CToken *)*((_QWORD *)a2 + 3);
  v85 = a4;
  hKey = (HKEY)a3;
  v87 = a2;
  v89 = a6;
  v88 = a5;
  v84 = (CMutexSem2 *)gpscmrot;
  if ( (a9 & 2) == 0 )
  {
    v77 = 0;
    goto LABEL_95;
  }
  memset_0(sz, 0, 0x4Eu);
  Buf1 = *(GUID *)((char *)a2 + 392);
  iid = 0;
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      iid = *(GUID *)((char *)a2 + 392);
    }
    else
    {
      Buf1 = *(GUID *)((char *)a2 + 392);
      v19 = (const unsigned __int16 *)GuidString::GuidString(v92, &Buf1);
      if ( (int)StringCchCopyW(sz, 0x27u, v19) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
    }
    goto LABEL_6;
  }
  FileNameW = PathFindFileNameW(*((LPCWSTR *)a2 + 48));
  wcscpy(SubKey, L"AppID\\");
  memset_0(v95, 0, 0x1FAu);
  v22 = StringCchCatW(SubKey, 0x104u, FileNameW);
  if ( v22 < 0 )
  {
    v23 = 425;
    goto LABEL_13;
  }
  v80 = 0;
  *(_QWORD *)&Buf1.Data1 = &v80;
  *(_QWORD *)Buf1.Data4 = &v78;
  v24 = *((_DWORD *)a2 + 23);
  hKey = 0;
  hkey = 0;
  if ( (v24 & 0x4000) != 0 && (int)CToken::GetPrivateHiveComRootKey(v78, &hKey) >= 0 )
  {
    v25 = lambda_2b39ab1cb3293c7772a1fea831a058d2_::operator()(&Buf1);
    v22 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
        (const char *)(unsigned int)v25,
        phkResult);
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      if ( hKey )
        CToken::ReleasePrivateHiveComRootKey(v78);
      if ( v80 )
        CToken::Revert(v78, v80);
      return (unsigned int)v22;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v26 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hkey);
    if ( v26 != 2 && v26 )
    {
      v22 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1D7,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
              (const char *)v26,
              phkResult);
      goto LABEL_18;
    }
  }
  v27 = hkey;
  v79 = 0;
  if ( !hkey )
  {
    v28 = 0;
    if ( v78 )
    {
      if ( (int)CToken::GetUserClassesRootKey(v78, &v79) >= 0 )
      {
        v28 = v79;
        v22 = lambda_2b39ab1cb3293c7772a1fea831a058d2_::operator()(&Buf1);
        if ( v22 < 0 )
        {
          v29 = 495;
LABEL_30:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
            (const char *)(unsigned int)v22,
            phkResult);
          goto LABEL_31;
        }
      }
    }
    v83 = 0;
    if ( !v28 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v83,
        0);
      v30 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes", 0, 0x20019u, &v83);
      if ( v30 )
      {
        v31 = 503;
LABEL_36:
        v22 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v31,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
                (const char *)v30,
                phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
        goto LABEL_31;
      }
      v28 = v83;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v30 = RegOpenKeyExW(v28, SubKey, 0, 0x20019u, &hkey);
    if ( v30 != 2 && v30 )
    {
      v31 = 510;
      goto LABEL_36;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v83);
    v27 = hkey;
  }
  v32 = 0;
  if ( v27 )
  {
    LODWORD(v83) = 78;
    ValueW = RegGetValueW(v27, 0, L"AppID", 2u, 0, sz, (LPDWORD)&v83);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v22 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x211,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
                (const char *)ValueW,
                phkResult);
LABEL_31:
        if ( v79 )
          CToken::ReleaseUserClassesRootKey(v78);
        goto LABEL_18;
      }
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      {
        v22 = IIDFromString(sz, &iid);
        if ( v22 < 0 )
        {
          v29 = 524;
          goto LABEL_30;
        }
      }
      v32 = 1;
    }
  }
  if ( v79 )
    CToken::ReleaseUserClassesRootKey(v78);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  if ( hKey )
    CToken::ReleasePrivateHiveComRootKey(v78);
  if ( v80 )
    CToken::Revert(v78, v80);
  if ( !v32 )
  {
    v22 = -2147467243;
    v23 = 534;
    goto LABEL_13;
  }
LABEL_6:
  v15 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    CAppidData::CAppidData((CAppidData *)SubKey, &iid, v78, 0);
    ClassicComActivationServerCatalogFlags = GetClassicComActivationServerCatalogFlags(a2, 1);
    v17 = CAppidData::Load((CAppidData *)SubKey, 0, ClassicComActivationServerCatalogFlags, 0, 0, a11, a12, 0, 0);
    if ( v17 < 0 )
    {
      v18 = 560;
      goto LABEL_72;
    }
    if ( (unsigned int)CAppidData::GetRunAsType(SubKey) != 2 || (unsigned int)CAppidData::GetProcessType(SubKey) == 1 )
    {
      if ( (unsigned int)CAppidData::GetRunAsType(SubKey) == 4 )
      {
        v79 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v79,
          0);
        PackageFullName = CToken::GetPackageFullName(v78, (unsigned __int16 **)&v79);
        v35 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v36 = 579;
          goto LABEL_82;
        }
        v77 = 0;
        PackageFullName = CanPackageUseAllowAnyClientBasedOnPackagedAppID((const unsigned __int16 *)v79, &v77);
        v35 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v36 = 583;
          goto LABEL_82;
        }
        if ( v77 )
        {
          v37 = CAppidData::CertifyServer((CAppidData *)SubKey, a2);
          if ( v37 < 0 )
          {
            v38 = 588;
            goto LABEL_86;
          }
LABEL_87:
          v15 = 1;
        }
LABEL_88:
        utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v79);
        goto LABEL_92;
      }
      v17 = CAppidData::CertifyServer((CAppidData *)SubKey, a2);
      if ( v17 < 0 )
      {
        v18 = 593;
        goto LABEL_72;
      }
LABEL_91:
      v15 = 1;
      goto LABEL_92;
    }
LABEL_75:
    if ( (unsigned int)CAppidData::GetRunAsType(SubKey) == 2 )
      v15 = v95[50] & 1;
    goto LABEL_92;
  }
  CAppidData::CAppidData((CAppidData *)SubKey, sz, v78, 0);
  v16 = GetClassicComActivationServerCatalogFlags(a2, 1);
  v17 = CAppidData::Load((CAppidData *)SubKey, 0, v16, 0, 0, 0, 0, 0, 0);
  if ( v17 >= 0 )
  {
    if ( (unsigned int)CAppidData::GetRunAsType(SubKey) != 2 || (unsigned int)CAppidData::GetProcessType(SubKey) == 1 )
    {
      if ( (unsigned int)CAppidData::GetRunAsType(SubKey) == 4 )
      {
        v79 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void PrivMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v79,
          0);
        PackageFullName = CToken::GetPackageFullName(v78, (unsigned __int16 **)&v79);
        v35 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v36 = 632;
LABEL_82:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v36,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
            (const char *)(unsigned int)PackageFullName,
            phkResult);
          utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<CClientOxid *>>>(&v79);
          CAppidData::~CAppidData((CAppidData *)SubKey);
          return v35;
        }
        v77 = 0;
        PackageFullName = CanPackageUseAllowAnyClientBasedOnPackagedAppID((const unsigned __int16 *)v79, &v77);
        v35 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v36 = 636;
          goto LABEL_82;
        }
        if ( v77 )
        {
          v37 = CAppidData::CertifyServer((CAppidData *)SubKey, a2);
          if ( v37 < 0 )
          {
            v38 = 641;
LABEL_86:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v38,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
              (const char *)(unsigned int)v37,
              phkResult);
            goto LABEL_88;
          }
          goto LABEL_87;
        }
        goto LABEL_88;
      }
      v17 = CAppidData::CertifyServer((CAppidData *)SubKey, a2);
      if ( v17 < 0 )
      {
        v18 = 646;
        goto LABEL_72;
      }
      goto LABEL_91;
    }
    goto LABEL_75;
  }
  v18 = 613;
LABEL_72:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
    (const char *)(unsigned int)v17,
    phkResult);
LABEL_92:
  CAppidData::~CAppidData((CAppidData *)SubKey);
  if ( v15 )
  {
    v14 = v84;
    v12 = 0;
    hKey = 0;
    v77 = 1;
LABEL_95:
    CMutexSem2::Request(v14);
    v41 = v85;
    ++*((_DWORD *)v14 + 12);
    v80 = ScmRotHash((const unsigned __int8 *)v41 + 4, *(_DWORD *)v41, v42);
    v43 = 0;
    v79 = 0;
    hkey = 0;
    v83 = 0;
    *(_QWORD *)&Buf1.Data1 = 0;
    if ( !v12 )
      goto LABEL_100;
    if ( (int)StringCchLengthW(v12, 0x7FFFFFFFu, (unsigned __int64 *)&v79) >= 0 )
    {
      v44 = (char *)v79 + 1;
      if ( (HKEY)((char *)v79 + 1) < v79 )
      {
        v79 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      else
      {
        v79 = (HKEY)((char *)v79 + 1);
        if ( (int)ULongLongMult((unsigned __int64)v44, 2u, (unsigned __int64 *)&v79) >= 0 )
        {
          v43 = v79;
LABEL_100:
          v22 = CalcIfdSize(a5, (unsigned __int64 *)&hkey);
          if ( v22 < 0 )
            goto LABEL_136;
          v22 = SizeMnkEqBufForRotEntry(v41, (unsigned __int64 *)&v83);
          if ( v22 < 0 )
            goto LABEL_136;
          v22 = CalcIfdSize(a6, (unsigned __int64 *)&Buf1.Data1);
          if ( v22 < 0 )
            goto LABEL_136;
          v45 = 0;
          v46 = 0;
          v47 = 0;
          v48 = 0;
          if ( !v43 )
            goto LABEL_110;
          v49 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, (SIZE_T)v43);
          v46 = v49;
          if ( v49 )
          {
            v22 = StringCbCopyW(v49, (unsigned __int64)v43, (const unsigned __int16 *)hKey);
            if ( v22 < 0 )
            {
              v50 = 0;
              goto LABEL_117;
            }
LABEL_110:
            v51 = HeapAlloc(g_hHeap, 0, (SIZE_T)hkey);
            v50 = (struct tagInterfaceData *)v51;
            if ( v51 )
            {
              v52 = (char *)v88 + 4;
              v53 = *(unsigned int *)v88;
              *v51 = *(_DWORD *)v88;
              memcpy_0(v51 + 1, v52, v53);
              v54 = HeapAlloc(g_hHeap, 0, (SIZE_T)v83);
              v47 = (struct _MnkEqBuf *)v54;
              if ( v54 )
              {
                v55 = (char *)v85 + 4;
                v56 = *(unsigned int *)v85;
                *v54 = *(_DWORD *)v85;
                memcpy_0(v54 + 1, v55, v56);
                v57 = HeapAlloc(g_hHeap, 0, *(SIZE_T *)&Buf1.Data1);
                v48 = v57;
                if ( v57 )
                {
                  v58 = (char *)v89 + 4;
                  v59 = *(unsigned int *)v89;
                  *v57 = *(_DWORD *)v89;
                  memcpy_0(v57 + 1, v58, v59);
                  v45 = HeapAlloc(g_hHeap, 0, 0x70u);
                  if ( v45 )
                  {
                    v60 = v47;
                    v61 = v80;
                    pcbData = v50;
                    v62 = v84;
                    CScmRotMgotEntryBase::CScmRotMgotEntryBase(
                      (CScmRotMgotEntryBase *)v45,
                      *((_DWORD *)v84 + 12),
                      v80,
                      v60,
                      v78,
                      v46,
                      pcbData,
                      (*((_DWORD *)v87 + 23) & 0x200) != 0,
                      *((_DWORD *)v87 + 22));
                    *((_DWORD *)v45 + 21) = a8;
                    *(_QWORD *)v45 = &CScmRotEntry::`vftable';
                    *((_DWORD *)v45 + 20) = 1953460835;
                    v65 = (const unsigned __int16 *)*a7;
                    *((struct _FILETIME *)v45 + 11) = *a7;
                    *((_DWORD *)v45 + 26) = a9;
                    *((_QWORD *)v45 + 12) = v48;
                    v66 = (_QWORD *)((char *)v62 + 56);
                    if ( *((_QWORD *)v62 + 7) )
                      goto LABEL_130;
                    v67 = OpenSharedFileMapping(v65, v63, (void **)v62 + 7, v64);
                    *((_QWORD *)v62 + 8) = v67;
                    if ( v67 )
                      goto LABEL_130;
                    LastError = GetLastError();
                    v22 = LastError;
                    if ( LastError > 0 )
                      v22 = (unsigned __int16)LastError | 0x80070000;
                    if ( v22 >= 0 )
                    {
LABEL_130:
                      v69 = v78;
                      if ( v77 )
                        v69 = 0;
                      RotMgotEntryFromTable = GetRotMgotEntryFromTable(
                                                1,
                                                v69,
                                                (const unsigned __int16 *)hKey,
                                                v85,
                                                0,
                                                (CMutexSem2 *)((char *)v62 + 72),
                                                0);
                      v71 = (CMutexSem2 *)((char *)v62 + 72);
                      v72 = RotMgotEntryFromTable;
                      CScmHashTable::SetAt(v71, v61, (struct CScmHashEntry *)v45);
                      v73 = SRWLock;
                      *(_BYTE *)(v61 + *v66) = 1;
                      v73->Ptr = v45;
                      v73[1].Ptr = (PVOID)*((_QWORD *)v45 + 9);
                      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpServerLock);
                      v74 = v87;
                      *((_QWORD *)v45 + 7) = *((_QWORD *)v87 + 19);
                      *((_QWORD *)v74 + 19) = v45;
                      _InterlockedIncrement((volatile signed __int32 *)v45 + 4);
                      v22 = v72 != 0 ? 0x401E7 : 0;
                      if ( SRWLock )
                        ReleaseSRWLockExclusive(SRWLock);
                      goto LABEL_136;
                    }
                    goto LABEL_134;
                  }
                  v45 = 0;
                }
              }
            }
            v22 = -2147024882;
            if ( !v46 )
            {
LABEL_118:
              if ( v50 )
                HeapFree(g_hHeap, 0, v50);
              if ( v47 )
                HeapFree(g_hHeap, 0, v47);
              if ( v48 )
                HeapFree(g_hHeap, 0, v48);
LABEL_134:
              if ( v45 )
                CScmRotMgotEntryBase::Release((CScmRotMgotEntryBase *)v45);
              goto LABEL_136;
            }
LABEL_117:
            HeapFree(g_hHeap, 0, v46);
            goto LABEL_118;
          }
          v22 = -2147024882;
LABEL_136:
          CMutexSem2::Release(v84);
          return (unsigned int)v22;
        }
      }
    }
    v22 = -2147024809;
    goto LABEL_136;
  }
  BreakOnServerCertificationFailureIfRequested();
  v23 = 664;
  v22 = -2147467243;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmrot.cxx",
    (const char *)(unsigned int)v22,
    phkResult);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180090a0c  mov     [rsp-8+arg_0], rbx
0x180090a11  push    rbp
0x180090a12  push    rsi
0x180090a13  push    rdi
0x180090a14  push    r12
0x180090a16  push    r13
0x180090a18  push    r14
0x180090a1a  push    r15
0x180090a1c  lea     rbp, [rsp-2A0h]
0x180090a24  sub     rsp, 3A0h
0x180090a2b  mov     rax, cs:__security_cookie
0x180090a32  xor     rax, rsp
0x180090a35  mov     [rbp+2D0h+var_40], rax
0x180090a3c  test    byte ptr [rbp+2D0h+arg_40], 2
0x180090a43  mov     rbx, r8
0x180090a46  mov     rax, [rbp+2D0h+arg_48]
0x180090a4d  mov     r14, rdx
0x180090a50  mov     r13, [rbp+2D0h+arg_28]
0x180090a57  mov     r12, [rbp+2D0h+arg_20]
0x180090a5e  mov     rdi, cs:?gpscmrot@@3PEAVCScmRot@@EA; CScmRot * gpscmrot
0x180090a65  mov     r15, [rbp+2D0h+arg_58]
0x180090a6c  mov     [rbp+2D0h+SRWLock], rax
0x180090a70  mov     rax, [rdx+18h]
0x180090a74  mov     [rsp+3D0h+var_378], rax
0x180090a79  mov     [rbp+2D0h+var_340], r9
0x180090a7d  mov     [rsp+3D0h+hKey], rbx
0x180090a82  mov     [rbp+2D0h+var_330], rdx
0x180090a86  mov     [rbp+2D0h+var_320], r13
0x180090a8a  mov     [rbp+2D0h+var_328], r12
0x180090a8e  mov     [rbp+2D0h+var_348], rdi
0x180090a92  jnz     short loc_180090AA0
0x180090a94  xor     esi, esi
0x180090a96  mov     [rsp+3D0h+var_380], sil
0x180090a9b  jmp     loc_180091204
0x180090aa0  xor     edx, edx; Val
0x180090aa2  lea     rcx, [rbp+2D0h+sz]; void *
0x180090aa6  lea     r8d, [rdx+4Eh]; Size
0x180090aaa  call    memset_0
0x180090aaf  movups  xmm1, xmmword ptr [r14+188h]
0x180090ab7  lea     rdx, GUID_NULL; Buf2
0x180090abe  mov     r8d, 10h; Size
0x180090ac4  xorps   xmm0, xmm0
0x180090ac7  lea     rcx, [rbp+2D0h+Buf1]; Buf1
0x180090acb  movdqu  [rbp+2D0h+Buf1], xmm1
0x180090ad0  movups  xmmword ptr [rbp+2D0h+iid.Data1], xmm0
0x180090ad4  call    memcmp_0
0x180090ad9  xor     esi, esi
0x180090adb  test    eax, eax
0x180090add  jz      loc_180090BAB
0x180090ae3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180090aea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180090aef  movups  xmm0, xmmword ptr [r14+188h]
0x180090af7  test    al, al
0x180090af9  jz      short loc_180090B76
0x180090afb  movdqu  xmmword ptr [rbp+2D0h+iid.Data1], xmm0
0x180090b00  mov     bl, sil
0x180090b03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180090b0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180090b0f  mov     r8, [rsp+3D0h+var_378]; struct CToken *
0x180090b14  lea     rcx, [rbp+2D0h+SubKey]; this
0x180090b1b  xor     r9d, r9d; unsigned __int64
0x180090b1e  test    al, al
0x180090b20  jnz     loc_18009102A
0x180090b26  lea     rdx, [rbp+2D0h+sz]; unsigned __int16 *
0x180090b2a  call    ??0CAppidData@@QEAA@PEAGPEAVCToken@@_K@Z; CAppidData::CAppidData(ushort *,CToken *,unsigned __int64)
0x180090b2f  mov     dl, 1; bool
0x180090b31  mov     rcx, r14; struct CProcess *
0x180090b34  call    ?GetClassicComActivationServerCatalogFlags@@YAKPEAVCProcess@@_N@Z; GetClassicComActivationServerCatalogFlags(CProcess *,bool)
0x180090b39  mov     [rsp+3D0h+var_390], rsi; HSTRING *
0x180090b3e  lea     rcx, [rbp+2D0h+SubKey]; this
0x180090b45  mov     dword ptr [rsp+3D0h+var_398], esi; unsigned int
0x180090b49  mov     r8d, eax; unsigned int
0x180090b4c  mov     [rsp+3D0h+pcbData], rsi; HSTRING *
0x180090b51  xor     r9d, r9d; unsigned __int16 *
0x180090b54  mov     dword ptr [rsp+3D0h+pvData], esi; unsigned int
0x180090b58  xor     edx, edx; struct IComProcessInfo *
0x180090b5a  mov     [rsp+3D0h+phkResult], rsi; unsigned __int16 *
0x180090b5f  call    ?Load@CAppidData@@QEAAJPEAUIComProcessInfo@@KPEBG1IQEBQEAUHSTRING__@@I2@Z; CAppidData::Load(IComProcessInfo *,ulong,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x180090b64  test    eax, eax
0x180090b66  jns     loc_180090F51
0x180090b6c  mov     edx, 265h
0x180090b71  jmp     loc_180091077
0x180090b76  lea     rdx, [rbp+2D0h+Buf1]; rguid
0x180090b7a  lea     rcx, [rbp+2D0h+var_2F0]; lpsz
0x180090b7e  movdqu  [rbp+2D0h+Buf1], xmm0
0x180090b83  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180090b88  mov     r8, rax; unsigned __int16 *
0x180090b8b  lea     rcx, [rbp+2D0h+sz]; unsigned __int16 *
0x180090b8f  mov     edx, 27h ; '''; unsigned __int64
0x180090b94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180090b99  test    eax, eax
0x180090b9b  jns     loc_180090B00
0x180090ba1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180090ba6  jmp     loc_180090B00
0x180090bab  mov     rcx, [r14+180h]; pszPath
0x180090bb2  call    cs:__imp_PathFindFileNameW
0x180090bb8  mov     ecx, dword ptr cs:aAppid+8; "D\\"
0x180090bbe  xor     edx, edx; Val
0x180090bc0  movsd   xmm0, qword ptr cs:aAppid; "AppID\\"
0x180090bc8  mov     r8d, 1FAh; Size
0x180090bce  mov     [rbp+2D0h+var_248], ecx
0x180090bd4  mov     rbx, rax
0x180090bd7  movzx   ecx, word ptr cs:aAppid+0Ch; ""
0x180090bde  mov     [rbp+2D0h+var_244], cx
0x180090be5  lea     rcx, [rbp+2D0h+var_242]; void *
0x180090bec  movsd   qword ptr [rbp+2D0h+SubKey], xmm0
0x180090bf4  call    memset_0
0x180090bf9  mov     r8, rbx; unsigned __int16 *
0x180090bfc  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x180090c03  mov     edx, 104h; unsigned __int64
0x180090c08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180090c0d  mov     ebx, eax
0x180090c0f  test    eax, eax
0x180090c11  jns     short loc_180090C33
0x180090c13  mov     edx, 1A9h; void *
0x180090c18  mov     rcx, [rbp+2D8h]; this
0x180090c1f  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180090c26  mov     r9d, ebx; char *
0x180090c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090c2e  jmp     loc_1800915EB
0x180090c33  lea     rax, [rsp+3D0h+var_368]
0x180090c38  mov     [rsp+3D0h+var_368], esi
0x180090c3c  mov     qword ptr [rbp+2D0h+Buf1], rax
0x180090c40  lea     rax, [rsp+3D0h+var_378]
0x180090c45  mov     qword ptr [rbp+2D0h+Buf1+8], rax
0x180090c49  mov     eax, [r14+5Ch]
0x180090c4d  mov     [rsp+3D0h+hKey], rsi
0x180090c52  mov     [rsp+3D0h+hkey], rsi
0x180090c57  bt      eax, 0Eh
0x180090c5b  jnb     loc_180090D34
0x180090c61  mov     rcx, [rsp+3D0h+var_378]; this
0x180090c66  lea     rdx, [rsp+3D0h+hKey]; HKEY *
0x180090c6b  call    ?GetPrivateHiveComRootKey@CToken@@UEAAJPEAPEAUHKEY__@@@Z; CToken::GetPrivateHiveComRootKey(HKEY__ * *)
0x180090c70  test    eax, eax
0x180090c72  js      loc_180090D34
0x180090c78  lea     rcx, [rbp+2D0h+Buf1]
0x180090c7c  call    _lambda_2b39ab1cb3293c7772a1fea831a058d2___operator__
0x180090c81  mov     ebx, eax
0x180090c83  test    eax, eax
0x180090c85  jns     short loc_180090CD8
0x180090c87  mov     rcx, [rbp+2D8h]; this
0x180090c8e  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180090c95  mov     r9d, eax; char *
0x180090c98  mov     edx, 1D1h; void *
0x180090c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090ca2  lea     rcx, [rsp+3D0h+hkey]
0x180090ca7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180090cac  cmp     [rsp+3D0h+hKey], rsi
0x180090cb1  jz      short loc_180090CBD
0x180090cb3  mov     rcx, [rsp+3D0h+var_378]; this
0x180090cb8  call    ?ReleasePrivateHiveComRootKey@CToken@@UEAAJXZ; CToken::ReleasePrivateHiveComRootKey(void)
0x180090cbd  mov     edx, [rsp+3D0h+var_368]; int
0x180090cc1  test    edx, edx
0x180090cc3  jz      loc_1800915EB
0x180090cc9  mov     rcx, [rsp+3D0h+var_378]; this
0x180090cce  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x180090cd3  jmp     loc_1800915EB
0x180090cd8  xor     edx, edx
0x180090cda  lea     rcx, [rsp+3D0h+hkey]
0x180090cdf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180090ce4  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180090ce9  lea     rax, [rsp+3D0h+hkey]
0x180090cee  mov     r9d, 20019h; samDesired
0x180090cf4  mov     [rsp+3D0h+phkResult], rax; unsigned int
0x180090cf9  xor     r8d, r8d; ulOptions
0x180090cfc  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180090d03  call    cs:__imp_RegOpenKeyExW
0x180090d09  cmp     eax, 2
0x180090d0c  jz      short loc_180090D34
0x180090d0e  test    eax, eax
0x180090d10  jz      short loc_180090D34
0x180090d12  mov     rcx, [rbp+2D8h]; this
0x180090d19  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180090d20  mov     r9d, eax; char *
0x180090d23  mov     edx, 1D7h; void *
0x180090d28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180090d2d  mov     ebx, eax
0x180090d2f  jmp     loc_180090CA2
0x180090d34  mov     rcx, [rsp+3D0h+hkey]
0x180090d39  mov     [rsp+3D0h+var_370], rsi
0x180090d3e  test    rcx, rcx
0x180090d41  jnz     loc_180090E62
0x180090d47  mov     rcx, [rsp+3D0h+var_378]; this
0x180090d4c  mov     rdi, rsi
0x180090d4f  test    rcx, rcx
0x180090d52  jz      short loc_180090DAB
0x180090d54  lea     rdx, [rsp+3D0h+var_370]; HKEY *
0x180090d59  call    ?GetUserClassesRootKey@CToken@@UEAAJPEAPEAUHKEY__@@@Z; CToken::GetUserClassesRootKey(HKEY__ * *)
0x180090d5e  test    eax, eax
0x180090d60  js      short loc_180090DAB
0x180090d62  mov     rdi, [rsp+3D0h+var_370]
0x180090d67  lea     rcx, [rbp+2D0h+Buf1]
0x180090d6b  call    _lambda_2b39ab1cb3293c7772a1fea831a058d2___operator__
0x180090d70  mov     ebx, eax
0x180090d72  test    eax, eax
0x180090d74  jns     short loc_180090DAB
0x180090d76  mov     edx, 1EFh; void *
0x180090d7b  mov     rcx, [rbp+2D8h]; this
0x180090d82  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180090d89  mov     r9d, ebx; char *
0x180090d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090d91  cmp     [rsp+3D0h+var_370], rsi
0x180090d96  jz      loc_180090CA2
0x180090d9c  mov     rcx, [rsp+3D0h+var_378]; this
0x180090da1  call    ?ReleaseUserClassesRootKey@CToken@@UEAAJXZ; CToken::ReleaseUserClassesRootKey(void)
0x180090da6  jmp     loc_180090CA2
0x180090dab  mov     [rbp+2D0h+var_350], rsi
0x180090daf  test    rdi, rdi
0x180090db2  jnz     short loc_180090E15
0x180090db4  xor     edx, edx
0x180090db6  lea     rcx, [rbp+2D0h+var_350]
0x180090dba  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180090dbf  lea     rax, [rbp+2D0h+var_350]
0x180090dc3  mov     r9d, 20019h; samDesired
0x180090dc9  xor     r8d, r8d; ulOptions
0x180090dcc  mov     [rsp+3D0h+phkResult], rax; unsigned int
0x180090dd1  lea     rdx, aSoftwareClasse_0; "Software\\Classes"
0x180090dd8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180090ddf  call    cs:__imp_RegOpenKeyExW
0x180090de5  test    eax, eax
0x180090de7  jz      short loc_180090E11
0x180090de9  mov     edx, 1F7h; void *
0x180090dee  mov     rcx, [rbp+2D8h]; this
0x180090df5  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180090dfc  mov     r9d, eax; char *
0x180090dff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180090e04  lea     rcx, [rbp+2D0h+var_350]
0x180090e08  mov     ebx, eax
0x180090e0a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180090e0f  jmp     short loc_180090D91
0x180090e11  mov     rdi, [rbp+2D0h+var_350]
0x180090e15  xor     edx, edx
0x180090e17  lea     rcx, [rsp+3D0h+hkey]
0x180090e1c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180090e21  lea     rax, [rsp+3D0h+hkey]
0x180090e26  mov     r9d, 20019h; samDesired
0x180090e2c  xor     r8d, r8d; ulOptions
0x180090e2f  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180090e34  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180090e3b  mov     rcx, rdi; hKey
0x180090e3e  call    cs:__imp_RegOpenKeyExW
0x180090e44  cmp     eax, 2
0x180090e47  jz      short loc_180090E54
0x180090e49  test    eax, eax
0x180090e4b  jz      short loc_180090E54
0x180090e4d  mov     edx, 1FEh
0x180090e52  jmp     short loc_180090DEE
0x180090e54  lea     rcx, [rbp+2D0h+var_350]
0x180090e58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180090e5d  mov     rcx, [rsp+3D0h+hkey]; hkey
0x180090e62  mov     bl, sil
0x180090e65  test    rcx, rcx
0x180090e68  jz      short loc_180090ED5
0x180090e6a  lea     rax, [rbp+2D0h+var_350]
0x180090e6e  mov     dword ptr [rbp+2D0h+var_350], 4Eh ; 'N'
0x180090e75  mov     [rsp+3D0h+pcbData], rax; pcbData
0x180090e7a  lea     r8, ?AppID@Constants@Catalog@Com@@3QBGB; "AppID"
0x180090e81  lea     rax, [rbp+2D0h+sz]
0x180090e85  mov     r9d, 2; dwFlags
0x180090e8b  mov     [rsp+3D0h+pvData], rax; pvData
0x180090e90  xor     edx, edx; lpSubKey
0x180090e92  mov     [rsp+3D0h+phkResult], rsi; unsigned int
0x180090e97  call    cs:__imp_RegGetValueW
0x180090e9d  test    eax, eax
0x180090e9f  jnz     loc_180090F2A
0x180090ea5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180090eac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180090eb1  test    al, al
0x180090eb3  jz      short loc_180090ED3
0x180090eb5  lea     rdx, [rbp+2D0h+iid]; lpiid
0x180090eb9  lea     rcx, [rbp+2D0h+sz]; lpsz
0x180090ebd  call    cs:__imp_IIDFromString
0x180090ec3  mov     ebx, eax
0x180090ec5  test    eax, eax
0x180090ec7  jns     short loc_180090ED3
0x180090ec9  mov     edx, 20Ch
0x180090ece  jmp     loc_180090D7B
0x180090ed3  mov     bl, 1
0x180090ed5  cmp     [rsp+3D0h+var_370], rsi
0x180090eda  jz      short loc_180090EE6
0x180090edc  mov     rcx, [rsp+3D0h+var_378]; this
0x180090ee1  call    ?ReleaseUserClassesRootKey@CToken@@UEAAJXZ; CToken::ReleaseUserClassesRootKey(void)
0x180090ee6  lea     rcx, [rsp+3D0h+hkey]
0x180090eeb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180090ef0  cmp     [rsp+3D0h+hKey], rsi
0x180090ef5  jz      short loc_180090F01
0x180090ef7  mov     rcx, [rsp+3D0h+var_378]; this
0x180090efc  call    ?ReleasePrivateHiveComRootKey@CToken@@UEAAJXZ; CToken::ReleasePrivateHiveComRootKey(void)
0x180090f01  mov     edx, [rsp+3D0h+var_368]; int
0x180090f05  test    edx, edx
0x180090f07  jz      short loc_180090F13
0x180090f09  mov     rcx, [rsp+3D0h+var_378]; this
0x180090f0e  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x180090f13  test    bl, bl
0x180090f15  jnz     loc_180090B00
0x180090f1b  mov     ebx, 80004015h
0x180090f20  mov     edx, 216h
0x180090f25  jmp     loc_180090C18
0x180090f2a  cmp     eax, 2
0x180090f2d  jz      short loc_180090ED5
  ... truncated ...
```
