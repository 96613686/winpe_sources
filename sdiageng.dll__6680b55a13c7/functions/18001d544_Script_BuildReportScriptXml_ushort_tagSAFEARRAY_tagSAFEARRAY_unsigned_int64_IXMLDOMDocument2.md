# Script::BuildReportScriptXml(ushort *,tagSAFEARRAY *,tagSAFEARRAY *,unsigned __int64,IXMLDOMDocument2 * *)

- ea: `0x18001d544`
- end: `0x18001dabd`
- name: `?BuildReportScriptXml@Script@@AEAAJPEAGPEAUtagSAFEARRAY@@1_KPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1401`
- prototype: `__int64 __fastcall(Script *this, unsigned __int16 *, struct tagSAFEARRAY *, struct tagSAFEARRAY *, unsigned __int64, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18001e194`

## callees

- `0x1800012a4`
- `0x180002978`
- `0x180005ffc`
- `0x18001d544`
- `0x180026fa0`
- `0x18002708c`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d842`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d85b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da71`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d842`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d85b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da71`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001d893`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001d8be`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001d893`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001d8be`

## string_xrefs

- `0x18001d5fe`: `<?xml version="1.0" encoding="utf-8"?><Script/>`
- `0x18001d5d3`: `Script::BuildReportScriptXml`
- `0x18001d619`: `Script::BuildReportScriptXml`
- `0x18001d683`: `Script::BuildReportScriptXml`
- `0x18001d6ec`: `Script::BuildReportScriptXml`
- `0x18001d74f`: `Script::BuildReportScriptXml`
- `0x18001d98d`: `Script::BuildReportScriptXml`

## pseudocode

