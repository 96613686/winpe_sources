# HrAppendActionResponseElementToBody(IUPnPAutomationProxy *,IXMLDOMDocument *,IXMLDOMNode *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUPnPServiceDescriptionInfo *)

- ea: `0x180003dac`
- end: `0x180004496`
- name: `?HrAppendActionResponseElementToBody@@YAJPEAUIUPnPAutomationProxy@@PEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUPnPServiceDescriptionInfo@@@Z`
- size: `1770`
- prototype: `__int64 __fastcall(struct IUPnPAutomationProxy *, struct IXMLDOMDocument *, struct IXMLDOMNode *, struct tagUPNP_CONTROL_REQUEST *, BSTR *, struct IUPnPServiceDescriptionInfo *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800063e0`

## callees

- `0x18000249c`
- `0x180003728`
- `0x1800038ec`
- `0x180003dac`
- `0x180006c44`
- `0x18000a070`
- `0x18000a4a4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800043f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800043f9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003e5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003e5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f63`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003e75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180003e75`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f87`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f87`
- `OLEAUT32!__imp_SysFreeString` at `0x180004048`
- `OLEAUT32!__imp_SysFreeString` at `0x180004074`
- `OLEAUT32!__imp_SysFreeString` at `0x180004288`
- `OLEAUT32!__imp_SysFreeString` at `0x18000429e`
- `OLEAUT32!__imp_SysFreeString` at `0x180004048`
- `OLEAUT32!__imp_SysFreeString` at `0x180004074`
- `OLEAUT32!__imp_SysFreeString` at `0x180004288`
- `OLEAUT32!__imp_SysFreeString` at `0x18000429e`
- `OLEAUT32!__imp_SysStringLen` at `0x180003e38`
- `OLEAUT32!__imp_SysStringLen` at `0x180003e38`

## string_xrefs

- `0x18000421b`: `HrAppendActionResponseElementToBody(): Failed to get create argument element`
- `0x1800043b0`: `HrAppendActionResponseElementToBody(): Failed to create action response element`
- `0x1800043d7`: `HrAppendActionResponseElementToBody(): Failed to get service type`

## pseudocode

```c
__int64 __fastcall HrAppendActionResponseElementToBody(
        struct IUPnPAutomationProxy *a1,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode *a3,
        struct tagUPNP_CONTROL_REQUEST *a4,
        BSTR *a5,
        struct IUPnPServiceDescriptionInfo *a6)
{
  const wchar_t *v6; // rax
  __int64 v7; // r10
  __int64 v11; // rdi
  const wchar_t *v12; // rax
  BSTR *v13; // r12
  __int64 v14; // rax
  unsigned int v15; // edi
  unsigned __int16 *v16; // rsi
  int v17; // ebx
  int Element; // edi
  int v19; // eax
  unsigned int v20; // r14d
  const unsigned __int16 *v21; // r8
  BSTR *v22; // r13
  void *v23; // rax
  BSTR v24; // rax
  struct IUPnPServiceDescriptionInfo *v25; // rcx
  int v26; // eax
  unsigned int v27; // ebx
  BSTR v28; // rax
  const unsigned __int16 *v29; // r8
  const unsigned __int16 *v30; // rdx
  IRecordInfo *v31; // xmm1_8
  int v32; // eax
  struct IXMLDOMElement *v33; // r14
  int v34; // eax
  __int64 v35; // rbx
  unsigned __int16 *v36; // rbx
  _QWORD *v37; // rcx
  int v38; // edx
  const char *v39; // r9
  _QWORD *v40; // rcx
  int v41; // edx
  const char *v42; // r9
  unsigned int v43; // ebx
  _QWORD *v44; // rcx
  LPCWSTR v46; // [rsp+20h] [rbp-60h]
  LPVOID v47; // [rsp+38h] [rbp-48h] BYREF
  LPVOID v48; // [rsp+40h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-38h] BYREF
  struct IXMLDOMElement *v50; // [rsp+50h] [rbp-30h] BYREF
  struct tagVARIANT v51; // [rsp+60h] [rbp-20h] BYREF

