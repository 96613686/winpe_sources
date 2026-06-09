# Interaction::BuildInteractionArray(Settings *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode *,IXMLDOMNode *,IXMLDOMNode *,IXMLDOMNode *,Interaction * *,ulong)

- ea: `0x18001f010`
- end: `0x18001f83e`
- name: `?BuildInteractionArray@Interaction@@KAJPEAVSettings@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@2222PEAPEAV1@K@Z`
- size: `2094`
- prototype: `__int64 __fastcall(struct Settings *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode *, struct Interaction **, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001fc10`

## callees

- `0x180001264`
- `0x18001f010`
- `0x18002021c`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x180029882`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Interaction::BuildInteractionArray(
        struct Settings *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3,
        struct IXMLDOMNode *a4,
        struct IXMLDOMNode *a5,
        struct IXMLDOMNode *a6,
        struct IXMLDOMNode *a7,
        struct Interaction **a8,
        unsigned int a9)
{
  struct IXMLDOMNode *v10; // rsi
  int ChildNodes; // eax
  unsigned int v12; // ebx
  int v13; // r8d
  struct IXMLDOMNodeList *v14; // r15
  unsigned int v16; // r12d
  __int64 v17; // r14
  int v18; // eax
  int v19; // eax
  char *v20; // rax
  char *v21; // rbx
  int v22; // eax
  int v23; // r9d
  int v24; // r8d
  int v25; // r8d
  unsigned int v26; // r12d
  int v27; // eax
  char *v28; // rax
  struct Interaction *v29; // rcx
  int v30; // eax
  unsigned int v31; // r12d
  int v32; // eax
  char *v33; // rax
  struct Interaction *v34; // rcx
  int v35; // eax
  unsigned int v36; // r12d
  int v37; // eax
  char *v38; // rax
  struct Interaction *v39; // rcx
  int v40; // eax
  unsigned int v41; // r12d
  int v42; // eax
  char *v43; // rax
  struct Interaction *v44; // rcx
  int v45; // eax
  unsigned int v46; // [rsp+20h] [rbp-20h] BYREF
  struct IXMLDOMNode *v47; // [rsp+28h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v48; // [rsp+30h] [rbp-10h] BYREF
  char *v49; // [rsp+38h] [rbp-8h]

  v48 = 0;
  v10 = 0;
  v47 = 0;
  v46 = 0;
  ChildNodes = SdpXmlGetChildNodes(0, a3, &v48, &v46);
  v12 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v13 = 224;
LABEL_3:
    SdpDebugTrace(1u, L"Interaction::BuildInteractionArray", v13, ChildNodes);
LABEL_4:
    v14 = v48;
    goto LABEL_5;
  }
  v16 = v46;
  v17 = 0;
  v14 = v48;
  if ( v46 )
  {
    while ( 1 )
    {
      if ( (unsigned int)v17 >= a9 )
        goto LABEL_24;
      if ( v10 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
        v47 = 0;
      }
      v18 = SdpXmlNextNode(v14, &v47);
      v12 = v18;
      if ( v18 < 0 )
      {
        v25 = 231;
        goto LABEL_35;
      }
      v10 = v47;
      v19 = SdpXmlCheckNode(v47, L"SingleResponseInteraction");
      v12 = v19;
      if ( v19 < 0 )
        break;
      if ( v19 == 1 || !v10 )
      {
        v23 = -2147467259;
        v12 = -2147467259;
LABEL_32:
        v24 = 232;
        goto LABEL_33;
      }
      v20 = (char *)operator new(0x88u);
      v49 = v20;
      v21 = v20;
      if ( v20 )
      {
        memset_0(v20, 0, 0x88u);
        *((_QWORD *)v21 + 1) = 0;
        *((_QWORD *)v21 + 2) = 0;
        *((_QWORD *)v21 + 7) = 0;
        *((_QWORD *)v21 + 10) = 0;
        *((_DWORD *)v21 + 22) = 0;
        *(_OWORD *)(v21 + 24) = 0;
        *(_OWORD *)(v21 + 40) = 0;
        *((_OWORD *)v21 + 4) = 0;
        *((_DWORD *)v21 + 24) = 0;
        *((_QWORD *)v21 + 13) = 0;
        *((_DWORD *)v21 + 28) = 0;
        *((_QWORD *)v21 + 15) = 0;
        *((_DWORD *)v21 + 32) = 0;
        *(_QWORD *)v21 = &SingleResponseInteraction::`vftable';
      }
      else
      {
        v21 = 0;
      }
      a8[v17] = (struct Interaction *)v21;
      if ( !v21 )
      {
        v23 = -2147024882;
        v24 = 235;
        v12 = -2147024882;
        goto LABEL_33;
      }
      v22 = Interaction::Initialize((Interaction *)v21, a1, v10, a2);
      v12 = v22;
      if ( v22 < 0 )
      {
        v23 = v22;
        v24 = 238;
LABEL_33:
        SdpDebugTrace(1u, L"Interaction::BuildInteractionArray", v24, v23);
        goto LABEL_5;
      }
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= v16 )
        goto LABEL_24;
    }
    v23 = v19;
    goto LABEL_32;
  }
