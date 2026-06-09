# CDeviceUserAssociation::ParseResponse(char const *,ulong,ulong &)

- ea: `0x1800d1aa0`
- end: `0x1800d1ff6`
- name: `?ParseResponse@CDeviceUserAssociation@@UEAAJPEBDKAEAK@Z`
- size: `1366`
- prototype: `__int64 __fastcall(CDeviceUserAssociation *__hidden this, const char *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000bff0`
- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015430`
- `0x1800167b8`
- `0x18001686c`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001b330`
- `0x18001cf20`
- `0x180021b28`
- `0x18002eed0`
- `0x180039ee8`
- `0x1800406a8`
- `0x1800428e4`
- `0x180044408`
- `0x1800469b8`
- `0x1800513cc`
- `0x18005dc64`
- `0x180062c8c`
- `0x1800d0824`
- `0x1800d1aa0`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800d1db6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800d1db6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1caa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1e51`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1ea2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1f36`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1caa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1e51`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1ea2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1f36`
- `OLEAUT32!__imp_VariantClear` at `0x1800d1fa1`
- `OLEAUT32!__imp_VariantClear` at `0x1800d1fa1`

## string_xrefs

- `0x1800d1afd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800d1bc7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800d1ec5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800d1f1a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800d1f72`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800d1f52`: `SUCCEEDED(hr = CreateDOM(strSoapResponse, k_cvPPCRLSAPINamespaces, pXmlResponse)) && pXmlResponse != nullptr`
- `0x1800d1b2b`: ` xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" xmlns:psf="http://schemas.microsoft.com/Passport/SoapServices/SOAPFault" xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL" xmlns:S="http://www.w3.org/2003/05/soap-envelope"`
- `0x1800d1cb4`: `SUCCEEDED(hr = pXmlResponse->selectSingleNode(CComBSTR("/S:Envelope/S:Body"), &pNode)) && hr != S_FALSE`
- `0x1800d1efa`: `SUCCEEDED(hr = pNode->selectSingleNode(m_deviceErrorCodeXPath, &pErrorNode)) && hr != S_FALSE && pErrorNode != nullptr`
- `0x1800d1df2`: `FAILED(ServiceHr = MapServiceError(bstrErr, SubHr))`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CDeviceUserAssociation::ParseResponse(
        CDeviceUserAssociation *this,
        const char *a2,
        unsigned int a3,
        unsigned int *a4)
{
  int v8; // r14d
  const char *v9; // rax
  int v10; // r9d
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // r8
  const char *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rdi
  ATL::CComBSTR *v19; // rax
  int v20; // eax
  char v21; // bl
  int v22; // eax
  int v23; // eax
  unsigned int v24; // ebx
  CPPCRLBaseRequest *v25; // rcx
  int v26; // eax
  const char *v27; // rax
  int v28; // r9d
  unsigned int v29; // r8d
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // rbx
  ATL::CComBSTR *v32; // rax
  int v33; // ebx
  unsigned int v34; // r8d
  __int64 *v35; // rax
  __int64 v36; // rcx
  char *v38; // [rsp+20h] [rbp-69h]
  char *v39; // [rsp+20h] [rbp-69h]
  CPPCRLBaseRequest *v40; // [rsp+30h] [rbp-59h] BYREF
  __int64 v41; // [rsp+38h] [rbp-51h] BYREF
  __int64 v42; // [rsp+40h] [rbp-49h] BYREF
  BSTR v43; // [rsp+48h] [rbp-41h] BYREF
  __int64 v44; // [rsp+50h] [rbp-39h] BYREF
  __int64 v45; // [rsp+58h] [rbp-31h] BYREF
  BSTR v46; // [rsp+60h] [rbp-29h] BYREF
  __int64 v47; // [rsp+68h] [rbp-21h] BYREF
  __int64 v48; // [rsp+70h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v50[10]; // [rsp+90h] [rbp+7h] BYREF
  int v51; // [rsp+F0h] [rbp+67h] BYREF
  wchar_t *String; // [rsp+F8h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+108h] [rbp+7Fh] BYREF

  LODWORD(String) = 0;
  v51 = 0;
  v8 = 0;
  v50[0] = "CDeviceUserAssociation::ParseResponse";
  v50[1] = &v51;
  v50[2] = 0;
  v50[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
    "CDeviceUserAssociation::ParseResponse",
    (const char *)0x2016,
    0,
    (const unsigned __int16 *)v38);
  v48 = 0;
  v42 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v45);
  pvarg.vt = 0;
  ATL::CComVariant::operator=(
    &pvarg,
    L" xmlns:SOAP=\"http://schemas.xmlsoap.org/soap/envelope/\" xmlns:psf=\"http://schemas.microsoft.com/Passport/SoapServ"
     "ices/SOAPFault\" xmlns:ps=\"http://schemas.microsoft.com/Passport/SoapServices/PPCRL\" xmlns:S=\"http://www.w3.org/"
     "2003/05/soap-envelope\"");
  *((_BYTE *)this + 248) = 1;
  *a4 = 7;
  if ( !a2 )
  {
    v51 = -2147418113;
    v9 = "szResponse != nullptr";
    v10 = -2147418113;
    v11 = 8227;
LABEL_50:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CDeviceUserAssociation::ParseResponse",
      v11,
      v10,
      v9);
    goto LABEL_51;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    v12 = -2147418113;
    v51 = -2147418113;
    goto LABEL_54;
  }
  ATL::CSimpleStringT<char,0>::SetString(&v47, a2, a3);
  v13 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
          &String,
          &v47);
  if ( !(unsigned __int8)ExtractSoapEnvelope(v13, &v45) )
  {
    v51 = -2147188477;
    LODWORD(v39) = -2147188477;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      0x2034u,
      L"ExtractSoapEnvelope failed with hr:%x",
      v39);
  }
  if ( (byte_1801C36C5 & 4) != 0 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&String);
    LOBYTE(v14) = PPTraceShouldRedact();
    if ( (int)RedactSensitiveXMLElements(&v45, &String, v14) >= 0 )
    {
      ReduceXmlForTracing((const unsigned __int8 **)&String, v15);
      if ( (byte_1801C36C5 & 4) != 0 )
        McTemplateU0s_EventWriteTransfer(v16, SOAPResponse, String);
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&String);
  }
  v51 = CPPCRLBaseRequest::CreateDOM(&v45, &pvarg, &v48, 1);
  if ( v51 < 0 || (v17 = v48) == 0 )
  {
    v9 = "SUCCEEDED(hr = CreateDOM(strSoapResponse, k_cvPPCRLSAPINamespaces, pXmlResponse)) && pXmlResponse != nullptr";
    v11 = 8262;
    goto LABEL_49;
  }
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 296LL);
  v19 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, "/S:Envelope/S:Body");
  LODWORD(String) = 1;
  v20 = v18(v17, *(_QWORD *)v19, &v42);
  v51 = v20;
  if ( v20 < 0 || (v21 = 0, v20 == 1) )
    v21 = 1;
  SysFreeString(bstrString);
  if ( v21 )
  {
    v9 = "SUCCEEDED(hr = pXmlResponse->selectSingleNode(CComBSTR(\"/S:Envelope/S:Body\"), &pNode)) && hr != S_FALSE";
    v11 = 8264;
LABEL_49:
    v10 = -2147188477;
    v51 = -2147188477;
    goto LABEL_50;
  }
  v51 = (*(__int64 (__fastcall **)(CDeviceUserAssociation *, __int64))(*(_QWORD *)this + 376LL))(this, v42);
  if ( v51 == 1 )
  {
    v41 = 0;
    v40 = 0;
    bstrString = 0;
    String = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 296LL))(
            v42,
            *((_QWORD *)this + 35),
            &v41);
    v51 = v22;
    if ( v22 < 0 || v22 == 1 || !v41 )
    {
      v27 = "SUCCEEDED(hr = pNode->selectSingleNode(m_deviceErrorCodeXPath, &pErrorNode)) && hr != S_FALSE && pErrorNode != nullptr";
      v29 = 8276;
    }
    else
    {
      v23 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v41 + 208LL))(v41, &bstrString);
      v51 = v23;
      if ( v23 >= 0 && v23 != 1 )
      {
        v24 = 0;
        v51 = (*(__int64 (__fastcall **)(__int64, _QWORD, CPPCRLBaseRequest **))(*(_QWORD *)v42 + 296LL))(
                v42,
                *((_QWORD *)this + 36),
                &v40);
        if ( v51 >= 0 )
        {
          v25 = v40;
          if ( v40 )
          {
            v51 = (*(__int64 (__fastcall **)(CPPCRLBaseRequest *, wchar_t **))(*(_QWORD *)v40 + 208LL))(v40, &String);
            if ( !v51 )
              v24 = wcstoul(String, 0, 0);
          }
        }
        if ( (byte_1801C36C5 & 2) != 0 )
          CPPCRLBaseRequest::FireServerError(this, v24);
        v26 = CPPCRLBaseRequest::MapServiceError(v25, (struct ATL::CComBSTR *)&bstrString, v24);
        v8 = v26;
        if ( v26 >= 0 )
        {
          v51 = -2147418113;
          v27 = "FAILED(ServiceHr = MapServiceError(bstrErr, SubHr))";
          v28 = -2147418113;
          v29 = 8302;
LABEL_46:
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
            "CDeviceUserAssociation::ParseResponse",
            v29,
            v28,
            v27);
          goto LABEL_47;
        }
        if ( v26 == -2147188632 )
        {
          v44 = 0;
          v43 = 0;
          v30 = v42;
          v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 296LL);
          v32 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v46, L"*/ServerInfo/@ServerTime");
          v33 = v31(v30, *(_QWORD *)v32, &v44);
          SysFreeString(v46);
          if ( v33 < 0 || v33 == 1 || !v44 )
          {
            v34 = 8324;
            goto LABEL_42;
          }
          if ( (*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v44 + 208LL))(v44, &v43) )
          {
            v34 = 8332;
LABEL_42:
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
              v34,
              L"Server response indicates time skew, but can't find server time in response.");
            SysFreeString(v43);
            ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v44);
            goto LABEL_47;
          }
          v35 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  (__int64 *)&v46,
                  v43);
          CPPCRLBaseRequest::SetClockSkew(v36, v35);
          SysFreeString(v43);
          ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v44);
        }
        v51 = 0;
