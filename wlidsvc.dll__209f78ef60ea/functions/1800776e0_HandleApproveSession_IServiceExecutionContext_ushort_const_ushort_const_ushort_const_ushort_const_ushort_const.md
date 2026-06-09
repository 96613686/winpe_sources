# HandleApproveSession(IServiceExecutionContext *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1800776e0`
- end: `0x18007848d`
- name: `?HandleApproveSession@@YAJPEAVIServiceExecutionContext@@PEBG1111_K@Z`
- size: `3501`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800784a0`

## callees

- `0x18000141c`
- `0x18000a354`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x18000fd48`
- `0x18001353c`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002d748`
- `0x18002df9c`
- `0x18003c814`
- `0x180043344`
- `0x180054fb4`
- `0x18005538c`
- `0x180055edc`
- `0x1800776e0`
- `0x180087a84`
- `0x1800a3b60`
- `0x1800a716c`
- `0x1800bc6c0`
- `0x18010e358`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800777ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077813`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077827`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077846`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007785a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077a51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077ea6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077eba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800781b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800781c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800777ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077813`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077827`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077846`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007785a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077a51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077ea6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077eba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800781b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800781c5`

## string_xrefs

- `0x1800777b0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077ae2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077bc4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077c49`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077d32`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077e34`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077f16`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077f68`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180077fe1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180078135`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18007823d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800783b1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180078022`: `login.live.com`
- `0x1800778c4`: `hr = pServiceWrapper->Impersonate(&client)`
- `0x18007794b`: `hr = pServiceWrapper->GetLogonId(&client, logonId)`
- `0x180077989`: `hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, pIdentity)`
- `0x180077911`: `hr = pServiceWrapper->HandleCreateContext(pUserName, CREATECONTEXT_SET_APP_IDENTITY, &hUserIdentity, c_sessionApprovalApplicationId)`
- `0x180077fc5`: `hr = pServiceWrapper->GetTokenUser(&client, accountSid)`
- `0x18007781d`: `ApproveUSID`
- `0x180077eb0`: `ApproveUSID`
- `0x1800781bb`: `ApproveUSID`
- `0x180077ac6`: `hr = pServiceWrapper->GetDeviceIdInternal( g_szStrongAuthAppId, IDCRL_DEVICE_ID_FROMCACHE, 0 , nullptr , nullptr , nullptr , &pDeviceIdentity)`
- `0x180077b55`: `hr = pIdentityWrapper->GetOneTimeCredential( pDeviceIdentity, 0, PPCRL_OTC_REQUESTING_APPID, nullptr, nullptr, nullptr, url, deviceToken, nullptr)`
- `0x180077d16`: `hr = pRequestWrapper->BuildApproveSessionRequest( pRequest, pExecutionContext, static_cast<LPCWSTR>(escapedDeviceToken), nullptr, pUserName, accountPuid, pAppVersion, pSessionID, pSessionState, pSessionType)`
- `0x180077e18`: `hr = pIdentityWrapper->GetOneTimeCredential( pIdentity, 0, PPCRL_OTC_REQUESTING_APPID, nullptr, nullptr, nullptr, url, userToken, nullptr)`
- `0x18007803d`: `hr = pNgcFunctions->NgcEnumUserIdKeys( PPCRL_MSA_IDP_DOMAIN, nullptr, static_cast<PCWSTR>(accountCid), static_cast<PCWSTR>(accountSid), &spKeyInfo, &spEnumState)`
- `0x1800780b1`: `hr = SetNgcKeyName(pExecutionContext, pIdentity, accountCid, accountSid)`
- `0x180078315`: `hr = pRequestWrapper->BuildApproveSessionRequest( pRequest, pExecutionContext, nullptr, static_cast<LPCWSTR>(escapedUserToken), pUserName, accountPuid, pAppVersion, pSessionID, pSessionState, pSessionType)`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall HandleApproveSession(
        struct IServiceExecutionContext *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int64 a7)
{
  CPPCRLRequest *v12; // rbx
  unsigned int v13; // r8d
  __int64 v14; // r12
  __int64 v15; // r14
  __int64 v16; // rsi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  CPPCRLRequest *v21; // rax
  int v22; // eax
  __int64 (__fastcall *v23)(__int64, const unsigned __int16 *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *); // rdi
  int v24; // eax
  const char *v25; // rcx
  unsigned int v26; // r8d
  int v27; // eax
  int v28; // eax
  const char *v29; // rcx
  unsigned int v30; // r8d
  int v31; // eax
  __int64 v32; // rdi
  int v33; // eax
  int v34; // eax
  const char *v35; // rcx
  unsigned int v36; // r8d
  struct IServiceExecutionContext *v37; // r12
  int v38; // eax
  const unsigned __int16 *v39; // r14
  const unsigned __int16 *v40; // rdi
  int v41; // eax
  const char *v42; // rcx
  unsigned int v43; // r8d
  unsigned int v44; // edi
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  char *v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h] BYREF
  int v53; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+88h] [rbp-78h] BYREF
  __int64 v55; // [rsp+90h] [rbp-70h] BYREF
  char v56; // [rsp+98h] [rbp-68h]
  struct IServiceExecutionContext *v57; // [rsp+A0h] [rbp-60h] BYREF
  char v58; // [rsp+A8h] [rbp-58h]
  _QWORD v59[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v60[3]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v61; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v62; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v63[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v64; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v65; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v66; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v67; // [rsp+120h] [rbp+20h]
  __int64 v68; // [rsp+128h] [rbp+28h] BYREF
  __int64 v69; // [rsp+130h] [rbp+30h] BYREF
  CPPCRLRequest *v70; // [rsp+138h] [rbp+38h]
  _QWORD v71[3]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v72[5]; // [rsp+158h] [rbp+58h] BYREF
  __int16 v73; // [rsp+180h] [rbp+80h] BYREF
  __int64 v74; // [rsp+188h] [rbp+88h]
  __int64 v75; // [rsp+190h] [rbp+90h]
  __int64 v76; // [rsp+198h] [rbp+98h]
  __int16 v77; // [rsp+1A0h] [rbp+A0h]
  __int64 v78; // [rsp+1A8h] [rbp+A8h]
  int v79; // [rsp+1B0h] [rbp+B0h]
  __int64 v80; // [rsp+1B8h] [rbp+B8h]
  int v81; // [rsp+1C0h] [rbp+C0h]
  __int128 v82; // [rsp+1C8h] [rbp+C8h]
  __int128 v83; // [rsp+1D8h] [rbp+D8h]
  __int64 v84; // [rsp+1E8h] [rbp+E8h]

  v67 = a4;
  v66 = a3;
  v65 = a2;
  v57 = a1;
  if ( MSAClientPlatformExtension::DoesPlatformSupportMediumIL() )
    return 2147500033LL;
  v49 = 0;
  v62 = 0;
  v69 = 0;
  v12 = 0;
  v70 = 0;
  v54 = 0;
  memset(v71, 0, sizeof(v71));
  v64 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
  v72[0] = "HandleApproveSession";
  v72[1] = &v49;
  v72[2] = 0;
  v72[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleApproveSession",
    (const char *)0x2EBA,
    0,
    (const unsigned __int16 *)v48);
  if ( !a2 || !*a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v13 = 11971;
    goto LABEL_98;
  }
  if ( !(unsigned int)_o__wcsicmp(a5, L"Approve")
    || !(unsigned int)_o__wcsicmp(a5, L"Deny")
    || !(unsigned int)_o__wcsicmp(a5, L"ApproveUSID") )
  {
    if ( (unsigned int)_o__wcsicmp(a6, L"Device") && (unsigned int)_o__wcsicmp(a6, L"NGC") )
    {
      v13 = 11984;
      goto LABEL_98;
    }
    v14 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
    v15 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
    v16 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 64LL))(a1);
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, &v62, 0);
    v49 = v17;
    if ( v17 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2EDBu,
        v17,
        "hr = pServiceWrapper->Impersonate(&client)");
      goto LABEL_99;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD *, const wchar_t *))(*(_QWORD *)v14 + 104LL))(
            v14,
            a2,
            0x800000,
            v71,
            L"{07f912dc-3518-4549-8286-7de7a2a443e6}");
    v49 = v18;
    if ( v18 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2EDCu,
        v18,
        "hr = pServiceWrapper->HandleCreateContext(pUserName, CREATECONTEXT_SET_APP_IDENTITY, &hUserIdentity, c_sessionAp"
        "provalApplicationId)");
      goto LABEL_99;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v14 + 40LL))(v14, &v62, &v69);
    v49 = v19;
    if ( v19 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2EDDu,
        v19,
        "hr = pServiceWrapper->GetLogonId(&client, logonId)");
      goto LABEL_99;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, __int64 *))(*(_QWORD *)v14 + 24LL))(
            v14,
            &v69,
            v71[0],
            &v54);
    v49 = v20;
    if ( v20 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2EDEu,
        v20,
        "hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, pIdentity)");
      goto LABEL_99;
    }
    v21 = (CPPCRLRequest *)operator new(0xF8u, (const struct std::nothrow_t *)std::nothrow);
    v12 = v21;
    v55 = (__int64)v21;
    if ( v21 )
    {
      CPPCRLRequest::CPPCRLRequest(v21);
      *(_QWORD *)v12 = &ApproveSessionRequest::`vftable'{for `CPPCRLBaseRequest'};
      *((_QWORD *)v12 + 8) = &ApproveSessionRequest::`vftable'{for `IPPCRLRequest'};
      *((_DWORD *)v12 + 60) = 0;
    }
    else
    {
      v12 = 0;
    }
    v70 = v12;
    if ( !v12 )
    {
      v49 = -2147024882;
      goto LABEL_100;
    }
    *((_QWORD *)v12 + 28) = a7;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, CPPCRLRequest *))(*(_QWORD *)v16 + 152LL))(v16, v54, v12);
    v49 = v22;
    if ( v22 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2EE3u,
        v22,
        "hr = pRequestWrapper->InitializeApproveSessionRequest(pIdentity, pRequest)");
      goto LABEL_99;
    }
    if ( !(unsigned int)_o__wcsicmp(a6, L"Device") )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
      v23 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v14 + 128LL);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v64);
      v24 = v23(v14, L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}", 16, 0, 0, 0, 0, &v64);
      v49 = v24;
      if ( v24 < 0 )
      {
        v25 = "hr = pServiceWrapper->GetDeviceIdInternal( g_szStrongAuthAppId, IDCRL_DEVICE_ID_FROMCACHE, 0 , nullptr , n"
              "ullptr , nullptr , &pDeviceIdentity)";
        v26 = 12019;
LABEL_34:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleApproveSession",
          v26,
          v24,
          v25);
