# HandleEnumDevices(ushort const *,unsigned __int64,ulong *,__MIDL_liveidsvc_0002 * *)

- ea: `0x180099d08`
- end: `0x18009a7fa`
- name: `?HandleEnumDevices@@YAJPEBG_KPEAKPEAPEAU__MIDL_liveidsvc_0002@@@Z`
- size: `2802`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int *, struct __MIDL_liveidsvc_0002 **)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180099bf0`

## callees

- `0x180006ac0`
- `0x180007da0`
- `0x18000c050`
- `0x18000dc34`
- `0x18000ed04`
- `0x18000fd04`
- `0x1800151c4`
- `0x180015860`
- `0x180015fdc`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001f968`
- `0x180023d24`
- `0x180030120`
- `0x180033218`
- `0x180035520`
- `0x180038a80`
- `0x180039d00`
- `0x18003fb3c`
- `0x180043344`
- `0x180053620`
- `0x180099d08`
- `0x1800a3b60`
- `0x1800a4778`
- `0x1800aec44`
- `0x1800af41c`
- `0x1800afce0`
- `0x1800b13bc`
- `0x1800dff90`
- `0x1800ece24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a228`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a228`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a679`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a6e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a719`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a749`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a679`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a6e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a719`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009a749`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009a368`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009a624`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009a368`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009a624`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009a063`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18009a063`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009a16b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009a16b`

## string_xrefs

