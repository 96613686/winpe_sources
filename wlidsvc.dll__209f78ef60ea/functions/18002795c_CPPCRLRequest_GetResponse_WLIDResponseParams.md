# CPPCRLRequest::GetResponse(_WLIDResponseParams * *)

- ea: `0x18002795c`
- end: `0x180028768`
- name: `?GetResponse@CPPCRLRequest@@QEAAJPEAPEAU_WLIDResponseParams@@@Z`
- size: `3596`
- prototype: `__int64 __fastcall(CPPCRLRequest *__hidden this, struct _WLIDResponseParams **)`
- caller_count: `4`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800563d0`
- `0x1800d7318`
- `0x1800d9080`
- `0x1800db220`

## callees

- `0x18000c050`
- `0x18000cf88`
- `0x18000ed04`
- `0x18000ed3c`
- `0x180011f38`
- `0x1800151c4`
- `0x180015fb0`
- `0x1800179c0`
- `0x1800181bc`
- `0x180018f80`
- `0x1800191c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180022db4`
- `0x180026c18`
- `0x180027270`
- `0x1800277c0`
- `0x1800277ec`
- `0x180027814`
- `0x18002783c`
- `0x18002795c`
- `0x180028770`
- `0x180029d54`
- `0x180030030`
- `0x180030120`
- `0x180033218`
- `0x180037288`
- `0x180037e48`
- `0x18004d6e4`
- `0x18004e6cc`
- `0x18004edf4`
- `0x18004ff98`
- `0x180051784`
- `0x180079554`
- `0x1800814f8`
- `0x180082230`
- `0x180084374`
- `0x1800a4778`
- `0x1800de8f0`
- `0x1800e0e6c`
- `0x1800e32e0`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027aa3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027e75`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027f9c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002801c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028095`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800280ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002814e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800281f0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002829d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027aa3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027e75`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180027f9c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002801c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028095`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800280ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002814e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800281f0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002829d`

## string_xrefs

