# WpGenerateProfileXml

- ea: `0x180023b50`
- end: `0x1800243f8`
- name: `WpGenerateProfileXml`
- size: `2216`
- prototype: `__int64 __fastcall(struct _PM_PROFILE *)`
- caller_count: `10`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002759c`
- `0x18003e670`
- `0x180057180`
- `0x18009b8f0`
- `0x1800b76c4`
- `0x1800fa22c`
- `0x180105384`
- `0x1801a516c`
- `0x1801b30ac`
- `0x1801fd6a0`

## callees

- `0x180023b50`
- `0x1800248e4`
- `0x180024930`
- `0x180025678`
- `0x1800258d8`
- `0x1800a7f2c`
- `0x1801b3df4`
- `0x18020a47c`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024088`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024097`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024097`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024158`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800240ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024158`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002415e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002415e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180023bd5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180023bd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023c26`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023f71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023c26`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023f71`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180023b9f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180023b9f`
- `OLEAUT32!__imp_SysAllocString` at `0x180023c6c`
- `OLEAUT32!__imp_SysAllocString` at `0x180023cad`
- `OLEAUT32!__imp_SysAllocString` at `0x180023db7`
- `OLEAUT32!__imp_SysAllocString` at `0x180023de1`
- `OLEAUT32!__imp_SysAllocString` at `0x180023c6c`
- `OLEAUT32!__imp_SysAllocString` at `0x180023cad`
- `OLEAUT32!__imp_SysAllocString` at `0x180023db7`
- `OLEAUT32!__imp_SysAllocString` at `0x180023de1`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180023d59`
- `OLEAUT32!__imp_SysFreeString` at `0x180023da8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023dc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180023dd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180023df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180023e72`
- `OLEAUT32!__imp_SysFreeString` at `0x180023e7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180023fc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180024128`
- `OLEAUT32!__imp_SysFreeString` at `0x180024148`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180023d59`
- `OLEAUT32!__imp_SysFreeString` at `0x180023da8`
- `OLEAUT32!__imp_SysFreeString` at `0x180023dc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180023dd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180023df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180023e72`
- `OLEAUT32!__imp_SysFreeString` at `0x180023e7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180023fc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180024128`
- `OLEAUT32!__imp_SysFreeString` at `0x180024148`
- `OLEAUT32!__imp_SysStringLen` at `0x180024071`
- `OLEAUT32!__imp_SysStringLen` at `0x180024071`
- `OLEAUT32!__imp_VariantInit` at `0x180023bf7`
- `OLEAUT32!__imp_VariantInit` at `0x180023c01`
- `OLEAUT32!__imp_VariantInit` at `0x180023f42`
- `OLEAUT32!__imp_VariantInit` at `0x180023f4c`
- `OLEAUT32!__imp_VariantInit` at `0x180023bf7`
- `OLEAUT32!__imp_VariantInit` at `0x180023c01`
- `OLEAUT32!__imp_VariantInit` at `0x180023f42`
- `OLEAUT32!__imp_VariantInit` at `0x180023f4c`
- `OLEAUT32!__imp_VariantClear` at `0x180023c89`
- `OLEAUT32!__imp_VariantClear` at `0x180023cbb`
- `OLEAUT32!__imp_VariantClear` at `0x180023d46`
- `OLEAUT32!__imp_VariantClear` at `0x180023d50`
- `OLEAUT32!__imp_VariantClear` at `0x180023fb1`
- `OLEAUT32!__imp_VariantClear` at `0x180023fbb`
- `OLEAUT32!__imp_VariantClear` at `0x180023c89`
- `OLEAUT32!__imp_VariantClear` at `0x180023cbb`
- `OLEAUT32!__imp_VariantClear` at `0x180023d46`
- `OLEAUT32!__imp_VariantClear` at `0x180023d50`
- `OLEAUT32!__imp_VariantClear` at `0x180023fb1`
- `OLEAUT32!__imp_VariantClear` at `0x180023fbb`

## string_xrefs