LABEL_35:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
        goto LABEL_99;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v15 + 96LL))(
              v15,
              v64,
              0,
              L"Default",
              0,
              0,
              0,
              &v68,
              &v50,
              0);
      v49 = v24;
      if ( v24 < 0 )
      {
        v25 = "hr = pIdentityWrapper->GetOneTimeCredential( pDeviceIdentity, 0, PPCRL_OTC_REQUESTING_APPID, nullptr, null"
              "ptr, nullptr, url, deviceToken, nullptr)";
        v26 = 12030;
        goto LABEL_34;
      }
      SanitizeAndEscapeXML(v50, &v51);
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, const WCHAR *, __int64 *))(*(_QWORD *)v15 + 112LL))(
              v15,
              v54,
              L"PUID",
              &v61);
      v49 = v24;
      if ( v24 < 0 )
      {
        v25 = "hr = pIdentityWrapper->GetCredProperty(pIdentity, PPCRL_CREDPROPERTY_PUIDSTR, accountPuid)";
        v26 = 12036;
        goto LABEL_34;
      }
      if ( !*(_DWORD *)(v61 - 16) )
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x2F07u,
          L"PUID is not set for the current identity.");
        v49 = -2147186543;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleApproveSession",
          0x2F08u,
          -2147186543,
          "hr = PPCRL_E_CREDPROP_NOTFOUND");
        goto LABEL_35;
      }
      v55 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 8LL))(v15, v54);
      v56 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 16LL))(v15, &v55);
      v49 = v27;
      if ( v27 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleApproveSession",
          0x2F0Du,
          v27,
          "hr = pIdentityWrapper->Lock(&lock)");