- `0x180027a0e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180027a60`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180027ce8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180028442`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800284a3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800286ab`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180027f32`: `hr = CAuthInfo::EncryptStringInSystemContext(&executionContext, token.GetToken(), tokenBlob)`
- `0x180028653`: `hr = token.GetAuthzToken(pszAuthzToken)`
- `0x180027a53`: `Could not get CID for this ID handle, even though it is marked linked. 0x%x`
- `0x1800286b7`: `hr = CopyResponseString(&rgResponses[i].wszInlineAuthUrl, authUrl)`
- `0x1800286c6`: `hr = CopyResponseString(&rgResponses[i].wszAuthChallenge, wszFlowUrl)`
- `0x180027cf4`: `g_pPPCRL->GetNegativeCacheManager()->UpdateNegativeCache( m_rgRequests[i].wszServiceTarget, m_rgRequests[i].wszServicePolicy, rgResponses[i].hrRequestStatus, m_pIdentity, (!m_pIdentity->GetAuthUrl().IsEmpty() || !m_pIdentity->GetEndAuthUrl().IsEmpty() || !authUrl.IsEmpty() || !wszFlowUrl.IsEmpty()), m_pIdentity->IsConnected())`
- `0x180028696`: `hr = CopyResponseString(&rgResponses[i].wszInlineEndAuthUrl, endAuthUrl)`
- `0x180028542`: `hr = g_pPPCRL->GetCertManager()->GetCert(m_pIdentity, m_rgRequests[i].wszServiceTarget, dwTTL, &pCertCtxt, nullptr)`
- `0x18002866d`: `hr = StringCchCopyW(rgResponses[i].wszToken, tokenBlob.GetLength() + 1, tokenBlob)`
- `0x180028556`: `hr = StringCchCopyW(rgResponses[i].wszToken, wstrCert.GetLength()+1, wstrCert)`
- `0x18002862d`: `hr = SafeCopyMemory(rgResponses[i].pbSessionKey, bpSessionKey.GetLength(), bpSessionKey.GetBuffer(), bpSessionKey.GetLength())`
- `0x18002858b`: `hr = StringCchCopyW(rgResponses[i].wszAuthorizationToken, pszAuthzToken.GetLength()+1, pszAuthzToken)`
- `0x180028607`: `hr = StringCchCopyW(rgResponses[i].wstrKeyPair, token.GetKeyPair().GetLength()+1, token.GetKeyPair())`
- `0x180028616`: `hr = StringCchCopyW(rgResponses[i].wszCID, wstrCID.GetLength()+1, wstrCID)`
- `0x1800285a5`: `hr = StringCchCopyW(rgResponses[i].tokenResponseData, tokenResponseData.GetLength() + 1, tokenResponseData)`
- `0x1800285de`: `hr = StringCchCopyW(rgResponses[i].wstrTokenURI, token.GetTokenURI().GetLength()+1, token.GetTokenURI())`
- `0x180028426`: `g_pPPCRL->GetNegativeCacheManager()->UpdateNegativeCache( m_rgRequests[i].wszServiceTarget, m_rgRequests[i].wszServicePolicy, rgResponses[i].hrRequestStatus, m_pIdentity, (!m_pIdentity->GetAuthUrl().IsEmpty() || !m_pIdentity->GetEndAuthUrl().IsEmpty()), m_pIdentity->IsConnected())`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CPPCRLRequest::GetResponse(CPPCRLRequest *this, struct _WLIDResponseParams **a2)
{
  int v3; // esi
  struct _WLIDResponseParams **v4; // rdi
  unsigned int v5; // r15d
  int v6; // ebx
  __int64 v7; // r12
  struct _WLIDResponseParams *v8; // rcx
  __int64 v9; // rcx
  unsigned int i; // r13d
  __int64 v11; // rax
  __int64 v12; // rdi
  struct _WLIDResponseParams *v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  CPassportClientLibrary *v18; // r15
  __int64 v19; // rcx
  bool v20; // r12
  _QWORD *AuthUrl; // rax
  _QWORD *EndAuthUrl; // rax
  bool v23; // al
  int updated; // r15d
  int Cert; // eax
  __int64 v26; // rbx
  int v27; // eax
  __int64 Token; // rax
  unsigned __int16 *v29; // rbx
  unsigned __int16 *v30; // rcx
  int v31; // eax
  unsigned __int16 **v32; // rcx
  _QWORD *v33; // rax
  int v34; // ebx
  unsigned __int16 **v35; // rcx
  __int64 v36; // rax
  unsigned __int16 *v37; // rbx
  unsigned __int16 *v38; // rcx
  int v39; // eax
  int AuthzToken; // eax
  unsigned __int16 *v41; // rbx
  int v42; // eax
  unsigned __int16 *v43; // rcx
  int v44; // eax
  int v45; // r15d
  unsigned int v46; // ebx
  __int64 v47; // rcx
  int v48; // eax
  unsigned __int16 *v49; // rcx
  int v50; // eax
  _QWORD *KeyPair; // rax
  const unsigned __int16 *v52; // rbx
  _QWORD *v53; // rax
  int v54; // ebx
  _QWORD *TokenURI; // rax
  const unsigned __int16 *v56; // rbx
  _QWORD *v57; // rax
  unsigned __int16 *v58; // rbx
  int v59; // eax
  unsigned __int16 *v60; // rcx
  int v61; // eax
  int v62; // eax
  CPassportClientLibrary *v63; // r15
  __int64 v64; // rcx
  bool v65; // r12
  _QWORD *v66; // rax
  _QWORD *v67; // rax
  bool v68; // al
  int v69; // ebx
  CIdentityCredentialBag *v70; // rax
  int v71; // eax
  const char *v72; // rax
  unsigned int v73; // r8d
  int v74; // r9d
  const char *v75; // rcx
  unsigned int v76; // r8d
  unsigned int v77; // ebx
  CAutoFreeWLIDResponse *v78; // rcx
  struct ISingleIdentity *v80; // [rsp+20h] [rbp-E0h]
  struct ISingleIdentity *v81; // [rsp+20h] [rbp-E0h]
  const char *v82; // [rsp+20h] [rbp-E0h]
  struct _WLIDResponseParams *v83; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v84; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v85; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v86; // [rsp+58h] [rbp-A8h] BYREF
  struct _WLIDResponseParams **v87; // [rsp+60h] [rbp-A0h]
  unsigned int v88; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v89; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v90; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v91; // [rsp+80h] [rbp-80h] BYREF
  size_t Size; // [rsp+88h] [rbp-78h] BYREF
  __int64 v93; // [rsp+90h] [rbp-70h]
  int v94; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v95; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v96; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v97; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v98[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v99; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v100[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v101; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v102; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v103; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v104; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v105; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v106; // [rsp+100h] [rbp+0h] BYREF
  __int64 v107; // [rsp+108h] [rbp+8h] BYREF
  __int64 v108; // [rsp+110h] [rbp+10h] BYREF
  __int64 v109; // [rsp+118h] [rbp+18h] BYREF
  __int64 v110; // [rsp+120h] [rbp+20h] BYREF
  __int64 v111; // [rsp+128h] [rbp+28h] BYREF
  __int64 v112; // [rsp+130h] [rbp+30h] BYREF
  __int64 v113; // [rsp+138h] [rbp+38h] BYREF
  __int64 v114; // [rsp+140h] [rbp+40h]
  _BYTE v115[24]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v116; // [rsp+168h] [rbp+68h]
  __int64 v117; // [rsp+170h] [rbp+70h]
  __int64 v118; // [rsp+188h] [rbp+88h]
  int v119; // [rsp+1B0h] [rbp+B0h]
  int v120; // [rsp+1B4h] [rbp+B4h]
  _BYTE v121[24]; // [rsp+1B8h] [rbp+B8h] BYREF
  const void *v122; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int v123; // [rsp+1D8h] [rbp+D8h]
  unsigned __int8 *v124; // [rsp+1E0h] [rbp+E0h]
  _QWORD v125[4]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v126[272]; // [rsp+220h] [rbp+120h] BYREF
  int v128; // [rsp+350h] [rbp+250h] BYREF
  int v129; // [rsp+358h] [rbp+258h] BYREF

  v3 = 0;
  v129 = 0;
  v128 = 0;
  v83 = 0;
  v95 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v4 = 0;
  v87 = 0;
  v5 = 0;
  v88 = 0;
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v126);
  v125[0] = "CPPCRLRequest::GetResponse";
  v125[1] = &v128;
  v125[2] = 0;
  v125[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
    "CPPCRLRequest::GetResponse",
    (const char *)0xE42,
    0,
    (const unsigned __int16 *)v80);
  v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 **))(**((_QWORD **)this + 3) + 64LL))(
         *((_QWORD *)this + 3),
         L"CID",
         &v95);
  if ( CSingleIdentity::GetIsLinkedHandle(*((CSingleIdentity **)this + 3)) && !*((_DWORD *)v95 - 4) )
  {
    LODWORD(v81) = v6;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      0xE4Cu,
      L"Could not get CID for this ID handle, even though it is marked linked. 0x%x",
      v81);
  }
  v7 = *(_QWORD *)(((*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3)) != 0
                  ? 8
                  : 0)
                 + *((_QWORD *)this + 3)
                 + 88LL);
  v114 = v7;
  v8 = (struct _WLIDResponseParams *)malloc(136LL * *((unsigned int *)this + 33));
  v83 = v8;
  if ( !v8 )
  {
    v128 = -2147024882;
    goto LABEL_105;
  }
  memset_0(v8, 0, 136LL * *((unsigned int *)this + 33));
  v87 = &v83;
  v88 = *((_DWORD *)this + 33);
  for ( i = 0; i < *((_DWORD *)this + 33); ++i )
  {
    CPPCRLToken::CPPCRLToken((CPPCRLToken *)v115);
    v11 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            v100,
            *(_QWORD *)(*((_QWORD *)this + 17) + 40LL * i));
    if ( (unsigned int)CIdentityTokenBag::RetrieveToken(v7, v11, v115) )
    {
      v93 = 0;
      LODWORD(Size) = 0;
      v94 = 0;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
      v12 = 136LL * i;
      v13 = v83;
      *(_DWORD *)((char *)v83 + v12) = v119;
      *(_DWORD *)((char *)v13 + v12 + 4) = v120;
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v85, v121);
      CPPCRLToken::GetAuthUrls(v115, &v84, &v86);
      v15 = CPPCRLRequest::CopyResponseString(v14, (char *)v83 + v12 + 56, &v85);
      v128 = v15;
      if ( v15 < 0 )
      {
        v75 = "hr = CopyResponseString(&rgResponses[i].wszAuthChallenge, wszFlowUrl)";
        v76 = 3693;
        goto LABEL_97;
      }
      v15 = CPPCRLRequest::CopyResponseString(v16, (char *)v83 + v12 + 64, &v84);
      v128 = v15;
      if ( v15 < 0 )
      {
        v75 = "hr = CopyResponseString(&rgResponses[i].wszInlineAuthUrl, authUrl)";
        v76 = 3694;
        goto LABEL_97;
      }
      v15 = CPPCRLRequest::CopyResponseString(v17, (char *)v83 + v12 + 72, &v86);
      v128 = v15;
      if ( v15 < 0 )
      {
        v75 = "hr = CopyResponseString(&rgResponses[i].wszInlineEndAuthUrl, endAuthUrl)";
        v76 = 3695;
LABEL_97:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          "CPPCRLRequest::GetResponse",
          v76,
          v15,
          v75);
        goto LABEL_77;
      }
      v18 = g_pPPCRL;
      v19 = *((_QWORD *)this + 3);
      v20 = *(_DWORD *)(v19 + 736) != 0;
      AuthUrl = (_QWORD *)CSingleIdentity::GetAuthUrl(v19, &v102);
      v3 |= 1u;
      v129 = v3;
      v23 = 1;
      if ( !*(_DWORD *)(*AuthUrl - 16LL) )
      {
        EndAuthUrl = (_QWORD *)CSingleIdentity::GetEndAuthUrl(*((_QWORD *)this + 3), &v101);
        v3 |= 2u;
        v129 = v3;
        if ( !*(_DWORD *)(*EndAuthUrl - 16LL) && !*(_DWORD *)(v84 - 16) && !*(_DWORD *)(v85 - 16) )
          v23 = 0;
      }
      updated = NegativeCacheManager::UpdateNegativeCache(
                  (CPassportClientLibrary *)((char *)v18 + 2312),
                  *(const unsigned __int16 **)(*((_QWORD *)this + 17) + 40LL * i),
                  *(const unsigned __int16 **)(*((_QWORD *)this + 17) + 40LL * i + 8),
                  *(_DWORD *)((char *)v83 + v12 + 4),
                  *((struct ISingleIdentity **)this + 3),
                  v23,
                  v20);
      if ( (v3 & 2) != 0 )
      {
        v3 &= ~2u;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v101);
      }
      if ( (v3 & 1) != 0 )
      {
        v3 &= ~1u;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v102);
      }
      if ( updated < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          "CPPCRLRequest::GetResponse",
          0xE78u,
          updated,
          "g_pPPCRL->GetNegativeCacheManager()->UpdateNegativeCache( m_rgRequests[i].wszServiceTarget, m_rgRequests[i].ws"
          "zServicePolicy, rgResponses[i].hrRequestStatus, m_pIdentity, (!m_pIdentity->GetAuthUrl().IsEmpty() || !m_pIden"
          "tity->GetEndAuthUrl().IsEmpty() || !authUrl.IsEmpty() || !wszFlowUrl.IsEmpty()), m_pIdentity->IsConnected())");
      if ( *(int *)((char *)v83 + v12 + 4) < 0 )
      {
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
        CBytePtr::Empty((CBytePtr *)&Size);
        goto LABEL_72;
      }
      if ( (*(_BYTE *)(*((_QWORD *)this + 17) + 40LL * i + 24) & 8) != 0 )
      {
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v90);
        if ( *(_QWORD *)(*((_QWORD *)this + 17) + 40LL * i + 16) )
        {
          Token = CPPCRLToken::GetToken(v115, &v103);
          ATL::CSimpleStringT<unsigned short,0>::operator=(&v90, Token);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v103);
        }
        else
        {
          v99 = 0;
          v98[1] = 0;
          v98[0] = &SmartPCCERT_CONTEXT::`vftable';
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v96);
          v129 = 0;
          Cert = CCertManager::GetCert(
                   (char *)g_pPPCRL + 1376,
                   *((_QWORD *)this + 3),
                   *(_QWORD *)(*((_QWORD *)this + 17) + 40LL * i),
                   &v129,
                   &v99,
                   0);
          v128 = Cert;
          if ( Cert < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
              "CPPCRLRequest::GetResponse",
              0xE8Fu,
              Cert,
              "hr = g_pPPCRL->GetCertManager()->GetCert(m_pIdentity, m_rgRequests[i].wszServiceTarget, dwTTL, &pCertCtxt, nullptr)");
            goto LABEL_74;
          }
          v26 = v99;
          SmartPtr<void *>::Attach(v98, v99);
          v27 = PassportEncode::Base64Encode(*(unsigned __int8 **)(v26 + 8), *(_DWORD *)(v26 + 16));
          v128 = v27;
          if ( v27 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
              "CPPCRLRequest::GetResponse",
              0xE94u,
              v27,
              "hr = PassportEncode::Base64Encode(pCertCtxt->pbCertEncoded, pCertCtxt->cbCertEncoded, strCert)");
