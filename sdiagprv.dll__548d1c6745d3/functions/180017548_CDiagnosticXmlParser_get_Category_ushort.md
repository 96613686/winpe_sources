# CDiagnosticXmlParser::get_Category(ushort * *)

- ea: `0x180017548`
- end: `0x180017620`
- name: `?get_Category@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
- size: `216`
- prototype: `__int64 __fastcall(CDiagnosticXmlParser *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001374c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18001737c`
- `0x180017548`

## string_xrefs

- `0x180017572`: `CDiagnosticXmlParser::get_Category`
- `0x1800175dd`: `CDiagnosticXmlParser::get_Category`
- `0x180017605`: `CDiagnosticXmlParser::get_Category`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_Category(CDiagnosticXmlParser *this, unsigned __int16 **a2)
{
  unsigned int XmlStringElement; // ebx
  __int64 v3; // rdx
  __int64 v4; // r9

  if ( !a2 )
  {
    XmlStringElement = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CDiagnosticXmlParser::get_Category",
        -2147024809,
        (__int64)"Category");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:Category", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Index/cfg:Category", a2);
  if ( (XmlStringElement & 0x80000000) != 0 )
  {
LABEL_9:
    if ( XmlStringElement == -2147024809 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return XmlStringElement;
      v4 = 2147942487LL;
      goto LABEL_13;
    }
  }
  if ( XmlStringElement )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return XmlStringElement;
    v4 = XmlStringElement;
LABEL_13:
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_Category", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Category");
  return XmlStringElement;
}

```

## disassembly

```asm
0x180017548  push    rbx
0x18001754a  sub     rsp, 30h
0x18001754e  test    rdx, rdx
0x180017551  jnz     short loc_180017588
0x180017553  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001755a  mov     ebx, 80070057h
0x18001755f  jz      loc_180017618
0x180017565  lea     rax, aCategory; "Category"
0x18001756c  mov     r9d, 80070057h
0x180017572  lea     r8, aCdiagnosticxml_10; "CDiagnosticXmlParser::get_Category"
0x180017579  mov     [rsp+38h+var_18], rax
0x18001757e  call    McTemplateU0sqs_EventWriteTransfer
0x180017583  jmp     loc_180017618
0x180017588  mov     qword ptr [rdx], 0
0x18001758f  cmp     dword ptr [rcx+10h], 0
0x180017593  jnz     short loc_1800175AC
0x180017595  mov     r8, rdx; unsigned __int16 **
0x180017598  lea     rdx, aCfgIndexCfgCat; "cfg:Index/cfg:Category"
0x18001759f  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x1800175a4  mov     ebx, eax
0x1800175a6  test    eax, eax
0x1800175a8  js      short loc_1800175C5
0x1800175aa  jmp     short loc_1800175CD
0x1800175ac  xor     ebx, ebx
0x1800175ae  cmp     dword ptr [rcx+10h], 1
0x1800175b2  jnz     short loc_1800175FC
0x1800175b4  mov     r8, rdx; unsigned __int16 **
0x1800175b7  lea     rdx, aDcpCategory; "dcp:Category"
0x1800175be  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x1800175c3  mov     ebx, eax
0x1800175c5  cmp     ebx, 80070057h
0x1800175cb  jz      short loc_1800175EB
0x1800175cd  test    ebx, ebx
0x1800175cf  jz      short loc_1800175FC
0x1800175d1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800175d8  jz      short loc_180017618
0x1800175da  mov     r9d, ebx
0x1800175dd  lea     r8, aCdiagnosticxml_10; "CDiagnosticXmlParser::get_Category"
0x1800175e4  call    McTemplateU0sq_EventWriteTransfer
0x1800175e9  jmp     short loc_180017618
0x1800175eb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800175f2  jz      short loc_180017618
0x1800175f4  mov     r9d, 80070057h
0x1800175fa  jmp     short loc_1800175DD
0x1800175fc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017603  jz      short loc_180017618
0x180017605  lea     r8, aCdiagnosticxml_10; "CDiagnosticXmlParser::get_Category"
0x18001760c  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017613  call    McTemplateU0s_EventWriteTransfer
0x180017618  mov     eax, ebx
0x18001761a  add     rsp, 30h
0x18001761e  pop     rbx
0x18001761f  retn
```