  v6 = L"Response";
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  v11 = 0x7FFFFFFF;
  v12 = L"m:";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = a5;
  v14 = (v7 != 0 ? 0x7FFFFFFF - (_DWORD)v7 : 0) + (v11 != 0 ? 0x7FFFFFFF - (_DWORD)v11 : 0) + SysStringLen(*a5) + 1;
  v15 = v14;
  v16 = (unsigned __int16 *)malloc(2 * v14);
  v17 = lstrcmpW(*v13, L"QueryStateVariable");
  if ( v16 )
  {
    v46 = *v13;
    a5 = 0;
    pv = 0;
    Element = StringCchPrintfW(v16, v15, L"%s%s%s", L"m:", v46, L"Response");
    if ( Element < 0
      || (v19 = (*(__int64 (__fastcall **)(struct IUPnPAutomationProxy *, LPVOID *))(*(_QWORD *)a1 + 56LL))(a1, &pv),
          v20 = 0,
          Element = v19,
          v19 < 0) )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_86;
      v41 = 51;
      v42 = "HrAppendActionResponseElementToBody(): Failed to get service type";
    }
    else
    {
      v21 = L"urn:schemas-upnp-org:control-1-0";
      if ( v17 )
        v21 = (const unsigned __int16 *)pv;
      Element = HrCreateElement(a2, v16, v21, (struct IXMLDOMNode **)&a5);
      CoTaskMemFree(pv);
      if ( Element >= 0 )
      {
        v22 = a5;
        if ( !*((_DWORD *)v13 + 4) )
        {
LABEL_66:
          v26 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *, _QWORD))a3->lpVtbl->appendChild)(a3, v22, 0);
          Element = v26;
          if ( v26 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              v36 = v16;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, v16);
              goto LABEL_78;
            }
LABEL_77:
            v36 = v16;
LABEL_78:
            (*((void (__fastcall **)(BSTR *))*v22 + 2))(v22);
            goto LABEL_87;
          }
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_77;
          v38 = 49;
          v39 = "HrAppendActionResponseElementToBody(): Failed to append action response element";
LABEL_76:
          WPP_SF_sd(v37[2], v38, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v39, v26);
          goto LABEL_77;
        }
        LODWORD(a5) = 0;
        v47 = 0;
        v48 = 0;
        if ( v17 )
        {
          v26 = (*(__int64 (__fastcall **)(struct IUPnPServiceDescriptionInfo *, BSTR, BSTR **, LPVOID *, LPVOID *))(*(_QWORD *)a6 + 40LL))(
                  a6,
                  *v13,
                  &a5,
                  &v47,
                  &v48);
          Element = v26;
          if ( v26 < 0 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_77;
            v38 = 43;
            v39 = "HrAppendActionResponseElementToBody(): Failed to obtain out arg name and data for action";
            goto LABEL_76;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, *v13);
          }
          goto LABEL_42;
        }
        LODWORD(a5) = 1;
        v47 = CoTaskMemAlloc(8u);
        v23 = CoTaskMemAlloc(8u);
        v48 = v23;
        if ( v47 && v23 )
        {
          v24 = SysAllocString(L"return");
          *(_QWORD *)v47 = v24;
          if ( v24 )
          {
            v25 = a6;
            *(_QWORD *)v48 = 0;
            Element = (*(__int64 (__fastcall **)(struct IUPnPServiceDescriptionInfo *, _QWORD, LPVOID))(*(_QWORD *)v25 + 24LL))(
                        v25,
                        *(_QWORD *)(*((_QWORD *)a4 + 2) + 8LL),
                        v48);
          }
          else
          {
            Element = -2147024882;
          }
          if ( Element >= 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
            }
            goto LABEL_36;
          }
        }
        else
        {
          Element = -2147024882;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
            (unsigned int)"HrAppendActionResponseElementToBody(): Failed to obtain out arg name and data type for QueryStateVariable",
            Element);
        if ( v47 )
        {
          if ( *(_QWORD *)v47 )
          {
            SysFreeString(*(BSTR *)v47);
            *(_QWORD *)v47 = 0;
          }
          CoTaskMemFree(v47);
          v47 = 0;
        }
        if ( v48 )
        {
          if ( *(_QWORD *)v48 )
          {
            SysFreeString(*(BSTR *)v48);
            *(_QWORD *)v48 = 0;
          }
          CoTaskMemFree(v48);
          v48 = 0;
        }
