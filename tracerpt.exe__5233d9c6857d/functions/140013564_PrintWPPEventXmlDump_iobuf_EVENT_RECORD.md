# PrintWPPEventXmlDump(_iobuf *,_EVENT_RECORD *)

- ea: `0x140013564`
- end: `0x1400137b2`
- name: `?PrintWPPEventXmlDump@@YAKPEAU_iobuf@@PEAU_EVENT_RECORD@@@Z`
- size: `590`
- prototype: `unsigned int __fastcall(struct _iobuf *, PEVENT_RECORD pEvent)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000faa4`

## callees

- `0x140013564`
- `0x1400137b8`
- `0x140016360`

## string_xrefs

- `0x14001365d`: `ComponentName`
- `0x14001369f`: `SubComponentName`
- `0x140013651`: `		<Component>`
- `0x14001367a`: `</Component>\n`
- `0x140013693`: `		<SubComponent>`
- `0x1400136bc`: `</SubComponent>\n`

## pseudocode

```c
__int64 __fastcall PrintWPPEventXmlDump(struct _iobuf *a1, PEVENT_RECORD pEvent)
{
  unsigned int v4; // esi
  unsigned int v6; // edi

  TracerptFPutws((wchar_t *)L"\t<DebugData>\r\n", a1);
  TracerptFPutws((wchar_t *)L"\t\t<SequenceNumber>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 8);
  TracerptFPutws((wchar_t *)L"</SequenceNumber>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<FlagsName>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</FlagsName>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<LevelName>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</LevelName>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<Component>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</Component>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<SubComponent>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</SubComponent>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<FileLine>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</FileLine>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<Function>", a1);
  v4 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</Function>\r\n", a1);
  if ( v4 )
    return v4;
  TracerptFPutws((wchar_t *)L"\t\t<Message>", a1);
  v6 = PrintWPPProperty(a1, pEvent, 1u, 1);
  TracerptFPutws((wchar_t *)L"</Message>\r\n", a1);
  if ( v6 )
    return v6;
  TracerptFPutws((wchar_t *)L"\t</DebugData>\r\n", a1);
  return 0;
}

```

## disassembly

