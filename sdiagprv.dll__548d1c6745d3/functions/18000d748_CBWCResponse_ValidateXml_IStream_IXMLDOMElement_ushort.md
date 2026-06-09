# CBWCResponse::ValidateXml(IStream *,IXMLDOMElement * *,ushort * *)

- ea: `0x18000d748`
- end: `0x18000da9a`
- name: `?ValidateXml@CBWCResponse@@CAJPEAUIStream@@PEAPEAUIXMLDOMElement@@PEAPEAG@Z`
- size: `850`
- prototype: `__int64 __fastcall(struct IStream *, struct IXMLDOMElement **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d244`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002bf0`
- `0x180002f24`
- `0x1800031d8`
- `0x1800032ec`
- `0x18000331c`
- `0x18000d21c`
- `0x18000d748`
- `0x1800166e4`
- `0x180016858`
- `0x1800169d0`
- `0x180019010`

## string_xrefs

- `0x18000d7f5`: `CBWCResponse::ValidateXml`
- `0x18000d996`: `CBWCResponse::ValidateXml`
- `0x18000da0f`: `CBWCResponse::ValidateXml`

## pseudocode

```c
__int64 __fastcall CBWCResponse::ValidateXml(struct IStream *a1, struct IXMLDOMElement **a2, unsigned __int16 **a3)
{
  CXmlValidator *v4; // rdi
  const unsigned __int16 *v7; // rdx
  struct IXMLDOMParseError *v8; // rcx
  int v9; // ebx
  const char *v10; // rax
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  int v12; // eax
  __int64 v13; // r9
  __int64 *v14; // rdx
  struct IXMLDOMDocument *v16; // [rsp+30h] [rbp-39h] BYREF
  struct IXMLDOMParseError *v17; // [rsp+38h] [rbp-31h] BYREF
  struct IXMLDOMDocument *v18; // [rsp+40h] [rbp-29h] BYREF
  CXmlValidator *v19; // [rsp+48h] [rbp-21h] BYREF
  struct tagVARIANT v20; // [rsp+50h] [rbp-19h] BYREF
  struct tagVARIANT v21; // [rsp+70h] [rbp+7h] BYREF
  __int16 v22; // [rsp+E8h] [rbp+7Fh] BYREF

  v18 = 0;
  v16 = 0;
  v4 = 0;
  v22 = -1;
  v19 = 0;
  v17 = 0;
  memset(&v20, 0, sizeof(v20));
  v9 = SDiagPrviVariantInit(&v20);
  if ( v9 >= 0 )
  {
    if ( !a1 )
    {
      v9 = -2147024809;
      goto LABEL_38;
    }
    if ( !a2 )
    {
      v9 = -2147024809;
      goto LABEL_41;
    }
    if ( !a3 )
    {
      v9 = -2147024809;
LABEL_8:
      if ( !v17 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_48;
        v10 = "ParseError";
        goto LABEL_11;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_48;
      v13 = 2147942487LL;
LABEL_34:
      McTemplateU0sq_EventWriteTransfer(v8, v7, "CBWCResponse::ValidateXml", v13);
      goto LABEL_48;
    }
    *a2 = 0;
    *a3 = 0;
    v9 = SDiagPrviCreateXmlDocument(&v16);
    if ( v9 >= 0 )
    {
      v20.vt = 13;
      v9 = (**(__int64 (__fastcall ***)(struct IStream *, GUID *, ULONG *))a1)(a1, &IID_IUnknown, (ULONG *)&v20.cyVal);
      if ( v9 >= 0 )
      {
        lpVtbl = v16->lpVtbl;
        v21 = v20;
        v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct tagVARIANT *, __int16 *))lpVtbl->load)(
               v16,
               &v21,
               &v22);
        if ( v9 >= 0 )
        {
          if ( v22 )
          {
            v9 = SDiagPrviSetDOMProperties(v16, v7);
            if ( v9 >= 0 )
            {
              v9 = CXmlValidator::CreateInstance(&v19, (int)v7);
              if ( v9 < 0 || (v9 = SDiagPrviLoadXsdResource((const unsigned __int16 *)v8, v7, &v18), v9 < 0) )
              {
                v4 = v19;
              }
              else
              {
                v4 = v19;
                v9 = CXmlValidator::AddSchema((__int64 **)v19, v7, v18);
                if ( v9 >= 0 )
                {
                  v12 = CXmlValidator::ValidateDocument(v4, v16, &v17);
                  v8 = v17;
                  v9 = v12;
                  if ( v17 )
                  {
                    v9 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, unsigned __int16 **))v17->lpVtbl->get_reason)(
                           v17,
                           a3);
                    if ( v9 >= 0 )
                    {
                      v9 = -2147446781;
                      goto LABEL_32;
                    }
                  }
                  else if ( v12 >= 0 )
                  {
                    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct IXMLDOMElement **))v16->lpVtbl->get_documentElement)(
                           v16,
                           a2);
                  }
                }
              }
            }
          }
          else
          {
            v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct IXMLDOMParseError **))v16->lpVtbl->get_parseError)(
                   v16,
                   &v17);
            if ( v9 >= 0 )
            {
              v9 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, unsigned __int16 **))v17->lpVtbl->get_reason)(
                     v17,
                     a3);
              if ( v9 >= 0 )
              {
                v9 = -2147023431;
LABEL_32:
                if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
                  goto LABEL_48;
                v13 = (unsigned int)v9;
                goto LABEL_34;
              }
            }
          }
        }
      }
    }
  }
  if ( v9 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_48;
    v14 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_47;
  }
  if ( v9 != -2147024809 )
  {
    if ( v9 )
      goto LABEL_32;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_48;
    v14 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_47:
    McTemplateU0s_EventWriteTransfer(v8, v14, "CBWCResponse::ValidateXml");
    goto LABEL_48;
  }
  if ( !a1 )
  {
LABEL_38:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v10 = "Stream";
LABEL_11:
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)v8,
        (_DWORD)v7,
        (unsigned int)"CBWCResponse::ValidateXml",
        -2147024809,
        (__int64)v10);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( a2 )
    goto LABEL_8;