LABEL_74:
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v96);
            SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v98);
LABEL_75:
            v35 = &v90;
            goto LABEL_76;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
            &v90,
            v96);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v96);
          SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v98);
        }
        v29 = v90;
        *(_QWORD *)((char *)v83 + v12 + 40) = malloc(2LL * (*((_DWORD *)v90 - 4) + 1));
        v30 = *(unsigned __int16 **)((char *)v83 + v12 + 40);
        if ( !v30 )
        {
          v128 = -2147024882;
          goto LABEL_75;
        }
        v31 = StringCchCopyW(v30, *((_DWORD *)v29 - 4) + 1, v29);
        v128 = v31;
        if ( v31 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
            "CPPCRLRequest::GetResponse",
            0xE9Eu,
            v31,
            "hr = StringCchCopyW(rgResponses[i].wszToken, wstrCert.GetLength()+1, wstrCert)");
          goto LABEL_75;
        }
        *(_DWORD *)((char *)v83 + v12 + 32) = 2;
        v32 = &v90;
      }
      else
      {
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v89);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v91);
        if ( ShouldEncryptServiceToken(
               *(wchar_t **)(*((_QWORD *)this + 17) + 40LL * i),
               *(const unsigned __int16 **)(*((_QWORD *)this + 17) + 40LL * i + 8)) )
        {
          v33 = (_QWORD *)CPPCRLToken::GetToken(v115, &v104);
          v34 = CAuthInfo::EncryptStringInSystemContext(v126, *v33, &v89);
          v128 = v34;
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v104);
          if ( v34 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
              "CPPCRLRequest::GetResponse",
              0xEA9u,
              v34,
              "hr = CAuthInfo::EncryptStringInSystemContext(&executionContext, token.GetToken(), tokenBlob)");
            goto LABEL_38;
          }
        }
        else
        {
          v36 = CPPCRLToken::GetToken(v115, &v105);
          ATL::CSimpleStringT<unsigned short,0>::operator=(&v89, v36);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v105);
        }
        v37 = v89;
        *(_QWORD *)((char *)v83 + v12 + 40) = malloc(2LL * (*((_DWORD *)v89 - 4) + 1));
        v38 = *(unsigned __int16 **)((char *)v83 + v12 + 40);
        if ( !v38 )
          goto LABEL_95;
        v39 = StringCchCopyW(v38, *((_DWORD *)v37 - 4) + 1, v37);
        v128 = v39;
        if ( v39 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
            "CPPCRLRequest::GetResponse",
            0xEB2u,
            v39,
            "hr = StringCchCopyW(rgResponses[i].wszToken, tokenBlob.GetLength() + 1, tokenBlob)");
          goto LABEL_38;
        }
        *(_DWORD *)((char *)v83 + v12 + 32) = GetTokenType(v116);
        AuthzToken = CPPCRLToken::GetAuthzToken(v115, &v91);
        v128 = AuthzToken;
        if ( AuthzToken < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
            "CPPCRLRequest::GetResponse",
            0xEB6u,
            AuthzToken,
            "hr = token.GetAuthzToken(pszAuthzToken)");
          goto LABEL_38;
        }
        v41 = v91;
        v42 = *((_DWORD *)v91 - 4);
        if ( v42 )
        {
          *(_QWORD *)((char *)v83 + v12 + 48) = malloc(2LL * (v42 + 1));
          v43 = *(unsigned __int16 **)((char *)v83 + v12 + 48);
          if ( !v43 )
          {
LABEL_95:
            v128 = -2147024882;
LABEL_38:
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v91);
            v35 = &v89;
            goto LABEL_76;
          }
          v44 = StringCchCopyW(v43, *((_DWORD *)v41 - 4) + 1, v41);
          v128 = v44;
          if ( v44 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
              "CPPCRLRequest::GetResponse",
              0xEBCu,
              v44,
              "hr = StringCchCopyW(rgResponses[i].wszAuthorizationToken, pszAuthzToken.GetLength()+1, pszAuthzToken)");
            goto LABEL_38;
          }
        }
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v91);
        v32 = &v89;
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v32);
      CBytePtr::Attach((CBytePtr *)&Size, v124, v123, 0);
      v45 = Size;
      v46 = Size;
      *(_QWORD *)((char *)v83 + v12 + 16) = malloc((unsigned int)Size);
      v47 = *(_QWORD *)((char *)v83 + v12 + 16);
      if ( !v47 )
        goto LABEL_92;
      v48 = SafeCopyMemory(v47, v46, v93, v46);
      v128 = v48;
      if ( v48 < 0 )
      {
        v82 = "hr = SafeCopyMemory(rgResponses[i].pbSessionKey, bpSessionKey.GetLength(), bpSessionKey.GetBuffer(), bpSes"
              "sionKey.GetLength())";
        v74 = v48;
        v73 = 3779;
        goto LABEL_87;
      }
      *(_DWORD *)((char *)v83 + v12 + 8) = v45;
      *(_QWORD *)((char *)v83 + v12 + 24) = malloc(2LL * (*((_DWORD *)v95 - 4) + 1));
      v49 = *(unsigned __int16 **)((char *)v83 + v12 + 24);
      if ( !v49 )
        goto LABEL_92;
      v50 = StringCchCopyW(v49, *((_DWORD *)v95 - 4) + 1, v95);
      v128 = v50;
      if ( v50 < 0 )
      {
        v82 = "hr = StringCchCopyW(rgResponses[i].wszCID, wstrCID.GetLength()+1, wstrCID)";
        v74 = v50;
        v73 = 3784;
        goto LABEL_87;
      }
      KeyPair = (_QWORD *)CPPCRLToken::GetKeyPair(v115, &v106);
      *(_QWORD *)((char *)v83 + v12 + 88) = malloc(2LL * (*(_DWORD *)(*KeyPair - 16LL) + 1));
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v106);
      if ( !*(_QWORD *)((char *)v83 + v12 + 88) )
        goto LABEL_92;
      v52 = *(const unsigned __int16 **)CPPCRLToken::GetKeyPair(v115, &v108);
      v53 = (_QWORD *)CPPCRLToken::GetKeyPair(v115, &v107);
      v54 = StringCchCopyW(*(unsigned __int16 **)((char *)v83 + v12 + 88), *(_DWORD *)(*v53 - 16LL) + 1, v52);
      v128 = v54;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v107);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v108);
      if ( v54 < 0 )
      {
        v72 = "hr = StringCchCopyW(rgResponses[i].wstrKeyPair, token.GetKeyPair().GetLength()+1, token.GetKeyPair())";
        v73 = 3788;
LABEL_86:
        v74 = v54;
        v82 = v72;
LABEL_87:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          "CPPCRLRequest::GetResponse",
          v73,
          v74,
          v82);