LABEL_44:
        CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v55);
        goto LABEL_35;
      }
      v73 = 0;
      v74 = 0;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      v81 = 0;
      v82 = 0;
      v83 = 0;
      v84 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, CPPCRLRequest *, struct IServiceExecutionContext *, __int64, _QWORD, const unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v16 + 160LL))(
              v16,
              v12,
              v57,
              v51,
              0,
              v65,
              v61,
              v66,
              v67,
              a5,
              a6);
      v49 = v28;
      if ( v28 >= 0 )
      {
        v28 = (*(__int64 (__fastcall **)(__int64, __int16 *, CPPCRLRequest *))(*(_QWORD *)v16 + 32LL))(v16, &v73, v12);
        v49 = v28;
        if ( v28 >= 0 )
        {
          v28 = (*(__int64 (__fastcall **)(__int64, CPPCRLRequest *))(*(_QWORD *)v16 + 176LL))(v16, v12);
          v49 = v28;
          if ( v28 >= 0 )
            goto LABEL_48;
          v29 = "hr = pRequestWrapper->GetApproveSessionRequestServerError(pRequest)";
          v30 = 12062;
        }
        else
        {
          v29 = "hr = pRequestWrapper->SendRequest(&transport, pRequest)";
          v30 = 12061;
        }
      }
      else
      {
        v29 = "hr = pRequestWrapper->BuildApproveSessionRequest( pRequest, pExecutionContext, static_cast<LPCWSTR>(escape"
              "dDeviceToken), nullptr, pUserName, accountPuid, pAppVersion, pSessionID, pSessionState, pSessionType)";
        v30 = 12059;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        v30,
        v28,
        v29);
