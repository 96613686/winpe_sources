# IASExim::ImportRegistry(ushort *,ushort *,IXMLDOMNode * *)

- ea: `0x18003bc7c`
- end: `0x18003c965`
- name: `?ImportRegistry@IASExim@@AEAAJPEAG0PEAPEAUIXMLDOMNode@@@Z`
- size: `3305`
- prototype: `int(IASExim *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d140`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002efa0`
- `0x18002f08c`
- `0x18002f240`
- `0x1800341e8`
- `0x180039198`
- `0x18003b8ac`
- `0x18003bc7c`
- `0x18003d9b0`
- `0x1800403bc`
- `0x1800404a4`
- `0x1800405a0`
- `0x180041a64`
- `0x1800420f0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `ADVAPI32!RegConnectRegistryW` at `0x18003bd9f`
- `ADVAPI32!RegConnectRegistryW` at `0x18003bd9f`
- `ADVAPI32!RegCloseKey` at `0x18003c918`
- `ADVAPI32!RegCloseKey` at `0x18003c918`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bce3`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bce3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c026`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c030`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c026`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c030`
- `OLEAUT32!__imp_VariantInit` at `0x18003bcd1`
- `OLEAUT32!__imp_VariantInit` at `0x18003c066`
- `OLEAUT32!__imp_VariantInit` at `0x18003c198`
- `OLEAUT32!__imp_VariantInit` at `0x18003bcd1`
- `OLEAUT32!__imp_VariantInit` at `0x18003c066`
- `OLEAUT32!__imp_VariantInit` at `0x18003c198`
- `OLEAUT32!__imp_VariantClear` at `0x18003c922`
- `OLEAUT32!__imp_VariantClear` at `0x18003c922`

## string_xrefs

- `0x18003be0b`: `registryKeys`
- `0x18003c0c1`: `registryValue`
- `0x18003c5bd`: `registryValue`
- `0x18003c5da`: `registryValue`
- `0x18003bdde`: `RegConnectRegistry failed with 0x%x`
- `0x18003bee1`: `pRegistryKeysNode->get_childNodes failed with 0x%x`
- `0x18003c8c5`: `DeleteRegistryValue(%S\%S) failed with 0x%x`
- `0x18003c728`: `pRegistryKeyNode->get_nodeName failed with 0x%x`
- `0x18003c6df`: `pRegistryKeyNode->get_nodeTypeString failed with 0x%x`
- `0x18003c693`: `pRegistryKeyNode->QI(IXMLDOMElement) failed with 0x%x`
- `0x18003c3e2`: `pRegistryKeyElement->getAttribute(%S) failed with 0x%x`
- `0x18003c62f`: `pRegistryKeyElement->getAttribute(%S) failed with 0x%x`
- `0x18003c5c4`: `pRegistryKeyElement->selectSingleNode(%S) failed with 0x%x`
- `0x18003c565`: `pRegistryValueNode->QI(IXMLDOMElement) failed with 0x%x`
- `0x18003c496`: `pRegistryValueElement->getAttribute(%S) failed with 0x%x`
- `0x18003c501`: `pRegistryValueElement->getAttribute(%S) failed with 0x%x`
- `0x18003c2e0`: `SetRegistryValue(%S\%S %S) failed with 0x%x`
- `0x18003c7d9`: `m_pXmlDom->removeChild(pRegistryKeysNode) failed with 0x%x`
- `0x18003c83f`: `m_pXmlDom->save failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall IASExim::ImportRegistry(
        struct IXMLDOMDocument2 **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNode **a4)
{
  signed int DocumentRootElement; // r14d
  LSTATUS v8; // eax
  char v9; // bl
  int v10; // edx
  unsigned int i; // edi
  int v12; // ebx
  int v13; // eax
  __int64 *v14; // rdi
  __int64 v15; // r9
  __int64 *v16; // rbx
  __int64 v17; // r8
  __int64 *v18; // rsi
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // edx
  struct IXMLDOMDocument2 *v25; // rcx
  __int64 v27; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v30; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-98h]
  __int64 *v33; // [rsp+78h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-88h] BYREF
  VARIANTARG v35; // [rsp+88h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-68h] BYREF
  BSTR v37; // [rsp+A8h] [rbp-60h] BYREF
  __int64 *v38; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-50h] BYREF
  struct IXMLDOMElement *v40; // [rsp+C0h] [rbp-48h] BYREF
  char v41[8]; // [rsp+C8h] [rbp-40h]
  __int64 v42; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v43; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-10h] BYREF

  v40 = 0;
  v39 = 0;
  v42 = 0;
  hKey = HKEY_LOCAL_MACHINE;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a3);
  v43 = pvarg;
  DocumentRootElement = GetDocumentRootElement(this[1], &v43, &v40);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetDocumentRootElement failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        DocumentRootElement);
    }
    goto LABEL_140;
  }
  LODWORD(v32) = 0;
  if ( a2 && *a2 )
  {
    v8 = RegConnectRegistryW(a2, hKey, &hKey);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("RegConnectRegistry failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          v9);
      }
      goto LABEL_140;
    }
    LODWORD(v32) = 1;
  }
  DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const unsigned __int16 *, __int64 *))v40->lpVtbl->selectSingleNode)(
                          v40,
                          L"registryKeys",
                          &v39);
  if ( DocumentRootElement )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pRootElement->selectSingleNode failed with 0x%x");
      v10 = 46;
