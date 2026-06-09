# HandleManageApprover(IServiceExecutionContext *,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int *)

- ea: `0x18009c4d0`
- end: `0x18009d260`
- name: `?HandleManageApprover@@YAJPEAVIServiceExecutionContext@@KPEBG1111PEAH@Z`
- size: `3472`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009c3a0`

## callees

- `0x18000141c`
- `0x18000a354`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x18000fd48`
- `0x18001426c`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180023208`
- `0x18002df9c`
- `0x18003c814`
- `0x180043344`
- `0x180053620`
- `0x180054fb4`
- `0x18005538c`
- `0x180055edc`
- `0x1800785c4`
- `0x18007a2e0`
- `0x180087a84`
- `0x180096a28`
- `0x18009c4d0`
- `0x1800a3b60`
- `0x1800a716c`
- `0x1800aea80`
- `0x1800f2d80`
- `0x18010e358`
- `0x180128010`

## string_xrefs

- `0x18009c5f0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009c88b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009c90b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009c987`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009ca00`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009ca9d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009cba0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009cc89`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009cd58`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009cdc8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009ce71`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009cf60`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009d038`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009d106`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009d146`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009c9cd`: `login.live.com`
- `0x18009c6e8`: `hr = pServiceWrapper->Impersonate(&client)`
- `0x18009c76b`: `hr = pServiceWrapper->GetLogonId(&client, logonId)`
- `0x18009c7a8`: `hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, pIdentity)`
- `0x18009c732`: `hr = pServiceWrapper->HandleCreateContext(pUserName, CREATECONTEXT_SET_APP_IDENTITY, &hUserIdentity, c_sessionApprovalApplicationId)`
- `0x18009c81a`: `hr = pServiceWrapper->GetDeviceIdInternal( g_szStrongAuthAppId, IDCRL_DEVICE_ID_FROMCACHE, 0 , &pDeviceId, nullptr , nullptr , &pDeviceIdentity)`
- `0x18009c96b`: `hr = pServiceWrapper->GetTokenUser(&client, accountSid)`
- `0x18009ca81`: `hr = HandleGetDeviceDAToken(pExecutionContext, &pDeviceDA)`
- `0x18009cb3c`: `hr = CAuthInfo::DecryptSystemContextString(pExecutionContext, pLoginProofToken, decryptedToken)`
- `0x18009cc6d`: `hr = pRequestWrapper->BuildRegisterApproverRequest( pRequest, pAppVersion, pApplicationSid, pChannelId, decryptedToken, static_cast<LPCWSTR>(pDeviceId), static_cast<LPCWSTR>(pDeviceDA), ngcPublicKey, ngcPublicKeySizeBytes)`
- `0x18009cdac`: `hr = pRequestWrapper->SaveApproverTotpKeyToCache(pRequest, static_cast<LPCWSTR>(keyIdentifier), isTotpEnabled)`
- `0x18009ce55`: `hr = pIdentityWrapper->GetOneTimeCredential(pDeviceIdentity, 0, PPCRL_OTC_REQUESTING_APPID, nullptr, nullptr, nullptr, url, deviceToken, nullptr)`
- `0x18009d01c`: `hr = pRequestWrapper->BuildManageApproverRequest( pRequest, localActionType, pAppVersion, pApplicationSid, pChannelId, static_cast<LPCWSTR>(escapedDeviceToken), accountPuid)`
- `0x18009d0ea`: `hr = ManageApproverRequest::DeleteTotpKeyFromCache(static_cast<LPCWSTR>(keyIdentifier))`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall HandleManageApprover(
        struct IServiceExecutionContext *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        int *a8)
{
  ManageApproverRequest *v11; // rbx
  __int64 v12; // r14
  __int64 v13; // r15
  __int64 v14; // rsi
  unsigned int v15; // r8d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 (__fastcall *v20)(__int64, const unsigned __int16 *, __int64); // rdi
  int v21; // eax
  int v22; // eax
  int v23; // r9d
  const char *v24; // rax
  int v25; // eax
  int v26; // eax
  const char *v27; // rcx
  unsigned int v28; // r8d
  struct IServiceExecutionContext **v29; // rcx
  __int64 v30; // rdi
  int v31; // eax
  struct IServiceExecutionContext *v32; // rdi
  int DeviceDAToken; // eax
  const char *v34; // rcx
  unsigned int v35; // r8d
  ManageApproverRequest *v36; // rax
  int v37; // eax
  int v38; // eax
  const char *v39; // rcx
  unsigned int v40; // r8d
  int v41; // edi
  int v42; // eax
  int v43; // eax
  const char *v44; // rcx
  unsigned int v45; // r8d
  ManageApproverRequest *v46; // rax
  int v47; // eax
  int v48; // eax
  const char *v49; // rcx
  unsigned int v50; // r8d
  int v51; // eax
  unsigned int v52; // edi
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  char *v56; // [rsp+20h] [rbp-E0h]
  char *v57; // [rsp+20h] [rbp-E0h]
  char *v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  struct IServiceExecutionContext *v61; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR TargetName; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  char v64; // [rsp+88h] [rbp-78h]
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  int v67; // [rsp+A0h] [rbp-60h] BYREF
  int v68; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  const BYTE *v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  _WORD *v72; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v74[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v77; // [rsp+F8h] [rbp-8h] BYREF
  int *v78; // [rsp+100h] [rbp+0h]
  ManageApproverRequest *v79; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v80; // [rsp+110h] [rbp+10h]
  _QWORD v81[3]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v82[3]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v83[3]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v84[3]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v85[5]; // [rsp+178h] [rbp+78h] BYREF
  __int16 v86; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v87; // [rsp+1A8h] [rbp+A8h]
  __int64 v88; // [rsp+1B0h] [rbp+B0h]
  __int64 v89; // [rsp+1B8h] [rbp+B8h]
  __int16 v90; // [rsp+1C0h] [rbp+C0h]
  __int64 v91; // [rsp+1C8h] [rbp+C8h]
  int v92; // [rsp+1D0h] [rbp+D0h]
  __int64 v93; // [rsp+1D8h] [rbp+D8h]
  int v94; // [rsp+1E0h] [rbp+E0h]
  __int128 v95; // [rsp+1E8h] [rbp+E8h]
  __int128 v96; // [rsp+1F8h] [rbp+F8h]
  __int64 v97; // [rsp+208h] [rbp+108h]

  v80 = a4;
  TargetName = a3;
  v61 = a1;
  v70 = (const BYTE *)a5;
  v78 = a8;
  if ( MSAClientPlatformExtension::DoesPlatformSupportMediumIL() )
    return 2147500033LL;
  v59 = 0;
  v69 = 0;
  v77 = 0;
  v11 = 0;
  v79 = 0;
  v65 = 0;
  memset(v83, 0, sizeof(v83));
  v73 = 0;
  v72 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v75);
  memset(v82, 0, sizeof(v82));
  v67 = 0;
  memset(v81, 0, sizeof(v81));
  v68 = 0;
  v85[0] = "HandleManageApprover";
  v85[1] = &v59;
  v85[2] = 0;
  v85[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleManageApprover",
    (const char *)0x2D43,
    0,
    (const unsigned __int16 *)v56);
  v12 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v13 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v14 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 64LL))(a1);
  v63 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)v61 + 48LL))(v61);
  v84[0] = 0;
  v84[2] = v63;
  v84[1] = 0;
  if ( !TargetName || !*TargetName || !a7 || !*a7 || !v78 )
  {
    v15 = 11606;
    goto LABEL_101;
  }
  *v78 = 0;
  if ( a2 )
  {
    if ( a2 - 1 > 1 )
    {
      v15 = 11615;
LABEL_101:
      v24 = "hr = E_INVALIDARG";
      v23 = -2147024809;
      goto LABEL_102;
    }
    if ( a6 )
    {
      v15 = 11630;
      goto LABEL_101;
    }
  }
  else if ( !a6 )
  {
    v15 = 11622;
    goto LABEL_101;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, &v69, 0);
  v59 = v16;
  if ( v16 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD *, const wchar_t *))(*(_QWORD *)v12 + 104LL))(
            v12,
            a7,
            0x800000,
            v83,
            L"{07f912dc-3518-4549-8286-7de7a2a443e6}");
    v59 = v17;
    if ( v17 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2D72u,
        v17,
        "hr = pServiceWrapper->HandleCreateContext(pUserName, CREATECONTEXT_SET_APP_IDENTITY, &hUserIdentity, c_sessionAp"
        "provalApplicationId)");
      goto LABEL_103;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v12 + 40LL))(v12, &v69, &v77);
    v59 = v18;
    if ( v18 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2D73u,
        v18,
        "hr = pServiceWrapper->GetLogonId(&client, logonId)");
      goto LABEL_103;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, __int64 *))(*(_QWORD *)v12 + 24LL))(
            v12,
            &v77,
            v83[0],
            &v65);
    v59 = v19;
    if ( v19 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2D74u,
        v19,
        "hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, pIdentity)");
      goto LABEL_103;
    }
    v20 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v12 + 128LL);
    CAutoRefPtr<CSingleIdentity>::Deinit(&v73);
    v21 = v20(v12, L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}", 16);
    v59 = v21;
    if ( v21 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2D7Du,
        v21,
        "hr = pServiceWrapper->GetDeviceIdInternal( g_szStrongAuthAppId, IDCRL_DEVICE_ID_FROMCACHE, 0 , &pDeviceId, nullp"
        "tr , nullptr , &pDeviceIdentity)");
      goto LABEL_103;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, const WCHAR *, __int64 *))(*(_QWORD *)v13 + 112LL))(
            v13,
            v65,
            L"PUID",
            &v66);
    v59 = v22;
    if ( v22 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2D80u,
        v22,
        "hr = pIdentityWrapper->GetCredProperty(pIdentity, PPCRL_CREDPROPERTY_PUIDSTR, accountPuid)");
      goto LABEL_103;
    }
    if ( !*(_DWORD *)(v66 - 16) )
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x2D83u,
        L"PUID is not set for the current identity.");
      v23 = -2147186543;
      v24 = "hr = PPCRL_E_CREDPROP_NOTFOUND";
      v15 = 11652;
