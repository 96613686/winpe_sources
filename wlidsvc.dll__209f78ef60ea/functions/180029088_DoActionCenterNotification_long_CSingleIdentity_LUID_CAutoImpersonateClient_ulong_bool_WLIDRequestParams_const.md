# DoActionCenterNotification(long,CSingleIdentity *,_LUID *,CAutoImpersonateClient *,ulong,bool,_WLIDRequestParams * const,CPPCRLRequest *)

- ea: `0x180029088`
- end: `0x180029946`
- name: `?DoActionCenterNotification@@YAJJPEAVCSingleIdentity@@PEAU_LUID@@PEAVCAutoImpersonateClient@@K_NQEAU_WLIDRequestParams@@PEAVCPPCRLRequest@@@Z`
- size: `2238`
- prototype: `__int64 __fastcall(int, struct CSingleIdentity *, struct _LUID *, struct CAutoImpersonateClient *this, unsigned int, bool, struct _WLIDRequestParams *const, struct CPPCRLRequest *)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800563d0`

## callees

- `0x18000a354`
- `0x18000c050`
- `0x18000ed04`
- `0x180010fb8`
- `0x180013448`
- `0x1800151c4`
- `0x180015fb0`
- `0x180019690`
- `0x180019780`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f4d0`
- `0x180021b28`
- `0x180021bbc`
- `0x180022f64`
- `0x180029088`
- `0x180029d54`
- `0x180029ef0`
- `0x18002a074`
- `0x18002a1d8`
- `0x1800396e8`
- `0x18003ccb0`
- `0x18003d188`
- `0x180045af8`
- `0x180051fb0`
- `0x18006b9a4`
- `0x180079554`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029704`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800293bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800293d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800293bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800293d8`
- `ntdll!RtlAcquireResourceShared` at `0x180029200`
- `ntdll!RtlAcquireResourceShared` at `0x180029200`
- `ntdll!RtlReleaseResource` at `0x180029900`
- `ntdll!RtlReleaseResource` at `0x180029900`

## string_xrefs

- `0x1800290ec`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800292cd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800292f4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002934b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800294e0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180029608`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18002972d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180029827`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800292b1`: `hr = SystemStoreLite::IsConnected(serviceExecutionContext.GetExternalExecutionContextLite(), &isConnected, &pConnectedLiveUserName)`
- `0x1800292e7`: `Current user is not connected, skipping interrupt notification update.`
- `0x1800294d3`: `Current connected username (%ls) does not match request (IdentityName: %ls, AuthMemberName: %ls), skipping interrupt notification update.`
- `0x180029549`: `hr = pClient->GetTokenUser(sid)`
- `0x1800296ab`: `hr = SystemStoreLite::IsUserDomainConnected( serviceExecutionContext.GetExternalExecutionContextLite(), static_cast<LPCWSTR>(sid), isDomainConnected)`
- `0x1800297bb`: `hr = InterruptNotifications::GetNotificationData( hrRequest, &serviceExecutionContext, pIdentity, static_cast<LPCWSTR>(sid), pRequestParams, requestCount, pRSTRequest, notificationFlags, triggerRequestTargets, triggerRequestPolicies, hrRequestStatus )`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall DoActionCenterNotification(
        int a1,
        struct CSingleIdentity *a2,
        struct _LUID *a3,
        struct CAutoImpersonateClient *this,
        unsigned int a5,
        unsigned int a6,
        struct _WLIDRequestParams *const a7,
        struct CPPCRLRequest *a8)
{
  unsigned int v9; // ebx
  int v12; // eax
  __int64 v13; // r8
  _QWORD *v14; // rax
  __int64 v15; // rcx
  MsaUserExtImpl *v16; // rcx
  int *v17; // r9
  int IsLoggedOnUser; // eax
  struct _RTL_RESOURCE *v19; // r14
  int v20; // esi
  unsigned __int16 *v21; // rbx
  int IsConnected; // eax
  const char *v23; // rcx
  unsigned int v24; // r8d
  int v25; // eax
  LPCWCH *v26; // rax
  const WCHAR *v27; // r12
  bool v28; // bl
  unsigned __int8 v29; // dl
  PPTraceStatus *v30; // rcx
  char v31; // cl
  const unsigned __int16 *String; // r15
  unsigned __int8 v33; // dl
  PPTraceStatus *v34; // rcx
  char v35; // bl
  const unsigned __int16 *v36; // rbx
  unsigned __int8 v37; // dl
  PPTraceStatus *v38; // rcx
  const unsigned __int16 *v39; // rax
  char v40; // bl
  struct CPPCRLRequest *v41; // r15
  __int64 v42; // rbx
  __int64 *v43; // rax
  int IsUserDomainConnected; // eax
  const char *v45; // rcx
  unsigned int v46; // r8d
  __int64 v47; // rbx
  __int64 *v48; // rax
  signed int LastError; // eax
  int SessionId; // eax
  unsigned int v51; // r15d
  int v52; // eax
  unsigned int v53; // ebx
  const unsigned __int16 *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea[2]; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCaseb[2]; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasec[2]; // [rsp+20h] [rbp-E0h]
  bool v59; // [rsp+50h] [rbp-B0h]
  LPCWCH lpString2; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v61; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  bool v65[4]; // [rsp+88h] [rbp-78h] BYREF
  struct _LUID v66; // [rsp+8Ch] [rbp-74h] BYREF
  int v67; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v68; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v69; // [rsp+A0h] [rbp-60h] BYREF
  LPCWCH lpString1[3]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v72; // [rsp+C8h] [rbp-38h]
  _QWORD v73[3]; // [rsp+D8h] [rbp-28h] BYREF
  char v74; // [rsp+F0h] [rbp-10h]
  _QWORD v75[3]; // [rsp+F8h] [rbp-8h] BYREF
  char v76; // [rsp+110h] [rbp+10h]
  _QWORD v77[3]; // [rsp+118h] [rbp+18h] BYREF
  char v78; // [rsp+130h] [rbp+30h]
  _QWORD v79[5]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v80[56]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v81[27]; // [rsp+198h] [rbp+98h] BYREF
  int v82; // [rsp+288h] [rbp+188h] BYREF
  CAutoImpersonateClient *v83; // [rsp+298h] [rbp+198h]

