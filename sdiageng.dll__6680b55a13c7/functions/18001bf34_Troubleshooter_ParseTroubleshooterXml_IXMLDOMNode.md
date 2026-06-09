# Troubleshooter::ParseTroubleshooterXml(IXMLDOMNode *)

- ea: `0x18001bf34`
- end: `0x18001c107`
- name: `?ParseTroubleshooterXml@Troubleshooter@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(Troubleshooter *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001bdac`

## callees

- `0x18001be18`
- `0x18001bf34`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x18001c07f`: `ExtensionPoint`
- `0x18001bf62`: `Troubleshooter::ParseTroubleshooterXml`
- `0x18001bfd8`: `Troubleshooter::ParseTroubleshooterXml`
- `0x18001c0c0`: `Troubleshooter::ParseTroubleshooterXml`

## pseudocode

```c
__int64 __fastcall Troubleshooter::ParseTroubleshooterXml(Troubleshooter *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  unsigned int v4; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r14
  int v7; // r9d
  int v8; // r8d
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v15; // [rsp+58h] [rbp+38h] BYREF
  struct IXMLDOMNode *v16; // [rsp+60h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v17; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Troubleshooter::ParseTroubleshooterXml", 146, -2147024809);
    return v4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v17, &v15);
  v6 = v17;
  v4 = ChildNodes;
  if ( ChildNodes < 0 )
  {
    v7 = ChildNodes;
    v8 = 149;
LABEL_26:
    SdpDebugTrace(1u, L"Troubleshooter::ParseTroubleshooterXml", v8, v7);
    goto LABEL_27;
  }
  if ( v15 < 2 )
  {
    v7 = -2147024809;
    v8 = 153;
LABEL_25:
    v4 = v7;
    goto LABEL_26;
  }
  v9 = SdpXmlNextNode(v17, &v16);
  v4 = v9;
  if ( v9 >= 0 )
  {
    v2 = v16;
    v11 = SdpXmlCheckNode(v16, L"Script");
    v4 = v11;
    if ( v11 < 0 )
    {
      v7 = v11;
      v8 = 162;
      goto LABEL_26;
    }
    if ( v11 == 1 || !v2 )
    {
      v8 = 162;
    }
    else
    {
      v12 = Troubleshooter::InitializeScript(this, v2);
      v4 = v12;
      if ( v12 < 0 )
      {
        v7 = v12;
        v8 = 165;
        goto LABEL_26;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
      v16 = 0;
      v9 = SdpXmlNextNode(v6, &v16);
      v4 = v9;
      if ( v9 < 0 )
      {
        v10 = 173;
        goto LABEL_9;
      }
      v2 = v16;
      v13 = SdpXmlCheckNode(v16, L"ExtensionPoint");
      v4 = v13;
      if ( v13 < 0 )
      {
        v7 = v13;
        v8 = 174;
        goto LABEL_26;
      }
      if ( v13 != 1 && v2 )
        goto LABEL_27;
      v8 = 174;
    }
    v7 = -2147467259;
    goto LABEL_25;
  }
  v10 = 161;
LABEL_9:
  SdpDebugTrace(1u, L"Troubleshooter::ParseTroubleshooterXml", v10, v9);
  v2 = v16;
LABEL_27:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  return v4;
}

