# WdcSaveSettingsToXml(_WDC_SETTINGS const *,ushort const *)

- ea: `0x18001b0cc`
- end: `0x18001bcf3`
- name: `?WdcSaveSettingsToXml@@YAJPEBU_WDC_SETTINGS@@PEBG@Z`
- size: `3111`
- prototype: `__int64 __fastcall(const struct _WDC_SETTINGS *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18006f5f8`

## callees

- `0x18000b854`
- `0x18001b0cc`
- `0x18001bcfc`
- `0x18001bf78`
- `0x18001c104`
- `0x18001c278`
- `0x180023fc8`
- `0x1800318a4`
- `0x1800737d4`
- `0x180074124`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001b8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b9db`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba3e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b9db`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b98b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001badd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b98b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001badd`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8bc`
- `OLEAUT32!__imp_VariantInit` at `0x18001b9ce`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8bc`
- `OLEAUT32!__imp_VariantInit` at `0x18001b9ce`
- `OLEAUT32!__imp_VariantClear` at `0x18001b995`
- `OLEAUT32!__imp_VariantClear` at `0x18001bae7`
- `OLEAUT32!__imp_VariantClear` at `0x18001b995`
- `OLEAUT32!__imp_VariantClear` at `0x18001bae7`
- `ole32!CoCreateInstance` at `0x18001b142`
- `ole32!CoCreateInstance` at `0x18001b142`

## string_xrefs

- `0x18001b15c`: `WdcSaveSettingsToXml`
- `0x18001b243`: `WdcSaveSettingsToXml`
- `0x18001b28a`: `WdcSaveSettingsToXml`
- `0x18001b2e6`: `WdcSaveSettingsToXml`
- `0x18001b44a`: `WdcSaveSettingsToXml`
- `0x18001b470`: `WdcSaveSettingsToXml`
- `0x18001b58d`: `WdcSaveSettingsToXml`
- `0x18001b5b7`: `WdcSaveSettingsToXml`
- `0x18001b6c7`: `WdcSaveSettingsToXml`
- `0x18001bc47`: `WdcSaveSettingsToXml`
- `0x18001b223`: `configuration`
- `0x18001b912`: `WdcXmlSetAttribute`
- `0x18001b975`: `WdcXmlSetAttribute`
- `0x18001ba20`: `WdcXmlSetAttribute`
- `0x18001bac7`: `WdcXmlSetAttribute`

## pseudocode

```c
__int64 __fastcall WdcSaveSettingsToXml(const struct _WDC_SETTINGS *a1, const unsigned __int16 *a2)
{
  struct IXMLDOMElement *v2; // rsi
  struct IXMLDOMElement *v4; // r14
  __int64 v5; // r12
  HRESULT Instance; // eax
  int v7; // ebx
  int Element; // eax
  struct IXMLDOMNode *v9; // r15
  int v10; // eax
  struct IXMLDOMElement *v11; // rdi
  const unsigned __int16 *v12; // r8
  int v13; // eax
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r9
  int i; // r15d
  int v17; // eax
  int v18; // eax
  unsigned int j; // r15d
  unsigned int v20; // r12d
  __int64 v21; // r13
  int v22; // eax
  const unsigned __int16 *v23; // r9
  int v24; // eax
  int v25; // eax
  int v26; // r15d
  struct IXMLDOMNode *v27; // r12
  int v28; // eax
  const unsigned __int16 *v29; // rdx
  signed int k; // eax
  __int64 v31; // r12
  __int64 v32; // r13
  __int64 v33; // r15
  const unsigned __int16 *v34; // r8
  _DWORD *v35; // r12
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r12
  int v39; // edx
  unsigned int n; // eax
  _DWORD *v41; // r13
  LONG v42; // ebx
  BSTR v43; // rax
  OLECHAR *v44; // r15
  BSTR v45; // rdx
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  HRESULT (__stdcall *setAttribute)(IXMLDOMElement *, BSTR, VARIANT); // rax
  int v48; // eax
  int v49; // eax
  const OLECHAR *v50; // rbx
  OLECHAR *v51; // r15
  BSTR v52; // rax
  HRESULT (__stdcall *v53)(IXMLDOMElement *, BSTR, VARIANT); // rax
  int v54; // eax
  const unsigned __int16 *v55; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-79h]
  LPVOID *ppva; // [rsp+20h] [rbp-79h]
  LPVOID *ppvb; // [rsp+20h] [rbp-79h]
  struct IXMLDOMElement *v60; // [rsp+30h] [rbp-69h] BYREF
  struct IXMLDOMDocument *v61; // [rsp+38h] [rbp-61h] BYREF
  struct IXMLDOMElement *v62; // [rsp+40h] [rbp-59h] BYREF
  struct IXMLDOMElement *v63; // [rsp+48h] [rbp-51h] BYREF
  struct IXMLDOMNode *v64; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-41h] BYREF
  __int64 v66; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v67; // [rsp+78h] [rbp-21h] BYREF
  _DWORD *v68; // [rsp+80h] [rbp-19h]
  __int64 m; // [rsp+88h] [rbp-11h]
  __int128 v70; // [rsp+90h] [rbp-9h] BYREF
  IRecordInfo *pRecInfo; // [rsp+A0h] [rbp+7h]
  int v74; // [rsp+110h] [rbp+77h]
  signed int v75; // [rsp+118h] [rbp+7Fh]

  v2 = 0;
  v61 = 0;
  v66 = 0;
  v64 = 0;
  v4 = 0;
  v60 = 0;
  v5 = 1;
  v63 = 0;
  v62 = 0;
  v67 = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
               (LPVOID *)&v61);
  v7 = Instance;
  if ( Instance < 0 )
    goto LABEL_2;
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))v61->lpVtbl->put_async)(v61, 0);
  v7 = Instance;
  if ( Instance < 0 )
    goto LABEL_2;
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))v61->lpVtbl->put_validateOnParse)(v61, 0);
  v7 = Instance;
  if ( Instance < 0
    || (Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))v61->lpVtbl->put_resolveExternals)(v61, 0),
        v7 = Instance,
        Instance < 0)
    || (Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const wchar_t *, const wchar_t *, __int64 *))v61->lpVtbl->createProcessingInstruction)(
                     v61,
                     L"xml",
                     L" version='1.0' encoding='UTF-8'",
                     &v66),
        v7 = Instance,
        Instance < 0)
    || (Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64, _QWORD))v61->lpVtbl->appendChild)(
                     v61,
                     v66,
                     0),
        v7 = Instance,
        Instance < 0) )
  {
LABEL_2:
    LODWORD(ppv) = Instance;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
      "WdcSaveSettingsToXml",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_127;
  }
  Element = WdcXmlCreateElement(v61, (struct IXMLDOMNode *)v61, L"configuration", (struct IXMLDOMElement **)&v64);
  v7 = Element;
  if ( Element >= 0 )
  {
    v9 = v64;
    v10 = WdcXmlCreateElement(v61, v64, L"tabpane", &v60);
    v7 = v10;
    if ( v10 < 0 )
    {
LABEL_11:
      LODWORD(ppv) = v10;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
        "WdcSaveSettingsToXml",
        0,
        L"FAILURE: 0x%08x",
        ppv);
      v11 = v60;
      goto LABEL_123;
    }
    v11 = v60;
    v12 = L"true";
    if ( !*((_DWORD *)a1 + 767) )
      v12 = L"false";
    v13 = WdcXmlSetAttribute(v60, L"autocolumns", v12);
    v7 = v13;
    if ( v13 >= 0 )
    {
      if ( v11 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
        v60 = 0;
      }
      v10 = WdcXmlCreateElement(v61, v9, L"chartpane", &v60);
      v7 = v10;
      if ( v10 < 0 )
        goto LABEL_11;
      v11 = v60;
      v13 = WdcXmlSetAttribute(v60, L"width", *(_DWORD *)a1);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v14 = L"true";
        if ( !*((_DWORD *)a1 + 1) )
          v14 = L"false";
        v13 = WdcXmlSetAttribute(v11, L"hidden", v14);
        v7 = v13;
        if ( v13 >= 0 )
        {
          if ( v11 )
          {
            ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
            v60 = 0;
          }
          v10 = WdcXmlCreateElement(v61, v9, L"cpuchart", &v60);
          v7 = v10;
          if ( v10 >= 0 )
          {
            v11 = v60;
            for ( i = 0; i < 64; ++i )
            {
              if ( (v5 & *((_QWORD *)a1 + 1)) == 0 )
              {
                v17 = WdcXmlCreateElement(v61, (struct IXMLDOMNode *)v11, L"node", v15, i, &v63);
                v7 = v17;
                if ( v17 < 0 )
                {
                  LODWORD(ppv) = v17;
                  WdcDebugMessage(
                    "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                    "WdcSaveSettingsToXml",
                    0,
                    L"FAILURE: 0x%08x",
                    ppv);
                  v2 = v63;
                  goto LABEL_121;
                }
                v2 = v63;
                v18 = WdcXmlSetAttribute(v63, L"hidden", L"true");
                v7 = v18;
                if ( v18 < 0 )
                {
                  LODWORD(ppv) = v18;
                  WdcDebugMessage(
                    "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                    "WdcSaveSettingsToXml",
                    0,
                    L"FAILURE: 0x%08x",
                    ppv);
                  goto LABEL_121;
                }
                if ( v2 )
                {
                  ((void (__fastcall *)(struct IXMLDOMElement *))v2->lpVtbl->Release)(v2);
                  v2 = 0;
                  v63 = 0;
                }
              }
              v5 *= 2;
            }
            for ( j = 0; j < 0x40; ++j )
            {
              v20 = 0;
              v21 = 1;
              while ( v20 < 0x40 )
              {
                if ( (v21 & *((_QWORD *)a1 + (int)j + 2)) == 0 )
                {
                  v22 = WdcXmlCreateElement(v61, (struct IXMLDOMNode *)v11, L"node", v15, j, &v63);
                  v7 = v22;
                  if ( v22 < 0 )
                    goto LABEL_51;
                  v2 = v63;
                  v24 = WdcXmlCreateElement(v61, (struct IXMLDOMNode *)v63, L"cpu", v23, v20, &v62);
                  v7 = v24;
                  if ( v24 < 0 )
                    goto LABEL_50;
                  v4 = v62;
                  v25 = WdcXmlSetAttribute(v62, L"hidden", L"true");
                  v7 = v25;
                  if ( v25 < 0 )
                    goto LABEL_117;
                  if ( v4 )
                  {
                    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
                    v4 = 0;
                    v62 = 0;
                  }
                  if ( v2 )
                  {
                    ((void (__fastcall *)(struct IXMLDOMElement *))v2->lpVtbl->Release)(v2);
                    v2 = 0;
                    v63 = 0;
                  }
                }
                ++v20;
                v21 *= 2;
              }
            }
            if ( v11 )
            {
              ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
              v11 = 0;
              v60 = 0;
            }
            v26 = 0;
            v27 = v64;
            while ( v26 < 5 )
            {
              v28 = WdcXmlCreateElement(v61, v27, L"tab", L"id", (const unsigned __int16 *)(&WdcTabXmlIds)[v26], &v60);
              v7 = v28;
              if ( v28 < 0 )
              {
LABEL_65:
                LODWORD(ppv) = v28;
                WdcDebugMessage(
                  "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                  "WdcSaveSettingsToXml",
                  0,
                  L"FAILURE: 0x%08x",
                  ppv);
                v11 = v60;
                goto LABEL_119;
              }
              v11 = v60;
              v25 = WdcXmlSetAttribute(v60, L"chartview", *((_DWORD *)a1 + v26 + 133));
              v7 = v25;
              if ( v25 < 0 )
                goto LABEL_117;
              v25 = v26 == *((_DWORD *)a1 + 132)
                  ? WdcXmlSetAttribute(v11, L"focused", L"true")
                  : WdcXmlRemoveAttribute(v11, v29);
              v7 = v25;
              if ( v25 < 0 )
                goto LABEL_117;
              if ( v11 )
              {
                ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
                v11 = 0;
                v60 = 0;
              }
              ++v26;
            }
            for ( k = 0; ; k = v75 + 1 )
            {
              v75 = k;
              if ( (unsigned int)k >= 0x11 )
                break;
              v31 = k;
              v32 = 3LL * k;
              v33 = dword_180098824[3 * k];
              v28 = WdcXmlCreateElement(
                      v61,
                      v64,
                      L"tab",
                      L"id",
                      (const unsigned __int16 *)(&WdcTabXmlIds)[dword_180098820[3 * k]],
                      &v60);
              v7 = v28;
              if ( v28 < 0 )
                goto LABEL_65;
              v11 = v60;
              v22 = WdcXmlCreateElement(
                      v61,
                      (struct IXMLDOMNode *)v60,
                      L"table",
                      L"id",
                      (const unsigned __int16 *)(&WdcTableXmlIds)[v33],
                      &v63);
              v7 = v22;
              if ( v22 < 0 )
              {
LABEL_51:
                LODWORD(ppv) = v22;
                WdcDebugMessage(
                  "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                  "WdcSaveSettingsToXml",
                  0,
                  L"FAILURE: 0x%08x",
                  ppv);
                v2 = v63;
                goto LABEL_119;
              }
              v2 = v63;
              v34 = L"true";
              v35 = (_DWORD *)((char *)a1 + 148 * v31 + 552);
              v68 = v35;
              if ( !*v35 )
                v34 = L"false";
              v25 = WdcXmlSetAttribute(v63, L"hidden", v34);
              v7 = v25;
              if ( v25 < 0 )
                goto LABEL_117;
              if ( (_DWORD)v33 != 7 )
              {
                v25 = WdcXmlSetAttribute(v2, L"height", v35[1]);
                v7 = v25;
                if ( v25 < 0 )
                  goto LABEL_117;
                v36 = 0;
                v37 = 32LL * dword_180098828[v32];
                for ( m = v37; ; v37 = m )
                {
                  v74 = v36;
                  if ( (unsigned int)v36 >= *(unsigned __int16 *)((char *)&ListViewColumns + v37 + 8) )
                    break;
                  v38 = (unsigned int)v35[v36 + 19];
                  v39 = (*(_DWORD **)((char *)&ListViewColumns + v37))[14 * v38 + 4];
                  for ( n = 0; ; ++n )
                  {
                    if ( n >= 0x35 )
                    {
                      v7 = -2147467259;
LABEL_115:
                      LODWORD(ppv) = v7;
                      goto LABEL_118;
                    }
                    if ( v39 == dword_1800870F0[4 * n] )
                      break;
                  }
                  v67 = (&off_1800870F8)[2 * n];
                  v24 = WdcXmlCreateElement(v61, (struct IXMLDOMNode *)v2, L"column", L"id", v67, &v62);
                  v7 = v24;
                  if ( v24 < 0 )
                    goto LABEL_50;
                  v41 = v68;
                  memset(&pvarg, 0, sizeof(pvarg));
                  v42 = v68[v38 + 3];
                  VariantInit(&pvarg);
                  v43 = SysAllocString(L"width");
                  v4 = v62;
                  v44 = v43;
                  if ( v43 )
                  {
                    pvarg.lVal = v42;
                    pvarg.vt = 22;
                    v45 = v43;
                    lpVtbl = v62->lpVtbl;
                    pRecInfo = pvarg.pRecInfo;
                    setAttribute = lpVtbl->setAttribute;
                    v70 = *(_OWORD *)&pvarg.vt;
                    v48 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR, __int128 *))setAttribute)(
                            v62,
                            v45,
                            &v70);
                    v7 = v48;
                    if ( v48 < 0 )
                    {
                      LODWORD(ppv) = v48;
                      WdcDebugMessage(
                        "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                        "WdcXmlSetAttribute",
                        0,
                        L"FAILURE: 0x%08x",
                        ppv);
                    }
                    SysFreeString(v44);
                  }
                  else
                  {
                    LODWORD(ppv) = -2147024882;
                    WdcDebugMessage(
                      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
                      "WdcAssignString",
                      0,
                      L"FAILURE: 0x%08x",
                      ppv);
                    LODWORD(ppva) = -2147024882;
                    v7 = -2147024882;
                    WdcDebugMessage(
                      "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                      "WdcXmlSetAttribute",
                      0,
                      L"FAILURE: 0x%08x",
                      ppva);
                  }
                  VariantClear(&pvarg);
                  if ( v7 < 0 )
                    goto LABEL_115;
                  v49 = v41[2];
                  v50 = L"false";
                  if ( !_bittest(&v49, v38) )
                    v50 = L"true";
                  memset(&pvarg, 0, sizeof(pvarg));
                  VariantInit(&pvarg);
                  v51 = SysAllocString(L"hidden");
                  if ( !v51 )
                  {
                    LODWORD(ppv) = -2147024882;
                    WdcDebugMessage(
                      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
                      "WdcAssignString",
                      0,
                      L"FAILURE: 0x%08x",
                      ppv);
                    LODWORD(ppvb) = -2147024882;
                    v7 = -2147024882;
                    WdcDebugMessage(
                      "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                      "WdcXmlSetAttribute",
                      0,
                      L"FAILURE: 0x%08x",
                      ppvb);
                    goto LABEL_98;
                  }
                  v52 = SysAllocString(v50);
                  if ( !v52 )
                  {
                    LODWORD(ppv) = -2147024882;
                    WdcDebugMessage(
                      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
                      "WdcAssignString",
                      0,
                      L"FAILURE: 0x%08x",
                      ppv);
                    v7 = -2147024882;
                    LODWORD(ppv) = -2147024882;
                    goto LABEL_96;
                  }
                  pvarg.llVal = (LONGLONG)v52;
                  pRecInfo = pvarg.pRecInfo;
                  pvarg.vt = 8;
                  v53 = v4->lpVtbl->setAttribute;
                  v70 = *(_OWORD *)&pvarg.vt;
                  v54 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, __int128 *))v53)(v4, v51, &v70);
                  v7 = v54;
                  if ( v54 < 0 )
                  {
                    LODWORD(ppv) = v54;
LABEL_96:
                    WdcDebugMessage(
                      "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                      "WdcXmlSetAttribute",
                      0,
                      L"FAILURE: 0x%08x",
                      ppv);
                  }
                  SysFreeString(v51);
