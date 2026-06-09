# XML_RESPONDER::SendXmlPropfindResponse(ushort const *,ushort const *,DAV_NAMESPACE_SET *,int)

- ea: `0x180015790`
- end: `0x1800158a0`
- name: `?SendXmlPropfindResponse@XML_RESPONDER@@QEAAJPEBG0PEAVDAV_NAMESPACE_SET@@H@Z`
- size: `272`
- prototype: `__int64 __fastcall(XML_RESPONDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct DAV_NAMESPACE_SET *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e6e0`

## callees

- `0x180013fd4`
- `0x180014404`
- `0x1800145a8`
- `0x180014ef4`
- `0x18001526c`
- `0x180015790`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800157f0`
- `iisutil!PuDbgPrint` at `0x1800157f0`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18001580f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180015835`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18001580f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180015835`

## string_xrefs

- `0x1800157e4`: `inetsrv\iis\iisrearc\iis70\webdav\module\src\xml_response.cxx`
- `0x1800157d2`: `XML_RESPONDER::SendXmlPropfindResponse`

## pseudocode

```c
int __fastcall XML_RESPONDER::SendXmlPropfindResponse(
        XML_RESPONDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct DAV_NAMESPACE_SET *a4,
        int a5)
{
  int result; // eax

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\xml_response.cxx",
      203,
      "XML_RESPONDER::SendXmlPropfindResponse",
      "HRef = %ws%ws\n",
      a2,
      a3);
  **((_BYTE **)this + 7) = 0;
  *((_DWORD *)this + 18) = 0;
  result = STRA::Append((XML_RESPONDER *)((char *)this + 24), "<D:response");
  if ( result >= 0 )
  {
    if ( !a4 || (result = XML_RENDERER::AppendNamespacePrefixes(this, a4), result >= 0) )
    {
      result = STRA::Append((XML_RESPONDER *)((char *)this + 24), *((const char **)this + 2));
      if ( result >= 0 )
      {
        result = XML_RENDERER::AppendHRef((const char **)this, a2, a3);
        if ( result >= 0 )
        {
          result = XML_RENDERER::AppendNamespaceSet(this, a4, 1, a5, 0x194u);
          if ( result >= 0 )
          {
            result = XML_RENDERER::OpenOrCloseXmlTag(this, "response", 1);
            if ( result >= 0 )
              return XML_RESPONDER::Flush(this);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015790  push    rbx
0x180015792  push    rbp
0x180015793  push    rsi
0x180015794  push    rdi
0x180015795  push    r14
0x180015797  sub     rsp, 40h
0x18001579b  mov     eax, cs:g_dwDebugFlags
0x1800157a1  mov     rsi, r9
0x1800157a4  test    al, 3
0x1800157a6  mov     rbp, r8
0x1800157a9  mov     r14, rdx
0x1800157ac  mov     rbx, rcx
0x1800157af  setnz   r10b
0x1800157b3  bt      eax, 1Ah
0x1800157b7  setb    al
0x1800157ba  test    al, r10b
0x1800157bd  jz      short loc_1800157F6
0x1800157bf  mov     rcx, cs:g_pDebug
0x1800157c6  lea     rax, aHrefWsWs; "HRef = %ws%ws\n"
0x1800157cd  mov     [rsp+68h+var_38], r8
0x1800157d2  lea     r9, aXmlResponderSe_0; "XML_RESPONDER::SendXmlPropfindResponse"
0x1800157d9  mov     [rsp+68h+var_40], rdx
0x1800157de  mov     r8d, 0CBh
0x1800157e4  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x1800157eb  mov     qword ptr [rsp+68h+var_48], rax
0x1800157f0  call    cs:__imp_PuDbgPrint
0x1800157f6  mov     rax, [rbx+38h]
0x1800157fa  lea     rdx, aDResponse; "<D:response"
0x180015801  lea     rcx, [rbx+18h]
0x180015805  mov     byte ptr [rax], 0
0x180015808  mov     dword ptr [rbx+48h], 0
0x18001580f  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180015815  test    eax, eax
0x180015817  js      short loc_180015895
0x180015819  test    rsi, rsi
0x18001581c  jz      short loc_18001582D
0x18001581e  mov     rdx, rsi; struct DAV_NAMESPACE_SET *
0x180015821  mov     rcx, rbx; this
0x180015824  call    ?AppendNamespacePrefixes@XML_RENDERER@@AEAAJPEAVDAV_NAMESPACE_SET@@@Z; XML_RENDERER::AppendNamespacePrefixes(DAV_NAMESPACE_SET *)
0x180015829  test    eax, eax
0x18001582b  js      short loc_180015895
0x18001582d  mov     rdx, [rbx+10h]
0x180015831  lea     rcx, [rbx+18h]
0x180015835  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18001583b  test    eax, eax
0x18001583d  js      short loc_180015895
0x18001583f  mov     r8, rbp; unsigned __int16 *
0x180015842  mov     rdx, r14; unsigned __int16 *
0x180015845  mov     rcx, rbx; this
0x180015848  call    ?AppendHRef@XML_RENDERER@@AEAAJPEBG0@Z; XML_RENDERER::AppendHRef(ushort const *,ushort const *)
0x18001584d  test    eax, eax
0x18001584f  js      short loc_180015895
0x180015851  mov     r9d, [rsp+68h+arg_20]; int
0x180015859  mov     edi, 1
0x18001585e  mov     r8d, edi; int
0x180015861  mov     [rsp+68h+var_48], 194h; unsigned __int16
0x180015868  mov     rdx, rsi; struct DAV_NAMESPACE_SET *
0x18001586b  mov     rcx, rbx; this
0x18001586e  call    ?AppendNamespaceSet@XML_RENDERER@@AEAAJPEAVDAV_NAMESPACE_SET@@HHG@Z; XML_RENDERER::AppendNamespaceSet(DAV_NAMESPACE_SET *,int,int,ushort)
0x180015873  test    eax, eax
0x180015875  js      short loc_180015895
0x180015877  mov     r8d, edi; int
0x18001587a  lea     rdx, aResponse; "response"
0x180015881  mov     rcx, rbx; this
0x180015884  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180015889  test    eax, eax
0x18001588b  js      short loc_180015895
0x18001588d  mov     rcx, rbx; this
0x180015890  call    ?Flush@XML_RESPONDER@@AEAAJXZ; XML_RESPONDER::Flush(void)
0x180015895  add     rsp, 40h
0x180015899  pop     r14
0x18001589b  pop     rdi
0x18001589c  pop     rsi
0x18001589d  pop     rbp
0x18001589e  pop     rbx
0x18001589f  retn
```
