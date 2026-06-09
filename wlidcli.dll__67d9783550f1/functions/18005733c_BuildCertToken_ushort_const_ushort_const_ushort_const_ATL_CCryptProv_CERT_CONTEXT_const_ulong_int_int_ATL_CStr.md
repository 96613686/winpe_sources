# BuildCertToken(ushort const *,ushort const *,ushort const *,ATL::CCryptProv &,_CERT_CONTEXT const *,ulong,int,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18005733c`
- end: `0x180057ddd`
- name: `?BuildCertToken@@YAJPEBG00AEAVCCryptProv@ATL@@PEBU_CERT_CONTEXT@@KHHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z`
- size: `2721`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *, PCCERT_CONTEXT pCertContext, int, int, int, __int64)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ba88`
- `0x18002ba10`

## callees

- `0x180002da0`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000cc9c`
- `0x18000cdac`
- `0x18000d1c8`
- `0x18000d3b4`
- `0x18000d438`
- `0x18000dff0`
- `0x18000e69c`
- `0x18000e728`
- `0x18000e870`
- `0x18000edbc`
- `0x18000fa70`
- `0x180010530`
- `0x180012240`
- `0x180012da8`
- `0x18001d310`
- `0x180023694`
- `0x180053890`
- `0x1800571d4`
- `0x180057248`
- `0x18005733c`
- `0x180057e94`
- `0x180058210`
- `0x180058270`
- `0x180058820`
- `0x18005a3bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x180057d22`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x180057d22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180057c07`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180057c07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057aa9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057a9f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057a9f`
- `CRYPT32!CertGetCertificateChain` at `0x180057542`
- `CRYPT32!CertGetCertificateChain` at `0x180057542`

## string_xrefs

- `0x180057450`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x18005757e`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180057717`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x1800577ad`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180057adf`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180057428`: `BuildCertToken`
- `0x180057710`: `BuildCertToken`
- `0x180057ad8`: `BuildCertToken`
- `0x18005784e`: `<saml:Assertion xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" AssertionID="`
- `0x18005789e`: `" Issuer="http://schemas.microsoft.com/ws/2005/05/identity/issuer/self"`
- `0x180057a3d`: `<saml:Subject><saml:SubjectConfirmation><saml:ConfirmationMethod>urn:oasis:names:tc:SAML:1.0:cm:bearer</saml:ConfirmationMethod><KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">`
- `0x180057a54`: `<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><wsse:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-soap-message-security-1.1#ThumbprintSHA1">`
- `0x180057b43`: `</wsse:KeyIdentifier></wsse:SecurityTokenReference>`
- `0x180057b96`: `<saml:Attribute AttributeName="EmailAddress" AttributeNamespace="http://schemas.microsoft.com/ws/2005/05/identity/claims">`

## pseudocode

