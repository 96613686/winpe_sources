# CDiagnosticXmlParser::get_Name(ushort * *)

- ea: `0x1800179a8`
- end: `0x180017a80`
- name: `?get_Name@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x1800179a8`

## string_xrefs

- `0x1800179d2`: `CDiagnosticXmlParser::get_Name`
- `0x180017a3d`: `CDiagnosticXmlParser::get_Name`
- `0x180017a65`: `CDiagnosticXmlParser::get_Name`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_Name(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_Name",
        -2147024809,
        (__int64)"Name");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:Title", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Execution/cfg:Name", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_Name", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Name");
  return XmlStringElement;
}

```

## disassembly

```asm
0x1800179a8  push    rbx
0x1800179aa  sub     rsp, 30h
0x1800179ae  test    rdx, rdx
0x1800179b1  jnz     short loc_1800179E8
0x1800179b3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800179ba  mov     ebx, 80070057h
0x1800179bf  jz      loc_180017A78
0x1800179c5  lea     rax, aName; "Name"
0x1800179cc  mov     r9d, 80070057h
0x1800179d2  lea     r8, aCdiagnosticxml_9; "CDiagnosticXmlParser::get_Name"
0x1800179d9  mov     [rsp+38h+var_18], rax
0x1800179de  call    McTemplateU0sqs_EventWriteTransfer
0x1800179e3  jmp     loc_180017A78
0x1800179e8  mov     qword ptr [rdx], 0
0x1800179ef  cmp     dword ptr [rcx+10h], 0
0x1800179f3  jnz     short loc_180017A0C
0x1800179f5  mov     r8, rdx; unsigned __int16 **
0x1800179f8  lea     rdx, aCfgExecutionCf_0; "cfg:Execution/cfg:Name"
0x1800179ff  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017a04  mov     ebx, eax
0x180017a06  test    eax, eax
0x180017a08  js      short loc_180017A25
0x180017a0a  jmp     short loc_180017A2D
0x180017a0c  xor     ebx, ebx
0x180017a0e  cmp     dword ptr [rcx+10h], 1
0x180017a12  jnz     short loc_180017A5C
0x180017a14  mov     r8, rdx; unsigned __int16 **
0x180017a17  lea     rdx, aDcpTitle; "dcp:Title"
0x180017a1e  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017a23  mov     ebx, eax
0x180017a25  cmp     ebx, 80070057h
0x180017a2b  jz      short loc_180017A4B
0x180017a2d  test    ebx, ebx
0x180017a2f  jz      short loc_180017A5C
0x180017a31  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017a38  jz      short loc_180017A78
0x180017a3a  mov     r9d, ebx
0x180017a3d  lea     r8, aCdiagnosticxml_9; "CDiagnosticXmlParser::get_Name"
0x180017a44  call    McTemplateU0sq_EventWriteTransfer
0x180017a49  jmp     short loc_180017A78
0x180017a4b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017a52  jz      short loc_180017A78
0x180017a54  mov     r9d, 80070057h
0x180017a5a  jmp     short loc_180017A3D
0x180017a5c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017a63  jz      short loc_180017A78
0x180017a65  lea     r8, aCdiagnosticxml_9; "CDiagnosticXmlParser::get_Name"
0x180017a6c  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017a73  call    McTemplateU0s_EventWriteTransfer
0x180017a78  mov     eax, ebx
0x180017a7a  add     rsp, 30h
0x180017a7e  pop     rbx
0x180017a7f  retn
```
