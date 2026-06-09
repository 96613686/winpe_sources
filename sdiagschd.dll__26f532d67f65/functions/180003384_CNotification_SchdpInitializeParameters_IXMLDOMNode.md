# CNotification::SchdpInitializeParameters(IXMLDOMNode *)

- ea: `0x180003384`
- end: `0x18000354e`
- name: `?SchdpInitializeParameters@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180002850`

## callees

- `0x180003100`
- `0x180003384`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800033fc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800033fc`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpInitializeParameters(struct IXMLDOMDocument2 *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v5; // r12
  unsigned int v6; // ebx
  int v7; // r9d
  int v8; // r8d
  signed int v9; // r14d
  SAFEARRAY *v10; // rax
  int v11; // r15d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  struct IXMLDOMNodeList *v16; // [rsp+20h] [rbp-20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+30h] [rbp-10h]
  int v19; // [rsp+34h] [rbp-Ch]
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMNode *v21; // [rsp+88h] [rbp+48h] BYREF

  v20 = 0;
  v16 = 0;
  v2 = 0;
  v21 = 0;
  ChildNodes = SdpXmlGetChildNodes(this, a2, &v16, &v20);
  v5 = v16;
  v6 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = ChildNodes;
    v8 = 354;
LABEL_23:
    SdpDebugTrace(1u, L"CNotification::SchdpInitializeParameters", v8, v7);
    goto LABEL_24;
  }
  v9 = v20;
  if ( !v20 )
    goto LABEL_24;
  rgsabound.lLbound = 0;
  v19 = 0;
  rgsabound.cElements = v20;
  v18 = v20;
  v10 = SafeArrayCreate(8u, 2u, &rgsabound);
  this[3].lpVtbl = (struct IXMLDOMDocument2Vtbl *)v10;
  if ( !v10 )
  {
    v6 = -2147024882;
    v8 = 366;
LABEL_22:
    v7 = v6;
    goto LABEL_23;
  }
  if ( (unsigned int)v9 > 0x7FFFFFFF )
  {
    v6 = -2147024362;
    v8 = 369;
    goto LABEL_22;
  }
  v6 = 0;
  v11 = 0;
  if ( v9 > 0 )
  {
    while ( 1 )
    {
      if ( v2 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
        v21 = 0;
      }
      v12 = SdpXmlNextNode(v5, &v21);
      v6 = v12;
      if ( v12 < 0 )
        break;
      v2 = v21;
      v13 = SdpXmlCheckNode(v21, L"Parameter");
      v6 = v13;
      if ( v13 < 0 )
      {
        v7 = v13;
        v8 = 376;
        goto LABEL_23;
      }
      if ( v13 == 1 || !v2 )
      {
        v6 = -2147467259;
        v8 = 376;
        goto LABEL_22;
      }
      v14 = CNotification::SchdpInitializeParameter((CNotification *)this, v2, v11);
      v6 = v14;
      if ( v14 < 0 )
      {
        v7 = v14;
        v8 = 379;
        goto LABEL_23;
      }
      if ( ++v11 >= v9 )
        goto LABEL_24;
    }
    SdpDebugTrace(1u, L"CNotification::SchdpInitializeParameters", 375, v12);
    v2 = v21;
  }
LABEL_24:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return v6;
}

```

## disassembly

