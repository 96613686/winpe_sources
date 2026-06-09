# Script::BuildResultXml(IXMLDOMDocument2 *)

- ea: `0x18001dac4`
- end: `0x18001db7d`
- name: `?BuildResultXml@Script@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(Script *this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001c224`

## callees

- `0x18001dac4`
- `0x180026fa0`
- `0x18002827c`

## string_xrefs

- `0x18001db5f`: `Script::BuildResultXml`

## pseudocode

```c
__int64 __fastcall Script::BuildResultXml(Script *this, struct IXMLDOMDocument2 *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  const unsigned __int16 *v7; // rbp
  const unsigned __int16 *v8; // r9
  int Node; // eax

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 894;
    v6 = -2147024809;
LABEL_12:
    SdpDebugTrace(1u, L"Script::BuildResultXml", v5, v6);
    return v4;
  }
  v7 = L"true";
  v8 = L"true";
  if ( !*((_DWORD *)this + 4) )
    v8 = L"false";
  Node = SdpXmlCreateNode(a2, 0, L"RequiresElevation", v8, 0);
  v4 = Node;
  if ( Node < 0 )
  {
    v5 = 906;
LABEL_11:
    v6 = Node;
    goto LABEL_12;
  }
  if ( !*((_DWORD *)this + 10) )
    v7 = L"false";
  Node = SdpXmlCreateNode(a2, 0, L"RequiresInteractivity", v7, 0);
  v4 = Node;
  if ( Node < 0 )
  {
    v5 = 918;
    goto LABEL_11;
  }
  return v4;
}

```

## disassembly

```asm
0x18001dac4  push    rbx
0x18001dac6  push    rbp
0x18001dac7  push    rsi
0x18001dac8  push    rdi
0x18001dac9  push    r15
0x18001dacb  sub     rsp, 30h
0x18001dacf  mov     rdi, rdx
0x18001dad2  mov     rsi, rcx
0x18001dad5  test    rdx, rdx
0x18001dad8  jnz     short loc_18001DAEA
0x18001dada  mov     ebx, 80070057h
0x18001dadf  mov     r8d, 37Eh
0x18001dae5  mov     r9d, ebx
0x18001dae8  jmp     short loc_18001DB5F
0x18001daea  cmp     dword ptr [rcx+10h], 0
0x18001daee  lea     rbp, aTrue; "true"
0x18001daf5  mov     r9, rbp
0x18001daf8  mov     [rsp+58h+var_38], 0; struct IXMLDOMElement **
0x18001db01  lea     r15, aFalse; "false"
0x18001db08  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001db0b  cmovz   r9, r15; unsigned __int16 *
0x18001db0f  lea     r8, aRequireselevat; "RequiresElevation"
0x18001db16  xor     edx, edx; struct IXMLDOMElement *
0x18001db18  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001db1d  mov     ebx, eax
0x18001db1f  test    eax, eax
0x18001db21  jns     short loc_18001DB2B
0x18001db23  mov     r8d, 38Ah
0x18001db29  jmp     short loc_18001DB5C
0x18001db2b  cmp     dword ptr [rsi+28h], 0
0x18001db2f  lea     r8, aRequiresintera; "RequiresInteractivity"
0x18001db36  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001db39  mov     [rsp+58h+var_38], 0; struct IXMLDOMElement **
0x18001db42  cmovz   rbp, r15
0x18001db46  xor     edx, edx; struct IXMLDOMElement *
0x18001db48  mov     r9, rbp; unsigned __int16 *
0x18001db4b  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001db50  mov     ebx, eax
0x18001db52  test    eax, eax
0x18001db54  jns     short loc_18001DB70
0x18001db56  mov     r8d, 396h; int
0x18001db5c  mov     r9d, eax; int
0x18001db5f  lea     rdx, aScriptBuildres; "Script::BuildResultXml"
0x18001db66  mov     ecx, 1; Level
0x18001db6b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001db70  mov     eax, ebx
0x18001db72  add     rsp, 30h
0x18001db76  pop     r15
0x18001db78  pop     rdi
0x18001db79  pop     rsi
0x18001db7a  pop     rbp
0x18001db7b  pop     rbx
0x18001db7c  retn
```
