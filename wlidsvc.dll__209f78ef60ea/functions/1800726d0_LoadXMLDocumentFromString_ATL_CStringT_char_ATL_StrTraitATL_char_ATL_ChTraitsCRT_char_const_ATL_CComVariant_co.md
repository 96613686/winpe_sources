# LoadXMLDocumentFromString(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CComVariant const &,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x1800726d0`
- end: `0x180072a6b`
- name: `?LoadXMLDocumentFromString@@YAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEBVCComVariant@2@AEAV?$CComPtr@UIXMLDOMDocument2@@@2@@Z`
- size: `923`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005dc64`
- `0x180108258`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180039ee8`
- `0x1800406a8`
- `0x180047a00`
- `0x1800726d0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800727a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800727a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18007286e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800729f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18007286e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800729f5`
- `OLEAUT32!__imp_VariantClear` at `0x18007293f`
- `OLEAUT32!__imp_VariantClear` at `0x18007294e`
- `OLEAUT32!__imp_VariantClear` at `0x18007293f`
- `OLEAUT32!__imp_VariantClear` at `0x18007294e`

## string_xrefs

- `0x18007273e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\xmlutilities.cpp`
- `0x18007288d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\xmlutilities.cpp`
- `0x18007292e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\xmlutilities.cpp`
- `0x1800729d9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\xmlutilities.cpp`
- `0x1800729cc`: `XML load for text failed at %d: %ls.`
- `0x18007270f`: `LoadXMLDocumentFromString`
- `0x180072878`: `hr = pDocument->setProperty(CComBSTR(XML_PROP_SELECTION_NAMESPACES), cvNamespaces)`
- `0x1800727ae`: `hr = pDocument.CoCreateInstance(CLSID_DOMDocument60)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LoadXMLDocumentFromString(__int64 *a1, __int128 *a2, _QWORD *a3)
{
  int v6; // r9d
  unsigned int v7; // r8d
  HRESULT v8; // eax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, VARIANTARG *); // rbx
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  ATL::CComBSTR *v13; // rax
  int v14; // ebx
  struct SmartPCCERT_CONTEXT *v15; // rdx
  int v16; // ecx
  int v17; // eax
  LPVOID v18; // rbx
  unsigned int v19; // ebx
  LPVOID *ppv; // [rsp+28h] [rbp-99h]
  const char *ppva; // [rsp+28h] [rbp-99h]
  LPVOID *ppvb; // [rsp+28h] [rbp-99h]
  LPVOID v24; // [rsp+38h] [rbp-89h] BYREF
  int v25; // [rsp+40h] [rbp-81h] BYREF
  __int64 v26; // [rsp+48h] [rbp-79h] BYREF
  BSTR v27; // [rsp+50h] [rbp-71h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-69h] BYREF
  void **v29; // [rsp+78h] [rbp-49h] BYREF
  __int64 v30; // [rsp+80h] [rbp-41h]
  int v31; // [rsp+88h] [rbp-39h]
  _QWORD v32[5]; // [rsp+90h] [rbp-31h] BYREF
  VARIANTARG v33; // [rsp+B8h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+128h] [rbp+67h] BYREF
  int v35; // [rsp+140h] [rbp+7Fh] BYREF

  v35 = 0;
  v24 = 0;
  v32[0] = "LoadXMLDocumentFromString";
  v32[1] = &v35;
  v32[2] = 0;
  v32[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\xmlutilities.cpp",
    "LoadXMLDocumentFromString",
    (const char *)0x9C,
    0,
    (const unsigned __int16 *)ppv);
  if ( *(int *)(*a1 - 16) <= 0 )
  {
    v6 = -2147418113;
    v35 = -2147418113;
    ppva = "strText.GetLength() > 0";
    v7 = 159;
LABEL_3:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\xmlutilities.cpp",
      "LoadXMLDocumentFromString",
      v7,
      v6,
      ppva);
    goto LABEL_18;
  }
  v8 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v24);
  v35 = v8;
  if ( v8 < 0 )
  {
    ppva = "hr = pDocument.CoCreateInstance(CLSID_DOMDocument60)";
    v6 = v8;
    v7 = 161;
    goto LABEL_3;
  }
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v24 + 504LL))(v24, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v24 + 544LL))(v24, 0);
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v24 + 576LL))(v24, 0xFFFFFFFFLL);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v24 + 560LL))(v24, 0);
  v9 = v24;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, VARIANTARG *))(*(_QWORD *)v24 + 640LL);
  v11 = *a2;
  v12 = (IRecordInfo *)*((_QWORD *)a2 + 2);
  v13 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
  *(_OWORD *)&pvarg.vt = v11;
  pvarg.pRecInfo = v12;
  v14 = v10(v9, *(_QWORD *)v13, &pvarg);
  v35 = v14;
  SysFreeString(bstrString);
  if ( v14 >= 0 )
  {
    v29 = &CReadStreamOnMemory::`vftable';
    v30 = 0;
    v31 = 0;
    LOWORD(bstrString) = 0;
    v16 = *(_DWORD *)(*a1 - 16);
    v30 = *a1;
    v31 = v16;
    pvarg.vt = 13;
    pvarg.llVal = (LONGLONG)&v29;
    CPPCRLBaseRequest::GetClientCert((CPPCRLBaseRequest *)&v29, v15);
    v33 = pvarg;
    v17 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, BSTR *))(*(_QWORD *)v24 + 464LL))(v24, &v33, &bstrString);
    v35 = v17;
    if ( v17 >= 0 )
    {
      VariantClear(&pvarg);
      if ( (_WORD)bstrString == 0xFFFF )
      {
        v18 = v24;
        v24 = 0;
        if ( *a3 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
        *a3 = v18;
      }
      else
      {
        v26 = 0;
        v27 = 0;
        v25 = -1;
        (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v24 + 480LL))(v24, &v26);
        if ( v26 )
        {
          (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 72LL))(v26, &v27);
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 88LL))(v26, &v25);
          LODWORD(ppvb) = v25;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\xmlutilities.cpp",
            0xC0u,
            L"XML load for text failed at %d: %ls.",
            ppvb,
            v27);
        }
        v35 = -2147188477;
        SysFreeString(v27);
        ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\xmlutilities.cpp",
        "LoadXMLDocumentFromString",
        0xB1u,
        v17,
        "hr = pDocument->load(varStream, &bIsOk)");
      VariantClear(&pvarg);
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\xmlutilities.cpp",
      "LoadXMLDocumentFromString",
      0xA8u,
      v14,
      "hr = pDocument->setProperty(CComBSTR(XML_PROP_SELECTION_NAMESPACES), cvNamespaces)");
  }
