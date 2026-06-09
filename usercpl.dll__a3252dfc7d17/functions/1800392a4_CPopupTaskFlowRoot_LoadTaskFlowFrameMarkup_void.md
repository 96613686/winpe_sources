# CPopupTaskFlowRoot::_LoadTaskFlowFrameMarkup(void)

- ea: `0x1800392a4`
- end: `0x180039397`
- name: `?_LoadTaskFlowFrameMarkup@CPopupTaskFlowRoot@@AEAAJXZ`
- size: `243`
- prototype: `int __fastcall(struct DirectUI::DUIXmlParser **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180038b64`

## callees

- `0x1800392a4`

## import_xrefs

- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800392f0`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800392f0`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800392cc`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800392cc`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18003932a`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18003932a`
- `DUI70!StrToID` at `0x18003933b`
- `DUI70!StrToID` at `0x18003935b`
- `DUI70!StrToID` at `0x18003933b`
- `DUI70!StrToID` at `0x18003935b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180039347`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180039367`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180039347`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180039367`

## string_xrefs

- `0x18003930b`: `taskflowmain`

## pseudocode

```c
int __fastcall CPopupTaskFlowRoot::_LoadTaskFlowFrameMarkup(struct DirectUI::DUIXmlParser **this)
{
  DirectUI::DUIXmlParser **v1; // rdi
  int result; // eax
  DirectUI::DUIXmlParser *v4; // rcx
  unsigned __int16 v5; // ax
  unsigned __int16 v6; // ax
  struct DirectUI::Element *Descendent; // rax
  bool v8; // zf
  struct DirectUI::Element *v9; // [rsp+40h] [rbp+8h] BYREF

  v1 = this + 26;
  result = DirectUI::DUIXmlParser::Create(this + 26, 0, 0, 0, 0);
  if ( result >= 0 )
  {
    result = DirectUI::DUIXmlParser::SetXMLFromResource(*v1, 0xBB8u, g_hinst, &_ImageBase);
    if ( result >= 0 )
    {
      v4 = *v1;
      v9 = 0;
      result = DirectUI::DUIXmlParser::CreateElement(v4, L"taskflowmain", (struct DirectUI::Element *)this, 0, 0, &v9);
      if ( result >= 0 )
      {
        v5 = StrToID(L"contentscrollviewer");
        this[28] = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v5);
        v6 = StrToID(L"panes");
        Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v6);
        v8 = this[28] == 0;
        this[27] = Descendent;
        if ( v8 || !Descendent )
          return -2147418113;
        else
          return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800392a4  mov     [rsp+arg_8], rbx
0x1800392a9  push    rdi
0x1800392aa  sub     rsp, 30h
0x1800392ae  lea     rdi, [rcx+0D0h]
0x1800392b5  mov     [rsp+38h+var_18], 0
0x1800392be  mov     rbx, rcx
0x1800392c1  xor     r9d, r9d
0x1800392c4  mov     rcx, rdi
0x1800392c7  xor     r8d, r8d
0x1800392ca  xor     edx, edx
0x1800392cc  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800392d2  test    eax, eax
0x1800392d4  js      loc_18003938C
0x1800392da  mov     r8, cs:g_hinst
0x1800392e1  lea     r9, __ImageBase
0x1800392e8  mov     rcx, [rdi]
0x1800392eb  mov     edx, 0BB8h
0x1800392f0  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800392f6  test    eax, eax
0x1800392f8  js      loc_18003938C
0x1800392fe  mov     rcx, [rdi]
0x180039301  lea     rax, [rsp+38h+arg_0]
0x180039306  mov     [rsp+38h+var_10], rax
0x18003930b  lea     rdx, aTaskflowmain; "taskflowmain"
0x180039312  xor     r9d, r9d
0x180039315  mov     [rsp+38h+var_18], 0
0x18003931e  mov     r8, rbx
0x180039321  mov     [rsp+38h+arg_0], 0
0x18003932a  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180039330  test    eax, eax
0x180039332  js      short loc_18003938C
0x180039334  lea     rcx, aContentscrollv; "contentscrollviewer"
0x18003933b  call    cs:__imp_StrToID
0x180039341  movzx   edx, ax
0x180039344  mov     rcx, rbx
0x180039347  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003934d  lea     rcx, aPanes; "panes"
0x180039354  mov     [rbx+0E0h], rax
0x18003935b  call    cs:__imp_StrToID
0x180039361  movzx   edx, ax
0x180039364  mov     rcx, rbx
0x180039367  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003936d  cmp     qword ptr [rbx+0E0h], 0
0x180039375  mov     [rbx+0D8h], rax
0x18003937c  jz      short loc_180039387
0x18003937e  test    rax, rax
0x180039381  jz      short loc_180039387
0x180039383  xor     eax, eax
0x180039385  jmp     short loc_18003938C
0x180039387  mov     eax, 8000FFFFh
0x18003938c  mov     rbx, [rsp+38h+arg_8]
0x180039391  add     rsp, 30h
0x180039395  pop     rdi
0x180039396  retn
```
