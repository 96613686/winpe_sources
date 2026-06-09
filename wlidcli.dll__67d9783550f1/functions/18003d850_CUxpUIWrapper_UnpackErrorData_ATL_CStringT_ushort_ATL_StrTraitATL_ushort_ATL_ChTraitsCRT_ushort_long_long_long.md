# CUxpUIWrapper::UnpackErrorData(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,long &,long &,long &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18003d850`
- end: `0x18003dbad`
- name: `?UnpackErrorData@CUxpUIWrapper@@SAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAJ11AEAV23@@Z`
- size: `861`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int *, unsigned int *, unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d0c4`

## callees

- `0x18000a7a8`
- `0x18000ade0`
- `0x18000af40`
- `0x18000ba8c`
- `0x18000be18`
- `0x18000cc9c`
- `0x18000e870`
- `0x18000edbc`
- `0x180013384`
- `0x180013638`
- `0x18001b3b4`
- `0x1800214d4`
- `0x18003b0b8`
- `0x18003cec0`
- `0x18003d850`
- `0x180040694`
- `0x1800530e4`
- `0x1800547c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003da16`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003da72`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003dace`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003da16`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003da72`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003dace`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d911`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d911`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d9a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d9a6`
- `OLEAUT32!__imp_VariantClear` at `0x18003d8fb`
- `OLEAUT32!__imp_VariantClear` at `0x18003db68`
- `OLEAUT32!__imp_VariantClear` at `0x18003d8fb`
- `OLEAUT32!__imp_VariantClear` at `0x18003db68`

## string_xrefs

- `0x18003d90a`: ` xmlns:ds="http://www.w3.org/2000/09/xmldsig#" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wssc="http://schemas.xmlsoap.org/ws/2005/02/sc" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:S="http://www.w3.org/2003/05/soap-envel`
- `0x18003d957`: `CreateDOM failed (0x%x).`
- `0x18003d9b3`: `LoadXMLPairs fail. hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUxpUIWrapper::UnpackErrorData(
        unsigned __int16 **a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        _QWORD *a5)
{
  _QWORD *v9; // rsi
  int DOM; // eax
  const unsigned __int16 *v11; // r9
  unsigned int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rax
  const wchar_t *Buffer; // rax
  __int64 v16; // rax
  const wchar_t *v17; // rax
  __int64 v18; // rax
  const wchar_t *v19; // rax
  __int64 v20; // rdx
  int *v21; // rdi
  __int64 v22; // rbx
  unsigned int v23; // ebx
  unsigned __int16 *v25; // [rsp+20h] [rbp-91h]
  unsigned __int16 *v26; // [rsp+20h] [rbp-91h]
  __int64 v27; // [rsp+30h] [rbp-81h] BYREF
  __int64 v28; // [rsp+38h] [rbp-79h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-71h] BYREF
  _QWORD v30[5]; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v31[128]; // [rsp+80h] [rbp-31h] BYREF
  int XMLPairs; // [rsp+118h] [rbp+67h] BYREF
  BSTR bstrString; // [rsp+120h] [rbp+6Fh] BYREF
  int v34; // [rsp+128h] [rbp+77h] BYREF

  XMLPairs = 0;
  v28 = 0;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(
    (unsigned int)v31,
    (_DWORD)a2,
    (_DWORD)a3,
    (_DWORD)a4,
    (_DWORD)FLOAT_2_25);
  v30[0] = "CUxpUIWrapper::UnpackErrorData";
  v30[1] = &XMLPairs;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
    "CUxpUIWrapper::UnpackErrorData",
    (const char *)0x21E,
    0,
    v25);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v9 = a5;
  ATL::CSimpleStringT<unsigned short,0>::Truncate(a5, 0);
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(
                            L" xmlns:ds=\"http://www.w3.org/2000/09/xmldsig#\" xmlns:wsse=\"http://docs.oasis-open.org/wss"
                             "/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd\" xmlns:wssc=\"http://schemas.xmlsoap.o"
                             "rg/ws/2005/02/sc\" xmlns:wsu=\"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wsse"
                             "curity-utility-1.0.xsd\" xmlns:wsp=\"http://schemas.xmlsoap.org/ws/2004/09/policy\" xmlns:w"
                             "st=\"http://schemas.xmlsoap.org/ws/2005/02/trust\" xmlns:saml=\"urn:oasis:names:tc:SAML:1.0"
                             ":assertion\" xmlns:S=\"http://www.w3.org/2003/05/soap-envelope\" xmlns:tb=\"http://schemas."
                             "microsoft.com/trustbridge/schema#1\" xmlns:xenc=\"http://www.w3.org/2001/04/xmlenc#\" xmlns"
                             ":psf=\"http://schemas.microsoft.com/Passport/SoapServices/SOAPFault\" xmlns:ps=\"http://sch"
                             "emas.microsoft.com/Passport/SoapServices/PPCRL\" xmlns:wsa=\"http://www.w3.org/2005/08/addr"
                             "essing\" xmlns:wlid=\"http://schemas.microsoft.com/windlowliveid/2007/01/sts\"");
  if ( !pvarg.llVal )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  DOM = CreateDOM(*a1);
  XMLPairs = DOM;
  if ( DOM < 0 )
  {
    v11 = L"CreateDOM failed (0x%x).";
    v12 = 555;
LABEL_5:
    LODWORD(v26) = DOM;
    TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp", v12, v11, v26);
    goto LABEL_20;
  }
  v13 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"//psf:ErrorData");
  XMLPairs = LoadXMLPairs(v28, v13, v31);
  SysFreeString(bstrString);
  DOM = XMLPairs;
  if ( XMLPairs < 0 )
  {
    v11 = L"LoadXMLPairs fail. hr = 0x%x";
    v12 = 562;
    goto LABEL_5;
  }
  v34 = 0;
  LODWORD(bstrString) = 0;
  v27 = 0;
  if ( ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
         (unsigned int)v31,
         (unsigned int)L"psf:AuthState",
         (unsigned int)&v34,
         (unsigned int)&bstrString,
         (__int64)&v27) )
  {
    v14 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
            v31,
            L"psf:AuthRequired");
    Buffer = (const wchar_t *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v14);
    *a2 = wcstoul(Buffer, 0, 0);
  }
  v34 = 0;
  LODWORD(bstrString) = 0;
  v27 = 0;
  if ( ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
         (unsigned int)v31,
         (unsigned int)L"psf:AuthRequired",
         (unsigned int)&v34,
         (unsigned int)&bstrString,
         (__int64)&v27) )
  {
    v16 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
            v31,
            L"psf:AuthRequired");
    v17 = (const wchar_t *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v16);
    *a3 = wcstoul(v17, 0, 0);
  }
  v34 = 0;
  LODWORD(bstrString) = 0;
  v27 = 0;
  if ( ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
         (unsigned int)v31,
         (unsigned int)L"psf:RequestStatus",
         (unsigned int)&v34,
         (unsigned int)&bstrString,
         (__int64)&v27) )
  {
    v18 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
            v31,
            L"psf:RequestStatus");
    v19 = (const wchar_t *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v18);
    *a4 = wcstoul(v19, 0, 0);
  }
  v34 = 0;
  LODWORD(bstrString) = 0;
  v27 = 0;
  if ( ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNode(
         (unsigned int)v31,
         (unsigned int)L"psf:FlowUrl",
         (unsigned int)&v34,
         (unsigned int)&bstrString,
         (__int64)&v27) )
  {
    v20 = *(_QWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                       v31,
                       L"psf:FlowUrl");
    v21 = (int *)(*v9 - 24LL);
    if ( (int *)(v20 - 24) != v21 )
    {
      if ( v21[4] >= 0 && *(_QWORD *)(v20 - 24) == *(_QWORD *)v21 )
      {
        v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v21);
        *v9 = v22 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v9, v20, *(unsigned int *)(v20 - 16));
      }
    }
  }
LABEL_20:
  v23 = XMLPairs;
  VariantClear(&pvarg);
  CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CDefaultCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CStringData::Release((ATL::CStringData *)(*a1 - 12));
  return v23;
}

```

