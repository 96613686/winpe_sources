# Interaction::ParseAnswerXml(IXMLDOMDocument2 *)

- ea: `0x180020648`
- end: `0x1800208ee`
- name: `?ParseAnswerXml@Interaction@@IEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(const wchar_t **this, struct IXMLDOMDocument2 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002021c`

## callees

- `0x180003410`
- `0x180020648`
- `0x180020c7c`
- `0x180026fa0`
- `0x180028038`
- `0x18002848c`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800207a7`
- `msvcrt!_wcsicmp` at `0x1800207a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002072e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800208d7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002072e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800208d7`

## string_xrefs

- `0x180020688`: `Interaction::ParseAnswerXml`
- `0x1800206e8`: `Interaction::ParseAnswerXml`
- `0x18002088d`: `Interaction::ParseAnswerXml`
- `0x180020833`: `SdpXmlDeleteNode`

## pseudocode

```c
__int64 __fastcall Interaction::ParseAnswerXml(
        const wchar_t **this,
        struct IXMLDOMDocument2 *a2,
        const unsigned __int16 *a3)
{
  struct IXMLDOMNode *v3; // rsi
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v11; // r12
  int v12; // r9d
  int v13; // r8d
  int v14; // r14d
  int v15; // eax
  int v16; // eax
  int Attribute; // eax
  int v18; // eax
  struct IXMLDOMNode v19; // rax
  int v20; // eax
  int v21; // r8d
  struct IXMLDOMNodeList *v23; // [rsp+20h] [rbp-10h] BYREF
  __int64 v24; // [rsp+78h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+50h] BYREF
  struct IXMLDOMNode *v26; // [rsp+88h] [rbp+58h] BYREF

  v3 = 0;
  v23 = 0;
  v26 = 0;
  bstrString = 0;
  LODWORD(v24) = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 916;
    v8 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Interaction::ParseAnswerXml", v7, v8);
    goto LABEL_42;
  }
  v9 = SdpCheckDocumentVersion(a2, L"Version", a3);
  v6 = v9;
  if ( v9 < 0 )
  {
    v8 = v9;
    v7 = 921;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(a2, 0, &v23, (unsigned int *)&v24);
  v11 = v23;
  v6 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v12 = ChildNodes;
    v13 = 924;
LABEL_8:
    SdpDebugTrace(1u, L"Interaction::ParseAnswerXml", v13, v12);
    goto LABEL_38;
  }
  v14 = 0;
  if ( !(_DWORD)v24 )
    goto LABEL_38;
  while ( 1 )
  {
    if ( v3 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
      v26 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    v15 = SdpXmlNextNode(v11, &v26);
    v6 = v15;
    if ( v15 < 0 )
    {
      SdpDebugTrace(1u, L"Interaction::ParseAnswerXml", 931, v15);
      v3 = v26;
      goto LABEL_38;
    }
    v3 = v26;
    v16 = SdpXmlCheckNode(v26, L"Interaction");
    v6 = v16;
    if ( v16 < 0 )
    {
      v12 = v16;
      goto LABEL_36;
    }
    if ( v16 == 1 || !v3 )
    {
      v6 = -2147467259;
      v12 = -2147467259;
LABEL_36:
      v13 = 932;
      goto LABEL_8;
    }
    Attribute = SdpXmlGetAttribute(0, v3, L"ID", &bstrString);
    v6 = Attribute;
    if ( Attribute < 0 )
    {
      v12 = Attribute;
      v13 = 935;
      goto LABEL_8;
    }
    if ( !_wcsicmp(this[2], bstrString) )
      break;
    if ( ++v14 >= (unsigned int)v24 )
      goto LABEL_38;
  }
  v18 = Interaction::SaveAnswers((Interaction *)this, v3);
  v6 = v18;
  if ( v18 < 0 )
  {
    v12 = v18;
    v13 = 939;
    goto LABEL_8;
  }
  v19.lpVtbl = v3->lpVtbl;
  v24 = 0;
  v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v19.lpVtbl->get_parentNode)(v3, &v24);
  v6 = v20;
  if ( v20 < 0 )
  {
    v21 = 1622;
    goto LABEL_28;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode *, _QWORD))(*(_QWORD *)v24 + 160LL))(v24, v3, 0);
  v6 = v20;
  if ( v20 < 0 )
  {
    v21 = 1625;
LABEL_28:
    SdpDebugTrace(1u, L"SdpXmlDeleteNode", v21, v20);
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v6 < 0 )
  {
    v12 = v6;
    v13 = 942;
    goto LABEL_8;
  }
