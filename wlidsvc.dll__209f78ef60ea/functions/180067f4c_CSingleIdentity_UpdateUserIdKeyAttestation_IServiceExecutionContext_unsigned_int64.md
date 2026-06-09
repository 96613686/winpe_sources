# CSingleIdentity::UpdateUserIdKeyAttestation(IServiceExecutionContext *,unsigned __int64)

- ea: `0x180067f4c`
- end: `0x180068b99`
- name: `?UpdateUserIdKeyAttestation@CSingleIdentity@@QEAAJPEAVIServiceExecutionContext@@_K@Z`
- size: `3149`
- prototype: `__int64 __fastcall(CSingleIdentity *__hidden this, struct IServiceExecutionContext *, unsigned __int64)`
- caller_count: `1`
- callee_count: `46`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180043e20`

## callees

- `0x180002200`
- `0x18000a354`
- `0x18000bff0`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x18000fd48`
- `0x1800151c4`
- `0x180015430`
- `0x180015fdc`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001f968`
- `0x180020b10`
- `0x180026398`
- `0x18002df9c`
- `0x18002eae8`
- `0x18002ed50`
- `0x18003b1e0`
- `0x18003c814`
- `0x180042214`
- `0x180043344`
- `0x180046aa4`
- `0x180050740`
- `0x180054fb4`
- `0x18005538c`
- `0x180055edc`
- `0x180067f4c`
- `0x18006a630`
- `0x18007ecc8`
- `0x1800841b0`
- `0x180086a68`
- `0x18008b9d4`
- `0x1800a3b60`
- `0x1800a3fec`
- `0x1800a6e7c`
- `0x1800a6ee8`
- `0x1800a716c`
- `0x1800aeab8`
- `0x1800d9080`
- `0x1800d9d20`
- `0x1800dbb7c`
- `0x1800f96e4`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800681ba`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800681ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068352`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068331`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068352`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800682ec`

## string_xrefs