LABEL_48:
      CTransport::~CTransport((CTransport *)&v73);
      goto LABEL_44;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
    ATL::CSimpleStringT<unsigned short,0>::Truncate(&v50, 0);
    v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _QWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v15 + 96LL))(
            v15,
            v54,
            0,
            L"Default",
            0,
            0,
            0,
            &v68,
            &v50,
            0);
    v49 = v31;
    if ( v31 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2F32u,
        v31,
        "hr = pIdentityWrapper->GetOneTimeCredential( pIdentity, 0, PPCRL_OTC_REQUESTING_APPID, nullptr, nullptr, nullptr"
        ", url, userToken, nullptr)");
      goto LABEL_35;
    }
    SanitizeAndEscapeXML(v50, &v51);
    v32 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)v57 + 48LL))(v57);
    v63[0] = 0;
    v63[2] = v32;
    v63[1] = 0;
    memset(v60, 0, sizeof(v60));
    v53 = 0;
    memset(v59, 0, sizeof(v59));
    if ( (unsigned int)_o__wcsicmp(a5, L"Approve") && (unsigned int)_o__wcsicmp(a5, L"ApproveUSID") )
    {
      v37 = v57;
    }
    else
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
      v33 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, __int64 *))(*(_QWORD *)v15 + 112LL))(
              v15,
              v54,
              L"CID",
              &v52);
      v49 = v33;
      if ( v33 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleApproveSession",
          0x2F44u,
          v33,
          "hr = pIdentityWrapper->GetCredProperty(pIdentity, PPCRL_CREDPROPERTY_CID, accountCid)");
LABEL_59:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
LABEL_60:
        Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v59);
        Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v60);
        Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(v63);
        goto LABEL_35;
      }
      if ( !*(_DWORD *)(v52 - 16) )
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x2F47u,
          L"CID is not set for the current identity.");
        v49 = -2147186543;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleApproveSession",
          0x2F48u,
          -2147186543,
          "hr = PPCRL_E_CREDPROP_NOTFOUND");
        goto LABEL_59;
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
      v34 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v14 + 72LL))(v14, &v62, &v55);
      v49 = v34;
      if ( v34 < 0 )
      {
        v35 = "hr = pServiceWrapper->GetTokenUser(&client, accountSid)";
        v36 = 12109;
LABEL_65:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleApproveSession",
          v36,
          v34,
          v35);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
        goto LABEL_59;
      }
      v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64, __int64, _QWORD *, _QWORD *))(*(_QWORD *)v32 + 72LL))(
              v32,
              L"login.live.com",
              0,
              v52,
              v55,
              v60,
              v63);
      v49 = v34;
      if ( v34 < 0 )
      {
        v35 = "hr = pNgcFunctions->NgcEnumUserIdKeys( PPCRL_MSA_IDP_DOMAIN, nullptr, static_cast<PCWSTR>(accountCid), sta"
              "tic_cast<PCWSTR>(accountSid), &spKeyInfo, &spEnumState)";
        v36 = 12118;
        goto LABEL_65;
      }
      if ( v60[0] && *(_DWORD *)(v60[0] + 40LL) == 2 )
      {
        v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, int *))(*(_QWORD *)v32 + 112LL))(
                v32,
                *(_QWORD *)(v60[0] + 32LL),
                v59,
                &v53);
        v49 = v34;
        if ( v34 < 0 )
        {
          v35 = "hr = pNgcFunctions->NgcGetUserIdKeyPublicKey( spKeyInfo->pwszKeyName, &ngcPublicKey, &ngcPublicKeySizeBytes)";
          v36 = 12126;
          goto LABEL_65;
        }
        v37 = v57;
        v34 = SetNgcKeyName(v57, &v54, v52, v55);
        v49 = v34;
        if ( v34 < 0 )
        {
          v35 = "hr = SetNgcKeyName(pExecutionContext, pIdentity, accountCid, accountSid)";
          v36 = 12128;
          goto LABEL_65;
        }
      }
      else
      {
        v37 = v57;
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
    }
    v57 = (struct IServiceExecutionContext *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 8LL))(
                                               v15,
                                               v54);
    v58 = 0;
    v38 = (*(__int64 (__fastcall **)(__int64, struct IServiceExecutionContext **))(*(_QWORD *)v15 + 16LL))(v15, &v57);
    v49 = v38;
    if ( v38 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleApproveSession",
        0x2F66u,
        v38,
        "hr = pIdentityWrapper->Lock(&lock)");