LABEL_38:
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v11->lpVtbl->Release)(v11);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
LABEL_42:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020648  push    rbp
0x18002064a  push    rbx
0x18002064b  push    rsi
0x18002064c  push    rdi
0x18002064d  push    r12
0x18002064f  push    r13
0x180020651  push    r14
0x180020653  mov     rbp, rsp
0x180020656  sub     rsp, 30h
0x18002065a  xor     esi, esi
0x18002065c  mov     [rbp+var_10], 0
0x180020664  mov     [rbp+arg_18], rsi
0x180020668  mov     rdi, rdx
0x18002066b  mov     [rbp+bstrString], rsi
0x18002066f  mov     r13, rcx
0x180020672  mov     dword ptr [rbp+arg_8], esi
0x180020675  test    rdx, rdx
0x180020678  jnz     short loc_18002069E
0x18002067a  mov     ebx, 80070057h
0x18002067f  mov     r8d, 394h; int
0x180020685  mov     r9d, ebx; int
0x180020688  lea     rdx, aInteractionPar; "Interaction::ParseAnswerXml"
0x18002068f  mov     ecx, 1; Level
0x180020694  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020699  jmp     loc_1800208CE
0x18002069e  lea     rdx, aVersion; "Version"
0x1800206a5  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x1800206a8  call    ?SdpCheckDocumentVersion@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; SdpCheckDocumentVersion(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x1800206ad  mov     ebx, eax
0x1800206af  test    eax, eax
0x1800206b1  jns     short loc_1800206BE
0x1800206b3  mov     r9d, eax
0x1800206b6  mov     r8d, 399h
0x1800206bc  jmp     short loc_180020688
0x1800206be  lea     r9, [rbp+arg_8]; unsigned int *
0x1800206c2  xor     edx, edx; struct IXMLDOMNode *
0x1800206c4  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x1800206c8  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x1800206cb  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x1800206d0  mov     r12, [rbp+var_10]
0x1800206d4  mov     ebx, eax
0x1800206d6  test    eax, eax
0x1800206d8  jns     short loc_1800206F9
0x1800206da  mov     r9d, eax; int
0x1800206dd  mov     r8d, 39Ch; int
0x1800206e3  mov     ecx, 1; Level
0x1800206e8  lea     rdx, aInteractionPar; "Interaction::ParseAnswerXml"
0x1800206ef  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800206f4  jmp     loc_1800208A5
0x1800206f9  xor     r14d, r14d
0x1800206fc  cmp     dword ptr [rbp+arg_8], esi
0x1800206ff  jbe     loc_1800208A5
0x180020705  lea     edi, [r14+1]
0x180020709  test    rsi, rsi
0x18002070c  jz      short loc_180020725
0x18002070e  mov     rax, [rsi]
0x180020711  mov     rcx, rsi
0x180020714  mov     rax, [rax+10h]
0x180020718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002071d  mov     [rbp+arg_18], 0
0x180020725  mov     rcx, [rbp+bstrString]; bstrString
0x180020729  test    rcx, rcx
0x18002072c  jz      short loc_18002073C
0x18002072e  call    cs:__imp_SysFreeString
0x180020734  mov     [rbp+bstrString], 0
0x18002073c  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180020740  mov     rcx, r12; struct IXMLDOMNodeList *
0x180020743  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180020748  mov     ebx, eax
0x18002074a  test    eax, eax
0x18002074c  js      loc_18002088A
0x180020752  mov     rsi, [rbp+arg_18]
0x180020756  lea     rdx, aInteraction; "Interaction"
0x18002075d  mov     rcx, rsi; struct IXMLDOMNode *
0x180020760  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180020765  mov     ebx, eax
0x180020767  test    eax, eax
0x180020769  js      loc_18002087A
0x18002076f  cmp     eax, edi
0x180020771  jz      loc_180020870
0x180020777  test    rsi, rsi
0x18002077a  jz      loc_180020870
0x180020780  lea     r9, [rbp+bstrString]; unsigned __int16 **
0x180020784  mov     rdx, rsi; struct IXMLDOMNode *
0x180020787  lea     r8, aId; "ID"
0x18002078e  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180020790  call    ?SdpXmlGetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBGPEAPEAG@Z; SdpXmlGetAttribute(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort * *)
0x180020795  mov     ebx, eax
0x180020797  test    eax, eax
0x180020799  js      loc_180020865
0x18002079f  mov     rdx, [rbp+bstrString]; String2
0x1800207a3  mov     rcx, [r13+10h]; String1
0x1800207a7  call    cs:__imp__wcsicmp
0x1800207ad  test    eax, eax
0x1800207af  jz      short loc_1800207C3
0x1800207b1  add     r14d, edi
0x1800207b4  cmp     r14d, dword ptr [rbp+arg_8]
0x1800207b8  jb      loc_180020709
0x1800207be  jmp     loc_1800208A5
0x1800207c3  mov     rdx, rsi; struct IXMLDOMNode *
0x1800207c6  mov     rcx, r13; this
0x1800207c9  call    ?SaveAnswers@Interaction@@IEAAJPEAUIXMLDOMNode@@@Z; Interaction::SaveAnswers(IXMLDOMNode *)
0x1800207ce  mov     ebx, eax
0x1800207d0  test    eax, eax
0x1800207d2  jns     short loc_1800207E2
0x1800207d4  mov     r9d, eax
0x1800207d7  mov     r8d, 3ABh
0x1800207dd  jmp     loc_180020883
0x1800207e2  mov     rax, [rsi]
0x1800207e5  lea     rdx, [rbp+arg_8]
0x1800207e9  mov     rcx, rsi
0x1800207ec  mov     [rbp+arg_8], 0
0x1800207f4  mov     rax, [rax+58h]
0x1800207f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207fd  mov     ebx, eax
0x1800207ff  test    eax, eax
0x180020801  jns     short loc_18002080B
0x180020803  mov     r8d, 656h
0x180020809  jmp     short loc_180020830
0x18002080b  mov     rcx, [rbp+arg_8]
0x18002080f  xor     r8d, r8d
0x180020812  mov     rdx, rsi
0x180020815  mov     rax, [rcx]
0x180020818  mov     rax, [rax+0A0h]
0x18002081f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020824  mov     ebx, eax
0x180020826  test    eax, eax
0x180020828  jns     short loc_180020841
0x18002082a  mov     r8d, 659h; int
0x180020830  mov     r9d, eax; int
0x180020833  lea     rdx, aSdpxmldeleteno; "SdpXmlDeleteNode"
0x18002083a  mov     ecx, edi; Level
0x18002083c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020841  mov     rcx, [rbp+arg_8]
0x180020845  test    rcx, rcx
0x180020848  jz      short loc_180020856
0x18002084a  mov     rax, [rcx]
0x18002084d  mov     rax, [rax+10h]
0x180020851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020856  test    ebx, ebx
0x180020858  jns     short loc_1800208A5
0x18002085a  mov     r9d, ebx
0x18002085d  mov     r8d, 3AEh
0x180020863  jmp     short loc_180020883
0x180020865  mov     r9d, eax
0x180020868  mov     r8d, 3A7h
0x18002086e  jmp     short loc_180020883
0x180020870  mov     ebx, 80004005h
0x180020875  mov     r9d, ebx
0x180020878  jmp     short loc_18002087D
0x18002087a  mov     r9d, eax
0x18002087d  mov     r8d, 3A4h
0x180020883  mov     ecx, edi
0x180020885  jmp     loc_1800206E8
0x18002088a  mov     r9d, eax; int
0x18002088d  lea     rdx, aInteractionPar; "Interaction::ParseAnswerXml"
0x180020894  mov     r8d, 3A3h; int
0x18002089a  mov     ecx, edi; Level
0x18002089c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800208a1  mov     rsi, [rbp+arg_18]
0x1800208a5  test    r12, r12
0x1800208a8  jz      short loc_1800208BA
0x1800208aa  mov     rax, [r12]
0x1800208ae  mov     rcx, r12
0x1800208b1  mov     rax, [rax+10h]
0x1800208b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ba  test    rsi, rsi
0x1800208bd  jz      short loc_1800208CE
0x1800208bf  mov     rax, [rsi]
0x1800208c2  mov     rcx, rsi
0x1800208c5  mov     rax, [rax+10h]
0x1800208c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ce  mov     rcx, [rbp+bstrString]; bstrString
0x1800208d2  test    rcx, rcx
0x1800208d5  jz      short loc_1800208DD
0x1800208d7  call    cs:__imp_SysFreeString
0x1800208dd  mov     eax, ebx
0x1800208df  add     rsp, 30h
0x1800208e3  pop     r14
0x1800208e5  pop     r13
0x1800208e7  pop     r12
0x1800208e9  pop     rdi
0x1800208ea  pop     rsi
0x1800208eb  pop     rbx
0x1800208ec  pop     rbp
0x1800208ed  retn
```