LABEL_24:
  if ( v14 )
  {
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    v48 = 0;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a4, &v48, &v46);
  v12 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v13 = 243;
    goto LABEL_3;
  }
  v26 = v46 + v16;
  v14 = v48;
  while ( (unsigned int)v17 < v26 && (unsigned int)v17 < a9 )
  {
    if ( v10 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      v47 = 0;
    }
    v18 = SdpXmlNextNode(v14, &v47);
    v12 = v18;
    if ( v18 < 0 )
    {
      v25 = 250;
      goto LABEL_35;
    }
    v10 = v47;
    v27 = SdpXmlCheckNode(v47, L"MultipleResponseInteraction");
    v12 = v27;
    if ( v27 < 0 )
    {
      v23 = v27;
      goto LABEL_59;
    }
    if ( v27 == 1 || !v10 )
    {
      v23 = -2147467259;
      v12 = -2147467259;
LABEL_59:
      v24 = 251;
      goto LABEL_33;
    }
    v28 = (char *)operator new(0x88u);
    v49 = v28;
    v29 = (struct Interaction *)v28;
    if ( v28 )
    {
      *((_QWORD *)v28 + 1) = 0;
      *((_QWORD *)v28 + 2) = 0;
      *((_QWORD *)v28 + 7) = 0;
      *((_QWORD *)v28 + 10) = 0;
      *((_DWORD *)v28 + 22) = 0;
      *(_OWORD *)(v28 + 24) = 0;
      *(_OWORD *)(v28 + 40) = 0;
      *((_OWORD *)v28 + 4) = 0;
      *((_DWORD *)v28 + 24) = 0;
      *(_QWORD *)v28 = &MultipleResponseInteraction::`vftable';
      *((_QWORD *)v28 + 13) = 0;
      *((_DWORD *)v28 + 28) = 0;
      *((_QWORD *)v28 + 15) = 0;
      *((_DWORD *)v28 + 32) = 0;
    }
    else
    {
      v29 = 0;
    }
    a8[v17] = v29;
    if ( !v29 )
    {
      v23 = -2147024882;
      v24 = 254;
      v12 = -2147024882;
      goto LABEL_33;
    }
    v30 = Interaction::Initialize(v29, a1, v10, a2);
    v12 = v30;
    if ( v30 < 0 )
    {
      v23 = v30;
      v24 = 257;
      goto LABEL_33;
    }
    v17 = (unsigned int)(v17 + 1);
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    v48 = 0;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a5, &v48, &v46);
  v12 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v13 = 262;
    goto LABEL_3;
  }
  v31 = v46 + v26;
  v14 = v48;
  while ( (unsigned int)v17 < v31 && (unsigned int)v17 < a9 )
  {
    if ( v10 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      v47 = 0;
    }
    v18 = SdpXmlNextNode(v14, &v47);
    v12 = v18;
    if ( v18 < 0 )
    {
      v25 = 269;
      goto LABEL_35;
    }
    v10 = v47;
    v32 = SdpXmlCheckNode(v47, L"TextInteraction");
    v12 = v32;
    if ( v32 < 0 )
    {
      v23 = v32;
      goto LABEL_84;
    }
    if ( v32 == 1 || !v10 )
    {
      v23 = -2147467259;
      v12 = -2147467259;
LABEL_84:
      v24 = 270;
      goto LABEL_33;
    }
    v33 = (char *)operator new(0x68u);
    v49 = v33;
    v34 = (struct Interaction *)v33;
    if ( v33 )
    {
      *((_QWORD *)v33 + 1) = 0;
      *((_QWORD *)v33 + 2) = 0;
      *((_QWORD *)v33 + 7) = 0;
      *((_QWORD *)v33 + 10) = 0;
      *((_DWORD *)v33 + 22) = 0;
      *(_OWORD *)(v33 + 24) = 0;
      *(_OWORD *)(v33 + 40) = 0;
      *((_OWORD *)v33 + 4) = 0;
      *((_QWORD *)v33 + 12) = 0;
      *(_QWORD *)v33 = &TextInteraction::`vftable';
    }
    else
    {
      v34 = 0;
    }
    a8[v17] = v34;
    if ( !v34 )
    {
      v23 = -2147024882;
      v24 = 273;
      v12 = -2147024882;
      goto LABEL_33;
    }
    v35 = Interaction::Initialize(v34, a1, v10, a2);
    v12 = v35;
    if ( v35 < 0 )
    {
      v23 = v35;
      v24 = 276;
      goto LABEL_33;
    }
    v17 = (unsigned int)(v17 + 1);
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    v48 = 0;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a6, &v48, &v46);
  v12 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v13 = 281;
    goto LABEL_3;
  }
  v36 = v46 + v31;
  v14 = v48;
  while ( (unsigned int)v17 < v36 && (unsigned int)v17 < a9 )
  {
    if ( v10 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      v47 = 0;
    }
    v18 = SdpXmlNextNode(v14, &v47);
    v12 = v18;
    if ( v18 < 0 )
    {
      v25 = 288;
      goto LABEL_35;
    }
    v10 = v47;
    v37 = SdpXmlCheckNode(v47, L"PauseInteraction");
    v12 = v37;
    if ( v37 < 0 )
    {
      v23 = v37;
      goto LABEL_109;
    }
    if ( v37 == 1 || !v10 )
    {
      v23 = -2147467259;
      v12 = -2147467259;
LABEL_109:
      v24 = 289;
      goto LABEL_33;
    }
    v38 = (char *)operator new(0x60u);
    v49 = v38;
    v39 = (struct Interaction *)v38;
    if ( v38 )
    {
      *((_QWORD *)v38 + 1) = 0;
      *((_QWORD *)v38 + 2) = 0;
      *((_QWORD *)v38 + 7) = 0;
      *((_QWORD *)v38 + 10) = 0;
      *(_OWORD *)(v38 + 24) = 0;
      *(_OWORD *)(v38 + 40) = 0;
      *((_OWORD *)v38 + 4) = 0;
      *((_DWORD *)v38 + 22) = 0;
      *(_QWORD *)v38 = &PauseInteraction::`vftable';
    }
    else
    {
      v39 = 0;
    }
    a8[v17] = v39;
    if ( !v39 )
    {
      v23 = -2147024882;
      v24 = 292;
      v12 = -2147024882;
      goto LABEL_33;
    }
    v40 = Interaction::Initialize(v39, a1, v10, a2);
    v12 = v40;
    if ( v40 < 0 )
    {
      v23 = v40;
      v24 = 295;
      goto LABEL_33;
    }
    v17 = (unsigned int)(v17 + 1);
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    v48 = 0;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a7, &v48, &v46);
  v12 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v13 = 300;
    goto LABEL_3;
  }
  v41 = v46 + v36;
  if ( (unsigned int)v17 >= v41 )
    goto LABEL_4;
  v14 = v48;
  while ( 1 )
  {
    if ( (unsigned int)v17 >= a9 )
      goto LABEL_5;
    if ( v10 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      v47 = 0;
    }
    v18 = SdpXmlNextNode(v14, &v47);
    v12 = v18;
    if ( v18 < 0 )
      break;
    v10 = v47;
    v42 = SdpXmlCheckNode(v47, L"LaunchUIInteraction");
    v12 = v42;
    if ( v42 < 0 )
    {
      v23 = v42;
      goto LABEL_131;
    }
    if ( v42 == 1 || !v10 )
    {
      v23 = -2147467259;
      v12 = -2147467259;
LABEL_131:
      v24 = 308;
      goto LABEL_33;
    }
    v43 = (char *)operator new(0x78u);
    v49 = v43;
    v44 = (struct Interaction *)v43;
    if ( v43 )
    {
      *((_QWORD *)v43 + 1) = 0;
      *((_QWORD *)v43 + 2) = 0;
      *((_QWORD *)v43 + 7) = 0;
      *((_QWORD *)v43 + 10) = 0;
      *(_OWORD *)(v43 + 24) = 0;
      *(_OWORD *)(v43 + 40) = 0;
      *((_OWORD *)v43 + 4) = 0;
      *((_QWORD *)v43 + 12) = 0;
      *(_QWORD *)v43 = &LaunchUIInteraction::`vftable';
      *((_DWORD *)v43 + 22) = 0;
      *(_OWORD *)(v43 + 104) = 0;
    }
    else
    {
      v44 = 0;
    }
    a8[v17] = v44;
    if ( !v44 )
    {
      v23 = -2147024882;
      v24 = 311;
      v12 = -2147024882;
      goto LABEL_33;
    }
    v45 = Interaction::Initialize(v44, a1, v10, a2);
    v12 = v45;
    if ( v45 < 0 )
    {
      v23 = v45;
      v24 = 314;
      goto LABEL_33;
    }
    v17 = (unsigned int)(v17 + 1);
    if ( (unsigned int)v17 >= v41 )
      goto LABEL_5;
  }
  v25 = 307;