- `0x1800680bf`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068185`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068255`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800686e7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800687cc`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068a39`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068465`: `hr = client.ImpersonateClient()`
- `0x1800682ac`: `login.live.com`
- `0x1800681ee`: `hr = pSystemStore->GetCurrentUserSidString(&spUserSid)`
- `0x18006808b`: `CSingleIdentity::UpdateUserIdKeyAttestation`
- `0x18006817e`: `CSingleIdentity::UpdateUserIdKeyAttestation`
- `0x1800686e0`: `CSingleIdentity::UpdateUserIdKeyAttestation`
- `0x1800687c5`: `CSingleIdentity::UpdateUserIdKeyAttestation`
- `0x1800682c7`: `hr = pNgcFunctions->NgcEnumUserIdKeys( PPCRL_MSA_IDP_DOMAIN, nullptr, static_cast<PCWSTR>(accountCid), static_cast<PCWSTR>(spUserSid), &spKeyInfo, &spEnumState)`
- `0x1800684ce`: `hr = pServiceWrapper->HandleCreateContext( this->GetIdentityName(), CREATECONTEXT_SET_APP_IDENTITY, &hUserIdentity, c_updateUserIdKeyAttestationApplicationId)`
- `0x180068538`: `hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, pUserIdentity)`
- `0x18006859a`: `hr = pUserIdentity->GetServiceTicket( pExecutionContext, PPCRL_LOGIN_PROOF_TOKEN_URI, PPCRL_LOGIN_PROOF_TOKEN_POLICY_KEYUPDATE, throttleScenario, loginProofToken)`
- `0x180068681`: `hr = pRequest->ComputeServerKeyId( ngcPublicKey, ngcPublicKeySizeBytes, serverKeyId)`
- `0x1800685c6`: `loginProofToken.GetLength() != 0`
- `0x1800687b0`: `hr = pRequest->BuildRequest( loginProofToken, "Update", nullptr, 0, serverKeyId, spAttestationStatement, attestationStatementSizeBytes, spAikCertChain, aikCertChainSizeBytes)`
- `0x180068796`: `Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall CSingleIdentity::UpdateUserIdKeyAttestation(
        CSingleIdentity *this,
        struct IServiceExecutionContext *a2,
        __int64 a3)
{
  UserIdKeyRegistrationRequest *v6; // rbx
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // r15
  int LogonId; // eax
  unsigned int v12; // r8d
  unsigned int v13; // eax
  int v14; // ecx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64, _QWORD *, const wchar_t *); // rdi
  _QWORD *v20; // rax
  int v21; // edi
  unsigned __int16 *v22; // rdi
  UserIdKeyRegistrationRequest *v23; // rax
  struct CSingleIdentity *v24; // rdx
  int v25; // eax
  int v26; // eax
  const char *v27; // rcx
  unsigned int v28; // r8d
  const unsigned __int16 **ServerBuildInfo; // rax
  int v30; // edi
  const unsigned __int16 **v31; // rax
  int v32; // edi
  const unsigned __int16 **v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // edi
  struct CSingleIdentity *v37; // rcx
  int v38; // eax
  char v39; // di
  unsigned int v40; // edi
  int v42; // edx
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  char *v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  char *v48; // [rsp+20h] [rbp-E0h]
  char *v49; // [rsp+20h] [rbp-E0h]
  char *v50; // [rsp+28h] [rbp-D8h]
  int v51; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+54h] [rbp-ACh]
  unsigned int v53; // [rsp+58h] [rbp-A8h] BYREF
  struct CSingleIdentity *v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v56; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int8 v57[8]; // [rsp+70h] [rbp-90h] BYREF
  int v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v60; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  __int64 v62; // [rsp+98h] [rbp-68h] BYREF
  char *v63; // [rsp+A0h] [rbp-60h] BYREF
  char v64; // [rsp+A8h] [rbp-58h]
  __int64 v65; // [rsp+B0h] [rbp-50h] BYREF
  char *v66; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v68; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v69; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v70; // [rsp+D8h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v71; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v72; // [rsp+E8h] [rbp-18h] BYREF
  struct _LUID v73; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v74[3]; // [rsp+F8h] [rbp-8h] BYREF
  UserIdKeyRegistrationRequest *v75; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v76; // [rsp+118h] [rbp+18h] BYREF
  const unsigned __int16 *v77; // [rsp+120h] [rbp+20h] BYREF
  __int64 v78; // [rsp+128h] [rbp+28h] BYREF
  __int64 v79; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v80[3]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v81[3]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v82[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int8 *v83[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int8 *v84[3]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v85[3]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v86[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v87; // [rsp+1E8h] [rbp+E8h] BYREF
  __int16 v88; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v89; // [rsp+1F8h] [rbp+F8h]
  __int64 v90; // [rsp+200h] [rbp+100h]
  __int64 v91; // [rsp+208h] [rbp+108h]
  __int16 v92; // [rsp+210h] [rbp+110h]
  __int64 v93; // [rsp+218h] [rbp+118h]
  int v94; // [rsp+220h] [rbp+120h]
  __int64 v95; // [rsp+228h] [rbp+128h]
  int v96; // [rsp+230h] [rbp+130h]
  __int128 v97; // [rsp+238h] [rbp+138h]
  __int128 v98; // [rsp+248h] [rbp+148h]
  __int64 v99; // [rsp+258h] [rbp+158h]

  v52 = 0;
  v51 = 0;
  v6 = 0;
  v75 = 0;
  memset(v84, 0, sizeof(v84));
  memset(v83, 0, sizeof(v83));
  v56 = 0;
  v55 = 0;
  memset(v82, 0, sizeof(v82));
  v60 = 0;
  memset(v81, 0, sizeof(v81));
  memset(v74, 0, sizeof(v74));
  v53 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v70);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v69);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
  v59 = 0;
  ATL::CTime::GetTickCount(v57);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v65,
    L"NGC_TpmBinding");
  memset(v80, 0, sizeof(v80));
  v54 = 0;
  v73 = 0;
  v62 = 0;
  if ( dword_1801C703C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 8LL) )
  {
    Init_thread_header(&dword_1801C703C);
    if ( dword_1801C703C == -1 )
    {
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,__int64,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<__int64>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,__int64,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<__int64>>(
        v43,
        v42,
        v44,
        v45,
        (_DWORD)FLOAT_2_25);
      atexit(CSingleIdentity::UpdateUserIdKeyAttestation_::_2_::_dynamic_atexit_destructor_for__ngcAttestationAttemptMap__);
      Init_thread_footer(&dword_1801C703C);
    }
  }
  v86[0] = "CSingleIdentity::UpdateUserIdKeyAttestation";
  v86[1] = &v51;
  v86[2] = 0;
  v86[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CSingleIdentity::UpdateUserIdKeyAttestation",
    (const char *)0xA94,
    0,
    (const unsigned __int16 *)v46);
  v7 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a2 + 48LL))(a2);
  v85[0] = 0;
  v85[2] = v7;
  v85[1] = 0;
  v8 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
  v72 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2);
  v10 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a2 + 80LL))(a2);
  LOBYTE(v47) = 0;
  LogonId = ThrottleManager::CheckCurrentLimit((char *)g_pPPCRL + 1936, this, 14, v65, v47);
  v51 = LogonId;
  if ( LogonId < 0 )
  {
    v48 = "hr = g_pPPCRL->GetThrottleManager()->CheckCurrentLimit(this, EPPCRLRequestTypeUserIdKeyRegistration, throttleScenario, false)";
    v12 = 2721;
LABEL_4:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CSingleIdentity::UpdateUserIdKeyAttestation",
      v12,
      LogonId,
      v48);
    goto LABEL_78;
  }
  (*(void (__fastcall **)(CSingleIdentity *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this + 64LL))(
    this,
    L"NgcAttestationKeyType",
    &v67);
  if ( *(int *)(v67 - 16) <= 0 || (v13 = _o__wtoi(v67), v13 > 6) || (v14 = 86, !_bittest(&v14, v13)) )
  {
    LogonId = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 32LL))(v9, v81);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = pSystemStore->GetCurrentUserSidString(&spUserSid)";
      v12 = 2738;
      goto LABEL_4;
    }
    LogonId = (*(__int64 (__fastcall **)(CSingleIdentity *, const wchar_t *, __int64 *))(*(_QWORD *)this + 64LL))(
                this,
                L"CID",
                &v68);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = this->GetCredProperty(PPCRL_CREDPROPERTY_CID, accountCid)";
      v12 = 2739;
      goto LABEL_4;
    }
    if ( !*(_DWORD *)(v68 - 16) )
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        0xAB6u,
        L"CID is not set for the current identity.");
      v51 = -2147186543;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::UpdateUserIdKeyAttestation",
        0xAB7u,
        -2147186543,
        "hr = PPCRL_E_CREDPROP_NOTFOUND");
      goto LABEL_78;
    }
    LogonId = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v7 + 72LL))(
                v7,
                L"login.live.com",
                0);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = pNgcFunctions->NgcEnumUserIdKeys( PPCRL_MSA_IDP_DOMAIN, nullptr, static_cast<PCWSTR>(accountCid), stati"
            "c_cast<PCWSTR>(spUserSid), &spKeyInfo, &spEnumState)";
      v12 = 2753;
      goto LABEL_4;
    }
    v71 = &CSingleIdentity::_criticalSection;
    EnterCriticalSection(&CSingleIdentity::_criticalSection);
    if ( (unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,__int64,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<__int64>>::Lookup(
                            v15,
                            *(_QWORD *)(v74[0] + 32LL),
                            &v59) == 1 )
    {
      v16 = *((int *)CClientConfigDataCacheManager::theConfigDataManager() + 68);
      v17 = *(_QWORD *)v57 - v16;
      *(_QWORD *)v57 = v17;
      if ( v17 - v59 < 120 )
      {
        LeaveCriticalSection(&CSingleIdentity::_criticalSection);
        goto LABEL_78;
      }
    }
    else
    {
      v17 = *(_QWORD *)v57;
    }
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,__int64,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<__int64>>::SetAt(
      v16,
      *(_QWORD *)(v74[0] + 32LL),
      v17);
    LeaveCriticalSection(&CSingleIdentity::_criticalSection);
    v51 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *))(*(_QWORD *)v7 + 40LL))(
            v7,
            *(_QWORD *)(v74[0] + 32LL),
            a3,
            v84,
            &v56,
            v83,
            &v55,
            &v53);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v69,
      L"%d",
      v53);
    CSingleIdentity::SetCredProperty(this, L"NgcAttestationKeyType", v69);
    if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
    {
      v58 = v51;
      LODWORD(v59) = v53;
      v61 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1801C2080,
        (unsigned __int8 *)&dword_180199CD4,
        0,
        v18,
        (__int64)&v61,
        (__int64)&v59,
        (__int64)&v58);
    }
    if ( !v56 || !v55 )
    {
      LODWORD(v50) = v53;
      LODWORD(v49) = v51;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        0xAEBu,
        L"NgcFunctions::NgcGetKeyAttestationForUserIdKey.(hr = 0x%x). Key Type: %d",
        v49,
        v50);
      goto LABEL_78;
    }
    LogonId = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v62, 0);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = client.ImpersonateClient()";
      v12 = 2800;
      goto LABEL_4;
    }
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *, const wchar_t *))(*(_QWORD *)v10 + 104LL);
    v20 = (_QWORD *)(*(__int64 (__fastcall **)(CSingleIdentity *, __int64 *))(*(_QWORD *)this + 32LL))(this, &v61);
    v21 = v19(v10, *v20, 0x800000, v80, L"{d1f1d8be-c318-497e-a721-00e06fe56916}");
    v51 = v21;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
    if ( v21 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::UpdateUserIdKeyAttestation",
        0xAF5u,
        v21,
        "hr = pServiceWrapper->HandleCreateContext( this->GetIdentityName(), CREATECONTEXT_SET_APP_IDENTITY, &hUserIdenti"
        "ty, c_updateUserIdKeyAttestationApplicationId)");
      goto LABEL_78;
    }
    LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v62, &v73);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = client.GetLogonId(logonId)";
      v12 = 2807;
      goto LABEL_4;
    }
    LogonId = (*(__int64 (__fastcall **)(__int64, struct _LUID *, _QWORD, struct CSingleIdentity **))(*(_QWORD *)v10 + 24LL))(
                v10,
                &v73,
                v80[0],
                &v54);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, pUserIdentity)";
      v12 = 2808;
      goto LABEL_4;
    }
    if ( !v54 )
    {
      v51 = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::UpdateUserIdKeyAttestation",
        0xAFAu,
        -2147418113,
        "pUserIdentity != nullptr");
      goto LABEL_78;
    }
    LogonId = CSingleIdentity::GetServiceTicket(v54, (__int64)&v65, (__int64)&v70);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = pUserIdentity->GetServiceTicket( pExecutionContext, PPCRL_LOGIN_PROOF_TOKEN_URI, PPCRL_LOGIN_PROOF_TOKE"
            "N_POLICY_KEYUPDATE, throttleScenario, loginProofToken)";
      v12 = 2818;
      goto LABEL_4;
    }
    v22 = v70;
    if ( !*((_DWORD *)v70 - 4) )
    {
      v51 = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::UpdateUserIdKeyAttestation",
        0xB04u,
        -2147418113,
        "loginProofToken.GetLength() != 0");
      goto LABEL_78;
    }
    LogonId = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v7 + 112LL))(
                v7,
                *(_QWORD *)(v74[0] + 32LL),
                v82,
                &v60);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = pNgcFunctions->NgcGetUserIdKeyPublicKey( spKeyInfo->pwszKeyName, &ngcPublicKey, &ngcPublicKeySizeBytes)";
      v12 = 2825;
      goto LABEL_4;
    }
    v23 = (UserIdKeyRegistrationRequest *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    v71 = (struct _RTL_CRITICAL_SECTION *)v23;
    if ( v23 )
      v6 = UserIdKeyRegistrationRequest::UserIdKeyRegistrationRequest(v23);
    else
      v6 = 0;
    v75 = v6;
    if ( !v6 )
    {
      v51 = -2147024882;
      goto LABEL_78;
    }
    LogonId = (*(__int64 (__fastcall **)(UserIdKeyRegistrationRequest *, _QWORD, _QWORD, char **))(*(_QWORD *)v6 + 136LL))(
                v6,
                v82[0],
                v60,
                &v66);
    v51 = LogonId;
    if ( LogonId < 0 )
    {
      v48 = "hr = pRequest->ComputeServerKeyId( ngcPublicKey, ngcPublicKeySizeBytes, serverKeyId)";
      v12 = 2833;
      goto LABEL_4;
    }
    v24 = v54;
    *((_BYTE *)v6 + 64) = 0;
    CPPCRLBaseRequest::InitializeBase(v6, v24);
    v63 = (char *)v54 + 16;
    v64 = 0;
    v25 = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v63);
    v51 = v25;
    if ( v25 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::UpdateUserIdKeyAttestation",
        0xB17u,
        v25,
        "hr = lock.Lock()");