```

## disassembly

```asm
0x18001bf34  push    rbp
0x18001bf36  push    rbx
0x18001bf37  push    rdi
0x18001bf38  push    r14
0x18001bf3a  push    r15
0x18001bf3c  mov     rbp, rsp
0x18001bf3f  sub     rsp, 20h
0x18001bf43  xor     edi, edi
0x18001bf45  mov     [rbp+arg_18], 0
0x18001bf4d  mov     [rbp+arg_10], rdi
0x18001bf51  mov     r15, rcx
0x18001bf54  mov     [rbp+arg_8], edi
0x18001bf57  test    rdx, rdx
0x18001bf5a  jnz     short loc_18001BF7F
0x18001bf5c  mov     r9d, 80070057h; int
0x18001bf62  lea     rdx, aTroubleshooter_1; "Troubleshooter::ParseTroubleshooterXml"
0x18001bf69  mov     r8d, 92h; int
0x18001bf6f  lea     ecx, [rdi+1]; Level
0x18001bf72  mov     ebx, r9d
0x18001bf75  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bf7a  jmp     loc_18001C0F9
0x18001bf7f  lea     r9, [rbp+arg_8]; unsigned int *
0x18001bf83  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001bf85  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18001bf89  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001bf8e  mov     r14, [rbp+arg_18]
0x18001bf92  mov     ebx, eax
0x18001bf94  test    eax, eax
0x18001bf96  jns     short loc_18001BFA6
0x18001bf98  mov     r9d, eax
0x18001bf9b  mov     r8d, 95h
0x18001bfa1  jmp     loc_18001C0C0
0x18001bfa6  cmp     [rbp+arg_8], 2
0x18001bfaa  jnb     short loc_18001BFBD
0x18001bfac  mov     r9d, 80070057h
0x18001bfb2  mov     r8d, 99h
0x18001bfb8  jmp     loc_18001C0BD
0x18001bfbd  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001bfc1  mov     rcx, r14; struct IXMLDOMNodeList *
0x18001bfc4  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001bfc9  mov     ebx, eax
0x18001bfcb  test    eax, eax
0x18001bfcd  jns     short loc_18001BFF2
0x18001bfcf  mov     r8d, 0A1h; int
0x18001bfd5  mov     r9d, eax; int
0x18001bfd8  lea     rdx, aTroubleshooter_1; "Troubleshooter::ParseTroubleshooterXml"
0x18001bfdf  mov     ecx, 1; Level
0x18001bfe4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bfe9  mov     rdi, [rbp+arg_10]
0x18001bfed  jmp     loc_18001C0D1
0x18001bff2  mov     rdi, [rbp+arg_10]
0x18001bff6  lea     rdx, aScript; "Script"
0x18001bffd  mov     rcx, rdi; struct IXMLDOMNode *
0x18001c000  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001c005  mov     ebx, eax
0x18001c007  test    eax, eax
0x18001c009  jns     short loc_18001C019
0x18001c00b  mov     r9d, eax
0x18001c00e  mov     r8d, 0A2h
0x18001c014  jmp     loc_18001C0C0
0x18001c019  cmp     eax, 1
0x18001c01c  jz      loc_18001C0B1
0x18001c022  test    rdi, rdi
0x18001c025  jz      loc_18001C0B1
0x18001c02b  mov     rdx, rdi; struct IXMLDOMNode *
0x18001c02e  mov     rcx, r15; this
0x18001c031  call    ?InitializeScript@Troubleshooter@@AEAAJPEAUIXMLDOMNode@@@Z; Troubleshooter::InitializeScript(IXMLDOMNode *)
0x18001c036  mov     ebx, eax
0x18001c038  test    eax, eax
0x18001c03a  jns     short loc_18001C047
0x18001c03c  mov     r9d, eax
0x18001c03f  mov     r8d, 0A5h
0x18001c045  jmp     short loc_18001C0C0
0x18001c047  mov     rax, [rdi]
0x18001c04a  mov     rcx, rdi
0x18001c04d  mov     rax, [rax+10h]
0x18001c051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c056  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001c05a  mov     [rbp+arg_10], 0
0x18001c062  mov     rcx, r14; struct IXMLDOMNodeList *
0x18001c065  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001c06a  mov     ebx, eax
0x18001c06c  test    eax, eax
0x18001c06e  jns     short loc_18001C07B
0x18001c070  mov     r8d, 0ADh
0x18001c076  jmp     loc_18001BFD5
0x18001c07b  mov     rdi, [rbp+arg_10]
0x18001c07f  lea     rdx, aExtensionpoint_0; "ExtensionPoint"
0x18001c086  mov     rcx, rdi; struct IXMLDOMNode *
0x18001c089  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001c08e  mov     ebx, eax
0x18001c090  test    eax, eax
0x18001c092  jns     short loc_18001C09F
0x18001c094  mov     r9d, eax
0x18001c097  mov     r8d, 0AEh
0x18001c09d  jmp     short loc_18001C0C0
0x18001c09f  cmp     eax, 1
0x18001c0a2  jz      short loc_18001C0A9
0x18001c0a4  test    rdi, rdi
0x18001c0a7  jnz     short loc_18001C0D1
0x18001c0a9  mov     r8d, 0AEh
0x18001c0af  jmp     short loc_18001C0B7
0x18001c0b1  mov     r8d, 0A2h; int
0x18001c0b7  mov     r9d, 80004005h; int
0x18001c0bd  mov     ebx, r9d
0x18001c0c0  lea     rdx, aTroubleshooter_1; "Troubleshooter::ParseTroubleshooterXml"
0x18001c0c7  mov     ecx, 1; Level
0x18001c0cc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c0d1  test    r14, r14
0x18001c0d4  jz      short loc_18001C0E5
0x18001c0d6  mov     rax, [r14]
0x18001c0d9  mov     rcx, r14
0x18001c0dc  mov     rax, [rax+10h]
0x18001c0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0e5  test    rdi, rdi
0x18001c0e8  jz      short loc_18001C0F9
0x18001c0ea  mov     rax, [rdi]
0x18001c0ed  mov     rcx, rdi
0x18001c0f0  mov     rax, [rax+10h]
0x18001c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0f9  mov     eax, ebx
0x18001c0fb  add     rsp, 20h
0x18001c0ff  pop     r15
0x18001c101  pop     r14
0x18001c103  pop     rdi
0x18001c104  pop     rbx
0x18001c105  pop     rbp
0x18001c106  retn
```
