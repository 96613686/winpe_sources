# CPPCRLRequest::AppendLoginKeyTokenToRequestXml(IServiceExecutionContext *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ulong)

- ea: `0x180024b20`
- end: `0x180025afc`
- name: `?AppendLoginKeyTokenToRequestXml@CPPCRLRequest@@UEAAJPEAVIServiceExecutionContext@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@K@Z`
- size: `4060`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009f00`
- `0x18000a354`
- `0x18000a36c`
- `0x18000ac0c`
- `0x18000c050`
- `0x18000db2c`
- `0x18000e008`
- `0x18000ed04`
- `0x18000ed3c`
- `0x180010fb8`
- `0x180013448`
- `0x180013488`
- `0x1800151c4`
- `0x180015430`
- `0x180015860`
- `0x180015fb0`
- `0x1800160a8`
- `0x18001647c`
- `0x180016500`
- `0x1800167b8`
- `0x1800167e4`
- `0x180017410`
- `0x1800179c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180024b20`
- `0x180026308`
- `0x180026c18`
- `0x1800808f8`
- `0x180080974`
- `0x1800809ec`
- `0x1800814f8`
- `0x18008651c`
- `0x1800a8798`
- `0x1800cdbc0`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800258b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800258b4`

## string_xrefs

- `0x180024b8b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180024d72`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180024dd6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180024f72`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800252ce`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800253c9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800255a8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180025682`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180025766`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180025856`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002588d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002596f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x180024b55`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180024d6b`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180024dcf`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180024f6b`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x1800252c7`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x1800253c2`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x1800255a1`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x18002567b`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x18002575f`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180025886`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180025968`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180025ac6`: `CPPCRLRequest::AppendLoginKeyTokenToRequestXml`
- `0x180024ea8`: `login.live.com`
- `0x1800259d1`: `</wsse:BinarySecurityToken>`
- `0x180024e19`: `hr = ComputeServerKeyId( spUserIdKeyPublic, userIdKeyPublicSizeBytes, serverKeyId)`
- `0x180024fc5`: `hr = LiteCryptUtilities::GetPublicKeyComponents( spTransportKeyPublic, transportKeyPublicSizeBytes, &spExponent, &exponentSizeBytes, &spModulus, &modulusSizeBytes)`
- `0x1800257db`: `hr = pNgcFunctions->NgcSignWithUserIdKeyEx( userIdKeyName, reinterpret_cast<const BYTE*>(jwtToken.GetString()), jwtToken.GetLength() * sizeof(CHAR), m_windowHandle, messageForPinPrompt.GetString(), ngcCredProviderFlags, &spEncryptedJwsPayload, &encryptedJwsPayloadSizeBytes)`
- `0x18002574a`: `hr = GetMessageForPinPrompt( pServiceExecutionContext, m_pIdentity, messageForPinPrompt)`
- `0x1800258fd`: `hr = pNgcFunctions->NgcSignWithUserIdKeySilent( userIdKeyName, ngcTicketToken, reinterpret_cast<const BYTE*>(jwtToken.GetString()), jwtToken.GetLength() * sizeof(CHAR), &spEncryptedJwsPayload, &encryptedJwsPayloadSizeBytes)`
- `0x18002597d`: `<wsse:BinarySecurityToken EncodingType="ps:JWT" ValueType="ps:LoginKeyToken" Id="LoginKeyToken">`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
__int64 __fastcall CPPCRLRequest::AppendLoginKeyTokenToRequestXml(const void **a1, __int64 a2, __int64 a3, int a4)
{
  unsigned __int64 v7; // r15
  PPTraceStatus *v8; // rcx
  PPTraceStatus *v9; // rcx
  bool v10; // zf
  char v11; // al
  __int64 v12; // r14
  __int64 v13; // rbx
  __int64 *v14; // rax
  int v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // rbx
  int v18; // eax
  const char *v19; // rcx
  unsigned int v20; // r8d
  int PublicKeyComponents; // eax
  unsigned __int8 *v22; // rdx
  const char *v23; // rcx
  unsigned int v24; // r8d
  _QWORD *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rax
  _QWORD *v42; // rax
  __int64 (__fastcall *v43)(const void **, __int64 *, unsigned __int8 **); // rdi
  int v44; // eax
  __int64 (__fastcall *v45)(const void **, __int64 *, unsigned __int8 **); // rdi
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rax
  int MessageForPinPrompt; // eax
  const char *v50; // rcx
  unsigned int v51; // r8d
  __int64 v52; // rdi
  __int64 *v53; // rax
  int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int v60; // ebx
  char *v62; // [rsp+20h] [rbp-E0h]
  char *v63; // [rsp+20h] [rbp-E0h]
  char *v64; // [rsp+20h] [rbp-E0h]
  const char *v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66; // [rsp+78h] [rbp-88h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v69; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v70[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v73; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v75; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v76; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v77; // [rsp+D0h] [rbp-30h] BYREF
  int v78; // [rsp+D8h] [rbp-28h]
  int v79; // [rsp+DCh] [rbp-24h]
  unsigned int v80[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v81; // [rsp+E8h] [rbp-18h]
  __int64 v82; // [rsp+F0h] [rbp-10h]
  __int64 v83; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v84; // [rsp+100h] [rbp+0h] BYREF
  __int64 v85; // [rsp+108h] [rbp+8h] BYREF
  __int64 v86; // [rsp+110h] [rbp+10h] BYREF
  __int64 v87; // [rsp+118h] [rbp+18h] BYREF
  LiteCryptUtilities *v88[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v89[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v90; // [rsp+140h] [rbp+40h]
  __int64 v91; // [rsp+148h] [rbp+48h]
  _QWORD v92[3]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int8 *v93[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int8 *v94[3]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v95; // [rsp+198h] [rbp+98h] BYREF
  ATL::CStringData *v96; // [rsp+1A0h] [rbp+A0h]
  _QWORD v97[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v98; // [rsp+1C8h] [rbp+C8h]
  int *v99; // [rsp+1D0h] [rbp+D0h]
  const char *v100; // [rsp+1D8h] [rbp+D8h]
  _QWORD v101[12]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v102; // [rsp+258h] [rbp+158h] BYREF
  int v103; // [rsp+268h] [rbp+168h]

  v103 = a4;
  v102 = 0;
  v101[0] = "CPPCRLRequest::AppendLoginKeyTokenToRequestXml";
  v101[1] = &v102;
  v101[2] = 0;
  v101[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
    "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
    (const char *)0x10AB,
    0,
    (const unsigned __int16 *)v62);
  v97[3] = &qword_18013B048;
  v7 = 11;
  v98 = 11;
  v99 = &v102;
  v100 = "CPPCRLRequest::AppendLoginKeyTokenToRequestXml";
  if ( PPTraceStatus::GetAssertFlag(v8) == 1 || (v10 = PPTraceStatus::GetAssertFlag(v9) == 2, v11 = 0, v10) )
    v11 = 1;
  if ( !v11 )
  {
    v7 = -(__int64)((Microsoft_Windows_LiveIdEnableBits & 0x20) != 0) & 0xB;
    v98 = v7;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 48LL))(a2);
  v96 = (ATL::CStringData *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v101[4] = (char *)v96 + 24;
  v77 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v87 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v86 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v85 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v84 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v83 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v78 = 0;
  v79 = 0;
  v75 = 0;
  memset(v94, 0, sizeof(v94));
  memset(v93, 0, sizeof(v93));
  memset(v92, 0, sizeof(v92));
  v13 = (*(__int64 (__fastcall **)(const void *))(*(_QWORD *)a1[3] + 8LL))(a1[3]);
  v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v67,
          L"ps:ngckn");
  v15 = CIdentityCredentialBag::RetrieveCredential(v13, v14, &v85, 1);
  v102 = v15;
  if ( v15 < 0 )
  {
    v63 = "hr = m_pIdentity->GetCredBag()->RetrieveCredential(PPCRL_CREDTYPE_NGCKEYNAME, userIdKeyName, TRUE)";
    v16 = 4293;
LABEL_8:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      v16,
      v15,
      v63);
    goto LABEL_68;
  }
  LODWORD(v69) = 0;
  *(_QWORD *)v80 = 0;
  v82 = 0;
  v81 = 0;
  v17 = v85;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, unsigned __int8 **))(*(_QWORD *)v12 + 112LL))(
          v12,
          v85,
          v80,
          &v69);
  v102 = v18;
  if ( v18 < 0 )
  {
    v19 = "hr = pNgcFunctions->NgcGetUserIdKeyPublicKey( userIdKeyName, &spUserIdKeyPublic, &userIdKeyPublicSizeBytes)";
    v20 = 4302;
LABEL_12:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      v20,
      v18,
      v19);
LABEL_13:
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v80);
    goto LABEL_68;
  }
  v18 = (*((__int64 (__fastcall **)(const void **, _QWORD, _QWORD, __int64 *))*a1 + 17))(
          a1,
          *(_QWORD *)v80,
          (unsigned int)v69,
          &v87);
  v102 = v18;
  if ( v18 < 0 )
  {
    v19 = "hr = ComputeServerKeyId( spUserIdKeyPublic, userIdKeyPublicSizeBytes, serverKeyId)";
    v20 = 4308;
    goto LABEL_12;
  }
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v80);
  v15 = (*(__int64 (__fastcall **)(const void *, const wchar_t *, __int64 *))(*(_QWORD *)a1[3] + 64LL))(
          a1[3],
          L"CID",
          &v86);
  v102 = v15;
  if ( v15 < 0 )
  {
    v63 = "hr = m_pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_CID, accountCid)";
    v16 = 4312;
    goto LABEL_8;
  }
  if ( !*(_DWORD *)(v86 - 16) )
  {
    v102 = -2147186543;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      0x10DCu,
      -2147186543,
      "hr = PPCRL_E_CREDPROP_NOTFOUND");
    goto LABEL_68;
  }
  v97[1] = 0;
  v97[2] = v86;
  v97[0] = L"login.live.com";
  LODWORD(v74) = 0;
  LODWORD(v73) = 0;
  LODWORD(v69) = 0;
  *(_QWORD *)v80 = 0;
  v82 = 0;
  v81 = 0;
  *(_QWORD *)v89 = 0;
  v91 = 0;
  v90 = 0;
  v70[0] = 0;
  memset(v88, 0, sizeof(v88));
  PublicKeyComponents = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD, int, LiteCryptUtilities **))(*(_QWORD *)v12 + 120LL))(
                          v12,
                          v97,
                          0,
                          0,
                          3,
                          v88);
  v102 = PublicKeyComponents;
  if ( PublicKeyComponents < 0 )
  {
    v23 = "hr = pNgcFunctions->NgcGetSymmetricPopKeyTransportKey( &accountInfo, nullptr, nullptr, keyTypeRequsted, &spTra"
          "nsportKeyPublic, &transportKeyPublicSizeBytes, &spAttestation, &attestationSizeBytes, &spAikCert, &aikCertSize"
          "Bytes, &keyTypeActual)";
    v24 = 4347;
LABEL_22:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      v24,
      PublicKeyComponents,
      v23);
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v88);
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v89);
    goto LABEL_13;
  }
  PublicKeyComponents = LiteCryptUtilities::GetPublicKeyComponents(v88[0], v22, (unsigned int)v89, &v69, v80, &v73, v70);
  v102 = PublicKeyComponents;
  if ( PublicKeyComponents < 0 )
  {
    v23 = "hr = LiteCryptUtilities::GetPublicKeyComponents( spTransportKeyPublic, transportKeyPublicSizeBytes, &spExponen"
          "t, &exponentSizeBytes, &spModulus, &modulusSizeBytes)";
    v24 = 4356;
    goto LABEL_22;
  }
  PublicKeyComponents = (*((__int64 (__fastcall **)(const void **, _QWORD, _QWORD, __int64 *))*a1 + 19))(
                          a1,
                          *(_QWORD *)v89,
                          (unsigned int)v69,
                          &v83);
  v102 = PublicKeyComponents;
  if ( PublicKeyComponents < 0 )
  {
    v23 = "hr = Base64UrlEncodeWithNoPadding(spExponent, exponentSizeBytes, transportKeyExponent)";
    v24 = 4358;
    goto LABEL_22;
  }
  PublicKeyComponents = (*((__int64 (__fastcall **)(const void **, _QWORD, _QWORD, __int64 *))*a1 + 19))(
                          a1,
                          *(_QWORD *)v80,
                          (unsigned int)v73,
                          &v84);
  v102 = PublicKeyComponents;
  if ( PublicKeyComponents < 0 )
  {
    v23 = "hr = Base64UrlEncodeWithNoPadding(spModulus, modulusSizeBytes, transportKeyModulus)";
    v24 = 4359;
    goto LABEL_22;
  }
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v88);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v89);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v80);
  v76 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v25 = (_QWORD *)(*((__int64 (__fastcall **)(const void **, __int64 *))*a1 + 2))(a1, &v67);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
    &v65,
    *v25);
  ATL::CStringData::Release((ATL::CStringData *)(v67 - 24));
  v74 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *(_QWORD *)v70 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v69 = (unsigned __int8 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v73 = (unsigned __int8 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Format(&v76, "http://%s", v65);
  v26 = ATL::operator+(&v71, "{\"typ\":\"JWT\",\"alg\":\"RS256\",\"kid\":\"", &v87);
  v27 = ATL::operator+(&v67, v26, "\"}");
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v74);
  ATL::CSimpleStringT<char,0>::operator=(&v74, v27);
  ATL::CStringData::Release((ATL::CStringData *)(v67 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v71 - 24));
  v28 = ATL::operator+(&v68, "{\"aud\":\"", &v76);
  v29 = ATL::operator+(&v72, v28, "\",\"cnf\":{\"jwk\":{\"kty\":\"RSA\",\"n\":\"");
  v30 = ATL::operator+(&v95, v29, &v84);
  v31 = ATL::operator+(&v66, v30, "\",\"e\":\"");
  v32 = ATL::operator+(&v71, v31, &v83);
  v33 = ATL::operator+(&v67, v32, "\",\"alg\":\"RSA-OAEP\",\"use\":\"enc\"}}");
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(v70);
  ATL::CSimpleStringT<char,0>::operator=(v70, v33);
  ATL::CStringData::Release((ATL::CStringData *)(v67 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v71 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v66 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v95 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v72 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v68 - 24));
  if ( v94[0] )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
    v34 = PassportEncode::Base64Encode(v94[0], v78);
    v102 = v34;
    if ( v34 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
        0x1127u,
        v34,
        "hr = PassportEncode::Base64Encode( spAikCert, aikCertSizeBytes, encodedCert)");
LABEL_32:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
LABEL_33:
      CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v73);
      CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v69);
      CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v70);
      CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v74);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
      goto LABEL_68;
    }
    v35 = ATL::operator+(&v72, ",\"attk\":\"", &v66);
    v36 = ATL::operator+(&v68, v35, "\"");
    ATL::CSimpleStringT<char,0>::Append(v70, v36);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
  }
  if ( v93[0] )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
    v37 = PassportEncode::Base64Encode(v93[0], v79);
    v102 = v37;
    if ( v37 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
        0x1134u,
        v37,
        "hr = PassportEncode::Base64Encode( spAttestation, attestationSizeBytes, encodedClaim)");
      goto LABEL_32;
    }
    v38 = ATL::operator+(&v72, ",\"attb\":\"", &v66);
    v39 = ATL::operator+(&v68, v38, "\"");
    ATL::CSimpleStringT<char,0>::Append(v70, v39);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v67,
    a1 + 19);
  v40 = v67;
  if ( *(_DWORD *)(v67 - 16) )
  {
    v71 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned __int64)"\"}" >= 0x10000 )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v71,
        "\"}");
    else
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        &v71,
        (unsigned __int16)"\"}");
    v66 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned __int64)",\"request_nonce\":\"" >= 0x10000 )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        &v66,
        ",\"request_nonce\":\"");
    else
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        &v66,
        (unsigned __int16)",\"request_nonce\":\"");
    v41 = ATL::operator+(&v72, &v66, &v67);
    v42 = (_QWORD *)ATL::operator+(&v68, v41, &v71);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(v70, *v42);
    ATL::CStringData::Release((ATL::CStringData *)(v68 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v72 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v66 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v71 - 24));
  }
  ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
  v43 = (__int64 (__fastcall *)(const void **, __int64 *, unsigned __int8 **))*((_QWORD *)*a1 + 18);
  v67 = ATL::CSimpleStringT<char,0>::CloneData(v74 - 24) + 24;
  v44 = v43(a1, &v67, &v69);
  v102 = v44;
  if ( v44 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      0x1141u,
      v44,
      "hr = Base64UrlEncodeWithNoPadding(jwtHeader, encodedJwsHeader)");
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v73);
    ATL::CStringData::Release((ATL::CStringData *)(v73 - 24));
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v69);
    ATL::CStringData::Release((ATL::CStringData *)(v69 - 24));
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(v70);
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v70 - 24LL));
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v74);
    ATL::CStringData::Release((ATL::CStringData *)(v74 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v65 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v76 - 24));
    goto LABEL_68;
  }
  v45 = (__int64 (__fastcall *)(const void **, __int64 *, unsigned __int8 **))*((_QWORD *)*a1 + 18);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
    &v67,
    v70);
  v46 = v45(a1, &v67, &v73);
  v102 = v46;
  if ( v46 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      0x1142u,
      v46,
      "hr = Base64UrlEncodeWithNoPadding(jwtPayload, encodedJwsPayload)");
    goto LABEL_33;
  }
  v47 = ATL::operator+(&v72, &v69, ".");
  v48 = ATL::operator+(&v68, v47, &v73);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(&v77, v48);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v73);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v69);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v70);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v74);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  if ( !a1[28] )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
    v52 = (*(__int64 (__fastcall **)(const void *))(*(_QWORD *)a1[3] + 8LL))(a1[3]);
    v53 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v68,
            L"ps:ngcat");
    v54 = CIdentityCredentialBag::RetrieveCredential(v52, v53, &v65, 1);
    v102 = v54;
    if ( v54 >= 0 )
    {
      v55 = _o__wcstoui64(v65, 0, 16);
      v56 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 144LL))(v12, v17, v55);
      v102 = v56;
      if ( v56 >= 0 )
      {
        CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v65);
        goto LABEL_64;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
        0x1174u,
        v56,
        "hr = pNgcFunctions->NgcSignWithUserIdKeySilent( userIdKeyName, ngcTicketToken, reinterpret_cast<const BYTE*>(jwt"
        "Token.GetString()), jwtToken.GetLength() * sizeof(CHAR), &spEncryptedJwsPayload, &encryptedJwsPayloadSizeBytes)");
    }
    else
    {
      LODWORD(v64) = v54;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        0x1168u,
        L"No window handle and no ngc ticket either. hr = 0x%x",
        v64);
      v102 = -2147023496;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
        0x1169u,
        -2147023496,
        "hr = HRESULT_FROM_WIN32(ERROR_INVALID_WINDOW_HANDLE)");
    }
    CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v65);
    goto LABEL_68;
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
  MessageForPinPrompt = GetMessageForPinPrompt(a2, a1[3], &v65);
  v102 = MessageForPinPrompt;
  if ( MessageForPinPrompt < 0 )
  {
    v50 = "hr = GetMessageForPinPrompt( pServiceExecutionContext, m_pIdentity, messageForPinPrompt)";
    v51 = 4431;
LABEL_54:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      v51,
      MessageForPinPrompt,
      v50);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
    goto LABEL_68;
  }
  MessageForPinPrompt = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, const void *, const char *, int, _QWORD *, unsigned int *))(*(_QWORD *)v12 + 136LL))(
                          v12,
                          v17,
                          v77,
                          *(unsigned int *)(v77 - 16),
                          a1[28],
                          v65,
                          v103,
                          v92,
                          &v75);
  v102 = MessageForPinPrompt;
  if ( MessageForPinPrompt < 0 )
  {
    v50 = "hr = pNgcFunctions->NgcSignWithUserIdKeyEx( userIdKeyName, reinterpret_cast<const BYTE*>(jwtToken.GetString())"
          ", jwtToken.GetLength() * sizeof(CHAR), m_windowHandle, messageForPinPrompt.GetString(), ngcCredProviderFlags, "
          "&spEncryptedJwsPayload, &encryptedJwsPayloadSizeBytes)";
    v51 = 4441;
    goto LABEL_54;
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v65);
LABEL_64:
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  v57 = (*((__int64 (__fastcall **)(const void **, _QWORD, _QWORD, __int64 *))*a1 + 19))(a1, v92[0], v75, &v71);
  v102 = v57;
  if ( v57 >= 0 )
  {
    ATL::CSimpleStringT<char,0>::Append(
      a3,
      "<wsse:BinarySecurityToken EncodingType=\"ps:JWT\" ValueType=\"ps:LoginKeyToken\" Id=\"LoginKeyToken\">");
    v58 = ATL::operator+(&v72, &v77, ".");
    v59 = ATL::operator+(&v68, v58, &v71);
    ATL::CSimpleStringT<char,0>::Append(a3, v59);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v72);
    ATL::CSimpleStringT<char,0>::Append(a3, "</wsse:BinarySecurityToken>");
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::AppendLoginKeyTokenToRequestXml",
      0x117Cu,
      v57,
      "hr = Base64UrlEncodeWithNoPadding( spEncryptedJwsPayload, encryptedJwsPayloadSizeBytes, jwsPayload)");
  }
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v71);
LABEL_68:
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 19, 0);
  v60 = v102;
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v92);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v93);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v94);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v83);
  ATL::CStringData::Release((ATL::CStringData *)(v83 - 24));
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v84);
  ATL::CStringData::Release((ATL::CStringData *)(v84 - 24));
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::SetZeroMemory(&v85);
  ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::SetZeroMemory(&v86);
  ATL::CStringData::Release((ATL::CStringData *)(v86 - 24));
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v87);
  ATL::CStringData::Release((ATL::CStringData *)(v87 - 24));
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(&v77);
  ATL::CStringData::Release((ATL::CStringData *)(v77 - 24));
  ATL::CStringData::Release(v96);
  ErrorVerifier::CheckAgainstList("CPPCRLRequest::AppendLoginKeyTokenToRequestXml", v102, v7, &qword_18013B048);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v101);
  return v60;
}

```