- `0x180099e02`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099e42`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099e8e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099ec6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099fdf`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009a08c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009a1b0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009a43b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009a515`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099e26`: `hr = client.ImpersonateClient()`
- `0x180099fd2`: `Open for %ls failed with hr=%x`
- `0x18009a41f`: `hr = StringCchCopyW(rgDeviceInfo[dwCount].wszDeviceId, length + 1, wszDeviceId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall HandleEnumDevices(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned int *a3,
        struct __MIDL_liveidsvc_0002 **a4)
{
  char v6; // r12
  unsigned int v8; // esi
  void *v9; // r14
  int v10; // eax
  int v11; // eax
  int IsCallerAdminEnabled; // eax
  struct CClientConfigDataCacheManager *v13; // rax
  const unsigned __int16 *v14; // rdi
  HKEY *CurrentUserKey; // rax
  signed int v16; // edi
  struct CClientConfigDataCacheManager *v17; // rax
  _QWORD *DeviceIdentityStoreRegRoot; // rax
  int v19; // eax
  unsigned int v20; // r15d
  DWORD i; // r12d
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdi
  void *v25; // r14
  unsigned __int16 *v26; // r14
  unsigned __int16 **v27; // rax
  int v28; // eax
  __int64 v29; // r14
  int v30; // edi
  int v31; // eax
  int v32; // eax
  struct __MIDL_liveidsvc_0002 *v33; // rax
  unsigned int j; // edi
  __int128 *v35; // rax
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int64 v38; // rsi
  __int64 v39; // rax
  unsigned __int64 k; // rdi
  void **v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  unsigned int v44; // ebx
  const unsigned __int16 *lpcSubKeys; // [rsp+20h] [rbp-3B8h]
  LPDWORD lpcSubKeysa; // [rsp+20h] [rbp-3B8h]
  LPDWORD lpcSubKeysb; // [rsp+20h] [rbp-3B8h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-3B0h]
  int DeviceID; // [rsp+60h] [rbp-378h] BYREF
  unsigned __int16 *v51; // [rsp+68h] [rbp-370h] BYREF
  __int64 v52; // [rsp+70h] [rbp-368h] BYREF
  __int64 v53; // [rsp+78h] [rbp-360h] BYREF
  __int64 v54; // [rsp+80h] [rbp-358h] BYREF
  void **v55; // [rsp+88h] [rbp-350h] BYREF
  __int64 v56; // [rsp+90h] [rbp-348h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-340h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-338h] BYREF
  __int64 *v59; // [rsp+A8h] [rbp-330h] BYREF
  void *v60; // [rsp+B0h] [rbp-328h] BYREF
  unsigned __int64 v61; // [rsp+B8h] [rbp-320h]
  __int64 v62; // [rsp+C0h] [rbp-318h]
  int v63; // [rsp+C8h] [rbp-310h]
  int v64; // [rsp+D0h] [rbp-308h] BYREF
  DWORD cchName; // [rsp+D4h] [rbp-304h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-300h] BYREF
  HKEY hKey[4]; // [rsp+E0h] [rbp-2F8h] BYREF
  __int64 v68; // [rsp+100h] [rbp-2D8h]
  unsigned __int16 *v69; // [rsp+108h] [rbp-2D0h]
  unsigned int *v70; // [rsp+110h] [rbp-2C8h]
  __int64 v71; // [rsp+118h] [rbp-2C0h] BYREF
  __int64 v72; // [rsp+120h] [rbp-2B8h] BYREF
  __int64 v73; // [rsp+128h] [rbp-2B0h] BYREF
  _OWORD v74[2]; // [rsp+130h] [rbp-2A8h] BYREF
  _QWORD v75[8]; // [rsp+150h] [rbp-288h] BYREF
  WCHAR Name[256]; // [rsp+190h] [rbp-248h] BYREF

  v70 = a3;
  v6 = a2;
  v68 = a2;
  v69 = a1;
  DeviceID = 0;
  v66 = 0;
  v73 = 0;
  v8 = *a3;
  v64 = 0;
  memset(hKey, 0, 24);
  cSubKeys = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  v9 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v75[0] = "HandleEnumDevices";
  v75[1] = &DeviceID;
  v75[2] = 0;
  v75[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleEnumDevices",
    (const char *)0x1919,
    0,
    lpcSubKeys);
  v10 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v66, 0);
  DeviceID = v10;
  if ( v10 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumDevices",
      0x191Bu,
      v10,
      "hr = client.ImpersonateClient()");
    goto LABEL_58;
  }
  if ( !a4 || !a1 )
  {
    DeviceID = -2147188642;
    goto LABEL_58;
  }
  v11 = DeviceIdHelpers::VerifyInitialization();
  DeviceID = v11;
  if ( v11 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumDevices",
      0x1926u,
      v11,
      "hr = DeviceIdHelpers::VerifyInitialization()");
    goto LABEL_58;
  }
  IsCallerAdminEnabled = DeviceIdHelpers::IsCallerAdminEnabled(&v64);
  DeviceID = IsCallerAdminEnabled;
  if ( IsCallerAdminEnabled < 0 )
  {
    LODWORD(lpcSubKeysa) = IsCallerAdminEnabled;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x192Eu,
      L"IsCallerAdminEnabled failed with hr = 0x%x",
      lpcSubKeysa);
    goto LABEL_58;
  }
  if ( !v64 )
  {
    DeviceID = -2147188638;
    goto LABEL_58;
  }
  if ( (v6 & 0x20) != 0 )
  {
    DeviceID = 0;
    goto LABEL_58;
  }
  *a4 = 0;
  LODWORD(v55) = 0;
  v56 = 0;
  CAutoRevertToSelf::Revert((void **)&v55, 0);
  v13 = CClientConfigDataCacheManager::theConfigDataManager();
  v14 = *(const unsigned __int16 **)CClientConfigDataCacheManager::GetDeviceIdentityStoreRegRoot(v13, &v59);
  CurrentUserKey = (HKEY *)GetCurrentUserKey(v74);
  v16 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *CurrentUserKey, v14, 0x20019u);
  ATL::CRegKey::Close((ATL::CRegKey *)v74);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  if ( v16 == 2 )
  {
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v55);
    goto LABEL_58;
  }
  if ( v16 )
  {
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    DeviceID = v16;
    v17 = CClientConfigDataCacheManager::theConfigDataManager();
    DeviceIdentityStoreRegRoot = (_QWORD *)CClientConfigDataCacheManager::GetDeviceIdentityStoreRegRoot(v17, &v59);
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x194Du,
      L"Open for %ls failed with hr=%x",
      *DeviceIdentityStoreRegRoot,
      v16);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
    DeviceID = -2147188658;
    CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v55);
    goto LABEL_58;
  }
  CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v55);
  v19 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v19 )
  {
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    DeviceID = v19;
    LODWORD(lpcSubKeysb) = v19;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1965u,
      L"RegQueryInfoKey failed with hr=%x",
      lpcSubKeysb);
    DeviceID = -2147188658;
    goto LABEL_58;
  }
  if ( v8 == -1 )
  {
    *a3 = cSubKeys;
    DeviceID = 0;
    goto LABEL_58;
  }
  v20 = 0;
  for ( i = 0; i < cSubKeys; ++i )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
    memset_0(Name, 0, 0x1FEu);
    cchName = 255;
    v56 = 0;
    v55 = &SmartPCCERT_CONTEXT::`vftable';
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
    v54 = 0;
    v51 = 0;
    v22 = RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0);
    if ( v22 == 259 )
    {
      CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
      break;
    }
    if ( v22 )
    {
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      DeviceID = v22;
      LODWORD(lpcbMaxSubKeyLen) = v22;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x198Bu,
        L"RegEnumKeyEx for %ls failed with hr=%x",
        Name,
        lpcbMaxSubKeyLen);
      DeviceID = -2147188658;
      CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
      goto LABEL_58;
    }
    if ( !(unsigned int)_o__wcsicmp(Name, L"PhysicalDeviceID") )
      goto LABEL_33;
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v52, Name);
    v59 = &v52;
    v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( !*(_QWORD *)(v23 + 16) )
      *(_QWORD *)(v23 + 16) = &v52;
    DeviceID = DeviceIdHelpers::RetrieveDeviceID(
                 v69,
                 (unsigned int)v68 & 0xFFFFFFB7,
                 (__int64)&v56,
                 (__int64)&v53,
                 (__int64)&v54);
    if ( DeviceID < 0 )
    {
      WlidsvcSmartTls<ImpersonationInformation,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~WlidsvcSmartTls<ImpersonationInformation,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>((__int64 *)&v59);
LABEL_33:
      CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
      goto LABEL_47;
    }
    WlidsvcSmartTls<ImpersonationInformation,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~WlidsvcSmartTls<ImpersonationInformation,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>((__int64 *)&v59);
    memset(v74, 0, sizeof(v74));
    ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::Add(&v60, v74);
    v24 = -1;
    do
      ++v24;
    while ( v51[v24] );
    v25 = malloc(2 * v24 + 2);
    *(_QWORD *)ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](&v60, v20) = v25;
    if ( !*(_QWORD *)ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                       &v60,
                       v20) )
    {
      DeviceID = -2147024882;
      CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
      goto LABEL_58;
    }
    v26 = v51;
    v27 = (unsigned __int16 **)ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                                 &v60,
                                 v20);
    v28 = StringCchCopyW(*v27, v24 + 1, v26);
    DeviceID = v28;
    if ( v28 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleEnumDevices",
        0x19C1u,
        v28,
        "hr = StringCchCopyW(rgDeviceInfo[dwCount].wszDeviceId, length + 1, wszDeviceId)");
      CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
      goto LABEL_58;
    }
    v29 = ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](&v60, v20);
    v30 = ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](&v60, v20);
    v31 = ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](&v60, v20);
    v32 = ConstructDeviceInfo(v56, (unsigned int)&v53, v31 + 8, v30 + 24, v29 + 16);
    DeviceID = v32;
    if ( v32 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleEnumDevices",
        0x19C8u,
        v32,
        "hr = ConstructDeviceInfo(pCertContext, pszKeypair, &rgDeviceInfo[dwCount].wszKeypair, &rgDeviceInfo[dwCount].pbD"
        "eviceCert, &rgDeviceInfo[dwCount].cbDeviceCert )");
      CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
      SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
      goto LABEL_58;
    }
    ++v20;
    CPassportStringW::~CPassportStringW((CPassportStringW *)&v51);
    CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v55);
    v9 = v60;
