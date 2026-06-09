# SdpXmlMerge(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x180028f24`
- end: `0x1800290b4`
- name: `?SdpXmlMerge@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@01@Z`
- size: `400`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014f7c`

## callees

- `0x180026fa0`
- `0x1800286a4`
- `0x180028f24`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x180028f62`: `SdpXmlMerge`
- `0x180028fa2`: `SdpXmlMerge`
- `0x180029075`: `SdpXmlMerge`
- `0x180029094`: `SdpXmlMerge`

## pseudocode

```c
__int64 __fastcall SdpXmlMerge(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMNode *a4)
{
  struct IXMLDOMNode *v4; // rdi
  unsigned int v6; // ebx
  int ChildNodes; // eax
  unsigned int v8; // r8d
  struct IXMLDOMNodeList *v9; // rsi
  int v11; // r14d
  int v12; // eax
  int v13; // eax
  struct IXMLDOMNode *v14; // [rsp+20h] [rbp-10h] BYREF
  struct IXMLDOMNodeList *v15; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+48h] BYREF
  int v17; // [rsp+7Ch] [rbp+4Ch]

  v17 = HIDWORD(a4);
  v4 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    SdpDebugTrace(1u, L"SdpXmlMerge", 0x47Cu, -2147467261);
    return v6;
  }
  if ( a3 )
  {
    ChildNodes = SdpXmlGetChildNodes(a3, 0, &v15, &v16);
    v6 = ChildNodes;
    if ( ChildNodes < 0 )
    {
      v8 = 1158;
LABEL_6:
      SdpDebugTrace(1u, L"SdpXmlMerge", v8, ChildNodes);
      goto LABEL_7;
    }
  }
  else
  {
    ChildNodes = SdpXmlGetChildNodes(0, 0, &v15, &v16);
    v6 = ChildNodes;
    if ( ChildNodes < 0 )
    {
      v8 = 1161;
      goto LABEL_6;
    }
  }
  v11 = 0;
  if ( v16 )
  {
    v9 = v15;
    while ( 1 )
    {
      if ( v4 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
        v14 = 0;
      }
      v12 = SdpXmlNextNode(v9, &v14);
      v6 = v12;
      if ( v12 < 0 )
        break;
      v4 = v14;
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, _QWORD))a2->lpVtbl->appendChild)(
              a2,
              v14,
              0);
      v6 = v13;
      if ( v13 < 0 )
      {
        SdpDebugTrace(1u, L"SdpXmlMerge", 0x497u, v13);
        goto LABEL_8;
      }
      if ( ++v11 >= v16 )
        goto LABEL_8;
    }
    SdpDebugTrace(1u, L"SdpXmlMerge", 0x494u, v12);
    v4 = v14;
    goto LABEL_8;
  }
LABEL_7:
  v9 = v15;
LABEL_8:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v9->lpVtbl->Release)(v9);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  return v6;
}

```

## disassembly

