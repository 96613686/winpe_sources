# DeviceIdHelpers::CreateNewDeviceIdentityInternal(ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64,unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long,CAutoRefPtr<CSingleIdentity> &)

- ea: `0x1800ea4fc`
- end: `0x1800eb10a`
- name: `?CreateNewDeviceIdentityInternal@DeviceIdHelpers@@SAJKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K10JAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z`
- size: `3086`
- prototype: ``
- caller_count: `2`
- callee_count: `46`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c27c0`
- `0x1800ea1a8`

## callees

- `0x180002e6c`
- `0x180002f34`
- `0x180006ac0`
- `0x180006b44`
- `0x18000c050`
- `0x18000ed04`
- `0x18000ed3c`
- `0x18000fd04`
- `0x180013510`
- `0x1800151c4`
- `0x180015860`
- `0x180015fdc`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x180029d54`
- `0x180031800`
- `0x18003ad50`
- `0x18003aea0`
- `0x18003c814`
- `0x180046d58`
- `0x180069ca0`
- `0x180079554`
- `0x18007a4b8`
- `0x18008b790`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800ae22c`
- `0x1800e519c`
- `0x1800e9cd0`
- `0x1800e9d28`
- `0x1800e9ff4`
- `0x1800ea4fc`
- `0x1800eb624`
- `0x1800eba1c`
- `0x1800ec4f8`
- `0x1800ed558`
- `0x1800ed584`
- `0x1800ed5ec`
- `0x1800ed784`
- `0x1800ff634`
- `0x18010003c`
- `0x180100490`
- `0x18010a214`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea969`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea97e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea969`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ea97e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ea633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ea72f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ea819`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ea633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ea72f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800ea819`

## string_xrefs

- `0x1800ea5c8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x1800ea5fb`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x1800ea6d8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x1800ea995`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x1800ea9dc`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x1800eaa01`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x1800ea5b1`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800ea6d1`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800ea9a2`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eaab2`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eac65`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eacf5`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800ead81`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eae50`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eaf32`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eaf85`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800eb07c`: `DeviceIdHelpers::CreateNewDeviceIdentityInternal`
- `0x1800ea6bc`: `hr = AcquireProvisioningMutex( true, failureThreshold, bMutexAcquired, bAttemptProvisioning)`
- `0x1800ea5ee`: `Failed to read current user SID hr=0x%x`
- `0x1800ea7af`: `CreateNewDeviceIdentity`
- `0x1800ea988`: `imageState.CompareNoCase(L"IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE") != 0 && imageState.CompareNoCase(L"IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT") != 0`
- `0x1800eab1e`: `hr = g_pPPCRL->GetIdentityStore()->RemoveDeviceIdentity(hDeviceIdentityLocal->GetIdentityName(), isPresent)`
- `0x1800eaa9d`: `hr = CDeviceIdentityBase::CreateNewDeviceIdentity(GetDeviceIdentityFlag(dwDeviceType), wstrAppId, hDeviceIdentityLocal, &createdIdentityLock)`
- `0x1800eac50`: `IsCallerAccountType(SECURITY_LOCAL_SYSTEM_RID, isSystemContext)`
- `0x1800eae3b`: `hr = pDeviceHelperWrapper->ReprovisionDevice(&serviceExecutionContext, g_szStrongAuthAppId, 0, hrProvisionFailure == PPCRL_E_DEVICE_KEY_SIGN_FAILURE ? hrProvisionFailure : hrInternal, hSystemDeviceIdentity, hNewSystemDeviceIdentity)`
- `0x1800ead6c`: `hr = pDeviceHelperWrapper->GetSystemHardwareID(&serviceExecutionContext, IDCRL_DEVICE_ID_FROMCACHE, hSystemDeviceIdentity)`
- `0x1800eb067`: `hr = g_pPPCRL->GetIdentityStore()->GetDeviceIdentityMap().UpdateValidDeviceIDKey( ((CSingleIdentity*)pDeviceIdentityObj)->GetUserType(), ((CSingleIdentity*)pDeviceIdentityObj)->GetIdentityName())`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall DeviceIdHelpers::CreateNewDeviceIdentityInternal(
        unsigned int a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        const void **a5,
        int a6,
        __int64 *a7)
{
  CClientConfigDataCacheManager *v10; // rax
  int CurrentUserSID; // eax
  ULONGLONG TickCount64; // rdi
  unsigned __int16 *Buffer; // rbx
  const unsigned __int16 *v14; // rdi
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  bool v19; // al
  unsigned int v20; // eax
  int v21; // ebx
  int v22; // edi
  ULONGLONG v23; // rsi
  unsigned __int16 *v24; // rax
  __int64 *v25; // r9
  const struct _tlgProvider_t *v26; // rbx
  __int64 v27; // r9
  int DeviceIdentityObject; // eax
  const char *v29; // rax
  unsigned int v30; // r8d
  unsigned int DeviceIdentityFlag; // eax
  int DeviceIdentity; // eax
  const char *v33; // rcx
  unsigned int v34; // r8d
  void *v35; // rbx
  CPassportClientLibrary *v36; // rbx
  __int64 v37; // rax
  _QWORD *v38; // rax
  int v39; // eax
  int IsCallerAccountType; // eax
  bool v41; // dl
  int v42; // r14d
  int v43; // edi
  int v44; // eax
  int v45; // eax
  __int64 (__fastcall *v46)(_QWORD *, _BYTE *, const unsigned __int16 **, _QWORD, int, __int64 *, __int64 *); // rbx
  int v47; // ebx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  const char *v51; // rcx
  unsigned int v52; // r8d
  CPassportClientLibrary *v53; // rdi
  __int64 v54; // rbx
  unsigned int v55; // eax
  int updated; // ebx
  unsigned int v57; // ebx
  char *v59; // [rsp+20h] [rbp-E0h]
  __int64 *v60; // [rsp+20h] [rbp-E0h]
  bool v61; // [rsp+50h] [rbp-B0h] BYREF
  bool v62[3]; // [rsp+51h] [rbp-AFh] BYREF
  int String; // [rsp+54h] [rbp-ACh] BYREF
  bool v64; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v65[7]; // [rsp+59h] [rbp-A7h] BYREF
  unsigned int v66; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  int v68[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v69; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v70; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+88h] [rbp-78h] BYREF
  int v72; // [rsp+90h] [rbp-70h] BYREF
  __int64 v73; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v74[4]; // [rsp+A0h] [rbp-60h] BYREF
  CSingleIdentity *v75; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v76; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-48h] BYREF
  __int64 DeviceProvisioningFailureThreshold; // [rsp+C0h] [rbp-40h]
  int v79; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v80; // [rsp+D0h] [rbp-30h]
  _QWORD v81[5]; // [rsp+D8h] [rbp-28h] BYREF
  char v82; // [rsp+100h] [rbp+0h]
  bool *v83; // [rsp+108h] [rbp+8h]
  char v84; // [rsp+110h] [rbp+10h]
  const char *v85[5]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v86[184]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v87[5]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v88[224]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v89[42]; // [rsp+300h] [rbp+200h] BYREF

  v66 = a1;
  String = 0;
  v75 = 0;
  v65[1] = 0;
  v77 = 0;
  *(_DWORD *)v74 = 0;
  v61 = 0;
  v64 = 0;
  v10 = CClientConfigDataCacheManager::theConfigDataManager();
  DeviceProvisioningFailureThreshold = CClientConfigDataCacheManager::GetDeviceProvisioningFailureThreshold(v10);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v88);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v85,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
    553,
    (const char *)&String,
    "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
    L"dwDeviceType=%d,wstrAppId=%ls,flags=%llx,internalFlags=%llx",
    v66,
    *a2,
    a3,
    a4);
  CurrentUserSID = DeviceIdHelpers::GetCurrentUserSID(&v76);
  String = CurrentUserSID;
  if ( CurrentUserSID )
  {
    LODWORD(v59) = CurrentUserSID;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
      0x235u,
      L"Failed to read current user SID hr=0x%x",
      v59);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v76, &qword_18013DE20);
    String = 0;
  }
  _InterlockedIncrement64(&DeviceIdHelpers::m_threadCount);
  v83 = &v64;
  v84 = 1;
  TickCount64 = GetTickCount64();
  Buffer = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v76);
  wil::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v89,
    (__int64)"DeviceProvisioningEarlyExitLogic");
  v89[0] = &MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::`vftable';
  MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::StartActivity(
    (MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic *)v89,
    Buffer,
    TickCount64,
    &DeviceIdHelpers::m_threadCount,
    &DeviceIdHelpers::m_requestFailureCount,
    DeviceProvisioningFailureThreshold);
  v14 = (const unsigned __int16 *)DeviceProvisioningFailureThreshold;
  v15 = DeviceIdHelpers::AcquireProvisioningMutex(1, DeviceProvisioningFailureThreshold, &v64, &v61);
  String = v15;
  if ( v15 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
      "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
      0x24Fu,
      v15,
      "hr = AcquireProvisioningMutex( true, failureThreshold, bMutexAcquired, bAttemptProvisioning)");