LABEL_102:
      v59 = v23;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        v15,
        v23,
        v24);
      goto LABEL_103;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, __int64 *))(*(_QWORD *)v13 + 112LL))(
            v13,
            v65,
            L"CID",
            &v71);
    v59 = v25;
    if ( v25 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2D88u,
        v25,
        "hr = pIdentityWrapper->GetCredProperty(pIdentity, PPCRL_CREDPROPERTY_CID, accountCid)");
      goto LABEL_103;
    }
    if ( !*(_DWORD *)(v71 - 16) )
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x2D8Bu,
        L"CID is not set for the current identity.");
      v23 = -2147186543;
      v24 = "hr = PPCRL_E_CREDPROP_NOTFOUND";
      v15 = 11660;
      goto LABEL_102;
    }
    if ( !a2 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
      v26 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v12 + 72LL))(v12, &v69, &v60);
      v59 = v26;
      if ( v26 < 0 )
      {
        v27 = "hr = pServiceWrapper->GetTokenUser(&client, accountSid)";
        v28 = 11667;
LABEL_36:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleManageApprover",
          v28,
          v26,
          v27);
LABEL_37:
        v29 = (struct IServiceExecutionContext **)&v60;
LABEL_38:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v29);
        goto LABEL_103;
      }
      v30 = v63;
      v31 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64, __int64, _QWORD *, _QWORD *))(*(_QWORD *)v63 + 72LL))(
              v63,
              L"login.live.com",
              0,
              v71,
              v60,
              v82,
              v84);
      v59 = v31;
      if ( v31 >= 0 )
      {
        if ( v82[0] )
        {
          if ( *(_DWORD *)(v82[0] + 40LL) == 2 )
          {
            v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, int *))(*(_QWORD *)v30 + 112LL))(
                    v30,
                    *(_QWORD *)(v82[0] + 32LL),
                    v81,
                    &v67);
            v59 = v26;
            if ( v26 < 0 )
            {
              v27 = "hr = pNgcFunctions->NgcGetUserIdKeyPublicKey( spKeyInfo->pwszKeyName, &ngcPublicKey, &ngcPublicKeySizeBytes)";
              v28 = 11691;
              goto LABEL_36;
            }
          }
        }
      }
      else if ( v31 != -2146893782 )
      {
        LODWORD(v57) = v31;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x2DA2u,
          L"NgcFunctions::NgcEnumUserIdKeys.(hr = 0x%x)",
          v57);
        goto LABEL_37;
      }
      v59 = 0;
      memset(v74, 0, sizeof(v74));
      v32 = v61;
      DeviceDAToken = HandleGetDeviceDAToken(v61, v74);
      v59 = DeviceDAToken;
      if ( DeviceDAToken < 0 )
      {
        v34 = "hr = HandleGetDeviceDAToken(pExecutionContext, &pDeviceDA)";
        v35 = 11698;
LABEL_48:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleManageApprover",
          v35,
          DeviceDAToken,
          v34);