LABEL_19:
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        DocumentRootElement);
    }
  }
  else
  {
    DocumentRootElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 96LL))(v39, &v42);
    if ( DocumentRootElement >= 0 )
    {
      for ( i = 0; i < 0x17; ++i )
      {
        v12 = DeleteRegistryValue(hKey, IASKEYS[3 * (int)i], IASKEYS[3 * (int)i + 1]);
        if ( (v12 & 0xFFFFFFFD) != 0 )
        {
          if ( v12 > 0 )
            DocumentRootElement = (unsigned __int16)v12 | 0x80070000;
          else
            DocumentRootElement = v12;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("DeleteRegistryValue(%S\\%S) failed with 0x%x");
            WPP_SF_sSSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (__int64)IASKEYS[3 * (int)i],
              (__int64)IASKEYS[3 * (int)i + 1],
              v12);
          }
          goto LABEL_138;
        }
      }
      while ( 1 )
      {
        v31 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 72LL))(v42, &v31);
        DocumentRootElement = v13;
        if ( v13 == 1 )
        {
          DocumentRootElement = 0;
          goto LABEL_115;
        }
        if ( v13 < 0 )
          goto LABEL_115;
        bstrString = 0;
        v37 = 0;
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v31 + 56LL))(v31, &bstrString);
        if ( DocumentRootElement < 0 )
          break;
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v31 + 200LL))(v31, &v37);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryKeyNode->get_nodeTypeString failed with 0x%x");
            v24 = 50;
            goto LABEL_109;
          }
          goto LABEL_115;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("Processing nodename: %S nodeType: %S");
          WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)bstrString, (__int64)v37);
        }
        SysFreeString(bstrString);
        SysFreeString(v37);
        v27 = 0;
        DocumentRootElement = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v31)(
                                v31,
                                &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                                &v27);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryKeyNode->QI(IXMLDOMElement) failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              DocumentRootElement);
          }
          goto LABEL_80;
        }
        VariantInit(&v35);
        _variant_t::Clear((_variant_t *)&v35);
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v27 + 352LL))(
                                v27,
                                L"keyName",
                                &v35);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryKeyElement->getAttribute(%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"keyName",
              DocumentRootElement);
          }
          goto LABEL_79;
        }
        _bstr_t::_bstr_t((_bstr_t *)&v30, v35.bstrVal);
        v29 = 0;
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v27 + 296LL))(
                                v27,
                                L"registryValue",
                                &v29);
        if ( DocumentRootElement )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryKeyElement->selectSingleNode(%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"registryValue",
              DocumentRootElement);
          }
          goto LABEL_78;
        }
        v28 = 0;
        DocumentRootElement = (**v29)(v29, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v28);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryValueNode->QI(IXMLDOMElement) failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              DocumentRootElement);
          }
          goto LABEL_77;
        }
        _variant_t::Clear((_variant_t *)&v35);
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v28 + 352LL))(
                                v28,
                                L"name",
                                &v35);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryValueElement->getAttribute(%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"name",
              DocumentRootElement);
          }
          goto LABEL_77;
        }
        _bstr_t::_bstr_t((_bstr_t *)&v33, v35.bstrVal, 1);
        _variant_t::Clear((_variant_t *)&v35);
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)v28 + 352LL))(
                                v28,
                                L"valueType",
                                &v35);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryValueElement->getAttribute(%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              57,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"valueType",
              DocumentRootElement);
          }
          goto LABEL_76;
        }
        _bstr_t::_bstr_t((_bstr_t *)&v38, v35.bstrVal, 1);
        VariantInit(&v43);
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v28 + 352LL))(
                                v28,
                                L"value",
                                &v43);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pRegistryKeyElement->getAttribute(%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"value",
              DocumentRootElement);
          }
          _variant_t::~_variant_t((_variant_t *)&v43);
          _bstr_t::_Free((_bstr_t *)&v38);