```c
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
  int v9; // r12d
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // r14
  signed int v14; // eax
  DWORD cElement; // r15d
  unsigned int v16; // r13d
  PCERT_CHAIN_ELEMENT v17; // r15
  char *v18; // rax
  ATL::CStringData *v19; // r15
  char *BufferSetLength; // rax
  int v21; // r15d
  ATL::CStringData *v22; // r15
  unsigned int v23; // r12d
  __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // r15
  __int64 v27; // rax
  signed int LastError; // eax
  const char *v29; // rcx
  unsigned int v30; // r8d
  ATL::CStringData *v31; // r15
  __int64 v32; // r15
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 *v38; // r15
  __int64 v39; // rax
  __int64 v40; // r8
  int v41; // eax
  __int64 v42; // r15
  unsigned __int8 *v43; // rax
  unsigned int v44; // r15d
  const unsigned __int16 *pChainPara; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *Str; // [rsp+40h] [rbp-C0h] BYREF
  int v48; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  __int64 v54; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h] BYREF
  PCCERT_CONTEXT v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  __int64 *v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  struct _CERT_CHAIN_PARA v62; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v63[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v64; // [rsp+100h] [rbp+0h]
  int v65; // [rsp+108h] [rbp+8h]
  _BYTE v66[8]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v67; // [rsp+118h] [rbp+18h] BYREF
  __int64 v68; // [rsp+120h] [rbp+20h] BYREF
  int v69; // [rsp+128h] [rbp+28h]
  __int128 v70; // [rsp+130h] [rbp+30h] BYREF
  int v71; // [rsp+140h] [rbp+40h]
  _QWORD v72[4]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v73; // [rsp+170h] [rbp+70h]
  void *Block; // [rsp+190h] [rbp+90h] BYREF
  char v75; // [rsp+198h] [rbp+98h] BYREF
  PCCERT_CHAIN_CONTEXT pvData[2]; // [rsp+220h] [rbp+120h] BYREF
  int v77; // [rsp+230h] [rbp+130h]

  v60 = a4;
  v58 = a3;
  v57 = a2;
  v59 = a1;
  v56 = pCertContext;
  v61 = a9;
  v9 = 0;
  v48 = 0;
  memset(v63, 0, sizeof(v63));
  v64 = 0;
  v65 = 10;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v66);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v67);
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 2;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v52);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v53);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v54);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v55);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&Str);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v50);
  ATL::CTime::GetTickCount(pcbData);
  v72[0] = "BuildCertToken";
  v72[1] = &v48;
  v72[2] = 0;
  v72[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
    "BuildCertToken",
    (const char *)0xEA,
    0,
    pChainPara);
  ATL::CSimpleStringT<unsigned short,0>::Truncate(a9, 0);
  GetFormattedTime(&v52, pcbData);
  GetFormattedTime(&v53, pcbData);
  *(_QWORD *)pcbData += 300LL;
  GetFormattedTime(&v54, pcbData);
  GetAssertionId(&v55);
  ATL::CSimpleStringT<char,0>::PrepareWrite(&Str, 12000);
  v10 = v52;
  v11 = v53;
  v12 = v54;
  v13 = v55;
  if ( !a7 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v51);
    pcbData[0] = ATL::Base64EncodeGetRequiredLength(pCertContext->cbCertEncoded, 0);
    BufferSetLength = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(&v51, pcbData[0]);
    v21 = ATL::Base64Encode(
            pCertContext->pbCertEncoded,
            pCertContext->cbCertEncoded,
            BufferSetLength,
            (int *)pcbData,
            0);
    ATL::CSimpleStringT<char,0>::ReleaseBuffer(&v51, pcbData[0]);
    if ( v21 )
    {
      ATL::CSimpleStringT<char,0>::SetString(&v50, "<X509Data>", 10);
      ATL::CSimpleStringT<char,0>::Append(&v50, "<X509Certificate>", 17);
      v22 = (ATL::CStringData *)(v51 - 24);
      ATL::CSimpleStringT<char,0>::Append(&v50, v51, *(unsigned int *)(v51 - 24 + 8));
      ATL::CSimpleStringT<char,0>::Append(&v50, "</X509Certificate>", 18);
      ATL::CSimpleStringT<char,0>::Append(&v50, "</X509Data>", 11);
      ATL::CStringData::Release(v22);
LABEL_19:
      ATL::CSimpleStringT<char,0>::Append(
        &Str,
        "<saml:Assertion xmlns:saml=\"urn:oasis:names:tc:SAML:1.0:assertion\" AssertionID=\"",
        80);
      ATL::CSimpleStringT<char,0>::Append(&Str, v13, *(unsigned int *)(v13 - 16));
      ATL::CSimpleStringT<char,0>::Append(&Str, "\" IssueInstant=\"", 16);
      ATL::CSimpleStringT<char,0>::Append(&Str, v10, *(unsigned int *)(v10 - 16));
      ATL::CSimpleStringT<char,0>::Append(
        &Str,
        "\" Issuer=\"http://schemas.microsoft.com/ws/2005/05/identity/issuer/self\"",
        71);
      ATL::CSimpleStringT<char,0>::Append(&Str, " MajorVersion=\"1\"", 17);
      ATL::CSimpleStringT<char,0>::Append(&Str, " MinorVersion=\"1\">", 18);
      v23 = -1;
      v24 = v57;
      if ( v57 )
      {
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)(v57 + 2 * v25) );
        if ( v25 )
        {
          ATL::CSimpleStringT<char,0>::Append(&Str, "<saml:Advice>", 13);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&Str, v24);
          ATL::CSimpleStringT<char,0>::Append(&Str, "</saml:Advice>", 14);
        }
      }
      ATL::CSimpleStringT<char,0>::Append(&Str, "<saml:Conditions ", 17);
      ATL::CSimpleStringT<char,0>::Append(&Str, "NotBefore=\"", 11);
      ATL::CSimpleStringT<char,0>::Append(&Str, v11, *(unsigned int *)(v11 - 16));
      ATL::CSimpleStringT<char,0>::Append(&Str, "\" NotOnOrAfter=\"", 16);
      ATL::CSimpleStringT<char,0>::Append(&Str, v12, *(unsigned int *)(v12 - 16));
      ATL::CSimpleStringT<char,0>::Append(&Str, "\">", 2);
      v26 = v58;
      if ( v58 )
      {
        v27 = -1;
        do
          ++v27;
        while ( *(_WORD *)(v58 + 2 * v27) );
        if ( v27 )
        {
          ATL::CSimpleStringT<char,0>::Append(&Str, "<saml:AudienceRestriction><saml:Audience>", 41);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(&Str, v26);
          ATL::CSimpleStringT<char,0>::Append(&Str, "</saml:Audience></saml:AudienceRestriction>", 43);
        }
      }
      ATL::CSimpleStringT<char,0>::Append(&Str, "</saml:Conditions>", 18);
      ATL::CSimpleStringT<char,0>::Append(&Str, "<saml:AttributeStatement>", 25);
      ATL::CSimpleStringT<char,0>::Append(
        &Str,
        "<saml:Subject><saml:SubjectConfirmation><saml:ConfirmationMethod>urn:oasis:names:tc:SAML:1.0:cm:bearer</saml:Con"
        "firmationMethod><KeyInfo xmlns=\"http://www.w3.org/2000/09/xmldsig#\">",
        180);
      ATL::CSimpleStringT<char,0>::Append(
        &Str,
        "<wsse:SecurityTokenReference xmlns:wsse=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-sec"
        "ext-1.0.xsd\"><wsse:KeyIdentifier ValueType=\"http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-soap-messa"
        "ge-security-1.1#ThumbprintSHA1\">",
        253);
      *(_OWORD *)pvData = 0;
      v77 = 0;
      pcbData[0] = 20;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v51);
      if ( CertGetCertificateContextProperty(v56, 3u, pvData, pcbData) )
        goto LABEL_35;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v48 = LastError;
      if ( LastError >= 0 )
      {
LABEL_35:
        LastError = PassportEncode::Base64Encode((unsigned __int8 *)pvData, pcbData[0]);
        v48 = LastError;
        if ( LastError >= 0 )
        {
          v31 = (ATL::CStringData *)(v51 - 24);
          ATL::CSimpleStringT<char,0>::Append(&Str, v51, *(unsigned int *)(v51 - 24 + 8));
          ATL::CStringData::Release(v31);
          ATL::CSimpleStringT<char,0>::Append(&Str, "</wsse:KeyIdentifier></wsse:SecurityTokenReference>", 51);
          ATL::CSimpleStringT<char,0>::Append(&Str, "</KeyInfo></saml:SubjectConfirmation></saml:Subject>", 52);
          v32 = v59;
          if ( v59 )
          {
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)(v59 + 2 * v33) );
            if ( v33 )
            {
              ATL::CSimpleStringT<char,0>::Append(
                &Str,
                "<saml:Attribute AttributeName=\"EmailAddress\" AttributeNamespace=\"http://schemas.microsoft.com/ws/2005"
                "/05/identity/claims\">",
                122);
              ATL::CSimpleStringT<char,0>::Append(&Str, "<saml:AttributeValue>", 21);
              v34 = *(_QWORD *)ATL::CW2AEX<128>::CW2AEX<128>(&Block, v32);
              if ( v34 )
              {
                v35 = -1;
                do
                  ++v35;
                while ( *(_BYTE *)(v34 + v35) );
              }
              else
              {
                v35 = 0;
              }
              ATL::CSimpleStringT<char,0>::Append(&Str, v34, v35);
              if ( Block != &v75 )
                free(Block);
              ATL::CSimpleStringT<char,0>::Append(&Str, "</saml:AttributeValue></saml:Attribute>", 39);
            }
          }
          ATL::CSimpleStringT<char,0>::Append(&Str, "</saml:AttributeStatement>", 26);
          ATL::CSimpleStringT<char,0>::Append(&Str, "</saml:Assertion>", 17);
          v37 = ATL::CAtlList<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CElementTraits<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>>>::NewNode(
                  v63,
                  Str,
                  v36,
                  *(_QWORD *)&v63[0]);
          if ( *(_QWORD *)&v63[0] )
            *(_QWORD *)(*(_QWORD *)&v63[0] + 8LL) = v37;
          else
            *((_QWORD *)&v63[0] + 1) = v37;
          *(_QWORD *)&v63[0] = v37;
          v38 = v60;
          v39 = *v60;
          *(_QWORD *)&v70 = v56;
          *((_QWORD *)&v70 + 1) = v39;
          if ( v39 )
            ATL::CCryptProv::AddRef((ATL::CCryptProv *)((char *)&v70 + 8));
          v68 = *v38;
          if ( v68 )
            ATL::CCryptProv::AddRef((ATL::CCryptProv *)&v68);
          v71 = a6;
          if ( v50 )
          {
            v40 = -1;
            do
              ++v40;
            while ( *(_BYTE *)(v50 + v40) );
          }
          else
          {
            v40 = 0;
          }
          ATL::CSimpleStringT<char,0>::SetString(v66, v50, v40);
          v41 = CXmlRSASHA1Sig::ComputeSignature((CXmlRSASHA1Sig *)v63);
          v48 = v41;
          if ( v41 >= 0 )
          {
            v42 = v67;
            if ( *((int *)Str - 4) >= 0 )
            {
              v43 = _mbsstr(Str, "</saml:Assertion>");
              if ( v43 )
                v23 = (_DWORD)v43 - (_DWORD)Str;
            }
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Insert(&Str, v23, v42);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              v61,
              Str);
          }
          else if ( a8 && v41 == -2146893790 )
          {
            v48 = -2146434961;
          }
          goto LABEL_67;
        }
        v29 = "hr = PassportEncode::Base64Encode(rgbThumbprint, cbThumbprint, strThumbprint)";
        v30 = 405;
      }
      else
      {
        v29 = "hr = HRESULT_FROM_WIN32(GetLastError())";
        v30 = 403;
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        "BuildCertToken",
        v30,
        LastError,
        v29);
    }
    else
    {
      v48 = -2147197938;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        "BuildCertToken",
        0x151u,
        -2147197938,
        "bRet");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
    goto LABEL_67;
  }
  pvData[1] = 0;
  pvData[0] = (PCCERT_CHAIN_CONTEXT)&SmartPCCERT_CHAIN_CONTEXT::`vftable';
  v73 = 0;
  *(_QWORD *)&v62.cbSize = 32;
  v51 = 0;
  memset(&v62.RequestedUsage, 0, sizeof(v62.RequestedUsage));
  if ( CertGetCertificateChain(0, pCertContext, 0, 0, &v62, 4u, 0, &pvData[1]) )
    goto LABEL_8;
  v14 = GetLastError();
  if ( v14 > 0 )
    v14 = (unsigned __int16)v14 | 0x80070000;
  v48 = v14;
  if ( v14 >= 0 )
  {
LABEL_8:
    cElement = (*pvData[1]->rgpChain)->cElement;
    ATL::CSimpleStringT<char,0>::PrepareWrite(&v50, 2000 * cElement);
    ATL::CSimpleStringT<char,0>::Append(&v50, "<X509Data>", 10);
    if ( cElement == 1 )
      v16 = 1;
    else
      v16 = cElement - 1;
    while ( 1 )
    {
      v17 = (*pvData[1]->rgpChain)->rgpElement[v9];
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v51);
      pcbData[0] = ATL::Base64EncodeGetRequiredLength(v17->pCertContext->cbCertEncoded, 0);
      v18 = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(&v51, pcbData[0]);
      LODWORD(v17) = ATL::Base64Encode(
                       v17->pCertContext->pbCertEncoded,
                       v17->pCertContext->cbCertEncoded,
                       v18,
                       (int *)pcbData,
                       0);
      ATL::CSimpleStringT<char,0>::ReleaseBuffer(&v51, pcbData[0]);
      if ( !(_DWORD)v17 )
        break;
      ATL::CSimpleStringT<char,0>::Append(&v50, "<X509Certificate>", 17);
      v19 = (ATL::CStringData *)(v51 - 24);
      ATL::CSimpleStringT<char,0>::Append(&v50, v51, *(unsigned int *)(v51 - 24 + 8));
      ATL::CSimpleStringT<char,0>::Append(&v50, "</X509Certificate>", 18);
      ATL::CStringData::Release(v19);
      if ( ++v9 >= v16 )
      {
        ATL::CSimpleStringT<char,0>::Append(&v50, "</X509Data>", 11);
        SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT((SmartPCCERT_CHAIN_CONTEXT *)pvData);
        goto LABEL_19;
      }
    }
    v48 = -2147197938;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      "BuildCertToken",
      0x132u,
      -2147197938,
      "bRet");
    ATL::CStringData::Release((ATL::CStringData *)(v51 - 24));
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      "BuildCertToken",
      0x111u,
      v14,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
  SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT((SmartPCCERT_CHAIN_CONTEXT *)pvData);
