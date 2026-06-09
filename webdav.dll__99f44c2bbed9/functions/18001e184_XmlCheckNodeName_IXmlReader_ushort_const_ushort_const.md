# XmlCheckNodeName(IXmlReader *,ushort const *,ushort const *)

- ea: `0x18001e184`
- end: `0x18001e288`
- name: `?XmlCheckNodeName@@YAJPEAUIXmlReader@@PEBG1@Z`
- size: `260`
- prototype: `__int64 __fastcall(struct IXmlReader *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012c54`
- `0x180013254`
- `0x1800134f0`

## callees

- `0x18001e184`
- `0x18001eb10`
- `0x1800224e6`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001e266`
- `iisutil!PuDbgPrint` at `0x18001e266`

## string_xrefs

- `0x18001e24a`: `inetsrv\iis\iisrearc\iis70\webdav\module\lib\xml_util.cxx`
- `0x18001e23e`: `XmlCheckNodeName`

## pseudocode

```c
__int64 __fastcall XmlCheckNodeName(struct IXmlReader *a1, const unsigned __int16 *a2, char *a3)
{
  int NamespaceAndName; // ebx
  wchar_t *v5; // rsi
  const unsigned __int16 *v6; // rdi
  const unsigned __int16 *v7; // rax
  int v8; // r8d
  int v9; // edx
  const unsigned __int16 *v11; // [rsp+78h] [rbp+10h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+20h] BYREF

  String1 = 0;
  v11 = 0;
  NamespaceAndName = XmlGetNamespaceAndName(a1, (const unsigned __int16 **)&String1, &v11);
  if ( NamespaceAndName >= 0 )
  {
    v5 = String1;
    v6 = v11;
    if ( !String1 || !v11 || wcscmp_0(String1, L"DAV:") )
      goto LABEL_9;
    v7 = v6;
    do
    {
      v8 = *(const unsigned __int16 *)((char *)v7 + a3 - (char *)v6);
      v9 = *v7 - v8;
      if ( v9 )
        break;
      ++v7;
    }
    while ( v8 );
    if ( v9 )
    {
LABEL_9:
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x8000000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\lib\\xml_util.cxx",
          239,
          "XmlCheckNodeName",
          "looking for %ws:%ws, found %ws:%ws\n",
          L"DAV:",
          a3,
          v5,
          v6);
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)NamespaceAndName;
}

```

## disassembly

```asm
0x18001e184  mov     rax, rsp
0x18001e187  mov     [rax+8], rbx
0x18001e18b  mov     [rax+18h], rbp
0x18001e18f  mov     [rax+10h], rdx
0x18001e193  push    rsi
0x18001e194  push    rdi
0x18001e195  push    r14
0x18001e197  sub     rsp, 50h
0x18001e19b  mov     rbp, r8
0x18001e19e  mov     qword ptr [rax+20h], 0
0x18001e1a6  lea     r8, [rax+10h]; unsigned __int16 **
0x18001e1aa  mov     qword ptr [rax+10h], 0
0x18001e1b2  lea     rdx, [rax+20h]; unsigned __int16 **
0x18001e1b6  call    ?XmlGetNamespaceAndName@@YAJPEAUIXmlReader@@PEAPEBG1@Z; XmlGetNamespaceAndName(IXmlReader *,ushort const * *,ushort const * *)
0x18001e1bb  mov     ebx, eax
0x18001e1bd  test    eax, eax
0x18001e1bf  js      loc_18001E271
0x18001e1c5  mov     rsi, [rsp+68h+String1]
0x18001e1cd  lea     r14, aDav; "DAV:"
0x18001e1d4  mov     rdi, [rsp+68h+arg_8]
0x18001e1d9  test    rsi, rsi
0x18001e1dc  jz      short loc_18001E215
0x18001e1de  test    rdi, rdi
0x18001e1e1  jz      short loc_18001E215
0x18001e1e3  mov     rdx, r14; String2
0x18001e1e6  mov     rcx, rsi; String1
0x18001e1e9  call    wcscmp_0
0x18001e1ee  test    eax, eax
0x18001e1f0  jnz     short loc_18001E215
0x18001e1f2  mov     rcx, rbp
0x18001e1f5  mov     rax, rdi
0x18001e1f8  sub     rcx, rdi
0x18001e1fb  movzx   edx, word ptr [rax]
0x18001e1fe  movzx   r8d, word ptr [rax+rcx]
0x18001e203  sub     edx, r8d
0x18001e206  jnz     short loc_18001E211
0x18001e208  add     rax, 2
0x18001e20c  test    r8d, r8d
0x18001e20f  jnz     short loc_18001E1FB
0x18001e211  test    edx, edx
0x18001e213  jz      short loc_18001E271
0x18001e215  mov     eax, cs:g_dwDebugFlags
0x18001e21b  test    al, 3
0x18001e21d  setnz   cl
0x18001e220  bt      eax, 1Bh
0x18001e224  setb    al
0x18001e227  test    al, cl
0x18001e229  jz      short loc_18001E26C
0x18001e22b  mov     rcx, cs:g_pDebug
0x18001e232  lea     rax, aLookingForWsWs; "looking for %ws:%ws, found %ws:%ws\n"
0x18001e239  mov     [rsp+68h+var_28], rdi
0x18001e23e  lea     r9, aXmlchecknodena; "XmlCheckNodeName"
0x18001e245  mov     [rsp+68h+var_30], rsi
0x18001e24a  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x18001e251  mov     [rsp+68h+var_38], rbp
0x18001e256  mov     r8d, 0EFh
0x18001e25c  mov     [rsp+68h+var_40], r14
0x18001e261  mov     [rsp+68h+var_48], rax
0x18001e266  call    cs:__imp_PuDbgPrint
0x18001e26c  mov     ebx, 80070057h
0x18001e271  lea     r11, [rsp+68h+var_18]
0x18001e276  mov     eax, ebx
0x18001e278  mov     rbx, [r11+20h]
0x18001e27c  mov     rbp, [r11+30h]
0x18001e280  mov     rsp, r11
0x18001e283  pop     r14
0x18001e285  pop     rdi
0x18001e286  pop     rsi
0x18001e287  retn
```
