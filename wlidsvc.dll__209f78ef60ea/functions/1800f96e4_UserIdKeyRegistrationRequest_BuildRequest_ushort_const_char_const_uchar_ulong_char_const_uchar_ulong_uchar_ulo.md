# UserIdKeyRegistrationRequest::BuildRequest(ushort const *,char const *,uchar *,ulong,char const *,uchar *,ulong,uchar *,ulong)

- ea: `0x1800f96e4`
- end: `0x1800f9fef`
- name: `?BuildRequest@UserIdKeyRegistrationRequest@@QEAAJPEBGPEBDPEAEK12K2K@Z`
- size: `2315`
- prototype: `__int64 __fastcall(UserIdKeyRegistrationRequest *__hidden this, const unsigned __int16 *, const char *, unsigned __int8 *, unsigned int, const char *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `44`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180067f4c`
- `0x1800be0d0`

## callees

- `0x180009e98`
- `0x18000a36c`
- `0x18000ae44`
- `0x18000c050`
- `0x18000e008`
- `0x18000ed04`
- `0x18000fd04`
- `0x180011f38`
- `0x1800151c4`
- `0x180015430`
- `0x180015fdc`
- `0x1800160a8`
- `0x1800161e0`
- `0x180016500`
- `0x180017410`
- `0x180017830`
- `0x180017af0`
- `0x180017bf0`
- `0x1800191c0`
- `0x18001925c`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001b330`
- `0x18001cf20`
- `0x180021b28`
- `0x1800268d0`
- `0x1800277c0`
- `0x180029d54`
- `0x18002eed0`
- `0x18003a8fc`
- `0x180046aa4`
- `0x1800529b8`
- `0x180079554`
- `0x1800814f8`
- `0x180084374`
- `0x1800a3b60`
- `0x1800a4718`
- `0x1800f96e4`
- `0x1800f9ff8`
- `0x1800fa1d0`
- `0x1800fa368`
- `0x1800fa53c`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800f9aa9`
- `bcrypt!BCryptGenRandom` at `0x1800f9aa9`

## string_xrefs