LABEL_36:
        if ( Element < 0 )
          goto LABEL_77;
LABEL_42:
        v27 = 0;
        while ( v27 < (unsigned int)a5 )
        {
          v28 = v13[3];
          v50 = 0;
          v29 = (const unsigned __int16 *)*((_QWORD *)v48 + v27);
          v30 = (const unsigned __int16 *)*((_QWORD *)v47 + v27);
          v31 = *(IRecordInfo **)&v28[12 * v27 + 8];
          *(_OWORD *)&v51.vt = *(_OWORD *)&v28[12 * v27];
          v51.pRecInfo = v31;
          v32 = HrCreateElementWithType(a2, v30, v29, &v51, &v50);
          Element = v32;
          if ( v32 < 0 )
          {
            if ( v32 == -2147467259 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  46,
                  (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                  (unsigned int)"HrAppendActionResponseElementToBody(): Probably failed to coerce argument element",
                  5);
              }
              Element = -2147220972;
              break;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                (unsigned int)"HrAppendActionResponseElementToBody(): Failed to get create argument element",
                v32);
              break;
            }
          }
          else
          {
            v33 = v50;
            v34 = (*((__int64 (__fastcall **)(BSTR *, struct IXMLDOMElement *, _QWORD))*v22 + 21))(v22, v50, 0);
            Element = v34;
            if ( v34 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  45,
                  (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                  (unsigned int)"HrAppendActionResponseElementToBody(): Failed to append argument element",
                  v34);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                44,
                WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                *((_QWORD *)v47 + v27));
            }
            ((void (__fastcall *)(struct IXMLDOMElement *))v33->lpVtbl->Release)(v33);
            v20 = 0;
          }
          ++v27;
          if ( Element < 0 )
            break;
        }
        if ( (_DWORD)a5 )
        {
          do
          {
            v35 = v20;
            SysFreeString(*((BSTR *)v47 + v20));
            *((_QWORD *)v47 + v20) = 0;
            SysFreeString(*((BSTR *)v48 + v20++));
            *((_QWORD *)v48 + v35) = 0;
          }
          while ( v20 < (unsigned int)a5 );
        }
        CoTaskMemFree(v47);
        v47 = 0;
        CoTaskMemFree(v48);
        if ( Element < 0 )
          goto LABEL_77;
        goto LABEL_66;
      }
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_86:
        v36 = v16;
LABEL_87:
        free(v36);
        v43 = Element;
        if ( !Element )
          return v43;
        goto LABEL_92;
      }
      v41 = 50;
      v42 = "HrAppendActionResponseElementToBody(): Failed to create action response element";
    }
    WPP_SF_sd(v40[2], v41, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v42, Element);
    goto LABEL_86;
  }
  v43 = -2147024882;
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v43;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_93;
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    52,
    (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
    (unsigned int)"HrAppendActionResponseElementToBody(): Failed to allocate memory for action response element name",
    14);
LABEL_92:
  v44 = WPP_GLOBAL_Control;
LABEL_93:
  if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 1) != 0 )
    WPP_SF_sd(
      v44[2],
      53,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrAppendActionResponseElementToBody(): Exiting",
      v43);
  return v43;
}