LABEL_5:
    v19 = v61;
    goto LABEL_6;
  }
  if ( (unsigned int)dword_1801C2080 > 5 )
  {
    v62[0] = v61;
    v65[0] = v64;
    v70 = L"CreateNewDeviceIdentity";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      v16,
      (__int64)&byte_18019AEA7,
      v17,
      v18,
      &v70,
      (__int64)v65,
      (__int64)v62);
  }
  v19 = v61;
  if ( v61 )
  {
    v26 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v26 > 5u )
    {
      v70 = v14;
      v71 = DeviceIdHelpers::m_requestFailureCount;
      v69 = DeviceIdHelpers::m_threadCount;
      v73 = GetTickCount64();
      *(_QWORD *)v68 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v76);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        (__int64)v26,
        (__int64)&unk_18019AE28,
        v89[34] + 8LL,
        v27,
        (const unsigned __int16 **)v68,
        (__int64)&v73,
        (__int64)&v69,
        (__int64)&v71,
        (__int64)&v70);
    }
    if ( !*(_DWORD *)(*a2 - 16LL) )
    {
      String = -2147188642;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
        "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
        0x26Bu,
        -2147188642,
        "!wstrAppId.IsEmpty()");
      goto LABEL_5;
    }
    v60 = a7;
    DeviceIdentityObject = DeviceIdHelpers::GetDeviceIdentityObject(a2, v66, a3, a4);
    String = DeviceIdentityObject;
    if ( ((DeviceIdentityObject + 2147188629) & 0xFFFFFFFC) != 0 || DeviceIdentityObject == -2147188628 )
      goto LABEL_5;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v73);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v69,
      L"ImageState");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v71,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State");
    String = Reg_QueryString(HKEY_LOCAL_MACHINE, (__int64)&v73);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v69);
    if ( String < 0 )
    {
      LODWORD(v60) = String;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
        0x283u,
        L"Reg_QueryString(SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State) failed hr = %x");
      if ( String != -2147024894 )
        goto LABEL_27;
      String = 0;
    }
    else if ( !(unsigned int)_o__wcsicmp(v73, L"IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE")
           || !(unsigned int)_o__wcsicmp(v73, L"IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT") )
    {
      v29 = "imageState.CompareNoCase(L\"IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE\") != 0 && imageState.CompareNoCase(L\"IMA"
            "GE_STATE_GENERALIZE_RESEAL_TO_AUDIT\") != 0";
      v30 = 639;
LABEL_26:
      String = -2147188641;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
        "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
        v30,
        -2147188641,
        v29);
