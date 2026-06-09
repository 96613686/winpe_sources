# SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)

- ea: `0x1800286a4`
- end: `0x1800288af`
- name: `?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z`
- size: `523`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNodeList **, unsigned int *)`
- caller_count: `23`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002d20`
- `0x1800038c4`
- `0x180003b2c`
- `0x180003e50`
- `0x1800040e8`
- `0x18000cf00`
- `0x180015c14`
- `0x180016228`
- `0x180016630`
- `0x18001a0bc`
- `0x18001a530`
- `0x18001bf34`
- `0x18001c6e8`
- `0x18001d20c`
- `0x18001dc28`
- `0x18001f010`
- `0x18001fc10`
- `0x180020648`
- `0x1800208f4`
- `0x180020c7c`
- `0x180022ce0`
- `0x180023020`
- `0x180028f24`

## callees

- `0x180026fa0`
- `0x1800286a4`
- `0x1800288b8`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x1800286e5`: `SdpXmlGetChildNodes`
- `0x18002871f`: `SdpXmlGetChildNodes`
- `0x180028765`: `SdpXmlGetChildNodes`
- `0x1800287d0`: `SdpXmlGetNumChildNodes`

## pseudocode

```c
__int64 __fastcall SdpXmlGetChildNodes(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct IXMLDOMNodeList **a3,
        unsigned int *a4)
{
  struct IXMLDOMElement *v4; // rsi
  unsigned int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  int RootNode; // eax
  int v11; // eax
  int v12; // r9d
  unsigned int v13; // r8d
  int v14; // eax
  struct IXMLDOMNodeList *v15; // rdi
  unsigned int i; // r14d
  struct IXMLDOMNodeList *v18[2]; // [rsp+20h] [rbp-10h] BYREF
  struct IXMLDOMElement *v19; // [rsp+70h] [rbp+40h] BYREF

  v4 = 0;
  v19 = 0;
  v18[0] = 0;
  if ( !a3 )
  {
    v7 = 790;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlGetChildNodes", v7, v8);
    goto LABEL_25;
  }
  if ( !a4 )
  {
    v7 = 791;
    goto LABEL_3;
  }
  if ( a1 )
  {
    RootNode = SdpXmlGetRootNode(a1, &v19);
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      SdpDebugTrace(1u, L"SdpXmlGetChildNodes", 0x31Eu, RootNode);
      v4 = v19;
      goto LABEL_23;
    }
    v4 = v19;
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMNodeList **))v19->lpVtbl->get_childNodes)(
            v19,
            v18);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = v11;
      v13 = 801;
LABEL_12:
      SdpDebugTrace(1u, L"SdpXmlGetChildNodes", v13, v12);
      goto LABEL_23;
    }
  }
  else
  {
    if ( !a2 )
    {
      v9 = -2147467261;
      v7 = 804;
      v8 = -2147467261;
      goto LABEL_4;
    }
    v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))a2->lpVtbl->get_childNodes)(a2, v18);
    v9 = v14;
    if ( v14 < 0 )
    {
      v8 = v14;
      v7 = 806;
      goto LABEL_4;
    }
  }
  v15 = v18[0];
  v19 = 0;
  if ( !v18[0] )
  {
    SdpDebugTrace(1u, L"SdpXmlGetNumChildNodes", 0x359u, -2147024809);
    v12 = -2147024809;
    v13 = 810;
    v9 = -2147024809;
    goto LABEL_12;
  }
  for ( i = 0; ; ++i )
  {
    SdpXmlNextNode(v15, (struct IXMLDOMNode **)&v19);
    if ( !v19 )
      break;
    ((void (__fastcall *)(struct IXMLDOMElement *))v19->lpVtbl->Release)(v19);
    v19 = 0;
  }
  ((void (__fastcall *)(struct IXMLDOMNodeList *))v15->lpVtbl->reset)(v15);
  v9 = 0;
  *a3 = v18[0];
  *a4 = i;
  ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->AddRef)(*a3);
LABEL_23:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
LABEL_25:
  if ( v18[0] )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v18[0]->lpVtbl->Release)(v18[0]);
  return v9;
}

