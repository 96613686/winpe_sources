# HrAppendFaultElementToBody(IXMLDOMDocument *,IXMLDOMNode *,tagUPNP_CONTROL_RESPONSE *)

- ea: `0x18000449c`
- end: `0x180004b9e`
- name: `?HrAppendFaultElementToBody@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagUPNP_CONTROL_RESPONSE@@@Z`
- size: `1794`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, struct IXMLDOMNode *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800063e0`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x18000449c`
- `0x18000a070`
- `0x18000a250`
- `0x18000c010`

## string_xrefs

- `0x1800046be`: `HrAppendFaultElementToBody(): Failed to create errorDescription element`
- `0x1800047a1`: `HrAppendFaultElementToBody(): Failed to create errorCode element`
- `0x1800047f2`: `HrAppendFaultElementToBody(): Failed to create UPnPError element`
- `0x180004819`: `HrAppendFaultElementToBody(): Failed to create detail element`
- `0x180004857`: `HrAppendFaultElementToBody(): Failed to create fault string element`
- `0x180004aa6`: `HrAppendFaultElementToBody(): Failed to create fault code element`
- `0x180004b36`: `HrAppendFaultElementToBody(): Failed to create fault element`
- `0x1800044d0`: `http://schemas.xmlsoap.org/soap/envelope/`

## pseudocode

