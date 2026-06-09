# CDiagnosticXmlParser::get_Id(ushort * *)

- ea: `0x1800177e8`
- end: `0x1800178c0`
- name: `?get_Id@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x1800177e8`

## string_xrefs

- `0x180017812`: `CDiagnosticXmlParser::get_Id`
- `0x18001787d`: `CDiagnosticXmlParser::get_Id`
- `0x1800178a5`: `CDiagnosticXmlParser::get_Id`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_Id(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_Id",
        -2147024809,
        (__int64)"Id");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:Id", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Index/cfg:Id", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_Id", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Id");
  return XmlStringElement;
}

```

## disassembly

```asm
0x1800177e8  push    rbx
0x1800177ea  sub     rsp, 30h
0x1800177ee  test    rdx, rdx
0x1800177f1  jnz     short loc_180017828
0x1800177f3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800177fa  mov     ebx, 80070057h
0x1800177ff  jz      loc_1800178B8
0x180017805  lea     rax, aId; "Id"
0x18001780c  mov     r9d, 80070057h
0x180017812  lea     r8, aCdiagnosticxml_2; "CDiagnosticXmlParser::get_Id"
0x180017819  mov     [rsp+38h+var_18], rax
0x18001781e  call    McTemplateU0sqs_EventWriteTransfer
0x180017823  jmp     loc_1800178B8
0x180017828  mov     qword ptr [rdx], 0
0x18001782f  cmp     dword ptr [rcx+10h], 0
0x180017833  jnz     short loc_18001784C
0x180017835  mov     r8, rdx; unsigned __int16 **
0x180017838  lea     rdx, aCfgIndexCfgId; "cfg:Index/cfg:Id"
0x18001783f  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017844  mov     ebx, eax
0x180017846  test    eax, eax
0x180017848  js      short loc_180017865
0x18001784a  jmp     short loc_18001786D
0x18001784c  xor     ebx, ebx
0x18001784e  cmp     dword ptr [rcx+10h], 1
0x180017852  jnz     short loc_18001789C
0x180017854  mov     r8, rdx; unsigned __int16 **
0x180017857  lea     rdx, aDcpId; "dcp:Id"
0x18001785e  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017863  mov     ebx, eax
0x180017865  cmp     ebx, 80070057h
0x18001786b  jz      short loc_18001788B
0x18001786d  test    ebx, ebx
0x18001786f  jz      short loc_18001789C
0x180017871  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017878  jz      short loc_1800178B8
0x18001787a  mov     r9d, ebx
0x18001787d  lea     r8, aCdiagnosticxml_2; "CDiagnosticXmlParser::get_Id"
0x180017884  call    McTemplateU0sq_EventWriteTransfer
0x180017889  jmp     short loc_1800178B8
0x18001788b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017892  jz      short loc_1800178B8
0x180017894  mov     r9d, 80070057h
0x18001789a  jmp     short loc_18001787D
0x18001789c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800178a3  jz      short loc_1800178B8
0x1800178a5  lea     r8, aCdiagnosticxml_2; "CDiagnosticXmlParser::get_Id"
0x1800178ac  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800178b3  call    McTemplateU0s_EventWriteTransfer
0x1800178b8  mov     eax, ebx
0x1800178ba  add     rsp, 30h
0x1800178be  pop     rbx
0x1800178bf  retn
```
