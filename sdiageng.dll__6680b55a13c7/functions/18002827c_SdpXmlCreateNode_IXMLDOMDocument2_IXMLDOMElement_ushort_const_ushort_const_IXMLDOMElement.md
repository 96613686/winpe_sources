# SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x18002827c`
- end: `0x180028485`
- name: `?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z`
- size: `521`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `22`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000312c`
- `0x180004518`
- `0x180004d58`
- `0x18001483c`
- `0x180014f7c`
- `0x1800151fc`
- `0x180017c90`
- `0x180018a9c`
- `0x18001955c`
- `0x1800199c4`
- `0x18001c224`
- `0x18001cc2c`
- `0x18001d544`
- `0x18001dac4`
- `0x18001f844`
- `0x180020fc0`
- `0x18002114c`
- `0x180021ec4`
- `0x180022174`
- `0x180022570`
- `0x180023e40`
- `0x180026500`

## callees

- `0x180026fa0`
- `0x18002827c`
- `0x1800288b8`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800282e2`
- `OLEAUT32!__imp_SysAllocString` at `0x180028331`
- `OLEAUT32!__imp_SysAllocString` at `0x1800282e2`
- `OLEAUT32!__imp_SysAllocString` at `0x180028331`
- `OLEAUT32!__imp_SysFreeString` at `0x180028462`
- `OLEAUT32!__imp_SysFreeString` at `0x180028470`
- `OLEAUT32!__imp_SysFreeString` at `0x180028462`
- `OLEAUT32!__imp_SysFreeString` at `0x180028470`

## string_xrefs

- `0x1800282bc`: `SdpXmlCreateNode`
- `0x1800283a7`: `SdpXmlCreateNode`
- `0x1800283ed`: `SdpXmlCreateNode`

## pseudocode

```c
__int64 __fastcall SdpXmlCreateNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IXMLDOMElement **a5)
{
  OLECHAR *v5; // rbp
  OLECHAR *v6; // rsi
  unsigned int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ebx
  BSTR v13; // rax
  int v14; // eax
  BSTR v15; // rax
  int v16; // eax
  int RootNode; // eax
  int v18; // eax
  struct IXMLDOMElement *v19; // rcx
  struct IXMLDOMElement *v21; // [rsp+20h] [rbp-48h] BYREF
  struct IXMLDOMElement *v22; // [rsp+70h] [rbp+8h] BYREF

  v5 = 0;
  v21 = 0;
  v6 = 0;
  v22 = 0;
  if ( !a1 )
  {
    v10 = 1549;
LABEL_3:
    v11 = -2147024809;
LABEL_4:
    v12 = v11;
LABEL_5:
    SdpDebugTrace(1u, L"SdpXmlCreateNode", v10, v11);
    goto LABEL_28;
  }
  if ( !a3 )
  {
    v10 = 1550;
    goto LABEL_3;
  }
  v13 = SysAllocString(a3);
  v5 = v13;
  if ( !v13 )
  {
    v11 = -2147024882;
    v10 = 1553;
    goto LABEL_4;
  }
  v14 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, struct IXMLDOMElement **))a1->lpVtbl->createElement)(
          a1,
          v13,
          &v22);
  v12 = v14;
  if ( v14 < 0 )
  {
    v11 = v14;
    v10 = 1556;
    goto LABEL_5;
  }
  if ( a4 )
  {
    v15 = SysAllocString(a4);
    v6 = v15;
    if ( !v15 )
    {
      v11 = -2147024882;
      v10 = 1560;
      goto LABEL_4;
    }
    v16 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR))v22->lpVtbl->put_text)(v22, v15);
    v12 = v16;
    if ( v16 < 0 )
    {
      v11 = v16;
      v10 = 1563;
      goto LABEL_5;
    }
  }
  if ( a2 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))a2->lpVtbl->AddRef)(a2);
    goto LABEL_22;
  }
  RootNode = SdpXmlGetRootNode(a1, &v21);
  v12 = RootNode;
  if ( RootNode >= 0 )
  {
    a2 = v21;
LABEL_22:
    v18 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))a2->lpVtbl->appendChild)(
            a2,
            v22,
            0);
    v12 = v18;
    if ( v18 >= 0 )
    {
      if ( a5 )
      {
        v19 = v22;
        *a5 = v22;
        ((void (__fastcall *)(struct IXMLDOMElement *))v19->lpVtbl->AddRef)(v19);
      }
    }
    else
    {
      SdpDebugTrace(1u, L"SdpXmlCreateNode", 0x628u, v18);
    }
    goto LABEL_26;
  }
  SdpDebugTrace(1u, L"SdpXmlCreateNode", 0x624u, RootNode);
  a2 = v21;
LABEL_26:
  if ( a2 )
    ((void (__fastcall *)(struct IXMLDOMElement *))a2->lpVtbl->Release)(a2);
LABEL_28:
  if ( v22 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v5 )
    SysFreeString(v5);
  if ( v6 )
    SysFreeString(v6);
  return v12;
}

```

## disassembly