LABEL_67:
  v44 = v48;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v72);
  ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(Str - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
  CXmlRSASHA1Sig::~CXmlRSASHA1Sig((CXmlRSASHA1Sig *)v63);
  return v44;
}

```

## disassembly

```asm
0x18005733c  mov     [rsp-8+arg_18], rbx
0x180057341  push    rbp
0x180057342  push    rsi
0x180057343  push    rdi
0x180057344  push    r12
0x180057346  push    r13
0x180057348  push    r14
0x18005734a  push    r15
0x18005734c  lea     rbp, [rsp-140h]
0x180057354  sub     rsp, 240h
0x18005735b  mov     rax, cs:__security_cookie
0x180057362  xor     rax, rsp
0x180057365  mov     [rbp+170h+var_38], rax
0x18005736c  mov     [rbp+170h+var_1C0], r9
0x180057370  mov     [rbp+170h+var_1D0], r8
0x180057374  mov     [rbp+170h+var_1D8], rdx
0x180057378  mov     [rbp+170h+var_1C8], rcx
0x18005737c  mov     r15, [rbp+170h+pCertContext]
0x180057383  mov     [rbp+170h+var_1E0], r15
0x180057387  mov     rbx, [rbp+170h+arg_40]
0x18005738e  mov     [rbp+170h+var_1B8], rbx
0x180057392  xor     r12d, r12d
0x180057395  mov     [rsp+270h+var_228], r12d
0x18005739a  xorps   xmm0, xmm0
0x18005739d  movdqa  [rbp+170h+var_190], xmm0
0x1800573a2  xorps   xmm1, xmm1
0x1800573a5  movdqa  [rbp+170h+var_180], xmm1
0x1800573aa  mov     [rbp+170h+var_170], r12
0x1800573ae  mov     [rbp+170h+var_168], 0Ah
0x1800573b5  lea     rcx, [rbp+170h+var_160]
0x1800573b9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800573be  lea     rcx, [rbp+170h+var_158]
0x1800573c2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800573c7  mov     [rbp+170h+var_150], r12
0x1800573cb  mov     [rbp+170h+var_148], r12d
0x1800573cf  xorps   xmm0, xmm0
0x1800573d2  movdqa  [rbp+170h+var_140], xmm0
0x1800573d7  mov     [rbp+170h+var_130], 2
0x1800573de  lea     rcx, [rsp+270h+var_200]
0x1800573e3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800573e8  nop
0x1800573e9  lea     rcx, [rsp+270h+var_1F8]
0x1800573ee  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800573f3  nop
0x1800573f4  lea     rcx, [rbp+170h+var_1F0]
0x1800573f8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800573fd  nop
0x1800573fe  lea     rcx, [rbp+170h+var_1E8]
0x180057402  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180057407  nop
0x180057408  lea     rcx, [rsp+270h+Str]
0x18005740d  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180057412  nop
0x180057413  lea     rcx, [rsp+270h+var_218]
0x180057418  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005741d  nop
0x18005741e  lea     rcx, [rsp+270h+pcbData]
0x180057423  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180057428  lea     r13, aBuildcerttoken; "BuildCertToken"
0x18005742f  mov     [rbp+170h+var_120], r13
0x180057433  lea     rax, [rsp+270h+var_228]
0x180057438  mov     [rbp+170h+var_118], rax
0x18005743c  mov     [rbp+170h+var_110], r12
0x180057440  mov     [rbp+170h+var_108], r12
0x180057444  xor     r9d, r9d; unsigned int
0x180057447  mov     r8d, 0EAh; char *
0x18005744d  mov     rdx, r13; char *
0x180057450  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180057457  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18005745c  nop
0x18005745d  xor     edx, edx
0x18005745f  mov     rcx, rbx
0x180057462  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x180057467  lea     rdx, [rsp+270h+pcbData]
0x18005746c  lea     rcx, [rsp+270h+var_200]
0x180057471  call    ?GetFormattedTime@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAVCTime@2@@Z; GetFormattedTime(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CTime *)
0x180057476  lea     rdx, [rsp+270h+pcbData]
0x18005747b  lea     rcx, [rsp+270h+var_1F8]
0x180057480  call    ?GetFormattedTime@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAVCTime@2@@Z; GetFormattedTime(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CTime *)
0x180057485  add     qword ptr [rsp+270h+pcbData], 12Ch
0x18005748e  lea     rdx, [rsp+270h+pcbData]
0x180057493  lea     rcx, [rbp+170h+var_1F0]
0x180057497  call    ?GetFormattedTime@@YAXAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAVCTime@2@@Z; GetFormattedTime(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CTime *)
0x18005749c  lea     rcx, [rbp+170h+var_1E8]
0x1800574a0  call    ?GetAssertionId@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; GetAssertionId(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800574a5  mov     edx, 2EE0h
0x1800574aa  lea     rcx, [rsp+270h+Str]
0x1800574af  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800574b4  mov     rsi, [rsp+270h+var_200]
0x1800574b9  mov     rbx, [rsp+270h+var_1F8]
0x1800574be  mov     rdi, [rbp+170h+var_1F0]
0x1800574c2  mov     r14, [rbp+170h+var_1E8]
0x1800574c6  cmp     [rbp+170h+arg_30], r12d
0x1800574cd  jz      loc_180057737
0x1800574d3  mov     [rbp+170h+pvData+8], r12
0x1800574da  lea     rax, ??_7SmartPCCERT_CHAIN_CONTEXT@@6B@; const SmartPCCERT_CHAIN_CONTEXT::`vftable'
0x1800574e1  mov     [rbp+170h+pvData], rax
0x1800574e8  xorps   xmm0, xmm0
0x1800574eb  movups  [rbp+170h+var_100], xmm0
0x1800574ef  mov     qword ptr [rbp+170h+var_1B0.cbSize], 20h ; ' '
0x1800574f7  movups  [rsp+270h+var_210], xmm0
0x1800574fc  mov     [rbp+170h+var_1B0.RequestedUsage.dwType], r12d
0x180057500  mov     eax, dword ptr [rbp+170h+var_100+4]
0x180057503  mov     dword ptr [rbp+170h+var_1B0.RequestedUsage+4], eax
0x180057506  mov     [rbp+170h+var_1B0.RequestedUsage.Usage.cUsageIdentifier], r12d
0x18005750a  mov     eax, dword ptr [rsp+270h+var_210+4]
0x18005750e  mov     dword ptr [rbp+170h+var_1B0.RequestedUsage.Usage+4], eax
0x180057511  mov     [rbp+170h+var_1B0.RequestedUsage.Usage.rgpszUsageIdentifier], r12
0x180057515  lea     rax, [rbp+170h+pvData+8]
0x18005751c  mov     [rsp+270h+ppChainContext], rax; ppChainContext
0x180057521  mov     [rsp+270h+pvReserved], r12; pvReserved
0x180057526  mov     [rsp+270h+dwFlags], 4; dwFlags
0x18005752e  lea     rax, [rbp+170h+var_1B0]
0x180057532  mov     [rsp+270h+pChainPara], rax; pChainPara
0x180057537  xor     r9d, r9d; hAdditionalStore
0x18005753a  xor     r8d, r8d; pTime
0x18005753d  mov     rdx, r15; pCertContext
0x180057540  xor     ecx, ecx; hChainEngine
0x180057542  call    cs:__imp_CertGetCertificateChain
0x180057548  test    eax, eax
0x18005754a  jnz     short loc_18005759C
0x18005754c  call    cs:__imp_GetLastError
0x180057552  test    eax, eax
0x180057554  jle     short loc_18005755E
0x180057556  movzx   eax, ax
0x180057559  or      eax, 80070000h
0x18005755e  mov     [rsp+270h+var_228], eax
0x180057562  test    eax, eax
0x180057564  jns     short loc_18005759C
0x180057566  lea     rcx, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x18005756d  mov     [rsp+270h+pChainPara], rcx; char *
0x180057572  mov     r9d, eax; int
0x180057575  mov     r8d, 111h; unsigned int
0x18005757b  mov     rdx, r13; char *
0x18005757e  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180057585  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005758a  nop
0x18005758b  lea     rcx, [rbp+170h+pvData]; this
0x180057592  call    ??1SmartPCCERT_CHAIN_CONTEXT@@UEAA@XZ; SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT(void)
0x180057597  jmp     loc_180057D52
0x18005759c  mov     rax, [rbp+170h+pvData+8]
0x1800575a3  mov     rcx, [rax+10h]
0x1800575a7  mov     rax, [rcx]
0x1800575aa  mov     r15d, [rax+0Ch]
0x1800575ae  imul    edx, r15d, 7D0h
0x1800575b5  lea     rcx, [rsp+270h+var_218]
0x1800575ba  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x1800575bf  mov     r8d, 0Ah
0x1800575c5  lea     rdx, aX509data_0; "<X509Data>"
0x1800575cc  lea     rcx, [rsp+270h+var_218]
0x1800575d1  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x1800575d6  cmp     r15d, 1
0x1800575da  jnz     short loc_1800575E1
0x1800575dc  mov     r13d, r15d
0x1800575df  jmp     short loc_1800575EE
0x1800575e1  lea     r13d, [r15-1]
0x1800575e5  test    r13d, r13d
0x1800575e8  jz      loc_1800576C4
0x1800575ee  mov     rax, [rbp+170h+pvData+8]
0x1800575f5  mov     rcx, [rax+10h]
0x1800575f9  mov     rax, [rcx]
0x1800575fc  mov     ecx, r12d
0x1800575ff  mov     rax, [rax+10h]
0x180057603  mov     r15, [rax+rcx*8]
0x180057607  lea     rcx, [rsp+270h+var_210]
0x18005760c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180057611  nop
0x180057612  mov     rcx, [r15+8]
0x180057616  xor     edx, edx; unsigned int
0x180057618  mov     ecx, [rcx+10h]; int
0x18005761b  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x180057620  mov     [rsp+270h+pcbData], eax
0x180057624  mov     edx, eax
0x180057626  lea     rcx, [rsp+270h+var_210]
0x18005762b  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x180057630  mov     rcx, [r15+8]
0x180057634  mov     dword ptr [rsp+270h+pChainPara], 0; unsigned int
0x18005763c  lea     r9, [rsp+270h+pcbData]; int *
0x180057641  mov     r8, rax; char *
0x180057644  mov     edx, [rcx+10h]; int
0x180057647  mov     rcx, [rcx+8]; unsigned __int8 *
0x18005764b  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x180057650  mov     r15d, eax
0x180057653  mov     edx, [rsp+270h+pcbData]
0x180057657  lea     rcx, [rsp+270h+var_210]
0x18005765c  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x180057661  test    r15d, r15d
0x180057664  jz      loc_1800576F3
0x18005766a  mov     r8d, 11h
0x180057670  lea     rdx, aX509certificat; "<X509Certificate>"
0x180057677  lea     rcx, [rsp+270h+var_218]
0x18005767c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x180057681  mov     rdx, qword ptr [rsp+270h+var_210]
0x180057686  lea     r15, [rdx-18h]
0x18005768a  mov     r8d, [r15+8]
0x18005768e  lea     rcx, [rsp+270h+var_218]
0x180057693  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x180057698  mov     r8d, 12h
0x18005769e  lea     rdx, aX509certificat_0; "</X509Certificate>"
0x1800576a5  lea     rcx, [rsp+270h+var_218]
0x1800576aa  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x1800576af  nop
0x1800576b0  mov     rcx, r15; this
0x1800576b3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800576b8  inc     r12d
0x1800576bb  cmp     r12d, r13d
0x1800576be  jb      loc_1800575EE
0x1800576c4  mov     r8d, 0Bh
0x1800576ca  lea     rdx, aX509data; "</X509Data>"
0x1800576d1  lea     rcx, [rsp+270h+var_218]
0x1800576d6  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x1800576db  nop
0x1800576dc  lea     rcx, [rbp+170h+pvData]; this
0x1800576e3  call    ??1SmartPCCERT_CHAIN_CONTEXT@@UEAA@XZ; SmartPCCERT_CHAIN_CONTEXT::~SmartPCCERT_CHAIN_CONTEXT(void)
0x1800576e8  mov     r13d, 11h
0x1800576ee  jmp     loc_180057848
0x1800576f3  mov     r9d, 80045C0Eh; int
0x1800576f9  mov     [rsp+270h+var_228], r9d
0x1800576fe  lea     rax, aBret; "bRet"
0x180057705  mov     [rsp+270h+pChainPara], rax; char *
0x18005770a  mov     r8d, 132h; unsigned int
0x180057710  lea     rdx, aBuildcerttoken; "BuildCertToken"
0x180057717  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005771e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180057723  nop
0x180057724  mov     rcx, qword ptr [rsp+270h+var_210]
0x180057729  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005772d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057732  jmp     loc_18005758B
0x180057737  lea     rcx, [rsp+270h+var_210]
0x18005773c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180057741  nop
0x180057742  xor     edx, edx; unsigned int
0x180057744  mov     ecx, [r15+10h]; int
0x180057748  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x18005774d  mov     [rsp+270h+pcbData], eax
0x180057751  mov     edx, eax
0x180057753  lea     rcx, [rsp+270h+var_210]
0x180057758  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x18005775d  mov     dword ptr [rsp+270h+pChainPara], r12d; unsigned int
0x180057762  lea     r9, [rsp+270h+pcbData]; int *
0x180057767  mov     r8, rax; char *
0x18005776a  mov     edx, [r15+10h]; int
0x18005776e  mov     rcx, [r15+8]; unsigned __int8 *
0x180057772  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x180057777  mov     r15d, eax
0x18005777a  mov     edx, [rsp+270h+pcbData]
0x18005777e  lea     rcx, [rsp+270h+var_210]
0x180057783  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x180057788  test    r15d, r15d
0x18005778b  jnz     short loc_1800577CD
0x18005778d  mov     r9d, 80045C0Eh; int
0x180057793  mov     [rsp+270h+var_228], r9d
0x180057798  lea     rax, aBret; "bRet"
0x18005779f  mov     [rsp+270h+pChainPara], rax; char *
0x1800577a4  mov     r8d, 151h; unsigned int
0x1800577aa  mov     rdx, r13; char *
0x1800577ad  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800577b4  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800577b9  nop
0x1800577ba  mov     rcx, qword ptr [rsp+270h+var_210]
0x1800577bf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800577c3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800577c8  jmp     loc_180057D52
0x1800577cd  mov     r8d, 0Ah
0x1800577d3  lea     rdx, aX509data_0; "<X509Data>"
0x1800577da  lea     rcx, [rsp+270h+var_218]
0x1800577df  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x1800577e4  mov     r13d, 11h
0x1800577ea  mov     r8d, r13d
0x1800577ed  lea     rdx, aX509certificat; "<X509Certificate>"
0x1800577f4  lea     rcx, [rsp+270h+var_218]
0x1800577f9  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x1800577fe  mov     rdx, qword ptr [rsp+270h+var_210]
0x180057803  lea     r15, [rdx-18h]
0x180057807  mov     r8d, [r15+8]
0x18005780b  lea     rcx, [rsp+270h+var_218]
0x180057810  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x180057815  lea     r8d, [r13+1]
0x180057819  lea     rdx, aX509certificat_0; "</X509Certificate>"
0x180057820  lea     rcx, [rsp+270h+var_218]
0x180057825  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005782a  lea     r8d, [r13-6]
0x18005782e  lea     rdx, aX509data; "</X509Data>"
0x180057835  lea     rcx, [rsp+270h+var_218]
0x18005783a  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005783f  nop
0x180057840  mov     rcx, r15; this
0x180057843  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057848  mov     r8d, 50h ; 'P'
0x18005784e  lea     rdx, aSamlAssertionX; "<saml:Assertion xmlns:saml=\"urn:oasis:"...
0x180057855  lea     rcx, [rsp+270h+Str]
0x18005785a  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x18005785f  mov     r8d, [r14-10h]
0x180057863  mov     rdx, r14
0x180057866  lea     rcx, [rsp+270h+Str]
0x18005786b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::Append(char const *,int)
0x180057870  mov     r8d, 10h
0x180057876  lea     rdx, aIssueinstant; "\" IssueInstant=\""
0x18005787d  lea     rcx, [rsp+270h+Str]
  ... truncated ...
```
