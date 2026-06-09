# XmlSkipRemainingNodes(IXmlReader *)

- ea: `0x18001eca4`
- end: `0x18001eda4`
- name: `?XmlSkipRemainingNodes@@YAJPEAUIXmlReader@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct IXmlReader *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013254`
- `0x1800134f0`

## callees

- `0x18001eca4`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001ed32`
- `iisutil!PuDbgPrint` at `0x18001ed8a`
- `iisutil!PuDbgPrint` at `0x18001ed32`
- `iisutil!PuDbgPrint` at `0x18001ed8a`

## string_xrefs

- `0x18001ed1c`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001ed6d`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001ed0e`: `XmlSkipRemainingNodes`
- `0x18001ed5f`: `XmlSkipRemainingNodes`

## pseudocode

```c
__int64 __fastcall XmlSkipRemainingNodes(struct IXmlReader *a1)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v4; // ebx
  int v5; // eax
  int v6; // [rsp+50h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v6 = 0;
  if ( ((unsigned int (__fastcall *)(struct IXmlReader *))lpVtbl->IsEOF)(a1) )
    return 0;
  while ( 1 )
  {
    v4 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->Read)(a1, &v6);
    v5 = g_dwDebugFlags;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
        658,
        "XmlSkipRemainingNodes",
        "hr = %08lx, nodeType = %lu\n",
        v4,
        v6);
      v5 = g_dwDebugFlags;
    }
    if ( v4 == 1 )
      break;
    if ( v4 < 0 )
      return (unsigned int)v4;
    if ( (v5 & 3) != 0 && (v5 & 0x8000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
        674,
        "XmlSkipRemainingNodes",
        "skipping %lu\n",
        v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18001eca4  mov     [rsp+arg_8], rbx
0x18001eca9  push    rdi
0x18001ecaa  sub     rsp, 40h
0x18001ecae  mov     rax, [rcx]
0x18001ecb1  mov     rdi, rcx
0x18001ecb4  mov     [rsp+48h+arg_0], 0
0x18001ecbc  mov     rax, [rax+0C8h]
0x18001ecc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecc8  test    eax, eax
0x18001ecca  jz      short loc_18001ECD3
0x18001eccc  xor     eax, eax
0x18001ecce  jmp     loc_18001ED99
0x18001ecd3  mov     rax, [rdi]
0x18001ecd6  lea     rdx, [rsp+48h+arg_0]
0x18001ecdb  mov     rcx, rdi
0x18001ecde  mov     rax, [rax+30h]
0x18001ece2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ece7  mov     ebx, eax
0x18001ece9  mov     eax, cs:g_dwDebugFlags
0x18001ecef  test    al, 3
0x18001ecf1  setnz   dl
0x18001ecf4  bt      eax, 1Bh
0x18001ecf8  setb    cl
0x18001ecfb  test    cl, dl
0x18001ecfd  jz      short loc_18001ED3E
0x18001ecff  mov     ecx, [rsp+48h+arg_0]
0x18001ed03  lea     rax, aHr08lxNodetype; "hr = %08lx, nodeType = %lu\n"
0x18001ed0a  mov     [rsp+48h+var_18], ecx
0x18001ed0e  lea     r9, aXmlskipremaini; "XmlSkipRemainingNodes"
0x18001ed15  mov     rcx, cs:g_pDebug
0x18001ed1c  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001ed23  mov     [rsp+48h+var_20], ebx
0x18001ed27  mov     r8d, 292h
0x18001ed2d  mov     [rsp+48h+var_28], rax
0x18001ed32  call    cs:__imp_PuDbgPrint
0x18001ed38  mov     eax, cs:g_dwDebugFlags
0x18001ed3e  cmp     ebx, 1
0x18001ed41  jz      short loc_18001ED95
0x18001ed43  test    ebx, ebx
0x18001ed45  js      short loc_18001ED97
0x18001ed47  test    al, 3
0x18001ed49  setnz   cl
0x18001ed4c  bt      eax, 1Bh
0x18001ed50  setb    al
0x18001ed53  test    al, cl
0x18001ed55  jz      loc_18001ECD3
0x18001ed5b  mov     eax, [rsp+48h+arg_0]
0x18001ed5f  lea     r9, aXmlskipremaini; "XmlSkipRemainingNodes"
0x18001ed66  mov     rcx, cs:g_pDebug
0x18001ed6d  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001ed74  mov     [rsp+48h+var_20], eax
0x18001ed78  mov     r8d, 2A2h
0x18001ed7e  lea     rax, aSkippingLu; "skipping %lu\n"
0x18001ed85  mov     [rsp+48h+var_28], rax
0x18001ed8a  call    cs:__imp_PuDbgPrint
0x18001ed90  jmp     loc_18001ECD3
0x18001ed95  xor     ebx, ebx
0x18001ed97  mov     eax, ebx
0x18001ed99  mov     rbx, [rsp+48h+arg_8]
0x18001ed9e  add     rsp, 40h
0x18001eda2  pop     rdi
0x18001eda3  retn
```
