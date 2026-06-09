# CServiceTokenInfo::UnPack(ushort const *,ulong &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,CBytePtr &,SessionKeyTypes::Type &,ATL::CTime &)

- ea: `0x180067778`
- end: `0x180067f44`
- name: `?UnPack@CServiceTokenInfo@@KAJPEBGAEAKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCBytePtr@@AEAW4Type@SessionKeyTypes@@AEAVCTime@3@@Z`
- size: `1996`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, enum SessionKeyTypes::Type *, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180047008`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015860`
- `0x180017af0`
- `0x180019690`
- `0x180019780`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180021b28`
- `0x180021bbc`
- `0x1800243e0`
- `0x1800396e8`
- `0x180039d94`
- `0x180039ee8`
- `0x1800406a8`
- `0x180044598`
- `0x1800665e4`
- `0x180067778`
- `0x1800838dc`
- `0x18008b4ac`
- `0x1800a3b60`
- `0x1800a4718`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180067a8c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180067a8c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800678a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800678a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18006791a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800679f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180067a44`
- `OLEAUT32!__imp_SysFreeString` at `0x180067ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x180067b60`
- `OLEAUT32!__imp_SysFreeString` at `0x180067c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180067d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180067ed1`
- `OLEAUT32!__imp_SysFreeString` at `0x18006791a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800679f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180067a44`
- `OLEAUT32!__imp_SysFreeString` at `0x180067ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x180067b60`
- `OLEAUT32!__imp_SysFreeString` at `0x180067c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180067d81`
- `OLEAUT32!__imp_SysFreeString` at `0x180067ed1`
- `OLEAUT32!__imp_SysStringLen` at `0x180067a79`
- `OLEAUT32!__imp_SysStringLen` at `0x180067b07`
- `OLEAUT32!__imp_SysStringLen` at `0x180067b95`
- `OLEAUT32!__imp_SysStringLen` at `0x180067c66`
- `OLEAUT32!__imp_SysStringLen` at `0x180067db1`
- `OLEAUT32!__imp_SysStringLen` at `0x180067a79`
- `OLEAUT32!__imp_SysStringLen` at `0x180067b07`
- `OLEAUT32!__imp_SysStringLen` at `0x180067b95`
- `OLEAUT32!__imp_SysStringLen` at `0x180067c66`
- `OLEAUT32!__imp_SysStringLen` at `0x180067db1`

## string_xrefs