LABEL_79:
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v57);
      goto LABEL_60;
    }
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    if ( (unsigned int)_o__wcsicmp(a5, L"Approve") && (unsigned int)_o__wcsicmp(a5, L"ApproveUSID") )
    {
      v40 = v65;
      v39 = v66;
    }
    else
    {
      v39 = v66;
      v40 = v65;
      v41 = (*(__int64 (__fastcall **)(__int64, CPPCRLRequest *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, int))(*(_QWORD *)v16 + 168LL))(
              v16,
              v12,
              v65,
              v66,
              v67,
              a5,
              a6,
              v59[0],
              v53);
      v49 = v41;
      if ( v41 < 0 )
      {
        v42 = "hr = pRequestWrapper->BuildApproveSessionNonceRequest( pRequest, pUserName, pAppVersion, pSessionID, pSess"
              "ionState, pSessionType, static_cast<BYTE*>(ngcPublicKey), ngcPublicKeySizeBytes)";
        v43 = 12149;
        goto LABEL_84;
      }
      v41 = (*(__int64 (__fastcall **)(__int64, __int16 *, CPPCRLRequest *))(*(_QWORD *)v16 + 32LL))(v16, &v73, v12);
      v49 = v41;
      if ( v41 < 0 )
      {
        v42 = "hr = pRequestWrapper->SendRequest(&transport, pRequest)";
        v43 = 12151;
        goto LABEL_84;
      }
      v41 = (*(__int64 (__fastcall **)(__int64, CPPCRLRequest *))(*(_QWORD *)v16 + 176LL))(v16, v12);
      v49 = v41;
      if ( v41 < 0 )
      {
        v42 = "hr = pRequestWrapper->GetApproveSessionRequestServerError(pRequest)";
        v43 = 12152;
        goto LABEL_84;
      }
    }
    v41 = (*(__int64 (__fastcall **)(__int64, CPPCRLRequest *, struct IServiceExecutionContext *, _QWORD, __int64, const unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v16 + 160LL))(
            v16,
            v12,
            v37,
            0,
            v51,
            v40,
            v61,
            v39,
            v67,
            a5,
            a6);
    v49 = v41;
    if ( v41 >= 0 )
    {
      v41 = (*(__int64 (__fastcall **)(__int64, __int16 *, CPPCRLRequest *))(*(_QWORD *)v16 + 32LL))(v16, &v73, v12);
      v49 = v41;
      if ( v41 >= 0 )
      {
        v41 = (*(__int64 (__fastcall **)(__int64, CPPCRLRequest *))(*(_QWORD *)v16 + 176LL))(v16, v12);
        v49 = v41;
        if ( v41 >= 0 )
          goto LABEL_85;
        v42 = "hr = pRequestWrapper->GetApproveSessionRequestServerError(pRequest)";
        v43 = 12169;
      }
      else
      {
        v42 = "hr = pRequestWrapper->SendRequest(&transport, pRequest)";
        v43 = 12168;
      }
    }
    else
    {
      v42 = "hr = pRequestWrapper->BuildApproveSessionRequest( pRequest, pExecutionContext, nullptr, static_cast<LPCWSTR>"
            "(escapedUserToken), pUserName, accountPuid, pAppVersion, pSessionID, pSessionState, pSessionType)";
      v43 = 12166;
    }
LABEL_84:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleApproveSession",
      v43,
      v41,
      v42);
LABEL_85:
    CTransport::~CTransport((CTransport *)&v73);
    goto LABEL_79;
  }
  v13 = 11978;
LABEL_98:
  v49 = -2147024809;
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleApproveSession",
    v13,
    -2147024809,
    "hr = E_INVALIDARG");
LABEL_99:
  v44 = v49;
  if ( v49 < 0 )
  {
LABEL_100:
    if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
    {
      v53 = v49;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v45,
        (__int64)byte_180197379,
        v46,
        v47,
        (__int64)&v53);
    }
    v44 = v49;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v72);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v64);
  Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(v71);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
  if ( v12 )
    (**(void (__fastcall ***)(CPPCRLRequest *, __int64))v12)(v12, 1);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v62);
  return v44;
}