```

## disassembly

```asm
0x1800286a4  mov     [rsp-28h+arg_0], rbx
0x1800286a9  mov     [rsp-28h+arg_8], rsi
0x1800286ae  push    rbp
0x1800286af  push    rdi
0x1800286b0  push    r12
0x1800286b2  push    r14
0x1800286b4  push    r15
0x1800286b6  mov     rbp, rsp
0x1800286b9  sub     rsp, 30h
0x1800286bd  xor     esi, esi
0x1800286bf  mov     r12, r9
0x1800286c2  mov     [rbp+arg_10], rsi
0x1800286c6  mov     r15, r8
0x1800286c9  mov     [rbp+var_10], rsi
0x1800286cd  mov     r10, rdx
0x1800286d0  test    r8, r8
0x1800286d3  jnz     short loc_1800286FB
0x1800286d5  mov     r8d, 316h; int
0x1800286db  mov     edi, 80070057h
0x1800286e0  mov     r9d, edi; int
0x1800286e3  mov     ebx, edi
0x1800286e5  lea     rdx, aSdpxmlgetchild; "SdpXmlGetChildNodes"
0x1800286ec  mov     ecx, 1; Level
0x1800286f1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800286f6  jmp     loc_180028881
0x1800286fb  test    r12, r12
0x1800286fe  jnz     short loc_180028708
0x180028700  mov     r8d, 317h
0x180028706  jmp     short loc_1800286DB
0x180028708  test    rcx, rcx
0x18002870b  jz      short loc_18002877B
0x18002870d  lea     rdx, [rbp+arg_10]; struct IXMLDOMElement **
0x180028711  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180028716  mov     ebx, eax
0x180028718  test    eax, eax
0x18002871a  jns     short loc_18002873F
0x18002871c  mov     r9d, eax; int
0x18002871f  lea     rdx, aSdpxmlgetchild; "SdpXmlGetChildNodes"
0x180028726  mov     r8d, 31Eh; int
0x18002872c  mov     ecx, 1; Level
0x180028731  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028736  mov     rsi, [rbp+arg_10]
0x18002873a  jmp     loc_18002886D
0x18002873f  mov     rsi, [rbp+arg_10]
0x180028743  lea     rdx, [rbp+var_10]
0x180028747  mov     rcx, rsi
0x18002874a  mov     rax, [rsi]
0x18002874d  mov     rax, [rax+60h]
0x180028751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028756  mov     ebx, eax
0x180028758  test    eax, eax
0x18002875a  jns     short loc_1800287BA
0x18002875c  mov     r9d, eax; int
0x18002875f  mov     r8d, 321h; int
0x180028765  lea     rdx, aSdpxmlgetchild; "SdpXmlGetChildNodes"
0x18002876c  mov     ecx, 1; Level
0x180028771  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028776  jmp     loc_18002886D
0x18002877b  test    r10, r10
0x18002877e  jnz     short loc_180028793
0x180028780  mov     ebx, 80004003h
0x180028785  mov     r8d, 324h
0x18002878b  mov     r9d, ebx
0x18002878e  jmp     loc_1800286E5
0x180028793  mov     rax, [rdx]
0x180028796  mov     rcx, r10
0x180028799  lea     rdx, [rbp+var_10]
0x18002879d  mov     rax, [rax+60h]
0x1800287a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287a6  mov     ebx, eax
0x1800287a8  test    eax, eax
0x1800287aa  jns     short loc_1800287BA
0x1800287ac  mov     r9d, eax
0x1800287af  mov     r8d, 326h
0x1800287b5  jmp     loc_1800286E5
0x1800287ba  mov     rdi, [rbp+var_10]
0x1800287be  mov     [rbp+arg_10], 0
0x1800287c6  test    rdi, rdi
0x1800287c9  jnz     short loc_1800287FA
0x1800287cb  mov     edi, 80070057h
0x1800287d0  lea     rdx, aSdpxmlgetnumch; "SdpXmlGetNumChildNodes"
0x1800287d7  mov     r9d, edi; int
0x1800287da  mov     r8d, 359h; int
0x1800287e0  mov     ecx, 1; Level
0x1800287e5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800287ea  mov     r9d, edi
0x1800287ed  mov     r8d, 32Ah
0x1800287f3  mov     ebx, edi
0x1800287f5  jmp     loc_180028765
0x1800287fa  xor     r14d, r14d
0x1800287fd  jmp     short loc_180028819
0x1800287ff  mov     rax, [rbx]
0x180028802  mov     rcx, rbx
0x180028805  mov     rax, [rax+10h]
0x180028809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002880e  inc     r14d
0x180028811  mov     [rbp+arg_10], 0
0x180028819  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18002881d  mov     rcx, rdi; struct IXMLDOMNodeList *
0x180028820  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180028825  mov     rbx, [rbp+arg_10]
0x180028829  test    rbx, rbx
0x18002882c  jnz     short loc_1800287FF
0x18002882e  mov     rax, [rdi]
0x180028831  mov     rcx, rdi
0x180028834  mov     rax, [rax+50h]
0x180028838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002883d  test    rbx, rbx
0x180028840  jz      short loc_180028851
0x180028842  mov     rax, [rbx]
0x180028845  mov     rcx, rbx
0x180028848  mov     rax, [rax+10h]
0x18002884c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028851  mov     rax, [rbp+var_10]
0x180028855  xor     ebx, ebx
0x180028857  mov     [r15], rax
0x18002885a  mov     [r12], r14d
0x18002885e  mov     rcx, [r15]
0x180028861  mov     rax, [rcx]
0x180028864  mov     rax, [rax+8]
0x180028868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002886d  test    rsi, rsi
0x180028870  jz      short loc_180028881
0x180028872  mov     rax, [rsi]
0x180028875  mov     rcx, rsi
0x180028878  mov     rax, [rax+10h]
0x18002887c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028881  mov     rcx, [rbp+var_10]
0x180028885  test    rcx, rcx
0x180028888  jz      short loc_180028896
0x18002888a  mov     rax, [rcx]
0x18002888d  mov     rax, [rax+10h]
0x180028891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028896  mov     rsi, [rsp+30h+arg_8]
0x18002889b  mov     eax, ebx
0x18002889d  mov     rbx, [rsp+30h+arg_0]
0x1800288a2  add     rsp, 30h
0x1800288a6  pop     r15
0x1800288a8  pop     r14
0x1800288aa  pop     r12
0x1800288ac  pop     rdi
0x1800288ad  pop     rbp
0x1800288ae  retn
```
