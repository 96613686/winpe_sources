# CNotification::SchdpInitializeParameter(IXMLDOMNode *,long)

- ea: `0x180003100`
- end: `0x18000337e`
- name: `?SchdpInitializeParameter@CNotification@@AEAAJPEAUIXMLDOMNode@@J@Z`
- size: `638`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180003384`

## callees

- `0x180003100`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000333c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003356`
- `OLEAUT32!__imp_SysFreeString` at `0x18000333c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003356`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000320f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800032c6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18000320f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800032c6`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpInitializeParameter(struct IXMLDOMNode *this, struct IXMLDOMNode *a2, int a3)
{
  struct IXMLDOMNode *v3; // rsi
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v7; // r14
  unsigned int v8; // ebx
  int v9; // r9d
  int v10; // r8d
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  HRESULT v14; // eax
  SAFEARRAY *lpVtbl; // rcx
  int v16; // eax
  SAFEARRAY *v17; // rcx
  struct IXMLDOMNode *v19; // [rsp+20h] [rbp-30h] BYREF
  LONG rgIndices; // [rsp+28h] [rbp-28h] BYREF
  int v21; // [rsp+2Ch] [rbp-24h]
  void *pv; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v24; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+98h] [rbp+48h] BYREF

  v25 = 0;
  v24 = 0;
  v3 = 0;
  pv = 0;
  bstrString = 0;
  v19 = 0;
  ChildNodes = SdpXmlGetChildNodes(this, a2, &v24, &v25);
  v7 = v24;
  v8 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    v11 = SdpXmlNextNode(v24, &v19);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 276;
LABEL_5:
      SdpDebugTrace(1u, L"CNotification::SchdpInitializeParameter", v12, v11);
      v3 = v19;
      goto LABEL_30;
    }
    v3 = v19;
    v13 = SdpXmlCheckNode(v19, L"Name");
    v8 = v13;
    if ( v13 < 0 )
    {
      v9 = v13;
LABEL_28:
      v10 = 277;
      goto LABEL_29;
    }
    if ( v13 == 1 || !v3 )
    {
      v9 = -2147467259;
      v8 = -2147467259;
      goto LABEL_28;
    }
    v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, void **))v3->lpVtbl->get_text)(v3, &pv);
    v8 = v14;
    if ( v14 >= 0 )
    {
      lpVtbl = (SAFEARRAY *)this[3].lpVtbl;
      rgIndices = 0;
      v21 = a3;
      v14 = SafeArrayPutElement(lpVtbl, &rgIndices, pv);
      v8 = v14;
      if ( v14 >= 0 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
        v19 = 0;
        v11 = SdpXmlNextNode(v7, &v19);
        v8 = v11;
        if ( v11 < 0 )
        {
          v12 = 291;
          goto LABEL_5;
        }
        v3 = v19;
        v16 = SdpXmlCheckNode(v19, L"Value");
        v8 = v16;
        if ( v16 >= 0 )
        {
          if ( v16 != 1 && v3 )
          {
            v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v3->lpVtbl->get_text)(v3, &bstrString);
            v8 = v14;
            if ( v14 >= 0 )
            {
              v17 = (SAFEARRAY *)this[3].lpVtbl;
              rgIndices = 1;
              v21 = a3;
              v14 = SafeArrayPutElement(v17, &rgIndices, bstrString);
              v8 = v14;
              if ( v14 >= 0 )
                goto LABEL_30;
              v10 = 305;
            }
            else
            {
              v10 = 299;
            }
            goto LABEL_12;
          }
          v9 = -2147467259;
          v8 = -2147467259;
        }
        else
        {
          v9 = v16;
        }
        v10 = 292;
        goto LABEL_29;
      }
      v10 = 286;
    }
    else
    {
      v10 = 280;
    }
LABEL_12:
    v9 = v14;
    goto LABEL_29;
  }
  v9 = ChildNodes;
  v10 = 272;
LABEL_29:
  SdpDebugTrace(1u, L"CNotification::SchdpInitializeParameter", v10, v9);
LABEL_30:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  if ( pv )
  {
    SysFreeString((BSTR)pv);
    pv = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v8;
}

```