LABEL_27:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v73);
      v19 = v61;
      goto LABEL_6;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v69,
      L"SystemSetupInProgress");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v71,
      L"SYSTEM\\Setup");
    v72 = 0;
    Reg_QueryDWORD(-2147483646, &v71, &v69, &v72);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v69);
    if ( v72 == 1 )
    {
      v29 = "systemUpgradeInProgress != 1";
      v30 = 658;
      goto LABEL_26;
    }
    Block = 0;
    DeviceIdentityFlag = GetDeviceIdentityFlag(v66);
    DeviceIdentity = CDeviceIdentityBase::CreateNewDeviceIdentity(DeviceIdentityFlag, a2, &v77, &Block);
    String = DeviceIdentity;
    if ( DeviceIdentity < 0 )
    {
      v33 = "hr = CDeviceIdentityBase::CreateNewDeviceIdentity(GetDeviceIdentityFlag(dwDeviceType), wstrAppId, hDeviceIde"
            "ntityLocal, &createdIdentityLock)";
      v34 = 663;
      goto LABEL_34;
    }
    v65[0] = 0;
    v36 = g_pPPCRL;
    v37 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v77 + 32LL))(v77, &v70);
    DeviceIdentity = CIdentityStore::RemoveDeviceIdentity((char *)v36 + 496, v37, v65);
    String = DeviceIdentity;
    if ( DeviceIdentity < 0 )
    {
      v33 = "hr = g_pPPCRL->GetIdentityStore()->RemoveDeviceIdentity(hDeviceIdentityLocal->GetIdentityName(), isPresent)";
      v34 = 668;
      goto LABEL_34;
    }
    DeviceIdentity = CIdentityStore::AddAndGetDeviceIdentity((LPCRITICAL_SECTION)((char *)g_pPPCRL + 496));
    String = DeviceIdentity;
    if ( DeviceIdentity < 0 )
    {
      v33 = "hr = g_pPPCRL->GetIdentityStore()->AddAndGetDeviceIdentity(hDeviceIdentityLocal, hDeviceIdentity)";
      v34 = 669;
      goto LABEL_34;
    }
    DeviceIdentity = (*(__int64 (__fastcall **)(__int64, __int64, CSingleIdentity **))(*(_QWORD *)*a7 + 88LL))(
                       *a7,
                       1,
                       &v75);
    String = DeviceIdentity;
    if ( DeviceIdentity < 0 )
    {
      v33 = "hr = hDeviceIdentity->QueryInterface(EDeviceIdentityType, (void**)&pDeviceIdentityObj)";
      v34 = 670;
LABEL_34:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
        "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
        v34,
        DeviceIdentity,
        v33);
      v35 = Block;
      if ( !Block )
        goto LABEL_27;
