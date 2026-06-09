# Resolver::ParseResolverXml(IXMLDOMNode *)

- ea: `0x18001c6e8`
- end: `0x18001cb88`
- name: `?ParseResolverXml@Resolver@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `1184`
- prototype: `__int64 __fastcall(Resolver *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a0bc`

## callees

- `0x180003b2c`
- `0x18000615c`
- `0x18001c5ac`
- `0x18001c6e8`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001c83e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c83e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9e0`

## string_xrefs

- `0x18001cab8`: `ExtensionPoint`
- `0x18001c719`: `Resolver::ParseResolverXml`
- `0x18001c79e`: `Resolver::ParseResolverXml`
- `0x18001cb42`: `Resolver::ParseResolverXml`

## pseudocode

```c
__int64 __fastcall Resolver::ParseResolverXml(Resolver *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  int v4; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r12
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int v10; // r8d
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v12; // eax
  OLECHAR *v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct IXMLDOMNode v18; // rax
  int v19; // eax
  OLECHAR *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  OLECHAR *v26; // [rsp+68h] [rbp+48h] BYREF
  struct IXMLDOMNode *v27; // [rsp+70h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v28; // [rsp+78h] [rbp+58h] BYREF

  v2 = 0;
  v28 = 0;
  v27 = 0;
  LODWORD(v26) = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Resolver::ParseResolverXml", 260, -2147024809);
    return (unsigned int)v4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v28, (unsigned int *)&v26);
  v6 = v28;
  v4 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = 263;
LABEL_5:
    v8 = ChildNodes;
LABEL_71:
    SdpDebugTrace(1u, L"Resolver::ParseResolverXml", v7, v8);
    goto LABEL_72;
  }
  if ( (unsigned int)v26 < 5 )
  {
    v8 = -2147024809;
    v7 = 267;
LABEL_70:
    v4 = v8;
    goto LABEL_71;
  }
  v9 = SdpXmlNextNode(v28, &v27);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 275;
LABEL_10:
    SdpDebugTrace(1u, L"Resolver::ParseResolverXml", v10, v9);
    v2 = v27;
    goto LABEL_72;
  }
  v2 = v27;
  ChildNodes = SdpXmlCheckNode(v27, L"ID");
  v4 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = 276;
    goto LABEL_5;
  }
  if ( ChildNodes == 1 || !v2 )
  {
    v7 = 276;
    goto LABEL_69;
  }
  lpVtbl = v2->lpVtbl;
  v26 = 0;
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR **))lpVtbl->get_text)(v2, &v26);
  v4 = v12;
  if ( v12 >= 0 )
  {
    v13 = 0;
    *((_QWORD *)this + 2) = v26;
    v26 = 0;
  }
  else
  {
    SdpDebugTrace(1u, L"Resolver::SetId", 373, v12);
    v13 = v26;
  }
  if ( v13 )
    SysFreeString(v13);
  if ( v4 < 0 )
  {
    v7 = 279;
LABEL_22:
    v8 = v4;
    goto LABEL_71;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v27 = 0;
  v9 = SdpXmlNextNode(v6, &v27);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 287;
    goto LABEL_10;
  }
  v2 = v27;
  v14 = SdpXmlCheckNode(v27, L"DisplayInformation");
  v4 = v14;
  if ( v14 < 0 )
  {
    v8 = v14;
    v7 = 288;
    goto LABEL_71;
  }
  if ( v14 == 1 || !v2 )
  {
    v7 = 288;
    goto LABEL_69;
  }
  v15 = SdpParseDisplayInformation(v2, (Resolver *)((char *)this + 32));
  v4 = v15;
  if ( v15 < 0 )
  {
    v8 = v15;
    v7 = 291;
    goto LABEL_71;
  }
  if ( !*(_QWORD *)this )
  {
    v4 = -2147467261;
    v7 = 293;
    goto LABEL_22;
  }
  v16 = SdpLocalizeDisplayInformation(*(struct Settings **)this, (Resolver *)((char *)this + 32), 0);
  v4 = v16;
  if ( v16 < 0 )
  {
    v8 = v16;
    v7 = 296;
    goto LABEL_71;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v27 = 0;
  v9 = SdpXmlNextNode(v6, &v27);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 304;
    goto LABEL_10;
  }
  v2 = v27;
  v17 = SdpXmlCheckNode(v27, L"RequiresConsent");
  v4 = v17;
  if ( v17 < 0 )
  {
    v8 = v17;
    v7 = 305;
    goto LABEL_71;
  }
  if ( v17 == 1 || !v2 )
  {
    v7 = 305;
    goto LABEL_69;
  }
  v18.lpVtbl = v2->lpVtbl;
  v26 = 0;
  v19 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR **))v18.lpVtbl->get_text)(v2, &v26);
  v4 = v19;
  if ( v19 >= 0 )
  {
    v20 = 0;
    *((_QWORD *)this + 8) = v26;
    v26 = 0;
  }
  else
  {
    SdpDebugTrace(1u, L"Resolver::SetConsent", 398, v19);
    v20 = v26;
  }
  if ( v20 )
    SysFreeString(v20);
  if ( v4 < 0 )
  {
    v7 = 308;
    goto LABEL_22;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v27 = 0;
  v9 = SdpXmlNextNode(v6, &v27);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 316;
    goto LABEL_10;
  }
  v2 = v27;
  v21 = SdpXmlCheckNode(v27, L"Script");
  v4 = v21;
  if ( v21 < 0 )
  {
    v8 = v21;
    v7 = 317;
    goto LABEL_71;
  }
  if ( v21 == 1 || !v2 )
  {
    v7 = 317;
    goto LABEL_69;
  }
  v22 = Resolver::InitializeScript(this, v2);
  v4 = v22;
  if ( v22 < 0 )
  {
    v8 = v22;
    v7 = 320;
    goto LABEL_71;
  }
  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  v27 = 0;
  v9 = SdpXmlNextNode(v6, &v27);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = 328;
    goto LABEL_10;
  }
  v2 = v27;
  v23 = SdpXmlCheckNode(v27, L"ExtensionPoint");
  v4 = v23;
  if ( v23 < 0 )
  {
    v8 = v23;
    v7 = 329;
    goto LABEL_71;
  }
  if ( v23 == 1 || !v2 )
  {
    v7 = 329;
LABEL_69:
    v8 = -2147467259;
    goto LABEL_70;
  }
  v24 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, char *))v2->lpVtbl->cloneNode)(
          v2,
          0xFFFFFFFFLL,
          (char *)this + 24);
  v4 = v24;
  if ( v24 < 0 )
  {
    v8 = v24;
    v7 = 332;
    goto LABEL_71;
  }
LABEL_72:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c6e8  push    rbp
0x18001c6ea  push    rbx
0x18001c6eb  push    rsi
0x18001c6ec  push    rdi
0x18001c6ed  push    r12
0x18001c6ef  push    r14
0x18001c6f1  push    r15
0x18001c6f3  mov     rbp, rsp
0x18001c6f6  sub     rsp, 20h
0x18001c6fa  xor     edi, edi
0x18001c6fc  mov     [rbp+arg_18], 0
0x18001c704  mov     [rbp+arg_10], rdi
0x18001c708  mov     r14, rcx
0x18001c70b  mov     dword ptr [rbp+arg_8], edi
0x18001c70e  test    rdx, rdx
0x18001c711  jnz     short loc_18001C736
0x18001c713  mov     r9d, 80070057h; int
0x18001c719  lea     rdx, aResolverParser; "Resolver::ParseResolverXml"
0x18001c720  mov     r8d, 104h; int
0x18001c726  lea     ecx, [rdi+1]; Level
0x18001c729  mov     ebx, r9d
0x18001c72c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c731  jmp     loc_18001CB77
0x18001c736  lea     r9, [rbp+arg_8]; unsigned int *
0x18001c73a  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001c73c  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18001c740  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001c745  mov     r12, [rbp+arg_18]
0x18001c749  mov     ebx, eax
0x18001c74b  test    eax, eax
0x18001c74d  jns     short loc_18001C762
0x18001c74f  mov     r8d, 107h
0x18001c755  mov     r9d, eax
0x18001c758  mov     ecx, 1
0x18001c75d  jmp     loc_18001CB42
0x18001c762  cmp     dword ptr [rbp+arg_8], 5
0x18001c766  jnb     short loc_18001C77E
0x18001c768  mov     r9d, 80070057h
0x18001c76e  mov     r8d, 10Bh
0x18001c774  mov     ecx, 1
0x18001c779  jmp     loc_18001CB3F
0x18001c77e  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001c782  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001c785  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001c78a  mov     ebx, eax
0x18001c78c  test    eax, eax
0x18001c78e  jns     short loc_18001C7B3
0x18001c790  mov     r8d, 113h; int
0x18001c796  mov     ecx, 1; Level
0x18001c79b  mov     r9d, eax; int
0x18001c79e  lea     rdx, aResolverParser; "Resolver::ParseResolverXml"
0x18001c7a5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c7aa  mov     rdi, [rbp+arg_10]
0x18001c7ae  jmp     loc_18001CB4E
0x18001c7b3  mov     rdi, [rbp+arg_10]
0x18001c7b7  lea     rdx, aId; "ID"
0x18001c7be  mov     rcx, rdi; struct IXMLDOMNode *
0x18001c7c1  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001c7c6  mov     ebx, eax
0x18001c7c8  test    eax, eax
0x18001c7ca  jns     short loc_18001C7D4
0x18001c7cc  mov     r8d, 114h
0x18001c7d2  jmp     short loc_18001C755
0x18001c7d4  mov     esi, 1
0x18001c7d9  cmp     eax, esi
0x18001c7db  jz      loc_18001CB31
0x18001c7e1  test    rdi, rdi
0x18001c7e4  jz      loc_18001CB31
0x18001c7ea  mov     rax, [rdi]
0x18001c7ed  lea     rdx, [rbp+arg_8]
0x18001c7f1  mov     rcx, rdi
0x18001c7f4  mov     [rbp+arg_8], 0
0x18001c7fc  mov     rax, [rax+0D0h]
0x18001c803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c808  mov     ebx, eax
0x18001c80a  test    eax, eax
0x18001c80c  jns     short loc_18001C82B
0x18001c80e  mov     r9d, eax; int
0x18001c811  lea     rdx, aResolverSetid; "Resolver::SetId"
0x18001c818  mov     r8d, 175h; int
0x18001c81e  mov     ecx, esi; Level
0x18001c820  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c825  mov     rcx, [rbp+arg_8]
0x18001c829  jmp     short loc_18001C839
0x18001c82b  mov     rax, [rbp+arg_8]
0x18001c82f  xor     ecx, ecx; bstrString
0x18001c831  mov     [r14+10h], rax
0x18001c835  mov     [rbp+arg_8], rcx
0x18001c839  test    rcx, rcx
0x18001c83c  jz      short loc_18001C844
0x18001c83e  call    cs:__imp_SysFreeString
0x18001c844  test    ebx, ebx
0x18001c846  jns     short loc_18001C858
0x18001c848  mov     r8d, 117h
0x18001c84e  mov     r9d, ebx
0x18001c851  mov     ecx, esi
0x18001c853  jmp     loc_18001CB42
0x18001c858  test    rdi, rdi
0x18001c85b  jz      short loc_18001C874
0x18001c85d  mov     rax, [rdi]
0x18001c860  mov     rcx, rdi
0x18001c863  mov     rax, [rax+10h]
0x18001c867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c86c  mov     [rbp+arg_10], 0
0x18001c874  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001c878  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001c87b  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001c880  mov     ebx, eax
0x18001c882  test    eax, eax
0x18001c884  jns     short loc_18001C893
0x18001c886  mov     r8d, 11Fh
0x18001c88c  mov     ecx, esi
0x18001c88e  jmp     loc_18001C79B
0x18001c893  mov     rdi, [rbp+arg_10]
0x18001c897  lea     rdx, aDisplayinforma; "DisplayInformation"
0x18001c89e  mov     rcx, rdi; struct IXMLDOMNode *
0x18001c8a1  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001c8a6  mov     ebx, eax
0x18001c8a8  test    eax, eax
0x18001c8aa  jns     short loc_18001C8B7
0x18001c8ac  mov     r9d, eax
0x18001c8af  mov     r8d, 120h
0x18001c8b5  jmp     short loc_18001C851
0x18001c8b7  cmp     eax, esi
0x18001c8b9  jz      loc_18001CB29
0x18001c8bf  test    rdi, rdi
0x18001c8c2  jz      loc_18001CB29
0x18001c8c8  lea     rdx, [r14+20h]; struct _SDIAG_DISPINFO *
0x18001c8cc  mov     rcx, rdi; struct IXMLDOMNode *
0x18001c8cf  call    ?SdpParseDisplayInformation@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_DISPINFO@@@Z; SdpParseDisplayInformation(IXMLDOMNode *,_SDIAG_DISPINFO *)
0x18001c8d4  mov     ebx, eax
0x18001c8d6  test    eax, eax
0x18001c8d8  jns     short loc_18001C8E8
0x18001c8da  mov     r9d, eax
0x18001c8dd  mov     r8d, 123h
0x18001c8e3  jmp     loc_18001C851
0x18001c8e8  mov     rcx, [r14]; struct Settings *
0x18001c8eb  test    rcx, rcx
0x18001c8ee  jnz     short loc_18001C900
0x18001c8f0  mov     ebx, 80004003h
0x18001c8f5  mov     r8d, 125h
0x18001c8fb  jmp     loc_18001C84E
0x18001c900  xor     r8d, r8d; int
0x18001c903  lea     rdx, [r14+20h]; struct _SDIAG_DISPINFO *
0x18001c907  call    ?SdpLocalizeDisplayInformation@@YAJPEAVSettings@@PEAU_SDIAG_DISPINFO@@H@Z; SdpLocalizeDisplayInformation(Settings *,_SDIAG_DISPINFO *,int)
0x18001c90c  mov     ebx, eax
0x18001c90e  test    eax, eax
0x18001c910  jns     short loc_18001C920
0x18001c912  mov     r9d, eax
0x18001c915  mov     r8d, 128h
0x18001c91b  jmp     loc_18001C851
0x18001c920  mov     rax, [rdi]
0x18001c923  mov     rcx, rdi
0x18001c926  mov     rax, [rax+10h]
0x18001c92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c92f  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001c933  mov     [rbp+arg_10], 0
0x18001c93b  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001c93e  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001c943  mov     ebx, eax
0x18001c945  test    eax, eax
0x18001c947  jns     short loc_18001C954
0x18001c949  mov     r8d, 130h
0x18001c94f  jmp     loc_18001C88C
0x18001c954  mov     rdi, [rbp+arg_10]
0x18001c958  lea     rdx, aRequiresconsen; "RequiresConsent"
0x18001c95f  mov     rcx, rdi; struct IXMLDOMNode *
0x18001c962  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001c967  mov     ebx, eax
0x18001c969  test    eax, eax
0x18001c96b  jns     short loc_18001C97B
0x18001c96d  mov     r9d, eax
0x18001c970  mov     r8d, 131h
0x18001c976  jmp     loc_18001C851
0x18001c97b  cmp     eax, esi
0x18001c97d  jz      loc_18001CB21
0x18001c983  test    rdi, rdi
0x18001c986  jz      loc_18001CB21
0x18001c98c  mov     rax, [rdi]
0x18001c98f  lea     rdx, [rbp+arg_8]
0x18001c993  mov     rcx, rdi
0x18001c996  mov     [rbp+arg_8], 0
0x18001c99e  mov     rax, [rax+0D0h]
0x18001c9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9aa  mov     ebx, eax
0x18001c9ac  test    eax, eax
0x18001c9ae  jns     short loc_18001C9CD
0x18001c9b0  mov     r9d, eax; int
0x18001c9b3  lea     rdx, aResolverSetcon; "Resolver::SetConsent"
0x18001c9ba  mov     r8d, 18Eh; int
0x18001c9c0  mov     ecx, esi; Level
0x18001c9c2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c9c7  mov     rcx, [rbp+arg_8]
0x18001c9cb  jmp     short loc_18001C9DB
0x18001c9cd  mov     rax, [rbp+arg_8]
0x18001c9d1  xor     ecx, ecx; bstrString
0x18001c9d3  mov     [r14+40h], rax
0x18001c9d7  mov     [rbp+arg_8], rcx
0x18001c9db  test    rcx, rcx
0x18001c9de  jz      short loc_18001C9E6
0x18001c9e0  call    cs:__imp_SysFreeString
0x18001c9e6  test    ebx, ebx
0x18001c9e8  jns     short loc_18001C9F5
0x18001c9ea  mov     r8d, 134h
0x18001c9f0  jmp     loc_18001C84E
0x18001c9f5  mov     rax, [rdi]
0x18001c9f8  mov     rcx, rdi
0x18001c9fb  mov     rax, [rax+10h]
0x18001c9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca04  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001ca08  mov     [rbp+arg_10], 0
0x18001ca10  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001ca13  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001ca18  mov     ebx, eax
0x18001ca1a  test    eax, eax
0x18001ca1c  jns     short loc_18001CA29
0x18001ca1e  mov     r8d, 13Ch
0x18001ca24  jmp     loc_18001C88C
0x18001ca29  mov     rdi, [rbp+arg_10]
0x18001ca2d  lea     rdx, aScript; "Script"
0x18001ca34  mov     rcx, rdi; struct IXMLDOMNode *
0x18001ca37  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001ca3c  mov     ebx, eax
0x18001ca3e  test    eax, eax
0x18001ca40  jns     short loc_18001CA50
0x18001ca42  mov     r9d, eax
0x18001ca45  mov     r8d, 13Dh
0x18001ca4b  jmp     loc_18001C851
0x18001ca50  cmp     eax, esi
0x18001ca52  jz      loc_18001CB19
0x18001ca58  test    rdi, rdi
0x18001ca5b  jz      loc_18001CB19
0x18001ca61  mov     rdx, rdi; struct IXMLDOMNode *
0x18001ca64  mov     rcx, r14; this
0x18001ca67  call    ?InitializeScript@Resolver@@AEAAJPEAUIXMLDOMNode@@@Z; Resolver::InitializeScript(IXMLDOMNode *)
0x18001ca6c  mov     ebx, eax
0x18001ca6e  test    eax, eax
0x18001ca70  jns     short loc_18001CA80
0x18001ca72  mov     r9d, eax
0x18001ca75  mov     r8d, 140h
0x18001ca7b  jmp     loc_18001C851
0x18001ca80  mov     rax, [rdi]
0x18001ca83  mov     rcx, rdi
0x18001ca86  mov     rax, [rax+10h]
0x18001ca8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca8f  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001ca93  mov     [rbp+arg_10], 0
0x18001ca9b  mov     rcx, r12; struct IXMLDOMNodeList *
0x18001ca9e  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001caa3  mov     ebx, eax
0x18001caa5  test    eax, eax
0x18001caa7  jns     short loc_18001CAB4
0x18001caa9  mov     r8d, 148h
0x18001caaf  jmp     loc_18001C88C
0x18001cab4  mov     rdi, [rbp+arg_10]
0x18001cab8  lea     rdx, aExtensionpoint_0; "ExtensionPoint"
0x18001cabf  mov     rcx, rdi; struct IXMLDOMNode *
0x18001cac2  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001cac7  mov     ebx, eax
0x18001cac9  test    eax, eax
0x18001cacb  jns     short loc_18001CADB
0x18001cacd  mov     r9d, eax
0x18001cad0  mov     r8d, 149h
0x18001cad6  jmp     loc_18001C851
0x18001cadb  cmp     eax, esi
0x18001cadd  jz      short loc_18001CB11
0x18001cadf  test    rdi, rdi
0x18001cae2  jz      short loc_18001CB11
0x18001cae4  mov     rax, [rdi]
0x18001cae7  lea     r8, [r14+18h]
0x18001caeb  or      edx, 0FFFFFFFFh
0x18001caee  mov     rcx, rdi
0x18001caf1  mov     rax, [rax+0C0h]
0x18001caf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cafd  mov     ebx, eax
0x18001caff  test    eax, eax
0x18001cb01  jns     short loc_18001CB4E
0x18001cb03  mov     r9d, eax
0x18001cb06  mov     r8d, 14Ch
0x18001cb0c  jmp     loc_18001C851
0x18001cb11  mov     r8d, 149h
0x18001cb17  jmp     short loc_18001CB37
0x18001cb19  mov     r8d, 13Dh
0x18001cb1f  jmp     short loc_18001CB37
0x18001cb21  mov     r8d, 131h
0x18001cb27  jmp     short loc_18001CB37
0x18001cb29  mov     r8d, 120h
0x18001cb2f  jmp     short loc_18001CB37
0x18001cb31  mov     r8d, 114h; int
0x18001cb37  mov     r9d, 80004005h; int
0x18001cb3d  mov     ecx, esi; Level
0x18001cb3f  mov     ebx, r9d
0x18001cb42  lea     rdx, aResolverParser; "Resolver::ParseResolverXml"
0x18001cb49  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001cb4e  test    r12, r12
0x18001cb51  jz      short loc_18001CB63
0x18001cb53  mov     rax, [r12]
0x18001cb57  mov     rcx, r12
0x18001cb5a  mov     rax, [rax+10h]
0x18001cb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