LABEL_18:
  v19 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v32);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v24);
  return v19;
}

```

## disassembly

```asm
0x1800726d0  mov     rax, rsp
0x1800726d3  mov     [rax+10h], rbx
0x1800726d7  mov     [rax+18h], rsi
0x1800726db  push    rbp
0x1800726dc  push    rdi
0x1800726dd  push    r13
0x1800726df  push    r14
0x1800726e1  push    r15
0x1800726e3  lea     rbp, [rax-5Fh]
0x1800726e7  sub     rsp, 0F0h
0x1800726ee  movaps  xmmword ptr [rax-38h], xmm6
0x1800726f2  movaps  xmmword ptr [rax-48h], xmm7
0x1800726f6  mov     rsi, r8
0x1800726f9  mov     r15, rdx
0x1800726fc  mov     r14, rcx
0x1800726ff  mov     [rbp+57h+arg_18], 0
0x180072706  mov     [rsp+110h+var_E0], 0
0x18007270f  lea     r13, aLoadxmldocumen; "LoadXMLDocumentFromString"
0x180072716  mov     [rbp+57h+var_88], r13
0x18007271a  lea     rax, [rbp+57h+arg_18]
0x18007271e  mov     [rbp+57h+var_80], rax
0x180072722  mov     [rbp+57h+var_78], 0
0x18007272a  mov     [rbp+57h+var_70], 0
0x180072732  xor     r9d, r9d; unsigned int
0x180072735  mov     r8d, 9Ch; char *
0x18007273b  mov     rdx, r13; char *
0x18007273e  lea     rbx, aOnecoreuapDsEx_65; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180072745  mov     rcx, rbx; this
0x180072748  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18007274d  nop
0x18007274e  mov     rax, [r14]
0x180072751  cmp     dword ptr [rax-10h], 0
0x180072755  jg      short loc_180072783
0x180072757  mov     r9d, 8000FFFFh; int
0x18007275d  mov     [rbp+57h+arg_18], r9d
0x180072761  lea     rax, aStrtextGetleng; "strText.GetLength() > 0"
0x180072768  mov     [rsp+110h+ppv], rax; char *
0x18007276d  mov     r8d, 9Fh; unsigned int
0x180072773  mov     rcx, rbx; char *
0x180072776  mov     rdx, r13; char *
0x180072779  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18007277e  jmp     loc_180072A2C
0x180072783  lea     rax, [rsp+110h+var_E0]
0x180072788  mov     [rsp+110h+ppv], rax; ppv
0x18007278d  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180072794  xor     edx, edx; pUnkOuter
0x180072796  lea     r8d, [rdx+17h]; dwClsContext
0x18007279a  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800727a1  call    cs:__imp_CoCreateInstance
0x1800727a7  mov     [rbp+57h+arg_18], eax
0x1800727aa  test    eax, eax
0x1800727ac  jns     short loc_1800727C5
0x1800727ae  lea     rcx, aHrPdocumentCoc; "hr = pDocument.CoCreateInstance(CLSID_D"...
0x1800727b5  mov     [rsp+110h+ppv], rcx
0x1800727ba  mov     r9d, eax
0x1800727bd  mov     r8d, 0A1h
0x1800727c3  jmp     short loc_180072773
0x1800727c5  mov     rcx, [rsp+110h+var_E0]
0x1800727ca  mov     rax, [rcx]
0x1800727cd  or      ebx, 0FFFFFFFFh
0x1800727d0  mov     edx, ebx
0x1800727d2  mov     rax, [rax+1F8h]
0x1800727d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727de  mov     rcx, [rsp+110h+var_E0]
0x1800727e3  mov     rax, [rcx]
0x1800727e6  xor     edx, edx
0x1800727e8  mov     rax, [rax+220h]
0x1800727ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727f4  mov     rcx, [rsp+110h+var_E0]
0x1800727f9  mov     rax, [rcx]
0x1800727fc  mov     edx, ebx
0x1800727fe  mov     rax, [rax+240h]
0x180072805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007280a  mov     rcx, [rsp+110h+var_E0]
0x18007280f  mov     rax, [rcx]
0x180072812  xor     edx, edx
0x180072814  mov     rax, [rax+230h]
0x18007281b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072820  mov     rdi, [rsp+110h+var_E0]
0x180072825  mov     rax, [rdi]
0x180072828  mov     rbx, [rax+280h]
0x18007282f  movups  xmm6, xmmword ptr [r15]
0x180072833  movsd   xmm7, qword ptr [r15+10h]
0x180072839  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180072840  lea     rcx, [rbp+57h+bstrString]; this
0x180072844  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180072849  nop
0x18007284a  movaps  xmmword ptr [rbp+57h+pvarg], xmm6
0x18007284e  movsd   qword ptr [rbp+57h+pvarg+10h], xmm7
0x180072853  lea     r8, [rbp+57h+pvarg]
0x180072857  mov     rdx, [rax]
0x18007285a  mov     rcx, rdi
0x18007285d  mov     rax, rbx
0x180072860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072865  mov     ebx, eax
0x180072867  mov     [rbp+57h+arg_18], eax
0x18007286a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18007286e  call    cs:__imp_SysFreeString
0x180072874  test    ebx, ebx
0x180072876  jns     short loc_180072899
0x180072878  lea     rax, aHrPdocumentSet; "hr = pDocument->setProperty(CComBSTR(XM"...
0x18007287f  mov     [rsp+110h+ppv], rax
0x180072884  mov     r9d, ebx
0x180072887  mov     r8d, 0A8h
0x18007288d  lea     rcx, aOnecoreuapDsEx_65; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180072894  jmp     loc_180072776
0x180072899  lea     rax, ??_7CReadStreamOnMemory@@6B@; const CReadStreamOnMemory::`vftable'
0x1800728a0  mov     [rbp+57h+var_A0], rax
0x1800728a4  mov     [rbp+57h+var_98], 0
0x1800728ac  mov     [rbp+57h+var_90], 0
0x1800728b3  xor     eax, eax
0x1800728b5  mov     word ptr [rbp+57h+bstrString], ax
0x1800728b9  mov     rax, [r14]
0x1800728bc  mov     ecx, [rax-10h]
0x1800728bf  mov     [rbp+57h+var_98], rax
0x1800728c3  mov     [rbp+57h+var_90], ecx
0x1800728c6  mov     eax, 0Dh
0x1800728cb  mov     word ptr [rbp+57h+pvarg], ax
0x1800728cf  lea     rax, [rbp+57h+var_A0]
0x1800728d3  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800728d7  lea     rcx, [rbp+57h+var_A0]; this
0x1800728db  call    ?GetClientCert@CPPCRLBaseRequest@@UEAAJAEAVSmartPCCERT_CONTEXT@@@Z; CPPCRLBaseRequest::GetClientCert(SmartPCCERT_CONTEXT &)
0x1800728e0  nop
0x1800728e1  mov     rcx, [rsp+110h+var_E0]
0x1800728e6  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800728ea  movaps  [rbp+57h+var_60], xmm0
0x1800728ee  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800728f3  movsd   [rbp+57h+var_50], xmm1
0x1800728f8  mov     rax, [rcx]
0x1800728fb  lea     r8, [rbp+57h+bstrString]
0x1800728ff  lea     rdx, [rbp+57h+var_60]
0x180072903  mov     rax, [rax+1D0h]
0x18007290a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007290f  mov     [rbp+57h+arg_18], eax
0x180072912  test    eax, eax
0x180072914  jns     short loc_18007294A
0x180072916  lea     rcx, aHrPdocumentLoa; "hr = pDocument->load(varStream, &bIsOk)"
0x18007291d  mov     [rsp+110h+ppv], rcx; char *
0x180072922  mov     r9d, eax; int
0x180072925  mov     r8d, 0B1h; unsigned int
0x18007292b  mov     rdx, r13; char *
0x18007292e  lea     rcx, aOnecoreuapDsEx_65; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180072935  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18007293a  nop
0x18007293b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007293f  call    cs:__imp_VariantClear
0x180072945  jmp     loc_180072A2C
0x18007294a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007294e  call    cs:__imp_VariantClear
0x180072954  or      eax, 0FFFFFFFFh
0x180072957  cmp     word ptr [rbp+57h+bstrString], ax
0x18007295b  jz      loc_180072A07
0x180072961  mov     [rbp+57h+var_D0], 0
0x180072969  mov     [rbp+57h+var_C8], 0
0x180072971  mov     [rsp+110h+var_D8], eax
0x180072975  mov     rcx, [rsp+110h+var_E0]
0x18007297a  mov     rax, [rcx]
0x18007297d  lea     rdx, [rbp+57h+var_D0]
0x180072981  mov     rax, [rax+1E0h]
0x180072988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007298d  mov     rcx, [rbp+57h+var_D0]
0x180072991  test    rcx, rcx
0x180072994  jz      short loc_1800729EA
0x180072996  mov     rax, [rcx]
0x180072999  lea     rdx, [rbp+57h+var_C8]
0x18007299d  mov     rax, [rax+48h]
0x1800729a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729a6  mov     rcx, [rbp+57h+var_D0]
0x1800729aa  mov     rax, [rcx]
0x1800729ad  lea     rdx, [rsp+110h+var_D8]
0x1800729b2  mov     rax, [rax+58h]
0x1800729b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729bb  mov     rax, [rbp+57h+var_C8]
0x1800729bf  mov     [rsp+110h+var_E8], rax
0x1800729c4  mov     eax, [rsp+110h+var_D8]
0x1800729c8  mov     dword ptr [rsp+110h+ppv], eax
0x1800729cc  lea     r9, aXmlLoadForText; "XML load for text failed at %d: %ls."
0x1800729d3  mov     r8d, 0C0h; unsigned int
0x1800729d9  lea     rdx, aOnecoreuapDsEx_65; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800729e0  mov     ecx, 2; unsigned __int8
0x1800729e5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800729ea  mov     [rbp+57h+arg_18], 80048103h
0x1800729f1  mov     rcx, [rbp+57h+var_C8]; bstrString
0x1800729f5  call    cs:__imp_SysFreeString
0x1800729fb  nop
0x1800729fc  lea     rcx, [rbp+57h+var_D0]
0x180072a00  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180072a05  jmp     short loc_180072A2C
0x180072a07  mov     rbx, [rsp+110h+var_E0]
0x180072a0c  mov     [rsp+110h+var_E0], 0
0x180072a15  mov     rcx, [rsi]
0x180072a18  test    rcx, rcx
0x180072a1b  jz      short loc_180072A29
0x180072a1d  mov     rax, [rcx]
0x180072a20  mov     rax, [rax+10h]
0x180072a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a29  mov     [rsi], rbx
0x180072a2c  mov     ebx, [rbp+57h+arg_18]
0x180072a2f  lea     rcx, [rbp+57h+var_88]
0x180072a33  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180072a38  nop
0x180072a39  lea     rcx, [rsp+110h+var_E0]
0x180072a3e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180072a43  mov     eax, ebx
0x180072a45  lea     r11, [rsp+110h+var_20]
0x180072a4d  mov     rbx, [r11+38h]
0x180072a51  mov     rsi, [r11+40h]
0x180072a55  movaps  xmm6, xmmword ptr [r11-10h]
0x180072a5a  movaps  xmm7, xmmword ptr [r11-20h]
0x180072a5f  mov     rsp, r11
0x180072a62  pop     r15
0x180072a64  pop     r14
0x180072a66  pop     r13
0x180072a68  pop     rdi
0x180072a69  pop     rbp
0x180072a6a  retn
```