LABEL_98:
                  VariantClear(&pvarg);
                  if ( v7 < 0 )
                    goto LABEL_115;
                  if ( v4 )
                  {
                    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
                    v4 = 0;
                    v62 = 0;
                  }
                  v35 = v68;
                  v36 = (unsigned int)(v74 + 1);
                }
                v25 = WdcColumnIdToXmlId(
                        (*(_DWORD **)((char *)&ListViewColumns + v37))[14 * v35[35] + 4],
                        (const unsigned __int16 **)&v67);
                v7 = v25;
                if ( v25 < 0 )
                  goto LABEL_117;
                v24 = WdcXmlCreateElement(v61, (struct IXMLDOMNode *)v2, L"sort", L"column", v67, &v62);
                v7 = v24;
                if ( v24 < 0 )
                {
LABEL_50:
                  LODWORD(ppv) = v24;
                  WdcDebugMessage(
                    "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                    "WdcSaveSettingsToXml",
                    0,
                    L"FAILURE: 0x%08x",
                    ppv);
                  v4 = v62;
                  goto LABEL_119;
                }
                v4 = v62;
                v55 = L"true";
                if ( !v35[36] )
                  v55 = L"false";
                v25 = WdcXmlSetAttribute(v62, L"descending", v55);
                v7 = v25;
                if ( v25 < 0 )
                  goto LABEL_117;
                if ( v4 )
                {
                  ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
                  v4 = 0;
                  v62 = 0;
                }
              }
              if ( v2 )
              {
                ((void (__fastcall *)(struct IXMLDOMElement *))v2->lpVtbl->Release)(v2);
                v2 = 0;
                v63 = 0;
              }
              if ( v11 )
              {
                ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
                v11 = 0;
                v60 = 0;
              }
            }
            v25 = WdcXmlSave(v61, a2);
            v7 = v25;
            if ( v25 < 0 )
            {
LABEL_117:
              LODWORD(ppv) = v25;
LABEL_118:
              WdcDebugMessage(
                "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
                "WdcSaveSettingsToXml",
                0,
                L"FAILURE: 0x%08x",
                ppv);
            }