LABEL_49:
        Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(v74);
        goto LABEL_37;
      }
      v36 = (ManageApproverRequest *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
      v63 = (__int64)v36;
      if ( v36 )
        v11 = ManageApproverRequest::ManageApproverRequest(v36);
      else
        v11 = 0;
      v79 = v11;
      if ( !v11 )
      {
        v59 = -2147024882;
        goto LABEL_49;
      }
      DeviceDAToken = (*(__int64 (__fastcall **)(__int64, __int64, ManageApproverRequest *))(*(_QWORD *)v14 + 80LL))(
                        v14,
                        v65,
                        v11);
      v59 = DeviceDAToken;
      if ( DeviceDAToken < 0 )
      {
        v34 = "hr = pRequestWrapper->InitializeManageApproverRequest(pIdentity, pRequest)";
        v35 = 11702;
        goto LABEL_48;
      }
      DeviceDAToken = CAuthInfo::DecryptSystemContextString(v32, a6, &v75);
      v59 = DeviceDAToken;
      if ( DeviceDAToken < 0 )
      {
        v34 = "hr = CAuthInfo::DecryptSystemContextString(pExecutionContext, pLoginProofToken, decryptedToken)";
        v35 = 11703;
        goto LABEL_48;
      }
      v63 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, v65);
      v64 = 0;
      v37 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 16LL))(v13, &v63);
      v59 = v37;
      if ( v37 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleManageApprover",
          0x2DBBu,
          v37,
          "hr = pIdentityWrapper->Lock(&lock)");