LABEL_61:
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)Block);
      operator delete(v35);
      goto LABEL_27;
    }
    *((_BYTE *)v75 + 833) = 0;
    *(_QWORD *)v68 = 0;
    if ( *((_DWORD *)*a5 - 4) )
    {
      v38 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v70,
              a5);
      CSingleIdentity::SetOldIdentityName(v75, v38);
      CSingleIdentity::SetReprovisionErrorCode(v75, a6);
    }
    v39 = GetDeviceIdentityFlag(v66);
    String = CDeviceIdentityBase::Provision((int)v75, 0, v39, (int)v68, v74);
    if ( String < 0 )
    {
      v62[0] = 0;
      v81[0] = v65;
      v81[1] = v62;
      v81[2] = a2;
      v81[3] = &v66;
      v81[4] = &v77;
      v82 = 1;
      v72 = 0;
      IsCallerAccountType = DeviceIdHelpers::IsCallerAccountType(0x12u, &v72);
      if ( IsCallerAccountType < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
          "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
          0x2C4u,
          IsCallerAccountType,
          "IsCallerAccountType(SECURITY_LOCAL_SYSTEM_RID, isSystemContext)");
        v82 = 0;
        lambda_112ed99a75b259de3376f2a5040ebad9_::operator()(v81);
LABEL_59:
        CAutoRefPtr<CSingleIdentity>::Deinit(v68);
        goto LABEL_60;
      }
      if ( !v72 )
      {
        v42 = *(_DWORD *)(*a7 + 240);
        v43 = String;
        if ( String == -2147187453 || v42 == -2147216617 || v42 == -2147217390 )
        {
          v79 = 0;
          v80 = 0;
          v69 = 0;
          v71 = 0;
          v44 = CAutoRevertToSelf::Revert((CAutoRevertToSelf *)&v79, v41);
          String = v44;
          if ( v44 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
              "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
              0x2D7u,
              v44,
              "hr = autoRevert.Revert(false)");
            CAutoRefPtr<CSingleIdentity>::Deinit(&v71);
            CAutoRefPtr<CSingleIdentity>::Deinit(&v69);
            CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v79);
            v82 = 0;
            lambda_112ed99a75b259de3376f2a5040ebad9_::operator()(v81);
            goto LABEL_59;
          }
          ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v86);
          v45 = (*(__int64 (__fastcall **)(_QWORD *, _BYTE *, __int64, __int64 *))(v87[0] + 72LL))(v87, v86, 16, &v69);
          String = v45;
          if ( v45 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
              "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
              0x2DDu,
              v45,
              "hr = pDeviceHelperWrapper->GetSystemHardwareID(&serviceExecutionContext, IDCRL_DEVICE_ID_FROMCACHE, hSyste"
              "mDeviceIdentity)");
            ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v86);
            CAutoRefPtr<CSingleIdentity>::Deinit(&v71);
            CAutoRefPtr<CSingleIdentity>::Deinit(&v69);
            CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v79);
            v82 = 0;
            lambda_112ed99a75b259de3376f2a5040ebad9_::operator()(v81);
            goto LABEL_59;
          }
          v46 = *(__int64 (__fastcall **)(_QWORD *, _BYTE *, const unsigned __int16 **, _QWORD, int, __int64 *, __int64 *))(v87[0] + 80LL);
          if ( v43 != -2147187453 )
            v43 = v42;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v70,
            L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}");
          v47 = v46(v87, v86, &v70, 0, v43, &v69, &v71);
          String = v47;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v70);
          if ( v47 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
              "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
              0x2E4u,
              v47,
              "hr = pDeviceHelperWrapper->ReprovisionDevice(&serviceExecutionContext, g_szStrongAuthAppId, 0, hrProvision"
              "Failure == PPCRL_E_DEVICE_KEY_SIGN_FAILURE ? hrProvisionFailure : hrInternal, hSystemDeviceIdentity, hNewS"
              "ystemDeviceIdentity)");
            ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v86);
            CAutoRefPtr<CSingleIdentity>::Deinit(&v71);
            CAutoRefPtr<CSingleIdentity>::Deinit(&v69);
            CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v79);
            v82 = 0;
            lambda_112ed99a75b259de3376f2a5040ebad9_::operator()(v81);
            goto LABEL_59;
          }
          ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v86);
          CAutoRefPtr<CSingleIdentity>::Deinit(&v71);
          CAutoRefPtr<CSingleIdentity>::Deinit(&v69);
          CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v79);
          v48 = GetDeviceIdentityFlag(v66);
          v49 = CDeviceIdentityBase::Provision((int)v75, 0, v48, (int)v68, v74);
          String = v49;
          if ( v49 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
              "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
              0x2E8u,
              v49,
              "hr = pDeviceIdentityObj->Provision(false, GetDeviceIdentityFlag(dwDeviceType), hRandomIdentity, hrSendResult)");
            v82 = 0;
            lambda_112ed99a75b259de3376f2a5040ebad9_::operator()(v81);
            goto LABEL_59;
          }
          v62[0] = 1;
        }
      }
      v82 = 0;
      lambda_112ed99a75b259de3376f2a5040ebad9_::operator()(v81);
      v50 = String;
      if ( String < 0 )
      {
        v51 = "hr";
        v52 = 749;
LABEL_67:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
          "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
          v52,
          v50,
          v51);
        goto LABEL_59;
      }
    }
    if ( *(_QWORD *)v68 )
    {
      v50 = CIdentityStore::AddAndGetDeviceIdentity((LPCRITICAL_SECTION)((char *)g_pPPCRL + 496));
      String = v50;
      if ( v50 < 0 )
      {
        v51 = "hr = g_pPPCRL->GetIdentityStore()->AddAndGetDeviceIdentity(hRandomIdentity, hDeviceIdentity)";
        v52 = 754;
        goto LABEL_67;
      }
      v50 = (*(__int64 (__fastcall **)(__int64, __int64, CSingleIdentity **))(*(_QWORD *)*a7 + 88LL))(*a7, 1, &v75);
      String = v50;
      if ( v50 < 0 )
      {
        v51 = "hr = ((CSingleIdentity*)hDeviceIdentity)->QueryInterface(EDeviceIdentityType, (void**)&pDeviceIdentityObj)";
        v52 = 755;
        goto LABEL_67;
      }
    }
    CAutoRefPtr<CSingleIdentity>::Deinit(v68);
    v53 = g_pPPCRL;
    v54 = (*(__int64 (__fastcall **)(CSingleIdentity *, const unsigned __int16 **))(*(_QWORD *)v75 + 32LL))(v75, &v70);
    v55 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v75 + 80LL))(v75);
    updated = CDeviceIdentityMap::UpdateValidDeviceIDKey((char *)v53 + 752, v55, v54, 0);
    String = updated;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v70);
    if ( updated < 0 )
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
        "DeviceIdHelpers::CreateNewDeviceIdentityInternal",
        0x2FAu,
        updated,
        "hr = g_pPPCRL->GetIdentityStore()->GetDeviceIdentityMap().UpdateValidDeviceIDKey( ((CSingleIdentity*)pDeviceIden"
        "tityObj)->GetUserType(), ((CSingleIdentity*)pDeviceIdentityObj)->GetIdentityName())");
LABEL_60:
    v35 = Block;
    if ( !Block )
      goto LABEL_27;
    goto LABEL_61;
  }
