# Interaction::ParseInteractionXml(IXMLDOMNode *)

- ea: `0x1800208f4`
- end: `0x180020c6a`
- name: `?ParseInteractionXml@Interaction@@IEAAJPEAUIXMLDOMNode@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(struct Settings **this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18002021c`

## callees

- `0x180003b2c`
- `0x1800040e8`
- `0x18000615c`
- `0x1800208f4`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x180020ba9`: `ExtensionPoint`
- `0x180020925`: `Interaction::ParseInteractionXml`
- `0x1800209ca`: `Interaction::ParseInteractionXml`
- `0x180020c25`: `Interaction::ParseInteractionXml`

## pseudocode

```c
__int64 __fastcall Interaction::ParseInteractionXml(struct Settings **this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  unsigned int v4; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r15
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  unsigned int v13; // [rsp+68h] [rbp+48h] BYREF
  struct IXMLDOMNode *v14; // [rsp+70h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v15; // [rsp+78h] [rbp+58h] BYREF

  v2 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Interaction::ParseInteractionXml", 583, -2147024809);
    return v4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v15, &v13);
  v6 = v15;
  v4 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = 586;
LABEL_5:
    v8 = ChildNodes;
LABEL_52:
    SdpDebugTrace(1u, L"Interaction::ParseInteractionXml", v7, v8);
    goto LABEL_53;
  }
  if ( v13 < 4 )
  {
    v8 = -2147024809;
    v7 = 590;
LABEL_51:
    v4 = v8;
    goto LABEL_52;
  }
  ChildNodes = (*((__int64 (__fastcall **)(struct Settings **, struct IXMLDOMNodeList *))*this + 3))(this, v15);
  v4 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = 598;
    goto LABEL_5;
  }
  v9 = SdpXmlNextNode(v6, &v14);
  v4 = v9;
  if ( v9 >= 0 )
  {
    v2 = v14;
    ChildNodes = SdpXmlCheckNode(v14, L"ID");
    v4 = ChildNodes;
    if ( ChildNodes < 0 )
    {
      v7 = 606;
      goto LABEL_5;
    }
    if ( ChildNodes == 1 || !v2 )
    {
      v7 = 606;
    }
    else
    {
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v2->lpVtbl->get_text)(v2, (char *)this + 16);
      v4 = v11;
      if ( v11 < 0 )
      {
        v7 = 609;
        goto LABEL_19;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
      v14 = 0;
      v9 = SdpXmlNextNode(v6, &v14);
      v4 = v9;
      if ( v9 < 0 )
      {
        v10 = 617;
        goto LABEL_12;
      }
      v2 = v14;
      v11 = SdpXmlCheckNode(v14, L"DisplayInformation");
      v4 = v11;
      if ( v11 < 0 )
      {
        v7 = 618;
        goto LABEL_19;
      }
      if ( v11 == 1 || !v2 )
      {
        v7 = 618;
      }
      else
      {
        v11 = SdpParseDisplayInformation(v2, (struct _SDIAG_DISPINFO *)(this + 3));
        v4 = v11;
        if ( v11 < 0 )
        {
          v7 = 621;
          goto LABEL_19;
        }
        v11 = SdpLocalizeDisplayInformation(this[1], (struct _SDIAG_DISPINFO *)(this + 3), 0);
        v4 = v11;
        if ( v11 < 0 )
        {
          v7 = 624;
          goto LABEL_19;
        }
        ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
        v14 = 0;
        v9 = SdpXmlNextNode(v6, &v14);
        v4 = v9;
        if ( v9 < 0 )
        {
          v10 = 632;
          goto LABEL_12;
        }
        v2 = v14;
        v11 = SdpXmlCheckNode(v14, L"ContextParameters");
        v4 = v11;
        if ( v11 < 0 )
        {
          v7 = 633;
          goto LABEL_19;
        }
        if ( v11 == 1 || !v2 )
        {
          v7 = 633;
        }
        else
        {
          v11 = SdpParseParameters(v2, (struct _SDIAG_PARAMSET *)(this + 8));
          v4 = v11;
          if ( v11 < 0 )
          {
            v7 = 636;
            goto LABEL_19;
          }
          ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
          v14 = 0;
          v9 = SdpXmlNextNode(v6, &v14);
          v4 = v9;
          if ( v9 < 0 )
          {
            v10 = 644;
            goto LABEL_12;
          }
          v2 = v14;
          v11 = SdpXmlCheckNode(v14, L"ExtensionPoint");
          v4 = v11;
          if ( v11 < 0 )
          {
            v7 = 645;
            goto LABEL_19;
          }
          if ( v11 != 1 && v2 )
          {
            v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, char *))v2->lpVtbl->cloneNode)(
                    v2,
                    0xFFFFFFFFLL,
                    (char *)this + 56);
            v4 = v11;
            if ( v11 >= 0 )
              goto LABEL_53;
            v7 = 648;
LABEL_19:
            v8 = v11;
            goto LABEL_52;
          }
          v7 = 645;
        }
      }
    }
    v8 = -2147467259;
    goto LABEL_51;
  }
  v10 = 605;