- `0x180023eb5`: `http://www.microsoft.com/networking/WLANAP/profile/v1`
- `0x1800242d8`: `http://www.microsoft.com/networking/WLANAP/profile/v1`
- `0x180023ca6`: `xmlns:WLANProfile='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:WLANPolicy='http://www.microsoft.com/networking/WLAN/policy/v1' xmlns:LANProfile='http://www.microsoft.com/networking/LAN/profile/v1' xmlns:LANPolicy='http://www.microsoft.com/networking/LAN/policy/v1' xmlns:LANPolicyV2='http://www.microsoft.com/networking/LAN/policy/v2' xmlns:OneX='http://www.microsoft.com/networking/OneX/v1' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WpGenerateProfileXml(struct _PM_PROFILE *a1, OLECHAR **a2)
{
  OLECHAR *v3; // rdi
  int v4; // r14d
  struct IXMLDOMDocument2 *v5; // rsi
  unsigned int APSSIDConfig; // r15d
  HRESULT v8; // eax
  struct IXMLDOMNode *v9; // rbx
  HRESULT Instance; // eax
  int v11; // eax
  BSTR v12; // r15
  __m128i v13; // xmm1
  IRecordInfo *pRecInfo; // xmm2_8
  int v15; // eax
  OLECHAR *v16; // rdi
  BSTR v17; // rbx
  OLECHAR *v18; // rbx
  BSTR v19; // r15
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  int v23; // eax
  struct IXMLDOMNode *v24; // rbx
  struct IXMLDOMDocument2 *v25; // rbx
  HRESULT v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rax
  unsigned __int64 v32; // rdi
  SIZE_T v33; // r15
  HANDLE ProcessHeap; // rax
  OLECHAR *v35; // r12
  __int64 v36; // rcx
  BSTR v37; // rdx
  OLECHAR *v38; // r8
  OLECHAR v39; // ax
  unsigned __int16 v40; // dx
  OLECHAR *v41; // rcx
  struct IXMLDOMNode **v42; // [rsp+28h] [rbp-51h]
  BSTR bstrString; // [rsp+30h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-41h] BYREF
  VARIANTARG v45; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG v46; // [rsp+70h] [rbp-9h] BYREF
  struct IXMLDOMNode *ppv; // [rsp+E0h] [rbp+67h] BYREF
  OLECHAR **v48; // [rsp+E8h] [rbp+6Fh]
  struct IXMLDOMDocument2 *v49; // [rsp+F0h] [rbp+77h] BYREF
  BSTR pbstr; // [rsp+F8h] [rbp+7Fh] BYREF

  v48 = a2;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  *a2 = 0;
  if ( !a1 || *((_DWORD *)a1 + 134) != 5304833 || !*((_QWORD *)a1 + 69) )
  {
    APSSIDConfig = 87;
    goto LABEL_3;
  }
  v8 = CoInitializeEx(0, 0);
  APSSIDConfig = v8;
  if ( v8 >= 0 )
    goto LABEL_11;
  if ( (v8 & 0x1FFF0000) == 0x70000 )
    APSSIDConfig = (unsigned __int16)v8;
  if ( APSSIDConfig )
  {
    if ( APSSIDConfig != -2147417850 )
      goto LABEL_3;
  }
  else
  {
LABEL_11:
    v4 = 1;
  }
  v9 = 0;
  ppv = 0;
  VariantInit(&pvarg);
  VariantInit(&v46);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, (LPVOID *)&ppv);
  APSSIDConfig = Instance;
  if ( Instance >= 0 )
    goto LABEL_96;
  if ( (Instance & 0x1FFF0000) == 0x70000 )
    APSSIDConfig = (unsigned __int16)Instance;
  if ( !APSSIDConfig )
  {
LABEL_96:
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD))ppv->lpVtbl[1].removeChild)(ppv, 0);
    APSSIDConfig = v11;
    if ( v11 >= 0 )
      goto LABEL_14;
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      APSSIDConfig = (unsigned __int16)v11;
    if ( !APSSIDConfig )
    {
LABEL_14:
      SysFreeString(0);
      v12 = SysAllocString(L"SelectionNamespaces");
      if ( v12 )
      {
        SysFreeString(0);
        v3 = v12;
      }
      if ( VariantClear(&pvarg) < 0
        || (*(_OWORD *)&v45.vt = 0,
            v45.vt = 8,
            v45.llVal = (LONGLONG)SysAllocString(
                                    L"xmlns:WLANProfile='http://www.microsoft.com/networking/WLAN/profile/v1' xmlns:WLANPo"
                                     "licy='http://www.microsoft.com/networking/WLAN/policy/v1' xmlns:LANProfile='http://"
                                     "www.microsoft.com/networking/LAN/profile/v1' xmlns:LANPolicy='http://www.microsoft."
                                     "com/networking/LAN/policy/v1' xmlns:LANPolicyV2='http://www.microsoft.com/networkin"
                                     "g/LAN/policy/v2' xmlns:OneX='http://www.microsoft.com/networking/OneX/v1' xmlns:bas"
                                     "eeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnection"
                                     "PropertiesV1' xmlns:mspeapconnectionpropertiesv1='http://www.microsoft.com/provisio"
                                     "ning/MsPeapConnectionPropertiesV1' xmlns:mschapv2connectionpropertiesv1='http://www"
                                     ".microsoft.com/provisioning/MsChapV2ConnectionPropertiesV1' xmlns:WLANProfileV2='ht"
                                     "tp://www.microsoft.com/networking/WLAN/profile/v2' xmlns:WLANProfileV3='http://www."
                                     "microsoft.com/networking/WLAN/profile/v3' xmlns:WLANProfileV4='http://www.microsoft"
                                     ".com/networking/WLAN/profile/v4' xmlns:WLANProfileV5='http://www.microsoft.com/netw"
                                     "orking/WLAN/profile/v5' xmlns:WLANPolicyV2='http://www.microsoft.com/networking/WLA"
                                     "N/policy/v2' xmlns:WLANPolicyV3='http://www.microsoft.com/networking/WLAN/policy/v3"
                                     "' xmlns:WLANPolicyV4='http://www.microsoft.com/networking/WLAN/policy/v4' xmlns:WLA"
                                     "NAPProfile='http://www.microsoft.com/networking/WLANAP/profile/v1' xmlns:WFDProfile"
                                     "='http://www.microsoft.com/networking/WiFiDirect/profile/v1' xmlns:WFDLegacyProfile"
                                     "='http://www.microsoft.com/networking/WiFiDirectLegacy/profile/v1' "),
            VariantClear(&pvarg) < 0) )
      {
        pRecInfo = pvarg.pRecInfo;
        v13 = *(__m128i *)&pvarg.vt;
      }
      else
      {
        v13 = *(__m128i *)&v45.vt;
        *(_OWORD *)&pvarg.vt = *(_OWORD *)&v45.vt;
        pRecInfo = 0;
        pvarg.pRecInfo = 0;
      }
      if ( v3 && (unsigned __int16)_mm_cvtsi128_si32(v13) == 8 && _mm_srli_si128(v13, 8).m128i_u64[0] )
      {
        *(__m128i *)&v45.vt = v13;
        v45.pRecInfo = pRecInfo;
        v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, VARIANTARG *))ppv->lpVtbl[1].selectSingleNode)(
                ppv,
                v3,
                &v45);
        APSSIDConfig = v15;
        if ( v15 >= 0 )
        {
          APSSIDConfig = 0;
LABEL_24:
          v9 = ppv;
          ppv = 0;
          goto LABEL_25;
        }
        if ( (v15 & 0x1FFF0000) == 0x70000 )
          APSSIDConfig = (unsigned __int16)v15;
        if ( !APSSIDConfig )
          goto LABEL_24;
      }
      else
      {
        APSSIDConfig = 8;
      }
    }
  }
LABEL_25:
  VariantClear(&v46);
  VariantClear(&pvarg);
  SysFreeString(v3);
  if ( ppv )
    ((void (__fastcall *)(struct IXMLDOMNode *))ppv->lpVtbl->Release)(ppv);
  if ( !APSSIDConfig )
  {
    v5 = (struct IXMLDOMDocument2 *)v9;
    v9 = 0;
  }
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v9->lpVtbl->Release)(v9);
  if ( !APSSIDConfig )
  {
    ppv = 0;
    SysFreeString(0);
    v16 = 0;
    v17 = SysAllocString(L"xml");
    if ( v17 )
    {
      SysFreeString(0);
      v16 = v17;
    }
    SysFreeString(0);
    v18 = 0;
    v19 = SysAllocString(L"version=\"1.0\"");
    if ( v19 )
    {
      SysFreeString(0);
      v18 = v19;
    }
    if ( v16 && v18 )
    {
      v20 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, OLECHAR *, struct IXMLDOMNode **))v5->lpVtbl->createProcessingInstruction)(
              v5,
              v16,
              v18,
              &ppv);
      APSSIDConfig = v20;
      if ( v20 >= 0 )
        goto LABEL_39;
      if ( (v20 & 0x1FFF0000) == 0x70000 )
        APSSIDConfig = (unsigned __int16)v20;
      if ( !APSSIDConfig )
      {
LABEL_39:
        v21 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, _QWORD))v5->lpVtbl->appendChild)(
                v5,
                ppv,
                0);
        APSSIDConfig = v21;
        if ( v21 < 0 )
        {
          if ( (v21 & 0x1FFF0000) == 0x70000 )
            APSSIDConfig = (unsigned __int16)v21;
        }
        else
        {
          APSSIDConfig = 0;
        }
      }
    }
    else
    {
      APSSIDConfig = 14;
    }
    if ( ppv )
      ((void (__fastcall *)(struct IXMLDOMNode *))ppv->lpVtbl->Release)(ppv);
    SysFreeString(v18);
    SysFreeString(v16);
    if ( !APSSIDConfig )
    {
      v22 = *((_QWORD *)a1 + 69);
      v23 = *(_DWORD *)(v22 + 20);
      if ( v23 == 8 || v23 == 32 )
      {
        ppv = 0;
        v49 = 0;
        APSSIDConfig = XcAddChildElement(
                         v5,
                         (struct IXMLDOMNode *)v5,
                         L"WLANAPProfile",
                         L"http://www.microsoft.com/networking/WLANAP/profile/v1",
                         0,
                         &ppv);
        v24 = ppv;
        if ( APSSIDConfig
          || (APSSIDConfig = XcAddChildElementFullString(
                               v5,
                               ppv,
                               L"name",
                               L"http://www.microsoft.com/networking/WLANAP/profile/v1",
                               (LPCWSTR)a1 + 12,
                               v42)) != 0
          || (APSSIDConfig = XwpGenerateAPSSIDConfig(v22, v5, v24)) != 0
          || (APSSIDConfig = XwpGenerateAPMSMSettings(*(struct _DOT11_MSM_PROFILE **)(v22 + 32), v5, v24)) != 0 )
        {
          ((void (__fastcall *)(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMDocument2 **))v5->lpVtbl->removeChild)(
            v5,
            v24,
            &v49);
        }
        if ( v49 )
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v49->lpVtbl->Release)(v49);
        if ( v24 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      }
      else
      {
        APSSIDConfig = XwGenerateWlanProfile(a1, v5, (struct IXMLDOMNode *)v5);
      }
      if ( !APSSIDConfig )
      {
        bstrString = 0;
        v25 = 0;
        LOWORD(ppv) = 0;
        v49 = 0;
        VariantInit(&v45);
        VariantInit(&v46);
        v26 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, (LPVOID *)&v49);
        APSSIDConfig = v26;
        if ( v26 >= 0 )
          goto LABEL_53;
        if ( (v26 & 0x1FFF0000) == 0x70000 )
          APSSIDConfig = (unsigned __int16)v26;
        if ( !APSSIDConfig )
        {
LABEL_53:
          v27 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD))v49->lpVtbl->put_async)(v49, 0);
          APSSIDConfig = v27;
          if ( v27 >= 0 )
          {
            APSSIDConfig = 0;
LABEL_55:
            v25 = v49;
            v49 = 0;
            goto LABEL_56;
          }
          if ( (v27 & 0x1FFF0000) == 0x70000 )
            APSSIDConfig = (unsigned __int16)v27;
          if ( !APSSIDConfig )
            goto LABEL_55;
        }
LABEL_56:
        VariantClear(&v46);
        VariantClear(&v45);
        SysFreeString(0);
        if ( v49 )
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v49->lpVtbl->Release)(v49);
        if ( APSSIDConfig )
          goto LABEL_81;
        v28 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR *))v5->lpVtbl->get_xml)(v5, &bstrString);
        APSSIDConfig = v28;
        if ( v28 < 0 )
        {
          if ( (v28 & 0x1FFF0000) == 0x70000 )
            APSSIDConfig = (unsigned __int16)v28;
          if ( APSSIDConfig )
            goto LABEL_81;
        }
        v29 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, struct IXMLDOMNode **))v25->lpVtbl->loadXML)(
                v25,
                bstrString,
                &ppv);
        APSSIDConfig = v29;
        if ( v29 < 0 )
        {
          if ( (v29 & 0x1FFF0000) == 0x70000 )
            APSSIDConfig = (unsigned __int16)v29;
          if ( APSSIDConfig )
            goto LABEL_81;
        }
        if ( (_WORD)ppv != 0xFFFF )
        {
          APSSIDConfig = XcGetLoadError(v25);
          if ( APSSIDConfig )
            goto LABEL_81;
        }
        pbstr = 0;
        v30 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR *))v25->lpVtbl->get_xml)(v25, &pbstr);
        APSSIDConfig = v30;
        if ( v30 < 0 )
        {
          if ( (v30 & 0x1FFF0000) == 0x70000 )
            APSSIDConfig = (unsigned __int16)v30;
          if ( APSSIDConfig )
            goto LABEL_80;
        }
        else
        {
          APSSIDConfig = 0;
        }
        if ( pbstr )
        {
          v31 = SysStringLen(pbstr) + 1;
          v32 = (unsigned int)v31;
          v33 = 2 * v31;
          if ( 2 * v31 )
          {
            ProcessHeap = GetProcessHeap();
            v35 = (OLECHAR *)HeapAlloc(ProcessHeap, 8u, v33);
            if ( v35 )
            {
              SetLastError(0);
              if ( !v32 )
              {
                v40 = 87;
                goto LABEL_78;
              }
              if ( v32 > 0x7FFFFFFF )
              {
                v40 = 87;
                *v35 = 0;
                goto LABEL_78;
              }
              v36 = 2147483646;
              v37 = pbstr;
              v38 = v35;
              do
              {
                if ( !v36 )
                  break;
                v39 = *v37;
                if ( !*v37 )
                  break;
                ++v37;
                *v38++ = v39;
                --v36;
                --v32;
              }
              while ( v32 );
              v40 = 122;
              if ( v32 )
                v40 = 0;
              v41 = v38 - 1;
              if ( v32 )
                v41 = v38;
              *v41 = 0;
              if ( !v32 )
              {
LABEL_78:
                APSSIDConfig = v40;
                if ( v40 )
                {
LABEL_79:
                  Xc_Process_user_free(v35);
LABEL_80:
                  SysFreeString(pbstr);
LABEL_81:
                  if ( v25 )
                    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v25->lpVtbl->Release)(v25);
                  SysFreeString(bstrString);
                  goto LABEL_3;
                }
                goto LABEL_90;
              }
              APSSIDConfig = 0;
LABEL_90:
              *v48 = v35;
              goto LABEL_86;
            }
            SetLastError(8u);
          }
          else
          {
            SetLastError(0x57u);
            v35 = 0;
          }
          APSSIDConfig = GetLastError();
LABEL_86:
          if ( !APSSIDConfig || !v35 )
            goto LABEL_80;
          goto LABEL_79;
        }
        v35 = 0;
        goto LABEL_90;
      }
    }
  }
LABEL_3:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  if ( v4 )
    CoUninitialize();
  return APSSIDConfig;
}

```

