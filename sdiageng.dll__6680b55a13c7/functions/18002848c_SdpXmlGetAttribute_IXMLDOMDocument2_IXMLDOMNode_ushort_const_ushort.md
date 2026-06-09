# SdpXmlGetAttribute(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort * *)

- ea: `0x18002848c`
- end: `0x18002869c`
- name: `?SdpXmlGetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBGPEAPEAG@Z`
- size: `528`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000330c`
- `0x180003410`
- `0x180020648`

## callees

- `0x180026fa0`
- `0x18002848c`
- `0x1800288b8`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002859e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002859e`
- `OLEAUT32!__imp_SysFreeString` at `0x180028687`
- `OLEAUT32!__imp_SysFreeString` at `0x180028687`

## string_xrefs

- `0x1800284d1`: `SdpXmlGetAttribute`
- `0x18002850b`: `SdpXmlGetAttribute`
- `0x180028620`: `SdpXmlGetAttribute`

## pseudocode

```c
__int64 __fastcall SdpXmlGetAttribute(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  struct IXMLDOMElement *v4; // rdi
  OLECHAR *v5; // rsi
  unsigned int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  int RootNode; // eax
  int v12; // eax
  int v13; // r9d
  unsigned int v14; // r8d
  int v15; // eax
  BSTR v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v20; // [rsp+20h] [rbp-18h] BYREF
  struct IXMLDOMElement *v21; // [rsp+28h] [rbp-10h] BYREF
  __int64 v22; // [rsp+80h] [rbp+48h] BYREF

  v4 = 0;
  v22 = 0;
  v5 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a3 )
  {
    v8 = 1671;
LABEL_3:
    v9 = -2147024809;
    v10 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlGetAttribute", v8, v9);
    goto LABEL_29;
  }
  if ( !a4 )
  {
    v8 = 1672;
    goto LABEL_3;
  }
  if ( a1 )
  {
    RootNode = SdpXmlGetRootNode(a1, &v21);
    v10 = RootNode;
    if ( RootNode < 0 )
    {
      SdpDebugTrace(1u, L"SdpXmlGetAttribute", 0x68Fu, RootNode);
      v4 = v21;
      goto LABEL_27;
    }
    v4 = v21;
    v12 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64 *))v21->lpVtbl->get_attributes)(v21, &v22);
    v10 = v12;
    if ( v12 < 0 )
    {
      v13 = v12;
      v14 = 1682;
      goto LABEL_26;
    }
  }
  else
  {
    if ( !a2 )
    {
      v10 = -2147467261;
      v8 = 1684;
      v9 = -2147467261;
      goto LABEL_4;
    }
    v15 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_attributes)(a2, &v22);
    v10 = v15;
    if ( v15 < 0 )
    {
      v9 = v15;
      v8 = 1686;
      goto LABEL_4;
    }
  }
  v16 = SysAllocString(a3);
  v5 = v16;
  if ( !v16 )
  {
    v10 = -2147024882;
    v14 = 1690;
LABEL_25:
    v13 = v10;
    goto LABEL_26;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v22 + 56LL))(v22, v16, &v20);
  v10 = v17;
  if ( v17 < 0 )
  {
    v13 = v17;
    v14 = 1693;
    goto LABEL_26;
  }
  if ( v17 == 1 || !v20 )
  {
    v10 = -2147467259;
    v14 = 1694;
    goto LABEL_25;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v20 + 208LL))(v20, a4);
  v10 = v18;
  if ( v18 >= 0 )
    goto LABEL_27;
  v13 = v18;
  v14 = 1697;
LABEL_26:
  SdpDebugTrace(1u, L"SdpXmlGetAttribute", v14, v13);
LABEL_27:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
LABEL_29:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v5 )
    SysFreeString(v5);
  return v10;
}

```

## disassembly

