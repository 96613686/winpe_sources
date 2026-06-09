# XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)

- ea: `0x18001e998`
- end: `0x18001ea63`
- name: `?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct IXmlReader *, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800121d8`
- `0x180012c54`
- `0x180013254`
- `0x1800134f0`
- `0x180013858`

## callees

- `0x18001e5e4`
- `0x18001e998`
- `0x18001eb10`
- `0x18001ebe8`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001e9f7`
- `iisutil!PuDbgPrint` at `0x18001e9f7`

## string_xrefs

- `0x18001e9e5`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e9de`: `XmlFindNextSubElement`

## pseudocode

```c
__int64 __fastcall XmlFindNextSubElement(
        struct IXmlReader *a1,
        unsigned int a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4)
{
  struct STRU *v8; // r8
  __int64 result; // rax
  enum XmlNodeType v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = XmlNodeType_None;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
      523,
      "XmlFindNextSubElement",
      "searching for depth %u\n",
      a2);
  if ( ((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1)
    || (result = XmlFindEndElementAtDepth(a1, a2), (int)result >= 0) )
  {
    result = XmlSkipFluff(a1, &v10, v8);
    if ( (int)result >= 0 )
    {
      if ( v10 == XmlNodeType_Element )
      {
        return XmlGetNamespaceAndName(a1, a3, a4);
      }
      else
      {
        result = 2147942487LL;
        if ( v10 == XmlNodeType_EndElement )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e998  push    rbx
0x18001e99a  push    rbp
0x18001e99b  push    rsi
0x18001e99c  push    rdi
0x18001e99d  sub     rsp, 38h
0x18001e9a1  mov     eax, cs:g_dwDebugFlags
0x18001e9a7  mov     rsi, r9
0x18001e9aa  test    al, 3
0x18001e9ac  mov     [rsp+58h+arg_0], 0
0x18001e9b4  mov     rbp, r8
0x18001e9b7  mov     edi, edx
0x18001e9b9  setnz   r10b
0x18001e9bd  mov     rbx, rcx
0x18001e9c0  bt      eax, 1Bh
0x18001e9c4  setb    al
0x18001e9c7  test    al, r10b
0x18001e9ca  jz      short loc_18001E9FD
0x18001e9cc  mov     rcx, cs:g_pDebug
0x18001e9d3  lea     rax, aSearchingForDe; "searching for depth %u\n"
0x18001e9da  mov     [rsp+58h+var_30], edx
0x18001e9de  lea     r9, aXmlfindnextsub; "XmlFindNextSubElement"
0x18001e9e5  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e9ec  mov     [rsp+58h+var_38], rax
0x18001e9f1  mov     r8d, 20Bh
0x18001e9f7  call    cs:__imp_PuDbgPrint
0x18001e9fd  mov     rax, [rbx]
0x18001ea00  mov     rcx, rbx
0x18001ea03  mov     rax, [rax+0A0h]
0x18001ea0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea0f  test    eax, eax
0x18001ea11  jnz     short loc_18001EA21
0x18001ea13  mov     edx, edi; unsigned int
0x18001ea15  mov     rcx, rbx; struct IXmlReader *
0x18001ea18  call    ?XmlFindEndElementAtDepth@@YAJPEAUIXmlReader@@I@Z; XmlFindEndElementAtDepth(IXmlReader *,uint)
0x18001ea1d  test    eax, eax
0x18001ea1f  js      short loc_18001EA5A
0x18001ea21  lea     rdx, [rsp+58h+arg_0]; enum XmlNodeType *
0x18001ea26  mov     rcx, rbx; struct IXmlReader *
0x18001ea29  call    ?XmlSkipFluff@@YAJPEAUIXmlReader@@PEAW4XmlNodeType@@PEAVSTRU@@@Z; XmlSkipFluff(IXmlReader *,XmlNodeType *,STRU *)
0x18001ea2e  test    eax, eax
0x18001ea30  js      short loc_18001EA5A
0x18001ea32  mov     ecx, 1
0x18001ea37  cmp     [rsp+58h+arg_0], ecx
0x18001ea3b  jnz     short loc_18001EA4D
0x18001ea3d  mov     r8, rsi; unsigned __int16 **
0x18001ea40  mov     rdx, rbp; unsigned __int16 **
0x18001ea43  mov     rcx, rbx; struct IXmlReader *
0x18001ea46  call    ?XmlGetNamespaceAndName@@YAJPEAUIXmlReader@@PEAPEBG1@Z; XmlGetNamespaceAndName(IXmlReader *,ushort const * *,ushort const * *)
0x18001ea4b  jmp     short loc_18001EA5A
0x18001ea4d  cmp     [rsp+58h+arg_0], 0Fh
0x18001ea52  mov     eax, 80070057h
0x18001ea57  cmovz   eax, ecx
0x18001ea5a  add     rsp, 38h
0x18001ea5e  pop     rdi
0x18001ea5f  pop     rsi
0x18001ea60  pop     rbp
0x18001ea61  pop     rbx
0x18001ea62  retn
```
