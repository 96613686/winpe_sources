# XML_RESPONDER::SendXmlProppatchResponse(ushort const *,ushort const *,DAV_NAMESPACE_SET *,int)

- ea: `0x1800158a8`
- end: `0x180015a02`
- name: `?SendXmlProppatchResponse@XML_RESPONDER@@QEAAJPEBG0PEAVDAV_NAMESPACE_SET@@H@Z`
- size: `346`
- prototype: `__int64 __fastcall(XML_RESPONDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct DAV_NAMESPACE_SET *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18000f200`

## callees

- `0x180013fd4`
- `0x180014404`
- `0x1800145a8`
- `0x180014ef4`
- `0x18001526c`
- `0x1800158a8`
- `0x180022520`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x1800159cf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800159cf`
- `iisutil!PuDbgPrint` at `0x18001591a`
- `iisutil!PuDbgPrint` at `0x18001591a`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180015944`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18001596e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180015944`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18001596e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180015933`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180015933`

## string_xrefs

- `0x18001590e`: `inetsrv\iis\iisrearc\iis70\webdav\module\src\xml_response.cxx`
- `0x1800158fc`: `XML_RESPONDER::SendXmlProppatchResponse`

## pseudocode

```c
__int64 __fastcall XML_RESPONDER::SendXmlProppatchResponse(
        XML_RESPONDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct DAV_NAMESPACE_SET *a4,
        int a5)
{
  int appended; // ebx
  _BYTE v11[56]; // [rsp+40h] [rbp-78h] BYREF

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\xml_response.cxx",
      237,
      "XML_RESPONDER::SendXmlProppatchResponse",
      "HRef = %ws%ws\n",
      a2,
      a3);
  **((_BYTE **)this + 7) = 0;
  *((_DWORD *)this + 18) = 0;
  STRA::STRA((STRA *)v11);
  appended = STRA::Append((XML_RESPONDER *)((char *)this + 24), "<D:response");
  if ( appended >= 0 )
  {
    if ( !a4 || (appended = XML_RENDERER::AppendNamespacePrefixes(this, a4), appended >= 0) )
    {
      appended = STRA::Append((XML_RESPONDER *)((char *)this + 24), *((const char **)this + 2));
      if ( appended >= 0 )
        appended = XML_RENDERER::AppendHRef((const char **)this, a2, a3);
    }
  }
  if ( appended >= 0 )
  {
    appended = XML_RENDERER::AppendNamespaceSet(this, a4, a5, 1, 0x1A8u);
    if ( appended >= 0 )
      appended = XML_RENDERER::OpenOrCloseXmlTag(this, "response", 1);
  }
  STRA::~STRA((STRA *)v11);
  if ( appended >= 0 )
    return (unsigned int)XML_RESPONDER::Flush(this);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800158a8  push    rbx