LABEL_47:
        SysFreeString(String);
        SysFreeString(bstrString);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v40);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
        goto LABEL_51;
      }
      v27 = "SUCCEEDED(hr = pErrorNode->get_text(&bstrErr)) && hr != S_FALSE";
      v29 = 8278;
    }
    v28 = -2147188477;
    v51 = -2147188477;
    goto LABEL_46;
  }
LABEL_51:
  if ( v51 < 0 )
    v8 = v51;
  CSingleIdentity::SetRequestStatus(*((CSingleIdentity **)this + 3), v8);
  *((_DWORD *)this + 61) = v8;
  v12 = v51;
LABEL_54:
  VariantClear(&pvarg);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v45);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v47);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v42);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v48);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v50);
  return v12;
}

```

## disassembly

```asm
0x1800d1aa0  mov     [rsp-8+arg_10], rbx
0x1800d1aa5  push    rbp
0x1800d1aa6  push    rsi
0x1800d1aa7  push    rdi
0x1800d1aa8  push    r12
0x1800d1aaa  push    r13
0x1800d1aac  push    r14
0x1800d1aae  push    r15
0x1800d1ab0  lea     rbp, [rsp-27h]
0x1800d1ab5  sub     rsp, 0B0h
0x1800d1abc  mov     rbx, r9
0x1800d1abf  mov     r12d, r8d
0x1800d1ac2  mov     rdi, rdx
0x1800d1ac5  mov     r15, rcx
0x1800d1ac8  xor     r13d, r13d
0x1800d1acb  mov     dword ptr [rbp+57h+String], r13d
0x1800d1acf  mov     [rbp+57h+arg_0], r13d
0x1800d1ad3  mov     r14d, r13d
0x1800d1ad6  lea     rcx, aCdeviceuserass_0; "CDeviceUserAssociation::ParseResponse"
0x1800d1add  mov     [rbp+57h+var_50], rcx
0x1800d1ae1  lea     rax, [rbp+57h+arg_0]
0x1800d1ae5  mov     [rbp+57h+var_48], rax
0x1800d1ae9  mov     [rbp+57h+var_40], r13
0x1800d1aed  mov     [rbp+57h+var_38], r13
0x1800d1af1  xor     r9d, r9d; unsigned int
0x1800d1af4  mov     r8d, 2016h; char *
0x1800d1afa  mov     rdx, rcx; char *
0x1800d1afd  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d1b04  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800d1b09  nop
0x1800d1b0a  mov     [rbp+57h+var_70], r13
0x1800d1b0e  mov     [rbp+57h+var_A0], r13
0x1800d1b12  lea     rcx, [rbp+57h+var_78]
0x1800d1b16  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d1b1b  nop
0x1800d1b1c  lea     rcx, [rbp+57h+var_88]
0x1800d1b20  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d1b25  nop
0x1800d1b26  mov     word ptr [rbp+57h+pvarg], r13w
0x1800d1b2b  lea     rdx, aXmlnsSoapHttpS_0; " xmlns:SOAP=\"http://schemas.xmlsoap.or"...
0x1800d1b32  lea     rcx, [rbp+57h+pvarg]
0x1800d1b36  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x1800d1b3b  nop
0x1800d1b3c  mov     byte ptr [r15+0F8h], 1
0x1800d1b44  mov     dword ptr [rbx], 7
0x1800d1b4a  test    rdi, rdi
0x1800d1b4d  jnz     short loc_1800D1B6C
0x1800d1b4f  mov     ebx, 8000FFFFh
0x1800d1b54  mov     [rbp+57h+arg_0], ebx
0x1800d1b57  lea     rax, aSzresponseNull; "szResponse != nullptr"
0x1800d1b5e  mov     r9d, ebx
0x1800d1b61  mov     r8d, 2023h
0x1800d1b67  jmp     loc_1800D1F66
0x1800d1b6c  cmp     [r15+18h], r13
0x1800d1b70  jnz     short loc_1800D1B7F
0x1800d1b72  mov     ebx, 8000FFFFh
0x1800d1b77  mov     [rbp+57h+arg_0], ebx
0x1800d1b7a  jmp     loc_1800D1F9D
0x1800d1b7f  mov     r8d, r12d
0x1800d1b82  mov     rdx, rdi
0x1800d1b85  lea     rcx, [rbp+57h+var_78]
0x1800d1b89  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x1800d1b8e  lea     rdx, [rbp+57h+var_78]
0x1800d1b92  lea     rcx, [rbp+57h+String]
0x1800d1b96  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x1800d1b9b  lea     rdx, [rbp+57h+var_88]
0x1800d1b9f  mov     rcx, rax
0x1800d1ba2  call    ?ExtractSoapEnvelope@@YA_NV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV12@@Z; ExtractSoapEnvelope(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800d1ba7  mov     r12d, 80048103h
0x1800d1bad  test    al, al
0x1800d1baf  jnz     short loc_1800D1BD8
0x1800d1bb1  mov     [rbp+57h+arg_0], r12d
0x1800d1bb5  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x1800d1bba  lea     r9, aExtractsoapenv_0; "ExtractSoapEnvelope failed with hr:%x"
0x1800d1bc1  mov     r8d, 2034h; unsigned int
0x1800d1bc7  lea     rdx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d1bce  mov     ecx, 5; unsigned __int8
0x1800d1bd3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800d1bd8  test    cs:byte_1801C36C5, 4
0x1800d1bdf  jz      short loc_1800D1C30
0x1800d1be1  lea     rcx, [rbp+57h+String]
0x1800d1be5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d1bea  nop
0x1800d1beb  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x1800d1bf0  mov     r8b, al
0x1800d1bf3  lea     rdx, [rbp+57h+String]
0x1800d1bf7  lea     rcx, [rbp+57h+var_88]
0x1800d1bfb  call    ?RedactSensitiveXMLElements@@YAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV12@_N@Z; RedactSensitiveXMLElements(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,bool)
0x1800d1c00  test    eax, eax
0x1800d1c02  js      short loc_1800D1C27
0x1800d1c04  lea     rcx, [rbp+57h+String]
0x1800d1c08  call    ?ReduceXmlForTracing@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; ReduceXmlForTracing(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800d1c0d  test    cs:byte_1801C36C5, 4
0x1800d1c14  jz      short loc_1800D1C27
0x1800d1c16  mov     r8, [rbp+57h+String]
0x1800d1c1a  lea     rdx, SOAPResponse
0x1800d1c21  call    McTemplateU0s_EventWriteTransfer
0x1800d1c26  nop
0x1800d1c27  lea     rcx, [rbp+57h+String]
0x1800d1c2b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800d1c30  mov     r9d, 1
0x1800d1c36  lea     r8, [rbp+57h+var_70]
0x1800d1c3a  lea     rdx, [rbp+57h+pvarg]
0x1800d1c3e  lea     rcx, [rbp+57h+var_88]
0x1800d1c42  call    ?CreateDOM@CPPCRLBaseRequest@@SAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEBVCComVariant@3@AEAV?$CComPtr@UIXMLDOMDocument2@@@3@H@Z; CPPCRLBaseRequest::CreateDOM(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CComVariant const &,ATL::CComPtr<IXMLDOMDocument2> &,int)
0x1800d1c47  mov     [rbp+57h+arg_0], eax
0x1800d1c4a  test    eax, eax
0x1800d1c4c  js      loc_1800D1F52
0x1800d1c52  mov     rbx, [rbp+57h+var_70]
0x1800d1c56  test    rbx, rbx
0x1800d1c59  jz      loc_1800D1F52
0x1800d1c5f  mov     rax, [rbx]
0x1800d1c62  mov     rdi, [rax+128h]
0x1800d1c69  lea     rdx, aSEnvelopeSBody_14; "/S:Envelope/S:Body"
0x1800d1c70  lea     rcx, [rbp+57h+bstrString]; this
0x1800d1c74  call    ??0CComBSTR@ATL@@QEAA@PEBD@Z; ATL::CComBSTR::CComBSTR(char const *)
0x1800d1c79  nop
0x1800d1c7a  mov     dword ptr [rbp+57h+String], 1
0x1800d1c81  lea     r8, [rbp+57h+var_A0]
0x1800d1c85  mov     rdx, [rax]
0x1800d1c88  mov     rcx, rbx
0x1800d1c8b  mov     rax, rdi
0x1800d1c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1c93  mov     [rbp+57h+arg_0], eax
0x1800d1c96  bt      eax, 1Fh
0x1800d1c9a  jb      short loc_1800D1CA4
0x1800d1c9c  cmp     eax, 1
0x1800d1c9f  mov     bl, r13b
0x1800d1ca2  jnz     short loc_1800D1CA6
0x1800d1ca4  mov     bl, 1
0x1800d1ca6  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800d1caa  call    cs:__imp_SysFreeString
0x1800d1cb0  test    bl, bl
0x1800d1cb2  jz      short loc_1800D1CC6
0x1800d1cb4  lea     rax, aSucceededHrPxm_6; "SUCCEEDED(hr = pXmlResponse->selectSing"...
0x1800d1cbb  mov     r8d, 2048h
0x1800d1cc1  jmp     loc_1800D1F5F
0x1800d1cc6  mov     rax, [r15]
0x1800d1cc9  mov     rdx, [rbp+57h+var_A0]
0x1800d1ccd  mov     rcx, r15
0x1800d1cd0  mov     rax, [rax+178h]
0x1800d1cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1cdc  mov     [rbp+57h+arg_0], eax
0x1800d1cdf  cmp     eax, 1
0x1800d1ce2  jnz     loc_1800D1F7E
0x1800d1ce8  mov     [rbp+57h+var_A8], r13
0x1800d1cec  mov     [rbp+57h+var_B0], r13
0x1800d1cf0  mov     [rbp+57h+bstrString], r13
0x1800d1cf4  mov     [rbp+57h+String], r13
0x1800d1cf8  mov     rcx, [rbp+57h+var_A0]
0x1800d1cfc  mov     rax, [rcx]
0x1800d1cff  lea     r8, [rbp+57h+var_A8]
0x1800d1d03  mov     rdx, [r15+118h]
0x1800d1d0a  mov     rax, [rax+128h]
0x1800d1d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d16  mov     [rbp+57h+arg_0], eax
0x1800d1d19  bt      eax, 1Fh
0x1800d1d1d  jb      loc_1800D1EFA
0x1800d1d23  cmp     eax, 1
0x1800d1d26  jz      loc_1800D1EFA
0x1800d1d2c  mov     rcx, [rbp+57h+var_A8]
0x1800d1d30  test    rcx, rcx
0x1800d1d33  jz      loc_1800D1EFA
0x1800d1d39  mov     rax, [rcx]
0x1800d1d3c  lea     rdx, [rbp+57h+bstrString]
0x1800d1d40  mov     rax, [rax+0D0h]
0x1800d1d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d4c  mov     [rbp+57h+arg_0], eax
0x1800d1d4f  bt      eax, 1Fh
0x1800d1d53  jb      loc_1800D1EEB
0x1800d1d59  cmp     eax, 1
0x1800d1d5c  jz      loc_1800D1EEB
0x1800d1d62  mov     ebx, r13d
0x1800d1d65  mov     rcx, [rbp+57h+var_A0]
0x1800d1d69  mov     rax, [rcx]
0x1800d1d6c  lea     r8, [rbp+57h+var_B0]
0x1800d1d70  mov     rdx, [r15+120h]
0x1800d1d77  mov     rax, [rax+128h]
0x1800d1d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d83  mov     [rbp+57h+arg_0], eax
0x1800d1d86  test    eax, eax
0x1800d1d88  js      short loc_1800D1DBE
0x1800d1d8a  mov     rcx, [rbp+57h+var_B0]
0x1800d1d8e  test    rcx, rcx
0x1800d1d91  jz      short loc_1800D1DBE
0x1800d1d93  mov     rax, [rcx]
0x1800d1d96  lea     rdx, [rbp+57h+String]
0x1800d1d9a  mov     rax, [rax+0D0h]
0x1800d1da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1da6  mov     [rbp+57h+arg_0], eax
0x1800d1da9  test    eax, eax
0x1800d1dab  jnz     short loc_1800D1DBE
0x1800d1dad  xor     r8d, r8d; Radix
0x1800d1db0  xor     edx, edx; EndPtr
0x1800d1db2  mov     rcx, [rbp+57h+String]; String
0x1800d1db6  call    cs:__imp_wcstoul
0x1800d1dbc  mov     ebx, eax
0x1800d1dbe  mov     r12d, 2
0x1800d1dc4  test    cs:byte_1801C36C5, r12b
0x1800d1dcb  jz      short loc_1800D1DD7
0x1800d1dcd  mov     edx, ebx; int
0x1800d1dcf  mov     rcx, r15; this
0x1800d1dd2  call    ?FireServerError@CPPCRLBaseRequest@@QEAAXJ@Z; CPPCRLBaseRequest::FireServerError(long)
0x1800d1dd7  mov     r8d, ebx; int
0x1800d1dda  lea     rdx, [rbp+57h+bstrString]; struct ATL::CComBSTR *
0x1800d1dde  call    ?MapServiceError@CPPCRLBaseRequest@@QEAAJAEAVCComBSTR@ATL@@J@Z; CPPCRLBaseRequest::MapServiceError(ATL::CComBSTR &,long)
0x1800d1de3  mov     r14d, eax
0x1800d1de6  test    eax, eax
0x1800d1de8  js      short loc_1800D1E07
0x1800d1dea  mov     ebx, 8000FFFFh
0x1800d1def  mov     [rbp+57h+arg_0], ebx
0x1800d1df2  lea     rax, aFailedServiceh; "FAILED(ServiceHr = MapServiceError(bstr"...
0x1800d1df9  mov     r9d, ebx
0x1800d1dfc  mov     r8d, 206Eh
0x1800d1e02  jmp     loc_1800D1F0E
0x1800d1e07  cmp     eax, 80048068h
0x1800d1e0c  jnz     loc_1800D1EB2
0x1800d1e12  mov     [rbp+57h+var_90], r13
0x1800d1e16  mov     [rbp+57h+var_98], r13
0x1800d1e1a  mov     rdi, [rbp+57h+var_A0]
0x1800d1e1e  mov     rax, [rdi]
0x1800d1e21  mov     rbx, [rax+128h]
0x1800d1e28  lea     rdx, aServerinfoServ; "*/ServerInfo/@ServerTime"
0x1800d1e2f  lea     rcx, [rbp+57h+var_80]; this
0x1800d1e33  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800d1e38  nop
0x1800d1e39  lea     r8, [rbp+57h+var_90]
0x1800d1e3d  mov     rdx, [rax]
0x1800d1e40  mov     rcx, rdi
0x1800d1e43  mov     rax, rbx
0x1800d1e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e4b  mov     ebx, eax
0x1800d1e4d  mov     rcx, [rbp+57h+var_80]; bstrString
0x1800d1e51  call    cs:__imp_SysFreeString
0x1800d1e57  test    ebx, ebx
0x1800d1e59  js      short loc_1800D1EB8
0x1800d1e5b  cmp     ebx, 1
0x1800d1e5e  jz      short loc_1800D1EB8
0x1800d1e60  mov     rcx, [rbp+57h+var_90]
0x1800d1e64  test    rcx, rcx
0x1800d1e67  jz      short loc_1800D1EB8
0x1800d1e69  mov     rax, [rcx]
0x1800d1e6c  lea     rdx, [rbp+57h+var_98]
0x1800d1e70  mov     rax, [rax+0D0h]
0x1800d1e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e7c  test    eax, eax
0x1800d1e7e  jz      short loc_1800D1E88
0x1800d1e80  mov     r8d, 208Ch
0x1800d1e86  jmp     short loc_1800D1EBE
0x1800d1e88  mov     rdx, [rbp+57h+var_98]
0x1800d1e8c  lea     rcx, [rbp+57h+var_80]
0x1800d1e90  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800d1e95  mov     rdx, rax
0x1800d1e98  call    ?SetClockSkew@CPPCRLBaseRequest@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CPPCRLBaseRequest::SetClockSkew(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800d1e9d  nop
0x1800d1e9e  mov     rcx, [rbp+57h+var_98]; bstrString
0x1800d1ea2  call    cs:__imp_SysFreeString
0x1800d1ea8  nop
0x1800d1ea9  lea     rcx, [rbp+57h+var_90]
0x1800d1ead  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800d1eb2  mov     [rbp+57h+arg_0], r13d
0x1800d1eb6  jmp     short loc_1800D1F27
0x1800d1eb8  mov     r8d, 2084h; unsigned int
0x1800d1ebe  lea     r9, aServerResponse; "Server response indicates time skew, bu"...
0x1800d1ec5  lea     rdx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d1ecc  mov     ecx, r12d; unsigned __int8
0x1800d1ecf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800d1ed4  nop
0x1800d1ed5  mov     rcx, [rbp+57h+var_98]; bstrString
0x1800d1ed9  call    cs:__imp_SysFreeString
0x1800d1edf  nop
0x1800d1ee0  lea     rcx, [rbp+57h+var_90]
0x1800d1ee4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800d1ee9  jmp     short loc_1800D1F27
0x1800d1eeb  lea     rax, aSucceededHrPer; "SUCCEEDED(hr = pErrorNode->get_text(&bs"...
0x1800d1ef2  mov     r8d, 2056h
0x1800d1ef8  jmp     short loc_1800D1F07
0x1800d1efa  lea     rax, aSucceededHrPno_1; "SUCCEEDED(hr = pNode->selectSingleNode("...
0x1800d1f01  mov     r8d, 2054h; unsigned int
0x1800d1f07  mov     r9d, r12d; int
0x1800d1f0a  mov     [rbp+57h+arg_0], r12d
0x1800d1f0e  mov     [rsp+0E0h+var_C0], rax; char *
0x1800d1f13  lea     rdx, aCdeviceuserass_0; "CDeviceUserAssociation::ParseResponse"
0x1800d1f1a  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800d1f21  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800d1f26  nop
0x1800d1f27  mov     rcx, [rbp+57h+String]; bstrString
0x1800d1f2b  call    cs:__imp_SysFreeString
0x1800d1f31  nop
0x1800d1f32  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800d1f36  call    cs:__imp_SysFreeString
0x1800d1f3c  nop
0x1800d1f3d  lea     rcx, [rbp+57h+var_B0]
0x1800d1f41  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800d1f46  nop
0x1800d1f47  lea     rcx, [rbp+57h+var_A8]
0x1800d1f4b  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800d1f50  jmp     short loc_1800D1F7E
0x1800d1f52  lea     rax, aSucceededHrCre; "SUCCEEDED(hr = CreateDOM(strSoapRespons"...
0x1800d1f59  mov     r8d, 2046h; unsigned int
  ... truncated ...
```
