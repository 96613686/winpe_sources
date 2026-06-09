# BuildCertToken(ushort const *,ushort const *,ushort const *,ATL::CCryptProv &,_CERT_CONTEXT const *,ulong,int,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18011112c`
- end: `0x1801118eb`
- name: `?BuildCertToken@@YAJPEBG00AEAVCCryptProv@ATL@@PEBU_CERT_CONTEXT@@KHHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z`
- size: `1983`
- prototype: `__int64 __fastcall(int, int, int, int, PCCERT_CONTEXT pCertContext, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cec54`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x18001353c`
- `0x1800151c4`
- `0x1800160a8`
- `0x180016500`
- `0x180017410`
- `0x180017830`
- `0x180017af0`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180026c18`
- `0x180037358`
- `0x1800378c0`
- `0x180039178`
- `0x180039be0`
- `0x1800406f0`
- `0x180043244`
- `0x180046aa4`
- `0x1800814f8`
- `0x18008b4ac`
- `0x1800a3b60`
- `0x1800a4718`
- `0x1800d0780`
- `0x180110f8c`
- `0x180110fcc`
- `0x18011112c`
- `0x180111a00`
- `0x180111d3c`
- `0x1801120a4`
- `0x180115c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011160c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180111303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011160c`
- `CRYPT32!CertGetCertificateChain` at `0x1801112f9`
- `CRYPT32!CertGetCertificateChain` at `0x1801112f9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1801115fe`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1801115fe`

## string_xrefs

- `0x180111228`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111335`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111642`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180111682`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x1801114fe`: `<ps:AssertionFormat xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL">EId</ps:AssertionFormat>`
- `0x1801116e7`: `</wsse:KeyIdentifier></wsse:SecurityTokenReference>`
- `0x180111200`: `BuildCertToken`
- `0x18011163b`: `BuildCertToken`
- `0x18011167b`: `BuildCertToken`
- `0x18011147b`: `<saml:Assertion xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" AssertionID="`
- `0x1801114ba`: `" Issuer="http://schemas.microsoft.com/ws/2005/05/identity/issuer/self"`
- `0x1801115b4`: `<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><wsse:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-soap-message-security-1.1#ThumbprintSHA1">`
- `0x1801115a3`: `<saml:Subject><saml:SubjectConfirmation><saml:ConfirmationMethod>urn:oasis:names:tc:SAML:1.0:cm:bearer</saml:ConfirmationMethod><KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">`
- `0x180111721`: `<saml:Attribute AttributeName="EmailAddress" AttributeNamespace="http://schemas.microsoft.com/ws/2005/05/identity/claims">`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall BuildCertToken(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        PCCERT_CONTEXT pCertContext,
        int a6,
        int a7,
        int a8,
        __int64 a9)
{
  int v11; // esi
  signed int LastError; // eax
  DWORD cElement; // ebx
  unsigned int v14; // edi
  PCERT_CHAIN_ELEMENT v15; // rbx
  char *BufferSetLength; // rax
  signed int v17; // eax
  const char *v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // rax
  const char **v21; // rax
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rbx
  unsigned int v27; // eax
  unsigned int v28; // ebx
  const unsigned __int16 *pChainPara; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  struct _CERT_CHAIN_PARA v40; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-30h]
  int v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v46; // [rsp+F0h] [rbp-10h] BYREF
  int v47; // [rsp+F8h] [rbp-8h]
  __int128 v48; // [rsp+100h] [rbp+0h] BYREF
  int v49; // [rsp+110h] [rbp+10h]
  _QWORD v50[4]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v51; // [rsp+140h] [rbp+40h]
  void *Block; // [rsp+160h] [rbp+60h] BYREF
  char v53; // [rsp+168h] [rbp+68h] BYREF
  PCCERT_CHAIN_CONTEXT pvData[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v55; // [rsp+200h] [rbp+100h]

  v11 = 0;
  v32 = 0;
  memset(v41, 0, sizeof(v41));
  v42 = 0;
  v43 = 10;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 2;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v34);
  ATL::CTime::GetTickCount(pcbData);
  v50[0] = "BuildCertToken";
  v50[1] = &v32;
  v50[2] = 0;
  v50[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
    "BuildCertToken",
    (const char *)0xEA,
    0,
    pChainPara);
  ATL::CSimpleStringT<unsigned short,0>::Truncate(a9, 0);
  GetFormattedTime(&v39, pcbData);
  GetFormattedTime(&v38, pcbData);
  *(_QWORD *)pcbData += 300LL;
  GetFormattedTime(&v37, pcbData);
  GetAssertionId(&v36);
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v31, 12000);
  pvData[1] = 0;
  pvData[0] = (PCCERT_CHAIN_CONTEXT)&SmartPCCERT_CHAIN_CONTEXT::`vftable';
  v51 = 0;
  *(_QWORD *)&v40.cbSize = 32;
  v35 = 0;
  memset(&v40.RequestedUsage, 0, sizeof(v40.RequestedUsage));
  if ( !CertGetCertificateChain(0, pCertContext, 0, 0, &v40, 4u, 0, &pvData[1]) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v32 = LastError;
    if ( LastError < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        "BuildCertToken",
        0x111u,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_6:
      SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT((SmartPCCERT_CHAIN_CONTEXT *)pvData);
      goto LABEL_40;
    }
  }
  cElement = (*pvData[1]->rgpChain)->cElement;
  ATL::CSimpleStringT<char,0>::PrepareWrite(&v34, 2000 * cElement);
  ATL::CSimpleStringT<char,0>::Append(&v34, "<X509Data>");
  v14 = 1;
  if ( cElement != 1 )
    v14 = cElement - 1;
  if ( v14 )
  {
    while ( 1 )
    {
      v15 = (*pvData[1]->rgpChain)->rgpElement[v11];
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
      pcbData[0] = ATL::Base64EncodeGetRequiredLength(v15->pCertContext->cbCertEncoded, 0);
      BufferSetLength = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(&v35, pcbData[0]);
      LODWORD(v15) = ATL::Base64Encode(
                       v15->pCertContext->pbCertEncoded,
                       v15->pCertContext->cbCertEncoded,
                       BufferSetLength,
                       (int *)pcbData,
                       0);
      ATL::CSimpleStringT<char,0>::ReleaseBuffer(&v35, pcbData[0]);
      if ( !(_DWORD)v15 )
        break;
      ATL::CSimpleStringT<char,0>::Append(&v34, "<X509Certificate>");
      ATL::CSimpleStringT<char,0>::Append(&v34, &v35);
      ATL::CSimpleStringT<char,0>::Append(&v34, "</X509Certificate>");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
      if ( ++v11 >= v14 )
        goto LABEL_12;
    }
    v32 = -2147197938;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      "BuildCertToken",
      0x132u,
      -2147197938,
      "bRet");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
    goto LABEL_6;
  }
LABEL_12:
  ATL::CSimpleStringT<char,0>::Append(&v34, "</X509Data>");
  SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT((SmartPCCERT_CHAIN_CONTEXT *)pvData);
  ATL::CSimpleStringT<char,0>::Append(
    &v31,
    "<saml:Assertion xmlns:saml=\"urn:oasis:names:tc:SAML:1.0:assertion\" AssertionID=\"");
  ATL::CSimpleStringT<char,0>::Append(&v31, &v36);
  ATL::CSimpleStringT<char,0>::Append(&v31, "\" IssueInstant=\"");
  ATL::CSimpleStringT<char,0>::Append(&v31, &v39);
  ATL::CSimpleStringT<char,0>::Append(
    &v31,
    "\" Issuer=\"http://schemas.microsoft.com/ws/2005/05/identity/issuer/self\"");
  ATL::CSimpleStringT<char,0>::Append(&v31, " MajorVersion=\"1\"");
  ATL::CSimpleStringT<char,0>::Append(&v31, " MinorVersion=\"1\">");
  ATL::CSimpleStringT<char,0>::Append(&v31, "<saml:Advice>");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(
    &v31,
    L"<ps:AssertionFormat xmlns:ps=\"http://schemas.microsoft.com/Passport/SoapServices/PPCRL\">EId</ps:AssertionFormat>");
  ATL::CSimpleStringT<char,0>::Append(&v31, "</saml:Advice>");
  ATL::CSimpleStringT<char,0>::Append(&v31, "<saml:Conditions ");
  ATL::CSimpleStringT<char,0>::Append(&v31, "NotBefore=\"");
  ATL::CSimpleStringT<char,0>::Append(&v31, &v38);
  ATL::CSimpleStringT<char,0>::Append(&v31, "\" NotOnOrAfter=\"");
  ATL::CSimpleStringT<char,0>::Append(&v31, &v37);
  ATL::CSimpleStringT<char,0>::Append(&v31, "\">");
  ATL::CSimpleStringT<char,0>::Append(&v31, "</saml:Conditions>");
  ATL::CSimpleStringT<char,0>::Append(&v31, "<saml:AttributeStatement>");
  ATL::CSimpleStringT<char,0>::Append(
    &v31,
    "<saml:Subject><saml:SubjectConfirmation><saml:ConfirmationMethod>urn:oasis:names:tc:SAML:1.0:cm:bearer</saml:Confirm"
    "ationMethod><KeyInfo xmlns=\"http://www.w3.org/2000/09/xmldsig#\">");
  ATL::CSimpleStringT<char,0>::Append(
    &v31,
    "<wsse:SecurityTokenReference xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-"
    "1.0.xsd\"><wsse:KeyIdentifier ValueType=\"http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-soap-message-secur"
    "ity-1.1#ThumbprintSHA1\">");
  *(_OWORD *)pvData = 0;
  v55 = 0;
  pcbData[0] = 20;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
  if ( !CertGetCertificateContextProperty(pCertContext, 3u, pvData, pcbData) )
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    v32 = v17;
    if ( v17 < 0 )
    {
      v18 = "hr = HRESULT_FROM_WIN32(GetLastError())";
      v19 = 403;
LABEL_17:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        "BuildCertToken",
        v19,
        v17,
        v18);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
      goto LABEL_40;
    }
  }
  v17 = PassportEncode::Base64Encode((unsigned __int8 *)pvData, pcbData[0]);
  v32 = v17;
  if ( v17 < 0 )
  {
    v18 = "hr = PassportEncode::Base64Encode(rgbThumbprint, cbThumbprint, strThumbprint)";
    v19 = 405;
    goto LABEL_17;
  }
  ATL::CSimpleStringT<char,0>::Append(&v31, &v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
  ATL::CSimpleStringT<char,0>::Append(&v31, "</wsse:KeyIdentifier></wsse:SecurityTokenReference>");
  ATL::CSimpleStringT<char,0>::Append(&v31, "</KeyInfo></saml:SubjectConfirmation></saml:Subject>");
  if ( a1 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(a1 + 2 * v20) );
    if ( v20 )
    {
      ATL::CSimpleStringT<char,0>::Append(
        &v31,
        "<saml:Attribute AttributeName=\"EmailAddress\" AttributeNamespace=\"http://schemas.microsoft.com/ws/2005/05/identity/claims\">");
      ATL::CSimpleStringT<char,0>::Append(&v31, "<saml:AttributeValue>");
      v21 = (const char **)ATL::CW2AEX<128>::CW2AEX<128>(&Block, a1);
      ATL::CSimpleStringT<char,0>::Append(&v31, *v21);
      if ( Block != &v53 )
        free(Block);
      ATL::CSimpleStringT<char,0>::Append(&v31, "</saml:AttributeValue></saml:Attribute>");
    }
  }
  ATL::CSimpleStringT<char,0>::Append(&v31, "</saml:AttributeStatement>");
  ATL::CSimpleStringT<char,0>::Append(&v31, "</saml:Assertion>");
  v23 = ATL::CAtlList<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CElementTraits<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>>>::NewNode(
          v41,
          v31,
          v22,
          *(_QWORD *)&v41[0]);
  if ( *(_QWORD *)&v41[0] )
    *(_QWORD *)(*(_QWORD *)&v41[0] + 8LL) = v23;
  else
    *((_QWORD *)&v41[0] + 1) = v23;
  *(_QWORD *)&v41[0] = v23;
  v24 = *a4;
  *(_QWORD *)&v48 = pCertContext;
  *((_QWORD *)&v48 + 1) = v24;
  if ( v24 )
    ATL::CCryptProv::AddRef((ATL::CCryptProv *)((char *)&v48 + 8));
  v46 = *a4;
  if ( v46 )
    ATL::CCryptProv::AddRef((ATL::CCryptProv *)&v46);
  v49 = a6;
  ATL::CSimpleStringT<char,0>::SetString(&v44, v34);
  v25 = CXmlRSASHA1Sig::ComputeSignature((CXmlRSASHA1Sig *)v41);
  v32 = v25;
  if ( v25 >= 0 )
  {
    v26 = v45;
    v27 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Find(&v31, "</saml:Assertion>", 0);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Insert(&v31, v27, v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a9, v31);
  }
  else if ( a8 && v25 == -2146893790 )
  {
    v32 = -2146434961;
  }
LABEL_40:
  v28 = v32;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v34);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v36);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  CXmlRSASHA1Sig::~CXmlRSASHA1Sig((CXmlRSASHA1Sig *)v41);
  return v28;
}

```