## disassembly

```asm
0x180023b50  mov     [rsp-8+arg_8], rdx
0x180023b55  push    rbp
0x180023b56  push    rbx
0x180023b57  push    rsi
0x180023b58  push    rdi
0x180023b59  push    r12
0x180023b5b  push    r13
0x180023b5d  push    r14
0x180023b5f  push    r15
0x180023b61  lea     rbp, [rsp-1Fh]
0x180023b66  sub     rsp, 98h
0x180023b6d  mov     r13, rcx
0x180023b70  xor     edi, edi
0x180023b72  mov     r14d, edi
0x180023b75  mov     esi, edi
0x180023b77  mov     [rdx], rdi
0x180023b7a  test    rcx, rcx
0x180023b7d  jnz     short loc_180023BBC
0x180023b7f  mov     r15d, 57h ; 'W'
0x180023b85  test    rsi, rsi
0x180023b88  jz      short loc_180023B9A
0x180023b8a  mov     rax, [rsi]
0x180023b8d  mov     rcx, rsi
0x180023b90  mov     rax, [rax+10h]
0x180023b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b99  nop
0x180023b9a  test    r14d, r14d
0x180023b9d  jz      short loc_180023BA5
0x180023b9f  call    cs:__imp_CoUninitialize
0x180023ba5  mov     eax, r15d
0x180023ba8  add     rsp, 98h
0x180023baf  pop     r15
0x180023bb1  pop     r14
0x180023bb3  pop     r13
0x180023bb5  pop     r12
0x180023bb7  pop     rdi
0x180023bb8  pop     rsi
0x180023bb9  pop     rbx
0x180023bba  pop     rbp
0x180023bbb  retn
0x180023bbc  cmp     dword ptr [rcx+218h], 50F201h
0x180023bc6  jnz     short loc_180023B7F
0x180023bc8  cmp     [rcx+228h], rsi
0x180023bcf  jz      short loc_180023B7F
0x180023bd1  xor     edx, edx; dwCoInit
0x180023bd3  xor     ecx, ecx; pvReserved
0x180023bd5  call    cs:__imp_CoInitializeEx
0x180023bdb  mov     r15d, eax
0x180023bde  test    eax, eax
0x180023be0  js      loc_180024219
0x180023be6  mov     r14d, 1
0x180023bec  mov     rbx, rdi
0x180023bef  mov     [rbp+57h+arg_0], rdi
0x180023bf3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023bf7  call    cs:__imp_VariantInit
0x180023bfd  lea     rcx, [rbp+57h+var_60]; pvarg
0x180023c01  call    cs:__imp_VariantInit
0x180023c07  lea     rax, [rbp+57h+arg_0]
0x180023c0b  mov     [rsp+0D0h+ppv], rax; ppv
0x180023c10  lea     r9, IID_IXMLDOMDocument2; riid
0x180023c17  xor     edx, edx; pUnkOuter
0x180023c19  mov     r8d, 1; dwClsContext
0x180023c1f  lea     rcx, CLSID_DOMDocument60; rclsid
0x180023c26  call    cs:__imp_CoCreateInstance
0x180023c2c  mov     r15d, eax
0x180023c2f  mov     r12d, 8
0x180023c35  test    eax, eax
0x180023c37  js      loc_180024244
0x180023c3d  mov     rcx, [rbp+57h+arg_0]
0x180023c41  mov     rax, [rcx]
0x180023c44  xor     edx, edx
0x180023c46  mov     rax, [rax+1F8h]
0x180023c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c52  mov     r15d, eax
0x180023c55  test    eax, eax
0x180023c57  js      loc_180024256
0x180023c5d  xor     ecx, ecx; bstrString
0x180023c5f  call    cs:__imp_SysFreeString
0x180023c65  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x180023c6c  call    cs:__imp_SysAllocString
0x180023c72  mov     r15, rax
0x180023c75  test    rax, rax
0x180023c78  jz      short loc_180023C85
0x180023c7a  xor     ecx, ecx; bstrString
0x180023c7c  call    cs:__imp_SysFreeString
0x180023c82  mov     rdi, r15
0x180023c85  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023c89  call    cs:__imp_VariantClear
0x180023c8f  test    eax, eax
0x180023c91  js      loc_18002426F
0x180023c97  xorps   xmm0, xmm0
0x180023c9a  xor     r15d, r15d
0x180023c9d  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180023ca1  mov     word ptr [rbp+57h+var_80], r12w
0x180023ca6  lea     rcx, aXmlnsWlanprofi; "xmlns:WLANProfile='http://www.microsoft"...
0x180023cad  call    cs:__imp_SysAllocString
0x180023cb3  mov     qword ptr [rbp+57h+var_80+8], rax
0x180023cb7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023cbb  call    cs:__imp_VariantClear
0x180023cc1  test    eax, eax
0x180023cc3  js      loc_18002426F
0x180023cc9  movups  xmm1, xmmword ptr [rbp+57h+var_80]
0x180023ccd  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x180023cd1  movq    xmm2, r15
0x180023cd6  movsd   qword ptr [rbp+57h+pvarg+10h], xmm2
0x180023cdb  test    rdi, rdi
0x180023cde  jz      loc_18002417F
0x180023ce4  movd    eax, xmm1
0x180023ce8  cmp     ax, r12w
0x180023cec  jnz     loc_18002417F
0x180023cf2  movdqa  xmm0, xmm1
0x180023cf6  psrldq  xmm0, 8
0x180023cfb  movq    rax, xmm0
0x180023d00  test    rax, rax
0x180023d03  jz      loc_18002417F
0x180023d09  mov     rcx, [rbp+57h+arg_0]
0x180023d0d  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x180023d11  movsd   qword ptr [rbp+57h+var_80+10h], xmm2
0x180023d16  mov     rax, [rcx]
0x180023d19  lea     r8, [rbp+57h+var_80]
0x180023d1d  mov     rdx, rdi
0x180023d20  mov     rax, [rax+280h]
0x180023d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d2c  mov     r15d, eax
0x180023d2f  test    eax, eax
0x180023d31  js      loc_18002427D
0x180023d37  xor     r15d, r15d
0x180023d3a  mov     rbx, [rbp+57h+arg_0]
0x180023d3e  mov     [rbp+57h+arg_0], rsi
0x180023d42  lea     rcx, [rbp+57h+var_60]; pvarg
0x180023d46  call    cs:__imp_VariantClear
0x180023d4c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023d50  call    cs:__imp_VariantClear
0x180023d56  mov     rcx, rdi; bstrString
0x180023d59  call    cs:__imp_SysFreeString
0x180023d5f  nop
0x180023d60  mov     rcx, [rbp+57h+arg_0]
0x180023d64  test    rcx, rcx
0x180023d67  jz      short loc_180023D76
0x180023d69  mov     rax, [rcx]
0x180023d6c  mov     rax, [rax+10h]
0x180023d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d75  nop
0x180023d76  test    r15d, r15d
0x180023d79  jnz     short loc_180023D80
0x180023d7b  mov     rsi, rbx
0x180023d7e  xor     ebx, ebx
0x180023d80  test    rbx, rbx
0x180023d83  jz      short loc_180023D95
0x180023d85  mov     rax, [rbx]
0x180023d88  mov     rcx, rbx
0x180023d8b  mov     rax, [rax+10h]
0x180023d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d94  nop
0x180023d95  test    r15d, r15d
0x180023d98  jnz     loc_180023B85
0x180023d9e  mov     [rbp+57h+arg_0], 0
0x180023da6  xor     ecx, ecx; bstrString
0x180023da8  call    cs:__imp_SysFreeString
0x180023dae  xor     edi, edi
0x180023db0  lea     rcx, aXml; "xml"
0x180023db7  call    cs:__imp_SysAllocString
0x180023dbd  mov     rbx, rax
0x180023dc0  test    rax, rax
0x180023dc3  jz      short loc_180023DD0
0x180023dc5  xor     ecx, ecx; bstrString
0x180023dc7  call    cs:__imp_SysFreeString
0x180023dcd  mov     rdi, rbx
0x180023dd0  xor     ecx, ecx; bstrString
0x180023dd2  call    cs:__imp_SysFreeString
0x180023dd8  xor     ebx, ebx
0x180023dda  lea     rcx, aVersion10; "version=\"1.0\""
0x180023de1  call    cs:__imp_SysAllocString
0x180023de7  mov     r15, rax
0x180023dea  test    rax, rax
0x180023ded  jz      short loc_180023DFA
0x180023def  xor     ecx, ecx; bstrString
0x180023df1  call    cs:__imp_SysFreeString
0x180023df7  mov     rbx, r15
0x180023dfa  test    rdi, rdi
0x180023dfd  jz      loc_1800242C4
0x180023e03  test    rbx, rbx
0x180023e06  jz      loc_1800242C4
0x180023e0c  mov     rax, [rsi]
0x180023e0f  lea     r9, [rbp+57h+arg_0]
0x180023e13  mov     r8, rbx
0x180023e16  mov     rdx, rdi
0x180023e19  mov     rcx, rsi
0x180023e1c  mov     rax, [rax+1A0h]
0x180023e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e28  mov     r15d, eax
0x180023e2b  test    eax, eax
0x180023e2d  js      loc_180024292
0x180023e33  mov     rax, [rsi]
0x180023e36  xor     r8d, r8d
0x180023e39  mov     rdx, [rbp+57h+arg_0]
0x180023e3d  mov     rcx, rsi
0x180023e40  mov     rax, [rax+0A8h]
0x180023e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e4c  mov     r15d, eax
0x180023e4f  test    eax, eax
0x180023e51  js      loc_1800242AB
0x180023e57  xor     r15d, r15d
0x180023e5a  mov     rcx, [rbp+57h+arg_0]
0x180023e5e  test    rcx, rcx
0x180023e61  jz      short loc_180023E6F
0x180023e63  mov     rax, [rcx]
0x180023e66  mov     rax, [rax+10h]
0x180023e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e6f  mov     rcx, rbx; bstrString
0x180023e72  call    cs:__imp_SysFreeString
0x180023e78  mov     rcx, rdi; bstrString
0x180023e7b  call    cs:__imp_SysFreeString
0x180023e81  test    r15d, r15d
0x180023e84  jnz     loc_180023B85
0x180023e8a  mov     rdi, [r13+228h]
0x180023e91  mov     eax, [rdi+14h]
0x180023e94  cmp     eax, 8
0x180023e97  jnz     loc_180024187
0x180023e9d  xor     ecx, ecx
0x180023e9f  mov     [rbp+57h+arg_0], rcx
0x180023ea3  mov     [rbp+57h+arg_10], rcx
0x180023ea7  lea     rax, [rbp+57h+arg_0]
0x180023eab  mov     [rsp+0D0h+var_A8], rax; struct IXMLDOMNode **
0x180023eb0  mov     [rsp+0D0h+ppv], rcx; unsigned __int16 *
0x180023eb5  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WLA"...
0x180023ebc  lea     r8, aWlanapprofile; "WLANAPProfile"
0x180023ec3  mov     rdx, rsi; struct IXMLDOMNode *
0x180023ec6  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180023ec9  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180023ece  mov     r15d, eax
0x180023ed1  mov     rbx, [rbp+57h+arg_0]
0x180023ed5  test    eax, eax
0x180023ed7  jz      loc_1800242CF
0x180023edd  mov     rax, [rsi]
0x180023ee0  lea     r8, [rbp+57h+arg_10]
0x180023ee4  mov     rdx, rbx
0x180023ee7  mov     rcx, rsi
0x180023eea  mov     rax, [rax+0A0h]
0x180023ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ef6  nop
0x180023ef7  mov     rcx, [rbp+57h+arg_10]
0x180023efb  test    rcx, rcx
0x180023efe  jz      short loc_180023F0D
0x180023f00  mov     rax, [rcx]
0x180023f03  mov     rax, [rax+10h]
0x180023f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f0c  nop
0x180023f0d  test    rbx, rbx
0x180023f10  jz      short loc_180023F22
0x180023f12  mov     rax, [rbx]
0x180023f15  mov     rcx, rbx
0x180023f18  mov     rax, [rax+10h]
0x180023f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f21  nop
0x180023f22  test    r15d, r15d
0x180023f25  jnz     loc_180023B85
0x180023f2b  xor     r13d, r13d
0x180023f2e  mov     [rbp+57h+bstrString], r13
0x180023f32  mov     ebx, r13d
0x180023f35  mov     word ptr [rbp+57h+arg_0], r13w
0x180023f3a  mov     [rbp+57h+arg_10], r13
0x180023f3e  lea     rcx, [rbp+57h+var_80]; pvarg
0x180023f42  call    cs:__imp_VariantInit
0x180023f48  lea     rcx, [rbp+57h+var_60]; pvarg
0x180023f4c  call    cs:__imp_VariantInit
0x180023f52  lea     rax, [rbp+57h+arg_10]
0x180023f56  mov     [rsp+0D0h+ppv], rax; ppv
0x180023f5b  lea     r9, IID_IXMLDOMDocument2; riid
0x180023f62  xor     edx, edx; pUnkOuter
0x180023f64  mov     r8d, 1; dwClsContext
0x180023f6a  lea     rcx, CLSID_DOMDocument60; rclsid
0x180023f71  call    cs:__imp_CoCreateInstance
0x180023f77  mov     r15d, eax
0x180023f7a  test    eax, eax
0x180023f7c  js      loc_18002431A
0x180023f82  mov     rcx, [rbp+57h+arg_10]
0x180023f86  mov     rax, [rcx]
0x180023f89  xor     edx, edx
0x180023f8b  mov     rax, [rax+1F8h]
0x180023f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f97  mov     r15d, eax
0x180023f9a  test    eax, eax
0x180023f9c  js      loc_180024333
0x180023fa2  mov     r15d, r13d
0x180023fa5  mov     rbx, [rbp+57h+arg_10]
0x180023fa9  mov     [rbp+57h+arg_10], r13
0x180023fad  lea     rcx, [rbp+57h+var_60]; pvarg
0x180023fb1  call    cs:__imp_VariantClear
0x180023fb7  lea     rcx, [rbp+57h+var_80]; pvarg
0x180023fbb  call    cs:__imp_VariantClear
0x180023fc1  xor     ecx, ecx; bstrString
0x180023fc3  call    cs:__imp_SysFreeString
0x180023fc9  nop
0x180023fca  mov     rcx, [rbp+57h+arg_10]
0x180023fce  test    rcx, rcx
0x180023fd1  jz      short loc_180023FE0
0x180023fd3  mov     rax, [rcx]
0x180023fd6  mov     rax, [rax+10h]
0x180023fda  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