```asm
0x18002827c  push    rbx
0x18002827e  push    rbp
0x18002827f  push    rsi
0x180028280  push    rdi
0x180028281  push    r14
0x180028283  push    r15
0x180028285  sub     rsp, 38h
0x180028289  xor     ebp, ebp
0x18002828b  mov     [rsp+68h+var_48], 0
0x180028294  xor     esi, esi
0x180028296  mov     [rsp+68h+arg_0], 0
0x18002829f  mov     r15, r9
0x1800282a2  mov     rdi, rdx
0x1800282a5  mov     r14, rcx
0x1800282a8  test    rcx, rcx
0x1800282ab  jnz     short loc_1800282D2
0x1800282ad  mov     r8d, 60Dh; int
0x1800282b3  mov     r9d, 80070057h; int
0x1800282b9  mov     ebx, r9d
0x1800282bc  lea     rdx, aSdpxmlcreateno; "SdpXmlCreateNode"
0x1800282c3  mov     ecx, 1; Level
0x1800282c8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800282cd  jmp     loc_18002843B
0x1800282d2  test    r8, r8
0x1800282d5  jnz     short loc_1800282DF
0x1800282d7  mov     r8d, 60Eh
0x1800282dd  jmp     short loc_1800282B3
0x1800282df  mov     rcx, r8; psz
0x1800282e2  call    cs:__imp_SysAllocString
0x1800282e8  mov     rbp, rax
0x1800282eb  test    rax, rax
0x1800282ee  jnz     short loc_1800282FE
0x1800282f0  mov     r9d, 8007000Eh
0x1800282f6  mov     r8d, 611h
0x1800282fc  jmp     short loc_1800282B9
0x1800282fe  mov     rax, [r14]
0x180028301  lea     r8, [rsp+68h+arg_0]
0x180028306  mov     rdx, rbp
0x180028309  mov     rcx, r14
0x18002830c  mov     rax, [rax+178h]
0x180028313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028318  mov     ebx, eax
0x18002831a  test    eax, eax
0x18002831c  jns     short loc_180028329
0x18002831e  mov     r9d, eax
0x180028321  mov     r8d, 614h
0x180028327  jmp     short loc_1800282BC
0x180028329  test    r15, r15
0x18002832c  jz      short loc_18002837B
0x18002832e  mov     rcx, r15; psz
0x180028331  call    cs:__imp_SysAllocString
0x180028337  mov     rsi, rax
0x18002833a  test    rax, rax
0x18002833d  jnz     short loc_180028350
0x18002833f  mov     r9d, 8007000Eh
0x180028345  mov     r8d, 618h
0x18002834b  jmp     loc_1800282B9
0x180028350  mov     rcx, [rsp+68h+arg_0]
0x180028355  mov     rdx, rsi
0x180028358  mov     rax, [rcx]
0x18002835b  mov     rax, [rax+0D8h]
0x180028362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028367  mov     ebx, eax
0x180028369  test    eax, eax
0x18002836b  jns     short loc_18002837B
0x18002836d  mov     r9d, eax
0x180028370  mov     r8d, 61Bh
0x180028376  jmp     loc_1800282BC
0x18002837b  test    rdi, rdi
0x18002837e  jz      short loc_180028391
0x180028380  mov     rax, [rdi]
0x180028383  mov     rcx, rdi
0x180028386  mov     rax, [rax+8]
0x18002838a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002838f  jmp     short loc_1800283CA
0x180028391  lea     rdx, [rsp+68h+var_48]; struct IXMLDOMElement **
0x180028396  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180028399  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x18002839e  mov     ebx, eax
0x1800283a0  test    eax, eax
0x1800283a2  jns     short loc_1800283C5
0x1800283a4  mov     r9d, eax; int
0x1800283a7  lea     rdx, aSdpxmlcreateno; "SdpXmlCreateNode"
0x1800283ae  mov     r8d, 624h; int
0x1800283b4  mov     ecx, 1; Level
0x1800283b9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800283be  mov     rdi, [rsp+68h+var_48]
0x1800283c3  jmp     short loc_180028427
0x1800283c5  mov     rdi, [rsp+68h+var_48]
0x1800283ca  mov     rax, [rdi]
0x1800283cd  xor     r8d, r8d
0x1800283d0  mov     rdx, [rsp+68h+arg_0]
0x1800283d5  mov     rcx, rdi
0x1800283d8  mov     rax, [rax+0A8h]
0x1800283df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283e4  mov     ebx, eax
0x1800283e6  test    eax, eax
0x1800283e8  jns     short loc_180028406
0x1800283ea  mov     r9d, eax; int
0x1800283ed  lea     rdx, aSdpxmlcreateno; "SdpXmlCreateNode"
0x1800283f4  mov     r8d, 628h; int
0x1800283fa  mov     ecx, 1; Level
0x1800283ff  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028404  jmp     short loc_180028427
0x180028406  mov     rax, [rsp+68h+arg_20]
0x18002840e  test    rax, rax
0x180028411  jz      short loc_180028427
0x180028413  mov     rcx, [rsp+68h+arg_0]
0x180028418  mov     [rax], rcx
0x18002841b  mov     rax, [rcx]
0x18002841e  mov     rax, [rax+8]
0x180028422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028427  test    rdi, rdi
0x18002842a  jz      short loc_18002843B
0x18002842c  mov     rax, [rdi]
0x18002842f  mov     rcx, rdi
0x180028432  mov     rax, [rax+10h]
0x180028436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002843b  mov     rcx, [rsp+68h+arg_0]
0x180028440  test    rcx, rcx
0x180028443  jz      short loc_18002845A
0x180028445  mov     rax, [rcx]
0x180028448  mov     rax, [rax+10h]
0x18002844c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028451  mov     [rsp+68h+arg_0], 0
0x18002845a  test    rbp, rbp
0x18002845d  jz      short loc_180028468
0x18002845f  mov     rcx, rbp; bstrString
0x180028462  call    cs:__imp_SysFreeString
0x180028468  test    rsi, rsi
0x18002846b  jz      short loc_180028476
0x18002846d  mov     rcx, rsi; bstrString
0x180028470  call    cs:__imp_SysFreeString
0x180028476  mov     eax, ebx
0x180028478  add     rsp, 38h
0x18002847c  pop     r15
0x18002847e  pop     r14
0x180028480  pop     rdi
0x180028481  pop     rsi
0x180028482  pop     rbp
0x180028483  pop     rbx
0x180028484  retn
```
