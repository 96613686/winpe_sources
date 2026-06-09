# CWorkspaceManager::ReadInWCXFile(ushort const *,WCXInfo &)

- ea: `0x180033718`
- end: `0x18003421e`
- name: `?ReadInWCXFile@CWorkspaceManager@@SAJPEBGAEAUWCXInfo@@@Z`
- size: `2822`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct WCXInfo *)`
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023e40`
- `0x180040bd0`

## callees

- `0x180005374`
- `0x180007598`
- `0x18000b1d8`
- `0x18000d948`
- `0x18000dbdc`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000ff00`
- `0x18001e610`
- `0x18001e974`
- `0x180020964`
- `0x180020bf0`
- `0x1800274e8`
- `0x180027e1c`
- `0x180027e9c`
- `0x180027ef8`
- `0x1800288ec`
- `0x1800289a8`
- `0x18002945c`
- `0x180033718`
- `0x18003acd4`
- `0x18003ae04`
- `0x18003b07c`
- `0x18003c9f4`
- `0x1800461b0`
- `0x18009a520`
- `0x18009a5e0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180033897`
- `ole32!CoCreateInstance` at `0x180033928`
- `ole32!CoCreateInstance` at `0x180033897`
- `ole32!CoCreateInstance` at `0x180033928`
- `OLEAUT32!__imp_SysAllocString` at `0x180033b63`
- `OLEAUT32!__imp_SysAllocString` at `0x180033b63`
- `OLEAUT32!__imp_SysFreeString` at `0x180033e97`
- `OLEAUT32!__imp_SysFreeString` at `0x18003415a`
- `OLEAUT32!__imp_SysFreeString` at `0x180033e97`
- `OLEAUT32!__imp_SysFreeString` at `0x18003415a`
- `OLEAUT32!__imp_VariantInit` at `0x180033782`
- `OLEAUT32!__imp_VariantInit` at `0x180033782`
- `OLEAUT32!__imp_VariantClear` at `0x180033b50`
- `OLEAUT32!__imp_VariantClear` at `0x180033bb4`
- `OLEAUT32!__imp_VariantClear` at `0x1800341be`
- `OLEAUT32!__imp_VariantClear` at `0x1800341c9`
- `OLEAUT32!__imp_VariantClear` at `0x180033b50`
- `OLEAUT32!__imp_VariantClear` at `0x180033bb4`
- `OLEAUT32!__imp_VariantClear` at `0x1800341be`
- `OLEAUT32!__imp_VariantClear` at `0x1800341c9`
- `SHELL32!SHGetKnownFolderPath` at `0x180033bdf`
- `SHELL32!SHGetKnownFolderPath` at `0x180033bdf`

## string_xrefs

- `0x1800338db`: `failed to CoCreate DOMDocument`
- `0x18003396c`: `CoCreateInstance XMLSchemaCache60 failed`
- `0x1800339cc`: `IXmlDOMDocument::put_async failed`
- `0x180033a2c`: `IXmlDOMDocument::put_validateOnParse failed`
- `0x180033a62`: `MaxXMLSize`
- `0x180033ab3`: `IXmlDOMDocument::setProperty  MaxXMLSize failed`
- `0x180033b31`: `IXmlDOMDocument::setProperty ResolveExternals failed`
- `0x180033c1e`: `SHGetKnownFolderPath failed`
- `0x180033ca5`: `TSWFileURLFromPath failed`
- `0x180033d70`: `IXMLDOMSchemaCollection::add failed`
- `0x180033e00`: `IXmlDOMDocument::putref_schemas failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall CWorkspaceManager::ReadInWCXFile(const unsigned __int16 *a1, struct WCXInfo *a2)
{
  int Instance; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  LPVOID v9; // rbx
  __int64 v10; // rdi
  int v11; // ebx
  const unsigned __int16 *v12; // rcx
  struct IDispatch *v13; // rbx
  HRESULT (__stdcall *QueryInterface)(IDispatch *, const IID *const, void **); // rdi
  const struct _bstr_t *v15; // rax
  _variant_t *v16; // rax
  __int128 v17; // xmm6
  IRecordInfo *v18; // xmm7_8
  const char *v19; // rdx
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  bool v22; // r8
  LPVOID v23; // rdi
  __int64 (__fastcall *v24)(LPVOID, VARIANTARG *); // rbx
  BSTR v25; // rbx
  unsigned int v26; // eax
  struct IUnknown **v27; // rbx
  bool v28; // bl
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // eax
  int v32; // edi
  unsigned int v33; // eax
  BSTR v34; // rbx
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int16 v38; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown **v41; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+74h] [rbp-8Ch]
  struct IDispatch *v45; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v46; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v47; // [rsp+88h] [rbp-78h] BYREF
  int v48; // [rsp+90h] [rbp-70h]
  int v49; // [rsp+94h] [rbp-6Ch]
  struct IUnknown *v50; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v51; // [rsp+A0h] [rbp-60h] BYREF
  int v52; // [rsp+A8h] [rbp-58h]
  int v53; // [rsp+ACh] [rbp-54h]
  __int64 v54; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  void *v56; // [rsp+C0h] [rbp-40h]
  PWSTR ppszPath; // [rsp+C8h] [rbp-38h] BYREF
  void *v58; // [rsp+D0h] [rbp-30h]
  _BYTE v59[16]; // [rsp+D8h] [rbp-28h] BYREF
  int v60; // [rsp+E8h] [rbp-18h]
  VARIANTARG v61; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+8h] BYREF
  __int64 v63; // [rsp+120h] [rbp+20h]
  VARIANTARG v64; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v65[3]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v66; // [rsp+168h] [rbp+68h]
  unsigned __int16 v67[2088]; // [rsp+170h] [rbp+70h] BYREF

  v63 = -2;
  v44 = 0;
  v38 = 0;
  VariantInit(&pvarg);
  v61.vt = 11;
  v61.iVal = 0;
  ppv = 0;
  v45 = 0;
  v55 = 0;
  v54 = 0;
  ppszPath = 0;
  v43 = 0;
  v66 = 7;
  v65[2] = 0;
  LOWORD(v65[0]) = 0;
  v41 = &v50;
  v50 = 0;
  bstrString = (BSTR)&v51;
  v51 = 0;
  v52 = -1;
  v53 = 0;
  v58 = &v46;
  v46 = 0;
  v56 = &v47;
  v47 = 0;
  v48 = -1;
  v49 = 0;
  if ( !a1 )
  {
    Instance = -2147024894;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024894);
    }
    goto LABEL_101;
  }
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               0x17u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               &ppv);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 61;
    v8 = "failed to CoCreate DOMDocument";
    goto LABEL_11;
  }
  Instance = CoCreateInstance(
               &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
               0,
               3u,
               &GUID_373984c8_b845_449b_91e7_45ac83036ade,
               (LPVOID *)&v45);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 62;
    v8 = "CoCreateInstance XMLSchemaCache60 failed";
    goto LABEL_11;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 63;
    v8 = "IXmlDOMDocument::put_async failed";
    goto LABEL_11;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 64;
    v8 = "IXmlDOMDocument::put_validateOnParse failed";
    goto LABEL_11;
  }
  ATL::CComVariant::operator=(&pvarg);
  v42 = pvarg;
  Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppv + 640LL))(
               ppv,
               L"MaxXMLSize",
               &v42);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 65;
    v8 = "IXmlDOMDocument::setProperty  MaxXMLSize failed";
    goto LABEL_11;
  }
  v42 = v61;
  Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)ppv + 640LL))(
               ppv,
               L"ResolveExternals",
               &v42);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_101;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 66;
    v8 = "IXmlDOMDocument::setProperty ResolveExternals failed";
    goto LABEL_11;
  }
  v9 = ppv;
  v10 = *(_QWORD *)ppv;
  v42.vt = 0;
  VariantClear(&v42);
  v42.vt = 8;
  v42.llVal = (LONGLONG)SysAllocString(a1);
  if ( !v42.llVal )
  {
    v42.vt = 10;
    v42.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v64 = v42;
  v11 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v10 + 464))(v9, &v64, &v38);
  VariantClear(&v42);
  if ( v11 == 1 || !v38 )
  {
    v41 = 0;
    bstrString = 0;
    v32 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown ***))(*(_QWORD *)ppv + 480LL))(ppv, &v41);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v33);
    }
    if ( v32 >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown **, BSTR *))(*v41)[9].lpVtbl)(v41, &bstrString);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = bstrString;
        v35 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v35,
          (__int64)v34);
      }
    }
    Instance = -2147467259;
    SysFreeString(bstrString);
    ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&v41);
  }
  else
  {
    Instance = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 69;
      v8 = "SHGetKnownFolderPath failed";
      goto LABEL_11;
    }
    std::wstring::assign(v65, ppszPath);
    std::wstring::append(v65, L"\\schemas\\tsworkspace\\tswcx.xsd");
    v43 = 2084;
    v12 = (const unsigned __int16 *)v65;
    if ( v66 >= 8 )
      v12 = v65[0];
    Instance = TSWFileURLFromPath(v12, v67, &v43);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 70;
      v8 = "TSWFileURLFromPath failed";
      goto LABEL_11;
    }
    v13 = v45;
    QueryInterface = v45->lpVtbl[1].QueryInterface;
    v15 = _bstr_t::_bstr_t((_bstr_t *)&bstrString, v67);
    v16 = _variant_t::_variant_t((_variant_t *)&v42, v15);
    v17 = *(_OWORD *)v16;
    v18 = (IRecordInfo *)*((_QWORD *)v16 + 2);
    v20 = _bstr_t::_bstr_t((_bstr_t *)&v41, v19);
    if ( *(_QWORD *)v20 )
      v21 = **(_QWORD **)v20;
    else
      v21 = 0;
    *(_OWORD *)&v64.vt = v17;
    v64.pRecInfo = v18;
    Instance = ((__int64 (__fastcall *)(struct IDispatch *, __int64, VARIANTARG *))QueryInterface)(v13, v21, &v64);
    _bstr_t::_Free((_bstr_t *)&v41);
    _variant_t::~_variant_t((_variant_t *)&v42);
    _bstr_t::_Free((_bstr_t *)&bstrString);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 71;
      v8 = "IXMLDOMSchemaCollection::add failed";
      goto LABEL_11;
    }
    v23 = ppv;
    v24 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 624LL);
    v64 = *(VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v42, v45, v22);
    Instance = v24(v23, &v64);
    _variant_t::~_variant_t((_variant_t *)&v42);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_101;
      }
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 72;
      v8 = "IXmlDOMDocument::putref_schemas failed";
      goto LABEL_11;
    }
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 632LL))(ppv, &v54);
    if ( Instance )
    {
      bstrString = 0;
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v54 + 72LL))(v54, &bstrString);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = bstrString;
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          73,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v26,
          (__int64)v25);
      }
      SysFreeString(bstrString);
    }
    else
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v55);
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_101;
        }
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 74;
        v8 = "failed to get_documentElement";
