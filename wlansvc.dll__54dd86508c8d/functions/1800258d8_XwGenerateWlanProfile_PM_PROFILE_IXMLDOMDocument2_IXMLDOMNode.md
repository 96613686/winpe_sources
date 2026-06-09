# XwGenerateWlanProfile(_PM_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x1800258d8`
- end: `0x1800263c0`
- name: `?XwGenerateWlanProfile@@YAKPEAU_PM_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `2792`
- prototype: `unsigned int(struct _PM_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023b50`

## callees

- `0x18002263c`
- `0x1800234b0`
- `0x180024930`
- `0x180024de8`
- `0x1800258d8`
- `0x1800263d0`
- `0x180026abc`
- `0x180026e60`
- `0x18006fd60`
- `0x18020a2a0`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180025a0b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180025a0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180025af0`
- `OLEAUT32!__imp_SysAllocString` at `0x180025b8a`
- `OLEAUT32!__imp_SysAllocString` at `0x180025eca`
- `OLEAUT32!__imp_SysAllocString` at `0x180025f3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180025af0`
- `OLEAUT32!__imp_SysAllocString` at `0x180025b8a`
- `OLEAUT32!__imp_SysAllocString` at `0x180025eca`
- `OLEAUT32!__imp_SysAllocString` at `0x180025f3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b33`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180025bcd`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ede`
- `OLEAUT32!__imp_SysFreeString` at `0x180025f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180025f36`
- `OLEAUT32!__imp_SysFreeString` at `0x180025f56`
- `OLEAUT32!__imp_SysFreeString` at `0x180025a6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b33`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180025b9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180025bcd`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ec1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ede`
- `OLEAUT32!__imp_SysFreeString` at `0x180025f09`
- `OLEAUT32!__imp_SysFreeString` at `0x180025f36`
- `OLEAUT32!__imp_SysFreeString` at `0x180025f56`
- `OLEAUT32!__imp_VariantInit` at `0x180025956`
- `OLEAUT32!__imp_VariantInit` at `0x180025cb7`
- `OLEAUT32!__imp_VariantInit` at `0x180025956`
- `OLEAUT32!__imp_VariantInit` at `0x180025cb7`
- `OLEAUT32!__imp_VariantClear` at `0x180025a61`
- `OLEAUT32!__imp_VariantClear` at `0x180025d13`
- `OLEAUT32!__imp_VariantClear` at `0x180025a61`
- `OLEAUT32!__imp_VariantClear` at `0x180025d13`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025cd8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025cd8`

## string_xrefs

- `0x180025926`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180025976`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180025b14`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180025bae`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002607e`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800260d2`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180026105`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180026153`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800261bc`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800261f7`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180026233`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002626b`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800262b4`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002631f`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180026377`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180026326`: `security`
- `0x180025e50`: `http://www.microsoft.com/networking/WLAN/profile/v3`
- `0x180026185`: `http://www.microsoft.com/networking/WLAN/profile/v5`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall XwGenerateWlanProfile(struct _PM_PROFILE *a1, struct IXMLDOMDocument2 *a2, struct IXMLDOMNode *a3)
{
  __int64 v5; // r13
  unsigned int SSIDConfig; // r15d
  const unsigned __int16 *v7; // r14
  struct IXMLDOMNode *v8; // rbx
  OLECHAR *v9; // rdi
  struct IXMLDOMNode *v10; // rsi
  int v11; // eax
  struct IXMLDOMNode *v12; // r14
  struct IXMLDOMNode *v13; // rdi
  unsigned __int16 *v14; // rbx
  unsigned int i; // eax
  const OLECHAR *v16; // rbx
  unsigned __int16 *v17; // rbx
  unsigned int j; // eax
  const OLECHAR *v19; // rbx
  unsigned int *v20; // rsi
  struct IXMLDOMNode *v21; // rbx
  struct IXMLDOMNode *v22; // rbx
  LONG v23; // edi
  HRESULT v24; // eax
  __int64 v26; // r13
  struct IXMLDOMNode *v27; // rbx
  struct IXMLDOMNode *v28; // rsi
  struct IXMLDOMNode *v29; // rdi
  struct IXMLDOMNode *v30; // rbx
  __int64 v31; // rsi
  unsigned __int16 *v32; // rdi
  unsigned int m; // ecx
  const OLECHAR *v34; // rdi
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned int k; // edi
  struct IXMLDOMNode **v39; // r9
  struct IXMLDOMNode **v40; // r9
  struct IXMLDOMNode **v41; // [rsp+28h] [rbp-41h]
  struct IXMLDOMNode **v42; // [rsp+28h] [rbp-41h]
  struct IXMLDOMNode **v43; // [rsp+28h] [rbp-41h]
  struct IXMLDOMNode **v44; // [rsp+28h] [rbp-41h]
  struct IXMLDOMNode **v45; // [rsp+30h] [rbp-39h]
  struct IXMLDOMNode **v46; // [rsp+30h] [rbp-39h]
  struct IXMLDOMNode **v47; // [rsp+38h] [rbp-31h]
  struct IXMLDOMNode *v48; // [rsp+40h] [rbp-29h] BYREF
  struct IXMLDOMNode *v49; // [rsp+48h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-19h] BYREF
  struct IXMLDOMNode *v51; // [rsp+68h] [rbp-1h] BYREF
  __int64 v52; // [rsp+70h] [rbp+7h] BYREF
  __int64 v53; // [rsp+78h] [rbp+Fh]
  __int64 v54; // [rsp+80h] [rbp+17h]
  __int64 v55; // [rsp+88h] [rbp+1Fh]
  struct IXMLDOMNode *v56; // [rsp+D0h] [rbp+67h] BYREF
  struct IXMLDOMNode *v57; // [rsp+E0h] [rbp+77h]
  struct IXMLDOMNode *v58; // [rsp+E8h] [rbp+7Fh] BYREF

  v57 = a3;
  v56 = 0;
  v52 = 0;
  v5 = *((_QWORD *)a1 + 69);
  v53 = v5;
  SSIDConfig = XcAddChildElement(
                 a2,
                 a3,
                 L"WLANProfile",
                 L"http://www.microsoft.com/networking/WLAN/profile/v1",
                 0,
                 &v56);
  if ( SSIDConfig )
    goto LABEL_46;
  v7 = (const unsigned __int16 *)((char *)a1 + 24);
  v8 = 0;
  v9 = 0;
  VariantInit(&pvarg);
  v49 = 0;
  v48 = 0;
  v58 = 0;
  SSIDConfig = XcAddChildElement(a2, v56, L"name", L"http://www.microsoft.com/networking/WLAN/profile/v1", v7, &v49);
  v10 = v49;
  if ( SSIDConfig )
    goto LABEL_10;
  if ( v49 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v49->lpVtbl->AddRef)(v49);
    v8 = v10;
  }
  v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v8->lpVtbl->get_nodeTypedValue)(v8, &pvarg);
  SSIDConfig = v11;
  if ( v11 < 0 )
  {
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      SSIDConfig = (unsigned __int16)v11;
  }
  else if ( pvarg.vt != 8 || (SSIDConfig = 0, !pvarg.llVal) )
  {
    SSIDConfig = 1168;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  if ( SSIDConfig || !lstrcmpW(pvarg.bstrVal, v7) )
  {
LABEL_10:
    v12 = 0;
  }
  else
  {
    SysFreeString(0);
    v9 = SysAllocString(v7);
    v12 = 0;
    if ( v9 )
    {
      SysFreeString(0);
      v35 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, struct IXMLDOMNode **))a2->lpVtbl->createCDATASection)(
              a2,
              v9,
              &v58);
      SSIDConfig = v35;
      if ( v35 >= 0 )
        goto LABEL_87;
      if ( (v35 & 0x1FFF0000) == 0x70000 )
        SSIDConfig = (unsigned __int16)v35;
      if ( !SSIDConfig )
      {
LABEL_87:
        v36 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v10->lpVtbl->get_firstChild)(
                v10,
                &v48);
        SSIDConfig = v36;
        if ( v36 >= 0 )
          goto LABEL_88;
        if ( (v36 & 0x1FFF0000) == 0x70000 )
          SSIDConfig = (unsigned __int16)v36;
        if ( !SSIDConfig )
        {
LABEL_88:
          v37 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))v10->lpVtbl->replaceChild)(
                  v10,
                  v58,
                  v48,
                  0);
          SSIDConfig = v37;
          if ( v37 < 0 )
          {
            if ( (v37 & 0x1FFF0000) == 0x70000 )
              SSIDConfig = (unsigned __int16)v37;
          }
          else
          {
            SSIDConfig = 0;
          }
        }
      }
    }
    else
    {
      v9 = 0;
      SSIDConfig = 14;
    }
  }
  if ( v58 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v58->lpVtbl->Release)(v58);
  if ( v48 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v48->lpVtbl->Release)(v48);
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
  VariantClear(&pvarg);
  SysFreeString(v9);
  if ( SSIDConfig )
    goto LABEL_46;
  v13 = v56;
  SSIDConfig = XwpGenerateSSIDConfig((struct _DOT11_AC_PROFILE *)v5, a2, v56);
  if ( SSIDConfig )
    goto LABEL_46;
  SSIDConfig = XwpGenerateHotspot2Config((struct _DOT11_AC_PROFILE *)v5, a2, v13);
  if ( SSIDConfig )
    goto LABEL_46;
  v14 = 0;
  SSIDConfig = 1206;
  for ( i = 0; i < 2; ++i )
  {
    if ( dword_1802398A8[4 * i] == *(_DWORD *)(v5 + 16) )
    {
      v16 = (&off_1802398A0)[2 * i];
      SysFreeString(0);
      v14 = SysAllocString(v16);
      if ( v14 )
      {
        SysFreeString(0);
        SSIDConfig = XcAddChildElement(
                       a2,
                       v13,
                       L"connectionType",
                       L"http://www.microsoft.com/networking/WLAN/profile/v1",
                       v14,
                       0);
      }
      else
      {
        v14 = 0;
        SSIDConfig = 14;
      }
      break;
    }
  }
  SysFreeString(v14);
  if ( SSIDConfig )
    goto LABEL_46;
  if ( (*(_BYTE *)(v5 + 4) & 1) != 0 )
  {
    v17 = 0;
    SSIDConfig = 1206;
    for ( j = 0; j < 2; ++j )
    {
      if ( dword_180239948[4 * j] == (*(_DWORD *)(v5 + 24) & 1) )
      {
        v19 = (&off_180239940)[2 * j];
        SysFreeString(0);
        v17 = SysAllocString(v19);
        if ( v17 )
        {
          SysFreeString(0);
          SSIDConfig = XcAddChildElement(
                         a2,
                         v13,
                         L"connectionMode",
                         L"http://www.microsoft.com/networking/WLAN/profile/v1",
                         v17,
                         0);
        }
        else
        {
          v17 = 0;
          SSIDConfig = 14;
        }
        break;
      }
    }
    SysFreeString(v17);
    if ( SSIDConfig )
      goto LABEL_46;
  }
  if ( (*(_BYTE *)(v5 + 4) & 2) != 0 )
  {
    SSIDConfig = XcAddChildElementBoolean(
                   a2,
                   v13,
                   L"autoSwitch",
                   L"http://www.microsoft.com/networking/WLAN/profile/v1",
                   (*(_DWORD *)(v5 + 24) >> 2) & 1,
                   v41);
    if ( SSIDConfig )
      goto LABEL_46;
  }
  v20 = *(unsigned int **)(v5 + 32);
  v58 = 0;
  v21 = 0;
  v48 = 0;
  if ( *v20 > 0x20 )
  {
    SSIDConfig = 1206;
  }
  else if ( *v20 || v20[104] )
  {
    SSIDConfig = XcGetSingleNode(v13, L"WLANProfile:MSM", &v58);
    if ( SSIDConfig == 1168 )
      SSIDConfig = XcAddChildElement(a2, v13, L"MSM", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v58);
    if ( !SSIDConfig )
    {
      SSIDConfig = XcAddChildElement(
                     a2,
                     v58,
                     L"connectivity",
                     L"http://www.microsoft.com/networking/WLAN/profile/v1",
                     0,
                     &v48);
      v21 = v48;
      if ( !SSIDConfig )
      {
        for ( k = 0; k < *v20; ++k )
        {
          SSIDConfig = XcAddChildElementEnum(
                         a2,
                         v21,
                         L"phyType",
                         L"http://www.microsoft.com/networking/WLAN/profile/v1",
                         v20[k + 1],
                         (const struct _XC_STRING_VALUE_MAPPING *)&off_1802398C0,
                         8u,
                         v47);
          if ( SSIDConfig )
            goto LABEL_120;
        }
        if ( v20[104] )
          SSIDConfig = XcAddChildElementBoolean(
                         a2,
                         v21,
                         L"QoSDSCPToUPMappingAllowed",
                         L"http://www.microsoft.com/networking/WLAN/profile/v5",
                         v20[104],
                         v43);
LABEL_120:
        v13 = v56;
      }
    }
  }
  else
  {
    SSIDConfig = 0;
  }
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v21->lpVtbl->Release)(v21);
  if ( v58 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v58->lpVtbl->Release)(v58);
  if ( SSIDConfig )
    goto LABEL_46;
  SSIDConfig = XwpGenerateSecuritySettings(
                 (struct _DOT11_MSM_SECURITY_SETTINGS *)(*(_QWORD *)(v5 + 32) + 424LL),
                 a2,
                 v13);
  if ( SSIDConfig )
    goto LABEL_46;
  v26 = *(_QWORD *)(v5 + 32);
  v27 = 0;
  v49 = 0;
  v28 = 0;
  v51 = 0;
  v58 = 0;
  v54 = 0;
  v29 = 0;
  v48 = 0;
  v55 = 0;
  if ( *(_DWORD *)(v26 + 400) || (SSIDConfig = 0, *(_DWORD *)(v26 + 432)) )
  {
    SSIDConfig = XcAddChildElement(a2, v56, L"IHV", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v49);
    v27 = v49;
    if ( !SSIDConfig )
    {
      SSIDConfig = XcAddChildElement(
                     a2,
                     v49,
                     L"OUIHeader",
                     L"http://www.microsoft.com/networking/WLAN/profile/v1",
                     0,
                     &v51);
      v28 = v51;
      if ( !SSIDConfig )
      {
        SSIDConfig = XcAddChildElementHexBinary(
                       a2,
                       v51,
                       L"OUI",
                       L"http://www.microsoft.com/networking/WLAN/profile/v1",
                       (unsigned __int8 *)(v26 + 448),
                       3u,
                       v45);
        if ( !SSIDConfig )
        {
          SSIDConfig = XcAddChildElementHexBinary(
                         a2,
                         v28,
                         L"type",
                         L"http://www.microsoft.com/networking/WLAN/profile/v1",
                         (unsigned __int8 *)(v26 + 451),
                         1u,
                         v46);
          if ( !SSIDConfig )
          {
            if ( !*(_DWORD *)(v26 + 400)
              || !*(_QWORD *)(v26 + 408)
              || (SSIDConfig = XcAddChildElement(
                                 a2,
                                 v27,
                                 L"connectivity",
                                 L"http://www.microsoft.com/networking/WLAN/profile/v1",
                                 0,
                                 &v58),
                  v12 = v58,
                  !SSIDConfig)
              && (SSIDConfig = XcAddChildElementXml(a2, v58, *(const unsigned __int16 **)(v26 + 408), v39)) == 0 )
            {
              if ( !*(_DWORD *)(v26 + 432)
                || !*(_QWORD *)(v26 + 440)
                || (SSIDConfig = XcAddChildElement(
                                   a2,
                                   v27,
                                   L"security",
                                   L"http://www.microsoft.com/networking/WLAN/profile/v1",
                                   0,
                                   &v48),
                    v29 = v48,
                    !SSIDConfig)
                && (SSIDConfig = XcAddChildElementXml(a2, v48, *(const unsigned __int16 **)(v26 + 440), v40)) == 0 )
              {
                if ( *(_DWORD *)(v26 + 436) )
                  SSIDConfig = XcAddChildElementBoolean(
                                 a2,
                                 v27,
                                 L"useMSOneX",
                                 L"http://www.microsoft.com/networking/WLAN/profile/v1",
                                 *(_DWORD *)(v26 + 436),
                                 v44);
              }
            }
          }
        }
      }
    }
  }
  if ( v29 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v29->lpVtbl->Release)(v29);
  if ( v12 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
  if ( v28 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
  if ( v27 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v27->lpVtbl->Release)(v27);
  if ( SSIDConfig )
    goto LABEL_46;
  SSIDConfig = 0;
  v30 = 0;
  v58 = 0;
  v31 = v53;
  if ( (*(_BYTE *)(v53 + 4) & 8) != 0 )
  {
    SSIDConfig = XcAddChildElement(
                   a2,
                   v56,
                   L"MacRandomization",
                   L"http://www.microsoft.com/networking/WLAN/profile/v3",
                   0,
                   &v58);
    if ( SSIDConfig )
    {
      v30 = v58;
    }
    else
    {
      v32 = 0;
      SSIDConfig = 1206;
      for ( m = 0; ; ++m )
      {
        v30 = v58;
        if ( m >= 4 )
          break;
        if ( dword_18022D008[4 * m] == ((*(_DWORD *)(v31 + 24) & 0x10) == 0) )
        {
          v34 = (&off_18022D000)[2 * m];
          SysFreeString(0);
          v32 = SysAllocString(v34);
          if ( v32 )
          {
            SysFreeString(0);
            SSIDConfig = XcAddChildElement(
                           a2,
                           v30,
                           L"enableRandomization",
                           L"http://www.microsoft.com/networking/WLAN/profile/v3",
                           v32,
                           0);
          }
          else
          {
            v32 = 0;
            SSIDConfig = 14;
          }
          break;
        }
      }
      SysFreeString(v32);
      if ( !SSIDConfig
        && ((*(_DWORD *)(v31 + 24) & 0x20) == 0
         || (SSIDConfig = XcAddChildElementBoolean(
                            a2,
                            v30,
                            L"randomizeEveryday",
                            L"http://www.microsoft.com/networking/WLAN/profile/v3",
                            *(_DWORD *)(v31 + 24) & 0x20,
                            v42)) == 0) )
      {
        v23 = *(_DWORD *)(v31 + 64);
        if ( v23 )
        {
          VariantInit(&pvarg);
          pvarg.vt = 19;
          pvarg.lVal = v23;
          v24 = VariantChangeType(&pvarg, &pvarg, 0, 8u);
          SSIDConfig = v24;
          if ( v24 >= 0 )
            goto LABEL_50;
          if ( (v24 & 0x1FFF0000) == 0x70000 )
            SSIDConfig = (unsigned __int16)v24;
          if ( !SSIDConfig )
LABEL_50:
            SSIDConfig = XcAddChildElement(
                           a2,
                           v30,
                           L"randomizationSeed",
                           L"http://www.microsoft.com/networking/WLAN/profile/v3",
                           pvarg.bstrVal,
                           0);
          VariantClear(&pvarg);
        }
      }
    }
  }
  if ( v30 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v30->lpVtbl->Release)(v30);
  if ( SSIDConfig )
  {
LABEL_46:
    v22 = v56;
    ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, __int64 *))v57->lpVtbl->removeChild)(
      v57,
      v56,
      &v52);
  }
  else
  {
    v22 = v56;
  }
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v22 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v22->lpVtbl->Release)(v22);
  return SSIDConfig;
}