0x1800158aa  push    rbp
0x1800158ab  push    rsi
0x1800158ac  push    rdi
0x1800158ad  push    r14
0x1800158af  push    r15
0x1800158b1  sub     rsp, 88h
0x1800158b8  mov     rax, cs:__security_cookie
0x1800158bf  xor     rax, rsp
0x1800158c2  mov     [rsp+0B8h+var_40], rax
0x1800158c7  mov     eax, cs:g_dwDebugFlags
0x1800158cd  mov     rdi, rcx
0x1800158d0  test    al, 3
0x1800158d2  mov     rbp, r9
0x1800158d5  mov     r15, r8
0x1800158d8  mov     r14, rdx
0x1800158db  setnz   cl
0x1800158de  bt      eax, 1Ah
0x1800158e2  setb    al
0x1800158e5  test    al, cl
0x1800158e7  jz      short loc_180015920
0x1800158e9  mov     rcx, cs:g_pDebug
0x1800158f0  lea     rax, aHrefWsWs; "HRef = %ws%ws\n"
0x1800158f7  mov     [rsp+0B8h+var_88], r8
0x1800158fc  lea     r9, aXmlResponderSe_1; "XML_RESPONDER::SendXmlProppatchResponse"
0x180015903  mov     [rsp+0B8h+var_90], rdx
0x180015908  mov     r8d, 0EDh
0x18001590e  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x180015915  mov     qword ptr [rsp+0B8h+var_98], rax
0x18001591a  call    cs:__imp_PuDbgPrint
0x180015920  mov     rax, [rdi+38h]
0x180015924  lea     rcx, [rsp+0B8h+var_78]
0x180015929  mov     byte ptr [rax], 0
0x18001592c  mov     dword ptr [rdi+48h], 0
0x180015933  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180015939  lea     rdx, aDResponse; "<D:response"
0x180015940  lea     rcx, [rdi+18h]
0x180015944  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18001594a  mov     ebx, eax
0x18001594c  test    eax, eax
0x18001594e  js      short loc_18001598A
0x180015950  test    rbp, rbp
0x180015953  jz      short loc_180015966
0x180015955  mov     rdx, rbp; struct DAV_NAMESPACE_SET *
0x180015958  mov     rcx, rdi; this
0x18001595b  call    ?AppendNamespacePrefixes@XML_RENDERER@@AEAAJPEAVDAV_NAMESPACE_SET@@@Z; XML_RENDERER::AppendNamespacePrefixes(DAV_NAMESPACE_SET *)
0x180015960  mov     ebx, eax
0x180015962  test    eax, eax
0x180015964  js      short loc_18001598A
0x180015966  mov     rdx, [rdi+10h]
0x18001596a  lea     rcx, [rdi+18h]
0x18001596e  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180015974  mov     ebx, eax
0x180015976  test    eax, eax
0x180015978  js      short loc_18001598A
0x18001597a  mov     r8, r15; unsigned __int16 *
0x18001597d  mov     rdx, r14; unsigned __int16 *
0x180015980  mov     rcx, rdi; this
0x180015983  call    ?AppendHRef@XML_RENDERER@@AEAAJPEBG0@Z; XML_RENDERER::AppendHRef(ushort const *,ushort const *)
0x180015988  mov     ebx, eax
0x18001598a  test    ebx, ebx
0x18001598c  js      short loc_1800159CA
0x18001598e  mov     r8d, [rsp+0B8h+arg_20]; int
0x180015996  mov     esi, 1
0x18001599b  mov     r9d, esi; int
0x18001599e  mov     [rsp+0B8h+var_98], 1A8h; unsigned __int16
0x1800159a5  mov     rdx, rbp; struct DAV_NAMESPACE_SET *
0x1800159a8  mov     rcx, rdi; this
0x1800159ab  call    ?AppendNamespaceSet@XML_RENDERER@@AEAAJPEAVDAV_NAMESPACE_SET@@HHG@Z; XML_RENDERER::AppendNamespaceSet(DAV_NAMESPACE_SET *,int,int,ushort)
0x1800159b0  mov     ebx, eax
0x1800159b2  test    eax, eax
0x1800159b4  js      short loc_1800159CA
0x1800159b6  mov     r8d, esi; int
0x1800159b9  lea     rdx, aResponse; "response"
0x1800159c0  mov     rcx, rdi; this
0x1800159c3  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x1800159c8  mov     ebx, eax
0x1800159ca  lea     rcx, [rsp+0B8h+var_78]
0x1800159cf  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800159d5  test    ebx, ebx
0x1800159d7  js      short loc_1800159E3
0x1800159d9  mov     rcx, rdi; this
0x1800159dc  call    ?Flush@XML_RESPONDER@@AEAAJXZ; XML_RESPONDER::Flush(void)
0x1800159e1  mov     ebx, eax
0x1800159e3  mov     eax, ebx
0x1800159e5  mov     rcx, [rsp+0B8h+var_40]
0x1800159ea  xor     rcx, rsp; StackCookie
0x1800159ed  call    __security_check_cookie
0x1800159f2  add     rsp, 88h
0x1800159f9  pop     r15
0x1800159fb  pop     r14
0x1800159fd  pop     rdi
0x1800159fe  pop     rsi
0x1800159ff  pop     rbp
0x180015a00  pop     rbx
0x180015a01  retn
```