LABEL_47:
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
  }
  DeviceID = 0;
  v33 = (struct __MIDL_liveidsvc_0002 *)malloc(32LL * v20);
  *a4 = v33;
  if ( v33 )
  {
    for ( j = 0; j < v20; ++j )
    {
      v35 = (__int128 *)ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                          &v60,
                          j);
      v36 = *v35;
      v37 = v35[1];
      v38 = 32LL * j;
      v39 = (__int64)*a4;
      *(_OWORD *)(v38 + v39) = v36;
      *(_OWORD *)(v38 + v39 + 16) = v37;
    }
    if ( v9 )
    {
      free(v9);
      v60 = 0;
    }
    v61 = 0;
    v62 = 0;
    *v70 = v20;
  }
  else
  {
    DeviceID = -2147024882;
  }
LABEL_58:
  for ( k = 0; k < v61; ++k )
  {
    if ( *(_QWORD *)ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                      &v60,
                      k) )
    {
      v41 = (void **)ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                       &v60,
                       k);
      free(*v41);
    }
    if ( *(_QWORD *)(ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                       &v60,
                       k)
                   + 8) )
    {
      v42 = ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](&v60, k);
      free(*(void **)(v42 + 8));
    }
    if ( *(_QWORD *)(ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](
                       &v60,
                       k)
                   + 24) )
    {
      v43 = ATL::CAtlArray<__MIDL_liveidsvc_0002,ATL::CElementTraits<__MIDL_liveidsvc_0002>>::operator[](&v60, k);
      free(*(void **)(v43 + 24));
    }
  }
  v44 = DeviceID;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v75);
  ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v60);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v73);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v66);
  return v44;
}