```

## disassembly

```asm
0x1800258d8  mov     [rsp-8+arg_8], rbx
0x1800258dd  mov     [rsp-8+arg_10], r8
0x1800258e2  push    rbp
0x1800258e3  push    rsi
0x1800258e4  push    rdi
0x1800258e5  push    r12
0x1800258e7  push    r13
0x1800258e9  push    r14
0x1800258eb  push    r15
0x1800258ed  lea     rbp, [rsp-27h]
0x1800258f2  sub     rsp, 90h
0x1800258f9  mov     rax, r8
0x1800258fc  mov     r12, rdx
0x1800258ff  mov     rbx, rcx
0x180025902  xor     r14d, r14d
0x180025905  mov     [rbp+57h+arg_0], r14
0x180025909  mov     [rbp+57h+var_50], r14
0x18002590d  mov     r13, [rcx+228h]
0x180025914  mov     [rbp+57h+var_48], r13
0x180025918  lea     rcx, [rbp+57h+arg_0]
0x18002591c  mov     [rsp+0C0h+var_98], rcx; struct IXMLDOMNode **
0x180025921  mov     [rsp+0C0h+var_A0], r14; unsigned __int16 *
0x180025926  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18002592d  lea     r8, aWlanprofile; "WLANProfile"
0x180025934  mov     rdx, rax; struct IXMLDOMNode *
0x180025937  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18002593a  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18002593f  mov     r15d, eax
0x180025942  test    eax, eax
0x180025944  jnz     loc_180025C69
0x18002594a  lea     r14, [rbx+18h]
0x18002594e  xor     ebx, ebx
0x180025950  mov     edi, ebx
0x180025952  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180025956  call    cs:__imp_VariantInit
0x18002595c  mov     [rbp+57h+var_78], rbx
0x180025960  mov     [rbp+57h+var_80], rbx
0x180025964  mov     [rbp+57h+arg_18], rbx
0x180025968  lea     rax, [rbp+57h+var_78]
0x18002596c  mov     [rsp+0C0h+var_98], rax; struct IXMLDOMNode **
0x180025971  mov     [rsp+0C0h+var_A0], r14; unsigned __int16 *
0x180025976  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18002597d  lea     r8, aName_1; "name"
0x180025984  mov     rdx, [rbp+57h+arg_0]; struct IXMLDOMNode *
0x180025988  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18002598b  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180025990  mov     r15d, eax
0x180025993  mov     rsi, [rbp+57h+var_78]
0x180025997  test    eax, eax
0x180025999  jnz     short loc_180025A19
0x18002599b  test    rsi, rsi
0x18002599e  jz      short loc_1800259B2
0x1800259a0  mov     rax, [rsi]
0x1800259a3  mov     rcx, rsi
0x1800259a6  mov     rax, [rax+8]
0x1800259aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259af  mov     rbx, rsi
0x1800259b2  mov     rax, [rbx]
0x1800259b5  lea     rdx, [rbp+57h+pvarg]
0x1800259b9  mov     rcx, rbx
0x1800259bc  mov     rax, [rax+0F0h]
0x1800259c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c8  mov     r15d, eax
0x1800259cb  test    eax, eax
0x1800259cd  js      loc_180025FE1
0x1800259d3  mov     eax, 8
0x1800259d8  cmp     word ptr [rbp+57h+pvarg], ax
0x1800259dc  jnz     loc_180025FD6
0x1800259e2  xor     r15d, r15d
0x1800259e5  cmp     qword ptr [rbp+57h+pvarg+8], rdi
0x1800259e9  jz      loc_180025FD6
0x1800259ef  mov     rax, [rbx]
0x1800259f2  mov     rcx, rbx
0x1800259f5  mov     rax, [rax+10h]
0x1800259f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259fe  nop
0x1800259ff  test    r15d, r15d
0x180025a02  jnz     short loc_180025A19
0x180025a04  mov     rdx, r14; lpString2
0x180025a07  mov     rcx, qword ptr [rbp+57h+pvarg+8]; lpString1
0x180025a0b  call    cs:__imp_lstrcmpW
0x180025a11  test    eax, eax
0x180025a13  jnz     loc_180025F34
0x180025a19  xor     r14d, r14d
0x180025a1c  mov     rcx, [rbp+57h+arg_18]
0x180025a20  test    rcx, rcx
0x180025a23  jz      short loc_180025A32
0x180025a25  mov     rax, [rcx]
0x180025a28  mov     rax, [rax+10h]
0x180025a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a31  nop
0x180025a32  mov     rcx, [rbp+57h+var_80]
0x180025a36  test    rcx, rcx
0x180025a39  jz      short loc_180025A48
0x180025a3b  mov     rax, [rcx]
0x180025a3e  mov     rax, [rax+10h]
0x180025a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a47  nop
0x180025a48  test    rsi, rsi
0x180025a4b  jz      short loc_180025A5D
0x180025a4d  mov     rax, [rsi]
0x180025a50  mov     rcx, rsi
0x180025a53  mov     rax, [rax+10h]
0x180025a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a5c  nop
0x180025a5d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180025a61  call    cs:__imp_VariantClear
0x180025a67  mov     rcx, rdi; bstrString
0x180025a6a  call    cs:__imp_SysFreeString
0x180025a70  test    r15d, r15d
0x180025a73  jnz     loc_180025C69
0x180025a79  mov     rdi, [rbp+57h+arg_0]
0x180025a7d  mov     r8, rdi; struct IXMLDOMNode *
0x180025a80  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180025a83  mov     rcx, r13; struct _DOT11_AC_PROFILE *
0x180025a86  call    ?XwpGenerateSSIDConfig@@YAKPEAU_DOT11_AC_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XwpGenerateSSIDConfig(_DOT11_AC_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x180025a8b  mov     r15d, eax
0x180025a8e  test    eax, eax
0x180025a90  jnz     loc_180025C69
0x180025a96  mov     r8, rdi; struct IXMLDOMNode *
0x180025a99  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180025a9c  mov     rcx, r13; struct _DOT11_AC_PROFILE *
0x180025a9f  call    ?XwpGenerateHotspot2Config@@YAKPEAU_DOT11_AC_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XwpGenerateHotspot2Config(_DOT11_AC_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x180025aa4  mov     r15d, eax
0x180025aa7  test    eax, eax
0x180025aa9  jnz     loc_180025C69
0x180025aaf  mov     edx, [r13+10h]
0x180025ab3  mov     rbx, r14
0x180025ab6  mov     r15d, 4B6h
0x180025abc  mov     eax, r14d
0x180025abf  lea     rsi, __ImageBase
0x180025ac6  cmp     eax, 2
0x180025ac9  jnb     short loc_180025B30
0x180025acb  mov     ecx, eax
0x180025acd  add     rcx, rcx
0x180025ad0  cmp     ds:rva dword_1802398A8[rsi+rcx*8], edx
0x180025ad7  jz      short loc_180025ADD
0x180025ad9  inc     eax
0x180025adb  jmp     short loc_180025AC6
0x180025add  mov     rbx, ds:rva off_1802398A0[rsi+rcx*8]; "IBSS" ...
0x180025ae5  xor     ecx, ecx; bstrString
0x180025ae7  call    cs:__imp_SysFreeString
0x180025aed  mov     rcx, rbx; psz
0x180025af0  call    cs:__imp_SysAllocString
0x180025af6  mov     rbx, rax
0x180025af9  test    rax, rax
0x180025afc  jz      loc_180026054
0x180025b02  xor     ecx, ecx; bstrString
0x180025b04  call    cs:__imp_SysFreeString
0x180025b0a  mov     [rsp+0C0h+var_98], r14; struct IXMLDOMNode **
0x180025b0f  mov     [rsp+0C0h+var_A0], rbx; unsigned __int16 *
0x180025b14  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180025b1b  lea     r8, aConnectiontype; "connectionType"
0x180025b22  mov     rdx, rdi; struct IXMLDOMNode *
0x180025b25  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180025b28  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180025b2d  mov     r15d, eax
0x180025b30  mov     rcx, rbx; bstrString
0x180025b33  call    cs:__imp_SysFreeString
0x180025b39  test    r15d, r15d
0x180025b3c  jnz     loc_180025C69
0x180025b42  test    byte ptr [r13+4], 1
0x180025b47  jz      loc_180025BDC
0x180025b4d  mov     edx, [r13+18h]
0x180025b51  and     edx, 1
0x180025b54  mov     rbx, r14
0x180025b57  mov     r15d, 4B6h
0x180025b5d  mov     eax, r14d
0x180025b60  cmp     eax, 2
0x180025b63  jnb     short loc_180025BCA
0x180025b65  mov     ecx, eax
0x180025b67  add     rcx, rcx
0x180025b6a  cmp     ds:rva dword_180239948[rsi+rcx*8], edx
0x180025b71  jz      short loc_180025B77
0x180025b73  inc     eax
0x180025b75  jmp     short loc_180025B60
0x180025b77  mov     rbx, ds:rva off_180239940[rsi+rcx*8]; "auto" ...
0x180025b7f  xor     ecx, ecx; bstrString
0x180025b81  call    cs:__imp_SysFreeString
0x180025b87  mov     rcx, rbx; psz
0x180025b8a  call    cs:__imp_SysAllocString
0x180025b90  mov     rbx, rax
0x180025b93  test    rax, rax
0x180025b96  jz      loc_180026062
0x180025b9c  xor     ecx, ecx; bstrString
0x180025b9e  call    cs:__imp_SysFreeString
0x180025ba4  mov     [rsp+0C0h+var_98], r14; struct IXMLDOMNode **
0x180025ba9  mov     [rsp+0C0h+var_A0], rbx; unsigned __int16 *
0x180025bae  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180025bb5  lea     r8, aConnectionmode; "connectionMode"
0x180025bbc  mov     rdx, rdi; struct IXMLDOMNode *
0x180025bbf  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180025bc2  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180025bc7  mov     r15d, eax
0x180025bca  mov     rcx, rbx; bstrString
0x180025bcd  call    cs:__imp_SysFreeString
0x180025bd3  test    r15d, r15d
0x180025bd6  jnz     loc_180025C69
0x180025bdc  test    byte ptr [r13+4], 2
0x180025be1  jnz     loc_180026070
0x180025be7  mov     rsi, [r13+20h]
0x180025beb  mov     [rbp+57h+arg_18], r14
0x180025bef  mov     rbx, r14
0x180025bf2  mov     [rbp+57h+var_80], rbx
0x180025bf6  cmp     dword ptr [rsi], 20h ; ' '
0x180025bf9  ja      loc_180025F29
0x180025bff  cmp     [rsi], r14d
0x180025c02  ja      loc_1800260A7
0x180025c08  cmp     [rsi+1A0h], r14d
0x180025c0f  jnz     loc_1800260A7
0x180025c15  mov     r15d, r14d
0x180025c18  test    rbx, rbx
0x180025c1b  jz      short loc_180025C2D
0x180025c1d  mov     rax, [rbx]
0x180025c20  mov     rcx, rbx
0x180025c23  mov     rax, [rax+10h]
0x180025c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c2c  nop
0x180025c2d  mov     rcx, [rbp+57h+arg_18]
0x180025c31  test    rcx, rcx
0x180025c34  jz      short loc_180025C43
0x180025c36  mov     rax, [rcx]
0x180025c39  mov     rax, [rax+10h]
0x180025c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c42  nop
0x180025c43  test    r15d, r15d
0x180025c46  jnz     short loc_180025C69
0x180025c48  mov     rcx, [r13+20h]
0x180025c4c  add     rcx, 1A8h; struct _DOT11_MSM_SECURITY_SETTINGS *
0x180025c53  mov     r8, rdi; struct IXMLDOMNode *
0x180025c56  mov     rdx, r12; struct IXMLDOMDocument2 *
0x180025c59  call    ?XwpGenerateSecuritySettings@@YAKPEAU_DOT11_MSM_SECURITY_SETTINGS@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XwpGenerateSecuritySettings(_DOT11_MSM_SECURITY_SETTINGS *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x180025c5e  mov     r15d, eax
0x180025c61  test    eax, eax
0x180025c63  jz      loc_180025D85
0x180025c69  mov     rcx, [rbp+57h+arg_10]
0x180025c6d  mov     rax, [rcx]
0x180025c70  lea     r8, [rbp+57h+var_50]
0x180025c74  mov     rbx, [rbp+57h+arg_0]
0x180025c78  mov     rdx, rbx
0x180025c7b  mov     rax, [rax+0A0h]
0x180025c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c87  jmp     loc_180025D3C
0x180025c8c  mov     dword ptr [rsp+0C0h+var_A0], eax; int
0x180025c90  mov     r9, r13; unsigned __int16 *
0x180025c93  lea     r8, aRandomizeevery; "randomizeEveryday"
0x180025c9a  mov     rdx, rbx; struct IXMLDOMNode *
0x180025c9d  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180025ca0  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x180025ca5  mov     r15d, eax
0x180025ca8  test    eax, eax
0x180025caa  jnz     short loc_180025D1A
0x180025cac  mov     edi, [rsi+40h]
0x180025caf  test    edi, edi
0x180025cb1  jz      short loc_180025D1A
0x180025cb3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180025cb7  call    cs:__imp_VariantInit
0x180025cbd  mov     eax, 13h
0x180025cc2  mov     word ptr [rbp+57h+pvarg], ax
0x180025cc6  mov     dword ptr [rbp+57h+pvarg+8], edi
0x180025cc9  lea     r9d, [rax-0Bh]; vt
0x180025ccd  xor     r8d, r8d; wFlags
0x180025cd0  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x180025cd4  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x180025cd8  call    cs:__imp_VariantChangeType
0x180025cde  mov     r15d, eax
0x180025ce1  test    eax, eax
0x180025ce3  js      loc_1800263A6
0x180025ce9  mov     [rsp+0C0h+var_98], r14; struct IXMLDOMNode **
0x180025cee  mov     rax, qword ptr [rbp+57h+pvarg+8]
0x180025cf2  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x180025cf7  mov     r9, r13; unsigned __int16 *
0x180025cfa  lea     r8, aRandomizations; "randomizationSeed"
0x180025d01  mov     rdx, rbx; struct IXMLDOMNode *
0x180025d04  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180025d07  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180025d0c  mov     r15d, eax
0x180025d0f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180025d13  call    cs:__imp_VariantClear
0x180025d19  nop
0x180025d1a  test    rbx, rbx
0x180025d1d  jz      short loc_180025D2F
0x180025d1f  mov     rax, [rbx]
0x180025d22  mov     rcx, rbx
0x180025d25  mov     rax, [rax+10h]
0x180025d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d2e  nop
0x180025d2f  test    r15d, r15d
0x180025d32  jnz     loc_180025C69
0x180025d38  mov     rbx, [rbp+57h+arg_0]
0x180025d3c  mov     rcx, [rbp+57h+var_50]
0x180025d40  test    rcx, rcx
0x180025d43  jz      short loc_180025D52
0x180025d45  mov     rax, [rcx]
0x180025d48  mov     rax, [rax+10h]
0x180025d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d51  nop
0x180025d52  test    rbx, rbx
0x180025d55  jz      short loc_180025D67
0x180025d57  mov     rax, [rbx]
  ... truncated ...
```