```

## disassembly

```asm
0x180003dac  mov     [rsp-38h+arg_0], rbx
0x180003db1  mov     [rsp-38h+arg_10], r8
0x180003db6  mov     [rsp-38h+arg_8], rdx
0x180003dbb  push    rbp
0x180003dbc  push    rsi
0x180003dbd  push    rdi
0x180003dbe  push    r12
0x180003dc0  push    r13
0x180003dc2  push    r14
0x180003dc4  push    r15
0x180003dc6  mov     rbp, rsp
0x180003dc9  sub     rsp, 80h
0x180003dd0  mov     ebx, 7FFFFFFFh
0x180003dd5  lea     rax, aResponse; "Response"
0x180003ddc  mov     r10d, ebx
0x180003ddf  mov     r15, r9
0x180003de2  mov     r13, rdx
0x180003de5  mov     r14, rcx
0x180003de8  xor     r8d, r8d
0x180003deb  cmp     [rax], r8w
0x180003def  jz      short loc_180003DFB
0x180003df1  add     rax, 2
0x180003df5  sub     r10, 1
0x180003df9  jnz     short loc_180003DEB
0x180003dfb  mov     rax, r10
0x180003dfe  mov     rcx, rbx
0x180003e01  sub     rcx, r10
0x180003e04  mov     rdi, rbx
0x180003e07  neg     rax
0x180003e0a  lea     rax, aM; "m:"
0x180003e11  sbb     rdx, rdx
0x180003e14  and     rdx, rcx
0x180003e17  neg     r10
0x180003e1a  sbb     rsi, rsi
0x180003e1d  and     rsi, rdx
0x180003e20  cmp     [rax], r8w
0x180003e24  jz      short loc_180003E30
0x180003e26  add     rax, 2
0x180003e2a  sub     rdi, 1
0x180003e2e  jnz     short loc_180003E20
0x180003e30  mov     r12, [rbp+arg_20]
0x180003e34  mov     rcx, [r12]; pbstr
0x180003e38  call    cs:__imp_SysStringLen
0x180003e3e  sub     ebx, edi
0x180003e40  mov     rcx, rdi
0x180003e43  neg     rcx
0x180003e46  sbb     edx, edx
0x180003e48  and     edx, ebx
0x180003e4a  neg     rdi
0x180003e4d  sbb     ecx, ecx
0x180003e4f  inc     eax
0x180003e51  and     ecx, edx
0x180003e53  add     eax, ecx
0x180003e55  add     eax, esi
0x180003e57  mov     edi, eax
0x180003e59  lea     rcx, [rax+rax]; Size
0x180003e5d  call    cs:__imp_malloc
0x180003e63  mov     rcx, [r12]; lpString1
0x180003e67  lea     rdx, aQuerystatevari; "QueryStateVariable"
0x180003e6e  mov     rsi, rax
0x180003e71  mov     [rbp+Block], rax
0x180003e75  call    cs:__imp_lstrcmpW
0x180003e7b  mov     ebx, eax
0x180003e7d  test    rsi, rsi
0x180003e80  jz      loc_180004407
0x180003e86  mov     rcx, [r12]
0x180003e8a  lea     rax, aResponse; "Response"
0x180003e91  mov     [rsp+80h+var_58], rax
0x180003e96  lea     r9, aM; "m:"
0x180003e9d  mov     [rsp+80h+var_60], rcx
0x180003ea2  lea     r8, aSSS; "%s%s%s"
0x180003ea9  mov     rcx, rsi; unsigned __int16 *
0x180003eac  mov     [rbp+arg_20], 0
0x180003eb4  mov     edx, edi; unsigned __int64
0x180003eb6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ebb  mov     [rbp+pv], 0
0x180003ec3  mov     edi, eax
0x180003ec5  test    eax, eax
0x180003ec7  js      loc_1800043B9
0x180003ecd  mov     rax, [r14]
0x180003ed0  lea     rdx, [rbp+pv]
0x180003ed4  mov     rcx, r14
0x180003ed7  mov     rax, [rax+38h]
0x180003edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee0  xor     r14d, r14d
0x180003ee3  mov     edi, eax
0x180003ee5  test    eax, eax
0x180003ee7  js      loc_1800043B9
0x180003eed  lea     r9, [rbp+arg_20]; struct IXMLDOMNode **
0x180003ef1  mov     rdx, rsi; unsigned __int16 *
0x180003ef4  lea     r8, aUrnSchemasUpnp; "urn:schemas-upnp-org:control-1-0"
0x180003efb  mov     rcx, r13; struct IXMLDOMDocument *
0x180003efe  test    ebx, ebx
0x180003f00  jz      short loc_180003F06
0x180003f02  mov     r8, [rbp+pv]; unsigned __int16 *
0x180003f06  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180003f0b  mov     rcx, [rbp+pv]; pv
0x180003f0f  mov     edi, eax
0x180003f11  call    cs:__imp_CoTaskMemFree
0x180003f17  test    edi, edi
0x180003f19  js      loc_180004392
0x180003f1f  lea     rsi, WPP_GLOBAL_Control
0x180003f26  mov     r13, [rbp+arg_20]
0x180003f2a  cmp     [r12+10h], r14d
0x180003f2f  jz      loc_1800042D8
0x180003f35  mov     dword ptr [rbp+arg_20], r14d
0x180003f39  mov     [rbp+var_48], r14
0x180003f3d  mov     [rbp+var_40], r14
0x180003f41  test    ebx, ebx
0x180003f43  jnz     loc_180004099
0x180003f49  mov     ebx, 8
0x180003f4e  mov     dword ptr [rbp+arg_20], 1
0x180003f55  mov     ecx, ebx; cb
0x180003f57  call    cs:__imp_CoTaskMemAlloc
0x180003f5d  mov     ecx, ebx; cb
0x180003f5f  mov     [rbp+var_48], rax
0x180003f63  call    cs:__imp_CoTaskMemAlloc
0x180003f69  mov     [rbp+var_40], rax
0x180003f6d  cmp     [rbp+var_48], r14
0x180003f71  jz      loc_180004000
0x180003f77  test    rax, rax
0x180003f7a  jz      loc_180004000
0x180003f80  lea     rcx, psz; "return"
0x180003f87  call    cs:__imp_SysAllocString
0x180003f8d  mov     rcx, [rbp+var_48]
0x180003f91  mov     [rcx], rax
0x180003f94  test    rax, rax
0x180003f97  jz      short loc_180003FC0
0x180003f99  mov     rax, [rbp+var_40]
0x180003f9d  mov     rcx, [rbp+arg_28]
0x180003fa1  mov     [rax], r14
0x180003fa4  mov     rax, [rcx]
0x180003fa7  mov     rdx, [r15+10h]
0x180003fab  mov     r8, [rbp+var_40]
0x180003faf  mov     rax, [rax+18h]
0x180003fb3  mov     rdx, [rdx+8]
0x180003fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fbc  mov     edi, eax
0x180003fbe  jmp     short loc_180003FC5
0x180003fc0  mov     edi, 8007000Eh
0x180003fc5  test    edi, edi
0x180003fc7  js      short loc_180004005
0x180003fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd0  cmp     rcx, rsi
0x180003fd3  jz      loc_18000408F
0x180003fd9  test    dword ptr [rcx+1Ch], 400h
0x180003fe0  jz      loc_18000408F
0x180003fe6  mov     rcx, [rcx+10h]
0x180003fea  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180003ff1  mov     edx, 28h ; '('
0x180003ff6  call    WPP_SF_
0x180003ffb  jmp     loc_18000408F
0x180004000  mov     edi, 8007000Eh
0x180004005  mov     rcx, cs:WPP_GLOBAL_Control
0x18000400c  cmp     rcx, rsi
0x18000400f  jz      short loc_180004037
0x180004011  test    byte ptr [rcx+1Ch], 1
0x180004015  jz      short loc_180004037
0x180004017  mov     rcx, [rcx+10h]
0x18000401b  lea     r9, aHrappendaction_4; "HrAppendActionResponseElementToBody(): "...
0x180004022  mov     edx, 29h ; ')'
0x180004027  mov     dword ptr [rsp+80h+var_60], edi
0x18000402b  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004032  call    WPP_SF_sd
0x180004037  mov     rax, [rbp+var_48]
0x18000403b  test    rax, rax
0x18000403e  jz      short loc_180004063
0x180004040  mov     rcx, [rax]; bstrString
0x180004043  test    rcx, rcx
0x180004046  jz      short loc_180004055
0x180004048  call    cs:__imp_SysFreeString
0x18000404e  mov     rax, [rbp+var_48]
0x180004052  mov     [rax], r14
0x180004055  mov     rcx, [rbp+var_48]; pv
0x180004059  call    cs:__imp_CoTaskMemFree
0x18000405f  mov     [rbp+var_48], r14
0x180004063  mov     rax, [rbp+var_40]
0x180004067  test    rax, rax
0x18000406a  jz      short loc_18000408F
0x18000406c  mov     rcx, [rax]; bstrString
0x18000406f  test    rcx, rcx
0x180004072  jz      short loc_180004081
0x180004074  call    cs:__imp_SysFreeString
0x18000407a  mov     rax, [rbp+var_40]
0x18000407e  mov     [rax], r14
0x180004081  mov     rcx, [rbp+var_40]; pv
0x180004085  call    cs:__imp_CoTaskMemFree
0x18000408b  mov     [rbp+var_40], r14
0x18000408f  test    edi, edi
0x180004091  js      loc_18000437C
0x180004097  jmp     short loc_1800040F6
0x180004099  mov     rcx, [rbp+arg_28]
0x18000409d  lea     rdx, [rbp+var_40]
0x1800040a1  mov     [rsp+80h+var_60], rdx
0x1800040a6  lea     r9, [rbp+var_48]
0x1800040aa  mov     rdx, [r12]
0x1800040ae  lea     r8, [rbp+arg_20]
0x1800040b2  mov     rax, [rcx]
0x1800040b5  mov     rax, [rax+28h]
0x1800040b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040be  mov     edi, eax
0x1800040c0  test    eax, eax
0x1800040c2  js      loc_18000432A
0x1800040c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040cf  cmp     rcx, rsi
0x1800040d2  jz      short loc_1800040F6
0x1800040d4  test    dword ptr [rcx+1Ch], 400h
0x1800040db  jz      short loc_1800040F6
0x1800040dd  mov     r9, [r12]
0x1800040e1  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800040e8  mov     rcx, [rcx+10h]
0x1800040ec  mov     edx, 2Ah ; '*'
0x1800040f1  call    WPP_SF_S
0x1800040f6  mov     ebx, r14d
0x1800040f9  cmp     ebx, dword ptr [rbp+arg_20]
0x1800040fc  jnb     loc_180004274
0x180004102  mov     rax, [r12+18h]
0x180004107  lea     r9, [rbp+var_20]; struct tagVARIANT
0x18000410b  mov     r8, [rbp+var_40]
0x18000410f  mov     rdx, [rbp+var_48]
0x180004113  mov     r15d, ebx
0x180004116  mov     [rbp+var_30], r14
0x18000411a  mov     r8, [r8+r15*8]; unsigned __int16 *
0x18000411e  lea     rcx, [r15+r15*2]
0x180004122  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180004126  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x18000412a  movsd   xmm1, qword ptr [rax+rcx*8+10h]
0x180004130  lea     rax, [rbp+var_30]
0x180004134  mov     rcx, [rbp+arg_8]; struct IXMLDOMDocument *
0x180004138  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000413c  movsd   qword ptr [rbp+var_20+10h], xmm1
0x180004141  mov     [rsp+80h+var_60], rax; struct IXMLDOMElement **
0x180004146  call    ?HrCreateElementWithType@@YAJPEAUIXMLDOMDocument@@PEBG1UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithType(IXMLDOMDocument *,ushort const *,ushort const *,tagVARIANT,IXMLDOMElement * *)
0x18000414b  mov     edi, eax
0x18000414d  test    eax, eax
0x18000414f  js      loc_1800041F2
0x180004155  mov     rax, [r13+0]
0x180004159  xor     r8d, r8d
0x18000415c  mov     r14, [rbp+var_30]
0x180004160  mov     rcx, r13
0x180004163  mov     rdx, r14
0x180004166  mov     rax, [rax+0A8h]
0x18000416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004172  mov     edi, eax
0x180004174  test    eax, eax
0x180004176  js      short loc_1800041AC
0x180004178  mov     rcx, cs:WPP_GLOBAL_Control
0x18000417f  cmp     rcx, rsi
0x180004182  jz      short loc_1800041DE
0x180004184  test    dword ptr [rcx+1Ch], 400h
0x18000418b  jz      short loc_1800041DE
0x18000418d  mov     r9, [rbp+var_48]
0x180004191  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004198  mov     rcx, [rcx+10h]
0x18000419c  mov     edx, 2Ch ; ','
0x1800041a1  mov     r9, [r9+r15*8]
0x1800041a5  call    WPP_SF_S
0x1800041aa  jmp     short loc_1800041DE
0x1800041ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041b3  cmp     rcx, rsi
0x1800041b6  jz      short loc_1800041DE
0x1800041b8  test    byte ptr [rcx+1Ch], 1
0x1800041bc  jz      short loc_1800041DE
0x1800041be  mov     rcx, [rcx+10h]
0x1800041c2  lea     r9, aHrappendaction_7; "HrAppendActionResponseElementToBody(): "...
0x1800041c9  mov     edx, 2Dh ; '-'
0x1800041ce  mov     dword ptr [rsp+80h+var_60], eax
0x1800041d2  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800041d9  call    WPP_SF_sd
0x1800041de  mov     rax, [r14]
0x1800041e1  mov     rcx, r14
0x1800041e4  mov     rax, [rax+10h]
0x1800041e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ed  xor     r14d, r14d
0x1800041f0  jmp     short loc_18000420B
0x1800041f2  cmp     eax, 80004005h
0x1800041f7  jz      short loc_180004239
0x1800041f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180004200  cmp     rcx, rsi
0x180004203  jz      short loc_18000420B
0x180004205  test    byte ptr [rcx+1Ch], 1
0x180004209  jnz     short loc_180004217
0x18000420b  inc     ebx
0x18000420d  test    edi, edi
0x18000420f  jns     loc_1800040F9
0x180004215  jmp     short loc_180004274
0x180004217  mov     rcx, [rcx+10h]
0x18000421b  lea     r9, aHrappendaction_1; "HrAppendActionResponseElementToBody(): "...
0x180004222  mov     edx, 2Fh ; '/'
0x180004227  mov     dword ptr [rsp+80h+var_60], eax
0x18000422b  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004232  call    WPP_SF_sd
0x180004237  jmp     short loc_180004274
0x180004239  mov     rcx, cs:WPP_GLOBAL_Control
0x180004240  cmp     rcx, rsi
0x180004243  jz      short loc_18000426F
0x180004245  test    byte ptr [rcx+1Ch], 1
0x180004249  jz      short loc_18000426F
0x18000424b  mov     rcx, [rcx+10h]
0x18000424f  lea     r9, aHrappendaction_3; "HrAppendActionResponseElementToBody(): "...
  ... truncated ...
```