- `0x1800f9a05`: `<wsu:Timestamp wsu:Id="Timestamp"><wsu:Created>`
- `0x1800f9a44`: `</wsu:Created><wsu:Expires>`
- `0x1800f9886`: `</wsse:BinarySecurityToken>`
- `0x1800f9e18`: `<?xml version="1.0" encoding="UTF-8"?><s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsa="http://www.w3.org/2005/`
- `0x1800f9b36`: `</wssc:Nonce></wssc:DerivedKeyToken>`
- `0x1800f9e29`: `<wsse:Security>`
- `0x1800f9e77`: `</wsse:Security>`
- `0x1800f9dd0`: `<wsse:SecurityTokenReference><wsse:Embedded wsu:Id="DeviceDAToken"><wsse:BinarySecurityToken ValueType="urn:liveid:device" id="DeviceDAToken">`
- `0x1800f986a`: `<wsse:BinarySecurityToken id="LoginProofToken" ValueType="ps:LoginProofToken">`
- `0x1800f9dee`: `</wsse:BinarySecurityToken></wsse:Embedded></wsse:SecurityTokenReference>`
- `0x1800f9805`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\useridkeyregistrationrequest.cpp`
- `0x1800f98ce`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\useridkeyregistrationrequest.cpp`
- `0x1800f9c89`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\useridkeyregistrationrequest.cpp`
- `0x1800f990c`: `hr = GetKeyAttestationXml(pAttestationKeyCert, certSizeBytes, pAttestationClaim, claimSizeBytes, attestationXml)`
- `0x1800f98b4`: `hr = GetPublicKeyXml(pPublicKey, publicKeySizeBytes, publicKeyXml)`
- `0x1800f9b60`: `hr = GetSessionKeyToSign(sessionKey, pDeviceIdentity, authToken)`
- `0x1800f9ccb`: `hr = GetSessionKeyToSign(sessionKey, pDeviceIdentity, authToken)`
- `0x1800f9b19`: `<wssc:DerivedKeyToken wsu:Id="SignKey" Algorithm="%s"><wssc:Nonce>`
- `0x1800f9c6d`: `hr = DeviceIdHelpers::HandleRenewDeviceId( &serviceExecutionContext, g_szStrongAuthAppId, pDeviceIdentity->GetUserType(), 0, pDeviceIdentity, pNewDeviceIdentity, nullptr, nullptr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall UserIdKeyRegistrationRequest::BuildRequest(
        UserIdKeyRegistrationRequest *this,
        const unsigned __int16 *a2,
        const char *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        const char *a6,
        unsigned __int8 *a7,
        unsigned int a8,
        unsigned __int8 *a9,
        unsigned int a10)
{
  char *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // r8
  int PublicKeyXml; // eax
  unsigned int v18; // r8d
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  const char *v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // ebx
  int v26; // ebx
  __int64 v27; // rcx
  int SessionKeyToSign; // eax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rcx
  unsigned int v34; // ebx
  char *v36; // [rsp+20h] [rbp-E0h]
  char *v37; // [rsp+20h] [rbp-E0h]
  int SignatureXml; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  const char *v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __time64_t Time; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h] BYREF
  char *v53; // [rsp+C8h] [rbp-38h] BYREF
  __time64_t v54; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[32]; // [rsp+D8h] [rbp-28h] BYREF
  int *v56[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v57[5]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v58[176]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v59[224]; // [rsp+1F0h] [rbp+F0h] BYREF
  void *Block; // [rsp+2D0h] [rbp+1D0h] BYREF
  UCHAR v61[136]; // [rsp+2D8h] [rbp+1D8h] BYREF
  UCHAR pbBuffer[16]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v63; // [rsp+370h] [rbp+270h]

  SignatureXml = 0;
  Time = 0;
  v54 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  SessionKey::SessionKey((SessionKey *)v55);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  v43 = 0;
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)v58);
  *(_OWORD *)pbBuffer = 0;
  v63 = 0;
  v57[0] = "UserIdKeyRegistrationRequest::BuildRequest";
  v57[1] = &SignatureXml;
  v57[2] = 0;
  v57[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\useridkeyregistrationrequest.cpp",
    "UserIdKeyRegistrationRequest::BuildRequest",
    (const char *)0x35,
    0,
    (const unsigned __int16 *)v36);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v56,
    "UserIdKeyRegistrationRequest::BuildRequest",
    &SignatureXml,
    0xAu,
    &qword_180185298);
  v14 = (char *)this + 40;
  v53 = v14;
  ATL::CSimpleStringT<char,0>::Truncate(v14, 0);
  ATL::CSimpleStringT<char,0>::SetString(&v47, "urn:liveid:SP800-108CTR-HMAC-SHA256");
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v44, 1800);
  ATL::CSimpleStringT<char,0>::Append(
    &v44,
    "<wsse:BinarySecurityToken id=\"LoginProofToken\" ValueType=\"ps:LoginProofToken\">");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v44, a2);
  ATL::CSimpleStringT<char,0>::Append(&v44, "</wsse:BinarySecurityToken>");
  if ( a5 )
  {
    PublicKeyXml = UserIdKeyRegistrationRequest::GetPublicKeyXml(v15, a4, v16, &v52);
    SignatureXml = PublicKeyXml;
    if ( PublicKeyXml < 0 )
    {
      v37 = "hr = GetPublicKeyXml(pPublicKey, publicKeySizeBytes, publicKeyXml)";
      v18 = 74;
LABEL_4:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\useridkeyregistrationrequest.cpp",
        "UserIdKeyRegistrationRequest::BuildRequest",
        v18,
        PublicKeyXml,
        v37);
      goto LABEL_39;
    }
  }
  PublicKeyXml = UserIdKeyRegistrationRequest::GetKeyAttestationXml(v15, a7, a8, a9, a10, &v51);
  SignatureXml = PublicKeyXml;
  if ( PublicKeyXml < 0 )
  {
    v37 = "hr = GetKeyAttestationXml(pAttestationKeyCert, certSizeBytes, pAttestationClaim, claimSizeBytes, attestationXml)";
    v18 = 77;
    goto LABEL_4;
  }
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v40, 1600);
  ATL::CSimpleStringT<char,0>::Append(&v40, "<ps:ManageLoginKeyRequest Id=\"KRR\" version=\"1.0\"><ps:Action>");
  ATL::CSimpleStringT<char,0>::Append(&v40, a3);
  ATL::CSimpleStringT<char,0>::Append(&v40, "</ps:Action>");
  if ( a6 && *a6 )
  {
    ATL::CSimpleStringT<char,0>::Append(&v40, "<ps:ServerKeyIdentifier>");
    ATL::CSimpleStringT<char,0>::Append(&v40, a6);
    ATL::CSimpleStringT<char,0>::Append(&v40, "</ps:ServerKeyIdentifier>");
  }
  ATL::CSimpleStringT<char,0>::Append(&v40, &v52);
  ATL::CSimpleStringT<char,0>::Append(&v40, &v51);
  ATL::CSimpleStringT<char,0>::Append(&v40, "</ps:ManageLoginKeyRequest>");
  Time = *(_QWORD *)ATL::CTime::GetTickCount(&v42);
  Time -= *((int *)CClientConfigDataCacheManager::theConfigDataManager() + 68);
  v54 = Time + 300;
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v41, 150);
  ATL::CSimpleStringT<char,0>::Append(&v41, "<wsu:Timestamp wsu:Id=\"Timestamp\"><wsu:Created>");
  v19 = (_QWORD *)ATL::CTime::FormatGmt(&Time);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v41, *v19);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  ATL::CSimpleStringT<char,0>::Append(&v41, "</wsu:Created><wsu:Expires>");
  v20 = (_QWORD *)ATL::CTime::FormatGmt(&v54);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&v41, *v20);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  ATL::CSimpleStringT<char,0>::Append(&v41, "</wsu:Expires></wsu:Timestamp>");
  PublicKeyXml = BCryptGenRandom(0, pbBuffer, 0x18u, 2u);
  if ( PublicKeyXml > 0 )
    PublicKeyXml = (unsigned __int16)PublicKeyXml | 0x80070000;
  SignatureXml = PublicKeyXml;
  if ( PublicKeyXml < 0 )
  {
    v37 = "hr = HRESULT_FROM_WIN32(::BCryptGenRandom(nullptr, random, sizeof(random), BCRYPT_USE_SYSTEM_PREFERRED_RNG))";
    v18 = 107;
    goto LABEL_4;
  }
  PublicKeyXml = PassportEncode::Base64Encode(pbBuffer, 24);
  SignatureXml = PublicKeyXml;
  if ( PublicKeyXml < 0 )
  {
    v37 = "hr = PassportEncode::Base64Encode(reinterpret_cast<void*>(random), sizeof(random), encodedRandom)";
    v18 = 108;
    goto LABEL_4;
  }
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v46, 170);
  ATL::CSimpleStringT<char,0>::Append(
    &v46,
    "<wssc:DerivedKeyToken wsu:Id=\"SignKey\" Algorithm=\"%s\"><wssc:Nonce>",
    v21);
  ATL::CSimpleStringT<char,0>::Append(&v46, &v50);
  ATL::CSimpleStringT<char,0>::Append(&v46, "</wssc:Nonce></wssc:DerivedKeyToken>");
  PublicKeyXml = UserIdKeyRegistrationRequest::GetSessionKeyToSign(v22, v55, &v43, v58);
  SignatureXml = PublicKeyXml;
  if ( PublicKeyXml < 0 )
  {
    v37 = "hr = GetSessionKeyToSign(sessionKey, pDeviceIdentity, authToken)";
    v18 = 115;
    goto LABEL_4;
  }
  PublicKeyXml = UserIdKeyRegistrationRequest::GetSignatureXml(v23, pbBuffer, v24, v55, &v41, &v40, &v43, &v49, &v47);
  SignatureXml = PublicKeyXml;
  if ( PublicKeyXml == -2147187452 )
  {
    if ( !v43 )
    {
      SignatureXml = -2147188626;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\useridkeyregistrationrequest.cpp",
        "UserIdKeyRegistrationRequest::BuildRequest",
        0x82u,
        -2147188626,
        "pDeviceIdentity != nullptr");
      goto LABEL_39;
    }
    v45 = 0;
    ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v59);
    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 80LL))(v43);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v42,
      L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}");
    v26 = DeviceIdHelpers::HandleRenewDeviceId(
            (unsigned int)v59,
            (unsigned int)&v42,
            v25,
            0,
            (__int64)&v43,
            (__int64)&v45,
            0,
            0);
    SignatureXml = v26;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
    if ( v26 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\useridkeyregistrationrequest.cpp",
        "UserIdKeyRegistrationRequest::BuildRequest",
        0x8Eu,
        v26,
        "hr = DeviceIdHelpers::HandleRenewDeviceId( &serviceExecutionContext, g_szStrongAuthAppId, pDeviceIdentity->GetUs"
        "erType(), 0, pDeviceIdentity, pNewDeviceIdentity, nullptr, nullptr)");