```asm
0x180028f24  mov     [rsp-28h+arg_8], rbx
0x180028f29  mov     qword ptr [rsp-28h+arg_18], r9
0x180028f2e  mov     [rsp-28h+arg_0], rcx
0x180028f33  push    rbp
0x180028f34  push    rsi
0x180028f35  push    rdi
0x180028f36  push    r12
0x180028f38  push    r14
0x180028f3a  mov     rbp, rsp
0x180028f3d  sub     rsp, 30h
0x180028f41  xor     edi, edi
0x180028f43  mov     [rbp+arg_0], 0
0x180028f4b  mov     [rbp+var_10], rdi
0x180028f4f  mov     rax, r8
0x180028f52  mov     [rbp+arg_18], edi
0x180028f55  mov     r12, rdx
0x180028f58  test    rdx, rdx
0x180028f5b  jnz     short loc_180028F7C
0x180028f5d  mov     ebx, 80004003h
0x180028f62  lea     rdx, aSdpxmlmerge; "SdpXmlMerge"
0x180028f69  mov     r9d, ebx; int
0x180028f6c  lea     ecx, [rdi+1]; Level
0x180028f6f  mov     r8d, 47Ch; int
0x180028f75  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028f7a  jmp     short loc_180028FDF
0x180028f7c  xor     edx, edx; struct IXMLDOMNode *
0x180028f7e  lea     r9, [rbp+arg_18]; unsigned int *
0x180028f82  lea     r8, [rbp+arg_0]; struct IXMLDOMNodeList **
0x180028f86  test    rax, rax
0x180028f89  jz      short loc_180028FF2
0x180028f8b  mov     rcx, rax; struct IXMLDOMDocument2 *
0x180028f8e  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180028f93  mov     ebx, eax
0x180028f95  test    eax, eax
0x180028f97  jns     short loc_180029007
0x180028f99  mov     r8d, 486h; int
0x180028f9f  mov     r9d, eax; int
0x180028fa2  lea     rdx, aSdpxmlmerge; "SdpXmlMerge"
0x180028fa9  mov     ecx, 1; Level
0x180028fae  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028fb3  mov     rsi, [rbp+arg_0]
0x180028fb7  test    rsi, rsi
0x180028fba  jz      short loc_180028FCB
0x180028fbc  mov     rax, [rsi]
0x180028fbf  mov     rcx, rsi
0x180028fc2  mov     rax, [rax+10h]
0x180028fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fcb  test    rdi, rdi
0x180028fce  jz      short loc_180028FDF
0x180028fd0  mov     rax, [rdi]
0x180028fd3  mov     rcx, rdi
0x180028fd6  mov     rax, [rax+10h]
0x180028fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fdf  mov     eax, ebx
0x180028fe1  mov     rbx, [rsp+30h+arg_8]
0x180028fe6  add     rsp, 30h
0x180028fea  pop     r14
0x180028fec  pop     r12
0x180028fee  pop     rdi
0x180028fef  pop     rsi
0x180028ff0  pop     rbp
0x180028ff1  retn
0x180028ff2  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180028ff4  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180028ff9  mov     ebx, eax
0x180028ffb  test    eax, eax
0x180028ffd  jns     short loc_180029007
0x180028fff  mov     r8d, 489h
0x180029005  jmp     short loc_180028F9F
0x180029007  xor     r14d, r14d
0x18002900a  cmp     [rbp+arg_18], edi
0x18002900d  jbe     short loc_180028FB3
0x18002900f  mov     rsi, [rbp+arg_0]
0x180029013  test    rdi, rdi
0x180029016  jz      short loc_18002902F
0x180029018  mov     rax, [rdi]
0x18002901b  mov     rcx, rdi
0x18002901e  mov     rax, [rax+10h]
0x180029022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029027  mov     [rbp+var_10], 0
0x18002902f  lea     rdx, [rbp+var_10]; struct IXMLDOMNode **
0x180029033  mov     rcx, rsi; struct IXMLDOMNodeList *
0x180029036  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18002903b  mov     ebx, eax
0x18002903d  test    eax, eax
0x18002903f  js      short loc_180029091
0x180029041  mov     rax, [r12]
0x180029045  xor     r8d, r8d
0x180029048  mov     rdi, [rbp+var_10]
0x18002904c  mov     rcx, r12
0x18002904f  mov     rdx, rdi
0x180029052  mov     rax, [rax+0A8h]
0x180029059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002905e  mov     ebx, eax
0x180029060  test    eax, eax
0x180029062  js      short loc_180029072
0x180029064  inc     r14d
0x180029067  cmp     r14d, [rbp+arg_18]
0x18002906b  jb      short loc_180029013
0x18002906d  jmp     loc_180028FB7
0x180029072  mov     r9d, eax; int
0x180029075  lea     rdx, aSdpxmlmerge; "SdpXmlMerge"
0x18002907c  mov     r8d, 497h; int
0x180029082  mov     ecx, 1; Level
0x180029087  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002908c  jmp     loc_180028FB7
0x180029091  mov     r9d, eax; int
0x180029094  lea     rdx, aSdpxmlmerge; "SdpXmlMerge"
0x18002909b  mov     r8d, 494h; int
0x1800290a1  mov     ecx, 1; Level
0x1800290a6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800290ab  mov     rdi, [rbp+var_10]
0x1800290af  jmp     loc_180028FB7
```
