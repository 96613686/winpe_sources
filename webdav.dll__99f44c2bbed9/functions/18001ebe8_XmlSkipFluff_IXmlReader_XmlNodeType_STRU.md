# XmlSkipFluff(IXmlReader *,XmlNodeType *,STRU *)

- ea: `0x18001ebe8`
- end: `0x18001ec9d`
- name: `?XmlSkipFluff@@YAJPEAUIXmlReader@@PEAW4XmlNodeType@@PEAVSTRU@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct IXmlReader *, enum XmlNodeType *, struct STRU *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e6a4`
- `0x18001e998`

## callees

- `0x18001ebe8`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001ec6c`
- `iisutil!PuDbgPrint` at `0x18001ec6c`

## string_xrefs

- `0x18001ec48`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001ec3d`: `XmlSkipFluff`

## pseudocode

```c
__int64 __fastcall XmlSkipFluff(struct IXmlReader *a1, enum XmlNodeType *a2, unsigned __int64 a3)
{
  int v5; // eax
  int v6; // ebx
  enum XmlNodeType v8; // [rsp+60h] [rbp+18h] BYREF
  int v9; // [rsp+64h] [rbp+1Ch]

  v9 = HIDWORD(a3);
  v8 = XmlNodeType_None;
  while ( 1 )
  {
    v5 = ((__int64 (__fastcall *)(struct IXmlReader *, enum XmlNodeType *, unsigned __int64))a1->lpVtbl->Read)(
           a1,
           &v8,
           a3);
    a3 = (unsigned int)g_dwDebugFlags;
    v6 = v5;
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
        270,
        "XmlSkipFluff",
        "hr = %08lx, nodeType = %lu\n",
        v5,
        v8);
    if ( v6 < 0 || v6 == 1 )
      break;
    if ( v8 != XmlNodeType_Comment && v8 != XmlNodeType_Whitespace )
    {
      *a2 = v8;
      return (unsigned int)v6;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ebe8  mov     rax, rsp
0x18001ebeb  mov     [rax+8], rbx
0x18001ebef  mov     [rax+10h], rsi
0x18001ebf3  mov     [rax+18h], r8
0x18001ebf7  push    rdi
0x18001ebf8  sub     rsp, 40h
0x18001ebfc  mov     rdi, rdx
0x18001ebff  mov     dword ptr [rax+18h], 0
0x18001ec06  mov     rsi, rcx
0x18001ec09  mov     rax, [rsi]
0x18001ec0c  lea     rdx, [rsp+48h+arg_10]
0x18001ec11  mov     rcx, rsi
0x18001ec14  mov     rax, [rax+30h]
0x18001ec18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec1d  mov     r8d, cs:g_dwDebugFlags
0x18001ec24  mov     ebx, eax
0x18001ec26  test    r8b, 3
0x18001ec2a  setnz   dl
0x18001ec2d  bt      r8d, 1Bh
0x18001ec32  setb    cl
0x18001ec35  test    cl, dl
0x18001ec37  jz      short loc_18001EC72
0x18001ec39  mov     ecx, [rsp+48h+arg_10]
0x18001ec3d  lea     r9, aXmlskipfluff; "XmlSkipFluff"
0x18001ec44  mov     [rsp+48h+var_18], ecx
0x18001ec48  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001ec4f  mov     rcx, cs:g_pDebug
0x18001ec56  mov     r8d, 10Eh
0x18001ec5c  mov     [rsp+48h+var_20], eax
0x18001ec60  lea     rax, aHr08lxNodetype; "hr = %08lx, nodeType = %lu\n"
0x18001ec67  mov     [rsp+48h+var_28], rax
0x18001ec6c  call    cs:__imp_PuDbgPrint
0x18001ec72  test    ebx, ebx
0x18001ec74  js      short loc_18001EC8B
0x18001ec76  cmp     ebx, 1
0x18001ec79  jz      short loc_18001EC8B
0x18001ec7b  mov     eax, [rsp+48h+arg_10]
0x18001ec7f  cmp     eax, 8
0x18001ec82  jz      short loc_18001EC09
0x18001ec84  cmp     eax, 0Dh
0x18001ec87  jz      short loc_18001EC09
0x18001ec89  mov     [rdi], eax
0x18001ec8b  mov     rsi, [rsp+48h+arg_8]
0x18001ec90  mov     eax, ebx
0x18001ec92  mov     rbx, [rsp+48h+arg_0]
0x18001ec97  add     rsp, 40h
0x18001ec9b  pop     rdi
0x18001ec9c  retn
```
