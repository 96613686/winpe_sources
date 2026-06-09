# Verifier::ParseVerifierXml(IXMLDOMNode *)

- ea: `0x18001d20c`
- end: `0x18001d41a`
- name: `?ParseVerifierXml@Verifier@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(Verifier *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a424`

## callees

- `0x18001d0f0`
- `0x18001d20c`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x18001d368`: `ExtensionPoint`
- `0x18001d23a`: `Verifier::ParseVerifierXml`
- `0x18001d2be`: `Verifier::ParseVerifierXml`
- `0x18001d3d3`: `Verifier::ParseVerifierXml`

## pseudocode

```c
__int64 __fastcall Verifier::ParseVerifierXml(Verifier *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rsi
  unsigned int v4; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r14
  int v7; // r9d
  int v8; // r8d
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int v16; // [rsp+58h] [rbp+38h] BYREF
  struct IXMLDOMNode *v17; // [rsp+60h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v18; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Verifier::ParseVerifierXml", 186, -2147024809);
    return v4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v18, &v16);
  v6 = v18;
  v4 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = ChildNodes;
    v8 = 189;
LABEL_30:
    SdpDebugTrace(1u, L"Verifier::ParseVerifierXml", v8, v7);
    goto LABEL_31;
  }
  if ( !v16 )
  {
    v4 = 1;
    goto LABEL_31;
  }
  if ( v16 < 2 )
  {
    v7 = -2147024809;
    v8 = 198;
LABEL_29:
    v4 = v7;
    goto LABEL_30;
  }
  v9 = SdpXmlNextNode(v18, &v17);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 206;
LABEL_11:
    SdpDebugTrace(1u, L"Verifier::ParseVerifierXml", v10, v9);
    v2 = v17;
    goto LABEL_31;
  }
  v2 = v17;
  v11 = SdpXmlCheckNode(v17, L"Script");
  v4 = v11;
  if ( v11 < 0 )
  {
    v7 = v11;
    v8 = 207;
    goto LABEL_30;
  }
  if ( v11 == 1 || !v2 )
  {
    v8 = 207;
    goto LABEL_28;
  }
  v12 = Verifier::InitializeScript(this, v2);
  v4 = v12;
  if ( v12 < 0 )
  {
    v7 = v12;
    v8 = 210;
    goto LABEL_30;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v17 = 0;
  v9 = SdpXmlNextNode(v6, &v17);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 218;
    goto LABEL_11;
  }
  v2 = v17;
  v13 = SdpXmlCheckNode(v17, L"ExtensionPoint");
  v4 = v13;
  if ( v13 < 0 )
  {
    v7 = v13;
    v8 = 219;
    goto LABEL_30;
  }
  if ( v13 == 1 || !v2 )
  {
    v8 = 219;
LABEL_28:
    v7 = -2147467259;
    goto LABEL_29;
  }
  v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, char *))v2->lpVtbl->cloneNode)(
          v2,
          0xFFFFFFFFLL,
          (char *)this + 16);
  v4 = v14;
  if ( v14 < 0 )
  {
    v7 = v14;
    v8 = 222;
    goto LABEL_30;
  }
LABEL_31:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return v4;
}