LABEL_76:
          _bstr_t::_Free((_bstr_t *)&v33);
LABEL_77:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
LABEL_78:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
          _bstr_t::_Free((_bstr_t *)&v30);
LABEL_79:
          _variant_t::~_variant_t((_variant_t *)&v35);
LABEL_80:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
          goto LABEL_115;
        }
        v14 = v38;
        if ( v38 )
          v15 = *v38;
        else
          v15 = 0;
        v16 = v33;
        if ( v33 )
          v17 = *v33;
        else
          v17 = 0;
        v18 = v30;
        if ( v30 )
          v19 = *v30;
        else
          v19 = 0;
        v20 = SetRegistryValue(hKey, v19, v17, v15, &v43);
        *(_DWORD *)v41 = v20;
        if ( v20 )
        {
          if ( v20 > 0 )
            DocumentRootElement = (unsigned __int16)v20 | 0x80070000;
          else
            DocumentRootElement = v20;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("SetRegistryValue(%S\\%S %S) failed with 0x%x");
            if ( v14 )
              v21 = *v14;
            else
              v21 = 0;
            if ( v16 )
              v22 = *v16;
            else
              v22 = 0;
            if ( v18 )
              v23 = *v18;
            else
              v23 = 0;
            WPP_SF_sSSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v22, v21, v41[0]);
          }
          _variant_t::~_variant_t((_variant_t *)&v43);
          _bstr_t::_Free((_bstr_t *)&v38);
          _bstr_t::_Free((_bstr_t *)&v33);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
          _bstr_t::_Free((_bstr_t *)&v30);
          _variant_t::~_variant_t((_variant_t *)&v35);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
          goto LABEL_115;
        }
        _variant_t::~_variant_t((_variant_t *)&v43);
        _bstr_t::_Free((_bstr_t *)&v38);
        _bstr_t::_Free((_bstr_t *)&v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
        _bstr_t::_Free((_bstr_t *)&v30);
        _variant_t::~_variant_t((_variant_t *)&v35);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pRegistryKeyNode->get_nodeName failed with 0x%x");
        v24 = 49;
LABEL_109:
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          DocumentRootElement);
      }
LABEL_115:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
      if ( DocumentRootElement >= 0 )
      {
        DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, struct IXMLDOMNode **))v40->lpVtbl->removeChild)(
                                v40,
                                v39,
                                a4);
        if ( DocumentRootElement >= 0 )
        {
          v25 = this[1];
          v43 = pvarg;
          DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))v25->lpVtbl->save)(
                                  v25,
                                  &v43);
          if ( DocumentRootElement < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WppDbgPrint("m_pXmlDom->save failed with 0x%x");
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                62,
                (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
                (unsigned int)"NPSSDO",
                DocumentRootElement);
            }
            TraceXMLFailure(this[1]);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("m_pXmlDom->removeChild(pRegistryKeysNode) failed with 0x%x");
          v10 = 61;
          goto LABEL_19;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("Iteration through regkey nodes failed with 0x%x");
        v10 = 60;
        goto LABEL_19;
      }
      goto LABEL_138;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pRegistryKeysNode->get_childNodes failed with 0x%x");
      v10 = 47;
      goto LABEL_19;
    }
  }
LABEL_138:
  if ( (_DWORD)v32 )
    RegCloseKey(hKey);