```asm
0x18002848c  push    rbp
0x18002848e  push    rbx
0x18002848f  push    rsi
0x180028490  push    rdi
0x180028491  push    r14
0x180028493  push    r15
0x180028495  mov     rbp, rsp
0x180028498  sub     rsp, 38h
0x18002849c  xor     edi, edi
0x18002849e  mov     [rbp+arg_10], 0
0x1800284a6  xor     esi, esi
0x1800284a8  mov     [rbp+var_18], 0
0x1800284b0  mov     [rbp+var_10], rdi
0x1800284b4  mov     r15, r9
0x1800284b7  mov     r14, r8
0x1800284ba  mov     r10, rdx
0x1800284bd  test    r8, r8
0x1800284c0  jnz     short loc_1800284E7
0x1800284c2  mov     r8d, 687h; int
0x1800284c8  mov     r9d, 80070057h; int
0x1800284ce  mov     ebx, r9d
0x1800284d1  lea     rdx, aSdpxmlgetattri; "SdpXmlGetAttribute"
0x1800284d8  mov     ecx, 1; Level
0x1800284dd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800284e2  jmp     loc_180028645
0x1800284e7  test    r15, r15
0x1800284ea  jnz     short loc_1800284F4
0x1800284ec  mov     r8d, 688h
0x1800284f2  jmp     short loc_1800284C8
0x1800284f4  test    rcx, rcx
0x1800284f7  jz      short loc_180028559
0x1800284f9  lea     rdx, [rbp+var_10]; struct IXMLDOMElement **
0x1800284fd  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180028502  mov     ebx, eax
0x180028504  test    eax, eax
0x180028506  jns     short loc_18002852B
0x180028508  mov     r9d, eax; int
0x18002850b  lea     rdx, aSdpxmlgetattri; "SdpXmlGetAttribute"
0x180028512  mov     r8d, 68Fh; int
0x180028518  mov     ecx, 1; Level
0x18002851d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028522  mov     rdi, [rbp+var_10]
0x180028526  jmp     loc_180028631
0x18002852b  mov     rdi, [rbp+var_10]
0x18002852f  lea     rdx, [rbp+arg_10]
0x180028533  mov     rcx, rdi
0x180028536  mov     rax, [rdi]
0x180028539  mov     rax, [rax+88h]
0x180028540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028545  mov     ebx, eax
0x180028547  test    eax, eax
0x180028549  jns     short loc_18002859B
0x18002854b  mov     r9d, eax
0x18002854e  mov     r8d, 692h
0x180028554  jmp     loc_180028620
0x180028559  test    r10, r10
0x18002855c  jnz     short loc_180028571
0x18002855e  mov     ebx, 80004003h
0x180028563  mov     r8d, 694h
0x180028569  mov     r9d, ebx
0x18002856c  jmp     loc_1800284D1
0x180028571  mov     rax, [rdx]
0x180028574  mov     rcx, r10
0x180028577  lea     rdx, [rbp+arg_10]
0x18002857b  mov     rax, [rax+88h]
0x180028582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028587  mov     ebx, eax
0x180028589  test    eax, eax
0x18002858b  jns     short loc_18002859B
0x18002858d  mov     r9d, eax
0x180028590  mov     r8d, 696h
0x180028596  jmp     loc_1800284D1
0x18002859b  mov     rcx, r14; psz
0x18002859e  call    cs:__imp_SysAllocString
0x1800285a4  mov     rsi, rax
0x1800285a7  test    rax, rax
0x1800285aa  jnz     short loc_1800285B9
0x1800285ac  mov     ebx, 8007000Eh
0x1800285b1  mov     r8d, 69Ah
0x1800285b7  jmp     short loc_18002861D
0x1800285b9  mov     rcx, [rbp+arg_10]
0x1800285bd  lea     r8, [rbp+var_18]
0x1800285c1  mov     rdx, rsi
0x1800285c4  mov     rax, [rcx]
0x1800285c7  mov     rax, [rax+38h]
0x1800285cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285d0  mov     ebx, eax
0x1800285d2  test    eax, eax
0x1800285d4  jns     short loc_1800285E1
0x1800285d6  mov     r9d, eax
0x1800285d9  mov     r8d, 69Dh
0x1800285df  jmp     short loc_180028620
0x1800285e1  cmp     eax, 1
0x1800285e4  jz      short loc_180028612
0x1800285e6  mov     rcx, [rbp+var_18]
0x1800285ea  test    rcx, rcx
0x1800285ed  jz      short loc_180028612
0x1800285ef  mov     rax, [rcx]
0x1800285f2  mov     rdx, r15
0x1800285f5  mov     rax, [rax+0D0h]
0x1800285fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028601  mov     ebx, eax
0x180028603  test    eax, eax
0x180028605  jns     short loc_180028631
0x180028607  mov     r9d, eax
0x18002860a  mov     r8d, 6A1h
0x180028610  jmp     short loc_180028620
0x180028612  mov     ebx, 80004005h
0x180028617  mov     r8d, 69Eh; int
0x18002861d  mov     r9d, ebx; int
0x180028620  lea     rdx, aSdpxmlgetattri; "SdpXmlGetAttribute"
0x180028627  mov     ecx, 1; Level
0x18002862c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028631  test    rdi, rdi
0x180028634  jz      short loc_180028645
0x180028636  mov     rax, [rdi]
0x180028639  mov     rcx, rdi
0x18002863c  mov     rax, [rax+10h]
0x180028640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028645  mov     rcx, [rbp+arg_10]
0x180028649  test    rcx, rcx
0x18002864c  jz      short loc_180028662
0x18002864e  mov     rax, [rcx]
0x180028651  mov     rax, [rax+10h]
0x180028655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002865a  mov     [rbp+arg_10], 0
0x180028662  mov     rcx, [rbp+var_18]
0x180028666  test    rcx, rcx
0x180028669  jz      short loc_18002867F
0x18002866b  mov     rax, [rcx]
0x18002866e  mov     rax, [rax+10h]
0x180028672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028677  mov     [rbp+var_18], 0
0x18002867f  test    rsi, rsi
0x180028682  jz      short loc_18002868D
0x180028684  mov     rcx, rsi; bstrString
0x180028687  call    cs:__imp_SysFreeString
0x18002868d  mov     eax, ebx
0x18002868f  add     rsp, 38h
0x180028693  pop     r15
0x180028695  pop     r14
0x180028697  pop     rdi
0x180028698  pop     rsi
0x180028699  pop     rbx
0x18002869a  pop     rbp
0x18002869b  retn
```
