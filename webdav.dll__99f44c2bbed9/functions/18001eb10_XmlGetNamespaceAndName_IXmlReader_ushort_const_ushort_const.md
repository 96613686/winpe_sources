# XmlGetNamespaceAndName(IXmlReader *,ushort const * *,ushort const * *)

- ea: `0x18001eb10`
- end: `0x18001ebdf`
- name: `?XmlGetNamespaceAndName@@YAJPEAUIXmlReader@@PEAPEBG1@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct IXmlReader *, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800122e0`
- `0x1800124f8`
- `0x180012970`
- `0x18001e184`
- `0x18001e6a4`
- `0x18001e998`

## callees

- `0x18001eb10`
- `0x180023010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001ebb9`
- `iisutil!PuDbgPrint` at `0x18001ebb9`

## string_xrefs

- `0x18001eb91`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001eb83`: `XmlGetNamespaceAndName`

## pseudocode

```c
__int64 __fastcall XmlGetNamespaceAndName(
        struct IXmlReader *a1,
        const unsigned __int16 **a2,
        const unsigned __int16 **a3)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v7; // ebx
  const unsigned __int16 *v9; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *v10; // [rsp+68h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  v10 = 0;
  v9 = 0;
  v7 = ((__int64 (__fastcall *)(struct IXmlReader *, const unsigned __int16 **, _QWORD))lpVtbl->GetNamespaceUri)(
         a1,
         &v9,
         0);
  if ( v7 >= 0 )
    v7 = ((__int64 (__fastcall *)(struct IXmlReader *, const unsigned __int16 **, _QWORD))a1->lpVtbl->GetLocalName)(
           a1,
           &v10,
           0);
  if ( (g_dwDebugFlags & 0x8000000) != 0 && v7 >= 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
      203,
      "XmlGetNamespaceAndName",
      "found %ws:%ws\n",
      v9,
      v10);
  *a2 = v9;
  *a3 = v10;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001eb10  mov     r11, rsp
0x18001eb13  mov     [r11+18h], rbx
0x18001eb17  push    rsi
0x18001eb18  push    rdi
0x18001eb19  push    r14
0x18001eb1b  sub     rsp, 40h
0x18001eb1f  mov     rax, [rcx]
0x18001eb22  mov     rsi, r8
0x18001eb25  mov     r14, rdx
0x18001eb28  mov     qword ptr [r11+10h], 0
0x18001eb30  xor     r8d, r8d
0x18001eb33  mov     qword ptr [r11+8], 0
0x18001eb3b  lea     rdx, [r11+8]
0x18001eb3f  mov     rdi, rcx
0x18001eb42  mov     rax, [rax+68h]
0x18001eb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb4b  mov     ebx, eax
0x18001eb4d  test    eax, eax
0x18001eb4f  js      short loc_18001EB6A
0x18001eb51  mov     rax, [rdi]
0x18001eb54  lea     rdx, [rsp+58h+arg_8]
0x18001eb59  xor     r8d, r8d
0x18001eb5c  mov     rcx, rdi
0x18001eb5f  mov     rax, [rax+70h]
0x18001eb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb68  mov     ebx, eax
0x18001eb6a  mov     eax, cs:g_dwDebugFlags
0x18001eb70  bt      eax, 1Bh
0x18001eb74  jnb     short loc_18001EBBF
0x18001eb76  test    ebx, ebx
0x18001eb78  js      short loc_18001EBBF
0x18001eb7a  test    al, 3
0x18001eb7c  jz      short loc_18001EBBF
0x18001eb7e  mov     rax, [rsp+58h+arg_8]
0x18001eb83  lea     r9, aXmlgetnamespac; "XmlGetNamespaceAndName"
0x18001eb8a  mov     rcx, cs:g_pDebug
0x18001eb91  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001eb98  mov     [rsp+58h+var_28], rax
0x18001eb9d  mov     r8d, 0CBh
0x18001eba3  mov     rax, [rsp+58h+arg_0]
0x18001eba8  mov     [rsp+58h+var_30], rax
0x18001ebad  lea     rax, aFoundWsWs; "found %ws:%ws\n"
0x18001ebb4  mov     [rsp+58h+var_38], rax
0x18001ebb9  call    cs:__imp_PuDbgPrint
0x18001ebbf  mov     rax, [rsp+58h+arg_0]
0x18001ebc4  mov     [r14], rax
0x18001ebc7  mov     rax, [rsp+58h+arg_8]
0x18001ebcc  mov     [rsi], rax
0x18001ebcf  mov     eax, ebx
0x18001ebd1  mov     rbx, [rsp+58h+arg_10]
0x18001ebd6  add     rsp, 40h
0x18001ebda  pop     r14
0x18001ebdc  pop     rdi
0x18001ebdd  pop     rsi
0x18001ebde  retn
```