LABEL_61:
        CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v63);
        goto LABEL_49;
      }
      v86 = 0;
      v87 = 0;
      v88 = 0;
      v89 = 0;
      v90 = 0;
      v91 = 0;
      v92 = 0;
      v93 = 0;
      v94 = 0;
      v95 = 0;
      v96 = 0;
      v97 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64, ManageApproverRequest *, LPCWSTR, const unsigned __int16 *, const BYTE *, __int64, _WORD *, unsigned __int16 *, _QWORD, int))(*(_QWORD *)v14 + 88LL))(
              v14,
              v11,
              TargetName,
              v80,
              v70,
              v75,
              v72,
              v74[0],
              v81[0],
              v67);
      v59 = v38;
      if ( v38 >= 0 )
      {
        v38 = (*(__int64 (__fastcall **)(__int64, __int16 *, ManageApproverRequest *))(*(_QWORD *)v14 + 32LL))(
                v14,
                &v86,
                v11);
        v59 = v38;
        if ( v38 >= 0 )
        {
          v38 = (*(__int64 (__fastcall **)(__int64, ManageApproverRequest *))(*(_QWORD *)v14 + 104LL))(v14, v11);
          v59 = v38;
          if ( v38 >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&v70,
              v72);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&TargetName,
              L"ManageApproverLID");
            v41 = SetExtendedPropertyInternal(&TargetName, &v70);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&TargetName);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v70);
            LODWORD(v58) = v41;
            TracePrintW(
              5u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              0x2DD0u,
              L"Non critical error SetExtendedProperty for Manage Approver returned hr = 0x%x",
              v58);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&v61,
              L"MicrosoftAccount:(TOTPSharedKey):UserPuid=");
            ATL::CSimpleStringT<unsigned short,0>::Append(&v61, &v66);
            v42 = (*(__int64 (__fastcall **)(__int64, ManageApproverRequest *, struct IServiceExecutionContext *, int *))(*(_QWORD *)v14 + 112LL))(
                    v14,
                    v11,
                    v61,
                    &v68);
            v59 = v42;
            if ( v42 >= 0 )
              *v78 = v68;
            else
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                "HandleManageApprover",
                0x2DD6u,
                v42,
                "hr = pRequestWrapper->SaveApproverTotpKeyToCache(pRequest, static_cast<LPCWSTR>(keyIdentifier), isTotpEnabled)");
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
            goto LABEL_65;
          }
          v39 = "hr = pRequestWrapper->GetManageApproverRequestServerError(pRequest)";
          v40 = 11722;
        }
        else
        {
          v39 = "hr = pRequestWrapper->SendRequest(&transport, pRequest)";
          v40 = 11721;
        }
      }
      else
      {
        v39 = "hr = pRequestWrapper->BuildRegisterApproverRequest( pRequest, pAppVersion, pApplicationSid, pChannelId, de"
              "cryptedToken, static_cast<LPCWSTR>(pDeviceId), static_cast<LPCWSTR>(pDeviceDA), ngcPublicKey, ngcPublicKeySizeBytes)";
        v40 = 11719;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        v40,
        v38,
        v39);
LABEL_65:
      CTransport::~CTransport((CTransport *)&v86);
      goto LABEL_61;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
    v43 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, _QWORD, _QWORD, _QWORD, struct IServiceExecutionContext **, __int64 *, _QWORD))(*(_QWORD *)v13 + 96LL))(
            v13,
            v73,
            0,
            L"Default",
            0,
            0,
            0,
            &v61,
            &v60,
            0);
    v59 = v43;
    if ( v43 < 0 )
    {
      v44 = "hr = pIdentityWrapper->GetOneTimeCredential(pDeviceIdentity, 0, PPCRL_OTC_REQUESTING_APPID, nullptr, nullptr"
            ", nullptr, url, deviceToken, nullptr)";
      v45 = 11742;
LABEL_76:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        v45,
        v43,
        v44);
LABEL_77:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
      v29 = &v61;
      goto LABEL_38;
    }
    SanitizeAndEscapeXML(v60, &v76);
    v46 = (ManageApproverRequest *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    v63 = (__int64)v46;
    if ( v46 )
      v11 = ManageApproverRequest::ManageApproverRequest(v46);
    else
      v11 = 0;
    v79 = v11;
    if ( !v11 )
    {
      v59 = -2147024882;
      goto LABEL_77;
    }
    v43 = (*(__int64 (__fastcall **)(__int64, __int64, ManageApproverRequest *))(*(_QWORD *)v14 + 80LL))(v14, v65, v11);
    v59 = v43;
    if ( v43 < 0 )
    {
      v44 = "hr = pRequestWrapper->InitializeManageApproverRequest(pIdentity, pRequest)";
      v45 = 11748;
      goto LABEL_76;
    }
    v63 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, v65);
    v64 = 0;
    v47 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 16LL))(v13, &v63);
    v59 = v47;
    if ( v47 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleManageApprover",
        0x2DE8u,
        v47,
        "hr = pIdentityWrapper->Lock(&lock)");