- `0x1800677e9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18006793b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800679c9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180067d12`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180067e15`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180067ead`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800678b6`: `hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)`
- `0x1800679bc`: `XML load for text failed at %d: %ls.`
- `0x180067e49`: `Could not read node. HR=0x%x.`
- `0x180067e6b`: `Could not read node. HR=0x%x.`
- `0x180067e8d`: `Could not read node. HR=0x%x.`
- `0x1800677c1`: `CServiceTokenInfo::UnPack`
- `0x1800678ce`: `CServiceTokenInfo::UnPack`
- `0x180067d0b`: `CServiceTokenInfo::UnPack`
- `0x180067926`: `hr = pDOMXml->loadXML(CComBSTR(wstrTokenBlob), &bParsedOK)`
- `0x180067835`: `dwTokenBlob %ls`
- `0x180067e08`: `Token node not found in service token info xml. 0x%x.`
- `0x180067e7a`: `Token node not found in service token info xml. 0x%x.`
- `0x180067e9c`: `Token type node not found in service token info xml. 0x%x.`
- `0x180067e58`: `Expire time node not found in service token info xml. 0x%x.`
- `0x180067e36`: `Session key node not found in service token info xml. 0x%x.`
- `0x180067df2`: `Could not read sessionKeyType node. HR=0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CServiceTokenInfo::UnPack(
        unsigned __int16 *a1,
        _DWORD *a2,
        char *a3,
        unsigned __int8 **a4,
        enum SessionKeyTypes::Type *a5,
        __int64 a6)
{
  unsigned __int8 v9; // dl
  PPTraceStatus *v10; // rcx
  bool v11; // zf
  char v12; // cl
  char v13; // al
  const unsigned __int16 *String; // rax
  HRESULT v15; // eax
  int v16; // r9d
  unsigned int v17; // r8d
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, _QWORD, _WORD *); // rbx
  ATL::CComBSTR *v20; // rax
  int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  _QWORD *v25; // rax
  char *v26; // rbx
  int v27; // eax
  int SessionKeyType; // eax
  const unsigned __int16 *v29; // r9
  unsigned int v30; // r8d
  unsigned int v31; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  const char *ppvb; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+30h] [rbp-D0h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v39; // [rsp+44h] [rbp-BCh] BYREF
  char *v40; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v41; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v49[3]; // [rsp+90h] [rbp-70h] BYREF
  char v50; // [rsp+A8h] [rbp-58h]
  _QWORD v51[4]; // [rsp+B0h] [rbp-50h] BYREF
  void *Block; // [rsp+D0h] [rbp-30h] BYREF
  char v53; // [rsp+D8h] [rbp-28h] BYREF

  v40 = a3;
  v36 = 0;
  v51[0] = "CServiceTokenInfo::UnPack";
  v51[1] = &v36;
  v51[2] = 0;
  v51[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CServiceTokenInfo::UnPack",
    (const char *)0x1305,
    0,
    (const unsigned __int16 *)ppv);
  if ( !PPTraceShouldRedact() || (LOBYTE(v10) = 1, v11 = !PPTraceStatus::TraceOnFlag(v10, v9), v13 = v12, v11) )
    v13 = 0;
  v49[0] = &PPRedactedStringW::`vftable';
  v49[1] = a1;
  v49[2] = 0;
  v50 = v13;
  String = PPRedactedStringW::GetString((PPRedactedStringW *)v49);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    0x1306u,
    L"dwTokenBlob %ls",
    String);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v49);
  v41 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  pbstr = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
  v38[0] = 0;
  v15 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v41);
  v36 = v15;
  if ( v15 < 0 )
  {
    ppvb = "hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)";
    v16 = v15;
    v17 = 4879;
LABEL_6:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      "CServiceTokenInfo::UnPack",
      v17,
      v16,
      ppvb);
    goto LABEL_58;
  }
  v18 = v41;
  v19 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _WORD *))(*(_QWORD *)v41 + 520LL);
  v20 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a1);
  v21 = v19(v18, *(_QWORD *)v20, v38);
  v36 = v21;
  SysFreeString(bstrString);
  if ( v21 < 0 )
  {
    ppvb = "hr = pDOMXml->loadXML(CComBSTR(wstrTokenBlob), &bParsedOK)";
    v16 = v21;
    v17 = 4881;
    goto LABEL_6;
  }
  if ( v38[0] == 0xFFFF )
  {
    v22 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v41 + 296LL))(
            v41,
            k_bstrServiceTokenTypePath,
            &v46);
    v36 = v22;
    if ( v22 < 0 || !v46 )
    {
      v29 = L"Token type node not found in service token info xml. 0x%x.";
      v30 = 4906;
      goto LABEL_57;
    }
    SysFreeString(pbstr);
    pbstr = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v46 + 208LL))(v46, &pbstr);
    v36 = v22;
    if ( v22 >= 0 )
    {
      if ( SysStringLen(pbstr) )
      {
        *a2 = _o__wtoi(pbstr);
        v22 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v41 + 296LL))(
                v41,
                k_bstrServiceTokenTicketPath,
                &v44);
        v36 = v22;
        if ( v22 < 0 || !v44 )
        {
          v29 = L"Token node not found in service token info xml. 0x%x.";
          v30 = 4923;
          goto LABEL_57;
        }
        SysFreeString(pbstr);
        pbstr = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v44 + 208LL))(v44, &pbstr);
        v36 = v22;
        if ( v22 >= 0 )
        {
          if ( SysStringLen(pbstr) )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(v40, pbstr);
            v22 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v41 + 296LL))(
                    v41,
                    k_bstrServiceTokenExpiredTimePath,
                    &v43);
            v36 = v22;
            if ( v22 < 0 || !v43 )
            {
              v29 = L"Expire time node not found in service token info xml. 0x%x.";
              v30 = 4940;
              goto LABEL_57;
            }
            SysFreeString(pbstr);
            pbstr = 0;
            v22 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v43 + 208LL))(v43, &pbstr);
            v36 = v22;
            if ( v22 >= 0 )
            {
              if ( SysStringLen(pbstr) )
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v48, pbstr);
                v23 = CTokenInfo::String2Time(&v48, a6);
                v36 = v23;
                if ( v23 < 0 )
                {
                  ppvb = "hr = String2Time(wstrExpireTime, ctExpireTime)";
                  v16 = v23;
                  v17 = 4952;
                  goto LABEL_6;
                }
                v22 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v41 + 296LL))(
                        v41,
                        k_bstrServiceTokenSessionKeyPath,
                        &v45);
                v36 = v22;
                if ( v22 >= 0 && v45 )
                {
                  SysFreeString(pbstr);
                  pbstr = 0;
                  v24 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v45 + 208LL))(v45, &pbstr);
                  v36 = v24;
                  if ( v24 < 0 )
                  {
                    ppvb = "hr = pSessionKeyNode->get_text(&bstrValue)";
                    v16 = v24;
                    v17 = 4963;
                    goto LABEL_6;
                  }
                  if ( SysStringLen(pbstr) )
                  {
                    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
                    v25 = (_QWORD *)ATL::CW2AEX<128>::CW2AEX<128>(&Block, pbstr);
                    ATL::CSimpleStringT<char,0>::SetString(&v40, *v25);
                    if ( Block != &v53 )
                      free(Block);
                    v26 = v40;
                    v39 = *((_DWORD *)v40 - 4);
                    CBytePtr::SetLength((CBytePtr *)a4, v39, 1);
                    LODWORD(v26) = ATL::Base64Decode(v26, *((_DWORD *)v26 - 4), a4[1], (int *)&v39);
                    CBytePtr::SetLength((CBytePtr *)a4, v39, 1);
                    if ( !(_DWORD)v26 )
                    {
                      v36 = -2147188474;
                      Telemetry::IfFailExit(
                        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
                        "CServiceTokenInfo::UnPack",
                        0x1378u,
                        -2147188474,
                        "bRet");
                      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
                      goto LABEL_58;
                    }
                    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
                  }
                  else
                  {
                    CBytePtr::SetLength((CBytePtr *)a4, 0, 1);
                  }
                  v27 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v41 + 296LL))(
                          v41,
                          k_bstrServiceTokenSessionKeyTypePath,
                          &v47);
                  v36 = v27;
                  if ( v27 < 0 || !v47 )
                  {
                    LODWORD(ppva) = v27;
                    TracePrintW(
                      2u,
                      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
                      0x1383u,
                      L"Token node not found in service token info xml. 0x%x.",
                      ppva);
                    *(_DWORD *)a5 = 1;
                    v36 = 0;
                    goto LABEL_58;
                  }
                  SysFreeString(pbstr);
                  pbstr = 0;
                  v22 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v47 + 208LL))(v47, &pbstr);
                  v36 = v22;
                  if ( v22 >= 0 )
                  {
                    if ( SysStringLen(pbstr) )
                    {
                      SessionKeyType = CAuthInfo::GetSessionKeyType(pbstr, a5);
                      v36 = SessionKeyType;
                      if ( SessionKeyType >= 0 )
                        goto LABEL_58;
                      ppvb = "hr = CAuthInfo::GetSessionKeyType(bstrValue, sessionKeyType)";
                      v16 = SessionKeyType;
                      v17 = 5012;
                      goto LABEL_6;
                    }
                    v22 = v36;
                  }
                  v29 = L"Could not read sessionKeyType node. HR=0x%x.";
                  v30 = 5008;
                }
                else
                {
                  v29 = L"Session key node not found in service token info xml. 0x%x.";
                  v30 = 4958;
                }
LABEL_57:
                LODWORD(ppva) = v22;
                TracePrintW(
                  2u,
                  "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
                  v30,
                  v29,
                  ppva);
                goto LABEL_58;
              }
              v22 = v36;
            }
            v29 = L"Could not read node. HR=0x%x.";
            v30 = 4948;
            goto LABEL_57;
          }
          v22 = v36;
        }
        v29 = L"Could not read node. HR=0x%x.";
        v30 = 4931;
        goto LABEL_57;
      }
      v22 = v36;
    }
    v29 = L"Could not read node. HR=0x%x.";
    v30 = 4914;
    goto LABEL_57;
  }
  v40 = 0;
  bstrString = 0;
  v39 = -1;
  (*(void (__fastcall **)(LPVOID, char **))(*(_QWORD *)v41 + 480LL))(v41, &v40);
  if ( v40 )
  {
    (*(void (__fastcall **)(char *, BSTR *))(*(_QWORD *)v40 + 72LL))(v40, &bstrString);
    (*(void (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v40 + 88LL))(v40, &v39);
    LODWORD(ppva) = v39;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x131Eu,
      L"XML load for text failed at %d: %ls.",
      ppva,
      bstrString);
  }
  v36 = -2147186552;
  ATL::CComPtrBase<IXMLDOMNodeList>::Release(&v41);
  SysFreeString(bstrString);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v40);
LABEL_58:
  v31 = v36;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
  SysFreeString(pbstr);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v43);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v44);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v45);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v46);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v47);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v41);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v51);
  return v31;
}

```

## disassembly

```asm
0x180067778  push    rbp
0x18006777a  push    rbx
0x18006777b  push    rsi
0x18006777c  push    rdi
0x18006777d  push    r12
0x18006777f  push    r13
0x180067781  push    r14
0x180067783  push    r15
0x180067785  lea     rbp, [rsp-78h]
0x18006778a  sub     rsp, 178h
0x180067791  mov     rax, cs:__security_cookie
0x180067798  xor     rax, rsp
0x18006779b  mov     [rbp+0B0h+var_50], rax
0x18006779f  mov     rsi, r9
0x1800677a2  mov     [rsp+1B0h+var_168], r8
0x1800677a7  mov     r12, rdx
0x1800677aa  mov     r14, rcx
0x1800677ad  mov     r15, [rbp+0B0h+arg_20]
0x1800677b4  mov     r13, [rbp+0B0h+arg_28]
0x1800677bb  xor     ebx, ebx
0x1800677bd  mov     [rsp+1B0h+var_180], ebx
0x1800677c1  lea     rcx, aCservicetokeni_2; "CServiceTokenInfo::UnPack"
0x1800677c8  mov     [rbp+0B0h+var_100], rcx
0x1800677cc  lea     rax, [rsp+1B0h+var_180]
0x1800677d1  mov     [rbp+0B0h+var_F8], rax
0x1800677d5  mov     [rbp+0B0h+var_F0], rbx
0x1800677d9  mov     [rbp+0B0h+var_E8], rbx
0x1800677dd  xor     r9d, r9d; unsigned int
0x1800677e0  mov     r8d, 1305h; char *
0x1800677e6  mov     rdx, rcx; char *
0x1800677e9  lea     rdi, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800677f0  mov     rcx, rdi; this
0x1800677f3  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800677f8  nop
0x1800677f9  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x1800677fe  test    al, al
0x180067800  jz      short loc_18006780F
0x180067802  mov     cl, 1; this
0x180067804  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180067809  test    al, al
0x18006780b  mov     al, cl
0x18006780d  jnz     short loc_180067811
0x18006780f  mov     al, bl
0x180067811  lea     rcx, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180067818  mov     [rbp+0B0h+var_120], rcx
0x18006781c  mov     [rbp+0B0h+var_118], r14
0x180067820  mov     [rbp+0B0h+var_110], rbx
0x180067824  mov     [rbp+0B0h+var_108], al
0x180067827  lea     rcx, [rbp+0B0h+var_120]; this
0x18006782b  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180067830  mov     [rsp+1B0h+ppv], rax
0x180067835  lea     r9, aDwtokenblobLs; "dwTokenBlob %ls"
0x18006783c  mov     r8d, 1306h; unsigned int
0x180067842  mov     rdx, rdi; char *
0x180067845  mov     ecx, 5; unsigned __int8
0x18006784a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006784f  nop
0x180067850  lea     rcx, [rbp+0B0h+var_120]; this
0x180067854  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180067859  mov     [rsp+1B0h+var_160], rbx
0x18006785e  mov     [rbp+0B0h+var_130], rbx
0x180067862  mov     [rsp+1B0h+var_138], rbx
0x180067867  mov     [rsp+1B0h+var_140], rbx
0x18006786c  mov     [rsp+1B0h+var_148], rbx
0x180067871  mov     [rsp+1B0h+var_150], rbx
0x180067876  mov     [rsp+1B0h+pbstr], rbx
0x18006787b  lea     rcx, [rbp+0B0h+var_128]
0x18006787f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180067884  nop
0x180067885  mov     [rsp+1B0h+var_170], bx
0x18006788a  lea     rax, [rsp+1B0h+var_160]
0x18006788f  mov     [rsp+1B0h+ppv], rax; ppv
0x180067894  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18006789b  xor     edx, edx; pUnkOuter
0x18006789d  lea     r8d, [rdx+17h]; dwClsContext
0x1800678a1  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800678a8  call    cs:__imp_CoCreateInstance
0x1800678ae  mov     [rsp+1B0h+var_180], eax
0x1800678b2  test    eax, eax
0x1800678b4  jns     short loc_1800678DF
0x1800678b6  lea     rcx, aHrPdomxmlCocre; "hr = pDOMXml.CoCreateInstance(CLSID_DOM"...
0x1800678bd  mov     [rsp+1B0h+ppv], rcx; char *
0x1800678c2  mov     r9d, eax; int
0x1800678c5  mov     r8d, 130Fh; unsigned int
0x1800678cb  mov     rcx, rdi; char *
0x1800678ce  lea     rdx, aCservicetokeni_2; "CServiceTokenInfo::UnPack"
0x1800678d5  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800678da  jmp     loc_180067EBE
0x1800678df  mov     rdi, [rsp+1B0h+var_160]
0x1800678e4  mov     rax, [rdi]
0x1800678e7  mov     rbx, [rax+208h]
0x1800678ee  mov     rdx, r14; unsigned __int16 *
0x1800678f1  lea     rcx, [rsp+1B0h+bstrString]; this
0x1800678f6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800678fb  nop
0x1800678fc  lea     r8, [rsp+1B0h+var_170]
0x180067901  mov     rdx, [rax]
0x180067904  mov     rcx, rdi
0x180067907  mov     rax, rbx
0x18006790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006790f  mov     ebx, eax
0x180067911  mov     [rsp+1B0h+var_180], eax
0x180067915  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x18006791a  call    cs:__imp_SysFreeString
0x180067920  xor     edi, edi
0x180067922  test    ebx, ebx
0x180067924  jns     short loc_180067944
0x180067926  lea     rax, aHrPdomxmlLoadx_2; "hr = pDOMXml->loadXML(CComBSTR(wstrToke"...
0x18006792d  mov     [rsp+1B0h+ppv], rax
0x180067932  mov     r9d, ebx
0x180067935  mov     r8d, 1311h
0x18006793b  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180067942  jmp     short loc_1800678CE
0x180067944  or      eax, 0FFFFFFFFh
0x180067947  cmp     ax, [rsp+1B0h+var_170]
0x18006794c  jz      loc_180067A08
0x180067952  mov     [rsp+1B0h+var_168], rdi
0x180067957  mov     [rsp+1B0h+bstrString], rdi
0x18006795c  mov     [rsp+1B0h+var_16C], eax
0x180067960  mov     rcx, [rsp+1B0h+var_160]
0x180067965  mov     rax, [rcx]
0x180067968  lea     rdx, [rsp+1B0h+var_168]
0x18006796d  mov     rax, [rax+1E0h]
0x180067974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067979  mov     rcx, [rsp+1B0h+var_168]
0x18006797e  test    rcx, rcx
0x180067981  jz      short loc_1800679DA
0x180067983  mov     rax, [rcx]
0x180067986  lea     rdx, [rsp+1B0h+bstrString]
0x18006798b  mov     rax, [rax+48h]
0x18006798f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067994  mov     rcx, [rsp+1B0h+var_168]
0x180067999  mov     rax, [rcx]
0x18006799c  lea     rdx, [rsp+1B0h+var_16C]
0x1800679a1  mov     rax, [rax+58h]
0x1800679a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679aa  mov     rax, [rsp+1B0h+bstrString]
0x1800679af  mov     [rsp+1B0h+var_188], rax
0x1800679b4  mov     eax, [rsp+1B0h+var_16C]
0x1800679b8  mov     dword ptr [rsp+1B0h+ppv], eax
0x1800679bc  lea     r9, aXmlLoadForText; "XML load for text failed at %d: %ls."
0x1800679c3  mov     r8d, 131Eh; unsigned int
0x1800679c9  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800679d0  mov     ecx, 2; unsigned __int8
0x1800679d5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800679da  mov     [rsp+1B0h+var_180], 80048888h
0x1800679e2  lea     rcx, [rsp+1B0h+var_160]
0x1800679e7  call    ?Release@?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNodeList>::Release(void)
0x1800679ec  nop
0x1800679ed  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x1800679f2  call    cs:__imp_SysFreeString
0x1800679f8  nop
0x1800679f9  lea     rcx, [rsp+1B0h+var_168]
0x1800679fe  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180067a03  jmp     loc_180067EBE
0x180067a08  mov     rcx, [rsp+1B0h+var_160]
0x180067a0d  mov     rax, [rcx]
0x180067a10  lea     r8, [rsp+1B0h+var_138]
0x180067a15  mov     rdx, cs:?k_bstrServiceTokenTypePath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrServiceTokenTypePath
0x180067a1c  mov     rax, [rax+128h]
0x180067a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a28  mov     [rsp+1B0h+var_180], eax
0x180067a2c  test    eax, eax
0x180067a2e  js      loc_180067E9C
0x180067a34  cmp     [rsp+1B0h+var_138], rdi
0x180067a39  jz      loc_180067E9C
0x180067a3f  mov     rcx, [rsp+1B0h+pbstr]; bstrString
0x180067a44  call    cs:__imp_SysFreeString
0x180067a4a  mov     [rsp+1B0h+pbstr], rdi
0x180067a4f  mov     rcx, [rsp+1B0h+var_138]
0x180067a54  mov     rax, [rcx]
0x180067a57  lea     rdx, [rsp+1B0h+pbstr]
0x180067a5c  mov     rax, [rax+0D0h]
0x180067a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a68  mov     [rsp+1B0h+var_180], eax
0x180067a6c  test    eax, eax
0x180067a6e  js      loc_180067E8D
0x180067a74  mov     rcx, [rsp+1B0h+pbstr]; pbstr
0x180067a79  call    cs:__imp_SysStringLen
0x180067a7f  test    eax, eax
0x180067a81  jz      loc_180067E89
0x180067a87  mov     rcx, [rsp+1B0h+pbstr]
0x180067a8c  call    cs:__imp__o__wtoi
0x180067a92  mov     [r12], eax
0x180067a96  mov     rcx, [rsp+1B0h+var_160]
0x180067a9b  mov     rax, [rcx]
0x180067a9e  lea     r8, [rsp+1B0h+var_148]
0x180067aa3  mov     rdx, cs:?k_bstrServiceTokenTicketPath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrServiceTokenTicketPath
0x180067aaa  mov     rax, [rax+128h]
0x180067ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ab6  mov     [rsp+1B0h+var_180], eax
0x180067aba  test    eax, eax
0x180067abc  js      loc_180067E7A
0x180067ac2  cmp     [rsp+1B0h+var_148], rdi
0x180067ac7  jz      loc_180067E7A
0x180067acd  mov     rcx, [rsp+1B0h+pbstr]; bstrString
0x180067ad2  call    cs:__imp_SysFreeString
0x180067ad8  mov     [rsp+1B0h+pbstr], rdi
0x180067add  mov     rcx, [rsp+1B0h+var_148]
0x180067ae2  mov     rax, [rcx]
0x180067ae5  lea     rdx, [rsp+1B0h+pbstr]
0x180067aea  mov     rax, [rax+0D0h]
0x180067af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067af6  mov     [rsp+1B0h+var_180], eax
0x180067afa  test    eax, eax
0x180067afc  js      loc_180067E6B
0x180067b02  mov     rcx, [rsp+1B0h+pbstr]; pbstr
0x180067b07  call    cs:__imp_SysStringLen
0x180067b0d  test    eax, eax
0x180067b0f  jz      loc_180067E67
0x180067b15  mov     rdx, [rsp+1B0h+pbstr]
0x180067b1a  mov     rcx, [rsp+1B0h+var_168]
0x180067b1f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180067b24  mov     rcx, [rsp+1B0h+var_160]
0x180067b29  mov     rax, [rcx]
0x180067b2c  lea     r8, [rsp+1B0h+var_150]
0x180067b31  mov     rdx, cs:?k_bstrServiceTokenExpiredTimePath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrServiceTokenExpiredTimePath
0x180067b38  mov     rax, [rax+128h]
0x180067b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b44  mov     [rsp+1B0h+var_180], eax
0x180067b48  test    eax, eax
0x180067b4a  js      loc_180067E58
0x180067b50  cmp     [rsp+1B0h+var_150], rdi
0x180067b55  jz      loc_180067E58
0x180067b5b  mov     rcx, [rsp+1B0h+pbstr]; bstrString
0x180067b60  call    cs:__imp_SysFreeString
0x180067b66  mov     [rsp+1B0h+pbstr], rdi
0x180067b6b  mov     rcx, [rsp+1B0h+var_150]
0x180067b70  mov     rax, [rcx]
0x180067b73  lea     rdx, [rsp+1B0h+pbstr]
0x180067b78  mov     rax, [rax+0D0h]
0x180067b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b84  mov     [rsp+1B0h+var_180], eax
0x180067b88  test    eax, eax
0x180067b8a  js      loc_180067E49
0x180067b90  mov     rcx, [rsp+1B0h+pbstr]; pbstr
0x180067b95  call    cs:__imp_SysStringLen
0x180067b9b  test    eax, eax
0x180067b9d  jz      loc_180067E45
0x180067ba3  mov     rdx, [rsp+1B0h+pbstr]
0x180067ba8  lea     rcx, [rbp+0B0h+var_128]
0x180067bac  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180067bb1  mov     rdx, r13
0x180067bb4  lea     rcx, [rbp+0B0h+var_128]
0x180067bb8  call    ?String2Time@CTokenInfo@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCTime@3@@Z; CTokenInfo::String2Time(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CTime &)
0x180067bbd  mov     [rsp+1B0h+var_180], eax
0x180067bc1  test    eax, eax
0x180067bc3  jns     short loc_180067BDF
0x180067bc5  lea     rcx, aHrString2timeW; "hr = String2Time(wstrExpireTime, ctExpi"...
0x180067bcc  mov     [rsp+1B0h+ppv], rcx
0x180067bd1  mov     r9d, eax
0x180067bd4  mov     r8d, 1358h
0x180067bda  jmp     loc_18006793B
0x180067bdf  mov     rcx, [rsp+1B0h+var_160]
0x180067be4  mov     rax, [rcx]
0x180067be7  lea     r8, [rsp+1B0h+var_140]
0x180067bec  mov     rdx, cs:?k_bstrServiceTokenSessionKeyPath@@3VCComBSTR@ATL@@A; ATL::CComBSTR k_bstrServiceTokenSessionKeyPath
0x180067bf3  mov     rax, [rax+128h]
0x180067bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067bff  mov     [rsp+1B0h+var_180], eax
0x180067c03  test    eax, eax
0x180067c05  js      loc_180067E36
0x180067c0b  cmp     [rsp+1B0h+var_140], rdi
0x180067c10  jz      loc_180067E36
0x180067c16  mov     rcx, [rsp+1B0h+pbstr]; bstrString
0x180067c1b  call    cs:__imp_SysFreeString
0x180067c21  mov     [rsp+1B0h+pbstr], rdi
0x180067c26  mov     rcx, [rsp+1B0h+var_140]
0x180067c2b  mov     rax, [rcx]
0x180067c2e  lea     rdx, [rsp+1B0h+pbstr]
0x180067c33  mov     rax, [rax+0D0h]
0x180067c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c3f  mov     [rsp+1B0h+var_180], eax
0x180067c43  test    eax, eax
0x180067c45  jns     short loc_180067C61
0x180067c47  lea     rcx, aHrPsessionkeyn; "hr = pSessionKeyNode->get_text(&bstrVal"...
0x180067c4e  mov     [rsp+1B0h+ppv], rcx
0x180067c53  mov     r9d, eax
0x180067c56  mov     r8d, 1363h
0x180067c5c  jmp     loc_18006793B
0x180067c61  mov     rcx, [rsp+1B0h+pbstr]; pbstr
0x180067c66  call    cs:__imp_SysStringLen
0x180067c6c  test    eax, eax
0x180067c6e  jz      loc_180067D3A
0x180067c74  lea     rcx, [rsp+1B0h+var_168]
0x180067c79  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180067c7e  nop
0x180067c7f  mov     rdx, [rsp+1B0h+pbstr]
0x180067c84  lea     rcx, [rbp+0B0h+Block]
0x180067c88  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x180067c8d  nop
0x180067c8e  mov     rdx, [rax]
0x180067c91  lea     rcx, [rsp+1B0h+var_168]
0x180067c96  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x180067c9b  nop
0x180067c9c  mov     rcx, [rbp+0B0h+Block]; Block
0x180067ca0  lea     rax, [rbp+0B0h+var_D8]
0x180067ca4  cmp     rcx, rax
0x180067ca7  jz      short loc_180067CAE
0x180067ca9  call    free
  ... truncated ...
```
