# CDiagnosticXmlParser::get_DiagnosticIcon(ushort * *)

- ea: `0x180017708`
- end: `0x1800177e0`
- name: `?get_DiagnosticIcon@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x180017708`

## string_xrefs

- `0x180017732`: `CDiagnosticXmlParser::get_DiagnosticIcon`
- `0x18001779d`: `CDiagnosticXmlParser::get_DiagnosticIcon`
- `0x1800177c5`: `CDiagnosticXmlParser::get_DiagnosticIcon`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_DiagnosticIcon(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_DiagnosticIcon",
        -2147024809,
        (__int64)"DiagnosticIcon");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:DiagnosticIcon", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Execution/cfg:Icon", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_DiagnosticIcon", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_DiagnosticIcon");
  return XmlStringElement;
}

```

## disassembly

```asm
0x180017708  push    rbx
0x18001770a  sub     rsp, 30h
0x18001770e  test    rdx, rdx
0x180017711  jnz     short loc_180017748
0x180017713  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001771a  mov     ebx, 80070057h
0x18001771f  jz      loc_1800177D8
0x180017725  lea     rax, aDiagnosticicon; "DiagnosticIcon"
0x18001772c  mov     r9d, 80070057h
0x180017732  lea     r8, aCdiagnosticxml_3; "CDiagnosticXmlParser::get_DiagnosticIco"...
0x180017739  mov     [rsp+38h+var_18], rax
0x18001773e  call    McTemplateU0sqs_EventWriteTransfer
0x180017743  jmp     loc_1800177D8
0x180017748  mov     qword ptr [rdx], 0
0x18001774f  cmp     dword ptr [rcx+10h], 0
0x180017753  jnz     short loc_18001776C
0x180017755  mov     r8, rdx; unsigned __int16 **
0x180017758  lea     rdx, aCfgExecutionCf; "cfg:Execution/cfg:Icon"
0x18001775f  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017764  mov     ebx, eax
0x180017766  test    eax, eax
0x180017768  js      short loc_180017785
0x18001776a  jmp     short loc_18001778D
0x18001776c  xor     ebx, ebx
0x18001776e  cmp     dword ptr [rcx+10h], 1
0x180017772  jnz     short loc_1800177BC
0x180017774  mov     r8, rdx; unsigned __int16 **
0x180017777  lea     rdx, aDcpDiagnostici; "dcp:DiagnosticIcon"
0x18001777e  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017783  mov     ebx, eax
0x180017785  cmp     ebx, 80070057h
0x18001778b  jz      short loc_1800177AB
0x18001778d  test    ebx, ebx
0x18001778f  jz      short loc_1800177BC
0x180017791  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017798  jz      short loc_1800177D8
0x18001779a  mov     r9d, ebx
0x18001779d  lea     r8, aCdiagnosticxml_3; "CDiagnosticXmlParser::get_DiagnosticIco"...
0x1800177a4  call    McTemplateU0sq_EventWriteTransfer
0x1800177a9  jmp     short loc_1800177D8
0x1800177ab  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800177b2  jz      short loc_1800177D8
0x1800177b4  mov     r9d, 80070057h
0x1800177ba  jmp     short loc_18001779D
0x1800177bc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800177c3  jz      short loc_1800177D8
0x1800177c5  lea     r8, aCdiagnosticxml_3; "CDiagnosticXmlParser::get_DiagnosticIco"...
0x1800177cc  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800177d3  call    McTemplateU0s_EventWriteTransfer
0x1800177d8  mov     eax, ebx
0x1800177da  add     rsp, 30h
0x1800177de  pop     rbx
0x1800177df  retn
```
