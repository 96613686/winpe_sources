# SdpParseDisplayInformation(IXMLDOMNode *,_SDIAG_DISPINFO *)

- ea: `0x180003b2c`
- end: `0x180003e47`
- name: `?SdpParseDisplayInformation@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_DISPINFO@@@Z`
- size: `795`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct _SDIAG_DISPINFO *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180016630`
- `0x18001a530`
- `0x18001c6e8`
- `0x1800208f4`
- `0x180022ce0`

## callees

- `0x180002554`
- `0x180002798`
- `0x180003b2c`
- `0x1800040e8`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x180003d9b`: `SdpMoveDispInfo`

## pseudocode

```c
__int64 __fastcall SdpParseDisplayInformation(struct IXMLDOMNode *a1, struct _SDIAG_DISPINFO *a2)
{
  struct IXMLDOMNode *v2; // rsi
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v7; // r15
  unsigned int v8; // r8d
  int v9; // r9d
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // eax
  __int128 v15; // [rsp+20h] [rbp-20h] BYREF
  __int128 v16; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v17; // [rsp+70h] [rbp+30h] BYREF
  struct IXMLDOMNode *v18; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v19; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( !a1 )
  {
    v4 = 150;
LABEL_3:
    v5 = -2147024809;
    SdpDebugTrace(1u, L"SdpParseDisplayInformation", v4, -2147024809);
    goto LABEL_50;
  }
  if ( !a2 )
  {
    v4 = 151;
    goto LABEL_3;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a1, &v19, &v17);
  v7 = v19;
  v5 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v8 = 157;
LABEL_8:
    v9 = ChildNodes;
LABEL_45:
    SdpDebugTrace(1u, L"SdpParseDisplayInformation", v8, v9);
    goto LABEL_46;
  }
  if ( v17 < 3 )
  {
    v9 = -2147024809;
    v8 = 161;
LABEL_44:
    v5 = v9;
    goto LABEL_45;
  }
  v10 = SdpXmlNextNode(v19, &v18);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 169;
LABEL_13:
    SdpDebugTrace(1u, L"SdpParseDisplayInformation", v11, v10);
    v2 = v18;
    goto LABEL_46;
  }
  v2 = v18;
  ChildNodes = SdpXmlCheckNode(v18, L"Parameters");
  v5 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v8 = 170;
    goto LABEL_8;
  }
  if ( ChildNodes == 1 || !v2 )
  {
    v8 = 170;
    goto LABEL_43;
  }
  v12 = SdpParseParameters(v2, (struct _SDIAG_PARAMSET *)&v16);
  v5 = v12;
  if ( v12 < 0 )
  {
    v8 = 173;
LABEL_20:
    v9 = v12;
    goto LABEL_45;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v18 = 0;
  v10 = SdpXmlNextNode(v7, &v18);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 181;
    goto LABEL_13;
  }
  v2 = v18;
  v12 = SdpXmlCheckNode(v18, L"Name");
  v5 = v12;
  if ( v12 < 0 )
  {
    v8 = 182;
    goto LABEL_20;
  }
  if ( v12 == 1 || !v2 )
  {
    v8 = 182;
    goto LABEL_43;
  }
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int128 *))v2->lpVtbl->get_text)(v2, &v15);
  v5 = v12;
  if ( v12 < 0 )
  {
    v8 = 185;
    goto LABEL_20;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v18 = 0;
  v10 = SdpXmlNextNode(v7, &v18);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 193;
    goto LABEL_13;
  }
  v2 = v18;
  v12 = SdpXmlCheckNode(v18, L"Description");
  v5 = v12;
  if ( v12 < 0 )
  {
    v8 = 194;
    goto LABEL_20;
  }
  if ( v12 == 1 || !v2 )
  {
    v8 = 194;
LABEL_43:
    v9 = -2147467259;
    goto LABEL_44;
  }
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v2->lpVtbl->get_text)(v2, (char *)&v15 + 8);
  v5 = v12;
  if ( v12 < 0 )
  {
    v8 = 197;
    goto LABEL_20;
  }
  v13 = SdpMoveParamSet((struct _SDIAG_DISPINFO *)((char *)a2 + 16), (struct _SDIAG_PARAMSET *)&v16);
  v5 = v13;
  if ( v13 < 0 )
  {
    SdpDebugTrace(1u, L"SdpMoveDispInfo", 0x2ACu, v13);
    v9 = v5;
    v8 = 204;
    goto LABEL_45;
  }
  *(_OWORD *)a2 = v15;
  v15 = 0;
LABEL_46:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
LABEL_50:
  SdpFreeDispInfo((struct _SDIAG_DISPINFO *)&v15);
  return v5;
}

```