LABEL_140:
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  return (unsigned int)DocumentRootElement;
}

```

## disassembly

```asm
0x18003bc7c  mov     rax, rsp
0x18003bc7f  mov     [rax+10h], rbx
0x18003bc83  mov     [rax+18h], rsi
0x18003bc87  mov     [rax+20h], r9
0x18003bc8b  mov     [rax+8], rcx
0x18003bc8f  push    rbp
0x18003bc90  push    rdi
0x18003bc91  push    r12
0x18003bc93  push    r13
0x18003bc95  push    r14
0x18003bc97  lea     rbp, [rax-38h]
0x18003bc9b  sub     rsp, 110h
0x18003bca2  mov     rbx, r8
0x18003bca5  mov     rdi, rdx
0x18003bca8  mov     rsi, rcx
0x18003bcab  xor     eax, eax
0x18003bcad  mov     [rbp+30h+var_78], rax
0x18003bcb1  mov     [rbp+30h+var_80], rax
0x18003bcb5  mov     [rbp+30h+var_68], rax
0x18003bcb9  mov     [rsp+130h+hKey], 0FFFFFFFF80000002h
0x18003bcc2  xorps   xmm0, xmm0
0x18003bcc5  movups  xmmword ptr [rbp+30h+pvarg], xmm0
0x18003bcc9  mov     qword ptr [rbp+30h+pvarg+10h], rax
0x18003bccd  lea     rcx, [rbp+30h+pvarg]; pvarg
0x18003bcd1  call    cs:__imp_VariantInit
0x18003bcd7  mov     eax, 8
0x18003bcdc  mov     word ptr [rbp+30h+pvarg], ax
0x18003bce0  mov     rcx, rbx; psz
0x18003bce3  call    cs:__imp_SysAllocString
0x18003bce9  mov     qword ptr [rbp+30h+pvarg+8], rax
0x18003bced  movups  xmm0, xmmword ptr [rbp+30h+pvarg]
0x18003bcf1  movaps  xmmword ptr [rbp+30h+var_60], xmm0
0x18003bcf5  movsd   xmm1, qword ptr [rbp+30h+pvarg+10h]
0x18003bcfa  movsd   qword ptr [rbp+30h+var_60+10h], xmm1
0x18003bcff  lea     r8, [rbp+30h+var_78]; struct IXMLDOMElement **
0x18003bd03  lea     rdx, [rbp+30h+var_60]; struct tagVARIANT
0x18003bd07  mov     rcx, [rsi+8]; struct IXMLDOMDocument2 *
0x18003bd0b  call    ?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)
0x18003bd10  mov     r14d, eax
0x18003bd13  xor     esi, esi
0x18003bd15  test    eax, eax
0x18003bd17  jns     short loc_18003BD84
0x18003bd19  lea     r13, WPP_GLOBAL_Control
0x18003bd20  mov     rax, cs:WPP_GLOBAL_Control
0x18003bd27  cmp     rax, r13
0x18003bd2a  jz      loc_18003C91E
0x18003bd30  cmp     byte ptr [rax+19h], 2
0x18003bd34  jb      loc_18003C91E
0x18003bd3a  mov     r12d, 400h
0x18003bd40  test    [rax+1Ch], r12d
0x18003bd44  jz      loc_18003C91E
0x18003bd4a  mov     edx, r14d
0x18003bd4d  lea     rcx, aGetdocumentroo; "GetDocumentRootElement failed with 0x%x"
0x18003bd54  call    WppDbgPrint
0x18003bd59  lea     edx, [rsi+2Ch]
0x18003bd5c  mov     dword ptr [rsp+130h+var_110], r14d
0x18003bd61  lea     r9, aNpssdo; "NPSSDO"
0x18003bd68  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003bd6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd76  mov     rcx, [rcx+10h]
0x18003bd7a  call    WPP_SF_sd
0x18003bd7f  jmp     loc_18003C91E
0x18003bd84  mov     dword ptr [rsp+130h+var_C8], esi
0x18003bd88  test    rdi, rdi
0x18003bd8b  jz      short loc_18003BE00
0x18003bd8d  cmp     [rdi], si
0x18003bd90  jz      short loc_18003BE00
0x18003bd92  lea     r8, [rsp+130h+hKey]; phkResult
0x18003bd97  mov     rdx, [rsp+130h+hKey]; hKey
0x18003bd9c  mov     rcx, rdi; lpMachineName
0x18003bd9f  call    cs:__imp_RegConnectRegistryW
0x18003bda5  mov     ebx, eax
0x18003bda7  test    eax, eax
0x18003bda9  jz      short loc_18003BDF8
0x18003bdab  lea     r13, WPP_GLOBAL_Control
0x18003bdb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bdb9  cmp     rcx, r13
0x18003bdbc  jz      loc_18003C91E
0x18003bdc2  cmp     byte ptr [rcx+19h], 2
0x18003bdc6  jb      loc_18003C91E
0x18003bdcc  mov     r12d, 400h
0x18003bdd2  test    [rcx+1Ch], r12d
0x18003bdd6  jz      loc_18003C91E
0x18003bddc  mov     edx, eax
0x18003bdde  lea     rcx, aRegconnectregi; "RegConnectRegistry failed with 0x%x"
0x18003bde5  call    WppDbgPrint
0x18003bdea  mov     edx, 2Dh ; '-'
0x18003bdef  mov     dword ptr [rsp+130h+var_110], ebx
0x18003bdf3  jmp     loc_18003BD61
0x18003bdf8  mov     dword ptr [rsp+130h+var_C8], 1
0x18003be00  mov     rcx, [rbp+30h+var_78]
0x18003be04  mov     rax, [rcx]
0x18003be07  lea     r8, [rbp+30h+var_80]
0x18003be0b  lea     rdx, aRegistrykeys; "registryKeys"
0x18003be12  mov     rax, [rax+128h]
0x18003be19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be1e  mov     r14d, eax
0x18003be21  test    eax, eax
0x18003be23  jz      short loc_18003BE92
0x18003be25  lea     r13, WPP_GLOBAL_Control
0x18003be2c  mov     rax, cs:WPP_GLOBAL_Control
0x18003be33  cmp     rax, r13
0x18003be36  jz      loc_18003C90D
0x18003be3c  cmp     byte ptr [rax+19h], 2
0x18003be40  jb      loc_18003C90D
0x18003be46  mov     r12d, 400h
0x18003be4c  test    [rax+1Ch], r12d
0x18003be50  jz      loc_18003C90D
0x18003be56  mov     edx, r14d
0x18003be59  lea     rcx, aProotelementSe; "pRootElement->selectSingleNode failed w"...
0x18003be60  call    WppDbgPrint
0x18003be65  mov     edx, 2Eh ; '.'
0x18003be6a  lea     r9, aNpssdo; "NPSSDO"
0x18003be71  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003be78  mov     dword ptr [rsp+130h+var_110], r14d
0x18003be7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be84  mov     rcx, [rcx+10h]
0x18003be88  call    WPP_SF_sd
0x18003be8d  jmp     loc_18003C90D
0x18003be92  mov     rcx, [rbp+30h+var_80]
0x18003be96  mov     rax, [rcx]
0x18003be99  lea     rdx, [rbp+30h+var_68]
0x18003be9d  mov     rax, [rax+60h]
0x18003bea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bea6  mov     r14d, eax
0x18003bea9  test    eax, eax
0x18003beab  jns     short loc_18003BEF7
0x18003bead  lea     r13, WPP_GLOBAL_Control
0x18003beb4  mov     rax, cs:WPP_GLOBAL_Control
0x18003bebb  cmp     rax, r13
0x18003bebe  jz      loc_18003C90D
0x18003bec4  cmp     byte ptr [rax+19h], 2
0x18003bec8  jb      loc_18003C90D
0x18003bece  mov     r12d, 400h
0x18003bed4  test    [rax+1Ch], r12d
0x18003bed8  jz      loc_18003C90D
0x18003bede  mov     edx, r14d
0x18003bee1  lea     rcx, aPregistrykeysn; "pRegistryKeysNode->get_childNodes faile"...
0x18003bee8  call    WppDbgPrint
0x18003beed  mov     edx, 2Fh ; '/'
0x18003bef2  jmp     loc_18003BE6A
0x18003bef7  mov     edi, esi
0x18003bef9  lea     rcx, IASKEYS
0x18003bf00  movsxd  rax, edi
0x18003bf03  lea     rsi, [rax+rax*2]
0x18003bf07  mov     r8, [rcx+rsi*8+8]
0x18003bf0c  mov     rdx, [rcx+rsi*8]
0x18003bf10  mov     rcx, [rsp+130h+hKey]
0x18003bf15  call    DeleteRegistryValue
0x18003bf1a  mov     ebx, eax
0x18003bf1c  test    eax, 0FFFFFFFDh
0x18003bf21  jnz     loc_18003C879
0x18003bf27  inc     edi
0x18003bf29  cmp     edi, 17h
0x18003bf2c  lea     rcx, IASKEYS
0x18003bf33  jb      short loc_18003BF00
0x18003bf35  lea     r13, WPP_GLOBAL_Control
0x18003bf3c  mov     r12d, 400h
0x18003bf42  lea     rdi, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003bf49  lea     rbx, aNpssdo; "NPSSDO"
0x18003bf50  xor     esi, esi
0x18003bf52  mov     [rsp+130h+var_D0], rsi
0x18003bf57  mov     rcx, [rbp+30h+var_68]
0x18003bf5b  mov     rax, [rcx]
0x18003bf5e  lea     rdx, [rsp+130h+var_D0]
0x18003bf63  mov     rax, [rax+48h]
0x18003bf67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf6c  mov     r14d, eax
0x18003bf6f  cmp     eax, 1
0x18003bf72  jz      loc_18003C73B
0x18003bf78  test    eax, eax
0x18003bf7a  js      loc_18003C73E
0x18003bf80  mov     [rbp+30h+bstrString], rsi
0x18003bf84  mov     [rbp+30h+var_90], rsi
0x18003bf88  mov     rcx, [rsp+130h+var_D0]
0x18003bf8d  mov     rax, [rcx]
0x18003bf90  lea     rdx, [rbp+30h+bstrString]
0x18003bf94  mov     rax, [rax+38h]
0x18003bf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf9d  mov     r14d, eax
0x18003bfa0  test    eax, eax
0x18003bfa2  js      loc_18003C70D
0x18003bfa8  mov     rcx, [rsp+130h+var_D0]
0x18003bfad  mov     rax, [rcx]
0x18003bfb0  lea     rdx, [rbp+30h+var_90]
0x18003bfb4  mov     rax, [rax+0C8h]
0x18003bfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfc0  mov     r14d, eax
0x18003bfc3  test    eax, eax
0x18003bfc5  js      loc_18003C6C4
0x18003bfcb  mov     rax, cs:WPP_GLOBAL_Control
0x18003bfd2  cmp     rax, r13
0x18003bfd5  jz      short loc_18003C022
0x18003bfd7  cmp     byte ptr [rax+19h], 4
0x18003bfdb  jb      short loc_18003C022
0x18003bfdd  test    [rax+1Ch], r12d
0x18003bfe1  jz      short loc_18003C022
0x18003bfe3  mov     r8, [rbp+30h+var_90]
0x18003bfe7  mov     rdx, [rbp+30h+bstrString]
0x18003bfeb  lea     rcx, aProcessingNode; "Processing nodename: %S nodeType: %S"
0x18003bff2  call    WppDbgPrint
0x18003bff7  lea     edx, [rsi+33h]
0x18003bffa  mov     rax, [rbp+30h+var_90]
0x18003bffe  mov     [rsp+130h+var_108], rax; __int64
0x18003c003  mov     rax, [rbp+30h+bstrString]
0x18003c007  mov     [rsp+130h+var_110], rax; __int64
0x18003c00c  mov     r9, rbx
0x18003c00f  mov     r8, rdi
0x18003c012  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c019  mov     rcx, [rcx+10h]; LoggerHandle
0x18003c01d  call    WPP_SF_sSS
0x18003c022  mov     rcx, [rbp+30h+bstrString]; bstrString
0x18003c026  call    cs:__imp_SysFreeString
0x18003c02c  mov     rcx, [rbp+30h+var_90]; bstrString
0x18003c030  call    cs:__imp_SysFreeString
0x18003c036  mov     [rsp+130h+var_F0], rsi
0x18003c03b  mov     rcx, [rsp+130h+var_D0]
0x18003c040  mov     rax, [rcx]
0x18003c043  lea     r8, [rsp+130h+var_F0]
0x18003c048  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003c04f  mov     rax, [rax]
0x18003c052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c057  mov     r14d, eax
0x18003c05a  test    eax, eax
0x18003c05c  js      loc_18003C66C
0x18003c062  lea     rcx, [rbp+30h+var_B0]; pvarg
0x18003c066  call    cs:__imp_VariantInit
0x18003c06c  nop
0x18003c06d  lea     rcx, [rbp+30h+var_B0]; this
0x18003c071  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003c076  mov     rcx, [rsp+130h+var_F0]
0x18003c07b  mov     rax, [rcx]
0x18003c07e  lea     r8, [rbp+30h+var_B0]
0x18003c082  lea     rdx, aKeyname; "keyName"
0x18003c089  mov     rax, [rax+160h]
0x18003c090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c095  mov     r14d, eax
0x18003c098  test    eax, eax
0x18003c09a  js      loc_18003C601
0x18003c0a0  mov     rdx, qword ptr [rbp+30h+var_B0+8]; unsigned __int16 *
0x18003c0a4  lea     rcx, [rsp+130h+var_D8]; this
0x18003c0a9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003c0ae  nop
0x18003c0af  mov     [rsp+130h+var_E0], rsi
0x18003c0b4  mov     rcx, [rsp+130h+var_F0]
0x18003c0b9  mov     rax, [rcx]
0x18003c0bc  lea     r8, [rsp+130h+var_E0]
0x18003c0c1  lea     rdx, aRegistryvalue; "registryValue"
0x18003c0c8  mov     rax, [rax+128h]
0x18003c0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0d4  mov     r14d, eax
0x18003c0d7  test    eax, eax
0x18003c0d9  jnz     loc_18003C596
0x18003c0df  mov     [rsp+130h+var_E8], rsi
0x18003c0e4  mov     rcx, [rsp+130h+var_E0]
0x18003c0e9  mov     rax, [rcx]
0x18003c0ec  lea     r8, [rsp+130h+var_E8]
0x18003c0f1  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003c0f8  mov     rax, [rax]
0x18003c0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c100  mov     r14d, eax
0x18003c103  test    eax, eax
0x18003c105  js      loc_18003C53E
0x18003c10b  lea     rcx, [rbp+30h+var_B0]; this
0x18003c10f  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003c114  mov     rcx, [rsp+130h+var_E8]
0x18003c119  mov     rax, [rcx]
0x18003c11c  lea     r8, [rbp+30h+var_B0]
0x18003c120  lea     rdx, aName; "name"
0x18003c127  mov     rax, [rax+160h]
0x18003c12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c133  mov     r14d, eax
0x18003c136  test    eax, eax
0x18003c138  js      loc_18003C4D3
0x18003c13e  mov     r8b, 1; bool
0x18003c141  mov     rdx, qword ptr [rbp+30h+var_B0+8]; unsigned __int16 *
0x18003c145  lea     rcx, [rsp+130h+var_C0]; this
0x18003c14a  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18003c14f  nop
0x18003c150  lea     rcx, [rbp+30h+var_B0]; this
0x18003c154  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003c159  mov     rcx, [rsp+130h+var_E8]
0x18003c15e  mov     rax, [rcx]
0x18003c161  lea     r8, [rbp+30h+var_B0]
0x18003c165  lea     rdx, aValuetype; "valueType"
0x18003c16c  mov     rax, [rax+160h]
0x18003c173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c178  mov     r14d, eax
0x18003c17b  test    eax, eax
0x18003c17d  js      loc_18003C474
0x18003c183  mov     r8b, 1; bool
0x18003c186  mov     rdx, qword ptr [rbp+30h+var_B0+8]; unsigned __int16 *
0x18003c18a  lea     rcx, [rbp+30h+var_88]; this
0x18003c18e  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18003c193  nop
0x18003c194  lea     rcx, [rbp+30h+var_60]; pvarg
0x18003c198  call    cs:__imp_VariantInit
0x18003c19e  nop
0x18003c19f  mov     rcx, [rsp+130h+var_E8]
0x18003c1a4  mov     rax, [rcx]
  ... truncated ...
```