LABEL_35:
  SdpDebugTrace(1u, L"Interaction::BuildInteractionArray", v25, v18);
  v10 = v47;
LABEL_5:
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
  return v12;
}

```

## disassembly

```asm
0x18001f010  mov     [rsp-38h+arg_10], rbx
0x18001f015  mov     [rsp-38h+arg_8], rdx
0x18001f01a  mov     [rsp-38h+arg_0], rcx
0x18001f01f  push    rbp
0x18001f020  push    rsi
0x18001f021  push    rdi
0x18001f022  push    r12
0x18001f024  push    r13
0x18001f026  push    r14
0x18001f028  push    r15
0x18001f02a  mov     rbp, rsp
0x18001f02d  sub     rsp, 40h
0x18001f031  mov     r13, r9
0x18001f034  mov     [rbp+var_10], 0
0x18001f03c  mov     rdx, r8; struct IXMLDOMNode *
0x18001f03f  lea     r9, [rbp+var_20]; unsigned int *
0x18001f043  xor     esi, esi
0x18001f045  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x18001f049  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001f04b  mov     [rbp+var_18], rsi
0x18001f04f  mov     [rbp+var_20], esi
0x18001f052  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001f057  mov     ebx, eax
0x18001f059  test    eax, eax
0x18001f05b  jns     short loc_18001F0BB
0x18001f05d  mov     r8d, 0E0h; int
0x18001f063  lea     ecx, [rsi+1]; Level
0x18001f066  mov     r9d, eax; int
0x18001f069  lea     rdx, aInteractionBui_2; "Interaction::BuildInteractionArray"
0x18001f070  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001f075  mov     r15, [rbp+var_10]
0x18001f079  test    r15, r15
0x18001f07c  jz      short loc_18001F08D
0x18001f07e  mov     rax, [r15]
0x18001f081  mov     rcx, r15
0x18001f084  mov     rax, [rax+10h]
0x18001f088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f08d  test    rsi, rsi
0x18001f090  jz      short loc_18001F0A1
0x18001f092  mov     rax, [rsi]
0x18001f095  mov     rcx, rsi
0x18001f098  mov     rax, [rax+10h]
0x18001f09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0a1  mov     eax, ebx
0x18001f0a3  mov     rbx, [rsp+40h+arg_10]
0x18001f0ab  add     rsp, 40h
0x18001f0af  pop     r15
0x18001f0b1  pop     r14
0x18001f0b3  pop     r13
0x18001f0b5  pop     r12
0x18001f0b7  pop     rdi
0x18001f0b8  pop     rsi
0x18001f0b9  pop     rbp
0x18001f0ba  retn
0x18001f0bb  mov     r12d, [rbp+var_20]
0x18001f0bf  xor     r14d, r14d
0x18001f0c2  mov     r15, [rbp+var_10]
0x18001f0c6  lea     edi, [r14+1]
0x18001f0ca  test    r12d, r12d
0x18001f0cd  jz      loc_18001F1DF
0x18001f0d3  cmp     r14d, [rbp+arg_40]
0x18001f0da  jnb     loc_18001F1DF
0x18001f0e0  test    rsi, rsi
0x18001f0e3  jz      short loc_18001F0FC
0x18001f0e5  mov     rax, [rsi]
0x18001f0e8  mov     rcx, rsi
0x18001f0eb  mov     rax, [rax+10h]
0x18001f0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0f4  mov     [rbp+var_18], 0
0x18001f0fc  lea     rdx, [rbp+var_18]; struct IXMLDOMNode **
0x18001f100  mov     rcx, r15; struct IXMLDOMNodeList *
0x18001f103  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001f108  mov     ebx, eax
0x18001f10a  test    eax, eax
0x18001f10c  js      loc_18001F263
0x18001f112  mov     rsi, [rbp+var_18]
0x18001f116  lea     rdx, aSingleresponse; "SingleResponseInteraction"
0x18001f11d  mov     rcx, rsi; struct IXMLDOMNode *
0x18001f120  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001f125  mov     ebx, eax
0x18001f127  test    eax, eax
0x18001f129  js      loc_18001F247
0x18001f12f  cmp     eax, edi
0x18001f131  jz      loc_18001F23C
0x18001f137  test    rsi, rsi
0x18001f13a  jz      loc_18001F23C
0x18001f140  mov     ecx, 88h; Size
0x18001f145  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f14a  xor     edx, edx; Val
0x18001f14c  mov     [rbp+var_8], rax
0x18001f150  mov     rbx, rax
0x18001f153  test    rax, rax
0x18001f156  jz      short loc_18001F1AA
0x18001f158  mov     r8d, 88h; Size
0x18001f15e  mov     rcx, rax; void *
0x18001f161  call    memset_0
0x18001f166  xor     edx, edx
0x18001f168  lea     rax, ??_7SingleResponseInteraction@@6B@; const SingleResponseInteraction::`vftable'
0x18001f16f  xorps   xmm0, xmm0
0x18001f172  mov     [rbx+8], rdx
0x18001f176  mov     [rbx+10h], rdx
0x18001f17a  mov     [rbx+38h], rdx
0x18001f17e  mov     [rbx+50h], rdx
0x18001f182  mov     [rbx+58h], edx
0x18001f185  movups  xmmword ptr [rbx+18h], xmm0
0x18001f189  movups  xmmword ptr [rbx+28h], xmm0
0x18001f18d  movups  xmmword ptr [rbx+40h], xmm0
0x18001f191  mov     [rbx+60h], edx
0x18001f194  mov     [rbx+68h], rdx
0x18001f198  mov     [rbx+70h], edx
0x18001f19b  mov     [rbx+78h], rdx
0x18001f19f  mov     [rbx+80h], edx
0x18001f1a5  mov     [rbx], rax
0x18001f1a8  jmp     short loc_18001F1AD
0x18001f1aa  mov     rbx, rdx
0x18001f1ad  mov     rcx, [rbp+arg_38]
0x18001f1b1  mov     [rcx+r14*8], rbx
0x18001f1b5  test    rbx, rbx
0x18001f1b8  jz      short loc_18001F22B
0x18001f1ba  mov     r9, [rbp+arg_8]; struct IXMLDOMDocument2 *
0x18001f1be  mov     r8, rsi; struct IXMLDOMNode *
0x18001f1c1  mov     rdx, [rbp+arg_0]; struct Settings *
0x18001f1c5  mov     rcx, rbx; this
0x18001f1c8  call    ?Initialize@Interaction@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@PEAUIXMLDOMDocument2@@@Z; Interaction::Initialize(Settings *,IXMLDOMNode *,IXMLDOMDocument2 *)
0x18001f1cd  mov     ebx, eax
0x18001f1cf  test    eax, eax
0x18001f1d1  js      short loc_18001F220
0x18001f1d3  add     r14d, edi
0x18001f1d6  cmp     r14d, r12d
0x18001f1d9  jb      loc_18001F0D3
0x18001f1df  test    r15, r15
0x18001f1e2  jz      short loc_18001F1FB
0x18001f1e4  mov     rax, [r15]
0x18001f1e7  mov     rcx, r15
0x18001f1ea  mov     rax, [rax+10h]
0x18001f1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1f3  mov     [rbp+var_10], 0
0x18001f1fb  lea     r9, [rbp+var_20]; unsigned int *
0x18001f1ff  mov     rdx, r13; struct IXMLDOMNode *
0x18001f202  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x18001f206  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001f208  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001f20d  mov     ebx, eax
0x18001f20f  test    eax, eax
0x18001f211  jns     short loc_18001F283
0x18001f213  mov     r8d, 0F3h
0x18001f219  mov     ecx, edi
0x18001f21b  jmp     loc_18001F066
0x18001f220  mov     r9d, eax
0x18001f223  mov     r8d, 0EEh
0x18001f229  jmp     short loc_18001F250
0x18001f22b  mov     r9d, 8007000Eh
0x18001f231  mov     r8d, 0EBh
0x18001f237  mov     ebx, r9d
0x18001f23a  jmp     short loc_18001F250
0x18001f23c  mov     r9d, 80004005h
0x18001f242  mov     ebx, r9d
0x18001f245  jmp     short loc_18001F24A
0x18001f247  mov     r9d, eax; int
0x18001f24a  mov     r8d, 0E8h; int
0x18001f250  lea     rdx, aInteractionBui_2; "Interaction::BuildInteractionArray"
0x18001f257  mov     ecx, edi; Level
0x18001f259  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001f25e  jmp     loc_18001F079
0x18001f263  mov     r8d, 0E7h; int
0x18001f269  mov     r9d, eax; int
0x18001f26c  lea     rdx, aInteractionBui_2; "Interaction::BuildInteractionArray"
0x18001f273  mov     ecx, edi; Level
0x18001f275  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001f27a  mov     rsi, [rbp+var_18]
0x18001f27e  jmp     loc_18001F079
0x18001f283  add     r12d, [rbp+var_20]
0x18001f287  mov     r15, [rbp+var_10]
0x18001f28b  mov     r13, [rbp+arg_38]
0x18001f28f  jmp     loc_18001F381
0x18001f294  cmp     r14d, [rbp+arg_40]
0x18001f29b  jnb     loc_18001F38A
0x18001f2a1  test    rsi, rsi
0x18001f2a4  jz      short loc_18001F2BD
0x18001f2a6  mov     rax, [rsi]
0x18001f2a9  mov     rcx, rsi
0x18001f2ac  mov     rax, [rax+10h]
0x18001f2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b5  mov     [rbp+var_18], 0
0x18001f2bd  lea     rdx, [rbp+var_18]; struct IXMLDOMNode **
0x18001f2c1  mov     rcx, r15; struct IXMLDOMNodeList *
0x18001f2c4  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001f2c9  mov     ebx, eax
0x18001f2cb  test    eax, eax
0x18001f2cd  js      loc_18001F405
0x18001f2d3  mov     rsi, [rbp+var_18]
0x18001f2d7  lea     rdx, aMultiplerespon; "MultipleResponseInteraction"
0x18001f2de  mov     rcx, rsi; struct IXMLDOMNode *
0x18001f2e1  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001f2e6  mov     ebx, eax
0x18001f2e8  test    eax, eax
0x18001f2ea  js      loc_18001F3F7
0x18001f2f0  cmp     eax, edi
0x18001f2f2  jz      loc_18001F3EC
0x18001f2f8  xor     ebx, ebx
0x18001f2fa  test    rsi, rsi
0x18001f2fd  jz      loc_18001F3EC
0x18001f303  mov     ecx, 88h; Size
0x18001f308  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f30d  mov     [rbp+var_8], rax
0x18001f311  mov     rcx, rax
0x18001f314  test    rax, rax
0x18001f317  jz      short loc_18001F35B
0x18001f319  mov     [rax+8], rbx
0x18001f31d  xorps   xmm0, xmm0
0x18001f320  mov     [rax+10h], rbx
0x18001f324  mov     [rax+38h], rbx
0x18001f328  mov     [rax+50h], rbx
0x18001f32c  mov     [rax+58h], ebx
0x18001f32f  movups  xmmword ptr [rax+18h], xmm0
0x18001f333  movups  xmmword ptr [rax+28h], xmm0
0x18001f337  movups  xmmword ptr [rax+40h], xmm0
0x18001f33b  lea     rax, ??_7MultipleResponseInteraction@@6B@; const MultipleResponseInteraction::`vftable'
0x18001f342  mov     [rcx+60h], ebx
0x18001f345  mov     [rcx], rax
0x18001f348  mov     [rcx+68h], rbx
0x18001f34c  mov     [rcx+70h], ebx
0x18001f34f  mov     [rcx+78h], rbx
0x18001f353  mov     [rcx+80h], ebx
0x18001f359  jmp     short loc_18001F35E
0x18001f35b  mov     rcx, rbx; this
0x18001f35e  mov     [r13+r14*8+0], rcx
0x18001f363  test    rcx, rcx
0x18001f366  jz      short loc_18001F3D8
0x18001f368  mov     r9, [rbp+arg_8]; struct IXMLDOMDocument2 *
0x18001f36c  mov     r8, rsi; struct IXMLDOMNode *
0x18001f36f  mov     rdx, [rbp+arg_0]; struct Settings *
0x18001f373  call    ?Initialize@Interaction@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@PEAUIXMLDOMDocument2@@@Z; Interaction::Initialize(Settings *,IXMLDOMNode *,IXMLDOMDocument2 *)
0x18001f378  mov     ebx, eax
0x18001f37a  test    eax, eax
0x18001f37c  js      short loc_18001F3CA
0x18001f37e  add     r14d, edi
0x18001f381  cmp     r14d, r12d
0x18001f384  jb      loc_18001F294
0x18001f38a  test    r15, r15
0x18001f38d  jz      short loc_18001F3A6
0x18001f38f  mov     rax, [r15]
0x18001f392  mov     rcx, r15
0x18001f395  mov     rax, [rax+10h]
0x18001f399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f39e  mov     [rbp+var_10], 0
0x18001f3a6  mov     rdx, [rbp+arg_20]; struct IXMLDOMNode *
0x18001f3aa  lea     r9, [rbp+var_20]; unsigned int *
0x18001f3ae  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x18001f3b2  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001f3b4  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001f3b9  mov     ebx, eax
0x18001f3bb  test    eax, eax
0x18001f3bd  jns     short loc_18001F410
0x18001f3bf  mov     r8d, 106h
0x18001f3c5  jmp     loc_18001F219
0x18001f3ca  mov     r9d, eax
0x18001f3cd  mov     r8d, 101h
0x18001f3d3  jmp     loc_18001F250
0x18001f3d8  mov     r9d, 8007000Eh
0x18001f3de  mov     r8d, 0FEh
0x18001f3e4  mov     ebx, r9d
0x18001f3e7  jmp     loc_18001F250
0x18001f3ec  mov     r9d, 80004005h
0x18001f3f2  mov     ebx, r9d
0x18001f3f5  jmp     short loc_18001F3FA
0x18001f3f7  mov     r9d, eax
0x18001f3fa  mov     r8d, 0FBh
0x18001f400  jmp     loc_18001F250
0x18001f405  mov     r8d, 0FAh
0x18001f40b  jmp     loc_18001F269
0x18001f410  add     r12d, [rbp+var_20]
0x18001f414  mov     r15, [rbp+var_10]
0x18001f418  jmp     loc_18001F4F8
0x18001f41d  cmp     r14d, [rbp+arg_40]
0x18001f424  jnb     loc_18001F501
0x18001f42a  test    rsi, rsi
0x18001f42d  jz      short loc_18001F446
0x18001f42f  mov     rax, [rsi]
0x18001f432  mov     rcx, rsi
0x18001f435  mov     rax, [rax+10h]
0x18001f439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f43e  mov     [rbp+var_18], 0
0x18001f446  lea     rdx, [rbp+var_18]; struct IXMLDOMNode **
0x18001f44a  mov     rcx, r15; struct IXMLDOMNodeList *
0x18001f44d  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001f452  mov     ebx, eax
0x18001f454  test    eax, eax
0x18001f456  js      loc_18001F57C
0x18001f45c  mov     rsi, [rbp+var_18]
0x18001f460  lea     rdx, aTextinteractio; "TextInteraction"
0x18001f467  mov     rcx, rsi; struct IXMLDOMNode *
0x18001f46a  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001f46f  mov     ebx, eax
0x18001f471  test    eax, eax
0x18001f473  js      loc_18001F56E
0x18001f479  cmp     eax, edi
0x18001f47b  jz      loc_18001F563
0x18001f481  xor     ebx, ebx
0x18001f483  test    rsi, rsi
  ... truncated ...
```