LABEL_6:
  if ( String >= 0 && !v19 )
  {
    v62[0] = 0;
    v20 = GetDeviceIdentityFlag(v66);
    CDeviceIdentityBase::IsProvisioningExplicit(v20, v62);
    String = v62[0] ? -2147186583 : -2147188655;
  }
  v21 = *(_DWORD *)v74;
  v22 = String;
  v23 = GetTickCount64();
  v24 = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v76);
  MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::Stop(
    (MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic *)v89,
    v24,
    v23,
    v25,
    v60,
    DeviceProvisioningFailureThreshold,
    v22,
    v21);
  if ( v61 )
  {
    if ( String < 0 && *(_DWORD *)v74 == -2147012894 )
      _InterlockedIncrement64(&DeviceIdHelpers::m_requestFailureCount);
    else
      _InterlockedAnd64(&DeviceIdHelpers::m_requestFailureCount, 0);
  }
  v57 = String;
  MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::~DeviceProvisioningEarlyExitLogic((MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic *)v89);
  _InterlockedDecrement64(&DeviceIdHelpers::m_threadCount);
  DeviceIdHelpers::ReleaseMutexIfNecessary(v64);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v85);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v88);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v77);
  return v57;
}

```

## disassembly

```asm
0x1800ea4fc  push    rbp
0x1800ea4fe  push    rbx
0x1800ea4ff  push    rsi
0x1800ea500  push    rdi
0x1800ea501  push    r12
0x1800ea503  push    r13
0x1800ea505  push    r14
0x1800ea507  push    r15
0x1800ea509  lea     rbp, [rsp-368h]
0x1800ea511  sub     rsp, 468h
0x1800ea518  mov     rax, cs:__security_cookie
0x1800ea51f  xor     rax, rsp
0x1800ea522  mov     [rbp+3A0h+var_50], rax
0x1800ea529  mov     r13, r9
0x1800ea52c  mov     r12, r8
0x1800ea52f  mov     r14, rdx
0x1800ea532  mov     rsi, [rbp+3A0h+arg_20]
0x1800ea539  mov     [rsp+4A0h+var_440], ecx
0x1800ea53d  mov     r15, [rbp+3A0h+arg_30]
0x1800ea544  xor     ebx, ebx
0x1800ea546  mov     [rsp+4A0h+var_44C], ebx
0x1800ea54a  mov     [rbp+3A0h+var_3F8], rbx
0x1800ea54e  mov     [rsp+4A0h+var_446], bl
0x1800ea552  mov     [rbp+3A0h+var_3E8], rbx
0x1800ea556  mov     dword ptr [rbp+3A0h+var_400], ebx
0x1800ea559  mov     [rsp+4A0h+var_450], bl
0x1800ea55d  mov     [rsp+4A0h+var_448], bl
0x1800ea561  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x1800ea566  mov     rcx, rax; this
0x1800ea569  call    ?GetDeviceProvisioningFailureThreshold@CClientConfigDataCacheManager@@QEAAKXZ; CClientConfigDataCacheManager::GetDeviceProvisioningFailureThreshold(void)
0x1800ea56e  mov     eax, eax
0x1800ea570  mov     [rbp+3A0h+var_3E0], rax
0x1800ea574  lea     rcx, [rbp+3A0h+var_3F0]
0x1800ea578  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ea57d  nop
0x1800ea57e  lea     rcx, [rbp+3A0h+var_280]; this
0x1800ea585  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800ea58a  nop
0x1800ea58b  mov     [rsp+4A0h+var_458], r13
0x1800ea590  mov     [rsp+4A0h+var_460], r12
0x1800ea595  mov     rax, [r14]
0x1800ea598  mov     qword ptr [rsp+4A0h+var_468], rax
0x1800ea59d  mov     eax, [rsp+4A0h+var_440]
0x1800ea5a1  mov     [rsp+4A0h+var_470], eax
0x1800ea5a5  lea     rax, aDwdevicetypeDW; "dwDeviceType=%d,wstrAppId=%ls,flags=%ll"...
0x1800ea5ac  mov     [rsp+4A0h+var_478], rax
0x1800ea5b1  lea     rax, aDeviceidhelper_43; "DeviceIdHelpers::CreateNewDeviceIdentit"...
0x1800ea5b8  mov     [rsp+4A0h+var_480], rax
0x1800ea5bd  lea     r9, [rsp+4A0h+var_44C]
0x1800ea5c2  mov     r8d, 229h
0x1800ea5c8  lea     rdx, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ea5cf  lea     rcx, [rbp+3A0h+var_388]
0x1800ea5d3  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800ea5d8  nop
0x1800ea5d9  lea     rcx, [rbp+3A0h+var_3F0]
0x1800ea5dd  call    ?GetCurrentUserSID@DeviceIdHelpers@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; DeviceIdHelpers::GetCurrentUserSID(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800ea5e2  mov     [rsp+4A0h+var_44C], eax
0x1800ea5e6  test    eax, eax
0x1800ea5e8  jz      short loc_1800EA61E
0x1800ea5ea  mov     dword ptr [rsp+4A0h+var_480], eax
0x1800ea5ee  lea     r9, aFailedToReadCu; "Failed to read current user SID hr=0x%x"
0x1800ea5f5  mov     r8d, 235h; unsigned int
0x1800ea5fb  lea     rdx, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ea602  lea     ecx, [rbx+5]; unsigned __int8
0x1800ea605  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800ea60a  lea     rdx, qword_18013DE20
0x1800ea611  lea     rcx, [rbp+3A0h+var_3F0]
0x1800ea615  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800ea61a  mov     [rsp+4A0h+var_44C], ebx
0x1800ea61e  lock inc cs:?m_threadCount@DeviceIdHelpers@@1_JC; __int64 volatile DeviceIdHelpers::m_threadCount
0x1800ea626  lea     rax, [rsp+4A0h+var_448]
0x1800ea62b  mov     [rbp+3A0h+var_398], rax
0x1800ea62f  mov     [rbp+3A0h+var_390], 1
0x1800ea633  call    cs:__imp_GetTickCount64
0x1800ea639  mov     rdi, rax
0x1800ea63c  lea     rcx, [rbp+3A0h+var_3F0]
0x1800ea640  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800ea645  mov     rbx, rax
0x1800ea648  lea     rdx, aDeviceprovisio; "DeviceProvisioningEarlyExitLogic"
0x1800ea64f  lea     rcx, [rbp+3A0h+var_1A0]
0x1800ea656  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800ea65b  lea     rax, ??_7DeviceProvisioningEarlyExitLogic@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::`vftable'
0x1800ea662  mov     [rbp+3A0h+var_1A0], rax
0x1800ea669  mov     rcx, [rbp+3A0h+var_3E0]
0x1800ea66d  mov     [rsp+4A0h+var_478], rcx; __int64
0x1800ea672  lea     rax, ?m_requestFailureCount@DeviceIdHelpers@@1_JC; __int64 volatile DeviceIdHelpers::m_requestFailureCount
0x1800ea679  mov     [rsp+4A0h+var_480], rax; __int64 *
0x1800ea67e  lea     r9, ?m_threadCount@DeviceIdHelpers@@1_JC; __int64 *
0x1800ea685  mov     r8, rdi; unsigned __int64
0x1800ea688  mov     rdx, rbx; unsigned __int16 *
0x1800ea68b  lea     rcx, [rbp+3A0h+var_1A0]; this
0x1800ea692  call    ?StartActivity@DeviceProvisioningEarlyExitLogic@MSAClientTraceTelemetry@@QEAAXPEAG_KAEA_J2_J@Z; MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::StartActivity(ushort *,unsigned __int64,__int64 &,__int64 &,__int64)
0x1800ea697  nop
0x1800ea698  lea     r9, [rsp+4A0h+var_450]; bool *
0x1800ea69d  lea     r8, [rsp+4A0h+var_448]; bool *
0x1800ea6a2  mov     rdi, [rbp+3A0h+var_3E0]
0x1800ea6a6  mov     rdx, rdi; __int64
0x1800ea6a9  mov     cl, 1; bool
0x1800ea6ab  call    ?AcquireProvisioningMutex@DeviceIdHelpers@@KAJ_N_JAEA_N2@Z; DeviceIdHelpers::AcquireProvisioningMutex(bool,__int64,bool &,bool &)
0x1800ea6b0  mov     [rsp+4A0h+var_44C], eax
0x1800ea6b4  test    eax, eax
0x1800ea6b6  jns     loc_1800EA794
0x1800ea6bc  lea     r8, aHrAcquireprovi; "hr = AcquireProvisioningMutex( true, fa"...
0x1800ea6c3  mov     [rsp+4A0h+var_480], r8; __int64 *
0x1800ea6c8  mov     r9d, eax; int
0x1800ea6cb  mov     r8d, 24Fh; unsigned int
0x1800ea6d1  lea     rdx, aDeviceidhelper_43; "DeviceIdHelpers::CreateNewDeviceIdentit"...
0x1800ea6d8  lea     rcx, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ea6df  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ea6e4  mov     al, [rsp+4A0h+var_450]
0x1800ea6e8  xor     r12d, r12d
0x1800ea6eb  cmp     [rsp+4A0h+var_44C], r12d
0x1800ea6f0  jl      short loc_1800EA728
0x1800ea6f2  test    al, al
0x1800ea6f4  jnz     short loc_1800EA728
0x1800ea6f6  mov     [rsp+4A0h+var_44F], r12b
0x1800ea6fb  mov     ecx, [rsp+4A0h+var_440]; unsigned int
0x1800ea6ff  call    ?GetDeviceIdentityFlag@@YAKK@Z; GetDeviceIdentityFlag(ulong)
0x1800ea704  mov     ecx, eax; unsigned int
0x1800ea706  lea     rdx, [rsp+4A0h+var_44F]; bool *
0x1800ea70b  call    ?IsProvisioningExplicit@CDeviceIdentityBase@@SAJKAEA_N@Z; CDeviceIdentityBase::IsProvisioningExplicit(ulong,bool &)
0x1800ea710  mov     al, [rsp+4A0h+var_44F]
0x1800ea714  neg     al
0x1800ea716  sbb     ecx, ecx
0x1800ea718  and     ecx, 818h
0x1800ea71e  add     ecx, 80048051h
0x1800ea724  mov     [rsp+4A0h+var_44C], ecx
0x1800ea728  mov     ebx, dword ptr [rbp+3A0h+var_400]
0x1800ea72b  mov     edi, [rsp+4A0h+var_44C]
0x1800ea72f  call    cs:__imp_GetTickCount64
0x1800ea735  mov     rsi, rax
0x1800ea738  lea     rcx, [rbp+3A0h+var_3F0]
0x1800ea73c  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800ea741  mov     [rsp+4A0h+var_468], ebx; int
0x1800ea745  mov     [rsp+4A0h+var_470], edi; int
0x1800ea749  mov     rcx, [rbp+3A0h+var_3E0]
0x1800ea74d  mov     [rsp+4A0h+var_478], rcx; __int64
0x1800ea752  mov     r8, rsi; unsigned __int64
0x1800ea755  mov     rdx, rax; unsigned __int16 *
0x1800ea758  lea     rcx, [rbp+3A0h+var_1A0]; this
0x1800ea75f  call    ?Stop@DeviceProvisioningEarlyExitLogic@MSAClientTraceTelemetry@@QEAAXPEAG_KAEA_J2_JJJ@Z; MSAClientTraceTelemetry::DeviceProvisioningEarlyExitLogic::Stop(ushort *,unsigned __int64,__int64 &,__int64 &,__int64,long,long)
0x1800ea764  cmp     [rsp+4A0h+var_450], 0
0x1800ea769  jz      loc_1800EB098
0x1800ea76f  cmp     [rsp+4A0h+var_44C], r12d
0x1800ea774  jge     loc_1800EB090
0x1800ea77a  cmp     dword ptr [rbp+3A0h+var_400], 80072EE2h
0x1800ea781  jnz     loc_1800EB090
0x1800ea787  lock inc cs:?m_requestFailureCount@DeviceIdHelpers@@1_JC; __int64 volatile DeviceIdHelpers::m_requestFailureCount
0x1800ea78f  jmp     loc_1800EB098
0x1800ea794  mov     eax, cs:dword_1801C2080
0x1800ea79a  cmp     eax, 5
0x1800ea79d  jbe     short loc_1800EA7E3
0x1800ea79f  mov     al, [rsp+4A0h+var_450]
0x1800ea7a3  mov     [rsp+4A0h+var_44F], al
0x1800ea7a7  mov     al, [rsp+4A0h+var_448]
0x1800ea7ab  mov     [rsp+4A0h+var_447], al
0x1800ea7af  lea     rax, aCreatenewdevic; "CreateNewDeviceIdentity"
0x1800ea7b6  mov     [rbp+3A0h+var_420], rax
0x1800ea7ba  lea     rax, [rsp+4A0h+var_44F]
0x1800ea7bf  mov     qword ptr [rsp+4A0h+var_470], rax
0x1800ea7c4  lea     rax, [rsp+4A0h+var_447]
0x1800ea7c9  mov     [rsp+4A0h+var_478], rax
0x1800ea7ce  lea     rax, [rbp+3A0h+var_420]
0x1800ea7d2  mov     [rsp+4A0h+var_480], rax
0x1800ea7d7  lea     rdx, byte_18019AEA7
0x1800ea7de  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1800ea7e3  mov     al, [rsp+4A0h+var_450]
0x1800ea7e7  test    al, al
0x1800ea7e9  jz      loc_1800EA6E8
0x1800ea7ef  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x1800ea7f4  mov     rbx, rax
0x1800ea7f7  mov     ecx, [rax]
0x1800ea7f9  cmp     ecx, 5
0x1800ea7fc  jbe     short loc_1800EA87A
0x1800ea7fe  mov     [rbp+3A0h+var_420], rdi
0x1800ea802  mov     rcx, cs:?m_requestFailureCount@DeviceIdHelpers@@1_JC; __int64 volatile DeviceIdHelpers::m_requestFailureCount
0x1800ea809  mov     [rbp+3A0h+var_418], rcx
0x1800ea80d  mov     rcx, cs:?m_threadCount@DeviceIdHelpers@@1_JC; __int64 volatile DeviceIdHelpers::m_threadCount
0x1800ea814  mov     [rsp+4A0h+var_428], rcx
0x1800ea819  call    cs:__imp_GetTickCount64
0x1800ea81f  mov     [rbp+3A0h+var_408], rax
0x1800ea823  lea     rcx, [rbp+3A0h+var_3F0]
0x1800ea827  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800ea82c  mov     qword ptr [rsp+4A0h+var_430], rax
0x1800ea831  mov     r8, [rbp+3A0h+var_90]
0x1800ea838  add     r8, 8
0x1800ea83c  lea     rax, [rbp+3A0h+var_420]
0x1800ea840  mov     [rsp+4A0h+var_460], rax
0x1800ea845  lea     rax, [rbp+3A0h+var_418]
0x1800ea849  mov     qword ptr [rsp+4A0h+var_468], rax
0x1800ea84e  lea     rax, [rsp+4A0h+var_428]
0x1800ea853  mov     qword ptr [rsp+4A0h+var_470], rax
0x1800ea858  lea     rax, [rbp+3A0h+var_408]
0x1800ea85c  mov     [rsp+4A0h+var_478], rax
0x1800ea861  lea     rax, [rsp+4A0h+var_430]
0x1800ea866  mov     [rsp+4A0h+var_480], rax
0x1800ea86b  lea     rdx, unk_18019AE28
0x1800ea872  mov     rcx, rbx
0x1800ea875  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800ea87a  mov     rax, [r14]
0x1800ea87d  cmp     dword ptr [rax-10h], 0
0x1800ea881  jnz     short loc_1800EA8A5
0x1800ea883  mov     r9d, 8004805Eh
0x1800ea889  mov     [rsp+4A0h+var_44C], r9d
0x1800ea88e  lea     rax, aWstrappidIsemp; "!wstrAppId.IsEmpty()"
0x1800ea895  mov     [rsp+4A0h+var_480], rax
0x1800ea89a  mov     r8d, 26Bh
0x1800ea8a0  jmp     loc_1800EA6D1
0x1800ea8a5  lea     rax, [rsp+4A0h+var_446]
0x1800ea8aa  mov     [rsp+4A0h+var_478], rax
0x1800ea8af  mov     [rsp+4A0h+var_480], r15
0x1800ea8b4  mov     r9, r13
0x1800ea8b7  mov     r8, r12
0x1800ea8ba  mov     edx, [rsp+4A0h+var_440]
0x1800ea8be  mov     rcx, r14
0x1800ea8c1  call    ?GetDeviceIdentityObject@DeviceIdHelpers@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@K_K1AEAV?$CAutoRefPtr@VCSingleIdentity@@@@AEA_N@Z; DeviceIdHelpers::GetDeviceIdentityObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong,unsigned __int64,unsigned __int64,CAutoRefPtr<CSingleIdentity> &,bool &)
0x1800ea8c6  mov     [rsp+4A0h+var_44C], eax
0x1800ea8ca  lea     ecx, [rax+7FFB7F95h]
0x1800ea8d0  test    ecx, 0FFFFFFFCh
0x1800ea8d6  jnz     loc_1800EA6E4
0x1800ea8dc  cmp     eax, 8004806Ch
0x1800ea8e1  jz      loc_1800EA6E4
0x1800ea8e7  lea     rcx, [rbp+3A0h+var_408]
0x1800ea8eb  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ea8f0  nop
0x1800ea8f1  lea     rdx, aImagestate; "ImageState"
0x1800ea8f8  lea     rcx, [rsp+4A0h+var_428]
0x1800ea8fd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800ea902  nop
0x1800ea903  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800ea90a  lea     rcx, [rbp+3A0h+var_418]
0x1800ea90e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800ea913  nop
0x1800ea914  lea     rax, [rbp+3A0h+var_408]
0x1800ea918  mov     [rsp+4A0h+var_480], rax; __int64
0x1800ea91d  mov     r9d, 1
0x1800ea923  lea     r8, [rsp+4A0h+var_428]
0x1800ea928  lea     rdx, [rbp+3A0h+var_418]
0x1800ea92c  mov     rbx, 0FFFFFFFF80000002h
0x1800ea933  mov     rcx, rbx; HKEY
0x1800ea936  call    ?Reg_QueryString@@YAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1KAEAV23@@Z; Reg_QueryString(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800ea93b  mov     [rsp+4A0h+var_44C], eax
0x1800ea93f  lea     rcx, [rbp+3A0h+var_418]
0x1800ea943  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ea948  nop
0x1800ea949  lea     rcx, [rsp+4A0h+var_428]
0x1800ea94e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ea953  mov     eax, [rsp+4A0h+var_44C]
0x1800ea957  xor     r12d, r12d
0x1800ea95a  test    eax, eax
0x1800ea95c  js      short loc_1800EA9CB
0x1800ea95e  lea     rdx, aImageStateGene; "IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE"
0x1800ea965  mov     rcx, [rbp+3A0h+var_408]
0x1800ea969  call    cs:__imp__o__wcsicmp
0x1800ea96f  test    eax, eax
0x1800ea971  jz      short loc_1800EA988
0x1800ea973  lea     rdx, aImageStateGene_0; "IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT"
0x1800ea97a  mov     rcx, [rbp+3A0h+var_408]
0x1800ea97e  call    cs:__imp__o__wcsicmp
0x1800ea984  test    eax, eax
0x1800ea986  jnz     short loc_1800EAA01
0x1800ea988  lea     rax, aImagestateComp; "imageState.CompareNoCase(L\"IMAGE_STATE"...
0x1800ea98f  mov     r8d, 27Fh; unsigned int
0x1800ea995  lea     rcx, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ea99c  mov     r9d, 8004805Fh; int
0x1800ea9a2  lea     rdx, aDeviceidhelper_43; "DeviceIdHelpers::CreateNewDeviceIdentit"...
0x1800ea9a9  mov     [rsp+4A0h+var_480], rax; char *
0x1800ea9ae  mov     [rsp+4A0h+var_44C], r9d
0x1800ea9b3  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800ea9b8  nop
0x1800ea9b9  lea     rcx, [rbp+3A0h+var_408]
0x1800ea9bd  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800ea9c2  mov     al, [rsp+4A0h+var_450]
0x1800ea9c6  jmp     loc_1800EA6EB
0x1800ea9cb  mov     dword ptr [rsp+4A0h+var_480], eax
0x1800ea9cf  lea     r9, aRegQuerystring; "Reg_QueryString(SOFTWARE\\Microsoft\\Wi"...
0x1800ea9d6  mov     r8d, 283h; unsigned int
0x1800ea9dc  lea     r13, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800ea9e3  mov     rdx, r13; char *
0x1800ea9e6  mov     ecx, 2; unsigned __int8
0x1800ea9eb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800ea9f0  cmp     [rsp+4A0h+var_44C], 80070002h
0x1800ea9f8  jnz     short loc_1800EA9B9
0x1800ea9fa  mov     [rsp+4A0h+var_44C], r12d
0x1800ea9ff  jmp     short loc_1800EAA08
0x1800eaa01  lea     r13, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800eaa08  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x1800eaa0f  lea     rcx, [rsp+4A0h+var_428]
0x1800eaa14  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800eaa19  nop
0x1800eaa1a  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1800eaa21  lea     rcx, [rbp+3A0h+var_418]
0x1800eaa25  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800eaa2a  nop
0x1800eaa2b  mov     [rbp+3A0h+var_410], r12d
0x1800eaa2f  lea     r9, [rbp+3A0h+var_410]
0x1800eaa33  lea     r8, [rsp+4A0h+var_428]
0x1800eaa38  lea     rdx, [rbp+3A0h+var_418]
0x1800eaa3c  mov     rcx, rbx
0x1800eaa3f  call    ?Reg_QueryDWORD@@YAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAKH@Z; Reg_QueryDWORD(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &,int)
  ... truncated ...
```
