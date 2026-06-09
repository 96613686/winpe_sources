# SdpBuildParameterXml(_SDIAG_PARAMSET *,int,IXMLDOMDocument2 * *)

- ea: `0x18000312c`
- end: `0x180003305`
- name: `?SdpBuildParameterXml@@YAJPEAU_SDIAG_PARAMSET@@HPEAPEAUIXMLDOMDocument2@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct _SDIAG_PARAMSET *, int, struct IXMLDOMDocument2 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001955c`
- `0x18001f844`

## callees

- `0x18000312c`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x18002a010`

## string_xrefs

- `0x180003154`: `<?xml version="1.0" encoding="utf-8"?><Parameters/>`
- `0x18000317f`: `SdpBuildParameterXml`
- `0x1800032e4`: `SdpBuildParameterXml`

## pseudocode

```c
__int64 __fastcall SdpBuildParameterXml(struct _SDIAG_PARAMSET *a1, int a2, struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMElement *v4; // rdi
  int Node; // eax
  struct IXMLDOMDocument2 *v7; // rsi
  unsigned int v8; // ebx
  int v9; // r8d
  __int64 v10; // r15
  int v11; // eax
  struct IXMLDOMDocument2 v12; // rax
  struct IXMLDOMDocument2 *v14; // [rsp+30h] [rbp-38h] BYREF
  struct IXMLDOMElement *v16; // [rsp+88h] [rbp+20h] BYREF

  v14 = 0;
  v4 = 0;
  v16 = 0;
  Node = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Parameters/>", &v14);
  v7 = v14;
  v8 = Node;
  if ( Node >= 0 )
  {
    if ( *(_QWORD *)a1 && (v10 = 0, *((_DWORD *)a1 + 2)) )
    {
      while ( 1 )
      {
        if ( v4 )
        {
          ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
          v16 = 0;
        }
        v11 = SdpXmlCreateNode(v7, 0, L"Parameter", 0, &v16);
        v8 = v11;
        if ( v11 < 0 )
          break;
        v4 = v16;
        Node = SdpXmlCreateNode(v7, v16, L"Name", *(const unsigned __int16 **)(*(_QWORD *)a1 + 24 * v10), 0);
        v8 = Node;
        if ( Node < 0 )
        {
          v9 = 676;
          goto LABEL_3;
        }
        Node = SdpXmlCreateNode(
                 v7,
                 v4,
                 L"Value",
                 *(const unsigned __int16 **)(*(_QWORD *)a1 + (a2 != 0 ? 16LL : 8LL) + 24 * v10),
                 0);
        v8 = Node;
        if ( Node < 0 )
        {
          v9 = 690;
          goto LABEL_3;
        }
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= *((_DWORD *)a1 + 2) )
          goto LABEL_12;
      }
      SdpDebugTrace(1u, L"SdpBuildParameterXml", 669, v11);
      v4 = v16;
    }
    else
    {
LABEL_12:
      v12.lpVtbl = v7->lpVtbl;
      *a3 = v7;
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v12.lpVtbl->AddRef)(v7);
    }
  }
  else
  {
    v9 = 647;
LABEL_3:
    SdpDebugTrace(1u, L"SdpBuildParameterXml", v9, Node);
  }
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  return v8;
}