## disassembly

```asm
0x180024b20  mov     [rsp-8+arg_0], rbx
0x180024b25  mov     [rsp-8+arg_18], r9d
0x180024b2a  push    rbp
0x180024b2b  push    rsi
0x180024b2c  push    rdi
0x180024b2d  push    r12
0x180024b2f  push    r13
0x180024b31  push    r14
0x180024b33  push    r15
0x180024b35  lea     rbp, [rsp-110h]
0x180024b3d  sub     rsp, 210h
0x180024b44  mov     r12, r8
0x180024b47  mov     r13, rdx
0x180024b4a  mov     rsi, rcx
0x180024b4d  xor     edi, edi
0x180024b4f  mov     [rbp+140h+arg_8], edi
0x180024b55  lea     rbx, aCppcrlrequestA_0; "CPPCRLRequest::AppendLoginKeyTokenToReq"...
0x180024b5c  mov     [rbp+140h+var_60], rbx
0x180024b63  lea     rax, [rbp+140h+arg_8]
0x180024b6a  mov     [rbp+140h+var_58], rax
0x180024b71  mov     [rbp+140h+var_50], rdi
0x180024b78  mov     [rbp+140h+var_48], rdi
0x180024b7f  xor     r9d, r9d; unsigned int
0x180024b82  mov     r8d, 10ABh; char *
0x180024b88  mov     rdx, rbx; char *
0x180024b8b  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180024b92  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180024b97  nop
0x180024b98  lea     rax, qword_18013B048
0x180024b9f  mov     [rbp+140h+var_80], rax
0x180024ba6  lea     r15d, [rdi+0Bh]
0x180024baa  mov     [rbp+140h+var_78], r15
0x180024bb1  lea     rax, [rbp+140h+arg_8]
0x180024bb8  mov     [rbp+140h+var_70], rax
0x180024bbf  mov     [rbp+140h+var_68], rbx
0x180024bc6  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x180024bcb  cmp     eax, 1
0x180024bce  jz      short loc_180024BDD
0x180024bd0  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x180024bd5  cmp     eax, 2
0x180024bd8  mov     al, dil
0x180024bdb  jnz     short loc_180024BDF
0x180024bdd  mov     al, 1
0x180024bdf  test    al, al
0x180024be1  jnz     short loc_180024BFD
0x180024be3  mov     al, cs:Microsoft_Windows_LiveIdEnableBits
0x180024be9  and     al, 20h
0x180024beb  neg     al
0x180024bed  sbb     rax, rax
0x180024bf0  and     rax, r15
0x180024bf3  mov     r15, rax
0x180024bf6  mov     [rbp+140h+var_78], rax
0x180024bfd  mov     rax, [r13+0]
0x180024c01  mov     rcx, r13
0x180024c04  mov     rax, [rax+30h]
0x180024c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c0d  mov     r14, rax
0x180024c10  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024c17  mov     rax, [rcx+18h]
0x180024c1b  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024c22  mov     rcx, rbx
0x180024c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c2a  mov     [rbp+140h+var_A0], rax
0x180024c31  lea     rcx, [rax+18h]
0x180024c35  mov     [rbp+140h+var_40], rcx
0x180024c3c  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024c43  mov     rax, [rcx+18h]
0x180024c47  mov     rcx, rbx
0x180024c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c4f  add     rax, 18h
0x180024c53  mov     [rbp+140h+var_170], rax
0x180024c57  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024c5e  mov     rcx, rbx
0x180024c61  mov     rax, [rax+18h]
0x180024c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c6a  add     rax, 18h
0x180024c6e  mov     [rbp+140h+var_128], rax
0x180024c72  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024c79  mov     rcx, rbx
0x180024c7c  mov     rax, [rax+18h]
0x180024c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c85  add     rax, 18h
0x180024c89  mov     [rbp+140h+var_130], rax
0x180024c8d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024c94  mov     rcx, rbx
0x180024c97  mov     rax, [rax+18h]
0x180024c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ca0  add     rax, 18h
0x180024ca4  mov     [rbp+140h+var_138], rax
0x180024ca8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024caf  mov     rcx, rbx
0x180024cb2  mov     rax, [rax+18h]
0x180024cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cbb  add     rax, 18h
0x180024cbf  mov     [rbp+140h+var_140], rax
0x180024cc3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180024cca  mov     rcx, rbx
0x180024ccd  mov     rax, [rax+18h]
0x180024cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cd6  add     rax, 18h
0x180024cda  mov     [rbp+140h+var_148], rax
0x180024cde  mov     [rbp+140h+var_168], edi
0x180024ce1  mov     [rbp+140h+var_164], edi
0x180024ce4  mov     [rbp+140h+var_180], edi
0x180024ce7  mov     [rbp+140h+var_C0], rdi
0x180024cee  mov     [rbp+140h+var_B0], rdi
0x180024cf5  mov     [rbp+140h+var_B8], rdi
0x180024cfc  mov     [rbp+140h+var_D8], rdi
0x180024d00  mov     [rbp+140h+var_C8], rdi
0x180024d04  mov     [rbp+140h+var_D0], rdi
0x180024d08  mov     [rbp+140h+var_F0], rdi
0x180024d0c  mov     [rbp+140h+var_E0], rdi
0x180024d10  mov     [rbp+140h+var_E8], rdi
0x180024d14  mov     rcx, [rsi+18h]
0x180024d18  mov     rax, [rcx]
0x180024d1b  mov     rax, [rax+8]
0x180024d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d24  mov     rbx, rax
0x180024d27  lea     rdx, aPsNgckn; "ps:ngckn"
0x180024d2e  lea     rcx, [rbp+140h+var_1C0]
0x180024d32  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180024d37  mov     r9d, 1
0x180024d3d  lea     r8, [rbp+140h+var_138]
0x180024d41  mov     rdx, rax
0x180024d44  mov     rcx, rbx
0x180024d47  call    ?RetrieveCredential@CIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@H@Z; CIdentityCredentialBag::RetrieveCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)
0x180024d4c  mov     [rbp+140h+arg_8], eax
0x180024d52  test    eax, eax
0x180024d54  jns     short loc_180024D83
0x180024d56  lea     rdx, aHrMPidentityGe_5; "hr = m_pIdentity->GetCredBag()->Retriev"...
0x180024d5d  mov     [rsp+240h+var_220], rdx; char *
0x180024d62  mov     r8d, 10C5h; unsigned int
0x180024d68  mov     r9d, eax; int
0x180024d6b  lea     rdx, aCppcrlrequestA_0; "CPPCRLRequest::AppendLoginKeyTokenToReq"...
0x180024d72  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180024d79  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180024d7e  jmp     loc_1800259EA
0x180024d83  mov     dword ptr [rbp+140h+var_1B0], edi
0x180024d86  mov     qword ptr [rbp+140h+var_160], rdi
0x180024d8a  mov     [rbp+140h+var_150], rdi
0x180024d8e  mov     [rbp+140h+var_158], rdi
0x180024d92  mov     rax, [r14]
0x180024d95  lea     r9, [rbp+140h+var_1B0]
0x180024d99  lea     r8, [rbp+140h+var_160]
0x180024d9d  mov     rbx, [rbp+140h+var_138]
0x180024da1  mov     rdx, rbx
0x180024da4  mov     rcx, r14
0x180024da7  mov     rax, [rax+70h]
0x180024dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024db0  mov     [rbp+140h+arg_8], eax
0x180024db6  test    eax, eax
0x180024db8  jns     short loc_180024DF1
0x180024dba  lea     rcx, aHrPngcfunction_13; "hr = pNgcFunctions->NgcGetUserIdKeyPubl"...
0x180024dc1  mov     r8d, 10CEh; unsigned int
0x180024dc7  mov     r9d, eax; int
0x180024dca  mov     [rsp+240h+var_220], rcx; char *
0x180024dcf  lea     rdx, aCppcrlrequestA_0; "CPPCRLRequest::AppendLoginKeyTokenToReq"...
0x180024dd6  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180024ddd  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180024de2  nop
0x180024de3  lea     rcx, [rbp+140h+var_160]
0x180024de7  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180024dec  jmp     loc_1800259EA
0x180024df1  mov     rax, [rsi]
0x180024df4  lea     r9, [rbp+140h+var_128]
0x180024df8  mov     r8d, dword ptr [rbp+140h+var_1B0]
0x180024dfc  mov     rdx, qword ptr [rbp+140h+var_160]
0x180024e00  mov     rcx, rsi
0x180024e03  mov     rax, [rax+88h]
0x180024e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e0f  mov     [rbp+140h+arg_8], eax
0x180024e15  test    eax, eax
0x180024e17  jns     short loc_180024E28
0x180024e19  lea     rcx, aHrComputeserve; "hr = ComputeServerKeyId( spUserIdKeyPub"...
0x180024e20  mov     r8d, 10D4h
0x180024e26  jmp     short loc_180024DC7
0x180024e28  lea     rcx, [rbp+140h+var_160]
0x180024e2c  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180024e31  mov     rcx, [rsi+18h]
0x180024e35  mov     rax, [rcx]
0x180024e38  lea     r8, [rbp+140h+var_130]
0x180024e3c  lea     rdx, aCid; "CID"
0x180024e43  mov     rax, [rax+40h]
0x180024e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e4c  mov     [rbp+140h+arg_8], eax
0x180024e52  test    eax, eax
0x180024e54  jns     short loc_180024E6D
0x180024e56  lea     rcx, aHrMPidentityGe_3; "hr = m_pIdentity->GetCredProperty(PPCRL"...
0x180024e5d  mov     [rsp+240h+var_220], rcx
0x180024e62  mov     r8d, 10D8h
0x180024e68  jmp     loc_180024D68
0x180024e6d  mov     rax, [rbp+140h+var_130]
0x180024e71  cmp     [rax-10h], edi
0x180024e74  jnz     short loc_180024E9A
0x180024e76  mov     r9d, 80048891h
0x180024e7c  mov     [rbp+140h+arg_8], r9d
0x180024e83  lea     rax, aHrPpcrlECredpr; "hr = PPCRL_E_CREDPROP_NOTFOUND"
0x180024e8a  mov     [rsp+240h+var_220], rax
0x180024e8f  mov     r8d, 10DCh
0x180024e95  jmp     loc_180024D6B
0x180024e9a  mov     [rbp+140h+var_90], rdi
0x180024ea1  mov     [rbp+140h+var_88], rax
0x180024ea8  lea     rax, aLoginLiveCom; "login.live.com"
0x180024eaf  mov     [rbp+140h+var_98], rax
0x180024eb6  mov     dword ptr [rbp+140h+var_188], edi
0x180024eb9  mov     dword ptr [rbp+140h+var_190], edi
0x180024ebc  mov     dword ptr [rbp+140h+var_1B0], edi
0x180024ebf  mov     qword ptr [rbp+140h+var_160], rdi
0x180024ec3  mov     [rbp+140h+var_150], rdi
0x180024ec7  mov     [rbp+140h+var_158], rdi
0x180024ecb  mov     qword ptr [rbp+140h+var_108], rdi
0x180024ecf  mov     [rbp+140h+var_F8], rdi
0x180024ed3  mov     [rbp+140h+var_100], rdi
0x180024ed7  mov     [rbp+140h+var_1A8], edi
0x180024eda  mov     [rbp+140h+var_120], rdi
0x180024ede  mov     [rbp+140h+var_110], rdi
0x180024ee2  mov     [rbp+140h+var_118], rdi
0x180024ee6  mov     rax, [r14]
0x180024ee9  lea     rcx, [rbp+140h+var_188]
0x180024eed  mov     [rsp+240h+var_1E8], rcx
0x180024ef2  lea     rcx, [rbp+140h+var_168]
0x180024ef6  mov     [rsp+240h+var_1F0], rcx
0x180024efb  lea     rcx, [rbp+140h+var_C0]
0x180024f02  mov     [rsp+240h+var_1F8], rcx
0x180024f07  lea     rcx, [rbp+140h+var_164]
0x180024f0b  mov     [rsp+240h+var_200], rcx
0x180024f10  lea     rcx, [rbp+140h+var_D8]
0x180024f14  mov     [rsp+240h+var_208], rcx
0x180024f19  lea     rcx, [rbp+140h+var_1A8]
0x180024f1d  mov     [rsp+240h+var_210], rcx; unsigned int *
0x180024f22  lea     rcx, [rbp+140h+var_120]
0x180024f26  mov     [rsp+240h+var_218], rcx
0x180024f2b  mov     dword ptr [rsp+240h+var_220], 3
0x180024f33  xor     r9d, r9d
0x180024f36  xor     r8d, r8d
0x180024f39  lea     rdx, [rbp+140h+var_98]
0x180024f40  mov     rcx, r14
0x180024f43  mov     rax, [rax+78h]
0x180024f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f4c  mov     [rbp+140h+arg_8], eax
0x180024f52  test    eax, eax
0x180024f54  jns     short loc_180024F98
0x180024f56  lea     rcx, aHrPngcfunction_9; "hr = pNgcFunctions->NgcGetSymmetricPopK"...
0x180024f5d  mov     r8d, 10FBh; unsigned int
0x180024f63  mov     r9d, eax; int
0x180024f66  mov     [rsp+240h+var_220], rcx; char *
0x180024f6b  lea     rdx, aCppcrlrequestA_0; "CPPCRLRequest::AppendLoginKeyTokenToReq"...
0x180024f72  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180024f79  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180024f7e  nop
0x180024f7f  lea     rcx, [rbp+140h+var_120]
0x180024f83  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180024f88  nop
0x180024f89  lea     rcx, [rbp+140h+var_108]
0x180024f8d  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180024f92  nop
0x180024f93  jmp     loc_180024DE3
0x180024f98  lea     rax, [rbp+140h+var_190]
0x180024f9c  mov     [rsp+240h+var_218], rax; unsigned __int8 **
0x180024fa1  lea     rax, [rbp+140h+var_160]
0x180024fa5  mov     [rsp+240h+var_220], rax; unsigned int *
0x180024faa  lea     r9, [rbp+140h+var_1B0]; unsigned __int8 **
0x180024fae  lea     r8, [rbp+140h+var_108]; unsigned int
0x180024fb2  mov     rcx, [rbp+140h+var_120]; this
0x180024fb6  call    ?GetPublicKeyComponents@LiteCryptUtilities@@YAJPEAEKPEAPEAEPEAK12@Z; LiteCryptUtilities::GetPublicKeyComponents(uchar *,ulong,uchar * *,ulong *,uchar * *,ulong *)
0x180024fbb  mov     [rbp+140h+arg_8], eax
0x180024fc1  test    eax, eax
0x180024fc3  jns     short loc_180024FD4
0x180024fc5  lea     rcx, aHrLitecryptuti_6; "hr = LiteCryptUtilities::GetPublicKeyCo"...
0x180024fcc  mov     r8d, 1104h
0x180024fd2  jmp     short loc_180024F63
0x180024fd4  mov     rax, [rsi]
0x180024fd7  lea     r9, [rbp+140h+var_148]
0x180024fdb  mov     r8d, dword ptr [rbp+140h+var_1B0]
0x180024fdf  mov     rdx, qword ptr [rbp+140h+var_108]
0x180024fe3  mov     rcx, rsi
0x180024fe6  mov     rax, [rax+98h]
0x180024fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff2  mov     [rbp+140h+arg_8], eax
0x180024ff8  test    eax, eax
0x180024ffa  jns     short loc_18002500E
0x180024ffc  lea     rcx, aHrBase64urlenc_2; "hr = Base64UrlEncodeWithNoPadding(spExp"...
0x180025003  mov     r8d, 1106h
0x180025009  jmp     loc_180024F63
0x18002500e  mov     rax, [rsi]
0x180025011  lea     r9, [rbp+140h+var_140]
0x180025015  mov     r8d, dword ptr [rbp+140h+var_190]
0x180025019  mov     rdx, qword ptr [rbp+140h+var_160]
0x18002501d  mov     rcx, rsi
0x180025020  mov     rax, [rax+98h]
0x180025027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002502c  mov     [rbp+140h+arg_8], eax
0x180025032  test    eax, eax
0x180025034  jns     short loc_180025048
0x180025036  lea     rcx, aHrBase64urlenc_1; "hr = Base64UrlEncodeWithNoPadding(spMod"...
0x18002503d  mov     r8d, 1107h
0x180025043  jmp     loc_180024F63
0x180025048  lea     rcx, [rbp+140h+var_120]
0x18002504c  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180025051  nop
  ... truncated ...
```