```c
__int64 __fastcall Script::BuildReportScriptXml(
        Script *this,
        unsigned __int16 *a2,
        struct tagSAFEARRAY *a3,
        struct tagSAFEARRAY *a4,
        unsigned __int64 a5,
        struct IXMLDOMDocument2 **a6)
{
  struct IXMLDOMElement *v8; // r14
  struct IXMLDOMElement *v9; // r15
  void *v10; // r12
  int v11; // r8d
  unsigned int v12; // ebx
  int FullPath; // eax
  int v14; // r8d
  struct IXMLDOMDocument2 *v15; // rsi
  int v16; // eax
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  int v20; // r8d
  int String; // eax
  ULONG cElements; // eax
  HRESULT Element; // eax
  HRESULT v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  struct IXMLDOMDocument2 *v28; // r8
  int v29; // eax
  LONG rgIndices; // [rsp+30h] [rbp-D0h] BYREF
  struct IXMLDOMElement *v32; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  BSTR pv; // [rsp+48h] [rbp-B8h] BYREF
  struct IXMLDOMDocument2 *v35; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMElement *v36; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v38; // [rsp+68h] [rbp-98h] BYREF
  SAFEARRAY *psa; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v40; // [rsp+78h] [rbp-88h] BYREF
  Script *v41; // [rsp+80h] [rbp-80h]
  struct IXMLDOMDocument2 **v42; // [rsp+88h] [rbp-78h]
  unsigned __int16 v43[1024]; // [rsp+90h] [rbp-70h] BYREF

  psa = a4;
  v41 = this;
  v42 = a6;
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v32 = 0;
  v10 = 0;
  v36 = 0;
  bstrString = 0;
  pv = 0;
  Block = 0;
  v40 = 0;
  v38 = 0;
  rgIndices = 0;
  if ( !a2 )
  {
    v11 = 727;
LABEL_3:
    v12 = -2147024809;
    SdpDebugTrace(1u, L"Script::BuildReportScriptXml", v11, -2147024809);
    goto LABEL_71;
  }
  if ( !a6 )
  {
    v11 = 728;
    goto LABEL_3;
  }
  FullPath = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Script/>", &v35);
  v12 = FullPath;
  if ( FullPath >= 0 )
  {
    FullPath = SdpGetFullPath(a2, &v40, &v38);
    v12 = FullPath;
    if ( FullPath < 0 )
    {
      v14 = 740;
      goto LABEL_8;
    }
    v15 = v35;
    v16 = SdpXmlSetAttribute(v35, 0, L"name", v38);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 746;
LABEL_13:
      v18 = v16;
LABEL_14:
      SdpDebugTrace(1u, L"Script::BuildReportScriptXml", v17, v18);
      goto LABEL_65;
    }
    v16 = StringCchPrintfW(v43, 0x400u, L"%I64u", a5);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 753;
      goto LABEL_13;
    }
    v19 = SdpXmlCreateNode(v15, 0, L"Data", v43, &v32);
    v12 = v19;
    if ( v19 < 0 )
    {
      v20 = 760;
LABEL_19:
      SdpDebugTrace(1u, L"Script::BuildReportScriptXml", v20, v19);
      v8 = v32;
      goto LABEL_65;
    }
    v8 = v32;
    v16 = SdpXmlSetAttribute(0, v32, L"id", L"RunningTime");
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 766;
      goto LABEL_13;
    }
    String = SdpLoadString(0, 0x6Au, (unsigned __int16 **)&Block);
    v12 = String;
    if ( String < 0 )
    {
      SdpDebugTrace(1u, L"Script::BuildReportScriptXml", 769, String);
      v10 = Block;
      goto LABEL_65;
    }
    v10 = Block;
    v16 = SdpXmlSetAttribute(0, v8, L"name", (const unsigned __int16 *)Block);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 772;
      goto LABEL_13;
    }
    if ( v8 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v8->lpVtbl->Release)(v8);
      v32 = 0;
    }
    if ( v10 )
    {
      operator delete(v10);
      v10 = 0;
    }
    v19 = SdpXmlCreateNode(v15, 0, L"Parameters", 0, &v32);
    v12 = v19;
    if ( v19 < 0 )
    {
      v20 = 786;
      goto LABEL_19;
    }
    v8 = v32;
    if ( a3 )
    {
      if ( a3->cDims > 1u
        || psa->cDims > 1u
        || (cElements = a3->rgsabound[0].cElements, cElements != psa->rgsabound[0].cElements) )
      {
        v18 = -2147024809;
        v17 = 794;
LABEL_61:
        v12 = v18;
        goto LABEL_14;
      }
      rgIndices = 0;
      if ( cElements )
      {
        while ( 1 )
        {
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( pv )
          {
            SysFreeString(pv);
            pv = 0;
          }
          if ( v9 )
          {
            ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
            v9 = 0;
            v36 = 0;
          }
          Element = SafeArrayGetElement(a3, &rgIndices, &bstrString);
          v12 = Element;
          if ( Element < 0 )
            break;
          if ( !bstrString )
          {
            v18 = -2147467261;
            v17 = 808;
            goto LABEL_61;
          }
          v24 = SafeArrayGetElement(psa, &rgIndices, &pv);
          v12 = v24;
          if ( v24 < 0 )
          {
            v18 = v24;
            v17 = 811;
            goto LABEL_14;
          }
          if ( !pv )
          {
            v18 = -2147467261;
            v17 = 812;
            goto LABEL_61;
          }
          v25 = SdpXmlCreateNode(v15, v8, L"Data", pv, &v36);
          v12 = v25;
          if ( v25 < 0 )
          {
            SdpDebugTrace(1u, L"Script::BuildReportScriptXml", 819, v25);
            v9 = v36;
            goto LABEL_65;
          }
          v9 = v36;
          v26 = SdpXmlSetAttribute(0, v36, L"id", L"Parameter");
          v12 = v26;
          if ( v26 < 0 )
          {
            v18 = v26;
            v17 = 825;
            goto LABEL_14;
          }
          v27 = SdpXmlSetAttribute(0, v9, L"name", bstrString);
          v12 = v27;
          if ( v27 < 0 )
          {
            v18 = v27;
            v17 = 831;
            goto LABEL_14;
          }
          if ( ++rgIndices >= a3->rgsabound[0].cElements )
            goto LABEL_51;
        }
        v18 = Element;
        v17 = 807;
        goto LABEL_14;
      }
    }
LABEL_51:
    v28 = (struct IXMLDOMDocument2 *)*((_QWORD *)v41 + 6);
    if ( v28 )
    {
      v29 = SdpXmlAppend(v15, 0, v28);
      v12 = v29;
      if ( v29 >= 0 )
      {
        *v42 = v15;
        v15 = 0;
        goto LABEL_65;
      }
      v18 = v29;
      v17 = 841;
      goto LABEL_14;
    }
    v18 = -2147467261;
    v17 = 839;
    goto LABEL_61;
  }
  v14 = 737;
LABEL_8:
  SdpDebugTrace(1u, L"Script::BuildReportScriptXml", v14, FullPath);
  v15 = v35;
LABEL_65:
  if ( v15 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v15->lpVtbl->Release)(v15);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v8->lpVtbl->Release)(v8);
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v9->lpVtbl->Release)(v9);
LABEL_71:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( pv )
  {
    SysFreeString(pv);
    pv = 0;
  }
  if ( v10 )
    operator delete(v10);
  if ( v40 )
    operator delete(v40);
  return v12;
}

```