LABEL_51:
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v63);
      goto LABEL_78;
    }
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
    v98 = 0;
    v99 = 0;
    v26 = UserIdKeyRegistrationRequest::BuildRequest(v6, v22, "Update", 0, 0, v66, v84[0], v56, v83[0], v55);
    v51 = v26;
    if ( v26 < 0 )
    {
      v27 = "hr = pRequest->BuildRequest( loginProofToken, \"Update\", nullptr, 0, serverKeyId, spAttestationStatement, a"
            "ttestationStatementSizeBytes, spAikCertChain, aikCertChainSizeBytes)";
      v28 = 2851;
LABEL_54:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CSingleIdentity::UpdateUserIdKeyAttestation",
        v28,
        v26,
        v27);
      CTransport::~CTransport((CTransport *)&v88);
      goto LABEL_51;
    }
    v26 = CTransport::SendRequest((CTransport *)&v88, v6, 0);
    v51 = v26;
    if ( v26 < 0 )
    {
      v27 = "hr = transport.SendRequest(pRequest)";
      v28 = 2853;
      goto LABEL_54;
    }
    v51 = *((_DWORD *)v6 + 17);
    CTransport::~CTransport((CTransport *)&v88);
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v63);
    if ( v51 >= 0 )
    {
      *(_QWORD *)v57 = *(_QWORD *)ATL::CTime::GetTickCount(&v63);
      *(_QWORD *)v57 -= *((int *)CClientConfigDataCacheManager::theConfigDataManager() + 68);
      RegistryHelper::WriteBufferToRegistry(
        (RegistryHelper *)&v72,
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\IdentityCRL",
        L"NgcUserIdKeyAttestedTime",
        0xBu,
        v57,
        8u);
    }
    else
    {
      CSingleIdentity::SetRequestStatus(v54, *((_DWORD *)v6 + 18));
      if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
      {
        if ( v54 )
        {
          ServerBuildInfo = (const unsigned __int16 **)CSingleIdentity::GetServerBuildInfo(v54, &v72);
          v30 = 1;
        }
        else
        {
          ServerBuildInfo = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                                         &v71,
                                                         "null");
          v30 = 2;
        }
        v52 = v30;
        v61 = (__int64)*ServerBuildInfo;
        v31 = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                           &v79,
                                           &cchOriginalDestLength);
        v32 = v30 | 8;
        v52 = v32;
        v76 = *v31;
        v33 = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                           &v78,
                                           &cchOriginalDestLength);
        v36 = v32 | 0x20;
        v52 = v36;
        v77 = *v33;
        v37 = v54;
        if ( v54 )
          v38 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)v54 + 56LL))(v54);
        else
          v38 = 0;
        LODWORD(v59) = v38;
        v58 = v51;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)v37,
          (__int64)byte_180199C75,
          v34,
          v35,
          (__int64)&v58,
          (__int64)&v59,
          &v77,
          &v76,
          (const unsigned __int16 **)&v61);
        v39 = v36 & 0xDF;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v78);
        if ( (v39 & 0x10) != 0 )
        {
          v39 &= ~0x10u;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v87);
        }
        if ( (v39 & 8) != 0 )
        {
          v39 &= ~8u;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v79);
        }
        if ( (v39 & 4) != 0 )
        {
          v39 &= ~4u;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
        }
        if ( (v39 & 2) != 0 )
        {
          v39 &= ~2u;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
        }
        if ( (v39 & 1) != 0 )
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
      }
    }
  }