## disassembly

```asm
0x18003d850  mov     [rsp-8+arg_0], rcx
0x18003d855  push    rbp
0x18003d856  push    rbx
0x18003d857  push    rsi
0x18003d858  push    rdi
0x18003d859  push    r12
0x18003d85b  push    r14
0x18003d85d  push    r15
0x18003d85f  lea     rbp, [rsp-1Fh]
0x18003d864  sub     rsp, 0D0h
0x18003d86b  mov     r15, r9
0x18003d86e  mov     rdi, r8
0x18003d871  mov     rbx, rdx
0x18003d874  mov     r14, rcx
0x18003d877  xor     r12d, r12d
0x18003d87a  mov     [rbp+4Fh+arg_8], r12d
0x18003d87e  mov     [rbp+4Fh+var_C8], r12
0x18003d882  movss   xmm0, cs:__real@40100000
0x18003d88a  movss   dword ptr [rsp+100h+var_E0], xmm0; unsigned __int16 *
0x18003d890  movss   xmm3, cs:__real@3e800000
0x18003d898  movss   xmm2, cs:__real@3f400000
0x18003d8a0  lea     rcx, [rbp+4Fh+var_80]
0x18003d8a4  call    ??0?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(uint,float,float,float,uint)
0x18003d8a9  nop
0x18003d8aa  lea     rdx, aCuxpuiwrapperU; "CUxpUIWrapper::UnpackErrorData"
0x18003d8b1  mov     [rbp+4Fh+var_A8], rdx
0x18003d8b5  lea     rax, [rbp+4Fh+arg_8]
0x18003d8b9  mov     [rbp+4Fh+var_A0], rax
0x18003d8bd  mov     [rbp+4Fh+var_98], r12
0x18003d8c1  mov     [rbp+4Fh+var_90], r12
0x18003d8c5  xor     r9d, r9d; unsigned int
0x18003d8c8  mov     r8d, 21Eh; char *
0x18003d8ce  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003d8d5  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003d8da  nop
0x18003d8db  mov     [rbx], r12d
0x18003d8de  mov     [rdi], r12d
0x18003d8e1  mov     [r15], r12d
0x18003d8e4  xor     edx, edx
0x18003d8e6  mov     rsi, [rbp+4Fh+arg_20]
0x18003d8ea  mov     rcx, rsi
0x18003d8ed  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18003d8f2  mov     word ptr [rbp+4Fh+pvarg], r12w
0x18003d8f7  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18003d8fb  call    cs:__imp_VariantClear
0x18003d901  lea     eax, [r12+8]
0x18003d906  mov     word ptr [rbp+4Fh+pvarg], ax
0x18003d90a  lea     rcx, aXmlnsDsHttpWww; " xmlns:ds=\"http://www.w3.org/2000/09/x"...
0x18003d911  call    cs:__imp_SysAllocString
0x18003d917  mov     dword ptr [rbp+4Fh+pvarg+8], eax
0x18003d91a  mov     rcx, rax
0x18003d91d  sar     rcx, 20h
0x18003d921  mov     dword ptr [rbp+4Fh+pvarg+0Ch], ecx
0x18003d924  test    rax, rax
0x18003d927  jnz     short loc_18003D940
0x18003d929  lea     eax, [r12+0Ah]
0x18003d92e  mov     word ptr [rbp+4Fh+pvarg], ax
0x18003d932  mov     ecx, 8007000Eh; int
0x18003d937  mov     dword ptr [rbp+4Fh+pvarg+8], ecx
0x18003d93a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003d940  lea     r8, [rbp+4Fh+var_C8]
0x18003d944  lea     rdx, [rbp+4Fh+pvarg]
0x18003d948  mov     rcx, [r14]; unsigned __int16 *
0x18003d94b  call    ?CreateDOM@@YAJPEBGAEBVCComVariant@ATL@@AEAV?$CComPtr@UIXMLDOMDocument2@@@2@@Z; CreateDOM(ushort const *,ATL::CComVariant const &,ATL::CComPtr<IXMLDOMDocument2> &)
0x18003d950  mov     [rbp+4Fh+arg_8], eax
0x18003d953  test    eax, eax
0x18003d955  jns     short loc_18003D97E
0x18003d957  lea     r9, aCreatedomFaile; "CreateDOM failed (0x%x)."
0x18003d95e  mov     r8d, 22Bh; unsigned int
0x18003d964  mov     dword ptr [rsp+100h+var_E0], eax
0x18003d968  lea     rdx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003d96f  mov     ecx, 2; unsigned __int8
0x18003d974  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003d979  jmp     loc_18003DB61
0x18003d97e  lea     rdx, aPsfErrordata; "//psf:ErrorData"
0x18003d985  lea     rcx, [rbp+4Fh+bstrString]; this
0x18003d989  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18003d98e  nop
0x18003d98f  lea     r8, [rbp+4Fh+var_80]
0x18003d993  mov     rdx, rax
0x18003d996  mov     rcx, [rbp+4Fh+var_C8]
0x18003d99a  call    ?LoadXMLPairs@@YAJPEAUIXMLDOMDocument@@AEAVCComBSTR@ATL@@AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; LoadXMLPairs(IXMLDOMDocument *,ATL::CComBSTR &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)
0x18003d99f  mov     [rbp+4Fh+arg_8], eax
0x18003d9a2  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x18003d9a6  call    cs:__imp_SysFreeString
0x18003d9ac  mov     eax, [rbp+4Fh+arg_8]
0x18003d9af  test    eax, eax
0x18003d9b1  jns     short loc_18003D9C2
0x18003d9b3  lea     r9, aLoadxmlpairsFa; "LoadXMLPairs fail. hr = 0x%x"
0x18003d9ba  mov     r8d, 232h
0x18003d9c0  jmp     short loc_18003D964
0x18003d9c2  mov     [rbp+4Fh+arg_18], r12d
0x18003d9c6  mov     dword ptr [rbp+4Fh+bstrString], r12d
0x18003d9ca  mov     [rsp+100h+var_D0], r12
0x18003d9cf  lea     rax, [rsp+100h+var_D0]
0x18003d9d4  mov     [rsp+100h+var_E0], rax
0x18003d9d9  lea     r9, [rbp+4Fh+bstrString]
0x18003d9dd  lea     r8, [rbp+4Fh+arg_18]
0x18003d9e1  lea     rdx, aPsfAuthstate; "psf:AuthState"
0x18003d9e8  lea     rcx, [rbp+4Fh+var_80]
0x18003d9ec  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode * &)
0x18003d9f1  test    rax, rax
0x18003d9f4  jz      short loc_18003DA1E
0x18003d9f6  lea     rdx, aPsfAuthrequire; "psf:AuthRequired"
0x18003d9fd  lea     rcx, [rbp+4Fh+var_80]
0x18003da01  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@PEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](ushort const *)
0x18003da06  mov     rcx, rax
0x18003da09  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18003da0e  mov     rcx, rax; String
0x18003da11  xor     r8d, r8d; Radix
0x18003da14  xor     edx, edx; EndPtr
0x18003da16  call    cs:__imp_wcstoul
0x18003da1c  mov     [rbx], eax
0x18003da1e  mov     [rbp+4Fh+arg_18], r12d
0x18003da22  mov     dword ptr [rbp+4Fh+bstrString], r12d
0x18003da26  mov     [rsp+100h+var_D0], r12
0x18003da2b  lea     rax, [rsp+100h+var_D0]
0x18003da30  mov     [rsp+100h+var_E0], rax
0x18003da35  lea     r9, [rbp+4Fh+bstrString]
0x18003da39  lea     r8, [rbp+4Fh+arg_18]
0x18003da3d  lea     rdx, aPsfAuthrequire; "psf:AuthRequired"
0x18003da44  lea     rcx, [rbp+4Fh+var_80]
0x18003da48  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode * &)
0x18003da4d  test    rax, rax
0x18003da50  jz      short loc_18003DA7A
0x18003da52  lea     rdx, aPsfAuthrequire; "psf:AuthRequired"
0x18003da59  lea     rcx, [rbp+4Fh+var_80]
0x18003da5d  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@PEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](ushort const *)
0x18003da62  mov     rcx, rax
0x18003da65  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18003da6a  mov     rcx, rax; String
0x18003da6d  xor     r8d, r8d; Radix
0x18003da70  xor     edx, edx; EndPtr
0x18003da72  call    cs:__imp_wcstoul
0x18003da78  mov     [rdi], eax
0x18003da7a  mov     [rbp+4Fh+arg_18], r12d
0x18003da7e  mov     dword ptr [rbp+4Fh+bstrString], r12d
0x18003da82  mov     [rsp+100h+var_D0], r12
0x18003da87  lea     rax, [rsp+100h+var_D0]
0x18003da8c  mov     [rsp+100h+var_E0], rax
0x18003da91  lea     r9, [rbp+4Fh+bstrString]
0x18003da95  lea     r8, [rbp+4Fh+arg_18]
0x18003da99  lea     rdx, aPsfRequeststat; "psf:RequestStatus"
0x18003daa0  lea     rcx, [rbp+4Fh+var_80]
0x18003daa4  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode * &)
0x18003daa9  test    rax, rax
0x18003daac  jz      short loc_18003DAD7
0x18003daae  lea     rdx, aPsfRequeststat; "psf:RequestStatus"
0x18003dab5  lea     rcx, [rbp+4Fh+var_80]
0x18003dab9  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@PEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](ushort const *)
0x18003dabe  mov     rcx, rax
0x18003dac1  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18003dac6  mov     rcx, rax; String
0x18003dac9  xor     r8d, r8d; Radix
0x18003dacc  xor     edx, edx; EndPtr
0x18003dace  call    cs:__imp_wcstoul
0x18003dad4  mov     [r15], eax
0x18003dad7  mov     [rbp+4Fh+arg_18], r12d
0x18003dadb  mov     dword ptr [rbp+4Fh+bstrString], r12d
0x18003dadf  mov     [rsp+100h+var_D0], r12
0x18003dae4  lea     rax, [rsp+100h+var_D0]
0x18003dae9  mov     [rsp+100h+var_E0], rax
0x18003daee  lea     r9, [rbp+4Fh+bstrString]
0x18003daf2  lea     r8, [rbp+4Fh+arg_18]
0x18003daf6  lea     rdx, aPsfFlowurl; "psf:FlowUrl"
0x18003dafd  lea     rcx, [rbp+4Fh+var_80]
0x18003db01  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode * &)
0x18003db06  test    rax, rax
0x18003db09  jz      short loc_18003DB61
0x18003db0b  lea     rdx, aPsfFlowurl; "psf:FlowUrl"
0x18003db12  lea     rcx, [rbp+4Fh+var_80]
0x18003db16  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@PEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](ushort const *)
0x18003db1b  mov     rdx, [rax]
0x18003db1e  lea     rcx, [rdx-18h]
0x18003db22  mov     rdi, [rsi]
0x18003db25  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18003db29  cmp     rcx, rdi
0x18003db2c  jz      short loc_18003DB61
0x18003db2e  cmp     [rdi+10h], r12d
0x18003db32  jl      short loc_18003DB55
0x18003db34  mov     rax, [rdi]
0x18003db37  cmp     [rcx], rax
0x18003db3a  jnz     short loc_18003DB55
0x18003db3c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003db41  mov     rbx, rax
0x18003db44  mov     rcx, rdi; this
0x18003db47  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003db4c  lea     rax, [rbx+18h]
0x18003db50  mov     [rsi], rax
0x18003db53  jmp     short loc_18003DB61
0x18003db55  mov     r8d, [rdx-10h]
0x18003db59  mov     rcx, rsi
0x18003db5c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003db61  mov     ebx, [rbp+4Fh+arg_8]
0x18003db64  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18003db68  call    cs:__imp_VariantClear
0x18003db6e  nop
0x18003db6f  lea     rcx, [rbp+4Fh+var_A8]
0x18003db73  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003db78  nop
0x18003db79  lea     rcx, [rbp+4Fh+var_80]
0x18003db7d  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@G@2@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CDefaultCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x18003db82  nop
0x18003db83  lea     rcx, [rbp+4Fh+var_C8]
0x18003db87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003db8c  nop
0x18003db8d  mov     rcx, [r14]
0x18003db90  sub     rcx, 18h; this
0x18003db94  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003db99  mov     eax, ebx
0x18003db9b  add     rsp, 0D0h
0x18003dba2  pop     r15
0x18003dba4  pop     r14
0x18003dba6  pop     r12
0x18003dba8  pop     rdi
0x18003dba9  pop     rsi
0x18003dbaa  pop     rbx
0x18003dbab  pop     rbp
0x18003dbac  retn
```
