# HrSerializeAndSendResponse(_EXTENSION_CONTROL_BLOCK *,IUPnPAutomationProxy *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUPnPServiceDescriptionInfo *)

- ea: `0x1800063e0`
- end: `0x18000675e`
- name: `?HrSerializeAndSendResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIUPnPAutomationProxy@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUPnPServiceDescriptionInfo@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, struct IUPnPAutomationProxy *, struct tagUPNP_CONTROL_REQUEST *, struct tagUPNP_CONTROL_RESPONSE *, struct IUPnPServiceDescriptionInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000512c`

## callees

- `0x1800038ec`
- `0x1800039d4`
- `0x180003dac`
- `0x18000449c`
- `0x1800063e0`
- `0x180006868`
- `0x180009f64`
- `0x18000a070`
- `0x18000b234`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000643e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000643e`
- `OLEAUT32!__imp_SysAllocString` at `0x180006562`
- `OLEAUT32!__imp_SysAllocString` at `0x180006572`
- `OLEAUT32!__imp_SysAllocString` at `0x180006583`
- `OLEAUT32!__imp_SysAllocString` at `0x180006594`
- `OLEAUT32!__imp_SysAllocString` at `0x180006562`
- `OLEAUT32!__imp_SysAllocString` at `0x180006572`
- `OLEAUT32!__imp_SysAllocString` at `0x180006583`
- `OLEAUT32!__imp_SysAllocString` at `0x180006594`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065a1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065af`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065bd`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065a1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065af`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065bd`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065cb`

## string_xrefs

- `0x18000666f`: `HrSerializeResponse(): Failed to create body element`
- `0x1800066b9`: `HrSerializeResponse(): Failed to create envelope element`
- `0x180006470`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x1800064e7`: `http://schemas.xmlsoap.org/soap/envelope/`

## pseudocode