  v83 = this;
  v9 = (unsigned int)a3;
  v82 = 0;
  v79[0] = "DoActionCenterNotification";
  v79[1] = &v82;
  v79[2] = 0;
  v79[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "DoActionCenterNotification",
    (const char *)0xE37,
    0,
    bIgnoreCase);
  v12 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)a2 + 80LL))(a2);
  v13 = *(_QWORD *)a2;
  if ( !v12 )
  {
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(struct CSingleIdentity *, unsigned __int16 **))(v13 + 16))(a2, &v61);
    LODWORD(v71) = ExtensionAPI::IsApplicationFullTrust(v15, *v14);
    ATL::CStringData::Release((ATL::CStringData *)(v61 - 12));
    v66.LowPart = 0;
    IsLoggedOnUser = MsaUserExtImpl::CallerIsLoggedOnUser(v16, v9, &v66, v17);
    if ( IsLoggedOnUser < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "DoActionCenterNotification",
        0xE53u,
        IsLoggedOnUser,
        "MsaUserExtImpl::CallerIsLoggedOnUser(0, pLogonId, &isLoggedOn)");
      goto LABEL_65;
    }
    if ( !v66.LowPart )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0xE57u,
        L"Session is not logged on.");
      goto LABEL_65;
    }
    ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v80);
    memset(lpString1, 0, sizeof(lpString1));
    a6 = 0;
    v19 = (struct _RTL_RESOURCE *)((char *)g_pPPCRL + 2136);
    v79[4] = (char *)g_pPPCRL + 2136;
    v20 = 1;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)g_pPPCRL + 2136), 1u);
    v68 = 0;
    v64 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v63 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v21 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v62 = v21;
    lpString2 = (LPCWCH)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    *(_DWORD *)v65 = 0;
    v66.HighPart = 0;
    v67 = 0;
    IsConnected = SystemStoreLite::IsConnected(
                    (struct IExecutionContextLite *)v81,
                    (int *)&a6,
                    (unsigned __int16 **)lpString1);
    v82 = IsConnected;
    if ( IsConnected < 0 )
    {
      v23 = "hr = SystemStoreLite::IsConnected(serviceExecutionContext.GetExternalExecutionContextLite(), &isConnected, &"
            "pConnectedLiveUserName)";
      v24 = 3692;
LABEL_9:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "DoActionCenterNotification",
        v24,
        IsConnected,
        v23);