LABEL_24:
      ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v59);
      CAutoRefPtr<CSingleIdentity>::Deinit(&v45);
      goto LABEL_39;
    }
    SessionKeyToSign = UserIdKeyRegistrationRequest::GetSessionKeyToSign(v27, v55, &v43, v58);
    SignatureXml = SessionKeyToSign;
    if ( SessionKeyToSign < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\useridkeyregistrationrequest.cpp",
        "UserIdKeyRegistrationRequest::BuildRequest",
        0x90u,
        SessionKeyToSign,
        "hr = GetSessionKeyToSign(sessionKey, pDeviceIdentity, authToken)");
      goto LABEL_24;
    }
    SignatureXml = UserIdKeyRegistrationRequest::GetSignatureXml(v29, pbBuffer, v30, v55, &v41, &v40, &v43, &v49, &v47);
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v59);
    CAutoRefPtr<CSingleIdentity>::Deinit(&v45);
    PublicKeyXml = SignatureXml;
    v14 = v53;
  }
  if ( PublicKeyXml < 0 )
  {
    v37 = "hr";
    v18 = 158;
    goto LABEL_4;
  }
  if ( v43 )
  {
    v31 = *(_QWORD *)CPPCRLToken::GetToken(v58, &v53);
    Block = v61;
    ATL::CW2AEX<128>::Init(&Block, v31, 65001);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
      &v42,
      Block);
    if ( Block != v61 )
      free(Block);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
    ATL::CSimpleStringT<char,0>::Append(
      &v44,
      "<wsse:SecurityTokenReference><wsse:Embedded wsu:Id=\"DeviceDAToken\"><wsse:BinarySecurityToken ValueType=\"urn:liv"
      "eid:device\" id=\"DeviceDAToken\">");
    ATL::CSimpleStringT<char,0>::Append(&v44, &v42);
    ATL::CSimpleStringT<char,0>::Append(
      &v44,
      "</wsse:BinarySecurityToken></wsse:Embedded></wsse:SecurityTokenReference>");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  }
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v39, 4500);
  ATL::CSimpleStringT<char,0>::Append(
    &v39,
    "<?xml version=\"1.0\" encoding=\"UTF-8\"?><s:Envelope xmlns:s=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:ps=\""
    "http://schemas.microsoft.com/Passport/SoapServices/PPCRL\" xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis"
    "-200401-wss-wssecurity-secext-1.0.xsd\" xmlns:saml=\"urn:oasis:names:tc:SAML:1.0:assertion\" xmlns:wsp=\"http://sche"
    "mas.xmlsoap.org/ws/2004/09/policy\" xmlns:wsu=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-u"
    "tility-1.0.xsd\" xmlns:wsa=\"http://www.w3.org/2005/08/addressing\" xmlns:wssc=\"http://schemas.xmlsoap.org/ws/2005/"
    "02/sc\" xmlns:wst=\"http://schemas.xmlsoap.org/ws/2005/02/trust\"><s:Header>");
  ATL::CSimpleStringT<char,0>::Append(&v39, "<wsse:Security>");
  ATL::CSimpleStringT<char,0>::Append(&v39, &v44);
  ATL::CSimpleStringT<char,0>::Append(&v39, &v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(&v39, v46, v47);
  ATL::CSimpleStringT<char,0>::Append(&v39, &v49);
  ATL::CSimpleStringT<char,0>::Append(&v39, "</wsse:Security>");
  ATL::CSimpleStringT<char,0>::Append(&v39, "</s:Header><s:Body>");
  ATL::CSimpleStringT<char,0>::Append(&v39, &v40);
  ATL::CSimpleStringT<char,0>::Append(&v39, "</s:Body></s:Envelope>");
  ATL::CSimpleStringT<char,0>::operator=(v14, &v39);
  if ( (byte_1801C36C5 & 4) != 0 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
    LOBYTE(v32) = PPTraceShouldRedact();
    if ( (int)RedactSensitiveXMLElements(&v39, &v45, v32) >= 0 )
    {
      ReduceXmlForTracing(&v45);
      if ( (byte_1801C36C5 & 4) != 0 )
        McTemplateU0s_EventWriteTransfer(v33, SOAPRequest, v45);
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  }
LABEL_39:
  v34 = SignatureXml;
  ErrorVerifier::CheckAgainstList((const char *)v56[3], *v56[2], (unsigned __int64)v56[1], v56[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v57);
  CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v58);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v43);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  CBytePtr::Empty((CBytePtr *)v55);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v44);
  return v34;
}

