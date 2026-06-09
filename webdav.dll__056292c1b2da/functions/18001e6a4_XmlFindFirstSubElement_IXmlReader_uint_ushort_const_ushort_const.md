# XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)

- ea: `0x18001e6a4`
- end: `0x18001e891`
- name: `?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct IXmlReader *, unsigned int *, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800121d8`
- `0x180012c54`
- `0x180013254`
- `0x1800134f0`
- `0x180013858`

## callees

- `0x18001e6a4`
- `0x18001eb10`
- `0x18001ebe8`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001e71d`
- `iisutil!PuDbgPrint` at `0x18001e7a0`
- `iisutil!PuDbgPrint` at `0x18001e831`
- `iisutil!PuDbgPrint` at `0x18001e87c`
- `iisutil!PuDbgPrint` at `0x18001e71d`
- `iisutil!PuDbgPrint` at `0x18001e7a0`
- `iisutil!PuDbgPrint` at `0x18001e831`
- `iisutil!PuDbgPrint` at `0x18001e87c`

## string_xrefs

- `0x18001e716`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e799`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e81f`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e875`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e704`: `XmlFindFirstSubElement`
- `0x18001e787`: `XmlFindFirstSubElement`
- `0x18001e818`: `XmlFindFirstSubElement`
- `0x18001e863`: `XmlFindFirstSubElement`

## pseudocode

```c
__int64 __fastcall XmlFindFirstSubElement(
        struct IXmlReader *a1,
        unsigned int *a2,
        const unsigned __int16 **a3,
        const unsigned __int16 **a4)
{
  struct STRU *v8; // r8
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // edi
  XmlNodeType v12; // edi
  int NamespaceAndName; // ebx
  int v14; // eax
  int v15; // edx
  bool v16; // zf
  _DWORD v17[18]; // [rsp+30h] [rbp-48h] BYREF
  XmlNodeType v18; // [rsp+80h] [rbp+8h] BYREF

  v18 = XmlNodeType_None;
  v17[0] = 0;
  if ( ((unsigned int (__fastcall *)(struct IXmlReader *))a1->lpVtbl->IsEmptyElement)(a1) )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
        387,
        "XmlFindFirstSubElement",
        "EMPTY\n");
    return 1;
  }
  else
  {
    v10 = XmlSkipFluff(a1, &v18, v8);
    v11 = v10;
    if ( v10 < 0 || v10 == 1 )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
          399,
          "XmlFindFirstSubElement",
          "cannot skip fluff %08lx\n",
          v10);
      return v11;
    }
    else
    {
      v12 = v18;
      if ( v18 == XmlNodeType_Element )
      {
        NamespaceAndName = XmlGetNamespaceAndName(a1, a3, a4);
        if ( NamespaceAndName >= 0 )
        {
          NamespaceAndName = ((__int64 (__fastcall *)(struct IXmlReader *, _DWORD *))a1->lpVtbl->GetDepth)(a1, v17);
          if ( NamespaceAndName >= 0 )
          {
            v14 = g_dwDebugFlags;
            v15 = v17[0] + 1;
            v16 = (g_dwDebugFlags & 3) == 0;
            *a2 = v17[0] + 1;
            if ( !v16 && (v14 & 0x8000000) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
                430,
                "XmlFindFirstSubElement",
                "search depth = %u\n",
                v15);
          }
        }
        return (unsigned int)NamespaceAndName;
      }
      else
      {
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
            409,
            "XmlFindFirstSubElement",
            "nodeType %lu, probably not expected\n",
            v18);
        result = 2147942487LL;
        if ( v12 == XmlNodeType_EndElement )
          return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e6a4  mov     rax, rsp
0x18001e6a7  push    rbx
0x18001e6a8  push    rbp
0x18001e6a9  push    rsi
0x18001e6aa  push    rdi
0x18001e6ab  push    r14
0x18001e6ad  push    r15
0x18001e6af  sub     rsp, 48h
0x18001e6b3  mov     dword ptr [rax+8], 0
0x18001e6ba  mov     rbp, r9
0x18001e6bd  mov     dword ptr [rax-48h], 0
0x18001e6c4  mov     r14, r8
0x18001e6c7  mov     rax, [rcx]
0x18001e6ca  mov     r15, rdx
0x18001e6cd  mov     rsi, rcx
0x18001e6d0  mov     rax, [rax+0A0h]
0x18001e6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6dc  test    eax, eax
0x18001e6de  jz      short loc_18001E72D
0x18001e6e0  mov     eax, cs:g_dwDebugFlags
0x18001e6e6  test    al, 3
0x18001e6e8  setnz   cl
0x18001e6eb  bt      eax, 1Bh
0x18001e6ef  setb    al
0x18001e6f2  test    al, cl
0x18001e6f4  jz      short loc_18001E723
0x18001e6f6  mov     rcx, cs:g_pDebug
0x18001e6fd  lea     rax, aEmpty; "EMPTY\n"
0x18001e704  lea     r9, aXmlfindfirstsu; "XmlFindFirstSubElement"
0x18001e70b  mov     [rsp+78h+var_58], rax
0x18001e710  mov     r8d, 183h
0x18001e716  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e71d  call    cs:__imp_PuDbgPrint
0x18001e723  mov     eax, 1
0x18001e728  jmp     loc_18001E884
0x18001e72d  lea     rdx, [rsp+78h+arg_0]; enum XmlNodeType *
0x18001e735  mov     rcx, rsi; struct IXmlReader *
0x18001e738  call    ?XmlSkipFluff@@YAJPEAUIXmlReader@@PEAW4XmlNodeType@@PEAVSTRU@@@Z; XmlSkipFluff(IXmlReader *,XmlNodeType *,STRU *)
0x18001e73d  mov     edi, eax
0x18001e73f  test    eax, eax
0x18001e741  js      loc_18001E83B
0x18001e747  mov     ebx, 1
0x18001e74c  cmp     eax, ebx
0x18001e74e  jz      loc_18001E83B
0x18001e754  mov     edi, [rsp+78h+arg_0]
0x18001e75b  cmp     edi, ebx
0x18001e75d  jz      short loc_18001E7B6
0x18001e75f  mov     eax, cs:g_dwDebugFlags
0x18001e765  test    al, 3
0x18001e767  setnz   cl
0x18001e76a  bt      eax, 1Bh
0x18001e76e  setb    al
0x18001e771  test    al, cl
0x18001e773  jz      short loc_18001E7A6
0x18001e775  mov     rcx, cs:g_pDebug
0x18001e77c  lea     rax, aNodetypeLuProb; "nodeType %lu, probably not expected\n"
0x18001e783  mov     [rsp+78h+var_50], edi
0x18001e787  lea     r9, aXmlfindfirstsu; "XmlFindFirstSubElement"
0x18001e78e  mov     r8d, 199h
0x18001e794  mov     [rsp+78h+var_58], rax
0x18001e799  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e7a0  call    cs:__imp_PuDbgPrint
0x18001e7a6  cmp     edi, 0Fh
0x18001e7a9  mov     eax, 80070057h
0x18001e7ae  cmovz   eax, ebx
0x18001e7b1  jmp     loc_18001E884
0x18001e7b6  mov     r8, rbp; unsigned __int16 **
0x18001e7b9  mov     rdx, r14; unsigned __int16 **
0x18001e7bc  mov     rcx, rsi; struct IXmlReader *
0x18001e7bf  call    ?XmlGetNamespaceAndName@@YAJPEAUIXmlReader@@PEAPEBG1@Z; XmlGetNamespaceAndName(IXmlReader *,ushort const * *,ushort const * *)
0x18001e7c4  mov     ebx, eax
0x18001e7c6  test    eax, eax
0x18001e7c8  js      short loc_18001E837
0x18001e7ca  mov     rax, [rsi]
0x18001e7cd  lea     rdx, [rsp+78h+var_48]
0x18001e7d2  mov     rcx, rsi
0x18001e7d5  mov     rax, [rax+0C0h]
0x18001e7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7e1  mov     ebx, eax
0x18001e7e3  test    eax, eax
0x18001e7e5  js      short loc_18001E837
0x18001e7e7  mov     eax, cs:g_dwDebugFlags
0x18001e7ed  mov     edx, [rsp+78h+var_48]
0x18001e7f1  inc     edx
0x18001e7f3  test    al, 3
0x18001e7f5  mov     [r15], edx
0x18001e7f8  setnz   cl
0x18001e7fb  bt      eax, 1Bh
0x18001e7ff  setb    al
0x18001e802  test    al, cl
0x18001e804  jz      short loc_18001E837
0x18001e806  mov     rcx, cs:g_pDebug
0x18001e80d  lea     rax, aSearchDepthU; "search depth = %u\n"
0x18001e814  mov     [rsp+78h+var_50], edx
0x18001e818  lea     r9, aXmlfindfirstsu; "XmlFindFirstSubElement"
0x18001e81f  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e826  mov     [rsp+78h+var_58], rax
0x18001e82b  mov     r8d, 1AEh
0x18001e831  call    cs:__imp_PuDbgPrint
0x18001e837  mov     eax, ebx
0x18001e839  jmp     short loc_18001E884
0x18001e83b  mov     eax, cs:g_dwDebugFlags
0x18001e841  test    al, 3
0x18001e843  setnz   cl
0x18001e846  bt      eax, 1Bh
0x18001e84a  setb    al
0x18001e84d  test    al, cl
0x18001e84f  jz      short loc_18001E882
0x18001e851  mov     rcx, cs:g_pDebug
0x18001e858  lea     rax, aCannotSkipFluf; "cannot skip fluff %08lx\n"
0x18001e85f  mov     [rsp+78h+var_50], edi
0x18001e863  lea     r9, aXmlfindfirstsu; "XmlFindFirstSubElement"
0x18001e86a  mov     r8d, 18Fh
0x18001e870  mov     [rsp+78h+var_58], rax
0x18001e875  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e87c  call    cs:__imp_PuDbgPrint
0x18001e882  mov     eax, edi
0x18001e884  add     rsp, 48h
0x18001e888  pop     r15
0x18001e88a  pop     r14
0x18001e88c  pop     rdi
0x18001e88d  pop     rsi
0x18001e88e  pop     rbp
0x18001e88f  pop     rbx
0x18001e890  retn
```