```c
__int64 __fastcall HrAppendFaultElementToBody(
        struct IXMLDOMDocument *a1,
        struct IXMLDOMNode *a2,
        const unsigned __int16 **a3)
{
  struct IXMLDOMNode *v4; // r15
  struct IXMLDOMElement *v5; // rsi
  struct IXMLDOMNode *v6; // r12
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  const unsigned __int16 *v13; // r8
  int v14; // eax
  struct IXMLDOMNode *v15; // r15
  struct IXMLDOMElement *v16; // r13
  int ElementWithTextValue; // eax
  const unsigned __int16 *v18; // r8
  struct IXMLDOMNode *v19; // rsi
  int v20; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  const char *v23; // r9
  _QWORD *v24; // rcx
  int v25; // edx
  const char *v26; // r9
  _QWORD *v27; // rcx
  int v28; // edx
  const char *v29; // r9
  struct IXMLDOMNode *v30; // r14
  int v31; // eax
  int v32; // eax
  _QWORD *v33; // rcx
  int v34; // edx
  const char *v35; // r9
  int v36; // eax
  _QWORD *v37; // rcx
  struct IXMLDOMElement *v39; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMElement *v40; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMNode *v41; // [rsp+40h] [rbp-10h] BYREF
  struct IXMLDOMElement *v42; // [rsp+48h] [rbp-8h] BYREF
  struct IXMLDOMNode *v44; // [rsp+A0h] [rbp+50h] BYREF
  struct IXMLDOMNode *v45; // [rsp+A8h] [rbp+58h] BYREF

  v44 = 0;
  v4 = a2;
  v40 = 0;
  v5 = 0;
  v6 = 0;
  v39 = 0;
  v45 = 0;
  v8 = HrCreateElement(a1, L"SOAP-ENV:Fault", L"http://schemas.xmlsoap.org/soap/envelope/", &v44);
  v9 = v8;
  if ( v8 < 0 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_96;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrAppendFaultElementToBody(): Failed to create fault element",
      v8);
LABEL_95:
    v37 = WPP_GLOBAL_Control;
LABEL_96:
    if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
      WPP_SF_sd(
        v37[2],
        39,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrAppendFaultElementToBody(): Exiting",
        v9);
    return (unsigned int)v9;
  }
  v10 = HrCreateElementWithTextValue(a1, L"faultcode", a3[2], &v40);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v11 = HrCreateElementWithTextValue(a1, L"faultstring", a3[3], &v39);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
          (unsigned int)"HrAppendFaultElementToBody(): Failed to create fault string element",
          v11);
LABEL_48:
      v30 = v44;
      if ( v9 >= 0 )
      {
        v31 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMElement *, _QWORD))v44->lpVtbl->appendChild)(
                v44,
                v40,
                0);
        v9 = v31;
        if ( v31 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
          }
          v5 = v39;
          v32 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMElement *, _QWORD))v30->lpVtbl->appendChild)(
                  v30,
                  v39,
                  0);
          v9 = v32;
          if ( v32 < 0 )
          {
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v34 = 34;
              v35 = "HrAppendFaultElementToBody(): Failed to append fault string element";
              goto LABEL_67;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
            }
            v32 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))v30->lpVtbl->appendChild)(
                    v30,
                    v6,
                    0);
            v9 = v32;
            if ( v32 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
              }
              goto LABEL_68;
            }
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v34 = 33;
              v35 = "HrAppendFaultElementToBody(): Failed to append detail element";
LABEL_67:
              WPP_SF_sd(v33[2], v34, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v35, v32);
            }
          }
LABEL_68:
          if ( v9 >= 0 )
          {
            v36 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))v4->lpVtbl->appendChild)(
                    v4,
                    v30,
                    0);
            v9 = v36;
            if ( v36 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  37,
                  (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                  (unsigned int)"HrAppendFaultElementToBody(): Failed to append fault element to body",
                  v36);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
            }
          }
          goto LABEL_84;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
            (unsigned int)"HrAppendFaultElementToBody(): Failed to append fault code element",
            v31);
      }
      v5 = v39;
      goto LABEL_84;
    }
    v12 = HrCreateElement(a1, L"detail", 0, &v45);
    v9 = v12;
    if ( v12 < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v28 = 27;
      v29 = "HrAppendFaultElementToBody(): Failed to create detail element";
    }
    else
    {
      v41 = 0;
      v12 = HrCreateElement(a1, L"u:UPnPError", L"urn:schemas-upnp-org:control-1-0", &v41);
      v9 = v12;
      if ( v12 >= 0 )
      {
        v13 = a3[4];
        v42 = 0;
        v14 = HrCreateElementWithTextValue(a1, L"u:errorCode", v13, &v42);
        v6 = v45;
        v9 = v14;
        v15 = v41;
        if ( v14 < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_36;
          v25 = 23;
          v26 = "HrAppendFaultElementToBody(): Failed to create errorCode element";
          goto LABEL_35;
        }
        v16 = v42;
        ElementWithTextValue = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMElement *, _QWORD))v41->lpVtbl->appendChild)(
                                 v41,
                                 v42,
                                 0);
        v9 = ElementWithTextValue;
        if ( ElementWithTextValue < 0 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_24;
          v22 = 22;
          v23 = "HrAppendFaultElementToBody(): Failed to append errorCode element";
        }
        else
        {
          v18 = a3[5];
          v45 = 0;
          ElementWithTextValue = HrCreateElementWithTextValue(
                                   a1,
                                   L"u:errorDescription",
                                   v18,
                                   (struct IXMLDOMElement **)&v45);
          v9 = ElementWithTextValue;
          if ( ElementWithTextValue >= 0 )
          {
            v19 = v45;
            v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))v15->lpVtbl->appendChild)(
                    v15,
                    v45,
                    0);
            v9 = v20;
            if ( v20 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
                  (unsigned int)"HrAppendFaultElementToBody(): Failed to append errorCode element",
                  v20);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
            }
            ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
LABEL_24:
            ((void (__fastcall *)(struct IXMLDOMElement *))v16->lpVtbl->Release)(v16);
            if ( v9 < 0 )
              goto LABEL_36;
            v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))v6->lpVtbl->appendChild)(
                    v6,
                    v15,
                    0);
            v9 = v14;
            if ( v14 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids);
              }
              goto LABEL_36;
            }
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_36:
              ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
              v4 = a2;
              goto LABEL_48;
            }
            v25 = 25;
            v26 = "HrAppendFaultElementToBody(): Failed to append UPnPError";
LABEL_35:
            WPP_SF_sd(v24[2], v25, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v26, v14);
            goto LABEL_36;
          }
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_24;
          v22 = 21;
          v23 = "HrAppendFaultElementToBody(): Failed to create errorDescription element";
        }
        WPP_SF_sd(
          v21[2],
          v22,
          (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
          (_DWORD)v23,
          ElementWithTextValue);
        goto LABEL_24;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v28 = 26;
      v29 = "HrAppendFaultElementToBody(): Failed to create UPnPError element";
    }
    WPP_SF_sd(v27[2], v28, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v29, v12);
LABEL_44:
    v6 = v45;
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrAppendFaultElementToBody(): Failed to create fault code element",
      v10);
  v30 = v44;
LABEL_84:
  if ( v40 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v40->lpVtbl->Release)(v40);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  ((void (__fastcall *)(struct IXMLDOMNode *))v30->lpVtbl->Release)(v30);
  if ( v9 )
    goto LABEL_95;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000449c  mov     [rsp-38h+arg_0], rbx
0x1800044a1  mov     [rsp-38h+arg_8], rdx
0x1800044a6  push    rbp
0x1800044a7  push    rsi
0x1800044a8  push    rdi
0x1800044a9  push    r12
0x1800044ab  push    r13
0x1800044ad  push    r14
0x1800044af  push    r15
0x1800044b1  mov     rbp, rsp
0x1800044b4  sub     rsp, 50h
0x1800044b8  mov     r14, r8
0x1800044bb  mov     [rbp+arg_10], 0
0x1800044c3  mov     r15, rdx
0x1800044c6  mov     [rbp+var_18], 0
0x1800044ce  xor     esi, esi
0x1800044d0  lea     r8, aHttpSchemasXml_0; "http://schemas.xmlsoap.org/soap/envelop"...
0x1800044d7  xor     r12d, r12d
0x1800044da  mov     [rbp+var_20], rsi
0x1800044de  lea     rdx, aSoapEnvFault; "SOAP-ENV:Fault"
0x1800044e5  mov     [rbp+arg_18], r12
0x1800044e9  lea     r9, [rbp+arg_10]; struct IXMLDOMNode **
0x1800044ed  mov     rdi, rcx
0x1800044f0  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800044f5  mov     ebx, eax
0x1800044f7  test    eax, eax
0x1800044f9  js      loc_180004B19
0x1800044ff  mov     r8, [r14+10h]; unsigned __int16 *
0x180004503  lea     r9, [rbp+var_18]; struct IXMLDOMElement **
0x180004507  lea     rdx, aFaultcode; "faultcode"
0x18000450e  mov     rcx, rdi; struct IXMLDOMDocument *
0x180004511  call    ?HrCreateElementWithTextValue@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithTextValue(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180004516  mov     ebx, eax
0x180004518  test    eax, eax
0x18000451a  js      loc_180004A89
0x180004520  mov     r8, [r14+18h]; unsigned __int16 *
0x180004524  lea     r9, [rbp+var_20]; struct IXMLDOMElement **
0x180004528  lea     rdx, aFaultstring; "faultstring"
0x18000452f  mov     rcx, rdi; struct IXMLDOMDocument *
0x180004532  call    ?HrCreateElementWithTextValue@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithTextValue(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180004537  mov     ebx, eax
0x180004539  test    eax, eax
0x18000453b  js      loc_18000483A
0x180004541  lea     r9, [rbp+arg_18]; struct IXMLDOMNode **
0x180004545  xor     r8d, r8d; unsigned __int16 *
0x180004548  lea     rdx, aDetail; "detail"
0x18000454f  mov     rcx, rdi; struct IXMLDOMDocument *
0x180004552  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180004557  mov     ebx, eax
0x180004559  test    eax, eax
0x18000455b  js      loc_1800047FB
0x180004561  lea     r9, [rbp+var_10]; struct IXMLDOMNode **
0x180004565  mov     [rbp+var_10], rsi
0x180004569  lea     r8, aUrnSchemasUpnp; "urn:schemas-upnp-org:control-1-0"
0x180004570  mov     rcx, rdi; struct IXMLDOMDocument *
0x180004573  lea     rdx, aUUpnperror; "u:UPnPError"
0x18000457a  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000457f  mov     ebx, eax
0x180004581  test    eax, eax
0x180004583  js      loc_1800047D4
0x180004589  mov     r8, [r14+20h]; unsigned __int16 *
0x18000458d  lea     r9, [rbp+var_8]; struct IXMLDOMElement **
0x180004591  lea     rdx, aUErrorcode; "u:errorCode"
0x180004598  mov     [rbp+var_8], rsi
0x18000459c  mov     rcx, rdi; struct IXMLDOMDocument *
0x18000459f  call    ?HrCreateElementWithTextValue@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithTextValue(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800045a4  mov     r12, [rbp+arg_18]
0x1800045a8  mov     ebx, eax
0x1800045aa  mov     r15, [rbp+var_10]
0x1800045ae  test    eax, eax
0x1800045b0  js      loc_180004783
0x1800045b6  mov     rax, [r15]
0x1800045b9  xor     r8d, r8d
0x1800045bc  mov     r13, [rbp+var_8]
0x1800045c0  mov     rcx, r15
0x1800045c3  mov     rdx, r13
0x1800045c6  mov     rax, [rax+0A8h]
0x1800045cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d2  mov     ebx, eax
0x1800045d4  test    eax, eax
0x1800045d6  js      loc_1800046C7
0x1800045dc  mov     r8, [r14+28h]; unsigned __int16 *
0x1800045e0  lea     r9, [rbp+arg_18]; struct IXMLDOMElement **
0x1800045e4  lea     rdx, aUErrordescript; "u:errorDescription"
0x1800045eb  mov     [rbp+arg_18], rsi
0x1800045ef  mov     rcx, rdi; struct IXMLDOMDocument *
0x1800045f2  call    ?HrCreateElementWithTextValue@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithTextValue(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800045f7  mov     ebx, eax
0x1800045f9  test    eax, eax
0x1800045fb  js      loc_1800046A0
0x180004601  mov     rax, [r15]
0x180004604  xor     r8d, r8d
0x180004607  mov     rsi, [rbp+arg_18]
0x18000460b  mov     rcx, r15
0x18000460e  mov     rdx, rsi
0x180004611  mov     rax, [rax+0A8h]
0x180004618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000461d  mov     ebx, eax
0x18000461f  test    eax, eax
0x180004621  js      short loc_180004656
0x180004623  mov     rcx, cs:WPP_GLOBAL_Control
0x18000462a  lea     rdi, WPP_GLOBAL_Control
0x180004631  cmp     rcx, rdi
0x180004634  jz      short loc_18000468F
0x180004636  test    dword ptr [rcx+1Ch], 400h
0x18000463d  jz      short loc_18000468F
0x18000463f  mov     rcx, [rcx+10h]
0x180004643  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000464a  mov     edx, 13h
0x18000464f  call    WPP_SF_
0x180004654  jmp     short loc_18000468F
0x180004656  mov     rcx, cs:WPP_GLOBAL_Control
0x18000465d  lea     rdi, WPP_GLOBAL_Control
0x180004664  cmp     rcx, rdi
0x180004667  jz      short loc_18000468F
0x180004669  test    byte ptr [rcx+1Ch], 1
0x18000466d  jz      short loc_18000468F
0x18000466f  mov     rcx, [rcx+10h]
0x180004673  lea     r9, aHrappendfaulte_5; "HrAppendFaultElementToBody(): Failed to"...
0x18000467a  mov     edx, 14h
0x18000467f  mov     [rsp+50h+var_30], eax
0x180004683  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000468a  call    WPP_SF_sd
0x18000468f  mov     rax, [rsi]
0x180004692  mov     rcx, rsi
0x180004695  mov     rax, [rax+10h]
0x180004699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469e  jmp     short loc_180004700
0x1800046a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046a7  lea     rdi, WPP_GLOBAL_Control
0x1800046ae  cmp     rcx, rdi
0x1800046b1  jz      short loc_180004700
0x1800046b3  test    byte ptr [rcx+1Ch], 1
0x1800046b7  jz      short loc_180004700
0x1800046b9  mov     edx, 15h
0x1800046be  lea     r9, aHrappendfaulte_12; "HrAppendFaultElementToBody(): Failed to"...
0x1800046c5  jmp     short loc_1800046EC
0x1800046c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046ce  lea     rdi, WPP_GLOBAL_Control
0x1800046d5  cmp     rcx, rdi
0x1800046d8  jz      short loc_180004700
0x1800046da  test    byte ptr [rcx+1Ch], 1
0x1800046de  jz      short loc_180004700
0x1800046e0  mov     edx, 16h
0x1800046e5  lea     r9, aHrappendfaulte_5; "HrAppendFaultElementToBody(): Failed to"...
0x1800046ec  mov     rcx, [rcx+10h]
0x1800046f0  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800046f7  mov     [rsp+50h+var_30], eax
0x1800046fb  call    WPP_SF_sd
0x180004700  mov     rax, [r13+0]
0x180004704  mov     rcx, r13
0x180004707  mov     rax, [rax+10h]
0x18000470b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004710  test    ebx, ebx
0x180004712  js      loc_1800047BC
0x180004718  mov     rax, [r12]
0x18000471c  xor     r8d, r8d
0x18000471f  mov     rdx, r15
0x180004722  mov     rcx, r12
0x180004725  mov     rax, [rax+0A8h]
0x18000472c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004731  mov     ebx, eax
0x180004733  test    eax, eax
0x180004735  js      short loc_180004763
0x180004737  mov     rcx, cs:WPP_GLOBAL_Control
0x18000473e  cmp     rcx, rdi
0x180004741  jz      short loc_1800047BC
0x180004743  test    dword ptr [rcx+1Ch], 400h
0x18000474a  jz      short loc_1800047BC
0x18000474c  mov     rcx, [rcx+10h]
0x180004750  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004757  mov     edx, 18h
0x18000475c  call    WPP_SF_
0x180004761  jmp     short loc_1800047BC
0x180004763  mov     rcx, cs:WPP_GLOBAL_Control
0x18000476a  cmp     rcx, rdi
0x18000476d  jz      short loc_1800047BC
0x18000476f  test    byte ptr [rcx+1Ch], 1
0x180004773  jz      short loc_1800047BC
0x180004775  mov     edx, 19h
0x18000477a  lea     r9, aHrappendfaulte_7; "HrAppendFaultElementToBody(): Failed to"...
0x180004781  jmp     short loc_1800047A8
0x180004783  mov     rcx, cs:WPP_GLOBAL_Control
0x18000478a  lea     rdi, WPP_GLOBAL_Control
0x180004791  cmp     rcx, rdi
0x180004794  jz      short loc_1800047BC
0x180004796  test    byte ptr [rcx+1Ch], 1
0x18000479a  jz      short loc_1800047BC
0x18000479c  mov     edx, 17h
0x1800047a1  lea     r9, aHrappendfaulte_0; "HrAppendFaultElementToBody(): Failed to"...
0x1800047a8  mov     rcx, [rcx+10h]
0x1800047ac  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800047b3  mov     [rsp+50h+var_30], eax
0x1800047b7  call    WPP_SF_sd
0x1800047bc  mov     rax, [r15]
0x1800047bf  mov     rcx, r15
0x1800047c2  mov     rax, [rax+10h]
0x1800047c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047cb  mov     r15, [rbp+arg_8]
0x1800047cf  jmp     loc_180004873
0x1800047d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047db  lea     rdi, WPP_GLOBAL_Control
0x1800047e2  cmp     rcx, rdi
0x1800047e5  jz      short loc_180004834
0x1800047e7  test    byte ptr [rcx+1Ch], 1
0x1800047eb  jz      short loc_180004834
0x1800047ed  mov     edx, 1Ah
0x1800047f2  lea     r9, aHrappendfaulte_10; "HrAppendFaultElementToBody(): Failed to"...
0x1800047f9  jmp     short loc_180004820
0x1800047fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004802  lea     rdi, WPP_GLOBAL_Control
0x180004809  cmp     rcx, rdi
0x18000480c  jz      short loc_180004834
0x18000480e  test    byte ptr [rcx+1Ch], 1
0x180004812  jz      short loc_180004834
0x180004814  mov     edx, 1Bh
0x180004819  lea     r9, aHrappendfaulte_4; "HrAppendFaultElementToBody(): Failed to"...
0x180004820  mov     rcx, [rcx+10h]
0x180004824  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000482b  mov     [rsp+50h+var_30], eax
0x18000482f  call    WPP_SF_sd
0x180004834  mov     r12, [rbp+arg_18]
0x180004838  jmp     short loc_180004873
0x18000483a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004841  lea     rdi, WPP_GLOBAL_Control
0x180004848  cmp     rcx, rdi
0x18000484b  jz      short loc_180004873
0x18000484d  test    byte ptr [rcx+1Ch], 1
0x180004851  jz      short loc_180004873
0x180004853  mov     rcx, [rcx+10h]
0x180004857  lea     r9, aHrappendfaulte_11; "HrAppendFaultElementToBody(): Failed to"...
0x18000485e  mov     edx, 1Ch
0x180004863  mov     [rsp+50h+var_30], eax
0x180004867  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000486e  call    WPP_SF_sd
0x180004873  mov     r14, [rbp+arg_10]
0x180004877  test    ebx, ebx
0x180004879  js      loc_180004A83
0x18000487f  mov     rax, [r14]
0x180004882  xor     r8d, r8d
0x180004885  mov     rdx, [rbp+var_18]
0x180004889  mov     rcx, r14
0x18000488c  mov     rax, [rax+0A8h]
0x180004893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004898  mov     ebx, eax
0x18000489a  test    eax, eax
0x18000489c  js      loc_180004A51
0x1800048a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048a9  cmp     rcx, rdi
0x1800048ac  jz      short loc_1800048CC
0x1800048ae  test    dword ptr [rcx+1Ch], 400h
0x1800048b5  jz      short loc_1800048CC
0x1800048b7  mov     rcx, [rcx+10h]
0x1800048bb  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800048c2  mov     edx, 1Eh
0x1800048c7  call    WPP_SF_
0x1800048cc  mov     rax, [r14]
0x1800048cf  xor     r8d, r8d
0x1800048d2  mov     rsi, [rbp+var_20]
0x1800048d6  mov     rcx, r14
0x1800048d9  mov     rdx, rsi
0x1800048dc  mov     rax, [rax+0A8h]
0x1800048e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e8  mov     ebx, eax
0x1800048ea  test    eax, eax
0x1800048ec  js      loc_180004986
0x1800048f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048f9  cmp     rcx, rdi
0x1800048fc  jz      short loc_18000491C
0x1800048fe  test    dword ptr [rcx+1Ch], 400h
0x180004905  jz      short loc_18000491C
0x180004907  mov     rcx, [rcx+10h]
0x18000490b  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004912  mov     edx, 1Fh
0x180004917  call    WPP_SF_
0x18000491c  mov     rax, [r14]
0x18000491f  xor     r8d, r8d
0x180004922  mov     rdx, r12
0x180004925  mov     rcx, r14
0x180004928  mov     rax, [rax+0A8h]
0x18000492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004934  mov     ebx, eax
0x180004936  test    eax, eax
0x180004938  js      short loc_180004966
0x18000493a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004941  cmp     rcx, rdi
0x180004944  jz      short loc_1800049B8
0x180004946  test    dword ptr [rcx+1Ch], 400h
0x18000494d  jz      short loc_1800049B8
0x18000494f  mov     rcx, [rcx+10h]
0x180004953  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000495a  mov     edx, 20h ; ' '
0x18000495f  call    WPP_SF_
0x180004964  jmp     short loc_1800049B8
0x180004966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000496d  cmp     rcx, rdi
0x180004970  jz      short loc_1800049B8
0x180004972  test    byte ptr [rcx+1Ch], 1
0x180004976  jz      short loc_1800049B8
0x180004978  mov     edx, 21h ; '!'
  ... truncated ...
```
