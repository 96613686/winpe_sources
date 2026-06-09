# XmlFindNodeByType(IXmlReader *,XmlNodeType)

- ea: `0x18001ea6c`
- end: `0x18001eb0a`
- name: `?XmlFindNodeByType@@YAJPEAUIXmlReader@@W4XmlNodeType@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(struct IXmlReader *, enum XmlNodeType)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012c54`
- `0x180013254`
- `0x1800134f0`
- `0x18001e5e4`

## callees

- `0x18001ea6c`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001eae8`
- `iisutil!PuDbgPrint` at `0x18001eae8`

## string_xrefs

- `0x18001eab9`: `XmlFindNodeByType`
- `0x18001eac4`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`

## pseudocode

```c
__int64 __fastcall XmlFindNodeByType(struct IXmlReader *a1, enum XmlNodeType a2)
{
  int v4; // eax
  int v5; // ebx
  int v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  do
  {
    v4 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a1->lpVtbl->Read)(a1, &v7);
    v5 = v4;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
        165,
        "XmlFindNodeByType",
        "hr = %08lx, currentNode = %lu\n",
        v4,
        v7);
  }
  while ( v5 >= 0 && v7 != a2 );
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ea6c  mov     [rsp+arg_8], rbx
0x18001ea71  mov     [rsp+arg_10], rsi
0x18001ea76  push    rdi
0x18001ea77  sub     rsp, 40h
0x18001ea7b  mov     edi, edx
0x18001ea7d  mov     [rsp+48h+arg_0], 0
0x18001ea85  mov     rsi, rcx
0x18001ea88  mov     rax, [rsi]
0x18001ea8b  lea     rdx, [rsp+48h+arg_0]
0x18001ea90  mov     rcx, rsi
0x18001ea93  mov     rax, [rax+30h]
0x18001ea97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea9c  mov     ecx, cs:g_dwDebugFlags
0x18001eaa2  mov     ebx, eax
0x18001eaa4  test    cl, 3
0x18001eaa7  setnz   dl
0x18001eaaa  bt      ecx, 1Bh
0x18001eaae  setb    cl
0x18001eab1  test    cl, dl
0x18001eab3  jz      short loc_18001EAEE
0x18001eab5  mov     ecx, [rsp+48h+arg_0]
0x18001eab9  lea     r9, aXmlfindnodebyt; "XmlFindNodeByType"
0x18001eac0  mov     [rsp+48h+var_18], ecx
0x18001eac4  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001eacb  mov     rcx, cs:g_pDebug
0x18001ead2  mov     r8d, 0A5h
0x18001ead8  mov     [rsp+48h+var_20], eax
0x18001eadc  lea     rax, aHr08lxCurrentn; "hr = %08lx, currentNode = %lu\n"
0x18001eae3  mov     [rsp+48h+var_28], rax
0x18001eae8  call    cs:__imp_PuDbgPrint
0x18001eaee  test    ebx, ebx
0x18001eaf0  js      short loc_18001EAF8
0x18001eaf2  cmp     [rsp+48h+arg_0], edi
0x18001eaf6  jnz     short loc_18001EA88
0x18001eaf8  mov     rsi, [rsp+48h+arg_10]
0x18001eafd  mov     eax, ebx
0x18001eaff  mov     rbx, [rsp+48h+arg_8]
0x18001eb04  add     rsp, 40h
0x18001eb08  pop     rdi
0x18001eb09  retn
```