```

## disassembly

```asm
0x180099d08  mov     r11, rsp
0x180099d0b  push    rbx
0x180099d0c  push    rsi
0x180099d0d  push    rdi
0x180099d0e  push    r12
0x180099d10  push    r13
0x180099d12  push    r14
0x180099d14  push    r15
0x180099d16  sub     rsp, 3A0h
0x180099d1d  mov     rax, cs:__security_cookie
0x180099d24  xor     rax, rsp
0x180099d27  mov     [rsp+3D8h+var_48], rax
0x180099d2f  mov     r13, r9
0x180099d32  mov     r15, r8
0x180099d35  mov     [rsp+3D8h+var_2C8], r8
0x180099d3d  mov     r12, rdx
0x180099d40  mov     [rsp+3D8h+var_2D8], rdx
0x180099d48  mov     rdi, rcx
0x180099d4b  mov     [rsp+3D8h+var_2D0], rcx
0x180099d53  xor     ebx, ebx
0x180099d55  mov     [rsp+3D8h+var_378], ebx
0x180099d59  mov     [r11-300h], rbx
0x180099d60  mov     [r11-2B0h], rbx
0x180099d67  mov     esi, [r8]
0x180099d6a  mov     [rsp+3D8h+var_308], ebx
0x180099d71  mov     [r11-2F8h], rbx
0x180099d78  mov     [r11-2F0h], rbx
0x180099d7f  mov     [r11-2E8h], rbx
0x180099d86  mov     [rsp+3D8h+cSubKeys], ebx
0x180099d8d  lea     rcx, [r11-2B8h]
0x180099d94  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180099d99  nop
0x180099d9a  lea     rcx, [rsp+3D8h+var_2C0]
0x180099da2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180099da7  nop
0x180099da8  mov     r14d, ebx
0x180099dab  mov     [rsp+3D8h+var_328], rbx
0x180099db3  mov     [rsp+3D8h+var_320], rbx
0x180099dbb  mov     [rsp+3D8h+var_318], rbx
0x180099dc3  mov     [rsp+3D8h+var_310], ebx
0x180099dca  lea     rcx, aHandleenumdevi; "HandleEnumDevices"
0x180099dd1  mov     [rsp+3D8h+var_288], rcx
0x180099dd9  lea     rax, [rsp+3D8h+var_378]
0x180099dde  mov     [rsp+3D8h+var_280], rax
0x180099de6  mov     [rsp+3D8h+var_278], rbx
0x180099dee  mov     [rsp+3D8h+var_270], rbx
0x180099df6  xor     r9d, r9d; unsigned int
0x180099df9  mov     r8d, 1919h; char *
0x180099dff  mov     rdx, rcx; char *
0x180099e02  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180099e09  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180099e0e  nop
0x180099e0f  xor     edx, edx; struct ATL::CAccessToken *
0x180099e11  lea     rcx, [rsp+3D8h+var_300]; this
0x180099e19  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x180099e1e  mov     [rsp+3D8h+var_378], eax
0x180099e22  test    eax, eax
0x180099e24  jns     short loc_180099E53
0x180099e26  lea     r8, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x180099e2d  mov     [rsp+3D8h+lpcSubKeys], r8; char *
0x180099e32  mov     r9d, eax; int
0x180099e35  mov     r8d, 191Bh; unsigned int
0x180099e3b  lea     rdx, aHandleenumdevi; "HandleEnumDevices"
0x180099e42  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180099e49  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180099e4e  jmp     loc_18009A6B0
0x180099e53  test    r13, r13
0x180099e56  jz      loc_18009A6A4
0x180099e5c  test    rdi, rdi
0x180099e5f  jz      loc_18009A6A4
0x180099e65  call    ?VerifyInitialization@DeviceIdHelpers@@SAJXZ; DeviceIdHelpers::VerifyInitialization(void)
0x180099e6a  mov     [rsp+3D8h+var_378], eax
0x180099e6e  test    eax, eax
0x180099e70  jns     short loc_180099EA0
0x180099e72  lea     rcx, aHrDeviceidhelp_11; "hr = DeviceIdHelpers::VerifyInitializat"...
0x180099e79  mov     [rsp+3D8h+lpcSubKeys], rcx; char *
0x180099e7e  mov     r9d, eax; int
0x180099e81  mov     r8d, 1926h; unsigned int
0x180099e87  lea     rdx, aHandleenumdevi; "HandleEnumDevices"
0x180099e8e  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180099e95  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180099e9a  nop
0x180099e9b  jmp     loc_18009A6B0
0x180099ea0  lea     rcx, [rsp+3D8h+var_308]; int *
0x180099ea8  call    ?IsCallerAdminEnabled@DeviceIdHelpers@@SAJAEAH@Z; DeviceIdHelpers::IsCallerAdminEnabled(int &)
0x180099ead  mov     [rsp+3D8h+var_378], eax
0x180099eb1  test    eax, eax
0x180099eb3  jns     short loc_180099EDD
0x180099eb5  mov     dword ptr [rsp+3D8h+lpcSubKeys], eax
0x180099eb9  lea     r9, aIscalleradmine; "IsCallerAdminEnabled failed with hr = 0"...
0x180099ec0  mov     r8d, 192Eh; unsigned int
0x180099ec6  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180099ecd  mov     ecx, 5; unsigned __int8
0x180099ed2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180099ed7  nop
0x180099ed8  jmp     loc_18009A6B0
0x180099edd  cmp     [rsp+3D8h+var_308], ebx
0x180099ee4  jnz     short loc_180099EF3
0x180099ee6  mov     [rsp+3D8h+var_378], 80048062h
0x180099eee  jmp     loc_18009A6B0
0x180099ef3  test    r12b, 20h
0x180099ef7  jz      short loc_180099F02
0x180099ef9  mov     [rsp+3D8h+var_378], ebx
0x180099efd  jmp     loc_18009A6B0
0x180099f02  mov     [r13+0], rbx
0x180099f06  mov     dword ptr [rsp+3D8h+var_350], ebx
0x180099f0d  mov     [rsp+3D8h+var_348], rbx
0x180099f15  xor     edx, edx; int
0x180099f17  lea     rcx, [rsp+3D8h+var_350]; this
0x180099f1f  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x180099f24  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x180099f29  lea     rdx, [rsp+3D8h+var_330]
0x180099f31  mov     rcx, rax
0x180099f34  call    ?GetDeviceIdentityStoreRegRoot@CClientConfigDataCacheManager@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CClientConfigDataCacheManager::GetDeviceIdentityStoreRegRoot(void)
0x180099f39  nop
0x180099f3a  mov     rdi, [rax]
0x180099f3d  lea     rcx, [rsp+3D8h+var_2A8]
0x180099f45  call    ?GetCurrentUserKey@@YA?AVCRegKey@ATL@@XZ; GetCurrentUserKey(void)
0x180099f4a  mov     r9d, 20019h; unsigned int
0x180099f50  mov     r8, rdi; unsigned __int16 *
0x180099f53  mov     rdx, [rax]; HKEY
0x180099f56  lea     rcx, [rsp+3D8h+hKey]; this
0x180099f5e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180099f63  mov     edi, eax
0x180099f65  lea     rcx, [rsp+3D8h+var_2A8]; this
0x180099f6d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180099f72  nop
0x180099f73  lea     rcx, [rsp+3D8h+var_330]
0x180099f7b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180099f80  mov     r12d, 2
0x180099f86  cmp     edi, r12d
0x180099f89  jnz     short loc_180099F9E
0x180099f8b  lea     rcx, [rsp+3D8h+var_350]; this
0x180099f93  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x180099f98  nop
0x180099f99  jmp     loc_18009A6B0
0x180099f9e  test    edi, edi
0x180099fa0  jz      short loc_18009A016
0x180099fa2  jle     short loc_180099FAD
0x180099fa4  movzx   edi, di
0x180099fa7  or      edi, 80070000h
0x180099fad  mov     [rsp+3D8h+var_378], edi
0x180099fb1  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x180099fb6  lea     rdx, [rsp+3D8h+var_330]
0x180099fbe  mov     rcx, rax
0x180099fc1  call    ?GetDeviceIdentityStoreRegRoot@CClientConfigDataCacheManager@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CClientConfigDataCacheManager::GetDeviceIdentityStoreRegRoot(void)
0x180099fc6  mov     dword ptr [rsp+3D8h+lpcbMaxSubKeyLen], edi
0x180099fca  mov     rax, [rax]
0x180099fcd  mov     [rsp+3D8h+lpcSubKeys], rax
0x180099fd2  lea     r9, aOpenForLsFaile; "Open for %ls failed with hr=%x"
0x180099fd9  mov     r8d, 194Dh; unsigned int
0x180099fdf  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180099fe6  mov     ecx, r12d; unsigned __int8
0x180099fe9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180099fee  lea     rcx, [rsp+3D8h+var_330]
0x180099ff6  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180099ffb  mov     [rsp+3D8h+var_378], 8004804Eh
0x18009a003  lea     rcx, [rsp+3D8h+var_350]; this
0x18009a00b  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x18009a010  nop
0x18009a011  jmp     loc_18009A6B0
0x18009a016  lea     rcx, [rsp+3D8h+var_350]; this
0x18009a01e  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x18009a023  mov     [rsp+3D8h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18009a028  mov     [rsp+3D8h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18009a02d  mov     [rsp+3D8h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18009a032  mov     [rsp+3D8h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18009a037  mov     [rsp+3D8h+lpcValues], rbx; lpcValues
0x18009a03c  mov     [rsp+3D8h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18009a041  mov     [rsp+3D8h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18009a046  lea     rax, [rsp+3D8h+cSubKeys]
0x18009a04e  mov     [rsp+3D8h+lpcSubKeys], rax; lpcSubKeys
0x18009a053  xor     r9d, r9d; lpReserved
0x18009a056  xor     r8d, r8d; lpcchClass
0x18009a059  xor     edx, edx; lpClass
0x18009a05b  mov     rcx, [rsp+3D8h+hKey]; hKey
0x18009a063  call    cs:__imp_RegQueryInfoKeyW
0x18009a069  test    eax, eax
0x18009a06b  jz      short loc_18009A0A8
0x18009a06d  jle     short loc_18009A077
0x18009a06f  movzx   eax, ax
0x18009a072  or      eax, 80070000h
0x18009a077  mov     [rsp+3D8h+var_378], eax
0x18009a07b  mov     dword ptr [rsp+3D8h+lpcSubKeys], eax
0x18009a07f  lea     r9, aRegqueryinfoke; "RegQueryInfoKey failed with hr=%x"
0x18009a086  mov     r8d, 1965h; unsigned int
0x18009a08c  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009a093  mov     ecx, r12d; unsigned __int8
0x18009a096  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009a09b  mov     [rsp+3D8h+var_378], 8004804Eh
0x18009a0a3  jmp     loc_18009A6B0
0x18009a0a8  cmp     esi, 0FFFFFFFFh
0x18009a0ab  jnz     short loc_18009A0C0
0x18009a0ad  mov     eax, [rsp+3D8h+cSubKeys]
0x18009a0b4  mov     [r15], eax
0x18009a0b7  mov     [rsp+3D8h+var_378], ebx
0x18009a0bb  jmp     loc_18009A6B0
0x18009a0c0  mov     r15d, ebx
0x18009a0c3  mov     r12d, ebx
0x18009a0c6  cmp     r12d, [rsp+3D8h+cSubKeys]
0x18009a0ce  jnb     loc_18009A619
0x18009a0d4  lea     rcx, [rsp+3D8h+var_338]
0x18009a0dc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a0e1  nop
0x18009a0e2  xor     edx, edx; Val
0x18009a0e4  mov     r8d, 1FEh; Size
0x18009a0ea  lea     rcx, [rsp+3D8h+Name]; void *
0x18009a0f2  call    memset_0
0x18009a0f7  mov     [rsp+3D8h+cchName], 0FFh
0x18009a102  mov     [rsp+3D8h+var_348], rbx
0x18009a10a  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18009a111  mov     [rsp+3D8h+var_350], rax
0x18009a119  lea     rcx, [rsp+3D8h+var_360]
0x18009a11e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a123  nop
0x18009a124  lea     rcx, [rsp+3D8h+var_368]
0x18009a129  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a12e  nop
0x18009a12f  mov     [rsp+3D8h+var_358], rbx
0x18009a137  mov     [rsp+3D8h+var_370], rbx
0x18009a13c  mov     [rsp+3D8h+lpcValues], rbx; lpftLastWriteTime
0x18009a141  mov     [rsp+3D8h+lpcbMaxClassLen], rbx; lpcchClass
0x18009a146  mov     [rsp+3D8h+lpcbMaxSubKeyLen], rbx; lpClass
0x18009a14b  mov     [rsp+3D8h+lpcSubKeys], rbx; lpReserved
0x18009a150  lea     r9, [rsp+3D8h+cchName]; lpcchName
0x18009a158  lea     r8, [rsp+3D8h+Name]; lpName
0x18009a160  mov     edx, r12d; dwIndex
0x18009a163  mov     rcx, [rsp+3D8h+hKey]; hKey
0x18009a16b  call    cs:__imp_RegEnumKeyExW
0x18009a171  cmp     eax, 103h
0x18009a176  jz      loc_18009A5CF
0x18009a17c  test    eax, eax
0x18009a17e  jz      loc_18009A219
0x18009a184  jle     short loc_18009A18E
0x18009a186  movzx   eax, ax
0x18009a189  or      eax, 80070000h
0x18009a18e  mov     [rsp+3D8h+var_378], eax
0x18009a192  mov     dword ptr [rsp+3D8h+lpcbMaxSubKeyLen], eax
0x18009a196  lea     rax, [rsp+3D8h+Name]
0x18009a19e  mov     [rsp+3D8h+lpcSubKeys], rax
0x18009a1a3  lea     r9, aRegenumkeyexFo; "RegEnumKeyEx for %ls failed with hr=%x"
0x18009a1aa  mov     r8d, 198Bh; unsigned int
0x18009a1b0  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009a1b7  mov     ecx, 2; unsigned __int8
0x18009a1bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009a1c1  mov     [rsp+3D8h+var_378], 8004804Eh
0x18009a1c9  lea     rcx, [rsp+3D8h+var_370]; this
0x18009a1ce  call    ??1CPassportStringW@@QEAA@XZ; CPassportStringW::~CPassportStringW(void)
0x18009a1d3  nop
0x18009a1d4  lea     rcx, [rsp+3D8h+var_358]
0x18009a1dc  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x18009a1e1  nop
0x18009a1e2  lea     rcx, [rsp+3D8h+var_368]
0x18009a1e7  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a1ec  nop
0x18009a1ed  lea     rcx, [rsp+3D8h+var_360]
0x18009a1f2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a1f7  nop
0x18009a1f8  lea     rcx, [rsp+3D8h+var_350]; this
0x18009a200  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009a205  nop
0x18009a206  lea     rcx, [rsp+3D8h+var_338]
0x18009a20e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a213  nop
0x18009a214  jmp     loc_18009A6B0
0x18009a219  lea     rdx, aPhysicaldevice; "PhysicalDeviceID"
0x18009a220  lea     rcx, [rsp+3D8h+Name]
0x18009a228  call    cs:__imp__o__wcsicmp
0x18009a22e  test    eax, eax
0x18009a230  jnz     short loc_18009A274
0x18009a232  lea     rcx, [rsp+3D8h+var_370]; this
0x18009a237  call    ??1CPassportStringW@@QEAA@XZ; CPassportStringW::~CPassportStringW(void)
0x18009a23c  nop
0x18009a23d  lea     rcx, [rsp+3D8h+var_358]
0x18009a245  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x18009a24a  nop
0x18009a24b  lea     rcx, [rsp+3D8h+var_368]
0x18009a250  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a255  nop
0x18009a256  lea     rcx, [rsp+3D8h+var_360]
0x18009a25b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009a260  nop
0x18009a261  lea     rcx, [rsp+3D8h+var_350]; this
0x18009a269  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x18009a26e  nop
0x18009a26f  jmp     loc_18009A5BA
0x18009a274  lea     rdx, [rsp+3D8h+Name]
0x18009a27c  lea     rcx, [rsp+3D8h+var_368]
0x18009a281  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18009a286  lea     rax, [rsp+3D8h+var_368]
0x18009a28b  mov     [rsp+3D8h+var_330], rax
0x18009a293  mov     ecx, cs:_tls_index
0x18009a299  mov     rax, gs:58h
0x18009a2a2  mov     r8d, 10h
0x18009a2a8  mov     rdx, [rax+rcx*8]
0x18009a2ac  cmp     [rdx+r8], rbx
0x18009a2b0  jnz     short loc_18009A2BB
0x18009a2b2  lea     rax, [rsp+3D8h+var_368]
0x18009a2b7  mov     [rdx+r8], rax
0x18009a2bb  mov     rdx, [rsp+3D8h+var_2D8]
  ... truncated ...
```