```

## disassembly

```asm
0x18001d20c  push    rbp
0x18001d20e  push    rbx
0x18001d20f  push    rsi
0x18001d210  push    r14
0x18001d212  push    r15
0x18001d214  mov     rbp, rsp
0x18001d217  sub     rsp, 20h
0x18001d21b  xor     esi, esi
0x18001d21d  mov     [rbp+arg_18], 0
0x18001d225  mov     [rbp+arg_10], rsi
0x18001d229  mov     r15, rcx
0x18001d22c  mov     [rbp+arg_8], esi
0x18001d22f  test    rdx, rdx
0x18001d232  jnz     short loc_18001D257
0x18001d234  mov     r9d, 80070057h; int
0x18001d23a  lea     rdx, aVerifierParsev; "Verifier::ParseVerifierXml"
0x18001d241  mov     r8d, 0BAh; int
0x18001d247  lea     ecx, [rsi+1]; Level
0x18001d24a  mov     ebx, r9d
0x18001d24d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d252  jmp     loc_18001D40C
0x18001d257  lea     r9, [rbp+arg_8]; unsigned int *
0x18001d25b  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001d25d  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18001d261  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001d266  mov     r14, [rbp+arg_18]
0x18001d26a  mov     ebx, eax
0x18001d26c  test    eax, eax
0x18001d26e  jns     short loc_18001D27E
0x18001d270  mov     r9d, eax
0x18001d273  mov     r8d, 0BDh
0x18001d279  jmp     loc_18001D3D3
0x18001d27e  mov     eax, [rbp+arg_8]
0x18001d281  test    eax, eax
0x18001d283  jnz     short loc_18001D28D
0x18001d285  lea     ebx, [rax+1]
0x18001d288  jmp     loc_18001D3E4
0x18001d28d  cmp     eax, 2
0x18001d290  jnb     short loc_18001D2A3
0x18001d292  mov     r9d, 80070057h
0x18001d298  mov     r8d, 0C6h
0x18001d29e  jmp     loc_18001D3D0
0x18001d2a3  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001d2a7  mov     rcx, r14; struct IXMLDOMNodeList *
0x18001d2aa  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001d2af  mov     ebx, eax
0x18001d2b1  test    eax, eax
0x18001d2b3  jns     short loc_18001D2D8
0x18001d2b5  mov     r8d, 0CEh; int
0x18001d2bb  mov     r9d, eax; int
0x18001d2be  lea     rdx, aVerifierParsev; "Verifier::ParseVerifierXml"
0x18001d2c5  mov     ecx, 1; Level
0x18001d2ca  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d2cf  mov     rsi, [rbp+arg_10]
0x18001d2d3  jmp     loc_18001D3E4
0x18001d2d8  mov     rsi, [rbp+arg_10]
0x18001d2dc  lea     rdx, aScript; "Script"
0x18001d2e3  mov     rcx, rsi; struct IXMLDOMNode *
0x18001d2e6  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001d2eb  mov     ebx, eax
0x18001d2ed  test    eax, eax
0x18001d2ef  jns     short loc_18001D2FF
0x18001d2f1  mov     r9d, eax
0x18001d2f4  mov     r8d, 0CFh
0x18001d2fa  jmp     loc_18001D3D3
0x18001d2ff  cmp     eax, 1
0x18001d302  jz      loc_18001D3C4
0x18001d308  test    rsi, rsi
0x18001d30b  jz      loc_18001D3C4
0x18001d311  mov     rdx, rsi; struct IXMLDOMNode *
0x18001d314  mov     rcx, r15; this
0x18001d317  call    ?InitializeScript@Verifier@@AEAAJPEAUIXMLDOMNode@@@Z; Verifier::InitializeScript(IXMLDOMNode *)
0x18001d31c  mov     ebx, eax
0x18001d31e  test    eax, eax
0x18001d320  jns     short loc_18001D330
0x18001d322  mov     r9d, eax
0x18001d325  mov     r8d, 0D2h
0x18001d32b  jmp     loc_18001D3D3
0x18001d330  mov     rax, [rsi]
0x18001d333  mov     rcx, rsi
0x18001d336  mov     rax, [rax+10h]
0x18001d33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d33f  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001d343  mov     [rbp+arg_10], 0
0x18001d34b  mov     rcx, r14; struct IXMLDOMNodeList *
0x18001d34e  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001d353  mov     ebx, eax
0x18001d355  test    eax, eax
0x18001d357  jns     short loc_18001D364
0x18001d359  mov     r8d, 0DAh
0x18001d35f  jmp     loc_18001D2BB
0x18001d364  mov     rsi, [rbp+arg_10]
0x18001d368  lea     rdx, aExtensionpoint_0; "ExtensionPoint"
0x18001d36f  mov     rcx, rsi; struct IXMLDOMNode *
0x18001d372  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001d377  mov     ebx, eax
0x18001d379  test    eax, eax
0x18001d37b  jns     short loc_18001D388
0x18001d37d  mov     r9d, eax
0x18001d380  mov     r8d, 0DBh
0x18001d386  jmp     short loc_18001D3D3
0x18001d388  cmp     eax, 1
0x18001d38b  jz      short loc_18001D3BC
0x18001d38d  test    rsi, rsi
0x18001d390  jz      short loc_18001D3BC
0x18001d392  mov     rax, [rsi]
0x18001d395  lea     r8, [r15+10h]
0x18001d399  or      edx, 0FFFFFFFFh
0x18001d39c  mov     rcx, rsi
0x18001d39f  mov     rax, [rax+0C0h]
0x18001d3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ab  mov     ebx, eax
0x18001d3ad  test    eax, eax
0x18001d3af  jns     short loc_18001D3E4
0x18001d3b1  mov     r9d, eax
0x18001d3b4  mov     r8d, 0DEh
0x18001d3ba  jmp     short loc_18001D3D3
0x18001d3bc  mov     r8d, 0DBh
0x18001d3c2  jmp     short loc_18001D3CA
0x18001d3c4  mov     r8d, 0CFh; int
0x18001d3ca  mov     r9d, 80004005h; int
0x18001d3d0  mov     ebx, r9d
0x18001d3d3  lea     rdx, aVerifierParsev; "Verifier::ParseVerifierXml"
0x18001d3da  mov     ecx, 1; Level
0x18001d3df  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d3e4  test    r14, r14
0x18001d3e7  jz      short loc_18001D3F8
0x18001d3e9  mov     rax, [r14]
0x18001d3ec  mov     rcx, r14
0x18001d3ef  mov     rax, [rax+10h]
0x18001d3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3f8  test    rsi, rsi
0x18001d3fb  jz      short loc_18001D40C
0x18001d3fd  mov     rax, [rsi]
0x18001d400  mov     rcx, rsi
0x18001d403  mov     rax, [rax+10h]
0x18001d407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40c  mov     eax, ebx
0x18001d40e  add     rsp, 20h
0x18001d412  pop     r15
0x18001d414  pop     r14
0x18001d416  pop     rsi
0x18001d417  pop     rbx
0x18001d418  pop     rbp
0x18001d419  retn
```