LABEL_77:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
        CBytePtr::Empty((CBytePtr *)&Size);
        CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v115);
        goto LABEL_104;
      }
      TokenURI = (_QWORD *)CPPCRLToken::GetTokenURI(v115, &v109);
      *(_QWORD *)((char *)v83 + v12 + 80) = malloc(2LL * (*(_DWORD *)(*TokenURI - 16LL) + 1));
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v109);
      if ( !*(_QWORD *)((char *)v83 + v12 + 80) )
      {
LABEL_92:
        v128 = -2147024882;
        goto LABEL_77;
      }
      v56 = *(const unsigned __int16 **)CPPCRLToken::GetTokenURI(v115, &v111);
      v57 = (_QWORD *)CPPCRLToken::GetTokenURI(v115, &v110);
      v54 = StringCchCopyW(*(unsigned __int16 **)((char *)v83 + v12 + 80), *(_DWORD *)(*v57 - 16LL) + 1, v56);
      v128 = v54;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v110);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v111);
      if ( v54 < 0 )
      {
        v72 = "hr = StringCchCopyW(rgResponses[i].wstrTokenURI, token.GetTokenURI().GetLength()+1, token.GetTokenURI())";
        v73 = 3792;
        goto LABEL_86;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v97,
        &v122);
      v3 |= 0x10u;
      v58 = v97;
      v59 = *((_DWORD *)v97 - 4);
      if ( v59 )
      {
        *(_QWORD *)((char *)v83 + v12 + 120) = malloc(2LL * (v59 + 1));
        v60 = *(unsigned __int16 **)((char *)v83 + v12 + 120);
        if ( !v60 )
        {
          v128 = -2147024882;
LABEL_83:
          v35 = &v97;
LABEL_76:
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v35);
          goto LABEL_77;
        }
        v61 = StringCchCopyW(v60, *((_DWORD *)v58 - 4) + 1, v58);
        v128 = v61;
        if ( v61 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
            "CPPCRLRequest::GetResponse",
            0xED7u,
            v61,
            "hr = StringCchCopyW(rgResponses[i].tokenResponseData, tokenResponseData.GetLength() + 1, tokenResponseData)");
          goto LABEL_83;
        }
      }
      *(_QWORD *)((char *)v83 + v12 + 96) = v117;
      *(_QWORD *)((char *)v83 + v12 + 104) = v118;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v97);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
      CBytePtr::Empty((CBytePtr *)&Size);
    }
    else
    {
      v12 = 136LL * i;
      *(_DWORD *)((char *)v83 + v12) = *(_DWORD *)(*((_QWORD *)this + 3) + 188LL);
      v62 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3));
      *(_DWORD *)((char *)v83 + v12 + 4) = v62;
      v63 = g_pPPCRL;
      v64 = *((_QWORD *)this + 3);
      v65 = *(_DWORD *)(v64 + 736) != 0;
      v66 = (_QWORD *)CSingleIdentity::GetAuthUrl(v64, &v113);
      v3 |= 4u;
      v129 = v3;
      v68 = 1;
      if ( !*(_DWORD *)(*v66 - 16LL) )
      {
        v67 = (_QWORD *)CSingleIdentity::GetEndAuthUrl(*((_QWORD *)this + 3), &v112);
        v3 |= 8u;
        v129 = v3;
        if ( !*(_DWORD *)(*v67 - 16LL) )
          v68 = 0;
      }
      v69 = NegativeCacheManager::UpdateNegativeCache(
              (CPassportClientLibrary *)((char *)v63 + 2312),
              *(const unsigned __int16 **)(*((_QWORD *)this + 17) + 40LL * i),
              *(const unsigned __int16 **)(*((_QWORD *)this + 17) + 40LL * i + 8),
              *(_DWORD *)((char *)v83 + v12 + 4),
              *((struct ISingleIdentity **)this + 3),
              v68,
              v65);
      if ( (v3 & 8) != 0 )
      {
        v3 &= ~8u;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v112);
      }
      if ( (v3 & 4) != 0 )
      {
        v3 &= ~4u;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v113);
      }
      if ( v69 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          "CPPCRLRequest::GetResponse",
          0xEE9u,
          v69,
          "g_pPPCRL->GetNegativeCacheManager()->UpdateNegativeCache( m_rgRequests[i].wszServiceTarget, m_rgRequests[i].ws"
          "zServicePolicy, rgResponses[i].hrRequestStatus, m_pIdentity, (!m_pIdentity->GetAuthUrl().IsEmpty() || !m_pIden"
          "tity->GetEndAuthUrl().IsEmpty()), m_pIdentity->IsConnected())");
    }
    if ( *(_DWORD *)((char *)v83 + v12 + 4) == -2147186626 )
    {
      v70 = (CIdentityCredentialBag *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
      v71 = CIdentityCredentialBag::ResetDefaultCredSavedProperty(
              v70,
              (struct IServiceExecutionContext *)v126,
              L"DefaultCredsInvalid");
      if ( v71 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          "CPPCRLRequest::GetResponse",
          0xEEEu,
          v71,
          "m_pIdentity->GetCredBag()->ResetDefaultCredSavedProperty(&executionContext, PPCRL_CREDPROPERTY_VALUE_CREDS_INVALID)");
    }
LABEL_72:
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v115);
    v7 = v114;
  }
  if ( *((_DWORD *)v95 - 4) && (Microsoft_Windows_LiveIdEnableBits & 0x10) != 0 )
    McTemplateU0z_EventWriteTransfer(v9, Telemetry_UserSpecificTrigger, v95);
  *a2 = v83;
  v83 = 0;