LABEL_12:
  SdpDebugTrace(1u, L"Interaction::ParseInteractionXml", v10, v9);
  v2 = v14;
LABEL_53:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return v4;
}

```

## disassembly

```asm
0x1800208f4  push    rbp
0x1800208f6  push    rbx
0x1800208f7  push    rsi
0x1800208f8  push    rdi
0x1800208f9  push    r12
0x1800208fb  push    r14
0x1800208fd  push    r15
0x1800208ff  mov     rbp, rsp
0x180020902  sub     rsp, 20h
0x180020906  xor     edi, edi
0x180020908  mov     [rbp+arg_18], 0
0x180020910  mov     [rbp+arg_10], rdi
0x180020914  mov     r14, rcx
0x180020917  mov     [rbp+arg_8], edi
0x18002091a  test    rdx, rdx
0x18002091d  jnz     short loc_180020942
0x18002091f  mov     r9d, 80070057h; int
0x180020925  lea     rdx, aInteractionPar_0; "Interaction::ParseInteractionXml"
0x18002092c  mov     r8d, 247h; int
0x180020932  lea     ecx, [rdi+1]; Level
0x180020935  mov     ebx, r9d
0x180020938  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002093d  jmp     loc_180020C59
0x180020942  lea     r9, [rbp+arg_8]; unsigned int *
0x180020946  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180020948  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18002094c  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180020951  mov     r15, [rbp+arg_18]
0x180020955  mov     ebx, eax
0x180020957  test    eax, eax
0x180020959  jns     short loc_18002096E
0x18002095b  mov     r8d, 24Ah
0x180020961  mov     r9d, eax
0x180020964  mov     ecx, 1
0x180020969  jmp     loc_180020C25
0x18002096e  cmp     [rbp+arg_8], 4
0x180020972  jnb     short loc_18002098A
0x180020974  mov     r9d, 80070057h
0x18002097a  mov     r8d, 24Eh
0x180020980  mov     ecx, 1
0x180020985  jmp     loc_180020C22
0x18002098a  mov     rax, [r14]
0x18002098d  mov     rdx, r15
0x180020990  mov     rcx, r14
0x180020993  mov     rax, [rax+18h]
0x180020997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002099c  mov     ebx, eax
0x18002099e  test    eax, eax
0x1800209a0  jns     short loc_1800209AA
0x1800209a2  mov     r8d, 256h
0x1800209a8  jmp     short loc_180020961
0x1800209aa  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x1800209ae  mov     rcx, r15; struct IXMLDOMNodeList *
0x1800209b1  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800209b6  mov     ebx, eax
0x1800209b8  test    eax, eax
0x1800209ba  jns     short loc_1800209DF
0x1800209bc  mov     r8d, 25Dh; int
0x1800209c2  mov     ecx, 1; Level
0x1800209c7  mov     r9d, eax; int
0x1800209ca  lea     rdx, aInteractionPar_0; "Interaction::ParseInteractionXml"
0x1800209d1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800209d6  mov     rdi, [rbp+arg_10]
0x1800209da  jmp     loc_180020C31
0x1800209df  mov     rdi, [rbp+arg_10]
0x1800209e3  lea     rdx, aId; "ID"
0x1800209ea  mov     rcx, rdi; struct IXMLDOMNode *
0x1800209ed  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800209f2  mov     ebx, eax
0x1800209f4  test    eax, eax
0x1800209f6  jns     short loc_180020A03
0x1800209f8  mov     r8d, 25Eh
0x1800209fe  jmp     loc_180020961
0x180020a03  mov     esi, 1
0x180020a08  cmp     eax, esi
0x180020a0a  jz      loc_180020C14
0x180020a10  test    rdi, rdi
0x180020a13  jz      loc_180020C14
0x180020a19  mov     rax, [rdi]
0x180020a1c  lea     rdx, [r14+10h]
0x180020a20  mov     rcx, rdi
0x180020a23  mov     rax, [rax+0D0h]
0x180020a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a2f  mov     ebx, eax
0x180020a31  test    eax, eax
0x180020a33  jns     short loc_180020A45
0x180020a35  mov     r8d, 261h
0x180020a3b  mov     r9d, eax
0x180020a3e  mov     ecx, esi
0x180020a40  jmp     loc_180020C25
0x180020a45  mov     rax, [rdi]
0x180020a48  mov     rcx, rdi
0x180020a4b  mov     rax, [rax+10h]
0x180020a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a54  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180020a58  mov     [rbp+arg_10], 0
0x180020a60  mov     rcx, r15; struct IXMLDOMNodeList *
0x180020a63  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180020a68  mov     ebx, eax
0x180020a6a  test    eax, eax
0x180020a6c  jns     short loc_180020A7B
0x180020a6e  mov     r8d, 269h
0x180020a74  mov     ecx, esi
0x180020a76  jmp     loc_1800209C7
0x180020a7b  mov     rdi, [rbp+arg_10]
0x180020a7f  lea     rdx, aDisplayinforma; "DisplayInformation"
0x180020a86  mov     rcx, rdi; struct IXMLDOMNode *
0x180020a89  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180020a8e  mov     ebx, eax
0x180020a90  test    eax, eax
0x180020a92  jns     short loc_180020A9C
0x180020a94  mov     r8d, 26Ah
0x180020a9a  jmp     short loc_180020A3B
0x180020a9c  cmp     eax, esi
0x180020a9e  jz      loc_180020C0C
0x180020aa4  test    rdi, rdi
0x180020aa7  jz      loc_180020C0C
0x180020aad  lea     rdx, [r14+18h]; struct _SDIAG_DISPINFO *
0x180020ab1  mov     rcx, rdi; struct IXMLDOMNode *
0x180020ab4  call    ?SdpParseDisplayInformation@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_DISPINFO@@@Z; SdpParseDisplayInformation(IXMLDOMNode *,_SDIAG_DISPINFO *)
0x180020ab9  mov     ebx, eax
0x180020abb  test    eax, eax
0x180020abd  jns     short loc_180020ACA
0x180020abf  mov     r8d, 26Dh
0x180020ac5  jmp     loc_180020A3B
0x180020aca  mov     rcx, [r14+8]; struct Settings *
0x180020ace  lea     rdx, [r14+18h]; struct _SDIAG_DISPINFO *
0x180020ad2  xor     r8d, r8d; int
0x180020ad5  call    ?SdpLocalizeDisplayInformation@@YAJPEAVSettings@@PEAU_SDIAG_DISPINFO@@H@Z; SdpLocalizeDisplayInformation(Settings *,_SDIAG_DISPINFO *,int)
0x180020ada  mov     ebx, eax
0x180020adc  test    eax, eax
0x180020ade  jns     short loc_180020AEB
0x180020ae0  mov     r8d, 270h
0x180020ae6  jmp     loc_180020A3B
0x180020aeb  mov     rax, [rdi]
0x180020aee  mov     rcx, rdi
0x180020af1  mov     rax, [rax+10h]
0x180020af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020afa  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180020afe  mov     [rbp+arg_10], 0
0x180020b06  mov     rcx, r15; struct IXMLDOMNodeList *
0x180020b09  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180020b0e  mov     ebx, eax
0x180020b10  test    eax, eax
0x180020b12  jns     short loc_180020B1F
0x180020b14  mov     r8d, 278h
0x180020b1a  jmp     loc_180020A74
0x180020b1f  mov     rdi, [rbp+arg_10]
0x180020b23  lea     rdx, aContextparamet; "ContextParameters"
0x180020b2a  mov     rcx, rdi; struct IXMLDOMNode *
0x180020b2d  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180020b32  mov     ebx, eax
0x180020b34  test    eax, eax
0x180020b36  jns     short loc_180020B43
0x180020b38  mov     r8d, 279h
0x180020b3e  jmp     loc_180020A3B
0x180020b43  cmp     eax, esi
0x180020b45  jz      loc_180020C04
0x180020b4b  test    rdi, rdi
0x180020b4e  jz      loc_180020C04
0x180020b54  lea     rdx, [r14+40h]; struct _SDIAG_PARAMSET *
0x180020b58  mov     rcx, rdi; struct IXMLDOMNode *
0x180020b5b  call    ?SdpParseParameters@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMSET@@@Z; SdpParseParameters(IXMLDOMNode *,_SDIAG_PARAMSET *)
0x180020b60  mov     ebx, eax
0x180020b62  test    eax, eax
0x180020b64  jns     short loc_180020B71
0x180020b66  mov     r8d, 27Ch
0x180020b6c  jmp     loc_180020A3B
0x180020b71  mov     rax, [rdi]
0x180020b74  mov     rcx, rdi
0x180020b77  mov     rax, [rax+10h]
0x180020b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b80  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180020b84  mov     [rbp+arg_10], 0
0x180020b8c  mov     rcx, r15; struct IXMLDOMNodeList *
0x180020b8f  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180020b94  mov     ebx, eax
0x180020b96  test    eax, eax
0x180020b98  jns     short loc_180020BA5
0x180020b9a  mov     r8d, 284h
0x180020ba0  jmp     loc_180020A74
0x180020ba5  mov     rdi, [rbp+arg_10]
0x180020ba9  lea     rdx, aExtensionpoint_0; "ExtensionPoint"
0x180020bb0  mov     rcx, rdi; struct IXMLDOMNode *
0x180020bb3  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180020bb8  mov     ebx, eax
0x180020bba  test    eax, eax
0x180020bbc  jns     short loc_180020BC9
0x180020bbe  mov     r8d, 285h
0x180020bc4  jmp     loc_180020A3B
0x180020bc9  cmp     eax, esi
0x180020bcb  jz      short loc_180020BFC
0x180020bcd  test    rdi, rdi
0x180020bd0  jz      short loc_180020BFC
0x180020bd2  mov     rax, [rdi]
0x180020bd5  lea     r8, [r14+38h]
0x180020bd9  or      edx, 0FFFFFFFFh
0x180020bdc  mov     rcx, rdi
0x180020bdf  mov     rax, [rax+0C0h]
0x180020be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020beb  mov     ebx, eax
0x180020bed  test    eax, eax
0x180020bef  jns     short loc_180020C31
0x180020bf1  mov     r8d, 288h
0x180020bf7  jmp     loc_180020A3B
0x180020bfc  mov     r8d, 285h
0x180020c02  jmp     short loc_180020C1A
0x180020c04  mov     r8d, 279h
0x180020c0a  jmp     short loc_180020C1A
0x180020c0c  mov     r8d, 26Ah
0x180020c12  jmp     short loc_180020C1A
0x180020c14  mov     r8d, 25Eh; int
0x180020c1a  mov     ecx, esi; Level
0x180020c1c  mov     r9d, 80004005h; int
0x180020c22  mov     ebx, r9d
0x180020c25  lea     rdx, aInteractionPar_0; "Interaction::ParseInteractionXml"
0x180020c2c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180020c31  test    r15, r15
0x180020c34  jz      short loc_180020C45
0x180020c36  mov     rax, [r15]
0x180020c39  mov     rcx, r15
0x180020c3c  mov     rax, [rax+10h]
0x180020c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c45  test    rdi, rdi
0x180020c48  jz      short loc_180020C59
0x180020c4a  mov     rax, [rdi]
0x180020c4d  mov     rcx, rdi
0x180020c50  mov     rax, [rax+10h]
0x180020c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c59  mov     eax, ebx
0x180020c5b  add     rsp, 20h
0x180020c5f  pop     r15
0x180020c61  pop     r14
0x180020c63  pop     r12
0x180020c65  pop     rdi
0x180020c66  pop     rsi
0x180020c67  pop     rbx
0x180020c68  pop     rbp
0x180020c69  retn
```