LABEL_87:
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v63);
      goto LABEL_77;
    }
    v86 = 0;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v48 = (*(__int64 (__fastcall **)(__int64, ManageApproverRequest *, _QWORD, LPCWSTR, const unsigned __int16 *, const BYTE *, __int64, __int64))(*(_QWORD *)v14 + 96LL))(
            v14,
            v11,
            a2,
            TargetName,
            v80,
            v70,
            v76,
            v66);
    v59 = v48;
    if ( v48 >= 0 )
    {
      v48 = (*(__int64 (__fastcall **)(__int64, __int16 *, ManageApproverRequest *))(*(_QWORD *)v14 + 32LL))(
              v14,
              &v86,
              v11);
      v59 = v48;
      if ( v48 >= 0 )
      {
        v48 = (*(__int64 (__fastcall **)(__int64, ManageApproverRequest *))(*(_QWORD *)v14 + 104LL))(v14, v11);
        v59 = v48;
        if ( v48 >= 0 )
        {
          if ( a2 == 2 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&TargetName,
              L"MicrosoftAccount:(TOTPSharedKey):UserPuid=");
            ATL::CSimpleStringT<unsigned short,0>::Append(&TargetName, &v66);
            v51 = ManageApproverRequest::DeleteTotpKeyFromCache(TargetName);
            v59 = v51;
            if ( v51 < 0 )
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                "HandleManageApprover",
                0x2DFCu,
                v51,
                "hr = ManageApproverRequest::DeleteTotpKeyFromCache(static_cast<LPCWSTR>(keyIdentifier))");
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&TargetName);
          }
          goto LABEL_91;
        }
        v49 = "hr = pRequestWrapper->GetManageApproverRequestServerError(pRequest)";
        v50 = 11765;
      }
      else
      {
        v49 = "hr = pRequestWrapper->SendRequest(&transport, pRequest)";
        v50 = 11764;
      }
    }
    else
    {
      v49 = "hr = pRequestWrapper->BuildManageApproverRequest( pRequest, localActionType, pAppVersion, pApplicationSid, p"
            "ChannelId, static_cast<LPCWSTR>(escapedDeviceToken), accountPuid)";
      v50 = 11762;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleManageApprover",
      v50,
      v48,
      v49);
LABEL_91:
    CTransport::~CTransport((CTransport *)&v86);
    goto LABEL_87;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleManageApprover",
    0x2D71u,
    v16,
    "hr = pServiceWrapper->Impersonate(&client)");
LABEL_103:
  v52 = v59;
  if ( v59 < 0 )
  {
    if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
    {
      LODWORD(v60) = v59;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v53,
        (__int64)byte_1801973C9,
        v54,
        v55,
        (__int64)&v60);
    }
    v52 = v59;
  }
  Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(v84);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v85);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v81);
  Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v82);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v75);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  CPassportStringW::~CPassportStringW((CPassportStringW *)&v72);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v73);
  Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(v83);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v65);
  if ( v11 )
    (**(void (__fastcall ***)(ManageApproverRequest *, __int64))v11)(v11, 1);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v69);
  return v52;
}

