# MultipleResponseInteraction::BuildChoiceDocument(MultipleResponseInteraction::_CHOICE,IXMLDOMDocument2 * *,int)

- ea: `0x180022570`
- end: `0x1800227bc`
- name: `?BuildChoiceDocument@MultipleResponseInteraction@@MEAAJU_CHOICE@1@PEAPEAUIXMLDOMDocument2@@H@Z`
- size: `588`
- prototype: `__int64 __fastcall(__int64, __int64, struct IXMLDOMDocument2 **, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180002d20`
- `0x180022570`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800288b8`
- `0x18002a010`

## string_xrefs

- `0x1800225d1`: `<?xml version="1.0" encoding="utf-8"?><Choice/>`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::BuildChoiceDocument(
        __int64 a1,
        __int64 a2,
        struct IXMLDOMDocument2 **a3,
        int a4)
{
  struct IXMLDOMElement *v4; // rsi
  struct IXMLDOMDocument2 *v5; // r14
  unsigned int v9; // ebx
  int RootNode; // eax
  struct IXMLDOMDocument2 *v11; // rdi
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  int v15; // eax
  int v16; // r9d
  int v17; // r8d
  __int64 v18; // rdx
  struct IXMLDOMDocument2 *v20; // [rsp+30h] [rbp-28h] BYREF
  struct IXMLDOMElement *v21; // [rsp+38h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v22; // [rsp+40h] [rbp-18h] BYREF
  struct IXMLDOMElement *v23; // [rsp+B0h] [rbp+58h] BYREF

  v4 = 0;
  v22 = 0;
  v5 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a3 )
  {
    v9 = -2147024809;
    SdpDebugTrace(1u, L"MultipleResponseInteraction::BuildChoiceDocument", 409, -2147024809);
    return v9;
  }
  RootNode = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Choice/>", &v22);
  v11 = v22;
  v9 = RootNode;
  if ( RootNode < 0 )
  {
    v12 = 412;
    goto LABEL_5;
  }
  RootNode = SdpXmlGetRootNode(v22, &v21);
  v9 = RootNode;
  if ( RootNode < 0 )
  {
    v12 = 415;
    goto LABEL_5;
  }
  v14 = SdpBuildDisplayInformationXml((struct _SDIAG_DISPINFO *)a2, a4, &v20);
  v9 = v14;
  if ( v14 < 0 )
  {
    SdpDebugTrace(1u, L"MultipleResponseInteraction::BuildChoiceDocument", 424, v14);
    v5 = v20;
    goto LABEL_25;
  }
  v5 = v20;
  RootNode = SdpXmlAppend(v11, 0, v20);
  v9 = RootNode;
  if ( RootNode < 0 )
  {
    v12 = 427;
    goto LABEL_5;
  }
  v15 = SdpXmlCreateNode(v11, 0, L"Value", 0, &v23);
  v9 = v15;
  if ( v15 < 0 )
  {
    v16 = v15;
    v17 = 434;
LABEL_15:
    SdpDebugTrace(1u, L"MultipleResponseInteraction::BuildChoiceDocument", v17, v16);
    v4 = v23;
    goto LABEL_25;
  }
  if ( !*(_QWORD *)(a2 + 32) )
  {
    v16 = -2147467261;
    v17 = 436;
    v9 = -2147467261;
    goto LABEL_15;
  }
  v4 = v23;
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *))v23->lpVtbl->put_text)(v23);
  v9 = RootNode;
  if ( RootNode >= 0 )
  {
    v18 = *(_QWORD *)(a2 + 40);
    if ( !v18 )
    {
      v13 = -2147467261;
      v12 = 444;
      v9 = -2147467261;
      goto LABEL_6;
    }
    RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, _QWORD))v21->lpVtbl->appendChild)(v21, v18, 0);
    v9 = RootNode;
    if ( RootNode >= 0 )
    {
      *a3 = v11;
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->AddRef)(v11);
      goto LABEL_25;
    }
    v12 = 446;
  }
  else
  {
    v12 = 438;
  }
LABEL_5:
  v13 = RootNode;
LABEL_6:
  SdpDebugTrace(1u, L"MultipleResponseInteraction::BuildChoiceDocument", v12, v13);
LABEL_25:
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v21->lpVtbl->Release)(v21);
  return v9;
}

```