```c
__int64 __fastcall HrSerializeAndSendResponse(
        struct _EXTENSION_CONTROL_BLOCK *a1,
        struct IUPnPAutomationProxy *a2,
        struct tagUPNP_CONTROL_REQUEST *a3,
        struct tagUPNP_CONTROL_RESPONSE *a4,
        struct IUPnPServiceDescriptionInfo *a5)
{
  bool v6; // zf
  const unsigned __int16 *v11; // rdx
  int Instance; // ebx
  const unsigned __int16 *v13; // r8
  struct IXMLDOMNode *v14; // rsi
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // r8
  struct IXMLDOMNode *v17; // r14
  int appended; // eax
  BSTR v19; // rax
  OLECHAR *v20; // rcx
  _QWORD *v21; // rcx
  struct IXMLDOMElement *v22; // [rsp+30h] [rbp-18h] BYREF
  struct IXMLDOMNode *v23[2]; // [rsp+38h] [rbp-10h] BYREF
  struct IXMLDOMDocument *ppv; // [rsp+A8h] [rbp+60h] BYREF

  v6 = *((_DWORD *)a4 + 2) == 1;
  ppv = 0;
  v23[0] = 0;
  if ( v6 && !a3 )
    return 2147942487LL;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&ppv);
  if ( Instance < 0 )
    goto LABEL_33;
  Instance = HrAppendProcessingInstruction(ppv, v11, v13);
  if ( Instance >= 0 )
  {
    Instance = HrCreateElement(ppv, L"SOAP-ENV:Envelope", L"http://schemas.xmlsoap.org/soap/envelope/", v23);
    if ( Instance >= 0 )
    {
      v14 = v23[0];
      v22 = 0;
      Instance = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, struct IXMLDOMElement **))v23[0]->lpVtbl->QueryInterface)(
                   v23[0],
                   &IID_IXMLDOMElement,
                   &v22);
      if ( Instance < 0
        || (Instance = HrSetTextAttribute(v22, v15, v16),
            ((void (__fastcall *)(struct IXMLDOMElement *))v22->lpVtbl->Release)(v22),
            v22 = 0,
            Instance < 0) )
      {
LABEL_26:
        ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
LABEL_30:
        v21 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
      v23[0] = 0;
      Instance = HrCreateElement(ppv, L"SOAP-ENV:Body", L"http://schemas.xmlsoap.org/soap/envelope/", v23);
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
            (unsigned int)"HrSerializeResponse(): Failed to create body element",
            Instance);
        goto LABEL_26;
      }
      v17 = v23[0];
      if ( *((_DWORD *)a4 + 2) )
      {
        appended = HrAppendActionResponseElementToBody(a2, ppv, v23[0], a3, (BSTR *)a4, a5);
        Instance = appended;
        if ( appended == -2147220972 )
        {
          CleanupResponseData((struct tagUPNP_CONTROL_RESPONSE *)((char *)a4 + 16), 1);
          *((_DWORD *)a4 + 2) = 0;
          *((_QWORD *)a4 + 2) = SysAllocString(L"SOAP-ENV:Client");
          *((_QWORD *)a4 + 3) = SysAllocString(L"UPnPError");
          *((_QWORD *)a4 + 4) = SysAllocString(L"501");
          v19 = SysAllocString(L"Internal Device Error");
          v20 = (OLECHAR *)*((_QWORD *)a4 + 2);
          *((_QWORD *)a4 + 5) = v19;
          if ( !SysStringLen(v20)
            || !SysStringLen(*((BSTR *)a4 + 3))
            || !SysStringLen(*((BSTR *)a4 + 4))
            || !SysStringLen(*((BSTR *)a4 + 5)) )
          {
            Instance = -2147024882;
            CleanupResponseData((struct tagUPNP_CONTROL_RESPONSE *)((char *)a4 + 16), 0);
            goto LABEL_21;
          }
        }
        else if ( appended < 0 )
        {
          goto LABEL_21;
        }
        if ( *((_DWORD *)a4 + 2) )
          goto LABEL_20;
      }
      Instance = HrAppendFaultElementToBody(ppv, v17, (const unsigned __int16 **)a4);
      if ( Instance >= 0 )
LABEL_20:
        Instance = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))v14->lpVtbl->appendChild)(
                     v14,
                     v17,
                     0);
LABEL_21:
      ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
      if ( Instance >= 0 )
        Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct IXMLDOMNode *, _QWORD))ppv->lpVtbl->appendChild)(
                     ppv,
                     v14,
                     0);
      goto LABEL_26;
    }
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_34;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrSerializeResponse(): Failed to create envelope element",
      Instance);
    goto LABEL_30;
  }
LABEL_31:
  if ( Instance >= 0 )
  {
    Instance = HrWriteResponse(a1, ppv, *((_DWORD *)a4 + 2));
LABEL_33:
    v21 = WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( ppv )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))ppv->lpVtbl->Release)(ppv);
    v21 = WPP_GLOBAL_Control;
    ppv = 0;
  }
  if ( Instance && v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
    WPP_SF_sd(
      v21[2],
      56,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrSerializeResponse(): Exiting",
      Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800063e0  push    rbp
0x1800063e2  push    rbx
0x1800063e3  push    rsi
0x1800063e4  push    rdi
0x1800063e5  push    r12
0x1800063e7  push    r13
0x1800063e9  push    r14
0x1800063eb  push    r15
0x1800063ed  mov     rbp, rsp
0x1800063f0  sub     rsp, 48h
0x1800063f4  xor     r14d, r14d
0x1800063f7  mov     rdi, r9
0x1800063fa  cmp     dword ptr [r9+8], 1
0x1800063ff  mov     r15, r8
0x180006402  mov     r12, rdx
0x180006405  mov     [rbp+arg_18], r14
0x180006409  mov     r13, rcx
0x18000640c  mov     [rbp+var_10], r14
0x180006410  jnz     short loc_180006421
0x180006412  test    r8, r8
0x180006415  jnz     short loc_180006421
0x180006417  mov     eax, 80070057h
0x18000641c  jmp     loc_18000674D
0x180006421  xor     edx, edx; pUnkOuter
0x180006423  lea     rax, [rbp+arg_18]
0x180006427  lea     r9, IID_IXMLDOMDocument; riid
0x18000642e  mov     [rsp+48h+ppv], rax; ppv
0x180006433  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000643a  lea     r8d, [rdx+1]; dwClsContext
0x18000643e  call    cs:__imp_CoCreateInstance
0x180006444  lea     rsi, WPP_GLOBAL_Control
0x18000644b  mov     ebx, eax
0x18000644d  test    eax, eax
0x18000644f  js      loc_1800066F2
0x180006455  mov     rcx, [rbp+arg_18]; struct IXMLDOMDocument *
0x180006459  call    ?HrAppendProcessingInstruction@@YAJPEAUIXMLDOMDocument@@PEBG1@Z; HrAppendProcessingInstruction(IXMLDOMDocument *,ushort const *,ushort const *)
0x18000645e  mov     ebx, eax
0x180006460  test    eax, eax
0x180006462  js      loc_1800066A3
0x180006468  mov     rcx, [rbp+arg_18]; struct IXMLDOMDocument *
0x18000646c  lea     r9, [rbp+var_10]; struct IXMLDOMNode **
0x180006470  lea     r8, aHttpSchemasXml_0; "http://schemas.xmlsoap.org/soap/envelop"...
0x180006477  lea     rdx, aSoapEnvEnvelop; "SOAP-ENV:Envelope"
0x18000647e  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180006483  mov     ebx, eax
0x180006485  test    eax, eax
0x180006487  js      loc_1800066A3
0x18000648d  mov     rsi, [rbp+var_10]
0x180006491  lea     r8, [rbp+var_18]
0x180006495  mov     [rbp+var_18], r14
0x180006499  lea     rdx, IID_IXMLDOMElement
0x1800064a0  mov     rcx, rsi
0x1800064a3  mov     rax, [rsi]
0x1800064a6  mov     rax, [rax]
0x1800064a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ae  mov     ebx, eax
0x1800064b0  test    eax, eax
0x1800064b2  js      loc_18000668B
0x1800064b8  mov     rcx, [rbp+var_18]; struct IXMLDOMElement *
0x1800064bc  call    ?HrSetTextAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; HrSetTextAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x1800064c1  mov     rcx, [rbp+var_18]
0x1800064c5  mov     ebx, eax
0x1800064c7  mov     rax, [rcx]
0x1800064ca  mov     rax, [rax+10h]
0x1800064ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d3  mov     [rbp+var_18], r14
0x1800064d7  test    ebx, ebx
0x1800064d9  js      loc_18000668B
0x1800064df  mov     rcx, [rbp+arg_18]; struct IXMLDOMDocument *
0x1800064e3  lea     r9, [rbp+var_10]; struct IXMLDOMNode **
0x1800064e7  lea     r8, aHttpSchemasXml_0; "http://schemas.xmlsoap.org/soap/envelop"...
0x1800064ee  mov     [rbp+var_10], r14
0x1800064f2  lea     rdx, aSoapEnvBody; "SOAP-ENV:Body"
0x1800064f9  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800064fe  mov     ebx, eax
0x180006500  test    eax, eax
0x180006502  js      loc_180006652
0x180006508  cmp     dword ptr [rdi+8], 0
0x18000650c  mov     r14, [rbp+var_10]
0x180006510  jz      loc_1800065F0
0x180006516  mov     rax, [rbp+arg_20]
0x18000651a  mov     r9, r15; struct tagUPNP_CONTROL_REQUEST *
0x18000651d  mov     rdx, [rbp+arg_18]; struct IXMLDOMDocument *
0x180006521  mov     r8, r14; struct IXMLDOMNode *
0x180006524  mov     [rsp+48h+var_20], rax; struct IUPnPServiceDescriptionInfo *
0x180006529  mov     rcx, r12; struct IUPnPAutomationProxy *
0x18000652c  mov     [rsp+48h+ppv], rdi; struct tagUPNP_CONTROL_RESPONSE *
0x180006531  call    ?HrAppendActionResponseElementToBody@@YAJPEAUIUPnPAutomationProxy@@PEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagUPNP_CONTROL_REQUEST@@PEAUtagUPNP_CONTROL_RESPONSE@@PEAUIUPnPServiceDescriptionInfo@@@Z; HrAppendActionResponseElementToBody(IUPnPAutomationProxy *,IXMLDOMDocument *,IXMLDOMNode *,tagUPNP_CONTROL_REQUEST *,tagUPNP_CONTROL_RESPONSE *,IUPnPServiceDescriptionInfo *)
0x180006536  mov     ebx, eax
0x180006538  cmp     eax, 80040214h
0x18000653d  jnz     loc_1800065E6
0x180006543  lea     r15, [rdi+10h]
0x180006547  mov     edx, 1; int
0x18000654c  mov     rcx, r15; union tagUPNP_CONTROL_RESPONSE_DATA *
0x18000654f  call    ?CleanupResponseData@@YAXPEATtagUPNP_CONTROL_RESPONSE_DATA@@H@Z; CleanupResponseData(tagUPNP_CONTROL_RESPONSE_DATA *,int)
0x180006554  lea     rcx, aSoapEnvClient; "SOAP-ENV:Client"
0x18000655b  mov     dword ptr [rdi+8], 0
0x180006562  call    cs:__imp_SysAllocString
0x180006568  lea     rcx, aUpnperror; "UPnPError"
0x18000656f  mov     [r15], rax
0x180006572  call    cs:__imp_SysAllocString
0x180006578  lea     rcx, a501; "501"
0x18000657f  mov     [rdi+18h], rax
0x180006583  call    cs:__imp_SysAllocString
0x180006589  lea     rcx, aInternalDevice; "Internal Device Error"
0x180006590  mov     [rdi+20h], rax
0x180006594  call    cs:__imp_SysAllocString
0x18000659a  mov     rcx, [r15]; pbstr
0x18000659d  mov     [rdi+28h], rax
0x1800065a1  call    cs:__imp_SysStringLen
0x1800065a7  test    eax, eax
0x1800065a9  jz      short loc_1800065D5
0x1800065ab  mov     rcx, [rdi+18h]; pbstr
0x1800065af  call    cs:__imp_SysStringLen
0x1800065b5  test    eax, eax
0x1800065b7  jz      short loc_1800065D5
0x1800065b9  mov     rcx, [rdi+20h]; pbstr
0x1800065bd  call    cs:__imp_SysStringLen
0x1800065c3  test    eax, eax
0x1800065c5  jz      short loc_1800065D5
0x1800065c7  mov     rcx, [rdi+28h]; pbstr
0x1800065cb  call    cs:__imp_SysStringLen
0x1800065d1  test    eax, eax
0x1800065d3  jnz     short loc_1800065EA
0x1800065d5  xor     edx, edx; int
0x1800065d7  mov     rcx, r15; union tagUPNP_CONTROL_RESPONSE_DATA *
0x1800065da  mov     ebx, 8007000Eh
0x1800065df  call    ?CleanupResponseData@@YAXPEATtagUPNP_CONTROL_RESPONSE_DATA@@H@Z; CleanupResponseData(tagUPNP_CONTROL_RESPONSE_DATA *,int)
0x1800065e4  jmp     short loc_18000661F
0x1800065e6  test    eax, eax
0x1800065e8  js      short loc_18000661F
0x1800065ea  cmp     dword ptr [rdi+8], 0
0x1800065ee  jnz     short loc_180006605
0x1800065f0  mov     rcx, [rbp+arg_18]; struct IXMLDOMDocument *
0x1800065f4  mov     r8, rdi; struct tagUPNP_CONTROL_RESPONSE *
0x1800065f7  mov     rdx, r14; struct IXMLDOMNode *
0x1800065fa  call    ?HrAppendFaultElementToBody@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagUPNP_CONTROL_RESPONSE@@@Z; HrAppendFaultElementToBody(IXMLDOMDocument *,IXMLDOMNode *,tagUPNP_CONTROL_RESPONSE *)
0x1800065ff  mov     ebx, eax
0x180006601  test    eax, eax
0x180006603  js      short loc_18000661F
0x180006605  mov     rax, [rsi]
0x180006608  xor     r8d, r8d
0x18000660b  mov     rdx, r14
0x18000660e  mov     rcx, rsi
0x180006611  mov     rax, [rax+0A8h]
0x180006618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661d  mov     ebx, eax
0x18000661f  mov     rax, [r14]
0x180006622  mov     rcx, r14
0x180006625  mov     rax, [rax+10h]
0x180006629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000662e  xor     r14d, r14d
0x180006631  test    ebx, ebx
0x180006633  js      short loc_18000668B
0x180006635  mov     rcx, [rbp+arg_18]
0x180006639  xor     r8d, r8d
0x18000663c  mov     rdx, rsi
0x18000663f  mov     rax, [rcx]
0x180006642  mov     rax, [rax+0A8h]
0x180006649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664e  mov     ebx, eax
0x180006650  jmp     short loc_18000668B
0x180006652  mov     rcx, cs:WPP_GLOBAL_Control
0x180006659  lea     rax, WPP_GLOBAL_Control
0x180006660  cmp     rcx, rax
0x180006663  jz      short loc_18000668B
0x180006665  test    byte ptr [rcx+1Ch], 1
0x180006669  jz      short loc_18000668B
0x18000666b  mov     rcx, [rcx+10h]
0x18000666f  lea     r9, aHrserializeres; "HrSerializeResponse(): Failed to create"...
0x180006676  mov     edx, 36h ; '6'
0x18000667b  mov     dword ptr [rsp+48h+ppv], ebx
0x18000667f  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006686  call    WPP_SF_sd
0x18000668b  mov     rax, [rsi]
0x18000668e  mov     rcx, rsi
0x180006691  mov     rax, [rax+10h]
0x180006695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669a  lea     rsi, WPP_GLOBAL_Control
0x1800066a1  jmp     short loc_1800066D5
0x1800066a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066aa  cmp     rcx, rsi
0x1800066ad  jz      short loc_1800066F9
0x1800066af  test    byte ptr [rcx+1Ch], 1
0x1800066b3  jz      short loc_1800066DC
0x1800066b5  mov     rcx, [rcx+10h]
0x1800066b9  lea     r9, aHrserializeres_1; "HrSerializeResponse(): Failed to create"...
0x1800066c0  mov     edx, 37h ; '7'
0x1800066c5  mov     dword ptr [rsp+48h+ppv], ebx
0x1800066c9  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800066d0  call    WPP_SF_sd
0x1800066d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066dc  test    ebx, ebx
0x1800066de  js      short loc_1800066F9
0x1800066e0  mov     r8d, [rdi+8]; int
0x1800066e4  mov     rcx, r13; struct _EXTENSION_CONTROL_BLOCK *
0x1800066e7  mov     rdx, [rbp+arg_18]; struct IXMLDOMDocument *
0x1800066eb  call    ?HrWriteResponse@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIXMLDOMDocument@@H@Z; HrWriteResponse(_EXTENSION_CONTROL_BLOCK *,IXMLDOMDocument *,int)
0x1800066f0  mov     ebx, eax
0x1800066f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066f9  mov     rdx, [rbp+arg_18]
0x1800066fd  test    rdx, rdx
0x180006700  jz      short loc_18000671C
0x180006702  mov     rax, [rdx]
0x180006705  mov     rcx, rdx
0x180006708  mov     rax, [rax+10h]
0x18000670c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006711  mov     rcx, cs:WPP_GLOBAL_Control
0x180006718  mov     [rbp+arg_18], r14
0x18000671c  test    ebx, ebx
0x18000671e  jz      short loc_18000674B
0x180006720  cmp     rcx, rsi
0x180006723  jz      short loc_18000674B
0x180006725  test    byte ptr [rcx+1Ch], 1
0x180006729  jz      short loc_18000674B
0x18000672b  mov     rcx, [rcx+10h]
0x18000672f  lea     r9, aHrserializeres_0; "HrSerializeResponse(): Exiting"
0x180006736  mov     edx, 38h ; '8'
0x18000673b  mov     dword ptr [rsp+48h+ppv], ebx
0x18000673f  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180006746  call    WPP_SF_sd
0x18000674b  mov     eax, ebx
0x18000674d  add     rsp, 48h
0x180006751  pop     r15
0x180006753  pop     r14
0x180006755  pop     r13
0x180006757  pop     r12
0x180006759  pop     rdi
0x18000675a  pop     rsi
0x18000675b  pop     rbx
0x18000675c  pop     rbp
0x18000675d  retn
```