```

## disassembly

```asm
0x18009c4d0  push    rbp
0x18009c4d2  push    rbx
0x18009c4d3  push    rsi
0x18009c4d4  push    rdi
0x18009c4d5  push    r12
0x18009c4d7  push    r13
0x18009c4d9  push    r14
0x18009c4db  push    r15
0x18009c4dd  lea     rbp, [rsp-128h]
0x18009c4e5  sub     rsp, 228h
0x18009c4ec  mov     rax, cs:__security_cookie
0x18009c4f3  xor     rax, rsp
0x18009c4f6  mov     [rbp+160h+var_50], rax
0x18009c4fd  mov     [rbp+160h+var_150], r9
0x18009c501  mov     [rsp+260h+TargetName], r8
0x18009c506  mov     r13d, edx
0x18009c509  mov     rsi, rcx
0x18009c50c  mov     [rsp+260h+var_1F0], rcx
0x18009c511  mov     rax, [rbp+160h+arg_20]
0x18009c518  mov     [rbp+160h+var_1B0], rax
0x18009c51c  mov     r12, [rbp+160h+arg_28]
0x18009c523  mov     rdi, [rbp+160h+arg_30]
0x18009c52a  mov     rcx, [rbp+160h+arg_38]
0x18009c531  mov     [rbp+160h+var_160], rcx
0x18009c535  call    ?DoesPlatformSupportMediumIL@MSAClientPlatformExtension@@SA_NXZ; MSAClientPlatformExtension::DoesPlatformSupportMediumIL(void)
0x18009c53a  cmp     al, 1
0x18009c53c  jnz     short loc_18009C548
0x18009c53e  mov     eax, 80004001h
0x18009c543  jmp     loc_18009D23D
0x18009c548  xor     r14d, r14d
0x18009c54b  mov     [rsp+260h+var_200], r14d
0x18009c550  mov     [rbp+160h+var_1B8], r14
0x18009c554  mov     [rbp+160h+var_168], r14
0x18009c558  mov     ebx, r14d
0x18009c55b  mov     [rbp+160h+var_158], rbx
0x18009c55f  mov     [rbp+160h+var_1D0], r14
0x18009c563  mov     [rbp+160h+var_118], r14
0x18009c567  mov     [rbp+160h+var_108], r14
0x18009c56b  mov     [rbp+160h+var_110], r14
0x18009c56f  mov     [rbp+160h+var_198], r14
0x18009c573  mov     [rbp+160h+var_1A0], r14
0x18009c577  lea     rcx, [rbp+160h+var_170]
0x18009c57b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c580  nop
0x18009c581  lea     rcx, [rbp+160h+var_1A8]
0x18009c585  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c58a  nop
0x18009c58b  lea     rcx, [rbp+160h+var_1C8]
0x18009c58f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c594  nop
0x18009c595  lea     rcx, [rbp+160h+var_178]
0x18009c599  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c59e  nop
0x18009c59f  mov     [rbp+160h+var_130], r14
0x18009c5a3  mov     [rbp+160h+var_120], r14
0x18009c5a7  mov     [rbp+160h+var_128], r14
0x18009c5ab  mov     [rbp+160h+var_1C0], r14d
0x18009c5af  mov     [rbp+160h+var_148], r14
0x18009c5b3  mov     [rbp+160h+var_138], r14
0x18009c5b7  mov     [rbp+160h+var_140], r14
0x18009c5bb  mov     [rbp+160h+var_1BC], r14d
0x18009c5bf  lea     rcx, aHandlemanageap; "HandleManageApprover"
0x18009c5c6  mov     [rbp+160h+var_E8], rcx
0x18009c5ca  lea     rax, [rsp+260h+var_200]
0x18009c5cf  mov     [rbp+160h+var_E0], rax
0x18009c5d6  mov     [rbp+160h+var_D8], r14
0x18009c5dd  mov     [rbp+160h+var_D0], r14
0x18009c5e4  xor     r9d, r9d; unsigned int
0x18009c5e7  mov     r8d, 2D43h; char *
0x18009c5ed  mov     rdx, rcx; char *
0x18009c5f0  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009c5f7  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18009c5fc  nop
0x18009c5fd  mov     rax, [rsi]
0x18009c600  mov     rcx, rsi
0x18009c603  mov     rax, [rax+50h]
0x18009c607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c60c  mov     r14, rax
0x18009c60f  mov     rcx, [rsi]
0x18009c612  mov     rax, [rcx+38h]
0x18009c616  mov     rcx, rsi
0x18009c619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c61e  mov     r15, rax
0x18009c621  mov     rcx, [rsi]
0x18009c624  mov     rax, [rcx+40h]
0x18009c628  mov     rcx, rsi
0x18009c62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c630  mov     rsi, rax
0x18009c633  mov     rdx, [rsp+260h+var_1F0]
0x18009c638  mov     rcx, [rdx]
0x18009c63b  mov     rax, [rcx+30h]
0x18009c63f  mov     rcx, rdx
0x18009c642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c647  mov     [rbp+160h+var_1E0], rax
0x18009c64b  xor     ecx, ecx
0x18009c64d  mov     [rbp+160h+var_100], rcx
0x18009c651  mov     [rbp+160h+var_F0], rax
0x18009c655  mov     [rbp+160h+var_F8], rcx
0x18009c659  mov     rax, [rsp+260h+TargetName]
0x18009c65e  test    rax, rax
0x18009c661  jz      loc_18009D122
0x18009c667  cmp     [rax], cx
0x18009c66a  jz      loc_18009D122
0x18009c670  test    rdi, rdi
0x18009c673  jz      loc_18009D122
0x18009c679  cmp     [rdi], cx
0x18009c67c  jz      loc_18009D122
0x18009c682  mov     rax, [rbp+160h+var_160]
0x18009c686  test    rax, rax
0x18009c689  jz      loc_18009D122
0x18009c68f  mov     [rax], ecx
0x18009c691  test    r13d, r13d
0x18009c694  jz      short loc_18009C6BA
0x18009c696  lea     eax, [r13-1]
0x18009c69a  cmp     eax, 1
0x18009c69d  jbe     short loc_18009C6AA
0x18009c69f  mov     r8d, 2D5Fh
0x18009c6a5  jmp     loc_18009D128
0x18009c6aa  test    r12, r12
0x18009c6ad  jz      short loc_18009C6CA
0x18009c6af  mov     r8d, 2D6Eh
0x18009c6b5  jmp     loc_18009D128
0x18009c6ba  test    r12, r12
0x18009c6bd  jnz     short loc_18009C6CA
0x18009c6bf  mov     r8d, 2D66h
0x18009c6c5  jmp     loc_18009D128
0x18009c6ca  mov     rax, [r14]
0x18009c6cd  xor     r8d, r8d
0x18009c6d0  lea     rdx, [rbp+160h+var_1B8]
0x18009c6d4  mov     rcx, r14
0x18009c6d7  mov     rax, [rax+20h]
0x18009c6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c6e0  mov     [rsp+260h+var_200], eax
0x18009c6e4  test    eax, eax
0x18009c6e6  jns     short loc_18009C702
0x18009c6e8  lea     rcx, aHrPservicewrap_25; "hr = pServiceWrapper->Impersonate(&clie"...
0x18009c6ef  mov     [rsp+260h+var_240], rcx
0x18009c6f4  mov     r9d, eax
0x18009c6f7  mov     r8d, 2D71h
0x18009c6fd  jmp     loc_18009D13F
0x18009c702  mov     rax, [r14]
0x18009c705  lea     rcx, a07f912dc351845; "{07f912dc-3518-4549-8286-7de7a2a443e6}"
0x18009c70c  mov     [rsp+260h+var_240], rcx
0x18009c711  lea     r9, [rbp+160h+var_118]
0x18009c715  mov     r8d, 800000h
0x18009c71b  mov     rdx, rdi
0x18009c71e  mov     rcx, r14
0x18009c721  mov     rax, [rax+68h]
0x18009c725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c72a  mov     [rsp+260h+var_200], eax
0x18009c72e  test    eax, eax
0x18009c730  jns     short loc_18009C74C
0x18009c732  lea     rcx, aHrPservicewrap_14; "hr = pServiceWrapper->HandleCreateConte"...
0x18009c739  mov     [rsp+260h+var_240], rcx
0x18009c73e  mov     r9d, eax
0x18009c741  mov     r8d, 2D72h
0x18009c747  jmp     loc_18009D13F
0x18009c74c  mov     rax, [r14]
0x18009c74f  lea     r8, [rbp+160h+var_168]
0x18009c753  lea     rdx, [rbp+160h+var_1B8]
0x18009c757  mov     rcx, r14
0x18009c75a  mov     rax, [rax+28h]
0x18009c75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c763  mov     [rsp+260h+var_200], eax
0x18009c767  test    eax, eax
0x18009c769  jns     short loc_18009C785
0x18009c76b  lea     rcx, aHrPservicewrap_16; "hr = pServiceWrapper->GetLogonId(&clien"...
0x18009c772  mov     [rsp+260h+var_240], rcx
0x18009c777  mov     r9d, eax
0x18009c77a  mov     r8d, 2D73h
0x18009c780  jmp     loc_18009D13F
0x18009c785  mov     rax, [r14]
0x18009c788  lea     r9, [rbp+160h+var_1D0]
0x18009c78c  mov     r8, [rbp+160h+var_118]
0x18009c790  lea     rdx, [rbp+160h+var_168]
0x18009c794  mov     rcx, r14
0x18009c797  mov     rax, [rax+18h]
0x18009c79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c7a0  mov     [rsp+260h+var_200], eax
0x18009c7a4  test    eax, eax
0x18009c7a6  jns     short loc_18009C7C2
0x18009c7a8  lea     rcx, aHrPservicewrap; "hr = pServiceWrapper->GetIdentityHandle"...
0x18009c7af  mov     [rsp+260h+var_240], rcx
0x18009c7b4  mov     r9d, eax
0x18009c7b7  mov     r8d, 2D74h
0x18009c7bd  jmp     loc_18009D13F
0x18009c7c2  mov     rax, [r14]
0x18009c7c5  mov     rdi, [rax+80h]
0x18009c7cc  lea     rcx, [rbp+160h+var_198]
0x18009c7d0  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x18009c7d5  lea     rax, [rbp+160h+var_198]
0x18009c7d9  mov     [rsp+260h+var_228], rax
0x18009c7de  mov     [rsp+260h+var_230], 0
0x18009c7e7  mov     [rsp+260h+var_238], 0
0x18009c7f0  lea     rax, [rbp+160h+var_1A0]
0x18009c7f4  mov     [rsp+260h+var_240], rax
0x18009c7f9  xor     r9d, r9d
0x18009c7fc  lea     r8d, [r9+10h]
0x18009c800  lea     rdx, aAfda72bf340941; "{AFDA72BF-3409-413a-B54E-2AB8D66A7826}"
0x18009c807  mov     rcx, r14
0x18009c80a  mov     rax, rdi
0x18009c80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c812  mov     [rsp+260h+var_200], eax
0x18009c816  test    eax, eax
0x18009c818  jns     short loc_18009C834
0x18009c81a  lea     rcx, aHrPservicewrap_11; "hr = pServiceWrapper->GetDeviceIdIntern"...
0x18009c821  mov     [rsp+260h+var_240], rcx
0x18009c826  mov     r9d, eax
0x18009c829  mov     r8d, 2D7Dh
0x18009c82f  jmp     loc_18009D13F
0x18009c834  mov     rax, [r15]
0x18009c837  lea     r9, [rbp+160h+var_1C8]
0x18009c83b  lea     r8, aPuid; "PUID"
0x18009c842  mov     rdx, [rbp+160h+var_1D0]
0x18009c846  mov     rcx, r15
0x18009c849  mov     rax, [rax+70h]
0x18009c84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c852  mov     [rsp+260h+var_200], eax
0x18009c856  test    eax, eax
0x18009c858  jns     short loc_18009C874
0x18009c85a  lea     rcx, aHrPidentitywra_8; "hr = pIdentityWrapper->GetCredProperty("...
0x18009c861  mov     [rsp+260h+var_240], rcx
0x18009c866  mov     r9d, eax
0x18009c869  mov     r8d, 2D80h
0x18009c86f  jmp     loc_18009D13F
0x18009c874  mov     rax, [rbp+160h+var_1C8]
0x18009c878  cmp     dword ptr [rax-10h], 0
0x18009c87c  jnz     short loc_18009C8B4
0x18009c87e  lea     r9, aPuidIsNotSetFo; "PUID is not set for the current identit"...
0x18009c885  mov     r8d, 2D83h; unsigned int
0x18009c88b  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009c892  mov     ecx, 2; unsigned __int8
0x18009c897  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009c89c  mov     r9d, 80048891h
0x18009c8a2  lea     rax, aHrPpcrlECredpr; "hr = PPCRL_E_CREDPROP_NOTFOUND"
0x18009c8a9  mov     r8d, 2D84h
0x18009c8af  jmp     loc_18009D135
0x18009c8b4  mov     rax, [r15]
0x18009c8b7  lea     r9, [rbp+160h+var_1A8]
0x18009c8bb  lea     r8, aCid; "CID"
0x18009c8c2  mov     rdx, [rbp+160h+var_1D0]
0x18009c8c6  mov     rcx, r15
0x18009c8c9  mov     rax, [rax+70h]
0x18009c8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8d2  mov     [rsp+260h+var_200], eax
0x18009c8d6  test    eax, eax
0x18009c8d8  jns     short loc_18009C8F4
0x18009c8da  lea     rcx, aHrPidentitywra_2; "hr = pIdentityWrapper->GetCredProperty("...
0x18009c8e1  mov     [rsp+260h+var_240], rcx
0x18009c8e6  mov     r9d, eax
0x18009c8e9  mov     r8d, 2D88h
0x18009c8ef  jmp     loc_18009D13F
0x18009c8f4  mov     rax, [rbp+160h+var_1A8]
0x18009c8f8  cmp     dword ptr [rax-10h], 0
0x18009c8fc  jnz     short loc_18009C934
0x18009c8fe  lea     r9, aCidIsNotSetFor_0; "CID is not set for the current identity"...
0x18009c905  mov     r8d, 2D8Bh; unsigned int
0x18009c90b  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009c912  mov     ecx, 2; unsigned __int8
0x18009c917  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009c91c  mov     r9d, 80048891h
0x18009c922  lea     rax, aHrPpcrlECredpr; "hr = PPCRL_E_CREDPROP_NOTFOUND"
0x18009c929  mov     r8d, 2D8Ch
0x18009c92f  jmp     loc_18009D135
0x18009c934  test    r13d, r13d
0x18009c937  jnz     loc_18009CDEF
0x18009c93d  lea     rcx, [rsp+260h+var_1F8]
0x18009c942  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c947  nop
0x18009c948  mov     rax, [r14]
0x18009c94b  lea     r8, [rsp+260h+var_1F8]
0x18009c950  lea     rdx, [rbp+160h+var_1B8]
0x18009c954  mov     rcx, r14
0x18009c957  mov     rax, [rax+48h]
0x18009c95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c960  mov     [rsp+260h+var_200], eax
0x18009c964  xor     r14d, r14d
0x18009c967  test    eax, eax
0x18009c969  jns     short loc_18009C9A3
0x18009c96b  lea     rcx, aHrPservicewrap_12; "hr = pServiceWrapper->GetTokenUser(&cli"...
0x18009c972  mov     r8d, 2D93h; unsigned int
0x18009c978  mov     r9d, eax; int
0x18009c97b  mov     [rsp+260h+var_240], rcx; char *
0x18009c980  lea     rdx, aHandlemanageap; "HandleManageApprover"
0x18009c987  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009c98e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18009c993  nop
0x18009c994  lea     rcx, [rsp+260h+var_1F8]
0x18009c999  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009c99e  jmp     loc_18009D152
0x18009c9a3  mov     rdi, [rbp+160h+var_1E0]
0x18009c9a7  mov     rax, [rdi]
0x18009c9aa  lea     rcx, [rbp+160h+var_100]
0x18009c9ae  mov     [rsp+260h+var_230], rcx
0x18009c9b3  lea     rcx, [rbp+160h+var_130]
0x18009c9b7  mov     [rsp+260h+var_238], rcx
0x18009c9bc  mov     rcx, [rsp+260h+var_1F8]
0x18009c9c1  mov     [rsp+260h+var_240], rcx
0x18009c9c6  mov     r9, [rbp+160h+var_1A8]
0x18009c9ca  xor     r8d, r8d
  ... truncated ...
```