LABEL_63:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpString2);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
      goto LABEL_64;
    }
    if ( !a6 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0xE6Fu,
        L"Current user is not connected, skipping interrupt notification update.");
      goto LABEL_63;
    }
    v25 = (*(__int64 (__fastcall **)(struct CSingleIdentity *, const wchar_t *, LPCWCH *))(*(_QWORD *)a2 + 64LL))(
            a2,
            L"AuthMembername",
            &lpString2);
    v82 = v25;
    if ( v25 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "DoActionCenterNotification",
        0xE86u,
        v25,
        "hr = pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_AUTHMEMBERNAME, authMembername)");
      ATL::CStringData::Release((ATL::CStringData *)(lpString2 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v64 - 24));
LABEL_64:
      RtlReleaseResource(v19);
      Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)lpString1);
      ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v80);
      goto LABEL_65;
    }
    v26 = (LPCWCH *)(*(__int64 (__fastcall **)(struct CSingleIdentity *, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      &v61);
    v27 = lpString1[0];
    v28 = CompareStringOrdinal(lpString1[0], -1, *v26, -1, 1) != 2
       && CompareStringOrdinal(v27, -1, lpString2, -1, 1) != 2;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
    if ( v28 )
    {
      if ( !PPTraceShouldRedact() || (LOBYTE(v30) = 1, !PPTraceStatus::TraceOnFlag(v30, v29)) )
        v31 = 0;
      v77[1] = lpString2;
      v77[2] = 0;
      v78 = v31;
      v77[0] = &PPRedactedStringW::`vftable';
      String = PPRedactedStringW::GetString((PPRedactedStringW *)v77);
      if ( !PPTraceShouldRedact() || (LOBYTE(v34) = 1, v35 = 1, !PPTraceStatus::TraceOnFlag(v34, v33)) )
        v35 = 0;
      v75[1] = *(_QWORD *)(*(__int64 (__fastcall **)(struct CSingleIdentity *, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(
                            a2,
                            &v61);
      v75[2] = 0;
      v76 = v35;
      v75[0] = &PPRedactedStringW::`vftable';
      v36 = PPRedactedStringW::GetString((PPRedactedStringW *)v75);
      if ( !PPTraceShouldRedact() || (LOBYTE(v38) = 1, !PPTraceStatus::TraceOnFlag(v38, v37)) )
        LOBYTE(v20) = 0;
      v73[1] = v27;
      v73[2] = 0;
      v74 = v20;
      v73[0] = &PPRedactedStringW::`vftable';
      v39 = PPRedactedStringW::GetString((PPRedactedStringW *)v73);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0xE92u,
        L"Current connected username (%ls) does not match request (IdentityName: %ls, AuthMemberName: %ls), skipping inter"
         "rupt notification update.",
        v39,
        v36,
        String);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v73);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v75);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v77);
      goto LABEL_63;
    }
    InterruptNotifications::GetCacheState((struct IServiceExecutionContext *)v80, &v66.HighPart, &v67);
    IsConnected = CAutoImpersonateClient::GetTokenUser(this, &v62);
    v82 = IsConnected;
    v40 = 0;
    if ( IsConnected < 0 )
    {
      v23 = "hr = pClient->GetTokenUser(sid)";
      v24 = 3744;
      goto LABEL_9;
    }
    v41 = a8;
    if ( a1 >= 0 && ShouldUpdateLogonCache(a2, a8) )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
      v72 = (unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *))(v81[0] + 24LL))(v81);
      LOBYTE(a6) = 0;
      v42 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)a2 + 8LL))(a2);
      v43 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&v69,
              L"ps:password");
      IsUserDomainConnected = CIdentityCredentialBag::RetrieveCredential(v42, v43, &v61, 0);
      v82 = IsUserDomainConnected;
      v40 = 0;
      if ( IsUserDomainConnected < 0 )
      {
        v45 = "hr = pIdentity->GetCredBag()->RetrieveCredential( PPCRL_CREDTYPE_PASSWORD, password)";
        v46 = 3756;
LABEL_35:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "DoActionCenterNotification",
          v46,
          IsUserDomainConnected,
          v45);
LABEL_36:
        CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v61);
        goto LABEL_63;
      }
      if ( v66.HighPart == -2147186642 || v66.HighPart == -2147186612 || v66.HighPart == -2147186500 )
      {
        v47 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)a2 + 8LL))(a2);
        v48 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64 *)&v69,
                L"ps:password");
        IsUserDomainConnected = CIdentityCredentialBag::PersistCredential(v47, 0, v48);
        v82 = IsUserDomainConnected;
        v40 = 0;
        if ( IsUserDomainConnected < 0 )
        {
          v45 = "hr = pIdentity->GetCredBag()->PersistCredential(false, PPCRL_CREDTYPE_PASSWORD)";
          v46 = 3762;
          goto LABEL_35;
        }
      }
      IsUserDomainConnected = SystemStoreLite::IsUserDomainConnected(
                                (struct IExecutionContextLite *)v81,
                                v62,
                                (bool *)&a6);
      v82 = IsUserDomainConnected;
      if ( IsUserDomainConnected < 0 )
      {
        v45 = "hr = SystemStoreLite::IsUserDomainConnected( serviceExecutionContext.GetExternalExecutionContextLite(), st"
              "atic_cast<LPCWSTR>(sid), isDomainConnected)";
        v46 = 3768;
        goto LABEL_35;
      }
      if ( !(_BYTE)a6
        && !(*(unsigned int (__fastcall **)(unsigned __int16 *, LPCWCH, _QWORD, unsigned __int16 *, int, _DWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v72 + 272LL))(
              v72,
              lpString2,
              0,
              v61,
              2,
              0,
              0,
              0,
              0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v82 = LastError;
        bIgnoreCaseb[0] = LastError;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0xEC6u,
          L"Failure - LogonUserExExW, HRESULT: 0x%08X\n",
          *(_QWORD *)bIgnoreCaseb);
        goto LABEL_36;
      }
      CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v61);
    }
    IsConnected = InterruptNotifications::GetNotificationData(
                    a1,
                    (struct IServiceExecutionContext *)v80,
                    (__int64)a7,
                    a5,
                    ((unsigned __int64)v41 + 64) & ((unsigned __int128)-(__int128)(unsigned __int64)v41 >> 64),
                    (__int64)&v68,
                    (__int64)&v64,
                    (__int64)&v63,
                    (__int64)v65);
    v82 = IsConnected;
    if ( IsConnected >= 0 )
    {
      if ( (_DWORD)v71 == 1 || v67 && *(int *)v65 >= 0 )
      {
        if ( v41 )
          v40 = *((_BYTE *)v41 + 98);
        a6 = -1;
        SessionId = CAutoImpersonateClient::GetSessionId(v83, &a6);
        if ( SessionId < 0 )
        {
          a6 = -1;
          bIgnoreCasec[0] = SessionId;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            0xEE9u,
            L"GetCallingProcessSessionId - Failed to get calling process session ID. hr = 0x%x.",
            *(_QWORD *)bIgnoreCasec);
        }
        v51 = a6;
        v72 = (unsigned __int16 *)v63;
        v69 = (unsigned __int16 *)v64;
        v61 = *(unsigned __int16 **)(*(__int64 (__fastcall **)(struct CSingleIdentity *, __int64 *))(*(_QWORD *)a2 + 16LL))(
                                      a2,
                                      &v71);
        v52 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)a2 + 56LL))(a2);
        if ( v52 != *(_DWORD *)v65 && a1 != -2147186655 )
          v20 = 0;
        InterruptNotifications::TriggerNotificationUpdate(
          (struct IServiceExecutionContext *)v80,
          *(int *)v65,
          v68,
          v20,
          v61,
          v69,
          v72,
          v27,
          v51,
          v40,
          v59);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
      }
      goto LABEL_63;
    }
    v23 = "hr = InterruptNotifications::GetNotificationData( hrRequest, &serviceExecutionContext, pIdentity, static_cast<"
          "LPCWSTR>(sid), pRequestParams, requestCount, pRSTRequest, notificationFlags, triggerRequestTargets, triggerReq"
          "uestPolicies, hrRequestStatus )";
    v24 = 3802;
    goto LABEL_9;
  }
  bIgnoreCasea[0] = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(v13 + 80))(a2);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0xE43u,
    L"No notification because: Usertype is = 0x%x.",
    *(_QWORD *)bIgnoreCasea);
LABEL_65:
  v53 = v82;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v79);
  return v53;
}

```

## disassembly

```asm
0x180029088  mov     [rsp-8+arg_0], rbx
0x18002908d  mov     [rsp-8+arg_18], r9
0x180029092  push    rbp
0x180029093  push    rsi
0x180029094  push    rdi
0x180029095  push    r12
0x180029097  push    r13
0x180029099  push    r14
0x18002909b  push    r15
0x18002909d  lea     rbp, [rsp-140h]
0x1800290a5  sub     rsp, 240h
0x1800290ac  mov     r15, r9
0x1800290af  mov     rbx, r8
0x1800290b2  mov     rdi, rdx
0x1800290b5  mov     r13d, ecx
0x1800290b8  xor     r12d, r12d
0x1800290bb  mov     [rbp+170h+arg_8], r12d
0x1800290c2  lea     r14, aDoactioncenter; "DoActionCenterNotification"
0x1800290c9  mov     [rbp+170h+var_138], r14
0x1800290cd  lea     rax, [rbp+170h+arg_8]
0x1800290d4  mov     [rbp+170h+var_130], rax
0x1800290d8  mov     [rbp+170h+var_128], r12
0x1800290dc  mov     [rbp+170h+var_120], r12
0x1800290e0  xor     r9d, r9d; unsigned int
0x1800290e3  mov     r8d, 0E37h; char *
0x1800290e9  mov     rdx, r14; char *
0x1800290ec  lea     rsi, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800290f3  mov     rcx, rsi; this
0x1800290f6  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800290fb  nop
0x1800290fc  mov     rax, [rdi]
0x1800290ff  mov     rcx, rdi
0x180029102  mov     rax, [rax+50h]
0x180029106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002910b  mov     r8, [rdi]
0x18002910e  mov     rcx, rdi
0x180029111  test    eax, eax
0x180029113  jz      short loc_180029141
0x180029115  mov     rax, [r8+50h]
0x180029119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002911e  mov     [rsp+270h+bIgnoreCase], eax
0x180029122  lea     r9, aNoNotification; "No notification because: Usertype is = "...
0x180029129  mov     r8d, 0E43h; unsigned int
0x18002912f  mov     rdx, rsi; char *
0x180029132  lea     ecx, [r12+5]; unsigned __int8
0x180029137  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002913c  jmp     loc_18002991A
0x180029141  lea     rdx, [rsp+270h+var_208]
0x180029146  mov     rax, [r8+10h]
0x18002914a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002914f  mov     rdx, [rax]
0x180029152  call    ?IsApplicationFullTrust@ExtensionAPI@@YAHW4MSA_APP_LIST_QUALIFIER@@PEBG@Z; ExtensionAPI::IsApplicationFullTrust(MSA_APP_LIST_QUALIFIER,ushort const *)
0x180029157  mov     dword ptr [rbp+170h+var_1B0], eax
0x18002915a  mov     rcx, [rsp+270h+var_208]
0x18002915f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180029163  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180029168  mov     [rbp+170h+var_1E4.LowPart], r12d
0x18002916c  lea     r8, [rbp+170h+var_1E4]; struct _LUID *
0x180029170  mov     rdx, rbx; unsigned int
0x180029173  call    ?CallerIsLoggedOnUser@MsaUserExtImpl@@YAJKPEAU_LUID@@PEAH@Z; MsaUserExtImpl::CallerIsLoggedOnUser(ulong,_LUID *,int *)
0x180029178  test    eax, eax
0x18002917a  jns     short loc_1800291A1
0x18002917c  lea     rcx, aMsauserextimpl; "MsaUserExtImpl::CallerIsLoggedOnUser(0,"...
0x180029183  mov     qword ptr [rsp+270h+bIgnoreCase], rcx; char *
0x180029188  mov     r9d, eax; int
0x18002918b  mov     r8d, 0E53h; unsigned int
0x180029191  mov     rdx, r14; char *
0x180029194  mov     rcx, rsi; char *
0x180029197  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002919c  jmp     loc_18002991A
0x1800291a1  cmp     [rbp+170h+var_1E4.LowPart], r12d
0x1800291a5  jnz     short loc_1800291C6
0x1800291a7  lea     r9, aSessionIsNotLo; "Session is not logged on."
0x1800291ae  mov     r8d, 0E57h; unsigned int
0x1800291b4  mov     rdx, rsi; char *
0x1800291b7  mov     ecx, 5; unsigned __int8
0x1800291bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800291c1  jmp     loc_18002991A
0x1800291c6  lea     rcx, [rbp+170h+var_110]; this
0x1800291ca  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800291cf  nop
0x1800291d0  mov     [rbp+170h+lpString1], r12
0x1800291d4  mov     [rbp+170h+var_1B8], r12
0x1800291d8  mov     [rbp+170h+var_1C0], r12
0x1800291dc  mov     [rbp+170h+arg_28], r12d
0x1800291e3  mov     r14, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800291ea  add     r14, 858h
0x1800291f1  mov     [rbp+170h+var_118], r14
0x1800291f5  mov     esi, 1
0x1800291fa  mov     dl, sil; Wait
0x1800291fd  mov     rcx, r14; Resource
0x180029200  call    cs:__imp_RtlAcquireResourceShared
0x180029206  nop
0x180029207  mov     [rbp+170h+var_1D8], r12d
0x18002920b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180029212  lea     r12, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180029219  mov     rcx, r12
0x18002921c  mov     rax, [rax+18h]
0x180029220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029225  add     rax, 18h
0x180029229  mov     [rbp+170h+var_1F0], rax
0x18002922d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180029234  mov     rcx, r12
0x180029237  mov     rax, [rax+18h]
0x18002923b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029240  add     rax, 18h
0x180029244  mov     [rsp+270h+var_1F8], rax
0x180029249  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180029250  mov     rcx, r12
0x180029253  mov     rax, [rax+18h]
0x180029257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002925c  lea     rbx, [rax+18h]
0x180029260  mov     [rsp+270h+var_200], rbx
0x180029265  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002926c  mov     rcx, r12
0x18002926f  mov     rax, [rax+18h]
0x180029273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029278  add     rax, 18h
0x18002927c  mov     [rsp+270h+lpString2], rax
0x180029281  xor     r12d, r12d
0x180029284  mov     dword ptr [rbp+170h+var_1E8], r12d
0x180029288  mov     [rbp+170h+var_1E4.HighPart], r12d
0x18002928c  mov     [rbp+170h+var_1DC], r12d
0x180029290  lea     r8, [rbp+170h+lpString1]; unsigned __int16 **
0x180029294  lea     rdx, [rbp+170h+arg_28]; int *
0x18002929b  lea     rcx, [rbp+170h+var_D8]; struct IExecutionContextLite *
0x1800292a2  call    ?IsConnected@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEAHPEAPEAG@Z; SystemStoreLite::IsConnected(IExecutionContextLite *,int *,ushort * *)
0x1800292a7  mov     [rbp+170h+arg_8], eax
0x1800292ad  test    eax, eax
0x1800292af  jns     short loc_1800292DE
0x1800292b1  lea     rcx, aHrSystemstorel_3; "hr = SystemStoreLite::IsConnected(servi"...
0x1800292b8  mov     r8d, 0E6Ch; unsigned int
0x1800292be  mov     qword ptr [rsp+270h+bIgnoreCase], rcx; char *
0x1800292c3  mov     r9d, eax; int
0x1800292c6  lea     rdx, aDoactioncenter; "DoActionCenterNotification"
0x1800292cd  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800292d4  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800292d9  jmp     loc_1800298D2
0x1800292de  cmp     [rbp+170h+arg_28], r12d
0x1800292e5  jnz     short loc_18002930A
0x1800292e7  lea     r9, aCurrentUserIsN; "Current user is not connected, skipping"...
0x1800292ee  mov     r8d, 0E6Fh; unsigned int
0x1800292f4  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800292fb  mov     ecx, 5; unsigned __int8
0x180029300  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180029305  jmp     loc_1800298D2
0x18002930a  mov     rax, [rdi]
0x18002930d  lea     r8, [rsp+270h+lpString2]
0x180029312  lea     rdx, aAuthmembername; "AuthMembername"
0x180029319  mov     rcx, rdi
0x18002931c  mov     rax, [rax+40h]
0x180029320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029325  mov     [rbp+170h+arg_8], eax
0x18002932b  test    eax, eax
0x18002932d  jns     short loc_180029392
0x18002932f  lea     rcx, aHrPidentityGet; "hr = pIdentity->GetCredProperty(PPCRL_C"...
0x180029336  mov     qword ptr [rsp+270h+bIgnoreCase], rcx; char *
0x18002933b  mov     r9d, eax; int
0x18002933e  mov     r8d, 0E86h; unsigned int
0x180029344  lea     rdx, aDoactioncenter; "DoActionCenterNotification"
0x18002934b  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180029352  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180029357  nop
0x180029358  mov     rcx, [rsp+270h+lpString2]
0x18002935d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180029361  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180029366  nop
0x180029367  lea     rcx, [rbx-18h]; this
0x18002936b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180029370  nop
0x180029371  mov     rcx, [rsp+270h+var_1F8]
0x180029376  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002937a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002937f  nop
0x180029380  mov     rcx, [rbp+170h+var_1F0]
0x180029384  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180029388  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002938d  jmp     loc_1800298FD
0x180029392  mov     rax, [rdi]
0x180029395  lea     rdx, [rsp+270h+var_208]
0x18002939a  mov     rcx, rdi
0x18002939d  mov     rax, [rax+20h]
0x1800293a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293a6  mov     [rsp+270h+bIgnoreCase], esi; bIgnoreCase
0x1800293aa  or      ebx, 0FFFFFFFFh
0x1800293ad  mov     r9d, ebx; cchCount2
0x1800293b0  mov     r8, [rax]; lpString2
0x1800293b3  mov     edx, ebx; cchCount1
0x1800293b5  mov     r12, [rbp+170h+lpString1]
0x1800293b9  mov     rcx, r12; lpString1
0x1800293bc  call    cs:__imp_CompareStringOrdinal
0x1800293c2  cmp     eax, 2
0x1800293c5  jz      short loc_1800293E8
0x1800293c7  mov     [rsp+270h+bIgnoreCase], esi; bIgnoreCase
0x1800293cb  mov     r9d, ebx; cchCount2
0x1800293ce  mov     r8, [rsp+270h+lpString2]; lpString2
0x1800293d3  mov     edx, ebx; cchCount1
0x1800293d5  mov     rcx, r12; lpString1
0x1800293d8  call    cs:__imp_CompareStringOrdinal
0x1800293de  cmp     eax, 2
0x1800293e1  jz      short loc_1800293E8
0x1800293e3  mov     bl, sil
0x1800293e6  jmp     short loc_1800293EA
0x1800293e8  xor     bl, bl
0x1800293ea  lea     rcx, [rsp+270h+var_208]
0x1800293ef  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800293f4  test    bl, bl
0x1800293f6  jz      loc_18002951F
0x1800293fc  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180029401  xor     r13d, r13d
0x180029404  test    al, al
0x180029406  jz      short loc_180029414
0x180029408  mov     cl, sil; this
0x18002940b  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180029410  test    al, al
0x180029412  jnz     short loc_180029417
0x180029414  mov     cl, r13b
0x180029417  mov     rax, [rsp+270h+lpString2]
0x18002941c  mov     [rbp+170h+var_150], rax
0x180029420  mov     [rbp+170h+var_148], r13
0x180029424  mov     [rbp+170h+var_140], cl
0x180029427  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x18002942e  mov     [rbp+170h+var_158], rax
0x180029432  lea     rcx, [rbp+170h+var_158]; this
0x180029436  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x18002943b  mov     r15, rax
0x18002943e  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180029443  test    al, al
0x180029445  jz      short loc_180029456
0x180029447  mov     cl, sil; this
0x18002944a  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18002944f  test    al, al
0x180029451  mov     bl, sil
0x180029454  jnz     short loc_180029459
0x180029456  mov     bl, r13b
0x180029459  mov     rax, [rdi]
0x18002945c  lea     rdx, [rsp+270h+var_208]
0x180029461  mov     rcx, rdi
0x180029464  mov     rax, [rax+20h]
0x180029468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002946d  nop
0x18002946e  mov     rax, [rax]
0x180029471  mov     [rbp+170h+var_170], rax
0x180029475  mov     [rbp+170h+var_168], r13
0x180029479  mov     [rbp+170h+var_160], bl
0x18002947c  lea     rdi, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180029483  mov     [rbp+170h+var_178], rdi
0x180029487  lea     rcx, [rbp+170h+var_178]; this
0x18002948b  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180029490  mov     rbx, rax
0x180029493  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180029498  test    al, al
0x18002949a  jz      short loc_1800294A8
0x18002949c  mov     cl, sil; this
0x18002949f  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x1800294a4  test    al, al
0x1800294a6  jnz     short loc_1800294AB
0x1800294a8  mov     sil, r13b
0x1800294ab  mov     [rbp+170h+var_190], r12
0x1800294af  mov     [rbp+170h+var_188], r13
0x1800294b3  mov     [rbp+170h+var_180], sil
0x1800294b7  mov     [rbp+170h+var_198], rdi
0x1800294bb  lea     rcx, [rbp+170h+var_198]; this
0x1800294bf  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x1800294c4  mov     [rsp+270h+var_240], r15
0x1800294c9  mov     [rsp+270h+var_248], rbx
0x1800294ce  mov     qword ptr [rsp+270h+bIgnoreCase], rax
0x1800294d3  lea     r9, aCurrentConnect; "Current connected username (%ls) does n"...
0x1800294da  mov     r8d, 0E92h; unsigned int
0x1800294e0  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800294e7  mov     ecx, 5; unsigned __int8
0x1800294ec  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800294f1  nop
0x1800294f2  lea     rcx, [rbp+170h+var_198]; this
0x1800294f6  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x1800294fb  nop
0x1800294fc  lea     rcx, [rbp+170h+var_178]; this
0x180029500  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180029505  nop
0x180029506  lea     rcx, [rsp+270h+var_208]
0x18002950b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180029510  nop
0x180029511  lea     rcx, [rbp+170h+var_158]; this
0x180029515  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x18002951a  jmp     loc_1800298D2
0x18002951f  lea     r8, [rbp+170h+var_1DC]; int *
0x180029523  lea     rdx, [rbp+170h+var_1E4.HighPart]; int *
0x180029527  lea     rcx, [rbp+170h+var_110]; struct IServiceExecutionContext *
0x18002952b  call    ?GetCacheState@InterruptNotifications@@SAJPEAVIServiceExecutionContext@@AEAJAEAH@Z; InterruptNotifications::GetCacheState(IServiceExecutionContext *,long &,int &)
0x180029530  lea     rdx, [rsp+270h+var_200]
0x180029535  mov     rcx, r15; this
0x180029538  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002953d  mov     [rbp+170h+arg_8], eax
0x180029543  xor     ebx, ebx
0x180029545  test    eax, eax
0x180029547  jns     short loc_18002955B
0x180029549  lea     rcx, aHrPclientGetto; "hr = pClient->GetTokenUser(sid)"
0x180029550  mov     r8d, 0EA0h
0x180029556  jmp     loc_1800292BE
0x18002955b  mov     r15, [rbp+170h+arg_38]
  ... truncated ...
```