```

## disassembly

```asm
0x1800f96e4  push    rbp
0x1800f96e6  push    rbx
0x1800f96e7  push    rsi
0x1800f96e8  push    rdi
0x1800f96e9  push    r12
0x1800f96eb  push    r13
0x1800f96ed  push    r14
0x1800f96ef  push    r15
0x1800f96f1  lea     rbp, [rsp-288h]
0x1800f96f9  sub     rsp, 388h
0x1800f9700  mov     rax, cs:__security_cookie
0x1800f9707  xor     rax, rsp
0x1800f970a  mov     [rbp+2C0h+var_48], rax
0x1800f9711  mov     r14, r9
0x1800f9714  mov     r13, r8
0x1800f9717  mov     rdi, rdx
0x1800f971a  mov     rbx, rcx
0x1800f971d  mov     rsi, [rbp+2C0h+arg_28]
0x1800f9724  mov     r15, [rbp+2C0h+arg_30]
0x1800f972b  mov     r12, [rbp+2C0h+arg_40]
0x1800f9732  xor     eax, eax
0x1800f9734  mov     [rsp+3C0h+var_370], eax
0x1800f9738  mov     [rbp+2C0h+Time], rax
0x1800f973c  mov     [rbp+2C0h+var_2F0], rax
0x1800f9740  lea     rcx, [rbp+2C0h+var_340]
0x1800f9744  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9749  nop
0x1800f974a  lea     rcx, [rsp+3C0h+var_360]
0x1800f974f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9754  nop
0x1800f9755  lea     rcx, [rbp+2C0h+var_300]
0x1800f9759  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f975e  nop
0x1800f975f  lea     rcx, [rbp+2C0h+var_308]
0x1800f9763  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9768  nop
0x1800f9769  lea     rcx, [rsp+3C0h+var_358]
0x1800f976e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9773  nop
0x1800f9774  lea     rcx, [rbp+2C0h+var_330]
0x1800f9778  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f977d  nop
0x1800f977e  lea     rcx, [rbp+2C0h+var_318]
0x1800f9782  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9787  nop
0x1800f9788  lea     rcx, [rbp+2C0h+var_310]
0x1800f978c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9791  nop
0x1800f9792  lea     rcx, [rsp+3C0h+var_368]
0x1800f9797  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f979c  nop
0x1800f979d  lea     rcx, [rbp+2C0h+var_2E8]; this
0x1800f97a1  call    ??0SessionKey@@QEAA@XZ; SessionKey::SessionKey(void)
0x1800f97a6  nop
0x1800f97a7  lea     rcx, [rbp+2C0h+var_328]
0x1800f97ab  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f97b0  nop
0x1800f97b1  mov     [rsp+3C0h+var_348], 0
0x1800f97ba  lea     rcx, [rbp+2C0h+var_280]; this
0x1800f97be  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x1800f97c3  nop
0x1800f97c4  xorps   xmm0, xmm0
0x1800f97c7  xor     eax, eax
0x1800f97c9  movups  xmmword ptr [rbp+2C0h+pbBuffer], xmm0
0x1800f97d0  mov     [rbp+2C0h+var_50], rax
0x1800f97d7  lea     rcx, aUseridkeyregis_3; "UserIdKeyRegistrationRequest::BuildRequ"...
0x1800f97de  mov     [rbp+2C0h+var_2A8], rcx
0x1800f97e2  lea     rax, [rsp+3C0h+var_370]
0x1800f97e7  mov     [rbp+2C0h+var_2A0], rax
0x1800f97eb  mov     [rbp+2C0h+var_298], 0
0x1800f97f3  mov     [rbp+2C0h+var_290], 0
0x1800f97fb  xor     r9d, r9d; unsigned int
0x1800f97fe  lea     r8d, [r9+35h]; char *
0x1800f9802  mov     rdx, rcx; char *
0x1800f9805  lea     rcx, aOnecoreuapDsEx_39; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f980c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800f9811  nop
0x1800f9812  lea     rax, qword_180185298
0x1800f9819  mov     [rsp+3C0h+var_3A0], rax; int *
0x1800f981e  mov     r9d, 0Ah; unsigned __int64
0x1800f9824  lea     r8, [rsp+3C0h+var_370]; int *
0x1800f9829  lea     rdx, aUseridkeyregis_3; "UserIdKeyRegistrationRequest::BuildRequ"...
0x1800f9830  lea     rcx, [rbp+2C0h+var_2C8]; this
0x1800f9834  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800f9839  nop
0x1800f983a  add     rbx, 28h ; '('
0x1800f983e  mov     [rbp+2C0h+var_2F8], rbx
0x1800f9842  xor     edx, edx
0x1800f9844  mov     rcx, rbx
0x1800f9847  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x1800f984c  lea     rdx, aUrnLiveidSp800_0; "urn:liveid:SP800-108CTR-HMAC-SHA256"
0x1800f9853  lea     rcx, [rbp+2C0h+var_328]
0x1800f9857  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x1800f985c  mov     edx, 708h
0x1800f9861  lea     rcx, [rbp+2C0h+var_340]
0x1800f9865  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800f986a  lea     rdx, aWsseBinarysecu_5; "<wsse:BinarySecurityToken id=\"LoginPro"...
0x1800f9871  lea     rcx, [rbp+2C0h+var_340]
0x1800f9875  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f987a  mov     rdx, rdi
0x1800f987d  lea     rcx, [rbp+2C0h+var_340]
0x1800f9881  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800f9886  lea     rdx, aWsseBinarysecu_1; "</wsse:BinarySecurityToken>"
0x1800f988d  lea     rcx, [rbp+2C0h+var_340]
0x1800f9891  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9896  xor     edi, edi
0x1800f9898  cmp     [rbp+2C0h+arg_20], edi
0x1800f989e  jz      short loc_1800F98DF
0x1800f98a0  lea     r9, [rbp+2C0h+var_300]
0x1800f98a4  mov     rdx, r14
0x1800f98a7  call    ?GetPublicKeyXml@UserIdKeyRegistrationRequest@@AEAAJPEAEKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UserIdKeyRegistrationRequest::GetPublicKeyXml(uchar *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800f98ac  mov     [rsp+3C0h+var_370], eax
0x1800f98b0  test    eax, eax
0x1800f98b2  jns     short loc_1800F98DF
0x1800f98b4  lea     r8, aHrGetpublickey; "hr = GetPublicKeyXml(pPublicKey, public"...
0x1800f98bb  mov     [rsp+3C0h+var_3A0], r8; char *
0x1800f98c0  lea     r8d, [rdi+4Ah]; unsigned int
0x1800f98c4  mov     r9d, eax; int
0x1800f98c7  lea     rdx, aUseridkeyregis_3; "UserIdKeyRegistrationRequest::BuildRequ"...
0x1800f98ce  lea     rcx, aOnecoreuapDsEx_39; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800f98d5  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800f98da  jmp     loc_1800F9F1F
0x1800f98df  lea     rax, [rbp+2C0h+var_308]
0x1800f98e3  mov     [rsp+3C0h+var_398], rax
0x1800f98e8  mov     eax, [rbp+2C0h+arg_48]
0x1800f98ee  mov     dword ptr [rsp+3C0h+var_3A0], eax
0x1800f98f2  mov     r9, r12
0x1800f98f5  mov     r8d, [rbp+2C0h+arg_38]
0x1800f98fc  mov     rdx, r15
0x1800f98ff  call    ?GetKeyAttestationXml@UserIdKeyRegistrationRequest@@AEAAJPEAEK0KAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; UserIdKeyRegistrationRequest::GetKeyAttestationXml(uchar *,ulong,uchar *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800f9904  mov     [rsp+3C0h+var_370], eax
0x1800f9908  test    eax, eax
0x1800f990a  jns     short loc_1800F9920
0x1800f990c  lea     rcx, aHrGetkeyattest; "hr = GetKeyAttestationXml(pAttestationK"...
0x1800f9913  mov     [rsp+3C0h+var_3A0], rcx
0x1800f9918  mov     r8d, 4Dh ; 'M'
0x1800f991e  jmp     short loc_1800F98C4
0x1800f9920  mov     edx, 640h
0x1800f9925  lea     rcx, [rsp+3C0h+var_360]
0x1800f992a  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800f992f  lea     rdx, aPsManagelogink_0; "<ps:ManageLoginKeyRequest Id=\"KRR\" ve"...
0x1800f9936  lea     rcx, [rsp+3C0h+var_360]
0x1800f993b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9940  mov     rdx, r13
0x1800f9943  lea     rcx, [rsp+3C0h+var_360]
0x1800f9948  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f994d  lea     rdx, aPsAction; "</ps:Action>"
0x1800f9954  lea     rcx, [rsp+3C0h+var_360]
0x1800f9959  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f995e  test    rsi, rsi
0x1800f9961  jz      short loc_1800F9997
0x1800f9963  cmp     [rsi], dil
0x1800f9966  jz      short loc_1800F9997
0x1800f9968  lea     rdx, aPsServerkeyide; "<ps:ServerKeyIdentifier>"
0x1800f996f  lea     rcx, [rsp+3C0h+var_360]
0x1800f9974  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9979  mov     rdx, rsi
0x1800f997c  lea     rcx, [rsp+3C0h+var_360]
0x1800f9981  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9986  lea     rdx, aPsServerkeyide_0; "</ps:ServerKeyIdentifier>"
0x1800f998d  lea     rcx, [rsp+3C0h+var_360]
0x1800f9992  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9997  lea     rdx, [rbp+2C0h+var_300]
0x1800f999b  lea     rcx, [rsp+3C0h+var_360]
0x1800f99a0  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800f99a5  lea     rdx, [rbp+2C0h+var_308]
0x1800f99a9  lea     rcx, [rsp+3C0h+var_360]
0x1800f99ae  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800f99b3  lea     rdx, aPsManagelogink_1; "</ps:ManageLoginKeyRequest>"
0x1800f99ba  lea     rcx, [rsp+3C0h+var_360]
0x1800f99bf  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f99c4  lea     rcx, [rsp+3C0h+var_350]
0x1800f99c9  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x1800f99ce  mov     rcx, [rax]
0x1800f99d1  mov     [rbp+2C0h+Time], rcx
0x1800f99d5  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x1800f99da  movsxd  rcx, dword ptr [rax+110h]
0x1800f99e1  mov     rax, [rbp+2C0h+Time]
0x1800f99e5  sub     rax, rcx
0x1800f99e8  mov     [rbp+2C0h+Time], rax
0x1800f99ec  add     rax, 12Ch
0x1800f99f2  mov     [rbp+2C0h+var_2F0], rax
0x1800f99f6  mov     edx, 96h
0x1800f99fb  lea     rcx, [rsp+3C0h+var_358]
0x1800f9a00  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800f9a05  lea     rdx, aWsuTimestampWs; "<wsu:Timestamp wsu:Id=\"Timestamp\"><ws"...
0x1800f9a0c  lea     rcx, [rsp+3C0h+var_358]
0x1800f9a11  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9a16  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x1800f9a1d  lea     rdx, [rsp+3C0h+var_350]
0x1800f9a22  lea     rcx, [rbp+2C0h+Time]; Time
0x1800f9a26  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x1800f9a2b  nop
0x1800f9a2c  mov     rdx, [rax]
0x1800f9a2f  lea     rcx, [rsp+3C0h+var_358]
0x1800f9a34  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800f9a39  nop
0x1800f9a3a  lea     rcx, [rsp+3C0h+var_350]
0x1800f9a3f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9a44  lea     rdx, aWsuCreatedWsuE; "</wsu:Created><wsu:Expires>"
0x1800f9a4b  lea     rcx, [rsp+3C0h+var_358]
0x1800f9a50  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9a55  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x1800f9a5c  lea     rdx, [rsp+3C0h+var_350]
0x1800f9a61  lea     rcx, [rbp+2C0h+var_2F0]; Time
0x1800f9a65  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x1800f9a6a  nop
0x1800f9a6b  mov     rdx, [rax]
0x1800f9a6e  lea     rcx, [rsp+3C0h+var_358]
0x1800f9a73  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x1800f9a78  nop
0x1800f9a79  lea     rcx, [rsp+3C0h+var_350]
0x1800f9a7e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800f9a83  lea     rdx, aWsuExpiresWsuT; "</wsu:Expires></wsu:Timestamp>"
0x1800f9a8a  lea     rcx, [rsp+3C0h+var_358]
0x1800f9a8f  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9a94  mov     esi, 18h
0x1800f9a99  lea     r9d, [rsi-16h]; dwFlags
0x1800f9a9d  mov     r8d, esi; cbBuffer
0x1800f9aa0  lea     rdx, [rbp+2C0h+pbBuffer]; pbBuffer
0x1800f9aa7  xor     ecx, ecx; hAlgorithm
0x1800f9aa9  call    cs:__imp_BCryptGenRandom
0x1800f9aaf  test    eax, eax
0x1800f9ab1  jle     short loc_1800F9ABB
0x1800f9ab3  movzx   eax, ax
0x1800f9ab6  or      eax, 80070000h
0x1800f9abb  mov     [rsp+3C0h+var_370], eax
0x1800f9abf  test    eax, eax
0x1800f9ac1  jns     short loc_1800F9ADA
0x1800f9ac3  lea     rcx, aHrHresultFromW_2; "hr = HRESULT_FROM_WIN32(::BCryptGenRand"...
0x1800f9aca  mov     [rsp+3C0h+var_3A0], rcx
0x1800f9acf  mov     r8d, 6Bh ; 'k'
0x1800f9ad5  jmp     loc_1800F98C4
0x1800f9ada  lea     r8, [rbp+2C0h+var_310]
0x1800f9ade  mov     edx, esi; int
0x1800f9ae0  lea     rcx, [rbp+2C0h+pbBuffer]; unsigned __int8 *
0x1800f9ae7  call    ?Base64Encode@PassportEncode@@YAJPEBXKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Encode(void const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800f9aec  mov     [rsp+3C0h+var_370], eax
0x1800f9af0  test    eax, eax
0x1800f9af2  jns     short loc_1800F9B0B
0x1800f9af4  lea     rcx, aHrPassportenco_36; "hr = PassportEncode::Base64Encode(reint"...
0x1800f9afb  mov     [rsp+3C0h+var_3A0], rcx
0x1800f9b00  mov     r8d, 6Ch ; 'l'
0x1800f9b06  jmp     loc_1800F98C4
0x1800f9b0b  mov     edx, 0AAh
0x1800f9b10  lea     rcx, [rbp+2C0h+var_330]
0x1800f9b14  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800f9b19  lea     rdx, aWsscDerivedkey_1; "<wssc:DerivedKeyToken wsu:Id=\"SignKey"...
0x1800f9b20  lea     rcx, [rbp+2C0h+var_330]
0x1800f9b24  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9b29  lea     rdx, [rbp+2C0h+var_310]
0x1800f9b2d  lea     rcx, [rbp+2C0h+var_330]
0x1800f9b31  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1800f9b36  lea     rdx, aWsscNonceWsscD; "</wssc:Nonce></wssc:DerivedKeyToken>"
0x1800f9b3d  lea     rcx, [rbp+2C0h+var_330]
0x1800f9b41  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1800f9b46  lea     r9, [rbp+2C0h+var_280]
0x1800f9b4a  lea     r8, [rsp+3C0h+var_348]
0x1800f9b4f  lea     rdx, [rbp+2C0h+var_2E8]
0x1800f9b53  call    ?GetSessionKeyToSign@UserIdKeyRegistrationRequest@@AEAAJAEAVSessionKey@@AEAV?$CAutoRefPtr@VCSingleIdentity@@@@AEAVCPPCRLToken@@@Z; UserIdKeyRegistrationRequest::GetSessionKeyToSign(SessionKey &,CAutoRefPtr<CSingleIdentity> &,CPPCRLToken &)
0x1800f9b58  mov     [rsp+3C0h+var_370], eax
0x1800f9b5c  test    eax, eax
0x1800f9b5e  jns     short loc_1800F9B77
0x1800f9b60  lea     rcx, aHrGetsessionke_0; "hr = GetSessionKeyToSign(sessionKey, pD"...
0x1800f9b67  mov     [rsp+3C0h+var_3A0], rcx
0x1800f9b6c  mov     r8d, 73h ; 's'
0x1800f9b72  jmp     loc_1800F98C4
0x1800f9b77  lea     rax, [rbp+2C0h+var_328]
0x1800f9b7b  mov     [rsp+3C0h+var_380], rax
0x1800f9b80  lea     rax, [rbp+2C0h+var_318]
0x1800f9b84  mov     [rsp+3C0h+var_388], rax
0x1800f9b89  lea     rax, [rsp+3C0h+var_348]
0x1800f9b8e  mov     [rsp+3C0h+var_390], rax
0x1800f9b93  lea     rax, [rsp+3C0h+var_360]
0x1800f9b98  mov     [rsp+3C0h+var_398], rax
0x1800f9b9d  lea     rax, [rsp+3C0h+var_358]
0x1800f9ba2  mov     [rsp+3C0h+var_3A0], rax
0x1800f9ba7  lea     r9, [rbp+2C0h+var_2E8]
0x1800f9bab  lea     rdx, [rbp+2C0h+pbBuffer]
0x1800f9bb2  call    ?GetSignatureXml@UserIdKeyRegistrationRequest@@AEAAJPEAEKAEAVSessionKey@@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@2AEAV?$CAutoRefPtr@VCSingleIdentity@@@@AEAV34@4@Z; UserIdKeyRegistrationRequest::GetSignatureXml(uchar *,ulong,SessionKey &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,CAutoRefPtr<CSingleIdentity> &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800f9bb7  mov     [rsp+3C0h+var_370], eax
0x1800f9bbb  cmp     eax, 80048504h
0x1800f9bc0  jnz     loc_1800F9D44
0x1800f9bc6  cmp     [rsp+3C0h+var_348], rdi
0x1800f9bcb  jnz     short loc_1800F9BEF
0x1800f9bcd  mov     r9d, 8004806Eh
0x1800f9bd3  mov     [rsp+3C0h+var_370], r9d
0x1800f9bd8  lea     rax, aPdeviceidentit; "pDeviceIdentity != nullptr"
0x1800f9bdf  mov     [rsp+3C0h+var_3A0], rax
0x1800f9be4  mov     r8d, 82h
0x1800f9bea  jmp     loc_1800F98C7
0x1800f9bef  mov     [rbp+2C0h+var_338], rdi
0x1800f9bf3  lea     rcx, [rbp+2C0h+var_1D0]; this
0x1800f9bfa  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800f9bff  nop
0x1800f9c00  mov     rcx, [rsp+3C0h+var_348]
0x1800f9c05  mov     rax, [rcx]
0x1800f9c08  mov     rax, [rax+50h]
0x1800f9c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c11  mov     ebx, eax
  ... truncated ...
```
