# CScmRot::Register(CProcess *,ushort const *,_MnkEqBuf const *,tagInterfaceData const *,tagInterfaceData const *,_FILETIME const *,ulong,ulong,_SCMREGKEY *,uint,HSTRING__ * const * const)

- ea: `0x180091b8c`
- end: `0x180092804`
- name: `?Register@CScmRot@@QEAAJPEAVCProcess@@PEBGPEBU_MnkEqBuf@@PEBUtagInterfaceData@@3PEBU_FILETIME@@KKPEAU_SCMREGKEY@@IQEBQEAUHSTRING__@@@Z`
- size: `3192`
- prototype: `int(CScmRot *__hidden this, struct CProcess *, const unsigned __int16 *, const struct _MnkEqBuf *, const struct tagInterfaceData *, const struct tagInterfaceData *, const struct _FILETIME *, unsigned int, unsigned int, struct _SCMREGKEY *, unsigned int, HSTRING *const)`
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091a30`

## callees

- `0x1800065a4`
- `0x18000caf8`
- `0x180011db0`
- `0x180013d34`
- `0x18001d3a0`
- `0x1800210f8`
- `0x180025950`
- `0x180025b54`
- `0x18002f670`
- `0x18002f704`
- `0x18003483c`
- `0x180035794`
- `0x180035c94`
- `0x180035cb8`
- `0x180039a7c`
- `0x18003f468`
- `0x18003fbd4`
- `0x180040548`
- `0x18004056c`
- `0x1800454f0`
- `0x18004b524`
- `0x180051680`
- `0x180059020`
- `0x1800642f0`
- `0x180064ed0`
- `0x18006bcd0`
- `0x180070074`
- `0x1800700e8`
- `0x180070f50`
- `0x180072ac0`
- `0x180076f30`
- `0x1800817ac`
- `0x180083ff0`
- `0x1800851b8`
- `0x18008678c`
- `0x180086ed8`
- `0x180091b8c`
- `0x18009280c`
- `0x1800932e0`
- `0x180095c0c`
- `0x18009e160`
- `0x1800a7580`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800fb734`
- `0x1800fb85c`
- `0x180112d78`
- `0x180112d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800926ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800926ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009265f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009267c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092699`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800926b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009265f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009267c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180092699`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800926b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092491`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800924ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009252b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009256b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800925ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092491`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800924ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009252b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009256b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800925ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180092032`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180092032`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091e89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091f6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091fd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091e89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091f6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091fd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800927b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800927b3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18009205e`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18009205e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180091d32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180091d32`

## string_xrefs

- `0x180091da5`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180091e14`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180091ea5`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180091f0e`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180091f87`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x1800920dd`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180092225`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x1800922e6`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`
- `0x180092338`: `onecore\com\combase\rpcss\olescm\scmrot.cxx`

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
0x180091b8c  mov     [rsp-8+arg_0], rbx
0x180091b91  push    rbp
0x180091b92  push    rsi
0x180091b93  push    rdi
0x180091b94  push    r12
0x180091b96  push    r13
0x180091b98  push    r14
0x180091b9a  push    r15
0x180091b9c  lea     rbp, [rsp-2A0h]
0x180091ba4  sub     rsp, 3A0h
0x180091bab  mov     rax, cs:__security_cookie
0x180091bb2  xor     rax, rsp
0x180091bb5  mov     [rbp+2D0h+var_40], rax
0x180091bbc  test    byte ptr [rbp+2D0h+arg_40], 2
0x180091bc3  mov     rbx, r8
0x180091bc6  mov     rax, [rbp+2D0h+arg_48]
0x180091bcd  mov     r14, rdx
0x180091bd0  mov     r13, [rbp+2D0h+arg_28]
0x180091bd7  mov     r12, [rbp+2D0h+arg_20]
0x180091bde  mov     rdi, cs:?gpscmrot@@3PEAVCScmRot@@EA; CScmRot * gpscmrot
0x180091be5  mov     r15, [rbp+2D0h+arg_58]
0x180091bec  mov     [rbp+2D0h+SRWLock], rax
0x180091bf0  mov     rax, [rdx+18h]
0x180091bf4  mov     [rsp+3D0h+var_378], rax
0x180091bf9  mov     [rbp+2D0h+var_340], r9
0x180091bfd  mov     [rsp+3D0h+hKey], rbx
0x180091c02  mov     [rbp+2D0h+var_330], rdx
0x180091c06  mov     [rbp+2D0h+var_320], r13
0x180091c0a  mov     [rbp+2D0h+var_328], r12
0x180091c0e  mov     [rbp+2D0h+var_348], rdi
0x180091c12  jnz     short loc_180091C20
0x180091c14  xor     esi, esi
0x180091c16  mov     [rsp+3D0h+var_380], sil
0x180091c1b  jmp     loc_1800923AB
0x180091c20  xor     edx, edx; Val
0x180091c22  lea     rcx, [rbp+2D0h+sz]; void *
0x180091c26  lea     r8d, [rdx+4Eh]; Size
0x180091c2a  call    memset_0
0x180091c2f  movups  xmm1, xmmword ptr [r14+188h]
0x180091c37  lea     rdx, GUID_NULL; Buf2
0x180091c3e  mov     r8d, 10h; Size
0x180091c44  xorps   xmm0, xmm0
0x180091c47  lea     rcx, [rbp+2D0h+Buf1]; Buf1
0x180091c4b  movdqu  [rbp+2D0h+Buf1], xmm1
0x180091c50  movups  xmmword ptr [rbp+2D0h+iid.Data1], xmm0
0x180091c54  call    memcmp_0
0x180091c59  xor     esi, esi
0x180091c5b  test    eax, eax
0x180091c5d  jz      loc_180091D2B
0x180091c63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180091c6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180091c6f  movups  xmm0, xmmword ptr [r14+188h]
0x180091c77  test    al, al
0x180091c79  jz      short loc_180091CF6
0x180091c7b  movdqu  xmmword ptr [rbp+2D0h+iid.Data1], xmm0
0x180091c80  mov     bl, sil
0x180091c83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180091c8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180091c8f  mov     r8, [rsp+3D0h+var_378]; struct CToken *
0x180091c94  lea     rcx, [rbp+2D0h+SubKey]; this
0x180091c9b  xor     r9d, r9d; unsigned __int64
0x180091c9e  test    al, al
0x180091ca0  jnz     loc_1800921D1
0x180091ca6  lea     rdx, [rbp+2D0h+sz]; unsigned __int16 *
0x180091caa  call    ??0CAppidData@@QEAA@PEAGPEAVCToken@@_K@Z; CAppidData::CAppidData(ushort *,CToken *,unsigned __int64)
0x180091caf  mov     dl, 1; bool
0x180091cb1  mov     rcx, r14; struct CProcess *
0x180091cb4  call    ?GetClassicComActivationServerCatalogFlags@@YAKPEAVCProcess@@_N@Z; GetClassicComActivationServerCatalogFlags(CProcess *,bool)
0x180091cb9  mov     [rsp+3D0h+var_390], rsi; HSTRING *
0x180091cbe  lea     rcx, [rbp+2D0h+SubKey]; this
0x180091cc5  mov     dword ptr [rsp+3D0h+var_398], esi; unsigned int
0x180091cc9  mov     r8d, eax; unsigned int
0x180091ccc  mov     [rsp+3D0h+pcbData], rsi; HSTRING *
0x180091cd1  xor     r9d, r9d; unsigned __int16 *
0x180091cd4  mov     dword ptr [rsp+3D0h+pvData], esi; unsigned int
0x180091cd8  xor     edx, edx; struct IComProcessInfo *
0x180091cda  mov     [rsp+3D0h+phkResult], rsi; unsigned __int16 *
0x180091cdf  call    ?Load@CAppidData@@QEAAJPEAUIComProcessInfo@@KPEBG1IQEBQEAUHSTRING__@@I2@Z; CAppidData::Load(IComProcessInfo *,ulong,ushort const *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x180091ce4  test    eax, eax
0x180091ce6  jns     loc_1800920F8
0x180091cec  mov     edx, 265h
0x180091cf1  jmp     loc_18009221E
0x180091cf6  lea     rdx, [rbp+2D0h+Buf1]; rguid
0x180091cfa  lea     rcx, [rbp+2D0h+var_2F0]; lpsz
0x180091cfe  movdqu  [rbp+2D0h+Buf1], xmm0
0x180091d03  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180091d08  mov     r8, rax; unsigned __int16 *
0x180091d0b  lea     rcx, [rbp+2D0h+sz]; unsigned __int16 *
0x180091d0f  mov     edx, 27h ; '''; unsigned __int64
0x180091d14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180091d19  test    eax, eax
0x180091d1b  jns     loc_180091C80
0x180091d21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180091d26  jmp     loc_180091C80
0x180091d2b  mov     rcx, [r14+180h]; pszPath
0x180091d32  call    cs:__imp_PathFindFileNameW
0x180091d39  nop     dword ptr [rax+rax+00h]
0x180091d3e  mov     ecx, dword ptr cs:aAppid+8; "D\\"
0x180091d44  xor     edx, edx; Val
0x180091d46  movsd   xmm0, qword ptr cs:aAppid; "AppID\\"
0x180091d4e  mov     r8d, 1FAh; Size
0x180091d54  mov     [rbp+2D0h+var_248], ecx
0x180091d5a  mov     rbx, rax
0x180091d5d  movzx   ecx, word ptr cs:aAppid+0Ch; ""
0x180091d64  mov     [rbp+2D0h+var_244], cx
0x180091d6b  lea     rcx, [rbp+2D0h+var_242]; void *
0x180091d72  movsd   qword ptr [rbp+2D0h+SubKey], xmm0
0x180091d7a  call    memset_0
0x180091d7f  mov     r8, rbx; unsigned __int16 *
0x180091d82  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x180091d89  mov     edx, 104h; unsigned __int64
0x180091d8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180091d93  mov     ebx, eax
0x180091d95  test    eax, eax
0x180091d97  jns     short loc_180091DB9
0x180091d99  mov     edx, 1A9h; void *
0x180091d9e  mov     rcx, [rbp+2D8h]; this
0x180091da5  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180091dac  mov     r9d, ebx; char *
0x180091daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091db4  jmp     loc_1800927D7
0x180091db9  lea     rax, [rsp+3D0h+var_368]
0x180091dbe  mov     [rsp+3D0h+var_368], esi
0x180091dc2  mov     qword ptr [rbp+2D0h+Buf1], rax
0x180091dc6  lea     rax, [rsp+3D0h+var_378]
0x180091dcb  mov     qword ptr [rbp+2D0h+Buf1+8], rax
0x180091dcf  mov     eax, [r14+5Ch]
0x180091dd3  mov     [rsp+3D0h+hKey], rsi
0x180091dd8  mov     [rsp+3D0h+hkey], rsi
0x180091ddd  bt      eax, 0Eh
0x180091de1  jnb     loc_180091EC0
0x180091de7  mov     rcx, [rsp+3D0h+var_378]; this
0x180091dec  lea     rdx, [rsp+3D0h+hKey]; HKEY *
0x180091df1  call    ?GetPrivateHiveComRootKey@CToken@@UEAAJPEAPEAUHKEY__@@@Z; CToken::GetPrivateHiveComRootKey(HKEY__ * *)
0x180091df6  test    eax, eax
0x180091df8  js      loc_180091EC0
0x180091dfe  lea     rcx, [rbp+2D0h+Buf1]
0x180091e02  call    _lambda_2b39ab1cb3293c7772a1fea831a058d2___operator__
0x180091e07  mov     ebx, eax
0x180091e09  test    eax, eax
0x180091e0b  jns     short loc_180091E5E
0x180091e0d  mov     rcx, [rbp+2D8h]; this
0x180091e14  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180091e1b  mov     r9d, eax; char *
0x180091e1e  mov     edx, 1D1h; void *
0x180091e23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091e28  lea     rcx, [rsp+3D0h+hkey]
0x180091e2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091e32  cmp     [rsp+3D0h+hKey], rsi
0x180091e37  jz      short loc_180091E43
0x180091e39  mov     rcx, [rsp+3D0h+var_378]; this
0x180091e3e  call    ?ReleasePrivateHiveComRootKey@CToken@@UEAAJXZ; CToken::ReleasePrivateHiveComRootKey(void)
0x180091e43  mov     edx, [rsp+3D0h+var_368]; int
0x180091e47  test    edx, edx
0x180091e49  jz      loc_1800927D7
0x180091e4f  mov     rcx, [rsp+3D0h+var_378]; this
0x180091e54  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x180091e59  jmp     loc_1800927D7
0x180091e5e  xor     edx, edx
0x180091e60  lea     rcx, [rsp+3D0h+hkey]
0x180091e65  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180091e6a  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180091e6f  lea     rax, [rsp+3D0h+hkey]
0x180091e74  mov     r9d, 20019h; samDesired
0x180091e7a  mov     [rsp+3D0h+phkResult], rax; unsigned int
0x180091e7f  xor     r8d, r8d; ulOptions
0x180091e82  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180091e89  call    cs:__imp_RegOpenKeyExW
0x180091e90  nop     dword ptr [rax+rax+00h]
0x180091e95  cmp     eax, 2
0x180091e98  jz      short loc_180091EC0
0x180091e9a  test    eax, eax
0x180091e9c  jz      short loc_180091EC0
0x180091e9e  mov     rcx, [rbp+2D8h]; this
0x180091ea5  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180091eac  mov     r9d, eax; char *
0x180091eaf  mov     edx, 1D7h; void *
0x180091eb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180091eb9  mov     ebx, eax
0x180091ebb  jmp     loc_180091E28
0x180091ec0  mov     rcx, [rsp+3D0h+hkey]
0x180091ec5  mov     [rsp+3D0h+var_370], rsi
0x180091eca  test    rcx, rcx
0x180091ecd  jnz     loc_180091FFD
0x180091ed3  mov     rcx, [rsp+3D0h+var_378]; this
0x180091ed8  mov     rdi, rsi
0x180091edb  test    rcx, rcx
0x180091ede  jz      short loc_180091F37
0x180091ee0  lea     rdx, [rsp+3D0h+var_370]; HKEY *
0x180091ee5  call    ?GetUserClassesRootKey@CToken@@UEAAJPEAPEAUHKEY__@@@Z; CToken::GetUserClassesRootKey(HKEY__ * *)
0x180091eea  test    eax, eax
0x180091eec  js      short loc_180091F37
0x180091eee  mov     rdi, [rsp+3D0h+var_370]
0x180091ef3  lea     rcx, [rbp+2D0h+Buf1]
0x180091ef7  call    _lambda_2b39ab1cb3293c7772a1fea831a058d2___operator__
0x180091efc  mov     ebx, eax
0x180091efe  test    eax, eax
0x180091f00  jns     short loc_180091F37
0x180091f02  mov     edx, 1EFh; void *
0x180091f07  mov     rcx, [rbp+2D8h]; this
0x180091f0e  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180091f15  mov     r9d, ebx; char *
0x180091f18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091f1d  cmp     [rsp+3D0h+var_370], rsi
0x180091f22  jz      loc_180091E28
0x180091f28  mov     rcx, [rsp+3D0h+var_378]; this
0x180091f2d  call    ?ReleaseUserClassesRootKey@CToken@@UEAAJXZ; CToken::ReleaseUserClassesRootKey(void)
0x180091f32  jmp     loc_180091E28
0x180091f37  mov     [rbp+2D0h+var_350], rsi
0x180091f3b  test    rdi, rdi
0x180091f3e  jnz     short loc_180091FAA
0x180091f40  xor     edx, edx
0x180091f42  lea     rcx, [rbp+2D0h+var_350]
0x180091f46  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180091f4b  lea     rax, [rbp+2D0h+var_350]
0x180091f4f  mov     r9d, 20019h; samDesired
0x180091f55  xor     r8d, r8d; ulOptions
0x180091f58  mov     [rsp+3D0h+phkResult], rax; unsigned int
0x180091f5d  lea     rdx, aSoftwareClasse_0; "Software\\Classes"
0x180091f64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091f6b  call    cs:__imp_RegOpenKeyExW
0x180091f72  nop     dword ptr [rax+rax+00h]
0x180091f77  test    eax, eax
0x180091f79  jz      short loc_180091FA6
0x180091f7b  mov     edx, 1F7h; void *
0x180091f80  mov     rcx, [rbp+2D8h]; this
0x180091f87  lea     r8, aOnecoreComComb_65; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180091f8e  mov     r9d, eax; char *
0x180091f91  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180091f96  lea     rcx, [rbp+2D0h+var_350]
0x180091f9a  mov     ebx, eax
0x180091f9c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091fa1  jmp     loc_180091F1D
0x180091fa6  mov     rdi, [rbp+2D0h+var_350]
0x180091faa  xor     edx, edx
0x180091fac  lea     rcx, [rsp+3D0h+hkey]
0x180091fb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180091fb6  lea     rax, [rsp+3D0h+hkey]
0x180091fbb  mov     r9d, 20019h; samDesired
0x180091fc1  xor     r8d, r8d; ulOptions
0x180091fc4  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180091fc9  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180091fd0  mov     rcx, rdi; hKey
0x180091fd3  call    cs:__imp_RegOpenKeyExW
0x180091fda  nop     dword ptr [rax+rax+00h]
0x180091fdf  cmp     eax, 2
0x180091fe2  jz      short loc_180091FEF
0x180091fe4  test    eax, eax
0x180091fe6  jz      short loc_180091FEF
0x180091fe8  mov     edx, 1FEh
0x180091fed  jmp     short loc_180091F80
0x180091fef  lea     rcx, [rbp+2D0h+var_350]
0x180091ff3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180091ff8  mov     rcx, [rsp+3D0h+hkey]; hkey
0x180091ffd  mov     bl, sil
0x180092000  test    rcx, rcx
0x180092003  jz      short loc_18009207C
0x180092005  lea     rax, [rbp+2D0h+var_350]
0x180092009  mov     dword ptr [rbp+2D0h+var_350], 4Eh ; 'N'
0x180092010  mov     [rsp+3D0h+pcbData], rax; pcbData
0x180092015  lea     r8, ?AppID@Constants@Catalog@Com@@3QBGB; "AppID"
0x18009201c  lea     rax, [rbp+2D0h+sz]
0x180092020  mov     r9d, 2; dwFlags
0x180092026  mov     [rsp+3D0h+pvData], rax; pvData
0x18009202b  xor     edx, edx; lpSubKey
0x18009202d  mov     [rsp+3D0h+phkResult], rsi; unsigned int
0x180092032  call    cs:__imp_RegGetValueW
0x180092039  nop     dword ptr [rax+rax+00h]
0x18009203e  test    eax, eax
0x180092040  jnz     loc_1800920D1
0x180092046  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18009204d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180092052  test    al, al
0x180092054  jz      short loc_18009207A
0x180092056  lea     rdx, [rbp+2D0h+iid]; lpiid
0x18009205a  lea     rcx, [rbp+2D0h+sz]; lpsz
0x18009205e  call    cs:__imp_IIDFromString
0x180092065  nop     dword ptr [rax+rax+00h]
0x18009206a  mov     ebx, eax
0x18009206c  test    eax, eax
0x18009206e  jns     short loc_18009207A
0x180092070  mov     edx, 20Ch
0x180092075  jmp     loc_180091F07
0x18009207a  mov     bl, 1
0x18009207c  cmp     [rsp+3D0h+var_370], rsi
0x180092081  jz      short loc_18009208D
0x180092083  mov     rcx, [rsp+3D0h+var_378]; this
0x180092088  call    ?ReleaseUserClassesRootKey@CToken@@UEAAJXZ; CToken::ReleaseUserClassesRootKey(void)
0x18009208d  lea     rcx, [rsp+3D0h+hkey]
0x180092092  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180092097  cmp     [rsp+3D0h+hKey], rsi
0x18009209c  jz      short loc_1800920A8
0x18009209e  mov     rcx, [rsp+3D0h+var_378]; this
0x1800920a3  call    ?ReleasePrivateHiveComRootKey@CToken@@UEAAJXZ; CToken::ReleasePrivateHiveComRootKey(void)
0x1800920a8  mov     edx, [rsp+3D0h+var_368]; int
0x1800920ac  test    edx, edx
0x1800920ae  jz      short loc_1800920BA
0x1800920b0  mov     rcx, [rsp+3D0h+var_378]; this
0x1800920b5  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x1800920ba  test    bl, bl
  ... truncated ...
```