LABEL_78:
  v40 = v51;
  Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>::~Auto<void *,NgcKeyEnumStateFunctor<void *>,INgcFunctions>(v85);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v86);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v62);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v54);
  Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(v80);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v66);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v69);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v70);
  Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(v74);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v81);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v82);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v83);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v84);
  if ( v6 )
    (**(void (__fastcall ***)(UserIdKeyRegistrationRequest *, __int64))v6)(v6, 1);
  return v40;
}

```

## disassembly

```asm
0x180067f4c  mov     [rsp-8+arg_18], rbx
0x180067f51  push    rbp
0x180067f52  push    rsi
0x180067f53  push    rdi
0x180067f54  push    r12
0x180067f56  push    r13
0x180067f58  push    r14
0x180067f5a  push    r15
0x180067f5c  lea     rbp, [rsp-170h]
0x180067f64  sub     rsp, 270h
0x180067f6b  mov     rax, cs:__security_cookie
0x180067f72  xor     rax, rsp
0x180067f75  mov     [rbp+1A0h+var_40], rax
0x180067f7c  mov     r12, r8
0x180067f7f  mov     r15, rdx
0x180067f82  mov     rsi, rcx
0x180067f85  xor     r13d, r13d
0x180067f88  mov     [rsp+2A0h+var_24C], r13d
0x180067f8d  mov     [rsp+2A0h+var_250], r13d
0x180067f92  mov     ebx, r13d
0x180067f95  mov     [rbp+1A0h+var_190], rbx
0x180067f99  mov     [rbp+1A0h+var_108], r13
0x180067fa0  mov     [rbp+1A0h+var_F8], r13
0x180067fa7  mov     [rbp+1A0h+var_100], r13
0x180067fae  mov     [rbp+1A0h+var_120], r13
0x180067fb5  mov     [rbp+1A0h+var_110], r13
0x180067fbc  mov     [rbp+1A0h+var_118], r13
0x180067fc3  mov     [rsp+2A0h+var_234], r13d
0x180067fc8  mov     [rsp+2A0h+var_238], r13d
0x180067fcd  mov     [rbp+1A0h+var_138], r13
0x180067fd1  mov     [rbp+1A0h+var_128], r13
0x180067fd5  mov     [rbp+1A0h+var_130], r13
0x180067fd9  mov     [rbp+1A0h+var_218], r13d
0x180067fdd  mov     [rbp+1A0h+var_150], r13
0x180067fe1  mov     [rbp+1A0h+var_140], r13
0x180067fe5  mov     [rbp+1A0h+var_148], r13
0x180067fe9  mov     [rbp+1A0h+var_1A8], r13
0x180067fed  mov     [rbp+1A0h+var_198], r13
0x180067ff1  mov     [rbp+1A0h+var_1A0], r13
0x180067ff5  mov     [rsp+2A0h+var_248], r13d
0x180067ffa  lea     rcx, [rbp+1A0h+var_1C8]
0x180067ffe  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068003  nop
0x180068004  lea     rcx, [rbp+1A0h+var_1D0]
0x180068008  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006800d  nop
0x18006800e  lea     rcx, [rbp+1A0h+var_1D8]
0x180068012  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068017  nop
0x180068018  lea     rcx, [rbp+1A0h+var_1E0]
0x18006801c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068021  nop
0x180068022  lea     rcx, [rbp+1A0h+var_1E8]
0x180068026  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006802b  nop
0x18006802c  mov     [rbp+1A0h+var_220], r13
0x180068030  lea     rcx, [rsp+2A0h+var_230]
0x180068035  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18006803a  lea     rdx, aNgcTpmbinding; "NGC_TpmBinding"
0x180068041  lea     rcx, [rbp+1A0h+var_1F0]
0x180068045  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006804a  nop
0x18006804b  mov     [rbp+1A0h+var_168], r13
0x18006804f  mov     [rbp+1A0h+var_158], r13
0x180068053  mov     [rbp+1A0h+var_160], r13
0x180068057  mov     [rsp+2A0h+var_240], r13
0x18006805c  mov     qword ptr [rbp+1A0h+var_1B0.LowPart], r13
0x180068060  mov     [rbp+1A0h+var_208], r13
0x180068064  mov     ecx, cs:_tls_index
0x18006806a  mov     rax, gs:58h
0x180068073  mov     edx, 8
0x180068078  mov     rax, [rax+rcx*8]
0x18006807c  mov     ecx, [rdx+rax]
0x18006807f  cmp     cs:dword_1801C703C, ecx
0x180068085  jg      loc_180068B3F
0x18006808b  lea     rcx, aCsingleidentit_12; "CSingleIdentity::UpdateUserIdKeyAttesta"...
0x180068092  mov     [rbp+1A0h+var_D8], rcx
0x180068099  lea     rax, [rsp+2A0h+var_250]
0x18006809e  mov     [rbp+1A0h+var_D0], rax
0x1800680a5  mov     [rbp+1A0h+var_C8], r13
0x1800680ac  mov     [rbp+1A0h+var_C0], r13
0x1800680b3  xor     r9d, r9d; unsigned int
0x1800680b6  mov     r8d, 0A94h; char *
0x1800680bc  mov     rdx, rcx; char *
0x1800680bf  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800680c6  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800680cb  nop
0x1800680cc  mov     rax, [r15]
0x1800680cf  mov     rcx, r15
0x1800680d2  mov     rax, [rax+30h]
0x1800680d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680db  mov     r14, rax
0x1800680de  mov     [rbp+1A0h+var_F0], r13
0x1800680e5  mov     [rbp+1A0h+var_E0], rax
0x1800680ec  mov     [rbp+1A0h+var_E8], r13
0x1800680f3  mov     rcx, [r15]
0x1800680f6  mov     rax, [rcx+28h]
0x1800680fa  mov     rcx, r15
0x1800680fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068102  mov     rdx, rax
0x180068105  mov     rcx, [rax]
0x180068108  mov     rax, [rcx+30h]
0x18006810c  mov     rcx, rdx
0x18006810f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068114  mov     rdi, rax
0x180068117  mov     rcx, [r15]
0x18006811a  mov     rax, [rcx+28h]
0x18006811e  mov     rcx, r15
0x180068121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068126  mov     [rbp+1A0h+var_1B8], rax
0x18006812a  mov     rcx, [r15]
0x18006812d  mov     rax, [rcx+50h]
0x180068131  mov     rcx, r15
0x180068134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068139  mov     r15, rax
0x18006813c  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x180068143  add     rcx, 790h
0x18006814a  mov     byte ptr [rsp+2A0h+var_280], r13b
0x18006814f  mov     r9, [rbp+1A0h+var_1F0]
0x180068153  mov     r8d, 0Eh
0x180068159  mov     rdx, rsi
0x18006815c  call    ?CheckCurrentLimit@ThrottleManager@@QEAAJPEAVISingleIdentity@@W4EPPCRLRequestType@@PEBG_N@Z; ThrottleManager::CheckCurrentLimit(ISingleIdentity *,EPPCRLRequestType,ushort const *,bool)
0x180068161  mov     [rsp+2A0h+var_250], eax
0x180068165  test    eax, eax
0x180068167  jns     short loc_180068196
0x180068169  lea     r8, aHrGPppcrlGetth_2; "hr = g_pPPCRL->GetThrottleManager()->Ch"...
0x180068170  mov     [rsp+2A0h+var_280], r8; char *
0x180068175  mov     r8d, 0AA1h; unsigned int
0x18006817b  mov     r9d, eax; int
0x18006817e  lea     rdx, aCsingleidentit_12; "CSingleIdentity::UpdateUserIdKeyAttesta"...
0x180068185  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006818c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180068191  jmp     loc_180068A4A
0x180068196  mov     rax, [rsi]
0x180068199  lea     r8, [rbp+1A0h+var_1E0]
0x18006819d  lea     rdx, aNgcattestation; "NgcAttestationKeyType"
0x1800681a4  mov     rcx, rsi
0x1800681a7  mov     rax, [rax+40h]
0x1800681ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681b0  mov     rcx, [rbp+1A0h+var_1E0]
0x1800681b4  cmp     [rcx-10h], r13d
0x1800681b8  jle     short loc_1800681D3
0x1800681ba  call    cs:__imp__o__wtoi
0x1800681c0  cmp     eax, 6
0x1800681c3  ja      short loc_1800681D3
0x1800681c5  mov     ecx, 56h ; 'V'
0x1800681ca  bt      ecx, eax
0x1800681cd  jb      loc_180068A4A
0x1800681d3  mov     rax, [rdi]
0x1800681d6  lea     rdx, [rbp+1A0h+var_150]
0x1800681da  mov     rcx, rdi
0x1800681dd  mov     rax, [rax+20h]
0x1800681e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681e6  mov     [rsp+2A0h+var_250], eax
0x1800681ea  test    eax, eax
0x1800681ec  jns     short loc_180068205
0x1800681ee  lea     rcx, aHrPsystemstore_1; "hr = pSystemStore->GetCurrentUserSidStr"...
0x1800681f5  mov     [rsp+2A0h+var_280], rcx
0x1800681fa  mov     r8d, 0AB2h
0x180068200  jmp     loc_18006817B
0x180068205  mov     rax, [rsi]
0x180068208  lea     r8, [rbp+1A0h+var_1D8]
0x18006820c  lea     rdx, aCid; "CID"
0x180068213  mov     rcx, rsi
0x180068216  mov     rax, [rax+40h]
0x18006821a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006821f  mov     [rsp+2A0h+var_250], eax
0x180068223  test    eax, eax
0x180068225  jns     short loc_18006823E
0x180068227  lea     rcx, aHrThisGetcredp; "hr = this->GetCredProperty(PPCRL_CREDPR"...
0x18006822e  mov     [rsp+2A0h+var_280], rcx
0x180068233  mov     r8d, 0AB3h
0x180068239  jmp     loc_18006817B
0x18006823e  mov     r9, [rbp+1A0h+var_1D8]
0x180068242  cmp     [r9-10h], r13d
0x180068246  jnz     short loc_180068288
0x180068248  lea     r9, aCidIsNotSetFor_0; "CID is not set for the current identity"...
0x18006824f  mov     r8d, 0AB6h; unsigned int
0x180068255  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006825c  mov     ecx, 2; unsigned __int8
0x180068261  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180068266  mov     r9d, 80048891h
0x18006826c  mov     [rsp+2A0h+var_250], r9d
0x180068271  lea     rax, aHrPpcrlECredpr; "hr = PPCRL_E_CREDPROP_NOTFOUND"
0x180068278  mov     [rsp+2A0h+var_280], rax
0x18006827d  mov     r8d, 0AB7h
0x180068283  jmp     loc_18006817E
0x180068288  mov     rax, [r14]
0x18006828b  lea     rcx, [rbp+1A0h+var_F0]
0x180068292  mov     [rsp+2A0h+var_270], rcx
0x180068297  lea     rcx, [rbp+1A0h+var_1A8]
0x18006829b  mov     [rsp+2A0h+var_278], rcx
0x1800682a0  mov     rcx, [rbp+1A0h+var_150]
0x1800682a4  mov     [rsp+2A0h+var_280], rcx
0x1800682a9  xor     r8d, r8d
0x1800682ac  lea     rdx, aLoginLiveCom; "login.live.com"
0x1800682b3  mov     rcx, r14
0x1800682b6  mov     rax, [rax+48h]
0x1800682ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800682bf  mov     [rsp+2A0h+var_250], eax
0x1800682c3  test    eax, eax
0x1800682c5  jns     short loc_1800682DE
0x1800682c7  lea     rcx, aHrPngcfunction_5; "hr = pNgcFunctions->NgcEnumUserIdKeys( "...
0x1800682ce  mov     [rsp+2A0h+var_280], rcx
0x1800682d3  mov     r8d, 0AC1h
0x1800682d9  jmp     loc_18006817B
0x1800682de  lea     rdi, ?_criticalSection@CSingleIdentity@@2VCCritSecLite@@A; CCritSecLite CSingleIdentity::_criticalSection
0x1800682e5  mov     [rbp+1A0h+var_1C0], rdi
0x1800682e9  mov     rcx, rdi; lpCriticalSection
0x1800682ec  call    cs:__imp_EnterCriticalSection
0x1800682f2  nop
0x1800682f3  lea     r8, [rbp+1A0h+var_220]
0x1800682f7  mov     rdx, [rbp+1A0h+var_1A8]
0x1800682fb  mov     rdx, [rdx+20h]
0x1800682ff  call    ?Lookup@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_JV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_J@2@@ATL@@QEBA_NPEBGAEA_J@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,__int64,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<__int64>>::Lookup(ushort const *,__int64 &)
0x180068304  cmp     al, 1
0x180068306  jnz     short loc_18006833C
0x180068308  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x18006830d  movsxd  rcx, dword ptr [rax+110h]
0x180068314  mov     r8, qword ptr [rsp+2A0h+var_230]
0x180068319  sub     r8, rcx
0x18006831c  mov     qword ptr [rsp+2A0h+var_230], r8
0x180068321  mov     rax, r8
0x180068324  sub     rax, [rbp+1A0h+var_220]
0x180068328  cmp     rax, 78h ; 'x'
0x18006832c  jge     short loc_180068341
0x18006832e  mov     rcx, rdi; lpCriticalSection
0x180068331  call    cs:__imp_LeaveCriticalSection
0x180068337  jmp     loc_180068A4A
0x18006833c  mov     r8, qword ptr [rsp+2A0h+var_230]
0x180068341  mov     rdx, [rbp+1A0h+var_1A8]
0x180068345  mov     rdx, [rdx+20h]
0x180068349  call    ?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_JV?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@_J@2@@ATL@@QEAAPEAU__POSITION@@PEBG_J@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,__int64,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<__int64>>::SetAt(ushort const *,__int64)
0x18006834e  nop
0x18006834f  mov     rcx, rdi; lpCriticalSection
0x180068352  call    cs:__imp_LeaveCriticalSection
0x180068358  mov     rax, [r14]
0x18006835b  lea     rcx, [rsp+2A0h+var_248]
0x180068360  mov     qword ptr [rsp+2A0h+var_268], rcx
0x180068365  lea     rcx, [rsp+2A0h+var_238]
0x18006836a  mov     [rsp+2A0h+var_270], rcx
0x18006836f  lea     rcx, [rbp+1A0h+var_120]
0x180068376  mov     [rsp+2A0h+var_278], rcx
0x18006837b  lea     rcx, [rsp+2A0h+var_234]
0x180068380  mov     [rsp+2A0h+var_280], rcx
0x180068385  lea     r9, [rbp+1A0h+var_108]
0x18006838c  mov     r8, r12
0x18006838f  mov     rdx, [rbp+1A0h+var_1A8]
0x180068393  mov     rdx, [rdx+20h]
0x180068397  mov     rcx, r14
0x18006839a  mov     rax, [rax+28h]
0x18006839e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683a3  mov     [rsp+2A0h+var_250], eax
0x1800683a7  mov     r8d, [rsp+2A0h+var_248]
0x1800683ac  lea     rdx, aD; "%d"
0x1800683b3  lea     rcx, [rbp+1A0h+var_1D0]
0x1800683b7  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800683bc  mov     r8, [rbp+1A0h+var_1D0]; unsigned __int16 *
0x1800683c0  lea     rdx, aNgcattestation; "NgcAttestationKeyType"
0x1800683c7  mov     rcx, rsi; this
0x1800683ca  call    ?SetCredProperty@CSingleIdentity@@QEAAJPEBG0@Z; CSingleIdentity::SetCredProperty(ushort const *,ushort const *)
0x1800683cf  mov     eax, cs:dword_1801C2080
0x1800683d5  lea     r12, dword_1801C2080
0x1800683dc  cmp     eax, 5
0x1800683df  jbe     short loc_18006843C
0x1800683e1  mov     rdx, 400000000000h
0x1800683eb  mov     rcx, r12
0x1800683ee  call    _tlgKeywordOn
0x1800683f3  test    al, al
0x1800683f5  jz      short loc_18006843C
0x1800683f7  mov     eax, [rsp+2A0h+var_250]
0x1800683fb  mov     [rsp+2A0h+var_228], eax
0x1800683ff  mov     eax, [rsp+2A0h+var_248]
0x180068403  mov     dword ptr [rbp+1A0h+var_220], eax
0x180068406  mov     [rbp+1A0h+var_210], 3000000h
0x18006840e  lea     rax, [rsp+2A0h+var_228]
0x180068413  mov     [rsp+2A0h+var_270], rax
0x180068418  lea     rax, [rbp+1A0h+var_220]
0x18006841c  mov     [rsp+2A0h+var_278], rax
0x180068421  lea     rax, [rbp+1A0h+var_210]
0x180068425  mov     [rsp+2A0h+var_280], rax
0x18006842a  xor     r8d, r8d
0x18006842d  lea     rdx, dword_180199CD4
0x180068434  mov     rcx, r12
0x180068437  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006843c  cmp     [rsp+2A0h+var_234], r13d
0x180068441  jz      loc_180068A1C
0x180068447  cmp     [rsp+2A0h+var_238], r13d
0x18006844c  jz      loc_180068A1C
0x180068452  xor     edx, edx; struct ATL::CAccessToken *
0x180068454  lea     rcx, [rbp+1A0h+var_208]; this
0x180068458  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18006845d  mov     [rsp+2A0h+var_250], eax
0x180068461  test    eax, eax
0x180068463  jns     short loc_18006847C
0x180068465  lea     rcx, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x18006846c  mov     [rsp+2A0h+var_280], rcx
0x180068471  mov     r8d, 0AF0h
0x180068477  jmp     loc_18006817B
0x18006847c  mov     rax, [r15]
  ... truncated ...
```