LABEL_41:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v10 = "DocumentRoot";
    goto LABEL_11;
  }
LABEL_48:
  if ( v16 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  if ( v18 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v4 )
    CXmlValidator::`scalar deleting destructor'(v4);
  if ( v17 )
  {
    ((void (__fastcall *)(struct IXMLDOMParseError *))v17->lpVtbl->Release)(v17);
    v17 = 0;
  }
  SDiagPrviVariantClear(&v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000d748  push    rbp
0x18000d74a  push    rbx
0x18000d74b  push    rsi
0x18000d74c  push    rdi
0x18000d74d  push    r14
0x18000d74f  push    r15
0x18000d751  lea     rbp, [rsp-2Fh]
0x18000d756  sub     rsp, 98h
0x18000d75d  xor     eax, eax
0x18000d75f  mov     [rbp+57h+var_80], 0
0x18000d767  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18000d76b  mov     r15, rcx
0x18000d76e  mov     [rbp+57h+var_90], rax
0x18000d772  lea     rcx, [rbp+57h+var_70]; struct tagVARIANT *
0x18000d776  or      eax, 0FFFFFFFFh
0x18000d779  xorps   xmm0, xmm0
0x18000d77c  xor     edi, edi
0x18000d77e  mov     [rbp+57h+arg_18], ax
0x18000d782  mov     r14, r8
0x18000d785  mov     [rbp+57h+var_78], rdi
0x18000d789  mov     rsi, rdx
0x18000d78c  mov     [rbp+57h+var_88], rdi
0x18000d790  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18000d794  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x18000d799  mov     ebx, eax
0x18000d79b  test    eax, eax
0x18000d79d  js      loc_18000D96E
0x18000d7a3  test    r15, r15
0x18000d7a6  jnz     short loc_18000D7B2
0x18000d7a8  mov     ebx, 80070057h
0x18000d7ad  jmp     loc_18000D9BB
0x18000d7b2  test    rsi, rsi
0x18000d7b5  jnz     short loc_18000D7C1
0x18000d7b7  mov     ebx, 80070057h
0x18000d7bc  jmp     loc_18000D9D9
0x18000d7c1  test    r14, r14
0x18000d7c4  jnz     short loc_18000D806
0x18000d7c6  mov     ebx, 80070057h
0x18000d7cb  cmp     [rbp+57h+var_88], 0
0x18000d7d0  jnz     loc_18000D9EE
0x18000d7d6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d7dd  jz      loc_18000DA1B
0x18000d7e3  lea     rax, aParseerror; "ParseError"
0x18000d7ea  mov     r9d, 80070057h
0x18000d7f0  mov     [rsp+0C0h+var_A0], rax
0x18000d7f5  lea     r8, aCbwcresponseVa; "CBWCResponse::ValidateXml"
0x18000d7fc  call    McTemplateU0sqs_EventWriteTransfer
0x18000d801  jmp     loc_18000DA1B
0x18000d806  mov     [rsi], rdi
0x18000d809  lea     rcx, [rbp+57h+var_90]; struct IXMLDOMDocument **
0x18000d80d  mov     [r14], rdi
0x18000d810  call    ?SDiagPrviCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@@Z; SDiagPrviCreateXmlDocument(IXMLDOMDocument * *)
0x18000d815  mov     ebx, eax
0x18000d817  test    eax, eax
0x18000d819  js      loc_18000D96E
0x18000d81f  mov     eax, 0Dh
0x18000d824  lea     r8, [rbp+57h+var_70+8]
0x18000d828  mov     word ptr [rbp+57h+var_70], ax
0x18000d82c  lea     rdx, IID_IUnknown
0x18000d833  mov     rax, [r15]
0x18000d836  mov     rcx, r15
0x18000d839  mov     rax, [rax]
0x18000d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d841  mov     ebx, eax
0x18000d843  test    eax, eax
0x18000d845  js      loc_18000D96E
0x18000d84b  mov     rcx, [rbp+57h+var_90]
0x18000d84f  lea     r8, [rbp+57h+arg_18]
0x18000d853  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18000d857  lea     rdx, [rbp+57h+var_50]
0x18000d85b  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x18000d860  mov     rax, [rcx]
0x18000d863  movaps  [rbp+57h+var_50], xmm0
0x18000d867  movsd   [rbp+57h+var_40], xmm1
0x18000d86c  mov     rax, [rax+1D0h]
0x18000d873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d878  mov     ebx, eax
0x18000d87a  test    eax, eax
0x18000d87c  js      loc_18000D96E
0x18000d882  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMDocument *
0x18000d886  xor     eax, eax
0x18000d888  cmp     ax, [rbp+57h+arg_18]
0x18000d88c  jnz     short loc_18000D8D2
0x18000d88e  mov     rax, [rcx]
0x18000d891  lea     rdx, [rbp+57h+var_88]
0x18000d895  mov     rax, [rax+1E0h]
0x18000d89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a1  mov     ebx, eax
0x18000d8a3  test    eax, eax
0x18000d8a5  js      loc_18000D96E
0x18000d8ab  mov     rcx, [rbp+57h+var_88]
0x18000d8af  mov     rdx, r14
0x18000d8b2  mov     rax, [rcx]
0x18000d8b5  mov     rax, [rax+48h]
0x18000d8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8be  mov     ebx, eax
0x18000d8c0  test    eax, eax
0x18000d8c2  js      loc_18000D96E
0x18000d8c8  mov     ebx, 800705B9h
0x18000d8cd  jmp     loc_18000D986
0x18000d8d2  call    ?SDiagPrviSetDOMProperties@@YAJPEAUIXMLDOMDocument@@PEBG@Z; SDiagPrviSetDOMProperties(IXMLDOMDocument *,ushort const *)
0x18000d8d7  mov     ebx, eax
0x18000d8d9  test    eax, eax
0x18000d8db  js      loc_18000D96E
0x18000d8e1  lea     rcx, [rbp+57h+var_78]; struct CXmlValidator **
0x18000d8e5  call    ?CreateInstance@CXmlValidator@@SAJPEAPEAV1@@Z; CXmlValidator::CreateInstance(CXmlValidator * *)
0x18000d8ea  mov     ebx, eax
0x18000d8ec  test    eax, eax
0x18000d8ee  js      short loc_18000D96A
0x18000d8f0  lea     r8, [rbp+57h+var_80]; struct IXMLDOMDocument **
0x18000d8f4  call    ?SDiagPrviLoadXsdResource@@YAJPEBG0PEAPEAUIXMLDOMDocument@@@Z; SDiagPrviLoadXsdResource(ushort const *,ushort const *,IXMLDOMDocument * *)
0x18000d8f9  mov     ebx, eax
0x18000d8fb  test    eax, eax
0x18000d8fd  js      short loc_18000D96A
0x18000d8ff  mov     rdi, [rbp+57h+var_78]
0x18000d903  mov     r8, [rbp+57h+var_80]; struct IXMLDOMDocument *
0x18000d907  mov     rcx, rdi; this
0x18000d90a  call    ?AddSchema@CXmlValidator@@QEAAJPEBGPEAUIXMLDOMDocument@@@Z; CXmlValidator::AddSchema(ushort const *,IXMLDOMDocument *)
0x18000d90f  mov     ebx, eax
0x18000d911  test    eax, eax
0x18000d913  js      short loc_18000D96E
0x18000d915  mov     rdx, [rbp+57h+var_90]; struct IXMLDOMDocument *
0x18000d919  lea     r8, [rbp+57h+var_88]; struct IXMLDOMParseError **
0x18000d91d  mov     rcx, rdi; this
0x18000d920  call    ?ValidateDocument@CXmlValidator@@QEAAJPEAUIXMLDOMDocument@@PEAPEAUIXMLDOMParseError@@@Z; CXmlValidator::ValidateDocument(IXMLDOMDocument *,IXMLDOMParseError * *)
0x18000d925  mov     rcx, [rbp+57h+var_88]
0x18000d929  mov     ebx, eax
0x18000d92b  test    rcx, rcx
0x18000d92e  jz      short loc_18000D94C
0x18000d930  mov     rax, [rcx]
0x18000d933  mov     rdx, r14
0x18000d936  mov     rax, [rax+48h]
0x18000d93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d93f  mov     ebx, eax
0x18000d941  test    eax, eax
0x18000d943  js      short loc_18000D96E
0x18000d945  mov     ebx, 80009003h
0x18000d94a  jmp     short loc_18000D986
0x18000d94c  test    eax, eax
0x18000d94e  js      short loc_18000D96E
0x18000d950  mov     rcx, [rbp+57h+var_90]
0x18000d954  mov     rdx, rsi
0x18000d957  mov     rax, [rcx]
0x18000d95a  mov     rax, [rax+168h]
0x18000d961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d966  mov     ebx, eax
0x18000d968  jmp     short loc_18000D96E
0x18000d96a  mov     rdi, [rbp+57h+var_78]
0x18000d96e  cmp     ebx, 8007000Eh
0x18000d974  jz      loc_18000D9FF
0x18000d97a  cmp     ebx, 80070057h
0x18000d980  jz      short loc_18000D9B6
0x18000d982  test    ebx, ebx
0x18000d984  jz      short loc_18000D9A4
0x18000d986  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d98d  jz      loc_18000DA1B
0x18000d993  mov     r9d, ebx
0x18000d996  lea     r8, aCbwcresponseVa; "CBWCResponse::ValidateXml"
0x18000d99d  call    McTemplateU0sq_EventWriteTransfer
0x18000d9a2  jmp     short loc_18000DA1B
0x18000d9a4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000d9ab  jz      short loc_18000DA1B
0x18000d9ad  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000d9b4  jmp     short loc_18000DA0F
0x18000d9b6  test    r15, r15
0x18000d9b9  jnz     short loc_18000D9D0
0x18000d9bb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d9c2  jz      short loc_18000DA1B
0x18000d9c4  lea     rax, aStream; "Stream"
0x18000d9cb  jmp     loc_18000D7EA
0x18000d9d0  test    rsi, rsi
0x18000d9d3  jnz     loc_18000D7CB
0x18000d9d9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d9e0  jz      short loc_18000DA1B
0x18000d9e2  lea     rax, aDocumentroot; "DocumentRoot"
0x18000d9e9  jmp     loc_18000D7EA
0x18000d9ee  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d9f5  jz      short loc_18000DA1B
0x18000d9f7  mov     r9d, 80070057h
0x18000d9fd  jmp     short loc_18000D996
0x18000d9ff  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000da06  jz      short loc_18000DA1B
0x18000da08  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000da0f  lea     r8, aCbwcresponseVa; "CBWCResponse::ValidateXml"
0x18000da16  call    McTemplateU0s_EventWriteTransfer
0x18000da1b  mov     rcx, [rbp+57h+var_90]
0x18000da1f  test    rcx, rcx
0x18000da22  jz      short loc_18000DA38
0x18000da24  mov     rax, [rcx]
0x18000da27  mov     rax, [rax+10h]
0x18000da2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da30  mov     [rbp+57h+var_90], 0
0x18000da38  mov     rcx, [rbp+57h+var_80]
0x18000da3c  test    rcx, rcx
0x18000da3f  jz      short loc_18000DA55
0x18000da41  mov     rax, [rcx]
0x18000da44  mov     rax, [rax+10h]
0x18000da48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da4d  mov     [rbp+57h+var_80], 0
0x18000da55  test    rdi, rdi
0x18000da58  jz      short loc_18000DA62
0x18000da5a  mov     rcx, rdi; this
0x18000da5d  call    ??_GCXmlValidator@@QEAAPEAXI@Z; CXmlValidator::`scalar deleting destructor'(uint)
0x18000da62  mov     rcx, [rbp+57h+var_88]
0x18000da66  test    rcx, rcx
0x18000da69  jz      short loc_18000DA7F
0x18000da6b  mov     rax, [rcx]
0x18000da6e  mov     rax, [rax+10h]
0x18000da72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da77  mov     [rbp+57h+var_88], 0
0x18000da7f  lea     rcx, [rbp+57h+var_70]; struct tagVARIANT *
0x18000da83  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x18000da88  mov     eax, ebx
0x18000da8a  add     rsp, 98h
0x18000da91  pop     r15
0x18000da93  pop     r14
0x18000da95  pop     rdi
0x18000da96  pop     rsi
0x18000da97  pop     rbx
0x18000da98  pop     rbp
0x18000da99  retn
```