```

## disassembly

```asm
0x1800776e0  push    rbp
0x1800776e2  push    rbx
0x1800776e3  push    rsi
0x1800776e4  push    rdi
0x1800776e5  push    r12
0x1800776e7  push    r13
0x1800776e9  push    r14
0x1800776eb  push    r15
0x1800776ed  lea     rbp, [rsp-108h]
0x1800776f5  sub     rsp, 208h
0x1800776fc  mov     rax, cs:__security_cookie
0x180077703  xor     rax, rsp
0x180077706  mov     [rbp+140h+var_50], rax
0x18007770d  mov     r12, r9
0x180077710  mov     [rbp+140h+var_120], r9
0x180077714  mov     r14, r8
0x180077717  mov     [rbp+140h+var_128], r8
0x18007771b  mov     rdi, rdx
0x18007771e  mov     [rbp+140h+var_130], rdx
0x180077722  mov     rsi, rcx
0x180077725  mov     [rbp+140h+var_1A0], rcx
0x180077729  mov     r15, [rbp+140h+arg_20]
0x180077730  mov     r13, [rbp+140h+arg_28]
0x180077737  call    ?DoesPlatformSupportMediumIL@MSAClientPlatformExtension@@SA_NXZ; MSAClientPlatformExtension::DoesPlatformSupportMediumIL(void)
0x18007773c  cmp     al, 1
0x18007773e  jnz     short loc_18007774A
0x180077740  mov     eax, 80004001h
0x180077745  jmp     loc_18007846A
0x18007774a  xor     eax, eax
0x18007774c  mov     [rsp+240h+var_1E0], eax
0x180077750  mov     [rbp+140h+var_158], rax
0x180077754  mov     [rbp+140h+var_110], rax
0x180077758  mov     ebx, eax
0x18007775a  mov     [rbp+140h+var_108], rax
0x18007775e  mov     [rbp+140h+var_1B8], rax
0x180077762  mov     [rbp+140h+var_100], rax
0x180077766  mov     [rbp+140h+var_F0], rax
0x18007776a  mov     [rbp+140h+var_F8], rax
0x18007776e  mov     [rbp+140h+var_138], rax
0x180077772  lea     rcx, [rbp+140h+var_118]
0x180077776  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18007777b  nop
0x18007777c  lea     rcx, [rbp+140h+var_160]
0x180077780  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180077785  nop
0x180077786  lea     rcx, aHandleapproves; "HandleApproveSession"
0x18007778d  mov     [rbp+140h+var_E8], rcx
0x180077791  lea     rax, [rsp+240h+var_1E0]
0x180077796  mov     [rbp+140h+var_E0], rax
0x18007779a  xor     eax, eax
0x18007779c  mov     [rbp+140h+var_D8], rax
0x1800777a0  mov     [rbp+140h+var_D0], rax
0x1800777a4  xor     r9d, r9d; unsigned int
0x1800777a7  mov     r8d, 2EBAh; char *
0x1800777ad  mov     rdx, rcx; char *
0x1800777b0  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800777b7  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800777bc  nop
0x1800777bd  xor     eax, eax
0x1800777bf  test    rdi, rdi
0x1800777c2  jz      loc_18007838D
0x1800777c8  cmp     [rdi], ax
0x1800777cb  jz      loc_18007838D
0x1800777d1  test    r14, r14
0x1800777d4  jz      loc_18007838D
0x1800777da  test    r12, r12
0x1800777dd  jz      loc_18007838D
0x1800777e3  test    r15, r15
0x1800777e6  jz      loc_18007838D
0x1800777ec  test    r13, r13
0x1800777ef  jz      loc_18007838D
0x1800777f5  lea     rdx, aApprove; "Approve"
0x1800777fc  mov     rcx, r15
0x1800777ff  call    cs:__imp__o__wcsicmp
0x180077805  test    eax, eax
0x180077807  jz      short loc_18007783C
0x180077809  lea     rdx, aDeny; "Deny"
0x180077810  mov     rcx, r15
0x180077813  call    cs:__imp__o__wcsicmp
0x180077819  test    eax, eax
0x18007781b  jz      short loc_18007783C
0x18007781d  lea     rdx, aApproveusid; "ApproveUSID"
0x180077824  mov     rcx, r15
0x180077827  call    cs:__imp__o__wcsicmp
0x18007782d  test    eax, eax
0x18007782f  jz      short loc_18007783C
0x180077831  mov     r8d, 2ECAh
0x180077837  jmp     loc_180078393
0x18007783c  lea     rdx, aDevice; "Device"
0x180077843  mov     rcx, r13
0x180077846  call    cs:__imp__o__wcsicmp
0x18007784c  test    eax, eax
0x18007784e  jz      short loc_18007786F
0x180077850  lea     rdx, aNgc; "NGC"
0x180077857  mov     rcx, r13
0x18007785a  call    cs:__imp__o__wcsicmp
0x180077860  test    eax, eax
0x180077862  jz      short loc_18007786F
0x180077864  mov     r8d, 2ED0h
0x18007786a  jmp     loc_180078393
0x18007786f  mov     rax, [rsi]
0x180077872  mov     rcx, rsi
0x180077875  mov     rax, [rax+50h]
0x180077879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007787e  mov     r12, rax
0x180077881  mov     rcx, [rsi]
0x180077884  mov     rax, [rcx+38h]
0x180077888  mov     rcx, rsi
0x18007788b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077890  mov     r14, rax
0x180077893  mov     rcx, [rsi]
0x180077896  mov     rax, [rcx+40h]
0x18007789a  mov     rcx, rsi
0x18007789d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778a2  mov     rsi, rax
0x1800778a5  mov     rcx, [r12]
0x1800778a9  mov     rax, [rcx+20h]
0x1800778ad  xor     r8d, r8d
0x1800778b0  lea     rdx, [rbp+140h+var_158]
0x1800778b4  mov     rcx, r12
0x1800778b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778bc  mov     [rsp+240h+var_1E0], eax
0x1800778c0  test    eax, eax
0x1800778c2  jns     short loc_1800778DE
0x1800778c4  lea     rcx, aHrPservicewrap_25; "hr = pServiceWrapper->Impersonate(&clie"...
0x1800778cb  mov     [rsp+240h+var_220], rcx
0x1800778d0  mov     r9d, eax
0x1800778d3  mov     r8d, 2EDBh
0x1800778d9  jmp     loc_1800783AA
0x1800778de  mov     rax, [r12]
0x1800778e2  lea     rcx, a07f912dc351845; "{07f912dc-3518-4549-8286-7de7a2a443e6}"
0x1800778e9  mov     [rsp+240h+var_220], rcx
0x1800778ee  lea     r9, [rbp+140h+var_100]
0x1800778f2  mov     r8d, 800000h
0x1800778f8  mov     rdx, rdi
0x1800778fb  mov     rcx, r12
0x1800778fe  mov     rax, [rax+68h]
0x180077902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077907  mov     [rsp+240h+var_1E0], eax
0x18007790b  xor     edi, edi
0x18007790d  test    eax, eax
0x18007790f  jns     short loc_18007792B
0x180077911  lea     rcx, aHrPservicewrap_14; "hr = pServiceWrapper->HandleCreateConte"...
0x180077918  mov     [rsp+240h+var_220], rcx
0x18007791d  mov     r9d, eax
0x180077920  mov     r8d, 2EDCh
0x180077926  jmp     loc_1800783AA
0x18007792b  mov     rax, [r12]
0x18007792f  lea     r8, [rbp+140h+var_110]
0x180077933  lea     rdx, [rbp+140h+var_158]
0x180077937  mov     rcx, r12
0x18007793a  mov     rax, [rax+28h]
0x18007793e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077943  mov     [rsp+240h+var_1E0], eax
0x180077947  test    eax, eax
0x180077949  jns     short loc_180077965
0x18007794b  lea     rcx, aHrPservicewrap_16; "hr = pServiceWrapper->GetLogonId(&clien"...
0x180077952  mov     [rsp+240h+var_220], rcx
0x180077957  mov     r9d, eax
0x18007795a  mov     r8d, 2EDDh
0x180077960  jmp     loc_1800783AA
0x180077965  mov     rax, [r12]
0x180077969  lea     r9, [rbp+140h+var_1B8]
0x18007796d  mov     r8, [rbp+140h+var_100]
0x180077971  lea     rdx, [rbp+140h+var_110]
0x180077975  mov     rcx, r12
0x180077978  mov     rax, [rax+18h]
0x18007797c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077981  mov     [rsp+240h+var_1E0], eax
0x180077985  test    eax, eax
0x180077987  jns     short loc_1800779A3
0x180077989  lea     rcx, aHrPservicewrap; "hr = pServiceWrapper->GetIdentityHandle"...
0x180077990  mov     [rsp+240h+var_220], rcx
0x180077995  mov     r9d, eax
0x180077998  mov     r8d, 2EDEh
0x18007799e  jmp     loc_1800783AA
0x1800779a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800779aa  mov     ecx, 0F8h; unsigned __int64
0x1800779af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800779b4  mov     rbx, rax
0x1800779b7  mov     [rbp+140h+var_1B0], rax
0x1800779bb  test    rax, rax
0x1800779be  jz      short loc_1800779E5
0x1800779c0  mov     rcx, rax; this
0x1800779c3  call    ??0CPPCRLRequest@@QEAA@XZ; CPPCRLRequest::CPPCRLRequest(void)
0x1800779c8  lea     rax, ??_7ApproveSessionRequest@@6BCPPCRLBaseRequest@@@; const ApproveSessionRequest::`vftable'{for `CPPCRLBaseRequest'}
0x1800779cf  mov     [rbx], rax
0x1800779d2  lea     rax, ??_7ApproveSessionRequest@@6BIPPCRLRequest@@@; const ApproveSessionRequest::`vftable'{for `IPPCRLRequest'}
0x1800779d9  mov     [rbx+40h], rax
0x1800779dd  mov     [rbx+0F0h], edi
0x1800779e3  jmp     short loc_1800779E8
0x1800779e5  mov     rbx, rdi
0x1800779e8  mov     [rbp+140h+var_108], rbx
0x1800779ec  test    rbx, rbx
0x1800779ef  jnz     short loc_1800779FE
0x1800779f1  mov     [rsp+240h+var_1E0], 8007000Eh
0x1800779f9  jmp     loc_1800783C5
0x1800779fe  mov     rax, [rbp+140h+arg_30]
0x180077a05  mov     [rbx+0E0h], rax
0x180077a0c  mov     rax, [rsi]
0x180077a0f  mov     r8, rbx
0x180077a12  mov     rdx, [rbp+140h+var_1B8]
0x180077a16  mov     rcx, rsi
0x180077a19  mov     rax, [rax+98h]
0x180077a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a25  mov     [rsp+240h+var_1E0], eax
0x180077a29  test    eax, eax
0x180077a2b  jns     short loc_180077A47
0x180077a2d  lea     rcx, aHrPrequestwrap_15; "hr = pRequestWrapper->InitializeApprove"...
0x180077a34  mov     [rsp+240h+var_220], rcx
0x180077a39  mov     r9d, eax
0x180077a3c  mov     r8d, 2EE3h
0x180077a42  jmp     loc_1800783AA
0x180077a47  lea     rdx, aDevice; "Device"
0x180077a4e  mov     rcx, r13
0x180077a51  call    cs:__imp__o__wcsicmp
0x180077a57  lea     rcx, [rsp+240h+var_1D8]
0x180077a5c  test    eax, eax
0x180077a5e  jnz     loc_180077DAF
0x180077a64  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180077a69  nop
0x180077a6a  lea     rcx, [rsp+240h+var_1D0]
0x180077a6f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180077a74  nop
0x180077a75  mov     rax, [r12]
0x180077a79  mov     rdi, [rax+80h]
0x180077a80  lea     rcx, [rbp+140h+var_138]
0x180077a84  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x180077a89  lea     rax, [rbp+140h+var_138]
0x180077a8d  mov     [rsp+240h+var_208], rax
0x180077a92  xor     eax, eax
0x180077a94  mov     [rsp+240h+var_210], rax
0x180077a99  mov     [rsp+240h+var_218], rax
0x180077a9e  mov     [rsp+240h+var_220], rax
0x180077aa3  xor     r9d, r9d
0x180077aa6  lea     r8d, [rax+10h]
0x180077aaa  lea     rdx, aAfda72bf340941; "{AFDA72BF-3409-413a-B54E-2AB8D66A7826}"
0x180077ab1  mov     rcx, r12
0x180077ab4  mov     rax, rdi
0x180077ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077abc  mov     [rsp+240h+var_1E0], eax
0x180077ac0  xor     edi, edi
0x180077ac2  test    eax, eax
0x180077ac4  jns     short loc_180077B09
0x180077ac6  lea     rcx, aHrPservicewrap_27; "hr = pServiceWrapper->GetDeviceIdIntern"...
0x180077acd  mov     r8d, 2EF3h; unsigned int
0x180077ad3  mov     [rsp+240h+var_220], rcx; char *
0x180077ad8  mov     r9d, eax; int
0x180077adb  lea     rdx, aHandleapproves; "HandleApproveSession"
0x180077ae2  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180077ae9  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180077aee  nop
0x180077aef  lea     rcx, [rsp+240h+var_1D0]
0x180077af4  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180077af9  nop
0x180077afa  lea     rcx, [rsp+240h+var_1D8]
0x180077aff  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180077b04  jmp     loc_1800783BD
0x180077b09  mov     rax, [r14]
0x180077b0c  mov     [rsp+240h+var_1F8], rdi
0x180077b11  lea     rcx, [rsp+240h+var_1D8]
0x180077b16  mov     [rsp+240h+var_200], rcx
0x180077b1b  lea     rcx, [rbp+140h+var_118]
0x180077b1f  mov     [rsp+240h+var_208], rcx
0x180077b24  mov     [rsp+240h+var_210], rdi
0x180077b29  mov     [rsp+240h+var_218], rdi
0x180077b2e  mov     [rsp+240h+var_220], rdi
0x180077b33  lea     r9, aDefault; "Default"
0x180077b3a  xor     r8d, r8d
0x180077b3d  mov     rdx, [rbp+140h+var_138]
0x180077b41  mov     rcx, r14
0x180077b44  mov     rax, [rax+60h]
0x180077b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b4d  mov     [rsp+240h+var_1E0], eax
0x180077b51  test    eax, eax
0x180077b53  jns     short loc_180077B67
0x180077b55  lea     rcx, aHrPidentitywra_3; "hr = pIdentityWrapper->GetOneTimeCreden"...
0x180077b5c  mov     r8d, 2EFEh
0x180077b62  jmp     loc_180077AD3
0x180077b67  lea     rdx, [rsp+240h+var_1D0]
0x180077b6c  mov     rcx, [rsp+240h+var_1D8]
0x180077b71  call    ?SanitizeAndEscapeXML@@YAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; SanitizeAndEscapeXML(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180077b76  mov     rax, [r14]
0x180077b79  lea     r9, [rbp+140h+var_160]
0x180077b7d  lea     r8, aPuid; "PUID"
0x180077b84  mov     rdx, [rbp+140h+var_1B8]
0x180077b88  mov     rcx, r14
0x180077b8b  mov     rax, [rax+70h]
0x180077b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b94  mov     [rsp+240h+var_1E0], eax
0x180077b98  test    eax, eax
0x180077b9a  jns     short loc_180077BAE
0x180077b9c  lea     rcx, aHrPidentitywra_8; "hr = pIdentityWrapper->GetCredProperty("...
0x180077ba3  mov     r8d, 2F04h
0x180077ba9  jmp     loc_180077AD3
0x180077bae  mov     rax, [rbp+140h+var_160]
0x180077bb2  cmp     [rax-10h], edi
0x180077bb5  jnz     short loc_180077BF7
0x180077bb7  lea     r9, aPuidIsNotSetFo; "PUID is not set for the current identit"...
0x180077bbe  mov     r8d, 2F07h; unsigned int
  ... truncated ...
```
