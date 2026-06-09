# SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)

- ea: `0x180027ea4`
- end: `0x18002802f`
- name: `?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z`
- size: `395`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMElement *, struct IXMLDOMDocument2 *)`
- caller_count: `18`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004d58`
- `0x180014f7c`
- `0x180017c90`
- `0x1800181a4`
- `0x180018a9c`
- `0x1800192ac`
- `0x18001955c`
- `0x18001b4d4`
- `0x18001b9c8`
- `0x18001bb50`
- `0x18001c224`
- `0x18001cc2c`
- `0x18001d544`
- `0x18001f844`
- `0x18002146c`
- `0x1800224e0`
- `0x180022570`
- `0x1800227d0`

## callees

- `0x180026fa0`
- `0x180027ea4`
- `0x1800288b8`
- `0x18002a010`

## string_xrefs

- `0x180027ee0`: `SdpXmlAppend`
- `0x180027f0d`: `SdpXmlAppend`
- `0x180027f49`: `SdpXmlAppend`
- `0x180027fce`: `SdpXmlAppend`

## pseudocode

```c
__int64 __fastcall SdpXmlAppend(struct IXMLDOMDocument2 *a1, struct IXMLDOMElement *a2, struct IXMLDOMDocument2 *a3)
{
  struct IXMLDOMElement *v3; // rsi
  struct IXMLDOMElement *v4; // rdi
  struct IXMLDOMElement *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  int RootNode; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  struct IXMLDOMElement *v15; // [rsp+70h] [rbp+40h] BYREF
  struct IXMLDOMElement *v16; // [rsp+78h] [rbp+48h] BYREF

  v3 = 0;
  v4 = 0;
  v15 = 0;
  v16 = 0;
  v6 = a2;
  v14 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = 1238;
LABEL_3:
    SdpDebugTrace(1u, L"SdpXmlAppend", v8, v7);
    goto LABEL_21;
  }
  if ( a1 )
  {
    RootNode = SdpXmlGetRootNode(a1, &v15);
    v7 = RootNode;
    if ( RootNode < 0 )
    {
      SdpDebugTrace(1u, L"SdpXmlAppend", 0x4DDu, RootNode);
      v4 = v15;
      goto LABEL_17;
    }
    v4 = v15;
    v6 = v15;
  }
  else if ( !a2 )
  {
    v7 = -2147467261;
    v8 = 1249;
    goto LABEL_3;
  }
  v10 = SdpXmlGetRootNode(a3, &v16);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v3 = v16;
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, __int64 *))v16->lpVtbl->cloneNode)(
            v16,
            0xFFFFFFFFLL,
            &v14);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, _QWORD))v6->lpVtbl->appendChild)(v6, v14, 0);
      v7 = v11;
      if ( v11 >= 0 )
        goto LABEL_17;
      v12 = 1260;
    }
    else
    {
      v12 = 1257;
    }
    SdpDebugTrace(1u, L"SdpXmlAppend", v12, v11);
    goto LABEL_17;
  }
  SdpDebugTrace(1u, L"SdpXmlAppend", 0x4E6u, v10);
  v3 = v16;
LABEL_17:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
LABEL_21:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v7;
}

```

## disassembly