```asm
0x140013564  push    rbx
0x140013566  push    rbp
0x140013567  push    rsi
0x140013568  push    rdi
0x140013569  sub     rsp, 38h
0x14001356d  mov     rdi, rdx
0x140013570  mov     rbx, rcx
0x140013573  mov     rdx, rcx; struct _iobuf *
0x140013576  lea     rcx, aDebugdata_0; "\t<DebugData>\r\n"
0x14001357d  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013582  mov     rdx, rbx; struct _iobuf *
0x140013585  lea     rcx, aSequencenumber; "\t\t<SequenceNumber>"
0x14001358c  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013591  mov     ebp, 1
0x140013596  mov     [rsp+58h+var_38], 8; __int16
0x14001359d  mov     r8b, bpl; unsigned __int8
0x1400135a0  lea     r9, aSequencenum; "SequenceNum"
0x1400135a7  mov     rdx, rdi; pEvent
0x1400135aa  mov     rcx, rbx; struct _iobuf *
0x1400135ad  call    PrintWPPProperty
0x1400135b2  mov     rdx, rbx; struct _iobuf *
0x1400135b5  lea     rcx, aSequencenumber_0; "</SequenceNumber>\r\n"
0x1400135bc  mov     esi, eax
0x1400135be  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400135c3  test    esi, esi
0x1400135c5  jz      short loc_1400135CE
0x1400135c7  mov     eax, esi
0x1400135c9  jmp     loc_1400137A9
0x1400135ce  mov     rdx, rbx; struct _iobuf *
0x1400135d1  lea     rcx, aFlagsname_1; "\t\t<FlagsName>"
0x1400135d8  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400135dd  lea     r9, aFlagsname; "FlagsName"
0x1400135e4  mov     [rsp+58h+var_38], bp; __int16
0x1400135e9  mov     r8b, bpl; unsigned __int8
0x1400135ec  mov     rdx, rdi; pEvent
0x1400135ef  mov     rcx, rbx; struct _iobuf *
0x1400135f2  call    PrintWPPProperty
0x1400135f7  mov     rdx, rbx; struct _iobuf *
0x1400135fa  lea     rcx, aFlagsname_0; "</FlagsName>\r\n"
0x140013601  mov     esi, eax
0x140013603  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013608  test    esi, esi
0x14001360a  jnz     short loc_1400135C7
0x14001360c  mov     rdx, rbx; struct _iobuf *
0x14001360f  lea     rcx, aLevelname_0; "\t\t<LevelName>"
0x140013616  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001361b  lea     r9, aLevelname; "LevelName"
0x140013622  mov     [rsp+58h+var_38], bp; __int16
0x140013627  mov     r8b, bpl; unsigned __int8
0x14001362a  mov     rdx, rdi; pEvent
0x14001362d  mov     rcx, rbx; struct _iobuf *
0x140013630  call    PrintWPPProperty
0x140013635  mov     rdx, rbx; struct _iobuf *
0x140013638  lea     rcx, aLevelname_1; "</LevelName>\r\n"
0x14001363f  mov     esi, eax
0x140013641  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013646  test    esi, esi
0x140013648  jnz     loc_1400135C7
0x14001364e  mov     rdx, rbx; struct _iobuf *
0x140013651  lea     rcx, aComponent; "\t\t<Component>"
0x140013658  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001365d  lea     r9, aComponentname; "ComponentName"
0x140013664  mov     [rsp+58h+var_38], bp; __int16
0x140013669  mov     r8b, bpl; unsigned __int8
0x14001366c  mov     rdx, rdi; pEvent
0x14001366f  mov     rcx, rbx; struct _iobuf *
0x140013672  call    PrintWPPProperty
0x140013677  mov     rdx, rbx; struct _iobuf *
0x14001367a  lea     rcx, aComponent_0; "</Component>\r\n"
0x140013681  mov     esi, eax
0x140013683  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013688  test    esi, esi
0x14001368a  jnz     loc_1400135C7
0x140013690  mov     rdx, rbx; struct _iobuf *
0x140013693  lea     rcx, aSubcomponent_0; "\t\t<SubComponent>"
0x14001369a  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001369f  lea     r9, aSubcomponentna; "SubComponentName"
0x1400136a6  mov     [rsp+58h+var_38], bp; __int16
0x1400136ab  mov     r8b, bpl; unsigned __int8
0x1400136ae  mov     rdx, rdi; pEvent
0x1400136b1  mov     rcx, rbx; struct _iobuf *
0x1400136b4  call    PrintWPPProperty
0x1400136b9  mov     rdx, rbx; struct _iobuf *
0x1400136bc  lea     rcx, aSubcomponent; "</SubComponent>\r\n"
0x1400136c3  mov     esi, eax
0x1400136c5  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400136ca  test    esi, esi
0x1400136cc  jnz     loc_1400135C7
0x1400136d2  mov     rdx, rbx; struct _iobuf *
0x1400136d5  lea     rcx, aFileline; "\t\t<FileLine>"
0x1400136dc  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400136e1  lea     r9, aGuidtypename; "GuidTypeName"
0x1400136e8  mov     [rsp+58h+var_38], bp; __int16
0x1400136ed  mov     r8b, bpl; unsigned __int8
0x1400136f0  mov     rdx, rdi; pEvent
0x1400136f3  mov     rcx, rbx; struct _iobuf *
0x1400136f6  call    PrintWPPProperty
0x1400136fb  mov     rdx, rbx; struct _iobuf *
0x1400136fe  lea     rcx, aFileline_0; "</FileLine>\r\n"
0x140013705  mov     esi, eax
0x140013707  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001370c  test    esi, esi
0x14001370e  jnz     loc_1400135C7
0x140013714  mov     rdx, rbx; struct _iobuf *
0x140013717  lea     rcx, aFunction; "\t\t<Function>"
0x14001371e  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013723  lea     r9, aFunctionname; "FunctionName"
0x14001372a  mov     [rsp+58h+var_38], bp; __int16
0x14001372f  mov     r8b, bpl; unsigned __int8
0x140013732  mov     rdx, rdi; pEvent
0x140013735  mov     rcx, rbx; struct _iobuf *
0x140013738  call    PrintWPPProperty
0x14001373d  mov     rdx, rbx; struct _iobuf *
0x140013740  lea     rcx, aFunction_0; "</Function>\r\n"
0x140013747  mov     esi, eax
0x140013749  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001374e  test    esi, esi
0x140013750  jnz     loc_1400135C7
0x140013756  mov     rdx, rbx; struct _iobuf *
0x140013759  lea     rcx, aMessage_1; "\t\t<Message>"
0x140013760  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013765  lea     r9, aFormattedstrin; "FormattedString"
0x14001376c  mov     [rsp+58h+var_38], bp; __int16
0x140013771  mov     r8b, bpl; unsigned __int8
0x140013774  mov     rdx, rdi; pEvent
0x140013777  mov     rcx, rbx; struct _iobuf *
0x14001377a  call    PrintWPPProperty
0x14001377f  mov     rdx, rbx; struct _iobuf *
0x140013782  lea     rcx, aMessage_2; "</Message>\r\n"
0x140013789  mov     edi, eax
0x14001378b  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140013790  test    edi, edi
0x140013792  jz      short loc_140013798
0x140013794  mov     eax, edi
0x140013796  jmp     short loc_1400137A9
0x140013798  mov     rdx, rbx; struct _iobuf *
0x14001379b  lea     rcx, aDebugdata; "\t</DebugData>\r\n"
0x1400137a2  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x1400137a7  xor     eax, eax
0x1400137a9  add     rsp, 38h
0x1400137ad  pop     rdi
0x1400137ae  pop     rsi
0x1400137af  pop     rbp
0x1400137b0  pop     rbx
0x1400137b1  retn
```