## disassembly

```asm
0x180003100  mov     [rsp-28h+arg_0], rbx
0x180003105  mov     [rsp-28h+arg_8], rsi
0x18000310a  push    rbp
0x18000310b  push    rdi
0x18000310c  push    r13
0x18000310e  push    r14
0x180003110  push    r15
0x180003112  mov     rbp, rsp
0x180003115  sub     rsp, 50h
0x180003119  and     [rbp+arg_18], 0
0x18000311d  lea     r9, [rbp+arg_18]; unsigned int *
0x180003121  and     [rbp+var_10], 0
0x180003126  xor     esi, esi
0x180003128  and     [rbp+pv], rsi
0x18000312c  mov     r15d, r8d
0x18000312f  and     [rbp+bstrString], rsi
0x180003133  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x180003137  mov     [rbp+var_30], rsi
0x18000313b  mov     r13, rcx
0x18000313e  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180003143  mov     r14, [rbp+var_10]
0x180003147  mov     ebx, eax
0x180003149  test    eax, eax
0x18000314b  jns     short loc_18000315E
0x18000314d  mov     r9d, eax
0x180003150  lea     ecx, [rsi+1]
0x180003153  mov     r8d, 110h
0x180003159  jmp     loc_1800032FF
0x18000315e  lea     rdx, [rbp+var_30]; struct IXMLDOMNode **
0x180003162  mov     rcx, r14; struct IXMLDOMNodeList *
0x180003165  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18000316a  mov     ebx, eax
0x18000316c  test    eax, eax
0x18000316e  jns     short loc_180003193
0x180003170  mov     r8d, 114h; int
0x180003176  mov     ecx, 1; Level
0x18000317b  lea     rdx, aCnotificationS_0; "CNotification::SchdpInitializeParameter"
0x180003182  mov     r9d, eax; int
0x180003185  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000318a  mov     rsi, [rbp+var_30]
0x18000318e  jmp     loc_18000330B
0x180003193  mov     rsi, [rbp+var_30]
0x180003197  lea     rdx, aName; "Name"
0x18000319e  mov     rcx, rsi; struct IXMLDOMNode *
0x1800031a1  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800031a6  mov     ebx, eax
0x1800031a8  test    eax, eax
0x1800031aa  jns     short loc_1800031B9
0x1800031ac  mov     r9d, eax
0x1800031af  mov     ecx, 1
0x1800031b4  jmp     loc_1800032F9
0x1800031b9  mov     edi, 1
0x1800031be  cmp     eax, edi
0x1800031c0  jz      loc_1800032EE
0x1800031c6  test    rsi, rsi
0x1800031c9  jz      loc_1800032EE
0x1800031cf  mov     rax, [rsi]
0x1800031d2  lea     rdx, [rbp+pv]
0x1800031d6  mov     rcx, rsi
0x1800031d9  mov     rax, [rax+0D0h]
0x1800031e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e5  mov     ebx, eax
0x1800031e7  test    eax, eax
0x1800031e9  jns     short loc_1800031FB
0x1800031eb  mov     r8d, 118h
0x1800031f1  mov     r9d, eax
0x1800031f4  mov     ecx, edi
0x1800031f6  jmp     loc_1800032FF
0x1800031fb  mov     r8, [rbp+pv]; pv
0x1800031ff  lea     rdx, [rbp+rgIndices]; rgIndices
0x180003203  mov     rcx, [r13+18h]; psa
0x180003207  and     [rbp+rgIndices], 0
0x18000320b  mov     [rbp+var_24], r15d
0x18000320f  call    cs:__imp_SafeArrayPutElement
0x180003216  nop     dword ptr [rax+rax+00h]
0x18000321b  mov     ebx, eax
0x18000321d  test    eax, eax
0x18000321f  jns     short loc_180003229
0x180003221  mov     r8d, 11Eh
0x180003227  jmp     short loc_1800031F1
0x180003229  mov     rax, [rsi]
0x18000322c  mov     rcx, rsi
0x18000322f  mov     rax, [rax+10h]
0x180003233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003238  and     [rbp+var_30], 0
0x18000323d  lea     rdx, [rbp+var_30]; struct IXMLDOMNode **
0x180003241  mov     rcx, r14; struct IXMLDOMNodeList *
0x180003244  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003249  mov     ebx, eax
0x18000324b  test    eax, eax
0x18000324d  jns     short loc_18000325C
0x18000324f  mov     r8d, 123h
0x180003255  mov     ecx, edi
0x180003257  jmp     loc_18000317B
0x18000325c  mov     rsi, [rbp+var_30]
0x180003260  lea     rdx, aValue; "Value"
0x180003267  mov     rcx, rsi; struct IXMLDOMNode *
0x18000326a  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18000326f  mov     ebx, eax
0x180003271  test    eax, eax
0x180003273  jns     short loc_180003283
0x180003275  mov     r9d, eax
0x180003278  mov     r8d, 124h
0x18000327e  jmp     loc_1800031F4
0x180003283  cmp     eax, edi
0x180003285  jz      short loc_1800032E3
0x180003287  test    rsi, rsi
0x18000328a  jz      short loc_1800032E3
0x18000328c  mov     rax, [rsi]
0x18000328f  lea     rdx, [rbp+bstrString]
0x180003293  mov     rcx, rsi
0x180003296  mov     rax, [rax+0D0h]
0x18000329d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a2  mov     ebx, eax
0x1800032a4  test    eax, eax
0x1800032a6  jns     short loc_1800032B3
0x1800032a8  mov     r8d, 12Bh
0x1800032ae  jmp     loc_1800031F1
0x1800032b3  mov     r8, [rbp+bstrString]; pv
0x1800032b7  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800032bb  mov     rcx, [r13+18h]; psa
0x1800032bf  mov     [rbp+rgIndices], edi
0x1800032c2  mov     [rbp+var_24], r15d
0x1800032c6  call    cs:__imp_SafeArrayPutElement
0x1800032cd  nop     dword ptr [rax+rax+00h]
0x1800032d2  mov     ebx, eax
0x1800032d4  test    eax, eax
0x1800032d6  jns     short loc_18000330B
0x1800032d8  mov     r8d, 131h
0x1800032de  jmp     loc_1800031F1
0x1800032e3  mov     r9d, 80004005h
0x1800032e9  mov     ebx, r9d
0x1800032ec  jmp     short loc_180003278
0x1800032ee  mov     r9d, 80004005h; int
0x1800032f4  mov     ecx, edi; Level
0x1800032f6  mov     ebx, r9d
0x1800032f9  mov     r8d, 115h; int
0x1800032ff  lea     rdx, aCnotificationS_0; "CNotification::SchdpInitializeParameter"
0x180003306  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000330b  test    r14, r14
0x18000330e  jz      short loc_18000331F
0x180003310  mov     rax, [r14]
0x180003313  mov     rcx, r14
0x180003316  mov     rax, [rax+10h]
0x18000331a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331f  test    rsi, rsi
0x180003322  jz      short loc_180003333
0x180003324  mov     rax, [rsi]
0x180003327  mov     rcx, rsi
0x18000332a  mov     rax, [rax+10h]
0x18000332e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003333  mov     rcx, [rbp+pv]; bstrString
0x180003337  test    rcx, rcx
0x18000333a  jz      short loc_18000334D
0x18000333c  call    cs:__imp_SysFreeString
0x180003343  nop     dword ptr [rax+rax+00h]
0x180003348  and     [rbp+pv], 0
0x18000334d  mov     rcx, [rbp+bstrString]; bstrString
0x180003351  test    rcx, rcx
0x180003354  jz      short loc_180003362
0x180003356  call    cs:__imp_SysFreeString
0x18000335d  nop     dword ptr [rax+rax+00h]
0x180003362  lea     r11, [rsp+50h+var_s0]
0x180003367  mov     eax, ebx
0x180003369  mov     rbx, [r11+30h]
0x18000336d  mov     rsi, [r11+38h]
0x180003371  mov     rsp, r11
0x180003374  pop     r15
0x180003376  pop     r14
0x180003378  pop     r13
0x18000337a  pop     rdi
0x18000337b  pop     rbp
0x18000337c  retn
```