## disassembly

```asm
0x180003b2c  mov     [rsp-28h+arg_8], rbx
0x180003b31  push    rbp
0x180003b32  push    rsi
0x180003b33  push    rdi
0x180003b34  push    r14
0x180003b36  push    r15
0x180003b38  mov     rbp, rsp
0x180003b3b  sub     rsp, 40h
0x180003b3f  xor     esi, esi
0x180003b41  mov     [rbp+arg_18], 0
0x180003b49  mov     [rbp+arg_10], rsi
0x180003b4d  xorps   xmm0, xmm0
0x180003b50  mov     [rbp+arg_0], esi
0x180003b53  mov     r14, rdx
0x180003b56  movups  [rbp+var_20], xmm0
0x180003b5a  movups  [rbp+var_10], xmm0
0x180003b5e  test    rcx, rcx
0x180003b61  jnz     short loc_180003B88
0x180003b63  mov     r8d, 96h; int
0x180003b69  mov     r9d, 80070057h; int
0x180003b6f  lea     rdx, aSdpparsedispla; "SdpParseDisplayInformation"
0x180003b76  mov     ecx, 1; Level
0x180003b7b  mov     ebx, r9d
0x180003b7e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003b83  jmp     loc_180003E2B
0x180003b88  test    r14, r14
0x180003b8b  jnz     short loc_180003B95
0x180003b8d  mov     r8d, 97h
0x180003b93  jmp     short loc_180003B69
0x180003b95  mov     rdx, rcx; struct IXMLDOMNode *
0x180003b98  lea     r9, [rbp+arg_0]; unsigned int *
0x180003b9c  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180003b9e  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180003ba2  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180003ba7  mov     r15, [rbp+arg_18]
0x180003bab  mov     ebx, eax
0x180003bad  test    eax, eax
0x180003baf  jns     short loc_180003BC4
0x180003bb1  mov     r8d, 9Dh
0x180003bb7  mov     r9d, eax
0x180003bba  mov     ecx, 1
0x180003bbf  jmp     loc_180003DF7
0x180003bc4  cmp     [rbp+arg_0], 3
0x180003bc8  jnb     short loc_180003BE0
0x180003bca  mov     r9d, 80070057h
0x180003bd0  mov     r8d, 0A1h
0x180003bd6  mov     ecx, 1
0x180003bdb  jmp     loc_180003DF4
0x180003be0  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180003be4  mov     rcx, r15; struct IXMLDOMNodeList *
0x180003be7  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003bec  mov     ebx, eax
0x180003bee  test    eax, eax
0x180003bf0  jns     short loc_180003C15
0x180003bf2  mov     r8d, 0A9h; int
0x180003bf8  mov     ecx, 1; Level
0x180003bfd  mov     r9d, eax; int
0x180003c00  lea     rdx, aSdpparsedispla; "SdpParseDisplayInformation"
0x180003c07  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003c0c  mov     rsi, [rbp+arg_10]
0x180003c10  jmp     loc_180003E03
0x180003c15  mov     rsi, [rbp+arg_10]
0x180003c19  lea     rdx, aParameters; "Parameters"
0x180003c20  mov     rcx, rsi; struct IXMLDOMNode *
0x180003c23  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003c28  mov     ebx, eax
0x180003c2a  test    eax, eax
0x180003c2c  jns     short loc_180003C36
0x180003c2e  mov     r8d, 0AAh
0x180003c34  jmp     short loc_180003BB7
0x180003c36  mov     edi, 1
0x180003c3b  cmp     eax, edi
0x180003c3d  jz      loc_180003DE6
0x180003c43  test    rsi, rsi
0x180003c46  jz      loc_180003DE6
0x180003c4c  lea     rdx, [rbp+var_10]; struct _SDIAG_PARAMSET *
0x180003c50  mov     rcx, rsi; struct IXMLDOMNode *
0x180003c53  call    ?SdpParseParameters@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_PARAMSET@@@Z; SdpParseParameters(IXMLDOMNode *,_SDIAG_PARAMSET *)
0x180003c58  mov     ebx, eax
0x180003c5a  test    eax, eax
0x180003c5c  jns     short loc_180003C6E
0x180003c5e  mov     r8d, 0ADh
0x180003c64  mov     r9d, eax
0x180003c67  mov     ecx, edi
0x180003c69  jmp     loc_180003DF7
0x180003c6e  mov     rax, [rsi]
0x180003c71  mov     rcx, rsi
0x180003c74  mov     rax, [rax+10h]
0x180003c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c7d  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180003c81  mov     [rbp+arg_10], 0
0x180003c89  mov     rcx, r15; struct IXMLDOMNodeList *
0x180003c8c  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003c91  mov     ebx, eax
0x180003c93  test    eax, eax
0x180003c95  jns     short loc_180003CA4
0x180003c97  mov     r8d, 0B5h
0x180003c9d  mov     ecx, edi
0x180003c9f  jmp     loc_180003BFD
0x180003ca4  mov     rsi, [rbp+arg_10]
0x180003ca8  lea     rdx, aName; "Name"
0x180003caf  mov     rcx, rsi; struct IXMLDOMNode *
0x180003cb2  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003cb7  mov     ebx, eax
0x180003cb9  test    eax, eax
0x180003cbb  jns     short loc_180003CC5
0x180003cbd  mov     r8d, 0B6h
0x180003cc3  jmp     short loc_180003C64
0x180003cc5  cmp     eax, edi
0x180003cc7  jz      loc_180003DDE
0x180003ccd  test    rsi, rsi
0x180003cd0  jz      loc_180003DDE
0x180003cd6  mov     rax, [rsi]
0x180003cd9  lea     rdx, [rbp+var_20]
0x180003cdd  mov     rcx, rsi
0x180003ce0  mov     rax, [rax+0D0h]
0x180003ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cec  mov     ebx, eax
0x180003cee  test    eax, eax
0x180003cf0  jns     short loc_180003CFD
0x180003cf2  mov     r8d, 0B9h
0x180003cf8  jmp     loc_180003C64
0x180003cfd  mov     rax, [rsi]
0x180003d00  mov     rcx, rsi
0x180003d03  mov     rax, [rax+10h]
0x180003d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d0c  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180003d10  mov     [rbp+arg_10], 0
0x180003d18  mov     rcx, r15; struct IXMLDOMNodeList *
0x180003d1b  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003d20  mov     ebx, eax
0x180003d22  test    eax, eax
0x180003d24  jns     short loc_180003D31
0x180003d26  mov     r8d, 0C1h
0x180003d2c  jmp     loc_180003C9D
0x180003d31  mov     rsi, [rbp+arg_10]
0x180003d35  lea     rdx, aDescription; "Description"
0x180003d3c  mov     rcx, rsi; struct IXMLDOMNode *
0x180003d3f  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003d44  mov     ebx, eax
0x180003d46  test    eax, eax
0x180003d48  jns     short loc_180003D55
0x180003d4a  mov     r8d, 0C2h
0x180003d50  jmp     loc_180003C64
0x180003d55  cmp     eax, edi
0x180003d57  jz      short loc_180003DD6
0x180003d59  test    rsi, rsi
0x180003d5c  jz      short loc_180003DD6
0x180003d5e  mov     rax, [rsi]
0x180003d61  lea     rdx, [rbp+var_20+8]
0x180003d65  mov     rcx, rsi
0x180003d68  mov     rax, [rax+0D0h]
0x180003d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d74  mov     ebx, eax
0x180003d76  test    eax, eax
0x180003d78  jns     short loc_180003D85
0x180003d7a  mov     r8d, 0C5h
0x180003d80  jmp     loc_180003C64
0x180003d85  lea     rcx, [r14+10h]; struct _SDIAG_PARAMSET *
0x180003d89  lea     rdx, [rbp+var_10]; struct _SDIAG_PARAMSET *
0x180003d8d  call    ?SdpMoveParamSet@@YAJPEAU_SDIAG_PARAMSET@@0@Z; SdpMoveParamSet(_SDIAG_PARAMSET *,_SDIAG_PARAMSET *)
0x180003d92  mov     ebx, eax
0x180003d94  test    eax, eax
0x180003d96  jns     short loc_180003DBD
0x180003d98  mov     r9d, eax; int
0x180003d9b  lea     rdx, aSdpmovedispinf; "SdpMoveDispInfo"
0x180003da2  mov     r8d, 2ACh; int
0x180003da8  mov     ecx, edi; Level
0x180003daa  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003daf  mov     r9d, ebx
0x180003db2  mov     r8d, 0CCh
0x180003db8  jmp     loc_180003C67
0x180003dbd  mov     rax, qword ptr [rbp+var_20]
0x180003dc1  xorps   xmm0, xmm0
0x180003dc4  mov     [r14], rax
0x180003dc7  mov     rax, qword ptr [rbp+var_20+8]
0x180003dcb  mov     [r14+8], rax
0x180003dcf  movdqu  [rbp+var_20], xmm0
0x180003dd4  jmp     short loc_180003E03
0x180003dd6  mov     r8d, 0C2h
0x180003ddc  jmp     short loc_180003DEC
0x180003dde  mov     r8d, 0B6h
0x180003de4  jmp     short loc_180003DEC
0x180003de6  mov     r8d, 0AAh; int
0x180003dec  mov     r9d, 80004005h; int
0x180003df2  mov     ecx, edi; Level
0x180003df4  mov     ebx, r9d
0x180003df7  lea     rdx, aSdpparsedispla; "SdpParseDisplayInformation"
0x180003dfe  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003e03  test    r15, r15
0x180003e06  jz      short loc_180003E17
0x180003e08  mov     rax, [r15]
0x180003e0b  mov     rcx, r15
0x180003e0e  mov     rax, [rax+10h]
0x180003e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e17  test    rsi, rsi
0x180003e1a  jz      short loc_180003E2B
0x180003e1c  mov     rax, [rsi]
0x180003e1f  mov     rcx, rsi
0x180003e22  mov     rax, [rax+10h]
0x180003e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e2b  lea     rcx, [rbp+var_20]; struct _SDIAG_DISPINFO *
0x180003e2f  call    ?SdpFreeDispInfo@@YAJPEAU_SDIAG_DISPINFO@@@Z; SdpFreeDispInfo(_SDIAG_DISPINFO *)
0x180003e34  mov     eax, ebx
0x180003e36  mov     rbx, [rsp+40h+arg_8]
0x180003e3b  add     rsp, 40h
0x180003e3f  pop     r15
0x180003e41  pop     r14
0x180003e43  pop     rdi
0x180003e44  pop     rsi
0x180003e45  pop     rbp
0x180003e46  retn
```