LABEL_11:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
          v6,
          (__int64)v8,
          Instance);
        goto LABEL_101;
      }
      v27 = (struct IUnknown **)ATL::CComPtr<IXMLDOMElement>::CComPtr<IXMLDOMElement>(&v41, &v55);
      v58 = v27;
      if ( v50 != *v27 )
        ATL::AtlComPtrAssign(&v50, *v27);
      TElem::get(&v50);
      ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(v27);
      if ( v46 != v50 )
        ATL::AtlComPtrAssign(&v46, v50);
      if ( v47 != v51 )
        ATL::AtlComPtrAssign(&v47, v51);
      v48 = v52;
      v49 = v53;
      Instance = 1;
      TElem::begin(&v46, v59);
      v56 = &v42;
      *(_OWORD *)&v42.vt = 0u;
      v58 = &v42.decVal.8;
      *((_DWORD *)&v42.decVal + 4) = -1;
      *((_DWORD *)&v42.decVal + 5) = v49;
      v28 = v60 != v49;
      v44 = 0;
      TElem::~TElem((TElem *)&v42);
      if ( v28 )
      {
        v56 = &v42;
        v29 = std::wstring::wstring(&v42, L"url");
        TElem::attr(v59, &v64, v29);
        if ( (unsigned int)std::wstring::compare(&v64, &LocaleName) )
        {
          std::wstring::operator=(a2, &v64);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v31, 1);
        }
        LOBYTE(v30) = 1;
        std::wstring::_Tidy(&v64, v30, 0);
      }
      TElem::~TElem((TElem *)v59);
    }
  }