LABEL_104:
  v5 = v88;
  v4 = v87;
LABEL_105:
  v77 = v128;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v125);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v126);
  CAutoFreeWLIDResponse::FreeWLIDResponseParams(v78, v4, v5);
  ATL::CStringData::Release((ATL::CStringData *)(v95 - 12));
  return v77;
}

```

## disassembly

```asm
0x18002795c  mov     [rsp-8+arg_0], rbx
0x180027961  mov     [rsp-8+arg_8], rdx
0x180027966  push    rbp
0x180027967  push    rsi
0x180027968  push    rdi
0x180027969  push    r12
0x18002796b  push    r13
0x18002796d  push    r14
0x18002796f  push    r15
0x180027971  lea     rbp, [rsp-200h]
0x180027979  sub     rsp, 300h
0x180027980  mov     r14, rcx
0x180027983  xor     r13d, r13d
0x180027986  mov     esi, r13d
0x180027989  mov     [rbp+230h+arg_18], r13d
0x180027990  mov     [rbp+230h+arg_10], r13d
0x180027997  mov     [rsp+330h+var_2F0], r13
0x18002799c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800279a3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800279aa  mov     rax, [rax+18h]
0x1800279ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279b3  add     rax, 18h
0x1800279b7  mov     [rbp+230h+var_290], rax
0x1800279bb  mov     edi, r13d
0x1800279be  mov     [rsp+330h+var_2D0], r13
0x1800279c3  mov     r15d, r13d
0x1800279c6  mov     [rsp+330h+var_2C8], r13d
0x1800279cb  lea     rcx, [rbp+230h+var_110]; this
0x1800279d2  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800279d7  nop
0x1800279d8  lea     rcx, aCppcrlrequestG_3; "CPPCRLRequest::GetResponse"
0x1800279df  mov     [rbp+230h+var_130], rcx
0x1800279e6  lea     rax, [rbp+230h+arg_10]
0x1800279ed  mov     [rbp+230h+var_128], rax
0x1800279f4  mov     [rbp+230h+var_120], r13
0x1800279fb  mov     [rbp+230h+var_118], r13
0x180027a02  xor     r9d, r9d; unsigned int
0x180027a05  mov     r8d, 0E42h; char *
0x180027a0b  mov     rdx, rcx; char *
0x180027a0e  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180027a15  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180027a1a  nop
0x180027a1b  mov     rcx, [r14+18h]
0x180027a1f  mov     rax, [rcx]
0x180027a22  lea     r8, [rbp+230h+var_290]
0x180027a26  lea     rdx, aCid; "CID"
0x180027a2d  mov     rax, [rax+40h]
0x180027a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a36  mov     ebx, eax
0x180027a38  mov     rcx, [r14+18h]; this
0x180027a3c  call    ?GetIsLinkedHandle@CSingleIdentity@@QEAA_NXZ; CSingleIdentity::GetIsLinkedHandle(void)
0x180027a41  test    al, al
0x180027a43  jz      short loc_180027A70
0x180027a45  mov     rcx, [rbp+230h+var_290]
0x180027a49  cmp     [rcx-10h], r13d
0x180027a4d  jnz     short loc_180027A70
0x180027a4f  mov     dword ptr [rsp+330h+var_310], ebx
0x180027a53  lea     r9, aCouldNotGetCid; "Could not get CID for this ID handle, e"...
0x180027a5a  mov     r8d, 0E4Ch; unsigned int
0x180027a60  lea     rdx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180027a67  lea     ecx, [r13+2]; unsigned __int8
0x180027a6b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180027a70  mov     rcx, [r14+18h]
0x180027a74  mov     rax, [rcx]
0x180027a77  mov     rax, [rax+30h]
0x180027a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a80  neg     al
0x180027a82  sbb     rcx, rcx
0x180027a85  and     ecx, 8
0x180027a88  mov     rax, [r14+18h]
0x180027a8c  mov     r12, [rcx+rax+58h]
0x180027a91  mov     [rbp+230h+var_1F0], r12
0x180027a95  mov     eax, [r14+84h]
0x180027a9c  imul    rcx, rax, 88h; Size
0x180027aa3  call    cs:__imp_malloc
0x180027aa9  mov     rcx, rax; void *
0x180027aac  mov     [rsp+330h+var_2F0], rax
0x180027ab1  test    rax, rax
0x180027ab4  jnz     short loc_180027AC5
0x180027ab6  mov     [rbp+230h+arg_10], 8007000Eh
0x180027ac0  jmp     loc_180028712
0x180027ac5  mov     eax, [r14+84h]
0x180027acc  imul    r8, rax, 88h; Size
0x180027ad3  xor     edx, edx; Val
0x180027ad5  call    memset_0
0x180027ada  lea     rax, [rsp+330h+var_2F0]
0x180027adf  mov     [rsp+330h+var_2D0], rax
0x180027ae4  mov     eax, [r14+84h]
0x180027aeb  mov     [rsp+330h+var_2C8], eax
0x180027aef  xor     r15d, r15d
0x180027af2  mov     r13d, r15d
0x180027af5  cmp     r13d, [r14+84h]
0x180027afc  jnb     loc_1800286D5
0x180027b02  lea     rcx, [rbp+230h+var_1E0]; this
0x180027b06  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x180027b0b  nop
0x180027b0c  mov     edi, r13d
0x180027b0f  lea     rbx, [rdi+rdi*4]
0x180027b13  mov     rdx, [r14+88h]
0x180027b1a  mov     rdx, [rdx+rbx*8]
0x180027b1e  lea     rcx, [rbp+230h+var_260]
0x180027b22  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x180027b27  lea     r8, [rbp+230h+var_1E0]
0x180027b2b  mov     rdx, rax
0x180027b2e  mov     rcx, r12
0x180027b31  call    ?RetrieveToken@CIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCPPCRLToken@@@Z; CIdentityTokenBag::RetrieveToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CPPCRLToken &)
0x180027b36  test    eax, eax
0x180027b38  jz      loc_180028336
0x180027b3e  mov     [rbp+230h+var_2A0], r15
0x180027b42  mov     dword ptr [rbp+230h+Size], r15d
0x180027b46  mov     [rbp+230h+var_298], r15d
0x180027b4a  lea     rcx, [rsp+330h+var_2E0]
0x180027b4f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027b54  nop
0x180027b55  lea     rcx, [rsp+330h+var_2E8]
0x180027b5a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027b5f  nop
0x180027b60  lea     rcx, [rsp+330h+var_2D8]
0x180027b65  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027b6a  nop
0x180027b6b  imul    rdi, 88h
0x180027b72  mov     rcx, [rsp+330h+var_2F0]
0x180027b77  mov     eax, [rbp+230h+var_180]
0x180027b7d  mov     [rdi+rcx], eax
0x180027b80  mov     eax, [rbp+230h+var_17C]
0x180027b86  mov     [rdi+rcx+4], eax
0x180027b8a  lea     rdx, [rbp+230h+var_178]
0x180027b91  lea     rcx, [rsp+330h+var_2E0]
0x180027b96  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180027b9b  lea     r8, [rsp+330h+var_2D8]
0x180027ba0  lea     rdx, [rsp+330h+var_2E8]
0x180027ba5  lea     rcx, [rbp+230h+var_1E0]
0x180027ba9  call    ?GetAuthUrls@CPPCRLToken@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; CPPCRLToken::GetAuthUrls(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180027bae  mov     rdx, [rsp+330h+var_2F0]
0x180027bb3  add     rdx, 38h ; '8'
0x180027bb7  add     rdx, rdi
0x180027bba  lea     r8, [rsp+330h+var_2E0]
0x180027bbf  call    ?CopyResponseString@CPPCRLRequest@@IEAAJPEAPEAGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPPCRLRequest::CopyResponseString(ushort * *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027bc4  mov     [rbp+230h+arg_10], eax
0x180027bca  test    eax, eax
0x180027bcc  js      loc_1800286C6
0x180027bd2  mov     rdx, [rsp+330h+var_2F0]
0x180027bd7  add     rdx, 40h ; '@'
0x180027bdb  add     rdx, rdi
0x180027bde  lea     r8, [rsp+330h+var_2E8]
0x180027be3  call    ?CopyResponseString@CPPCRLRequest@@IEAAJPEAPEAGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPPCRLRequest::CopyResponseString(ushort * *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027be8  mov     [rbp+230h+arg_10], eax
0x180027bee  test    eax, eax
0x180027bf0  js      loc_1800286B7
0x180027bf6  mov     rdx, [rsp+330h+var_2F0]
0x180027bfb  add     rdx, 48h ; 'H'
0x180027bff  add     rdx, rdi
0x180027c02  lea     r8, [rsp+330h+var_2D8]
0x180027c07  call    ?CopyResponseString@CPPCRLRequest@@IEAAJPEAPEAGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPPCRLRequest::CopyResponseString(ushort * *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027c0c  mov     [rbp+230h+arg_10], eax
0x180027c12  test    eax, eax
0x180027c14  js      loc_180028696
0x180027c1a  mov     r15, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x180027c21  mov     rcx, [r14+18h]
0x180027c25  cmp     dword ptr [rcx+2E0h], 0
0x180027c2c  setnz   r12b
0x180027c30  lea     rdx, [rbp+230h+var_250]
0x180027c34  call    ?GetAuthUrl@CSingleIdentity@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CSingleIdentity::GetAuthUrl(void)
0x180027c39  nop
0x180027c3a  or      esi, 1
0x180027c3d  mov     [rbp+230h+arg_18], esi
0x180027c43  mov     rax, [rax]
0x180027c46  cmp     dword ptr [rax-10h], 0
0x180027c4a  jnz     short loc_180027C86
0x180027c4c  lea     rdx, [rbp+230h+var_258]
0x180027c50  mov     rcx, [r14+18h]
0x180027c54  call    ?GetEndAuthUrl@CSingleIdentity@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CSingleIdentity::GetEndAuthUrl(void)
0x180027c59  nop
0x180027c5a  or      esi, 2
0x180027c5d  mov     [rbp+230h+arg_18], esi
0x180027c63  mov     rax, [rax]
0x180027c66  cmp     dword ptr [rax-10h], 0
0x180027c6a  jnz     short loc_180027C86
0x180027c6c  mov     rax, [rsp+330h+var_2E8]
0x180027c71  cmp     dword ptr [rax-10h], 0
0x180027c75  jnz     short loc_180027C86
0x180027c77  mov     rax, [rsp+330h+var_2E0]
0x180027c7c  cmp     dword ptr [rax-10h], 0
0x180027c80  jnz     short loc_180027C86
0x180027c82  xor     eax, eax
0x180027c84  jmp     short loc_180027C88
0x180027c86  mov     al, 1
0x180027c88  mov     rdx, [r14+88h]
0x180027c8f  mov     [rsp+330h+var_300], r12b; bool
0x180027c94  mov     [rsp+330h+var_308], al; bool
0x180027c98  mov     rax, [r14+18h]
0x180027c9c  mov     [rsp+330h+var_310], rax; struct ISingleIdentity *
0x180027ca1  mov     r9, [rsp+330h+var_2F0]
0x180027ca6  mov     r9d, [rdi+r9+4]; int
0x180027cab  mov     r8, [rdx+rbx*8+8]; unsigned __int16 *
0x180027cb0  mov     rdx, [rdx+rbx*8]; unsigned __int16 *
0x180027cb4  lea     rcx, [r15+908h]; this
0x180027cbb  call    ?UpdateNegativeCache@NegativeCacheManager@@QEAAJPEBG0JPEAVISingleIdentity@@_N2@Z; NegativeCacheManager::UpdateNegativeCache(ushort const *,ushort const *,long,ISingleIdentity *,bool,bool)
0x180027cc0  mov     r15d, eax
0x180027cc3  test    sil, 2
0x180027cc7  jz      short loc_180027CD6
0x180027cc9  and     esi, 0FFFFFFFDh
0x180027ccc  lea     rcx, [rbp+230h+var_258]
0x180027cd0  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027cd5  nop
0x180027cd6  test    sil, 1
0x180027cda  jz      short loc_180027CE8
0x180027cdc  and     esi, 0FFFFFFFEh
0x180027cdf  lea     rcx, [rbp+230h+var_250]
0x180027ce3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027ce8  lea     r12, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180027cef  test    r15d, r15d
0x180027cf2  jns     short loc_180027D18
0x180027cf4  lea     rax, aGPppcrlGetnega_0; "g_pPPCRL->GetNegativeCacheManager()->Up"...
0x180027cfb  mov     [rsp+330h+var_310], rax; char *
0x180027d00  mov     r9d, r15d; int
0x180027d03  mov     r8d, 0E78h; unsigned int
0x180027d09  lea     rdx, aCppcrlrequestG_3; "CPPCRLRequest::GetResponse"
0x180027d10  mov     rcx, r12; char *
0x180027d13  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180027d18  mov     rax, [rsp+330h+var_2F0]
0x180027d1d  xor     r15d, r15d
0x180027d20  cmp     [rdi+rax+4], r15d
0x180027d25  jge     short loc_180027D56
0x180027d27  lea     rcx, [rsp+330h+var_2D8]
0x180027d2c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027d31  nop
0x180027d32  lea     rcx, [rsp+330h+var_2E8]
0x180027d37  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027d3c  nop
0x180027d3d  lea     rcx, [rsp+330h+var_2E0]
0x180027d42  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027d47  nop
0x180027d48  lea     rcx, [rbp+230h+Size]; this
0x180027d4c  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x180027d51  jmp     loc_1800284B0
0x180027d56  mov     rax, [r14+88h]
0x180027d5d  test    byte ptr [rax+rbx*8+18h], 8
0x180027d62  jz      loc_180027ECD
0x180027d68  lea     rcx, [rsp+330h+var_2B8]
0x180027d6d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027d72  nop
0x180027d73  mov     rax, [r14+88h]
0x180027d7a  cmp     [rax+rbx*8+10h], r15
0x180027d7f  jnz     loc_180027E40
0x180027d85  mov     [rbp+230h+var_268], r15
0x180027d89  mov     [rbp+230h+var_270], r15
0x180027d8d  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x180027d94  mov     [rbp+230h+var_278], rax
0x180027d98  lea     rcx, [rbp+230h+var_288]
0x180027d9c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027da1  nop
0x180027da2  mov     [rbp+230h+arg_18], r15d
0x180027da9  mov     r8, [r14+88h]
0x180027db0  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x180027db7  add     rcx, 560h
0x180027dbe  mov     qword ptr [rsp+330h+var_308], r15
0x180027dc3  lea     rax, [rbp+230h+var_268]
0x180027dc7  mov     [rsp+330h+var_310], rax
0x180027dcc  lea     r9, [rbp+230h+arg_18]
0x180027dd3  mov     r8, [r8+rbx*8]
0x180027dd7  mov     rdx, [r14+18h]
0x180027ddb  call    ?GetCert@CCertManager@@QEAAJPEAXPEBGAEAKPEAPEBU_CERT_CONTEXT@@PEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CCertManager::GetCert(void *,ushort const *,ulong &,_CERT_CONTEXT const * *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> *)
0x180027de0  mov     [rbp+230h+arg_10], eax
0x180027de6  test    eax, eax
0x180027de8  js      loc_180028542
0x180027dee  mov     rbx, [rbp+230h+var_268]
0x180027df2  mov     rdx, rbx
0x180027df5  lea     rcx, [rbp+230h+var_278]
0x180027df9  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x180027dfe  lea     r8, [rbp+230h+var_288]
0x180027e02  mov     edx, [rbx+10h]; int
0x180027e05  mov     rcx, [rbx+8]; unsigned __int8 *
0x180027e09  call    ?Base64Encode@PassportEncode@@YAJPEBXKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Encode(void const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x180027e0e  mov     [rbp+230h+arg_10], eax
0x180027e14  test    eax, eax
0x180027e16  js      loc_1800284C5
0x180027e1c  mov     rdx, [rbp+230h+var_288]
0x180027e20  lea     rcx, [rsp+330h+var_2B8]
0x180027e25  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180027e2a  nop
0x180027e2b  lea     rcx, [rbp+230h+var_288]
0x180027e2f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027e34  nop
0x180027e35  lea     rcx, [rbp+230h+var_278]; this
0x180027e39  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x180027e3e  jmp     short loc_180027E65
0x180027e40  lea     rdx, [rbp+230h+var_248]
0x180027e44  lea     rcx, [rbp+230h+var_1E0]
0x180027e48  call    ?GetToken@CPPCRLToken@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPPCRLToken::GetToken(void)
0x180027e4d  nop
0x180027e4e  mov     rdx, rax
0x180027e51  lea     rcx, [rsp+330h+var_2B8]
0x180027e56  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180027e5b  nop
0x180027e5c  lea     rcx, [rbp+230h+var_248]
0x180027e60  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180027e65  mov     rbx, [rsp+330h+var_2B8]
0x180027e6a  mov     eax, [rbx-10h]
0x180027e6d  inc     eax
  ... truncated ...
```