LABEL_119:
            if ( v4 )
              ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
LABEL_121:
            if ( v2 )
              ((void (__fastcall *)(struct IXMLDOMElement *))v2->lpVtbl->Release)(v2);
            goto LABEL_123;
          }
          goto LABEL_11;
        }
      }
    }
    LODWORD(ppv) = v13;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
      "WdcSaveSettingsToXml",
      0,
      L"FAILURE: 0x%08x",
      ppv);
LABEL_123:
    if ( v11 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
    goto LABEL_125;
  }
  LODWORD(ppv) = Element;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
    "WdcSaveSettingsToXml",
    0,
    L"FAILURE: 0x%08x",
    ppv);
LABEL_125:
  if ( v64 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v64->lpVtbl->Release)(v64);
LABEL_127:
  if ( v66 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    v66 = 0;
  }
  if ( v61 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v61->lpVtbl->Release)(v61);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b0cc  mov     [rsp-8+arg_8], rdx
0x18001b0d1  mov     [rsp-8+arg_0], rcx
0x18001b0d6  push    rbp
0x18001b0d7  push    rbx
0x18001b0d8  push    rsi
0x18001b0d9  push    rdi
0x18001b0da  push    r12
0x18001b0dc  push    r13
0x18001b0de  push    r14
0x18001b0e0  push    r15
0x18001b0e2  lea     rbp, [rsp-1Fh]
0x18001b0e7  sub     rsp, 0B8h
0x18001b0ee  xor     esi, esi
0x18001b0f0  mov     [rbp+57h+var_B8], 0
0x18001b0f8  mov     r13, rcx
0x18001b0fb  mov     [rbp+57h+var_80], 0
0x18001b103  lea     rax, [rbp+57h+var_B8]
0x18001b107  mov     [rbp+57h+var_A0], 0
0x18001b10f  xor     r14d, r14d
0x18001b112  mov     [rbp+57h+var_C0], 0
0x18001b11a  lea     r12d, [rsi+1]
0x18001b11e  mov     [rbp+57h+var_A8], rsi
0x18001b122  mov     r8d, r12d; dwClsContext
0x18001b125  mov     [rbp+57h+var_B0], r14
0x18001b129  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18001b130  mov     [rbp+57h+var_78], rsi
0x18001b134  xor     edx, edx; pUnkOuter
0x18001b136  mov     [rsp+0F0h+ppv], rax; ppv
0x18001b13b  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18001b142  call    cs:__imp_CoCreateInstance
0x18001b148  mov     ebx, eax
0x18001b14a  test    eax, eax
0x18001b14c  jns     short loc_18001B174
0x18001b14e  xor     r8d, r8d; int
0x18001b151  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b158  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b15c  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b163  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b16a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b16f  jmp     loc_18001BCAB
0x18001b174  mov     rcx, [rbp+57h+var_B8]
0x18001b178  xor     edx, edx
0x18001b17a  mov     rax, [rcx]
0x18001b17d  mov     rax, [rax+1F8h]
0x18001b184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b189  mov     ebx, eax
0x18001b18b  test    eax, eax
0x18001b18d  js      short loc_18001B14E
0x18001b18f  mov     rcx, [rbp+57h+var_B8]
0x18001b193  xor     edx, edx
0x18001b195  mov     rax, [rcx]
0x18001b198  mov     rax, [rax+220h]
0x18001b19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1a4  mov     ebx, eax
0x18001b1a6  test    eax, eax
0x18001b1a8  js      short loc_18001B14E
0x18001b1aa  mov     rcx, [rbp+57h+var_B8]
0x18001b1ae  xor     edx, edx
0x18001b1b0  mov     rax, [rcx]
0x18001b1b3  mov     rax, [rax+230h]
0x18001b1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1bf  mov     ebx, eax
0x18001b1c1  test    eax, eax
0x18001b1c3  js      short loc_18001B14E
0x18001b1c5  mov     rcx, [rbp+57h+var_B8]
0x18001b1c9  lea     r9, [rbp+57h+var_80]
0x18001b1cd  lea     r8, aVersion10Encod; " version='1.0' encoding='UTF-8'"
0x18001b1d4  lea     rdx, aXml; "xml"
0x18001b1db  mov     rax, [rcx]
0x18001b1de  mov     rax, [rax+1A0h]
0x18001b1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ea  xor     r8d, r8d
0x18001b1ed  mov     ebx, eax
0x18001b1ef  test    eax, eax
0x18001b1f1  js      loc_18001B151
0x18001b1f7  mov     rcx, [rbp+57h+var_B8]
0x18001b1fb  mov     rdx, [rbp+57h+var_80]
0x18001b1ff  mov     rax, [rcx]
0x18001b202  mov     rax, [rax+0A8h]
0x18001b209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b20e  mov     ebx, eax
0x18001b210  test    eax, eax
0x18001b212  js      loc_18001B14E
0x18001b218  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b21c  lea     r9, [rbp+57h+var_A0]; struct IXMLDOMElement **
0x18001b220  mov     rdx, rcx; struct IXMLDOMNode *
0x18001b223  lea     r8, aConfiguration; "configuration"
0x18001b22a  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001b22f  mov     ebx, eax
0x18001b231  test    eax, eax
0x18001b233  jns     short loc_18001B25B
0x18001b235  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b23c  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b240  xor     r8d, r8d; int
0x18001b243  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b24a  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b251  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b256  jmp     loc_18001BC96
0x18001b25b  mov     r15, [rbp+57h+var_A0]
0x18001b25f  lea     r9, [rbp+57h+var_C0]; struct IXMLDOMElement **
0x18001b263  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b267  lea     r8, aTabpane; "tabpane"
0x18001b26e  mov     rdx, r15; struct IXMLDOMNode *
0x18001b271  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001b276  mov     ebx, eax
0x18001b278  test    eax, eax
0x18001b27a  jns     short loc_18001B2A6
0x18001b27c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b283  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b287  xor     r8d, r8d; int
0x18001b28a  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b291  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b298  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b29d  mov     rdi, [rbp+57h+var_C0]
0x18001b2a1  jmp     loc_18001BC82
0x18001b2a6  cmp     [r13+0BFCh], esi
0x18001b2ad  lea     rax, aFalse; "false"
0x18001b2b4  mov     rdi, [rbp+57h+var_C0]
0x18001b2b8  lea     r8, String1; "true"
0x18001b2bf  cmovz   r8, rax; unsigned __int16 *
0x18001b2c3  lea     rdx, aAutocolumns; "autocolumns"
0x18001b2ca  mov     rcx, rdi; struct IXMLDOMElement *
0x18001b2cd  call    ?WdcXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; WdcXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001b2d2  mov     ebx, eax
0x18001b2d4  test    eax, eax
0x18001b2d6  jns     short loc_18001B2FE
0x18001b2d8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b2df  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b2e3  xor     r8d, r8d; int
0x18001b2e6  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b2ed  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b2f4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b2f9  jmp     loc_18001BC82
0x18001b2fe  test    rdi, rdi
0x18001b301  jz      short loc_18001B316
0x18001b303  mov     rax, [rdi]
0x18001b306  mov     rcx, rdi
0x18001b309  mov     rax, [rax+10h]
0x18001b30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b312  mov     [rbp+57h+var_C0], rsi
0x18001b316  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b31a  lea     r9, [rbp+57h+var_C0]; struct IXMLDOMElement **
0x18001b31e  lea     r8, aChartpane; "chartpane"
0x18001b325  mov     rdx, r15; struct IXMLDOMNode *
0x18001b328  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001b32d  mov     ebx, eax
0x18001b32f  test    eax, eax
0x18001b331  js      loc_18001B27C
0x18001b337  mov     rdi, [rbp+57h+var_C0]
0x18001b33b  lea     rdx, aWidth; "width"
0x18001b342  mov     r8d, [r13+0]; int
0x18001b346  mov     rcx, rdi; struct IXMLDOMElement *
0x18001b349  call    ?WdcXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBGH@Z; WdcXmlSetAttribute(IXMLDOMElement *,ushort const *,int)
0x18001b34e  mov     ebx, eax
0x18001b350  test    eax, eax
0x18001b352  js      short loc_18001B2D8
0x18001b354  cmp     [r13+4], esi
0x18001b358  lea     rax, aFalse; "false"
0x18001b35f  lea     r8, String1; "true"
0x18001b366  mov     rcx, rdi; struct IXMLDOMElement *
0x18001b369  cmovz   r8, rax; unsigned __int16 *
0x18001b36d  lea     rdx, aHidden; "hidden"
0x18001b374  call    ?WdcXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; WdcXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001b379  mov     ebx, eax
0x18001b37b  test    eax, eax
0x18001b37d  js      loc_18001B2D8
0x18001b383  test    rdi, rdi
0x18001b386  jz      short loc_18001B39B
0x18001b388  mov     rax, [rdi]
0x18001b38b  mov     rcx, rdi
0x18001b38e  mov     rax, [rax+10h]
0x18001b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b397  mov     [rbp+57h+var_C0], rsi
0x18001b39b  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b39f  lea     r9, [rbp+57h+var_C0]; struct IXMLDOMElement **
0x18001b3a3  lea     r8, aCpuchart; "cpuchart"
0x18001b3aa  mov     rdx, r15; struct IXMLDOMNode *
0x18001b3ad  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001b3b2  mov     ebx, eax
0x18001b3b4  test    eax, eax
0x18001b3b6  js      loc_18001B27C
0x18001b3bc  mov     rdi, [rbp+57h+var_C0]
0x18001b3c0  xor     r15d, r15d
0x18001b3c3  cmp     r15d, 40h ; '@'
0x18001b3c7  jge     loc_18001B48C
0x18001b3cd  test    [r13+8], r12
0x18001b3d1  jnz     short loc_18001B434
0x18001b3d3  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b3d7  lea     rax, [rbp+57h+var_A8]
0x18001b3db  mov     [rsp+0F0h+var_C8], rax; struct IXMLDOMElement **
0x18001b3e0  lea     r8, aNode; "node"
0x18001b3e7  mov     rdx, rdi; struct IXMLDOMNode *
0x18001b3ea  mov     dword ptr [rsp+0F0h+ppv], r15d; int
0x18001b3ef  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBG2HPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18001b3f4  mov     ebx, eax
0x18001b3f6  test    eax, eax
0x18001b3f8  js      short loc_18001B462
0x18001b3fa  mov     rsi, [rbp+57h+var_A8]
0x18001b3fe  lea     r8, String1; "true"
0x18001b405  mov     rcx, rsi; struct IXMLDOMElement *
0x18001b408  lea     rdx, aHidden; "hidden"
0x18001b40f  call    ?WdcXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; WdcXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001b414  mov     ebx, eax
0x18001b416  test    eax, eax
0x18001b418  js      short loc_18001B43C
0x18001b41a  test    rsi, rsi
0x18001b41d  jz      short loc_18001B434
0x18001b41f  mov     rax, [rsi]
0x18001b422  mov     rcx, rsi
0x18001b425  mov     rax, [rax+10h]
0x18001b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b42e  xor     esi, esi
0x18001b430  mov     [rbp+57h+var_A8], rsi
0x18001b434  inc     r15d
0x18001b437  add     r12, r12
0x18001b43a  jmp     short loc_18001B3C3
0x18001b43c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b443  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b447  xor     r8d, r8d; int
0x18001b44a  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b451  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b458  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b45d  jmp     loc_18001BC6E
0x18001b462  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b469  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b46d  xor     r8d, r8d; int
0x18001b470  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b477  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b47e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b483  mov     rsi, [rbp+57h+var_A8]
0x18001b487  jmp     loc_18001BC6E
0x18001b48c  xor     r15d, r15d
0x18001b48f  cmp     r15d, 40h ; '@'
0x18001b493  jnb     loc_18001B5D3
0x18001b499  xor     r12d, r12d
0x18001b49c  lea     r13d, [r12+1]
0x18001b4a1  cmp     r12d, 40h ; '@'
0x18001b4a5  jnb     loc_18001B577
0x18001b4ab  mov     rcx, [rbp+57h+arg_0]
0x18001b4af  movsxd  rax, r15d
0x18001b4b2  test    [rcx+rax*8+10h], r13
0x18001b4b7  jnz     loc_18001B56C
0x18001b4bd  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b4c1  lea     rax, [rbp+57h+var_A8]
0x18001b4c5  mov     [rsp+0F0h+var_C8], rax; struct IXMLDOMElement **
0x18001b4ca  lea     r8, aNode; "node"
0x18001b4d1  mov     rdx, rdi; struct IXMLDOMNode *
0x18001b4d4  mov     dword ptr [rsp+0F0h+ppv], r15d; int
0x18001b4d9  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBG2HPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18001b4de  mov     ebx, eax
0x18001b4e0  test    eax, eax
0x18001b4e2  js      loc_18001B5A9
0x18001b4e8  mov     rsi, [rbp+57h+var_A8]
0x18001b4ec  lea     rax, [rbp+57h+var_B0]
0x18001b4f0  mov     rcx, [rbp+57h+var_B8]; struct IXMLDOMDocument *
0x18001b4f4  lea     r8, aCpu_0; "cpu"
0x18001b4fb  mov     [rsp+0F0h+var_C8], rax; struct IXMLDOMElement **
0x18001b500  mov     rdx, rsi; struct IXMLDOMNode *
0x18001b503  mov     dword ptr [rsp+0F0h+ppv], r12d; int
0x18001b508  call    ?WdcXmlCreateElement@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEBG2HPEAPEAUIXMLDOMElement@@@Z; WdcXmlCreateElement(IXMLDOMDocument *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMElement * *)
0x18001b50d  mov     ebx, eax
0x18001b50f  test    eax, eax
0x18001b511  js      short loc_18001B57F
0x18001b513  mov     r14, [rbp+57h+var_B0]
0x18001b517  lea     r8, String1; "true"
0x18001b51e  mov     rcx, r14; struct IXMLDOMElement *
0x18001b521  lea     rdx, aHidden; "hidden"
0x18001b528  call    ?WdcXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; WdcXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001b52d  mov     ebx, eax
0x18001b52f  test    eax, eax
0x18001b531  js      loc_18001BC39
0x18001b537  test    r14, r14
0x18001b53a  jz      short loc_18001B552
0x18001b53c  mov     rax, [r14]
0x18001b53f  mov     rcx, r14
0x18001b542  mov     rax, [rax+10h]
0x18001b546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b54b  xor     r14d, r14d
0x18001b54e  mov     [rbp+57h+var_B0], r14
0x18001b552  test    rsi, rsi
0x18001b555  jz      short loc_18001B56C
0x18001b557  mov     rax, [rsi]
0x18001b55a  mov     rcx, rsi
0x18001b55d  mov     rax, [rax+10h]
0x18001b561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b566  xor     esi, esi
0x18001b568  mov     [rbp+57h+var_A8], rsi
0x18001b56c  inc     r12d
0x18001b56f  add     r13, r13
0x18001b572  jmp     loc_18001B4A1
0x18001b577  inc     r15d
0x18001b57a  jmp     loc_18001B48F
0x18001b57f  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001b586  mov     dword ptr [rsp+0F0h+ppv], eax
0x18001b58a  xor     r8d, r8d; int
0x18001b58d  lea     rdx, aWdcsavesetting; "WdcSaveSettingsToXml"
0x18001b594  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001b59b  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001b5a0  mov     r14, [rbp+57h+var_B0]
0x18001b5a4  jmp     loc_18001BC5A
  ... truncated ...
```