```asm
0x180027ea4  mov     [rsp-28h+arg_0], rbx
0x180027ea9  push    rbp
0x180027eaa  push    rsi
0x180027eab  push    rdi
0x180027eac  push    r14
0x180027eae  push    r15
0x180027eb0  mov     rbp, rsp
0x180027eb3  sub     rsp, 30h
0x180027eb7  xor     esi, esi
0x180027eb9  xor     edi, edi
0x180027ebb  mov     [rbp+arg_10], rdi
0x180027ebf  mov     r15, r8
0x180027ec2  mov     [rbp+arg_18], rsi
0x180027ec6  mov     r14, rdx
0x180027ec9  mov     [rbp+var_10], rsi
0x180027ecd  test    r8, r8
0x180027ed0  jnz     short loc_180027EF6
0x180027ed2  mov     ebx, 80070057h
0x180027ed7  mov     r8d, 4D6h; int
0x180027edd  mov     r9d, ebx; int
0x180027ee0  lea     rdx, aSdpxmlappend; "SdpXmlAppend"
0x180027ee7  mov     ecx, 1; Level
0x180027eec  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027ef1  jmp     loc_180028007
0x180027ef6  test    rcx, rcx
0x180027ef9  jz      short loc_180027F66
0x180027efb  lea     rdx, [rbp+arg_10]; struct IXMLDOMElement **
0x180027eff  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180027f04  mov     ebx, eax
0x180027f06  test    eax, eax
0x180027f08  jns     short loc_180027F2D
0x180027f0a  mov     r9d, eax; int
0x180027f0d  lea     rdx, aSdpxmlappend; "SdpXmlAppend"
0x180027f14  mov     r8d, 4DDh; int
0x180027f1a  mov     ecx, 1; Level
0x180027f1f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027f24  mov     rdi, [rbp+arg_10]
0x180027f28  jmp     loc_180027FDF
0x180027f2d  mov     rdi, [rbp+arg_10]
0x180027f31  mov     r14, rdi
0x180027f34  lea     rdx, [rbp+arg_18]; struct IXMLDOMElement **
0x180027f38  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180027f3b  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180027f40  mov     ebx, eax
0x180027f42  test    eax, eax
0x180027f44  jns     short loc_180027F7B
0x180027f46  mov     r9d, eax; int
0x180027f49  lea     rdx, aSdpxmlappend; "SdpXmlAppend"
0x180027f50  mov     r8d, 4E6h; int
0x180027f56  mov     ecx, 1; Level
0x180027f5b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027f60  mov     rsi, [rbp+arg_18]
0x180027f64  jmp     short loc_180027FDF
0x180027f66  test    rdx, rdx
0x180027f69  jnz     short loc_180027F34
0x180027f6b  mov     ebx, 80004003h
0x180027f70  mov     r8d, 4E1h
0x180027f76  jmp     loc_180027EDD
0x180027f7b  mov     rsi, [rbp+arg_18]
0x180027f7f  lea     r8, [rbp+var_10]
0x180027f83  or      edx, 0FFFFFFFFh
0x180027f86  mov     rcx, rsi
0x180027f89  mov     rax, [rsi]
0x180027f8c  mov     rax, [rax+0C0h]
0x180027f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f98  mov     ebx, eax
0x180027f9a  test    eax, eax
0x180027f9c  jns     short loc_180027FA6
0x180027f9e  mov     r8d, 4E9h
0x180027fa4  jmp     short loc_180027FCB
0x180027fa6  mov     rax, [r14]
0x180027fa9  xor     r8d, r8d
0x180027fac  mov     rdx, [rbp+var_10]
0x180027fb0  mov     rcx, r14
0x180027fb3  mov     rax, [rax+0A8h]
0x180027fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fbf  mov     ebx, eax
0x180027fc1  test    eax, eax
0x180027fc3  jns     short loc_180027FDF
0x180027fc5  mov     r8d, 4ECh; int
0x180027fcb  mov     r9d, eax; int
0x180027fce  lea     rdx, aSdpxmlappend; "SdpXmlAppend"
0x180027fd5  mov     ecx, 1; Level
0x180027fda  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180027fdf  test    rdi, rdi
0x180027fe2  jz      short loc_180027FF3
0x180027fe4  mov     rax, [rdi]
0x180027fe7  mov     rcx, rdi
0x180027fea  mov     rax, [rax+10h]
0x180027fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff3  test    rsi, rsi
0x180027ff6  jz      short loc_180028007
0x180027ff8  mov     rax, [rsi]
0x180027ffb  mov     rcx, rsi
0x180027ffe  mov     rax, [rax+10h]
0x180028002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028007  mov     rcx, [rbp+var_10]
0x18002800b  test    rcx, rcx
0x18002800e  jz      short loc_18002801C
0x180028010  mov     rax, [rcx]
0x180028013  mov     rax, [rax+10h]
0x180028017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002801c  mov     eax, ebx
0x18002801e  mov     rbx, [rsp+30h+arg_0]
0x180028023  add     rsp, 30h
0x180028027  pop     r15
0x180028029  pop     r14
0x18002802b  pop     rdi
0x18002802c  pop     rsi
0x18002802d  pop     rbp
0x18002802e  retn
```