```

## disassembly

```asm
0x18000312c  mov     rax, rsp
0x18000312f  mov     [rax+8], rbx
0x180003133  mov     [rax+18h], rsi
0x180003137  mov     [rax+10h], edx
0x18000313a  push    rdi
0x18000313b  push    r12
0x18000313d  push    r13
0x18000313f  push    r14
0x180003141  push    r15
0x180003143  sub     rsp, 40h
0x180003147  mov     r14, rcx
0x18000314a  mov     qword ptr [rax-38h], 0
0x180003152  xor     edi, edi
0x180003154  lea     rcx, aXmlVersion10En_18; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18000315b  lea     rdx, [rax-38h]; struct IXMLDOMDocument2 **
0x18000315f  mov     [rax+20h], rdi
0x180003163  mov     r13, r8
0x180003166  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18000316b  mov     rsi, [rsp+68h+var_38]
0x180003170  mov     ebx, eax
0x180003172  test    eax, eax
0x180003174  jns     short loc_180003195
0x180003176  mov     r8d, 287h; int
0x18000317c  mov     r9d, eax; int
0x18000317f  lea     rdx, aSdpbuildparame; "SdpBuildParameterXml"
0x180003186  mov     ecx, 1; Level
0x18000318b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003190  jmp     loc_180003287
0x180003195  cmp     [r14], rdi
0x180003198  jz      loc_180003274
0x18000319e  xor     r15d, r15d
0x1800031a1  cmp     [r14+8], edi
0x1800031a5  jbe     loc_180003274
0x1800031ab  test    rdi, rdi
0x1800031ae  jz      short loc_1800031CB
0x1800031b0  mov     rax, [rdi]
0x1800031b3  mov     rcx, rdi
0x1800031b6  mov     rax, [rax+10h]
0x1800031ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bf  mov     [rsp+68h+arg_18], 0
0x1800031cb  lea     rax, [rsp+68h+arg_18]
0x1800031d3  xor     r9d, r9d; unsigned __int16 *
0x1800031d6  lea     r8, aParameter; "Parameter"
0x1800031dd  mov     [rsp+68h+var_48], rax; struct IXMLDOMElement **
0x1800031e2  xor     edx, edx; struct IXMLDOMElement *
0x1800031e4  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800031e7  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800031ec  mov     ebx, eax
0x1800031ee  test    eax, eax
0x1800031f0  js      loc_1800032E1
0x1800031f6  mov     r9, [r14]
0x1800031f9  lea     r12, [r15+r15*2]
0x1800031fd  mov     rdi, [rsp+68h+arg_18]
0x180003205  lea     r8, aName; "Name"
0x18000320c  mov     rdx, rdi; struct IXMLDOMElement *
0x18000320f  mov     [rsp+68h+var_48], 0; struct IXMLDOMElement **
0x180003218  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18000321b  mov     r9, [r9+r12*8]; unsigned __int16 *
0x18000321f  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180003224  mov     ebx, eax
0x180003226  test    eax, eax
0x180003228  js      loc_1800032D6
0x18000322e  mov     eax, [rsp+68h+arg_8]
0x180003232  lea     r8, aValue; "Value"
0x180003239  neg     eax
0x18000323b  mov     [rsp+68h+var_48], 0; struct IXMLDOMElement **
0x180003244  mov     rdx, rdi; struct IXMLDOMElement *
0x180003247  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18000324a  sbb     r9, r9
0x18000324d  and     r9d, 8
0x180003251  add     r9, 8
0x180003255  add     r9, [r14]
0x180003258  mov     r9, [r9+r12*8]; unsigned __int16 *
0x18000325c  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180003261  mov     ebx, eax
0x180003263  test    eax, eax
0x180003265  js      short loc_1800032CB
0x180003267  inc     r15d
0x18000326a  cmp     r15d, [r14+8]
0x18000326e  jb      loc_1800031AB
0x180003274  mov     rax, [rsi]
0x180003277  mov     rcx, rsi
0x18000327a  mov     [r13+0], rsi
0x18000327e  mov     rax, [rax+8]
0x180003282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003287  test    rsi, rsi
0x18000328a  jz      short loc_18000329B
0x18000328c  mov     rax, [rsi]
0x18000328f  mov     rcx, rsi
0x180003292  mov     rax, [rax+10h]
0x180003296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000329b  test    rdi, rdi
0x18000329e  jz      short loc_1800032AF
0x1800032a0  mov     rax, [rdi]
0x1800032a3  mov     rcx, rdi
0x1800032a6  mov     rax, [rax+10h]
0x1800032aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032af  lea     r11, [rsp+68h+var_28]
0x1800032b4  mov     eax, ebx
0x1800032b6  mov     rbx, [r11+30h]
0x1800032ba  mov     rsi, [r11+40h]
0x1800032be  mov     rsp, r11
0x1800032c1  pop     r15
0x1800032c3  pop     r14
0x1800032c5  pop     r13
0x1800032c7  pop     r12
0x1800032c9  pop     rdi
0x1800032ca  retn
0x1800032cb  mov     r8d, 2B2h
0x1800032d1  jmp     loc_18000317C
0x1800032d6  mov     r8d, 2A4h
0x1800032dc  jmp     loc_18000317C
0x1800032e1  mov     r9d, eax; int
0x1800032e4  lea     rdx, aSdpbuildparame; "SdpBuildParameterXml"
0x1800032eb  mov     r8d, 29Dh; int
0x1800032f1  mov     ecx, 1; Level
0x1800032f6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800032fb  mov     rdi, [rsp+68h+arg_18]
0x180003303  jmp     short loc_180003287
```
