# Rootcause::ParseRootcauseXml(IXMLDOMNode *)

- ea: `0x18001a530`
- end: `0x18001aa49`
- name: `?ParseRootcauseXml@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `1305`
- prototype: `__int64 __fastcall(struct Settings **this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180016148`

## callees

- `0x180003b2c`
- `0x1800040e8`
- `0x18000615c`
- `0x18001a0bc`
- `0x18001a36c`
- `0x18001a424`
- `0x18001a530`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x18001a977`: `ExtensionPoint`
- `0x18001a56a`: `Rootcause::ParseRootcauseXml`
- `0x18001a5fd`: `Rootcause::ParseRootcauseXml`
- `0x18001aa03`: `Rootcause::ParseRootcauseXml`

## pseudocode

```c
__int64 __fastcall Rootcause::ParseRootcauseXml(struct Settings **this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  int v4; // r9d
  int v5; // r8d
  unsigned int v6; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v8; // r12
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  unsigned int v15; // [rsp+68h] [rbp+48h] BYREF
  struct IXMLDOMNode *v16; // [rsp+70h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v17; // [rsp+78h] [rbp+58h] BYREF

  v2 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 940;
    v6 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::ParseRootcauseXml", v5, v4);
    return v6;
  }
  if ( !*this )
  {
    v6 = -2147467261;
    v5 = 941;
    v4 = -2147467261;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v17, &v15);
  v8 = v17;
  v6 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v9 = 944;
LABEL_8:
    v10 = ChildNodes;
LABEL_81:
    SdpDebugTrace(1u, L"Rootcause::ParseRootcauseXml", v9, v10);
    goto LABEL_82;
  }
  if ( v15 < 6 )
  {
    v10 = -2147024809;
    v9 = 948;
LABEL_80:
    v6 = v10;
    goto LABEL_81;
  }
  v11 = SdpXmlNextNode(v17, &v16);
  v6 = v11;
  if ( v11 >= 0 )
  {
    v2 = v16;
    ChildNodes = SdpXmlCheckNode(v16, L"ID");
    v6 = ChildNodes;
    if ( ChildNodes < 0 )
    {
      v9 = 957;
      goto LABEL_8;
    }
    if ( ChildNodes == 1 || !v2 )
    {
      v9 = 957;
      goto LABEL_79;
    }
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v2->lpVtbl->get_text)(v2, (char *)this + 40);
    v6 = v13;
    if ( v13 < 0 )
    {
      v9 = 960;
      goto LABEL_20;
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
    v16 = 0;
    v11 = SdpXmlNextNode(v8, &v16);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = 968;
      goto LABEL_13;
    }
    v2 = v16;
    v13 = SdpXmlCheckNode(v16, L"DisplayInformation");
    v6 = v13;
    if ( v13 < 0 )
    {
      v9 = 969;
      goto LABEL_20;
    }
    if ( v13 == 1 || !v2 )
    {
      v9 = 969;
      goto LABEL_79;
    }
    v13 = SdpParseDisplayInformation(v2, (struct _SDIAG_DISPINFO *)(this + 7));
    v6 = v13;
    if ( v13 < 0 )
    {
      v9 = 972;
      goto LABEL_20;
    }
    v13 = SdpLocalizeDisplayInformation(*this, (struct _SDIAG_DISPINFO *)(this + 7), 0);
    v6 = v13;
    if ( v13 < 0 )
    {
      v9 = 975;
      goto LABEL_20;
    }
    if ( (*((_BYTE *)*this + 56) & 1) == 0 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
      v16 = 0;
      v11 = SdpXmlNextNode(v8, &v16);
      v6 = v11;
      if ( v11 < 0 )
      {
        v12 = 987;
        goto LABEL_13;
      }
      v2 = v16;
      v13 = SdpXmlCheckNode(v16, L"Troubleshooter");
      v6 = v13;
      if ( v13 < 0 )
      {
        v9 = 988;
        goto LABEL_20;
      }
      if ( v13 == 1 || !v2 )
      {
        v9 = 988;
        goto LABEL_79;
      }
      v13 = Rootcause::InitializeTroubleshooter((Rootcause *)this, v2);
      v6 = v13;
      if ( v13 < 0 )
      {
        v9 = 991;
        goto LABEL_20;
      }
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
    v16 = 0;
    v11 = SdpXmlNextNode(v8, &v16);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = 1000;
      goto LABEL_13;
    }
    v2 = v16;
    v13 = SdpXmlCheckNode(v16, L"Resolvers");
    v6 = v13;
    if ( v13 < 0 )
    {
      v9 = 1001;
      goto LABEL_20;
    }
    if ( v13 == 1 || !v2 )
    {
      v9 = 1001;
    }
    else
    {
      v13 = Rootcause::InitializeResolvers((Rootcause *)this, v2);
      v6 = v13;
      if ( v13 < 0 )
      {
        v9 = 1004;
        goto LABEL_20;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
      v16 = 0;
      v11 = SdpXmlNextNode(v8, &v16);
      v6 = v11;
      if ( v11 < 0 )
      {
        v12 = 1012;
        goto LABEL_13;
      }
      v2 = v16;
      v13 = SdpXmlCheckNode(v16, L"Verifier");
      v6 = v13;
      if ( v13 < 0 )
      {
        v9 = 1013;
        goto LABEL_20;
      }
      if ( v13 == 1 || !v2 )
      {
        v9 = 1013;
      }
      else
      {
        v13 = Rootcause::InitializeVerifier((Rootcause *)this, v2);
        v6 = v13;
        if ( v13 < 0 )
        {
          v9 = 1016;
          goto LABEL_20;
        }
        ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
        v16 = 0;
        v11 = SdpXmlNextNode(v8, &v16);
        v6 = v11;
        if ( v11 < 0 )
        {
          v12 = 1024;
          goto LABEL_13;
        }
        v2 = v16;
        v13 = SdpXmlCheckNode(v16, L"ContextParameters");
        v6 = v13;
        if ( v13 < 0 )
        {
          v9 = 1025;
          goto LABEL_20;
        }
        if ( v13 == 1 || !v2 )
        {
          v9 = 1025;
        }
        else
        {
          v13 = SdpParseParameters(v2, (struct _SDIAG_PARAMSET *)(this + 11));
          v6 = v13;
          if ( v13 < 0 )
          {
            v9 = 1028;
            goto LABEL_20;
          }
          ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
          v16 = 0;
          v11 = SdpXmlNextNode(v8, &v16);
          v6 = v11;
          if ( v11 < 0 )
          {
            v12 = 1036;
            goto LABEL_13;
          }
          v2 = v16;
          v13 = SdpXmlCheckNode(v16, L"ExtensionPoint");
          v6 = v13;
          if ( v13 < 0 )
          {
            v9 = 1037;
            goto LABEL_20;
          }
          if ( v13 != 1 && v2 )
          {
            v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, char *))v2->lpVtbl->cloneNode)(
                    v2,
                    0xFFFFFFFFLL,
                    (char *)this + 48);
            v6 = v13;
            if ( v13 >= 0 )
              goto LABEL_82;
            v9 = 1040;
LABEL_20:
            v10 = v13;
            goto LABEL_81;
          }
          v9 = 1037;
        }
      }
    }
LABEL_79:
    v10 = -2147467259;
    goto LABEL_80;
  }
  v12 = 956;
LABEL_13:
  SdpDebugTrace(1u, L"Rootcause::ParseRootcauseXml", v12, v11);
  v2 = v16;
LABEL_82:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v8->lpVtbl->Release)(v8);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return v6;
}

```

## disassembly

```asm
0x18001a530  push    rbp
0x18001a532  push    rbx
0x18001a533  push    rsi
0x18001a534  push    rdi
0x18001a535  push    r12
0x18001a537  push    r14
0x18001a539  push    r15
0x18001a53b  mov     rbp, rsp
0x18001a53e  sub     rsp, 20h
0x18001a542  xor     edi, edi
0x18001a544  mov     [rbp+arg_18], 0
0x18001a54c  mov     [rbp+arg_10], rdi
0x18001a550  mov     r14, rcx
0x18001a553  mov     [rbp+arg_8], edi
0x18001a556  test    rdx, rdx
0x18001a559  jnz     short loc_18001A580
0x18001a55b  mov     r9d, 80070057h; int
0x18001a561  mov     r8d, 3ACh; int
0x18001a567  mov     ebx, r9d
0x18001a56a  lea     rdx, aRootcauseParse; "Rootcause::ParseRootcauseXml"
0x18001a571  mov     ecx, 1; Level
0x18001a576  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a57b  jmp     loc_18001AA38
0x18001a580  cmp     [rcx], rdi
0x18001a583  jnz     short loc_18001A595
0x18001a585  mov     ebx, 80004003h
0x18001a58a  mov     r8d, 3ADh
0x18001a590  mov     r9d, ebx
0x18001a593  jmp     short loc_18001A56A
0x18001a595  lea     r9, [rbp+arg_8]; unsigned int *
0x18001a599  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001a59b  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18001a59f  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001a5a4  mov     r12, [rbp+arg_18]
0x18001a5a8  mov     ebx, eax
0x18001a5aa  test    eax, eax
0x18001a5ac  jns     short loc_18001A5C1
0x18001a5ae  mov     r8d, 3B0h
0x18001a5b4  mov     r9d, eax
0x18001a5b7  mov     ecx, 1
0x18001a5bc  jmp     loc_18001AA03
0x18001a5c1  cmp     [rbp+arg_8], 6
0x18001a5c5  jnb     short loc_18001A5DD
0x18001a5c7  mov     r9d, 80070057h
0x18001a5cd  mov     r8d, 3B4h
0x18001a5d3  mov     ecx, 1
0x18001a5d8  jmp     loc_18001AA00
0x18001a5dd  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a5e1  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a5e4  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a5e9  mov     ebx, eax
0x18001a5eb  test    eax, eax
0x18001a5ed  jns     short loc_18001A612
0x18001a5ef  mov     r8d, 3BCh; int
0x18001a5f5  mov     ecx, 1; Level
0x18001a5fa  mov     r9d, eax; int
0x18001a5fd  lea     rdx, aRootcauseParse; "Rootcause::ParseRootcauseXml"
0x18001a604  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a609  mov     rdi, [rbp+arg_10]
0x18001a60d  jmp     loc_18001AA0F
0x18001a612  mov     rdi, [rbp+arg_10]
0x18001a616  lea     rdx, aId; "ID"
0x18001a61d  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a620  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a625  mov     ebx, eax
0x18001a627  test    eax, eax
0x18001a629  jns     short loc_18001A633
0x18001a62b  mov     r8d, 3BDh
0x18001a631  jmp     short loc_18001A5B4
0x18001a633  mov     esi, 1
0x18001a638  cmp     eax, esi
0x18001a63a  jz      loc_18001A9F2
0x18001a640  test    rdi, rdi
0x18001a643  jz      loc_18001A9F2
0x18001a649  mov     rax, [rdi]
0x18001a64c  lea     rdx, [r14+28h]
0x18001a650  mov     rcx, rdi
0x18001a653  mov     rax, [rax+0D0h]
0x18001a65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a65f  mov     ebx, eax
0x18001a661  test    eax, eax
0x18001a663  jns     short loc_18001A675
0x18001a665  mov     r8d, 3C0h
0x18001a66b  mov     r9d, eax
0x18001a66e  mov     ecx, esi
0x18001a670  jmp     loc_18001AA03
0x18001a675  mov     rax, [rdi]
0x18001a678  mov     rcx, rdi
0x18001a67b  mov     rax, [rax+10h]
0x18001a67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a684  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a688  mov     [rbp+arg_10], 0
0x18001a690  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a693  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a698  mov     ebx, eax
0x18001a69a  test    eax, eax
0x18001a69c  jns     short loc_18001A6AB
0x18001a69e  mov     r8d, 3C8h
0x18001a6a4  mov     ecx, esi
0x18001a6a6  jmp     loc_18001A5FA
0x18001a6ab  mov     rdi, [rbp+arg_10]
0x18001a6af  lea     rdx, aDisplayinforma; "DisplayInformation"
0x18001a6b6  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a6b9  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a6be  mov     ebx, eax
0x18001a6c0  test    eax, eax
0x18001a6c2  jns     short loc_18001A6CC
0x18001a6c4  mov     r8d, 3C9h
0x18001a6ca  jmp     short loc_18001A66B
0x18001a6cc  cmp     eax, esi
0x18001a6ce  jz      loc_18001A9EA
0x18001a6d4  test    rdi, rdi
0x18001a6d7  jz      loc_18001A9EA
0x18001a6dd  lea     rdx, [r14+38h]; struct _SDIAG_DISPINFO *
0x18001a6e1  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a6e4  call    ?SdpParseDisplayInformation@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_DISPINFO@@@Z; SdpParseDisplayInformation(IXMLDOMNode *,_SDIAG_DISPINFO *)
0x18001a6e9  mov     ebx, eax
0x18001a6eb  test    eax, eax
0x18001a6ed  jns     short loc_18001A6FA
0x18001a6ef  mov     r8d, 3CCh
0x18001a6f5  jmp     loc_18001A66B
0x18001a6fa  mov     rcx, [r14]; struct Settings *
0x18001a6fd  lea     rdx, [r14+38h]; struct _SDIAG_DISPINFO *
0x18001a701  xor     r8d, r8d; int
0x18001a704  call    ?SdpLocalizeDisplayInformation@@YAJPEAVSettings@@PEAU_SDIAG_DISPINFO@@H@Z; SdpLocalizeDisplayInformation(Settings *,_SDIAG_DISPINFO *,int)
0x18001a709  mov     ebx, eax
0x18001a70b  test    eax, eax
0x18001a70d  jns     short loc_18001A71A
0x18001a70f  mov     r8d, 3CFh
0x18001a715  jmp     loc_18001A66B
0x18001a71a  mov     rax, [r14]
0x18001a71d  test    [rax+38h], sil
0x18001a721  jnz     loc_18001A7AF
0x18001a727  mov     rax, [rdi]
0x18001a72a  mov     rcx, rdi
0x18001a72d  mov     rax, [rax+10h]
0x18001a731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a736  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a73a  mov     [rbp+arg_10], 0
0x18001a742  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a745  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a74a  mov     ebx, eax
0x18001a74c  test    eax, eax
0x18001a74e  jns     short loc_18001A75B
0x18001a750  mov     r8d, 3DBh
0x18001a756  jmp     loc_18001A6A4
0x18001a75b  mov     rdi, [rbp+arg_10]
0x18001a75f  lea     rdx, aTroubleshooter_3; "Troubleshooter"
0x18001a766  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a769  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a76e  mov     ebx, eax
0x18001a770  test    eax, eax
0x18001a772  jns     short loc_18001A77F
0x18001a774  mov     r8d, 3DCh
0x18001a77a  jmp     loc_18001A66B
0x18001a77f  cmp     eax, esi
0x18001a781  jz      short loc_18001A7A4
0x18001a783  test    rdi, rdi
0x18001a786  jz      short loc_18001A7A4
0x18001a788  mov     rdx, rdi; struct IXMLDOMNode *
0x18001a78b  mov     rcx, r14; this
0x18001a78e  call    ?InitializeTroubleshooter@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z; Rootcause::InitializeTroubleshooter(IXMLDOMNode *)
0x18001a793  mov     ebx, eax
0x18001a795  test    eax, eax
0x18001a797  jns     short loc_18001A7AF
0x18001a799  mov     r8d, 3DFh
0x18001a79f  jmp     loc_18001A66B
0x18001a7a4  mov     r8d, 3DCh
0x18001a7aa  jmp     loc_18001A9F8
0x18001a7af  mov     rax, [rdi]
0x18001a7b2  mov     rcx, rdi
0x18001a7b5  mov     rax, [rax+10h]
0x18001a7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7be  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a7c2  mov     [rbp+arg_10], 0
0x18001a7ca  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a7cd  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a7d2  mov     ebx, eax
0x18001a7d4  test    eax, eax
0x18001a7d6  jns     short loc_18001A7E3
0x18001a7d8  mov     r8d, 3E8h
0x18001a7de  jmp     loc_18001A6A4
0x18001a7e3  mov     rdi, [rbp+arg_10]
0x18001a7e7  lea     rdx, aResolvers; "Resolvers"
0x18001a7ee  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a7f1  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a7f6  mov     ebx, eax
0x18001a7f8  test    eax, eax
0x18001a7fa  jns     short loc_18001A807
0x18001a7fc  mov     r8d, 3E9h
0x18001a802  jmp     loc_18001A66B
0x18001a807  cmp     eax, esi
0x18001a809  jz      loc_18001A9E2
0x18001a80f  test    rdi, rdi
0x18001a812  jz      loc_18001A9E2
0x18001a818  mov     rdx, rdi; struct IXMLDOMNode *
0x18001a81b  mov     rcx, r14; this
0x18001a81e  call    ?InitializeResolvers@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z; Rootcause::InitializeResolvers(IXMLDOMNode *)
0x18001a823  mov     ebx, eax
0x18001a825  test    eax, eax
0x18001a827  jns     short loc_18001A834
0x18001a829  mov     r8d, 3ECh
0x18001a82f  jmp     loc_18001A66B
0x18001a834  mov     rax, [rdi]
0x18001a837  mov     rcx, rdi
0x18001a83a  mov     rax, [rax+10h]
0x18001a83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a843  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a847  mov     [rbp+arg_10], 0
0x18001a84f  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a852  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a857  mov     ebx, eax
0x18001a859  test    eax, eax
0x18001a85b  jns     short loc_18001A868
0x18001a85d  mov     r8d, 3F4h
0x18001a863  jmp     loc_18001A6A4
0x18001a868  mov     rdi, [rbp+arg_10]
0x18001a86c  lea     rdx, aVerifier; "Verifier"
0x18001a873  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a876  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a87b  mov     ebx, eax
0x18001a87d  test    eax, eax
0x18001a87f  jns     short loc_18001A88C
0x18001a881  mov     r8d, 3F5h
0x18001a887  jmp     loc_18001A66B
0x18001a88c  cmp     eax, esi
0x18001a88e  jz      loc_18001A9DA
0x18001a894  test    rdi, rdi
0x18001a897  jz      loc_18001A9DA
0x18001a89d  mov     rdx, rdi; struct IXMLDOMNode *
0x18001a8a0  mov     rcx, r14; this
0x18001a8a3  call    ?InitializeVerifier@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z; Rootcause::InitializeVerifier(IXMLDOMNode *)
0x18001a8a8  mov     ebx, eax
0x18001a8aa  test    eax, eax
0x18001a8ac  jns     short loc_18001A8B9
0x18001a8ae  mov     r8d, 3F8h
0x18001a8b4  jmp     loc_18001A66B
0x18001a8b9  mov     rax, [rdi]
0x18001a8bc  mov     rcx, rdi
0x18001a8bf  mov     rax, [rax+10h]
0x18001a8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8c8  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a8cc  mov     [rbp+arg_10], 0
0x18001a8d4  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a8d7  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a8dc  mov     ebx, eax
0x18001a8de  test    eax, eax
0x18001a8e0  jns     short loc_18001A8ED
0x18001a8e2  mov     r8d, 400h
0x18001a8e8  jmp     loc_18001A6A4
0x18001a8ed  mov     rdi, [rbp+arg_10]
0x18001a8f1  lea     rdx, aContextparamet; "ContextParameters"
0x18001a8f8  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a8fb  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a900  mov     ebx, eax
0x18001a902  test    eax, eax
0x18001a904  jns     short loc_18001A911
0x18001a906  mov     r8d, 401h
0x18001a90c  jmp     loc_18001A66B
0x18001a911  cmp     eax, esi
0x18001a913  jz      loc_18001A9D2
0x18001a919  test    rdi, rdi
0x18001a91c  jz      loc_18001A9D2
0x18001a922  lea     rdx, [r14+58h]; struct _SDIAG_PARAMSET *
0x18001a926  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a929  call    ?SdpParseParameters@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMSET@@@Z; SdpParseParameters(IXMLDOMNode *,_SDIAG_PARAMSET *)
0x18001a92e  mov     ebx, eax
0x18001a930  test    eax, eax
0x18001a932  jns     short loc_18001A93F
0x18001a934  mov     r8d, 404h
0x18001a93a  jmp     loc_18001A66B
0x18001a93f  mov     rax, [rdi]
0x18001a942  mov     rcx, rdi
0x18001a945  mov     rax, [rax+10h]
0x18001a949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a94e  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a952  mov     [rbp+arg_10], 0
0x18001a95a  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001a95d  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a962  mov     ebx, eax
0x18001a964  test    eax, eax
0x18001a966  jns     short loc_18001A973
0x18001a968  mov     r8d, 40Ch
0x18001a96e  jmp     loc_18001A6A4
0x18001a973  mov     rdi, [rbp+arg_10]
0x18001a977  lea     rdx, aExtensionpoint_0; "ExtensionPoint"
0x18001a97e  mov     rcx, rdi; struct IXMLDOMNode *
0x18001a981  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a986  mov     ebx, eax
0x18001a988  test    eax, eax
0x18001a98a  jns     short loc_18001A997
0x18001a98c  mov     r8d, 40Dh
0x18001a992  jmp     loc_18001A66B
0x18001a997  cmp     eax, esi
0x18001a999  jz      short loc_18001A9CA
0x18001a99b  test    rdi, rdi
0x18001a99e  jz      short loc_18001A9CA
0x18001a9a0  mov     rax, [rdi]
0x18001a9a3  lea     r8, [r14+30h]
0x18001a9a7  or      edx, 0FFFFFFFFh
  ... truncated ...
```