## disassembly

```asm
0x18011112c  push    rbp
0x18011112e  push    rbx
0x18011112f  push    rsi
0x180111130  push    rdi
0x180111131  push    r12
0x180111133  push    r13
0x180111135  push    r14
0x180111137  push    r15
0x180111139  lea     rbp, [rsp-118h]
0x180111141  sub     rsp, 218h
0x180111148  mov     rax, cs:__security_cookie
0x18011114f  xor     rax, rsp
0x180111152  mov     [rbp+150h+var_48], rax
0x180111159  mov     r15, r9
0x18011115c  mov     r14, rcx
0x18011115f  mov     r12, [rbp+150h+pCertContext]
0x180111166  mov     r13, [rbp+150h+arg_40]
0x18011116d  xor     esi, esi
0x18011116f  mov     [rsp+250h+var_208], esi
0x180111173  xorps   xmm0, xmm0
0x180111176  movdqa  [rbp+150h+var_1A0], xmm0
0x18011117b  xorps   xmm1, xmm1
0x18011117e  movdqa  [rbp+150h+var_190], xmm1
0x180111183  mov     [rbp+150h+var_180], rsi
0x180111187  mov     [rbp+150h+var_178], 0Ah
0x18011118e  lea     rcx, [rbp+150h+var_170]
0x180111192  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180111197  lea     rcx, [rbp+150h+var_168]
0x18011119b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111a0  mov     [rbp+150h+var_160], rsi
0x1801111a4  mov     [rbp+150h+var_158], esi
0x1801111a7  xorps   xmm0, xmm0
0x1801111aa  movdqa  [rbp+150h+var_150], xmm0
0x1801111af  mov     [rbp+150h+var_140], 2
0x1801111b6  lea     rcx, [rbp+150h+var_1C8]
0x1801111ba  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111bf  nop
0x1801111c0  lea     rcx, [rbp+150h+var_1D0]
0x1801111c4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111c9  nop
0x1801111ca  lea     rcx, [rsp+250h+var_1D8]
0x1801111cf  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111d4  nop
0x1801111d5  lea     rcx, [rsp+250h+var_1E0]
0x1801111da  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111df  nop
0x1801111e0  lea     rcx, [rsp+250h+var_210]
0x1801111e5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111ea  nop
0x1801111eb  lea     rcx, [rsp+250h+var_1F8]
0x1801111f0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801111f5  nop
0x1801111f6  lea     rcx, [rsp+250h+pcbData]
0x1801111fb  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180111200  lea     rbx, aBuildcerttoken; "BuildCertToken"
0x180111207  mov     [rbp+150h+var_130], rbx
0x18011120b  lea     rax, [rsp+250h+var_208]
0x180111210  mov     [rbp+150h+var_128], rax
0x180111214  mov     [rbp+150h+var_120], rsi
0x180111218  mov     [rbp+150h+var_118], rsi
0x18011121c  xor     r9d, r9d; unsigned int
0x18011121f  mov     r8d, 0EAh; char *
0x180111225  mov     rdx, rbx; char *
0x180111228  lea     rcx, aOnecoreuapDsEx_96; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18011122f  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180111234  nop
0x180111235  xor     edx, edx
0x180111237  mov     rcx, r13
0x18011123a  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18011123f  lea     rdx, [rsp+250h+pcbData]
0x180111244  lea     rcx, [rbp+150h+var_1C8]
0x180111248  call    ?GetFormattedTime@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAVCTime@2@@Z; GetFormattedTime(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CTime *)
0x18011124d  lea     rdx, [rsp+250h+pcbData]
0x180111252  lea     rcx, [rbp+150h+var_1D0]
0x180111256  call    ?GetFormattedTime@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAVCTime@2@@Z; GetFormattedTime(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CTime *)
0x18011125b  add     qword ptr [rsp+250h+pcbData], 12Ch
0x180111264  lea     rdx, [rsp+250h+pcbData]
0x180111269  lea     rcx, [rsp+250h+var_1D8]
0x18011126e  call    ?GetFormattedTime@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAVCTime@2@@Z; GetFormattedTime(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CTime *)
0x180111273  lea     rcx, [rsp+250h+var_1E0]
0x180111278  call    ?GetAssertionId@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; GetAssertionId(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18011127d  mov     edx, 2EE0h
0x180111282  lea     rcx, [rsp+250h+var_210]
0x180111287  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x18011128c  mov     [rbp+150h+pvData+8], rsi
0x180111293  lea     rax, ??_7SmartPCCERT_CHAIN_CONTEXT@@6B@; const SmartPCCERT_CHAIN_CONTEXT::`vftable'
0x18011129a  mov     [rbp+150h+pvData], rax
0x1801112a1  xorps   xmm0, xmm0
0x1801112a4  movups  [rbp+150h+var_110], xmm0
0x1801112a8  mov     qword ptr [rbp+150h+var_1C0.cbSize], 20h ; ' '
0x1801112b0  movups  [rsp+250h+var_1F0], xmm0
0x1801112b5  mov     [rbp+150h+var_1C0.RequestedUsage.dwType], esi
0x1801112b8  mov     eax, dword ptr [rbp+150h+var_110+4]
0x1801112bb  mov     dword ptr [rbp+150h+var_1C0.RequestedUsage+4], eax
0x1801112be  mov     [rbp+150h+var_1C0.RequestedUsage.Usage.cUsageIdentifier], esi
0x1801112c1  mov     eax, dword ptr [rsp+250h+var_1F0+4]
0x1801112c5  mov     dword ptr [rbp+150h+var_1C0.RequestedUsage.Usage+4], eax
0x1801112c8  mov     [rbp+150h+var_1C0.RequestedUsage.Usage.rgpszUsageIdentifier], rsi
0x1801112cc  lea     rax, [rbp+150h+pvData+8]
0x1801112d3  mov     [rsp+250h+ppChainContext], rax; ppChainContext
0x1801112d8  mov     [rsp+250h+pvReserved], rsi; pvReserved
0x1801112dd  mov     [rsp+250h+dwFlags], 4; dwFlags
0x1801112e5  lea     rax, [rbp+150h+var_1C0]
0x1801112e9  mov     [rsp+250h+pChainPara], rax; pChainPara
0x1801112ee  xor     r9d, r9d; hAdditionalStore
0x1801112f1  xor     r8d, r8d; pTime
0x1801112f4  mov     rdx, r12; pCertContext
0x1801112f7  xor     ecx, ecx; hChainEngine
0x1801112f9  call    cs:__imp_CertGetCertificateChain
0x1801112ff  test    eax, eax
0x180111301  jnz     short loc_180111353
0x180111303  call    cs:__imp_GetLastError
0x180111309  test    eax, eax
0x18011130b  jle     short loc_180111315
0x18011130d  movzx   eax, ax
0x180111310  or      eax, 80070000h
0x180111315  mov     [rsp+250h+var_208], eax
0x180111319  test    eax, eax
0x18011131b  jns     short loc_180111353
0x18011131d  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180111324  mov     [rsp+250h+pChainPara], rcx; char *
0x180111329  mov     r9d, eax; int
0x18011132c  mov     r8d, 111h; unsigned int
0x180111332  mov     rdx, rbx; char *
0x180111335  lea     rcx, aOnecoreuapDsEx_96; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18011133c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180111341  nop
0x180111342  lea     rcx, [rbp+150h+pvData]; this
0x180111349  call    ??1SmartPCCERT_CHAIN_CONTEXT@@UEAA@XZ; SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT(void)
0x18011134e  jmp     loc_18011186F
0x180111353  mov     rax, [rbp+150h+pvData+8]
0x18011135a  mov     rcx, [rax+10h]
0x18011135e  mov     rax, [rcx]
0x180111361  mov     ebx, [rax+0Ch]
0x180111364  imul    edx, ebx, 7D0h
0x18011136a  lea     rcx, [rsp+250h+var_1F8]
0x18011136f  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x180111374  lea     rdx, aX509data_0; "<X509Data>"
0x18011137b  lea     rcx, [rsp+250h+var_1F8]
0x180111380  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111385  lea     eax, [rbx-1]
0x180111388  mov     edi, 1
0x18011138d  cmp     ebx, edi
0x18011138f  cmovnz  edi, eax
0x180111392  xor     ebx, ebx
0x180111394  test    edi, edi
0x180111396  jz      loc_18011145D
0x18011139c  mov     rax, [rbp+150h+pvData+8]
0x1801113a3  mov     rcx, [rax+10h]
0x1801113a7  mov     rax, [rcx]
0x1801113aa  mov     ecx, esi
0x1801113ac  mov     rax, [rax+10h]
0x1801113b0  mov     rbx, [rax+rcx*8]
0x1801113b4  lea     rcx, [rsp+250h+var_1F0]
0x1801113b9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801113be  nop
0x1801113bf  mov     rcx, [rbx+8]
0x1801113c3  xor     edx, edx; unsigned int
0x1801113c5  mov     ecx, [rcx+10h]; int
0x1801113c8  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x1801113cd  mov     [rsp+250h+pcbData], eax
0x1801113d1  mov     edx, eax
0x1801113d3  lea     rcx, [rsp+250h+var_1F0]
0x1801113d8  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x1801113dd  mov     rcx, [rbx+8]
0x1801113e1  mov     dword ptr [rsp+250h+pChainPara], 0; unsigned int
0x1801113e9  lea     r9, [rsp+250h+pcbData]; int *
0x1801113ee  mov     r8, rax; char *
0x1801113f1  mov     edx, [rcx+10h]; int
0x1801113f4  mov     rcx, [rcx+8]; unsigned __int8 *
0x1801113f8  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x1801113fd  mov     ebx, eax
0x1801113ff  mov     edx, [rsp+250h+pcbData]
0x180111403  lea     rcx, [rsp+250h+var_1F0]
0x180111408  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x18011140d  test    ebx, ebx
0x18011140f  jz      loc_18011165E
0x180111415  lea     rdx, aX509certificat; "<X509Certificate>"
0x18011141c  lea     rcx, [rsp+250h+var_1F8]
0x180111421  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111426  lea     rdx, [rsp+250h+var_1F0]
0x18011142b  lea     rcx, [rsp+250h+var_1F8]
0x180111430  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x180111435  lea     rdx, aX509certificat_0; "</X509Certificate>"
0x18011143c  lea     rcx, [rsp+250h+var_1F8]
0x180111441  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111446  nop
0x180111447  lea     rcx, [rsp+250h+var_1F0]
0x18011144c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180111451  inc     esi
0x180111453  cmp     esi, edi
0x180111455  jb      loc_18011139C
0x18011145b  xor     ebx, ebx
0x18011145d  lea     rdx, aX509data; "</X509Data>"
0x180111464  lea     rcx, [rsp+250h+var_1F8]
0x180111469  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18011146e  nop
0x18011146f  lea     rcx, [rbp+150h+pvData]; this
0x180111476  call    ??1SmartPCCERT_CHAIN_CONTEXT@@UEAA@XZ; SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT(void)
0x18011147b  lea     rdx, aSamlAssertionX; "<saml:Assertion xmlns:saml=\"urn:oasis:"...
0x180111482  lea     rcx, [rsp+250h+var_210]
0x180111487  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18011148c  lea     rdx, [rsp+250h+var_1E0]
0x180111491  lea     rcx, [rsp+250h+var_210]
0x180111496  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x18011149b  lea     rdx, aIssueinstant; "\" IssueInstant=\""
0x1801114a2  lea     rcx, [rsp+250h+var_210]
0x1801114a7  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801114ac  lea     rdx, [rbp+150h+var_1C8]
0x1801114b0  lea     rcx, [rsp+250h+var_210]
0x1801114b5  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x1801114ba  lea     rdx, aIssuerHttpSche; "\" Issuer=\"http://schemas.microsoft.co"...
0x1801114c1  lea     rcx, [rsp+250h+var_210]
0x1801114c6  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801114cb  lea     rdx, aMajorversion1; " MajorVersion=\"1\""
0x1801114d2  lea     rcx, [rsp+250h+var_210]
0x1801114d7  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801114dc  lea     rdx, aMinorversion1; " MinorVersion=\"1\">"
0x1801114e3  lea     rcx, [rsp+250h+var_210]
0x1801114e8  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801114ed  lea     rdx, aSamlAdvice; "<saml:Advice>"
0x1801114f4  lea     rcx, [rsp+250h+var_210]
0x1801114f9  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801114fe  lea     rdx, aPsAssertionfor; "<ps:AssertionFormat xmlns:ps=\"http://s"...
0x180111505  lea     rcx, [rsp+250h+var_210]
0x18011150a  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x18011150f  lea     rdx, aSamlAdvice_0; "</saml:Advice>"
0x180111516  lea     rcx, [rsp+250h+var_210]
0x18011151b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111520  lea     rdx, aSamlConditions; "<saml:Conditions "
0x180111527  lea     rcx, [rsp+250h+var_210]
0x18011152c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111531  lea     rdx, aNotbefore; "NotBefore=\""
0x180111538  lea     rcx, [rsp+250h+var_210]
0x18011153d  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111542  lea     rdx, [rbp+150h+var_1D0]
0x180111546  lea     rcx, [rsp+250h+var_210]
0x18011154b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x180111550  lea     rdx, aNotonorafter; "\" NotOnOrAfter=\""
0x180111557  lea     rcx, [rsp+250h+var_210]
0x18011155c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111561  lea     rdx, [rsp+250h+var_1D8]
0x180111566  lea     rcx, [rsp+250h+var_210]
0x18011156b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x180111570  lea     rdx, asc_180184330; "\">"
0x180111577  lea     rcx, [rsp+250h+var_210]
0x18011157c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111581  lea     rdx, aSamlConditions_0; "</saml:Conditions>"
0x180111588  lea     rcx, [rsp+250h+var_210]
0x18011158d  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x180111592  lea     rdx, aSamlAttributes; "<saml:AttributeStatement>"
0x180111599  lea     rcx, [rsp+250h+var_210]
0x18011159e  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801115a3  lea     rdx, aSamlSubjectSam; "<saml:Subject><saml:SubjectConfirmation"...
0x1801115aa  lea     rcx, [rsp+250h+var_210]
0x1801115af  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801115b4  lea     rdx, aWsseSecurityto_4; "<wsse:SecurityTokenReference xmlns:wsse"...
0x1801115bb  lea     rcx, [rsp+250h+var_210]
0x1801115c0  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x1801115c5  xorps   xmm0, xmm0
0x1801115c8  xor     eax, eax
0x1801115ca  movups  xmmword ptr [rbp+150h+pvData], xmm0
0x1801115d1  mov     [rbp+150h+var_50], eax
0x1801115d7  mov     [rsp+250h+pcbData], 14h
0x1801115df  lea     rcx, [rsp+250h+var_1F0]
0x1801115e4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1801115e9  nop
0x1801115ea  lea     r9, [rsp+250h+pcbData]; pcbData
0x1801115ef  lea     r8, [rbp+150h+pvData]; pvData
0x1801115f6  mov     edx, 3; dwPropId
0x1801115fb  mov     rcx, r12; pCertContext
0x1801115fe  call    cs:__imp_CertGetCertificateContextProperty
0x180111604  test    eax, eax
0x180111606  jnz     loc_18011169E
0x18011160c  call    cs:__imp_GetLastError
0x180111612  test    eax, eax
0x180111614  jle     short loc_18011161E
0x180111616  movzx   eax, ax
0x180111619  or      eax, 80070000h
0x18011161e  mov     [rsp+250h+var_208], eax
0x180111622  test    eax, eax
0x180111624  jns     short loc_18011169E
0x180111626  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18011162d  mov     r8d, 193h; unsigned int
0x180111633  mov     r9d, eax; int
0x180111636  mov     [rsp+250h+pChainPara], rcx; char *
0x18011163b  lea     rdx, aBuildcerttoken; "BuildCertToken"
0x180111642  lea     rcx, aOnecoreuapDsEx_96; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180111649  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18011164e  nop
0x18011164f  lea     rcx, [rsp+250h+var_1F0]
0x180111654  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180111659  jmp     loc_18011186F
0x18011165e  mov     r9d, 80045C0Eh; int
0x180111664  mov     [rsp+250h+var_208], r9d
0x180111669  lea     rax, aBret; "bRet"
0x180111670  mov     [rsp+250h+pChainPara], rax; char *
0x180111675  mov     r8d, 132h; unsigned int
0x18011167b  lea     rdx, aBuildcerttoken; "BuildCertToken"
0x180111682  lea     rcx, aOnecoreuapDsEx_96; "onecoreuap\\ds\\ext\\live\\identity\\li"...
  ... truncated ...
```