LABEL_101:
  TElem::~TElem((TElem *)&v46);
  TElem::~TElem((TElem *)&v50);
  LOBYTE(v36) = 1;
  std::wstring::_Tidy(v65, v36, 0);
  ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&v54);
  ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&v55);
  ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&v45);
  ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&ppv);
  VariantClear(&v61);
  VariantClear(&pvarg);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180033718  push    rbp
0x18003371a  push    rsi
0x18003371b  push    rdi
0x18003371c  push    r12
0x18003371e  push    r13
0x180033720  push    r14
0x180033722  push    r15
0x180033724  lea     rbp, [rsp-10F0h]
0x18003372c  mov     eax, 11F0h
0x180033731  call    _alloca_probe
0x180033736  sub     rsp, rax
0x180033739  mov     [rbp+1120h+var_1100], 0FFFFFFFFFFFFFFFEh
0x180033741  mov     [rsp+1220h+arg_10], rbx
0x180033749  movaps  [rsp+1220h+var_40], xmm6
0x180033751  movaps  [rsp+1220h+var_50], xmm7
0x180033759  mov     rax, cs:__security_cookie
0x180033760  xor     rax, rsp
0x180033763  mov     [rbp+1120h+var_60], rax
0x18003376a  mov     r15, rdx
0x18003376d  mov     r14, rcx
0x180033770  xor     r12d, r12d
0x180033773  mov     [rsp+1220h+var_11AC], r12d
0x180033778  mov     [rsp+1220h+var_11F0], r12w
0x18003377e  lea     rcx, [rbp+1120h+pvarg]; pvarg
0x180033782  call    cs:__imp_VariantInit
0x180033788  nop
0x180033789  lea     eax, [r12+0Bh]
0x18003378e  mov     word ptr [rbp+1120h+var_1130], ax
0x180033792  mov     word ptr [rbp+1120h+var_1130+8], r12w
0x180033797  mov     [rsp+1220h+var_11E8], r12
0x18003379c  mov     [rsp+1220h+var_11A8], r12
0x1800337a1  mov     [rbp+1120h+var_1168], r12
0x1800337a5  mov     [rbp+1120h+var_1170], r12
0x1800337a9  mov     [rbp+1120h+ppszPath], r12
0x1800337ad  mov     [rsp+1220h+var_11B0], r12d
0x1800337b2  mov     [rbp+1120h+var_10C0], r12
0x1800337b6  mov     [rbp+1120h+var_10B8], r12
0x1800337ba  mov     [rbp+1120h+var_10B8], 7
0x1800337c2  mov     [rbp+1120h+var_10C0], r12
0x1800337c6  mov     word ptr [rbp+1120h+var_10D0], r12w
0x1800337cb  lea     rax, [rbp+1120h+var_1188]
0x1800337cf  mov     [rsp+1220h+var_11D8], rax
0x1800337d4  mov     [rbp+1120h+var_1188], r12
0x1800337d8  lea     rax, [rbp+1120h+var_1180]
0x1800337dc  mov     [rsp+1220h+bstrString], rax
0x1800337e1  mov     [rbp+1120h+var_1180], r12
0x1800337e5  or      ecx, 0FFFFFFFFh
0x1800337e8  mov     [rbp+1120h+var_1178], ecx
0x1800337eb  mov     [rbp+1120h+var_1174], r12d
0x1800337ef  lea     rax, [rbp+1120h+var_11A0]
0x1800337f3  mov     [rbp+1120h+var_1150], rax
0x1800337f7  mov     [rbp+1120h+var_11A0], r12
0x1800337fb  lea     rax, [rbp+1120h+var_1198]
0x1800337ff  mov     [rbp+1120h+var_1160], rax
0x180033803  mov     [rbp+1120h+var_1198], r12
0x180033807  mov     [rbp+1120h+var_1190], ecx
0x18003380a  mov     [rbp+1120h+var_118C], r12d
0x18003380e  lea     r13d, [r12+1]
0x180033813  test    r14, r14
0x180033816  jnz     short loc_180033879
0x180033818  mov     edi, 80070002h
0x18003381d  lea     rbx, WPP_GLOBAL_Control
0x180033824  mov     rax, cs:WPP_GLOBAL_Control
0x18003382b  cmp     rax, rbx
0x18003382e  jz      loc_18003416C
0x180033834  test    [rax+1Ch], r13b
0x180033838  jz      loc_18003416C
0x18003383e  cmp     byte ptr [rax+19h], 2
0x180033842  jb      loc_18003416C
0x180033848  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003384d  lea     edx, [r12+3Ch]
0x180033852  mov     dword ptr [rsp+1220h+ppv], 80070002h
0x18003385a  mov     r9d, eax
0x18003385d  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180033864  mov     rcx, cs:WPP_GLOBAL_Control
0x18003386b  mov     rcx, [rcx+10h]
0x18003386f  call    WPP_SF_Dd
0x180033874  jmp     loc_18003416C
0x180033879  lea     rax, [rsp+1220h+var_11E8]
0x18003387e  mov     [rsp+1220h+ppv], rax; ppv
0x180033883  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18003388a  xor     edx, edx; pUnkOuter
0x18003388c  lea     r8d, [rdx+17h]; dwClsContext
0x180033890  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180033897  call    cs:__imp_CoCreateInstance
0x18003389d  mov     edi, eax
0x18003389f  test    eax, eax
0x1800338a1  jns     short loc_18003390A
0x1800338a3  lea     rbx, WPP_GLOBAL_Control
0x1800338aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800338b1  cmp     rax, rbx
0x1800338b4  jz      loc_18003416C
0x1800338ba  mov     esi, 8
0x1800338bf  test    [rax+1Ch], sil
0x1800338c3  jz      loc_18003416C
0x1800338c9  cmp     byte ptr [rax+19h], 2
0x1800338cd  jb      loc_18003416C
0x1800338d3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800338d8  lea     edx, [rsi+35h]
0x1800338db  lea     rcx, aFailedToCocrea; "failed to CoCreate DOMDocument"
0x1800338e2  mov     [rsp+1220h+var_11F8], edi
0x1800338e6  mov     [rsp+1220h+ppv], rcx
0x1800338eb  mov     r9d, eax
0x1800338ee  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800338f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338fc  mov     rcx, [rcx+10h]
0x180033900  call    WPP_SF_DsD
0x180033905  jmp     loc_18003416C
0x18003390a  lea     rax, [rsp+1220h+var_11A8]
0x18003390f  mov     [rsp+1220h+ppv], rax; ppv
0x180033914  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x18003391b  xor     edx, edx; pUnkOuter
0x18003391d  lea     r8d, [rdx+3]; dwClsContext
0x180033921  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180033928  call    cs:__imp_CoCreateInstance
0x18003392e  mov     edi, eax
0x180033930  test    eax, eax
0x180033932  jns     short loc_180033978
0x180033934  lea     rbx, WPP_GLOBAL_Control
0x18003393b  mov     rax, cs:WPP_GLOBAL_Control
0x180033942  cmp     rax, rbx
0x180033945  jz      loc_18003416C
0x18003394b  mov     esi, 8
0x180033950  test    [rax+1Ch], sil
0x180033954  jz      loc_18003416C
0x18003395a  cmp     byte ptr [rax+19h], 2
0x18003395e  jb      loc_18003416C
0x180033964  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033969  lea     edx, [rsi+36h]
0x18003396c  lea     rcx, aCocreateinstan; "CoCreateInstance XMLSchemaCache60 faile"...
0x180033973  jmp     loc_1800338E2
0x180033978  mov     rcx, [rsp+1220h+var_11E8]
0x18003397d  mov     rax, [rcx]
0x180033980  xor     edx, edx
0x180033982  mov     rax, [rax+1F8h]
0x180033989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003398e  mov     edi, eax
0x180033990  test    eax, eax
0x180033992  jns     short loc_1800339D8
0x180033994  lea     rbx, WPP_GLOBAL_Control
0x18003399b  mov     rax, cs:WPP_GLOBAL_Control
0x1800339a2  cmp     rax, rbx
0x1800339a5  jz      loc_18003416C
0x1800339ab  mov     esi, 8
0x1800339b0  test    [rax+1Ch], sil
0x1800339b4  jz      loc_18003416C
0x1800339ba  cmp     byte ptr [rax+19h], 2
0x1800339be  jb      loc_18003416C
0x1800339c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800339c9  lea     edx, [rsi+37h]
0x1800339cc  lea     rcx, aIxmldomdocumen_4; "IXmlDOMDocument::put_async failed"
0x1800339d3  jmp     loc_1800338E2
0x1800339d8  mov     rcx, [rsp+1220h+var_11E8]
0x1800339dd  mov     rax, [rcx]
0x1800339e0  xor     edx, edx
0x1800339e2  mov     rax, [rax+220h]
0x1800339e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339ee  mov     edi, eax
0x1800339f0  test    eax, eax
0x1800339f2  jns     short loc_180033A38
0x1800339f4  lea     rbx, WPP_GLOBAL_Control
0x1800339fb  mov     rax, cs:WPP_GLOBAL_Control
0x180033a02  cmp     rax, rbx
0x180033a05  jz      loc_18003416C
0x180033a0b  mov     esi, 8
0x180033a10  test    [rax+1Ch], sil
0x180033a14  jz      loc_18003416C
0x180033a1a  cmp     byte ptr [rax+19h], 2
0x180033a1e  jb      loc_18003416C
0x180033a24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033a29  lea     edx, [rsi+38h]
0x180033a2c  lea     rcx, aIxmldomdocumen_6; "IXmlDOMDocument::put_validateOnParse fa"...
0x180033a33  jmp     loc_1800338E2
0x180033a38  lea     rcx, [rbp+1120h+pvarg]
0x180033a3c  call    ??4CComVariant@ATL@@QEAAAEAV01@H@Z; ATL::CComVariant::operator=(int)
0x180033a41  mov     rcx, [rsp+1220h+var_11E8]
0x180033a46  movups  xmm0, xmmword ptr [rbp+1120h+pvarg]
0x180033a4a  movaps  xmmword ptr [rsp+1220h+var_11D0], xmm0
0x180033a4f  movsd   xmm1, qword ptr [rbp+1120h+pvarg+10h]
0x180033a54  movsd   qword ptr [rsp+1220h+var_11D0+10h], xmm1
0x180033a5a  mov     rax, [rcx]
0x180033a5d  lea     r8, [rsp+1220h+var_11D0]
0x180033a62  lea     rdx, aMaxxmlsize; "MaxXMLSize"
0x180033a69  mov     rax, [rax+280h]
0x180033a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a75  mov     edi, eax
0x180033a77  test    eax, eax
0x180033a79  jns     short loc_180033ABF
0x180033a7b  lea     rbx, WPP_GLOBAL_Control
0x180033a82  mov     rax, cs:WPP_GLOBAL_Control
0x180033a89  cmp     rax, rbx
0x180033a8c  jz      loc_18003416C
0x180033a92  mov     esi, 8
0x180033a97  test    [rax+1Ch], sil
0x180033a9b  jz      loc_18003416C
0x180033aa1  cmp     byte ptr [rax+19h], 2
0x180033aa5  jb      loc_18003416C
0x180033aab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033ab0  lea     edx, [rsi+39h]
0x180033ab3  lea     rcx, aIxmldomdocumen_1; "IXmlDOMDocument::setProperty  MaxXMLSiz"...
0x180033aba  jmp     loc_1800338E2
0x180033abf  mov     rcx, [rsp+1220h+var_11E8]
0x180033ac4  movups  xmm0, xmmword ptr [rbp+1120h+var_1130]
0x180033ac8  movaps  xmmword ptr [rsp+1220h+var_11D0], xmm0
0x180033acd  movsd   xmm1, qword ptr [rbp+1120h+var_1130+10h]
0x180033ad2  movsd   qword ptr [rsp+1220h+var_11D0+10h], xmm1
0x180033ad8  mov     rax, [rcx]
0x180033adb  lea     r8, [rsp+1220h+var_11D0]
0x180033ae0  lea     rdx, aResolveexterna; "ResolveExternals"
0x180033ae7  mov     rax, [rax+280h]
0x180033aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af3  mov     edi, eax
0x180033af5  test    eax, eax
0x180033af7  jns     short loc_180033B3D
0x180033af9  lea     rbx, WPP_GLOBAL_Control
0x180033b00  mov     rax, cs:WPP_GLOBAL_Control
0x180033b07  cmp     rax, rbx
0x180033b0a  jz      loc_18003416C
0x180033b10  mov     esi, 8
0x180033b15  test    [rax+1Ch], sil
0x180033b19  jz      loc_18003416C
0x180033b1f  cmp     byte ptr [rax+19h], 2
0x180033b23  jb      loc_18003416C
0x180033b29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033b2e  lea     edx, [rsi+3Ah]
0x180033b31  lea     rcx, aIxmldomdocumen_2; "IXmlDOMDocument::setProperty ResolveExt"...
0x180033b38  jmp     loc_1800338E2
0x180033b3d  mov     rbx, [rsp+1220h+var_11E8]
0x180033b42  mov     rdi, [rbx]
0x180033b45  mov     word ptr [rsp+1220h+var_11D0], r12w
0x180033b4b  lea     rcx, [rsp+1220h+var_11D0]; pvarg
0x180033b50  call    cs:__imp_VariantClear
0x180033b56  mov     esi, 8
0x180033b5b  mov     word ptr [rsp+1220h+var_11D0], si
0x180033b60  mov     rcx, r14; psz
0x180033b63  call    cs:__imp_SysAllocString
0x180033b69  mov     dword ptr [rsp+1220h+var_11D0+8], eax
0x180033b6d  mov     rcx, rax
0x180033b70  sar     rcx, 20h
0x180033b74  mov     dword ptr [rsp+1220h+var_11D0+0Ch], ecx
0x180033b78  test    rax, rax
0x180033b7b  jz      loc_180034205
0x180033b81  movups  xmm0, xmmword ptr [rsp+1220h+var_11D0]
0x180033b86  movaps  [rbp+1120h+var_10F0], xmm0
0x180033b8a  movsd   xmm1, qword ptr [rsp+1220h+var_11D0+10h]
0x180033b90  movsd   [rbp+1120h+var_10E0], xmm1
0x180033b95  lea     r8, [rsp+1220h+var_11F0]
0x180033b9a  lea     rdx, [rbp+1120h+var_10F0]
0x180033b9e  mov     rcx, rbx
0x180033ba1  mov     rax, [rdi+1D0h]
0x180033ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bad  mov     ebx, eax
0x180033baf  lea     rcx, [rsp+1220h+var_11D0]; pvarg
0x180033bb4  call    cs:__imp_VariantClear
0x180033bba  cmp     ebx, r13d
0x180033bbd  jz      loc_180034088
0x180033bc3  cmp     [rsp+1220h+var_11F0], r12w
0x180033bc9  jz      loc_180034088
0x180033bcf  lea     r9, [rbp+1120h+ppszPath]; ppszPath
0x180033bd3  xor     r8d, r8d; hToken
0x180033bd6  xor     edx, edx; dwFlags
0x180033bd8  lea     rcx, FOLDERID_Windows; rfid
0x180033bdf  call    cs:__imp_SHGetKnownFolderPath
0x180033be5  mov     edi, eax
0x180033be7  test    eax, eax
0x180033be9  jns     short loc_180033C2A
0x180033beb  lea     rbx, WPP_GLOBAL_Control
0x180033bf2  mov     rax, cs:WPP_GLOBAL_Control
0x180033bf9  cmp     rax, rbx
0x180033bfc  jz      loc_18003416C
0x180033c02  test    [rax+1Ch], sil
0x180033c06  jz      loc_18003416C
0x180033c0c  cmp     byte ptr [rax+19h], 2
0x180033c10  jb      loc_18003416C
0x180033c16  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033c1b  lea     edx, [rsi+3Dh]
0x180033c1e  lea     rcx, aShgetknownfold_0; "SHGetKnownFolderPath failed"
0x180033c25  jmp     loc_1800338E2
0x180033c2a  mov     rdx, [rbp+1120h+ppszPath]
0x180033c2e  lea     rcx, [rbp+1120h+var_10D0]
0x180033c32  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180033c37  lea     rdx, aSchemasTsworks_0; "\\schemas\\tsworkspace\\tswcx.xsd"
0x180033c3e  lea     rcx, [rbp+1120h+var_10D0]
0x180033c42  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180033c47  mov     [rsp+1220h+var_11B0], 824h
0x180033c4f  lea     rcx, [rbp+1120h+var_10D0]
0x180033c53  cmp     [rbp+1120h+var_10B8], rsi
0x180033c57  cmovnb  rcx, [rbp+1120h+var_10D0]; unsigned __int16 *
0x180033c5c  lea     r8, [rsp+1220h+var_11B0]; unsigned int *
0x180033c61  lea     rdx, [rbp+1120h+var_10B0]; unsigned __int16 *
0x180033c65  call    ?TSWFileURLFromPath@@YAJPEBGPEAGPEAK@Z; TSWFileURLFromPath(ushort const *,ushort *,ulong *)
0x180033c6a  mov     edi, eax
0x180033c6c  test    eax, eax
0x180033c6e  jns     short loc_180033CB1
0x180033c70  lea     rbx, WPP_GLOBAL_Control
0x180033c77  mov     rax, cs:WPP_GLOBAL_Control
0x180033c7e  cmp     rax, rbx
0x180033c81  jz      loc_18003416C
0x180033c87  test    [rax+1Ch], sil
0x180033c8b  jz      loc_18003416C
  ... truncated ...
```
