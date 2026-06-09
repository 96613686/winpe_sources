# CDiagnosticXmlParser::get_Description(ushort * *)

- ea: `0x180017628`
- end: `0x180017700`
- name: `?get_Description@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x180017628`

## string_xrefs

- `0x180017652`: `CDiagnosticXmlParser::get_Description`
- `0x1800176bd`: `CDiagnosticXmlParser::get_Description`
- `0x1800176e5`: `CDiagnosticXmlParser::get_Description`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_Description(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_Description",
        -2147024809,
        (__int64)"Description");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:Description", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Execution/cfg:Description", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_Description", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Description");
  return XmlStringElement;
}

```

## disassembly

```asm
0x180017628  push    rbx
0x18001762a  sub     rsp, 30h
0x18001762e  test    rdx, rdx
0x180017631  jnz     short loc_180017668
0x180017633  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001763a  mov     ebx, 80070057h
0x18001763f  jz      loc_1800176F8
0x180017645  lea     rax, aDescription; "Description"
0x18001764c  mov     r9d, 80070057h
0x180017652  lea     r8, aCdiagnosticxml_13; "CDiagnosticXmlParser::get_Description"
0x180017659  mov     [rsp+38h+var_18], rax
0x18001765e  call    McTemplateU0sqs_EventWriteTransfer
0x180017663  jmp     loc_1800176F8
0x180017668  mov     qword ptr [rdx], 0
0x18001766f  cmp     dword ptr [rcx+10h], 0
0x180017673  jnz     short loc_18001768C
0x180017675  mov     r8, rdx; unsigned __int16 **
0x180017678  lea     rdx, aCfgExecutionCf_1; "cfg:Execution/cfg:Description"
0x18001767f  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017684  mov     ebx, eax
0x180017686  test    eax, eax
0x180017688  js      short loc_1800176A5
0x18001768a  jmp     short loc_1800176AD
0x18001768c  xor     ebx, ebx
0x18001768e  cmp     dword ptr [rcx+10h], 1
0x180017692  jnz     short loc_1800176DC
0x180017694  mov     r8, rdx; unsigned __int16 **
0x180017697  lea     rdx, aDcpDescription; "dcp:Description"
0x18001769e  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x1800176a3  mov     ebx, eax
0x1800176a5  cmp     ebx, 80070057h
0x1800176ab  jz      short loc_1800176CB
0x1800176ad  test    ebx, ebx
0x1800176af  jz      short loc_1800176DC
0x1800176b1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800176b8  jz      short loc_1800176F8
0x1800176ba  mov     r9d, ebx
0x1800176bd  lea     r8, aCdiagnosticxml_13; "CDiagnosticXmlParser::get_Description"
0x1800176c4  call    McTemplateU0sq_EventWriteTransfer
0x1800176c9  jmp     short loc_1800176F8
0x1800176cb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800176d2  jz      short loc_1800176F8
0x1800176d4  mov     r9d, 80070057h
0x1800176da  jmp     short loc_1800176BD
0x1800176dc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800176e3  jz      short loc_1800176F8
0x1800176e5  lea     r8, aCdiagnosticxml_13; "CDiagnosticXmlParser::get_Description"
0x1800176ec  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800176f3  call    McTemplateU0s_EventWriteTransfer
0x1800176f8  mov     eax, ebx
0x1800176fa  add     rsp, 30h
0x1800176fe  pop     rbx
0x1800176ff  retn
```