```asm
0x180003384  mov     [rsp-28h+arg_0], rbx
0x180003389  mov     [rsp-28h+arg_8], rdi
0x18000338e  push    rbp
0x18000338f  push    r12
0x180003391  push    r13
0x180003393  push    r14
0x180003395  push    r15
0x180003397  mov     rbp, rsp
0x18000339a  sub     rsp, 40h
0x18000339e  and     [rbp+arg_10], 0
0x1800033a2  lea     r9, [rbp+arg_10]; unsigned int *
0x1800033a6  and     [rbp+var_20], 0
0x1800033ab  lea     r8, [rbp+var_20]; struct IXMLDOMNodeList **
0x1800033af  xor     edi, edi
0x1800033b1  mov     r13, rcx
0x1800033b4  mov     [rbp+arg_18], rdi
0x1800033b8  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x1800033bd  mov     r12, [rbp+var_20]
0x1800033c1  mov     ebx, eax
0x1800033c3  test    eax, eax
0x1800033c5  jns     short loc_1800033D5
0x1800033c7  mov     r9d, eax
0x1800033ca  mov     r8d, 162h
0x1800033d0  jmp     loc_1800034F9
0x1800033d5  mov     r14d, [rbp+arg_10]
0x1800033d9  test    r14d, r14d
0x1800033dc  jz      loc_18000350A
0x1800033e2  and     [rbp+rgsabound.lLbound], edi
0x1800033e5  lea     r8, [rbp+rgsabound]; rgsabound
0x1800033e9  and     [rbp+var_C], edi
0x1800033ec  mov     ecx, 8; vt
0x1800033f1  mov     [rbp+rgsabound.cElements], r14d
0x1800033f5  mov     [rbp+var_10], r14d
0x1800033f9  lea     edx, [rcx-6]; cDims
0x1800033fc  call    cs:__imp_SafeArrayCreate
0x180003403  nop     dword ptr [rax+rax+00h]
0x180003408  mov     [r13+18h], rax
0x18000340c  test    rax, rax
0x18000340f  jnz     short loc_180003421
0x180003411  mov     ebx, 8007000Eh
0x180003416  mov     r8d, 16Eh
0x18000341c  jmp     loc_1800034F6
0x180003421  cmp     r14d, 7FFFFFFFh
0x180003428  ja      loc_1800034EB
0x18000342e  xor     ebx, ebx
0x180003430  xor     r15d, r15d
0x180003433  test    r14d, r14d
0x180003436  jle     loc_18000350A
0x18000343c  test    rdi, rdi
0x18000343f  jz      short loc_180003455
0x180003441  mov     rax, [rdi]
0x180003444  mov     rcx, rdi
0x180003447  mov     rax, [rax+10h]
0x18000344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003450  and     [rbp+arg_18], 0
0x180003455  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180003459  mov     rcx, r12; struct IXMLDOMNodeList *
0x18000345c  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003461  mov     ebx, eax
0x180003463  test    eax, eax
0x180003465  js      short loc_1800034CB
0x180003467  mov     rdi, [rbp+arg_18]
0x18000346b  lea     rdx, aParameter; "Parameter"
0x180003472  mov     rcx, rdi; struct IXMLDOMNode *
0x180003475  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18000347a  mov     ebx, eax
0x18000347c  test    eax, eax
0x18000347e  js      short loc_1800034C0
0x180003480  cmp     eax, 1
0x180003483  jz      short loc_1800034B3
0x180003485  test    rdi, rdi
0x180003488  jz      short loc_1800034B3
0x18000348a  mov     r8d, r15d; int
0x18000348d  mov     rdx, rdi; struct IXMLDOMNode *
0x180003490  mov     rcx, r13; this
0x180003493  call    ?SchdpInitializeParameter@CNotification@@AEAAJPEAUIXMLDOMNode@@J@Z; CNotification::SchdpInitializeParameter(IXMLDOMNode *,long)
0x180003498  mov     ebx, eax
0x18000349a  test    eax, eax
0x18000349c  js      short loc_1800034A8
0x18000349e  inc     r15d
0x1800034a1  cmp     r15d, r14d
0x1800034a4  jl      short loc_18000343C
0x1800034a6  jmp     short loc_18000350A
0x1800034a8  mov     r9d, eax
0x1800034ab  mov     r8d, 17Bh
0x1800034b1  jmp     short loc_1800034F9
0x1800034b3  mov     ebx, 80004005h
0x1800034b8  mov     r8d, 178h
0x1800034be  jmp     short loc_1800034F6
0x1800034c0  mov     r9d, eax
0x1800034c3  mov     r8d, 178h
0x1800034c9  jmp     short loc_1800034F9
0x1800034cb  mov     r9d, eax; int
0x1800034ce  lea     rdx, aCnotificationS; "CNotification::SchdpInitializeParameter"...
0x1800034d5  mov     r8d, 177h; int
0x1800034db  mov     ecx, 1; Level
0x1800034e0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800034e5  mov     rdi, [rbp+arg_18]
0x1800034e9  jmp     short loc_18000350A
0x1800034eb  mov     ebx, 80070216h
0x1800034f0  mov     r8d, 171h; int
0x1800034f6  mov     r9d, ebx; int
0x1800034f9  lea     rdx, aCnotificationS; "CNotification::SchdpInitializeParameter"...
0x180003500  mov     ecx, 1; Level
0x180003505  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000350a  test    r12, r12
0x18000350d  jz      short loc_18000351F
0x18000350f  mov     rax, [r12]
0x180003513  mov     rcx, r12
0x180003516  mov     rax, [rax+10h]
0x18000351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351f  test    rdi, rdi
0x180003522  jz      short loc_180003533
0x180003524  mov     rax, [rdi]
0x180003527  mov     rcx, rdi
0x18000352a  mov     rax, [rax+10h]
0x18000352e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003533  mov     rdi, [rsp+40h+arg_8]
0x180003538  mov     eax, ebx
0x18000353a  mov     rbx, [rsp+40h+arg_0]
0x18000353f  add     rsp, 40h
0x180003543  pop     r15
0x180003545  pop     r14
0x180003547  pop     r13
0x180003549  pop     r12
0x18000354b  pop     rbp
0x18000354c  retn
```
