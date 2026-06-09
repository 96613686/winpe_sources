# XML_RESPONDER::SendXmlErrorResponse(ushort const *,ushort const *,ushort,ushort,char const *)

- ea: `0x1800152f8`
- end: `0x1800153a3`
- name: `?SendXmlErrorResponse@XML_RESPONDER@@QEAAJPEBG0GGPEBD@Z`
- size: `171`
- prototype: `__int64 __usercall@<rax>(XML_RESPONDER *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, char *@<r8>, unsigned __int16@<r9w>, unsigned __int16, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e6e0`
- `0x180010ea0`

## callees

- `0x180014fa0`
- `0x18001526c`
- `0x1800152f8`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001535b`
- `iisutil!PuDbgPrint` at `0x18001535b`

## string_xrefs

- `0x180015338`: `XML_RESPONDER::SendXmlErrorResponse`
- `0x18001534f`: `inetsrv\iis\iisrearc\iis70\webdav\module\src\xml_response.cxx`

## pseudocode

```c
__int64 __fastcall XML_RESPONDER::SendXmlErrorResponse(
        XML_RESPONDER *this,
        const unsigned __int16 *a2,
        char *a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        char *a6)
{
  __int64 result; // rax
  unsigned __int16 v11; // [rsp+20h] [rbp-48h]
  char *v12; // [rsp+30h] [rbp-38h]

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    v12 = a3;
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\xml_response.cxx",
      168,
      "XML_RESPONDER::SendXmlErrorResponse",
      "HRef = %ws%ws, Status = %u\n");
  }
  **((_BYTE **)this + 7) = 0;
  *((_DWORD *)this + 18) = 0;
  result = XML_RENDERER::RenderXmlErrorResponse(this, a2, (const unsigned __int16 *)a3, a4, v11, a6, v12);
  if ( (int)result >= 0 )
    return XML_RESPONDER::Flush(this);
  return result;
}

```

## disassembly

```asm
0x1800152f8  push    rbx
0x1800152fa  push    rbp
0x1800152fb  push    rsi
0x1800152fc  push    rdi
0x1800152fd  sub     rsp, 48h
0x180015301  mov     eax, cs:g_dwDebugFlags
0x180015307  mov     rsi, r8
0x18001530a  test    al, 3
0x18001530c  movzx   edi, r9w
0x180015310  mov     rbp, rdx
0x180015313  mov     rbx, rcx
0x180015316  setnz   r10b
0x18001531a  bt      eax, 1Ah
0x18001531e  setb    al
0x180015321  test    al, r10b
0x180015324  jz      short loc_180015361
0x180015326  mov     rcx, cs:g_pDebug
0x18001532d  lea     rax, aHrefWsWsStatus; "HRef = %ws%ws, Status = %u\n"
0x180015334  mov     [rsp+68h+var_30], edi
0x180015338  lea     r9, aXmlResponderSe; "XML_RESPONDER::SendXmlErrorResponse"
0x18001533f  mov     [rsp+68h+var_38], r8; char *
0x180015344  mov     r8d, 0A8h
0x18001534a  mov     [rsp+68h+var_40], rdx
0x18001534f  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x180015356  mov     qword ptr [rsp+68h+var_48], rax; unsigned __int16
0x18001535b  call    cs:__imp_PuDbgPrint
0x180015361  mov     rax, [rbx+38h]
0x180015365  movzx   r9d, di; unsigned __int16
0x180015369  mov     r8, rsi; unsigned __int16 *
0x18001536c  mov     rdx, rbp; unsigned __int16 *
0x18001536f  mov     rcx, rbx; this
0x180015372  mov     byte ptr [rax], 0
0x180015375  mov     rax, [rsp+68h+arg_28]
0x18001537d  mov     [rsp+68h+var_40], rax; char *
0x180015382  mov     dword ptr [rbx+48h], 0
0x180015389  call    ?RenderXmlErrorResponse@XML_RENDERER@@QEAAJPEBG0GGPEBD1@Z; XML_RENDERER::RenderXmlErrorResponse(ushort const *,ushort const *,ushort,ushort,char const *,char const *)
0x18001538e  test    eax, eax
0x180015390  js      short loc_18001539A
0x180015392  mov     rcx, rbx; this
0x180015395  call    ?Flush@XML_RESPONDER@@AEAAJXZ; XML_RESPONDER::Flush(void)
0x18001539a  add     rsp, 48h
0x18001539e  pop     rdi
0x18001539f  pop     rsi
0x1800153a0  pop     rbp
0x1800153a1  pop     rbx
0x1800153a2  retn
```