## disassembly

```asm
0x18001d544  push    rbp
0x18001d546  push    rbx
0x18001d547  push    rsi
0x18001d548  push    rdi
0x18001d549  push    r12
0x18001d54b  push    r13
0x18001d54d  push    r14
0x18001d54f  push    r15
0x18001d551  lea     rbp, [rsp-7A8h]
0x18001d559  sub     rsp, 8A8h
0x18001d560  mov     rax, cs:__security_cookie
0x18001d567  xor     rax, rsp
0x18001d56a  mov     [rbp+7E0h+var_50], rax
0x18001d571  mov     rax, [rbp+7E0h+arg_28]
0x18001d578  xor     esi, esi
0x18001d57a  mov     [rsp+8E0h+psa], r9
0x18001d57f  mov     r13, r8
0x18001d582  mov     [rbp+7E0h+var_860], rcx
0x18001d586  mov     rdi, rdx
0x18001d589  mov     [rbp+7E0h+var_858], rax
0x18001d58d  mov     r14d, esi
0x18001d590  mov     [rsp+8E0h+var_890], rsi
0x18001d595  mov     r15d, esi
0x18001d598  mov     [rsp+8E0h+var_8A8], rsi
0x18001d59d  mov     r12d, esi
0x18001d5a0  mov     [rsp+8E0h+var_888], rsi
0x18001d5a5  mov     [rsp+8E0h+bstrString], rsi
0x18001d5aa  mov     [rsp+8E0h+pv], rsi
0x18001d5af  mov     [rsp+8E0h+Block], rsi
0x18001d5b4  mov     [rsp+8E0h+var_868], rsi
0x18001d5b9  mov     [rsp+8E0h+var_878], rsi
0x18001d5be  mov     [rsp+8E0h+rgIndices], esi
0x18001d5c2  test    rdx, rdx
0x18001d5c5  jnz     short loc_18001D5EC
0x18001d5c7  mov     r8d, 2D7h; int
0x18001d5cd  mov     r9d, 80070057h; int
0x18001d5d3  lea     rdx, aScriptBuildrep; "Script::BuildReportScriptXml"
0x18001d5da  mov     ecx, 1; Level
0x18001d5df  mov     ebx, r9d
0x18001d5e2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d5e7  jmp     loc_18001DA52
0x18001d5ec  test    rax, rax
0x18001d5ef  jnz     short loc_18001D5F9
0x18001d5f1  mov     r8d, 2D8h
0x18001d5f7  jmp     short loc_18001D5CD
0x18001d5f9  lea     rdx, [rsp+8E0h+var_890]; struct IXMLDOMDocument2 **
0x18001d5fe  lea     rcx, aXmlVersion10En_17; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001d605  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001d60a  mov     ebx, eax
0x18001d60c  test    eax, eax
0x18001d60e  jns     short loc_18001D634
0x18001d610  mov     r8d, 2E1h; int
0x18001d616  mov     r9d, eax; int
0x18001d619  lea     rdx, aScriptBuildrep; "Script::BuildReportScriptXml"
0x18001d620  mov     ecx, 1; Level
0x18001d625  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d62a  mov     rsi, [rsp+8E0h+var_890]
0x18001d62f  jmp     loc_18001DA14
0x18001d634  lea     r8, [rsp+8E0h+var_878]; unsigned __int16 **
0x18001d639  mov     rcx, rdi; unsigned __int16 *
0x18001d63c  lea     rdx, [rsp+8E0h+var_868]; unsigned __int16 **
0x18001d641  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x18001d646  mov     ebx, eax
0x18001d648  test    eax, eax
0x18001d64a  jns     short loc_18001D654
0x18001d64c  mov     r8d, 2E4h
0x18001d652  jmp     short loc_18001D616
0x18001d654  mov     rsi, [rsp+8E0h+var_890]
0x18001d659  lea     r8, aName_0; "name"
0x18001d660  mov     r9, [rsp+8E0h+var_878]; unsigned __int16 *
0x18001d665  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18001d668  xor     edx, edx; struct IXMLDOMElement *
0x18001d66a  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001d66f  mov     ebx, eax
0x18001d671  test    eax, eax
0x18001d673  jns     short loc_18001D694
0x18001d675  mov     r8d, 2EAh; int
0x18001d67b  mov     r9d, eax; int
0x18001d67e  mov     ecx, 1; Level
0x18001d683  lea     rdx, aScriptBuildrep; "Script::BuildReportScriptXml"
0x18001d68a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d68f  jmp     loc_18001DA14
0x18001d694  mov     r9, [rbp+7E0h+arg_20]
0x18001d69b  lea     r8, aI64u; "%I64u"
0x18001d6a2  mov     edx, 400h; unsigned __int64
0x18001d6a7  lea     rcx, [rbp+7E0h+var_850]; unsigned __int16 *
0x18001d6ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d6b0  mov     ebx, eax
0x18001d6b2  test    eax, eax
0x18001d6b4  jns     short loc_18001D6BE
0x18001d6b6  mov     r8d, 2F1h
0x18001d6bc  jmp     short loc_18001D67B
0x18001d6be  lea     rax, [rsp+8E0h+var_8A8]
0x18001d6c3  xor     edx, edx; struct IXMLDOMElement *
0x18001d6c5  lea     r9, [rbp+7E0h+var_850]; unsigned __int16 *
0x18001d6c9  mov     [rsp+8E0h+var_8C0], rax; struct IXMLDOMElement **
0x18001d6ce  lea     r8, aData; "Data"
0x18001d6d5  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18001d6d8  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d6dd  mov     ebx, eax
0x18001d6df  test    eax, eax
0x18001d6e1  jns     short loc_18001D707
0x18001d6e3  mov     r8d, 2F8h; int
0x18001d6e9  mov     r9d, eax; int
0x18001d6ec  lea     rdx, aScriptBuildrep; "Script::BuildReportScriptXml"
0x18001d6f3  mov     ecx, 1; Level
0x18001d6f8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d6fd  mov     r14, [rsp+8E0h+var_8A8]
0x18001d702  jmp     loc_18001DA14
0x18001d707  mov     r14, [rsp+8E0h+var_8A8]
0x18001d70c  lea     r9, aRunningtime; "RunningTime"
0x18001d713  mov     rdx, r14; struct IXMLDOMElement *
0x18001d716  lea     r8, aId_0; "id"
0x18001d71d  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001d71f  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001d724  mov     ebx, eax
0x18001d726  test    eax, eax
0x18001d728  jns     short loc_18001D735
0x18001d72a  mov     r8d, 2FEh
0x18001d730  jmp     loc_18001D67B
0x18001d735  lea     r8, [rsp+8E0h+Block]; unsigned __int16 **
0x18001d73a  mov     edx, 6Ah ; 'j'; unsigned int
0x18001d73f  xor     ecx, ecx; unsigned __int16 *
0x18001d741  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18001d746  mov     ebx, eax
0x18001d748  test    eax, eax
0x18001d74a  jns     short loc_18001D770
0x18001d74c  mov     r9d, eax; int
0x18001d74f  lea     rdx, aScriptBuildrep; "Script::BuildReportScriptXml"
0x18001d756  mov     r8d, 301h; int
0x18001d75c  mov     ecx, 1; Level
0x18001d761  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d766  mov     r12, [rsp+8E0h+Block]
0x18001d76b  jmp     loc_18001DA14
0x18001d770  mov     r12, [rsp+8E0h+Block]
0x18001d775  lea     r8, aName_0; "name"
0x18001d77c  mov     r9, r12; unsigned __int16 *
0x18001d77f  mov     rdx, r14; struct IXMLDOMElement *
0x18001d782  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001d784  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001d789  mov     ebx, eax
0x18001d78b  test    eax, eax
0x18001d78d  jns     short loc_18001D79A
0x18001d78f  mov     r8d, 304h
0x18001d795  jmp     loc_18001D67B
0x18001d79a  test    r14, r14
0x18001d79d  jz      short loc_18001D7B3
0x18001d79f  mov     rax, [r14]
0x18001d7a2  mov     rcx, r14
0x18001d7a5  mov     rax, [rax+10h]
0x18001d7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ae  mov     [rsp+8E0h+var_8A8], r15
0x18001d7b3  test    r12, r12
0x18001d7b6  jz      short loc_18001D7C3
0x18001d7b8  mov     rcx, r12; Block
0x18001d7bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d7c0  xor     r12d, r12d
0x18001d7c3  lea     rax, [rsp+8E0h+var_8A8]
0x18001d7c8  xor     r9d, r9d; unsigned __int16 *
0x18001d7cb  lea     r8, aParameters; "Parameters"
0x18001d7d2  mov     [rsp+8E0h+var_8C0], rax; struct IXMLDOMElement **
0x18001d7d7  xor     edx, edx; struct IXMLDOMElement *
0x18001d7d9  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18001d7dc  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d7e1  mov     ebx, eax
0x18001d7e3  test    eax, eax
0x18001d7e5  jns     short loc_18001D7F2
0x18001d7e7  mov     r8d, 312h
0x18001d7ed  jmp     loc_18001D6E9
0x18001d7f2  mov     r14, [rsp+8E0h+var_8A8]
0x18001d7f7  mov     edi, 1
0x18001d7fc  test    r13, r13
0x18001d7ff  jz      loc_18001D955
0x18001d805  cmp     [r13+0], di
0x18001d80a  ja      loc_18001D9DA
0x18001d810  mov     rcx, [rsp+8E0h+psa]
0x18001d815  cmp     [rcx], di
0x18001d818  ja      loc_18001D9DA
0x18001d81e  mov     eax, [r13+18h]
0x18001d822  cmp     eax, [rcx+18h]
0x18001d825  jnz     loc_18001D9DA
0x18001d82b  mov     [rsp+8E0h+rgIndices], r15d
0x18001d830  test    eax, eax
0x18001d832  jz      loc_18001D955
0x18001d838  mov     rcx, [rsp+8E0h+bstrString]; bstrString
0x18001d83d  test    rcx, rcx
0x18001d840  jz      short loc_18001D851
0x18001d842  call    cs:__imp_SysFreeString
0x18001d848  mov     [rsp+8E0h+bstrString], 0
0x18001d851  mov     rcx, [rsp+8E0h+pv]; bstrString
0x18001d856  test    rcx, rcx
0x18001d859  jz      short loc_18001D86A
0x18001d85b  call    cs:__imp_SysFreeString
0x18001d861  mov     [rsp+8E0h+pv], 0
0x18001d86a  test    r15, r15
0x18001d86d  jz      short loc_18001D886
0x18001d86f  mov     rax, [r15]
0x18001d872  mov     rcx, r15
0x18001d875  mov     rax, [rax+10h]
0x18001d879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d87e  xor     r15d, r15d
0x18001d881  mov     [rsp+8E0h+var_888], r15
0x18001d886  lea     r8, [rsp+8E0h+bstrString]; pv
0x18001d88b  mov     rcx, r13; psa
0x18001d88e  lea     rdx, [rsp+8E0h+rgIndices]; rgIndices
0x18001d893  call    cs:__imp_SafeArrayGetElement
0x18001d899  mov     ebx, eax
0x18001d89b  test    eax, eax
0x18001d89d  js      loc_18001D9CF
0x18001d8a3  cmp     [rsp+8E0h+bstrString], 0
0x18001d8a9  jz      loc_18001D9C1
0x18001d8af  mov     rcx, [rsp+8E0h+psa]; psa
0x18001d8b4  lea     r8, [rsp+8E0h+pv]; pv
0x18001d8b9  lea     rdx, [rsp+8E0h+rgIndices]; rgIndices
0x18001d8be  call    cs:__imp_SafeArrayGetElement
0x18001d8c4  mov     ebx, eax
0x18001d8c6  test    eax, eax
0x18001d8c8  js      loc_18001D9B6
0x18001d8ce  mov     r9, [rsp+8E0h+pv]; unsigned __int16 *
0x18001d8d3  test    r9, r9
0x18001d8d6  jz      loc_18001D9A8
0x18001d8dc  lea     rax, [rsp+8E0h+var_888]
0x18001d8e1  mov     rdx, r14; struct IXMLDOMElement *
0x18001d8e4  lea     r8, aData; "Data"
0x18001d8eb  mov     [rsp+8E0h+var_8C0], rax; struct IXMLDOMElement **
0x18001d8f0  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18001d8f3  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001d8f8  mov     ebx, eax
0x18001d8fa  test    eax, eax
0x18001d8fc  js      loc_18001D98A
0x18001d902  mov     r15, [rsp+8E0h+var_888]
0x18001d907  lea     r9, aParameter; "Parameter"
0x18001d90e  mov     rdx, r15; struct IXMLDOMElement *
0x18001d911  lea     r8, aId_0; "id"
0x18001d918  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001d91a  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001d91f  mov     ebx, eax
0x18001d921  test    eax, eax
0x18001d923  js      short loc_18001D97F
0x18001d925  mov     r9, [rsp+8E0h+bstrString]; unsigned __int16 *
0x18001d92a  lea     r8, aName_0; "name"
0x18001d931  mov     rdx, r15; struct IXMLDOMElement *
0x18001d934  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001d936  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001d93b  mov     ebx, eax
0x18001d93d  test    eax, eax
0x18001d93f  js      short loc_18001D974
0x18001d941  mov     eax, [rsp+8E0h+rgIndices]
0x18001d945  add     eax, edi
0x18001d947  mov     [rsp+8E0h+rgIndices], eax
0x18001d94b  cmp     eax, [r13+18h]
0x18001d94f  jb      loc_18001D838
0x18001d955  mov     r8, [rbp+7E0h+var_860]
0x18001d959  mov     r8, [r8+30h]; struct IXMLDOMDocument2 *
0x18001d95d  test    r8, r8
0x18001d960  jnz     loc_18001D9F0
0x18001d966  mov     r9d, 80004003h
0x18001d96c  mov     r8d, 347h
0x18001d972  jmp     short loc_18001D9E6
0x18001d974  mov     r9d, eax
0x18001d977  mov     r8d, 33Fh
0x18001d97d  jmp     short loc_18001D9E9
0x18001d97f  mov     r9d, eax
0x18001d982  mov     r8d, 339h
0x18001d988  jmp     short loc_18001D9E9
0x18001d98a  mov     r9d, eax; int
0x18001d98d  lea     rdx, aScriptBuildrep; "Script::BuildReportScriptXml"
0x18001d994  mov     r8d, 333h; int
0x18001d99a  mov     ecx, edi; Level
0x18001d99c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d9a1  mov     r15, [rsp+8E0h+var_888]
0x18001d9a6  jmp     short loc_18001DA14
0x18001d9a8  mov     r9d, 80004003h
0x18001d9ae  mov     r8d, 32Ch
0x18001d9b4  jmp     short loc_18001D9E6
0x18001d9b6  mov     r9d, eax
0x18001d9b9  mov     r8d, 32Bh
0x18001d9bf  jmp     short loc_18001D9E9
0x18001d9c1  mov     r9d, 80004003h
0x18001d9c7  mov     r8d, 328h
0x18001d9cd  jmp     short loc_18001D9E6
0x18001d9cf  mov     r9d, eax
0x18001d9d2  mov     r8d, 327h
0x18001d9d8  jmp     short loc_18001D9E9
0x18001d9da  mov     r9d, 80070057h
0x18001d9e0  mov     r8d, 31Ah
0x18001d9e6  mov     ebx, r9d
0x18001d9e9  mov     ecx, edi
0x18001d9eb  jmp     loc_18001D683
0x18001d9f0  xor     edx, edx; struct IXMLDOMElement *
0x18001d9f2  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18001d9f5  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001d9fa  mov     ebx, eax
0x18001d9fc  test    eax, eax
0x18001d9fe  jns     short loc_18001DA0B
0x18001da00  mov     r9d, eax
0x18001da03  mov     r8d, 349h
0x18001da09  jmp     short loc_18001D9E9
0x18001da0b  mov     rax, [rbp+7E0h+var_858]
0x18001da0f  mov     [rax], rsi
  ... truncated ...
```