## disassembly

```asm
0x180022570  push    rbp
0x180022572  push    rbx
0x180022573  push    rsi
0x180022574  push    rdi
0x180022575  push    r12
0x180022577  push    r13
0x180022579  push    r14
0x18002257b  push    r15
0x18002257d  mov     rbp, rsp
0x180022580  sub     rsp, 58h
0x180022584  xor     esi, esi
0x180022586  mov     [rbp+var_18], 0
0x18002258e  xor     r14d, r14d
0x180022591  mov     [rbp+arg_10], rsi
0x180022595  mov     [rbp+var_28], r14
0x180022599  mov     r12d, r9d
0x18002259c  mov     [rbp+var_20], rsi
0x1800225a0  mov     r13, r8
0x1800225a3  mov     r15, rdx
0x1800225a6  test    r8, r8
0x1800225a9  jnz     short loc_1800225CD
0x1800225ab  mov     ebx, 80070057h
0x1800225b0  lea     rdx, aMultiplerespon_2; "MultipleResponseInteraction::BuildChoic"...
0x1800225b7  mov     r9d, ebx; int
0x1800225ba  lea     ecx, [rsi+1]; Level
0x1800225bd  mov     r8d, 199h; int
0x1800225c3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800225c8  jmp     loc_1800227A9
0x1800225cd  lea     rdx, [rbp+var_18]; struct IXMLDOMDocument2 **
0x1800225d1  lea     rcx, aXmlVersion10En_15; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x1800225d8  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1800225dd  mov     rdi, [rbp+var_18]
0x1800225e1  mov     ebx, eax
0x1800225e3  test    eax, eax
0x1800225e5  jns     short loc_180022606
0x1800225e7  mov     r8d, 19Ch; int
0x1800225ed  mov     r9d, eax; int
0x1800225f0  lea     rdx, aMultiplerespon_2; "MultipleResponseInteraction::BuildChoic"...
0x1800225f7  mov     ecx, 1; Level
0x1800225fc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022601  jmp     loc_180022758
0x180022606  lea     rdx, [rbp+var_20]; struct IXMLDOMElement **
0x18002260a  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18002260d  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180022612  mov     ebx, eax
0x180022614  test    eax, eax
0x180022616  jns     short loc_180022620
0x180022618  mov     r8d, 19Fh
0x18002261e  jmp     short loc_1800225ED
0x180022620  lea     r8, [rbp+var_28]; struct IXMLDOMDocument2 **
0x180022624  mov     edx, r12d; int
0x180022627  mov     rcx, r15; struct _SDIAG_DISPINFO *
0x18002262a  call    ?SdpBuildDisplayInformationXml@@YAJPEAU_SDIAG_DISPINFO@@HPEAPEAUIXMLDOMDocument2@@@Z; SdpBuildDisplayInformationXml(_SDIAG_DISPINFO *,int,IXMLDOMDocument2 * *)
0x18002262f  mov     ebx, eax
0x180022631  test    eax, eax
0x180022633  jns     short loc_180022658
0x180022635  mov     r9d, eax; int
0x180022638  lea     rdx, aMultiplerespon_2; "MultipleResponseInteraction::BuildChoic"...
0x18002263f  mov     r8d, 1A8h; int
0x180022645  mov     ecx, 1; Level
0x18002264a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002264f  mov     r14, [rbp+var_28]
0x180022653  jmp     loc_180022758
0x180022658  mov     r14, [rbp+var_28]
0x18002265c  xor     edx, edx; struct IXMLDOMElement *
0x18002265e  mov     r8, r14; struct IXMLDOMDocument2 *
0x180022661  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180022664  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180022669  mov     ebx, eax
0x18002266b  test    eax, eax
0x18002266d  jns     short loc_18002267A
0x18002266f  mov     r8d, 1ABh
0x180022675  jmp     loc_1800225ED
0x18002267a  lea     rax, [rbp+arg_10]
0x18002267e  xor     r9d, r9d; unsigned __int16 *
0x180022681  lea     r8, aValue; "Value"
0x180022688  mov     [rsp+58h+var_38], rax; struct IXMLDOMElement **
0x18002268d  xor     edx, edx; struct IXMLDOMElement *
0x18002268f  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180022692  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180022697  mov     ebx, eax
0x180022699  test    eax, eax
0x18002269b  jns     short loc_1800226C0
0x18002269d  mov     r9d, eax; int
0x1800226a0  mov     r8d, 1B2h; int
0x1800226a6  lea     rdx, aMultiplerespon_2; "MultipleResponseInteraction::BuildChoic"...
0x1800226ad  mov     ecx, 1; Level
0x1800226b2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800226b7  mov     rsi, [rbp+arg_10]
0x1800226bb  jmp     loc_180022758
0x1800226c0  mov     rdx, [r15+20h]
0x1800226c4  test    rdx, rdx
0x1800226c7  jnz     short loc_1800226DA
0x1800226c9  mov     r9d, 80004003h
0x1800226cf  mov     r8d, 1B4h
0x1800226d5  mov     ebx, r9d
0x1800226d8  jmp     short loc_1800226A6
0x1800226da  mov     rsi, [rbp+arg_10]
0x1800226de  mov     rcx, rsi
0x1800226e1  mov     rax, [rsi]
0x1800226e4  mov     rax, [rax+0D8h]
0x1800226eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226f0  mov     ebx, eax
0x1800226f2  test    eax, eax
0x1800226f4  jns     short loc_180022701
0x1800226f6  mov     r8d, 1B6h
0x1800226fc  jmp     loc_1800225ED
0x180022701  mov     rdx, [r15+28h]
0x180022705  test    rdx, rdx
0x180022708  jnz     short loc_18002271E
0x18002270a  mov     r9d, 80004003h
0x180022710  mov     r8d, 1BCh
0x180022716  mov     ebx, r9d
0x180022719  jmp     loc_1800225F0
0x18002271e  mov     rcx, [rbp+var_20]
0x180022722  xor     r8d, r8d
0x180022725  mov     rax, [rcx]
0x180022728  mov     rax, [rax+0A8h]
0x18002272f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022734  mov     ebx, eax
0x180022736  test    eax, eax
0x180022738  jns     short loc_180022745
0x18002273a  mov     r8d, 1BEh
0x180022740  jmp     loc_1800225ED
0x180022745  mov     [r13+0], rdi
0x180022749  mov     rcx, rdi
0x18002274c  mov     rax, [rdi]
0x18002274f  mov     rax, [rax+8]
0x180022753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022758  test    rdi, rdi
0x18002275b  jz      short loc_18002276C
0x18002275d  mov     rax, [rdi]
0x180022760  mov     rcx, rdi
0x180022763  mov     rax, [rax+10h]
0x180022767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002276c  test    r14, r14
0x18002276f  jz      short loc_180022780
0x180022771  mov     rax, [r14]
0x180022774  mov     rcx, r14
0x180022777  mov     rax, [rax+10h]
0x18002277b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022780  test    rsi, rsi
0x180022783  jz      short loc_180022794
0x180022785  mov     rax, [rsi]
0x180022788  mov     rcx, rsi
0x18002278b  mov     rax, [rax+10h]
0x18002278f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022794  mov     rcx, [rbp+var_20]
0x180022798  test    rcx, rcx
0x18002279b  jz      short loc_1800227A9
0x18002279d  mov     rax, [rcx]
0x1800227a0  mov     rax, [rax+10h]
0x1800227a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227a9  mov     eax, ebx
0x1800227ab  add     rsp, 58h
0x1800227af  pop     r15
0x1800227b1  pop     r14
0x1800227b3  pop     r13
0x1800227b5  pop     r12
0x1800227b7  pop     rdi
0x1800227b8  pop     rsi
0x1800227b9  pop     rbx
0x1800227ba  pop     rbp
0x1800227bb  retn
```
