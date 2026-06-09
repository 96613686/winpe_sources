# CDiagnosticXmlParser::get_PublisherName(ushort * *)

- ea: `0x180017d30`
- end: `0x180017e08`
- name: `?get_PublisherName@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x180017d30`

## string_xrefs

- `0x180017d5a`: `CDiagnosticXmlParser::get_PublisherName`
- `0x180017dc5`: `CDiagnosticXmlParser::get_PublisherName`
- `0x180017ded`: `CDiagnosticXmlParser::get_PublisherName`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_PublisherName(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_PublisherName",
        -2147024809,
        (__int64)"PublisherName");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:PublisherName", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Index/cfg:PublisherName", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_PublisherName", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_PublisherName");
  return XmlStringElement;
}

```

## disassembly

```asm
0x180017d30  push    rbx
0x180017d32  sub     rsp, 30h
0x180017d36  test    rdx, rdx
0x180017d39  jnz     short loc_180017D70
0x180017d3b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017d42  mov     ebx, 80070057h
0x180017d47  jz      loc_180017E00
0x180017d4d  lea     rax, aPublishername; "PublisherName"
0x180017d54  mov     r9d, 80070057h
0x180017d5a  lea     r8, aCdiagnosticxml_1; "CDiagnosticXmlParser::get_PublisherName"
0x180017d61  mov     [rsp+38h+var_18], rax
0x180017d66  call    McTemplateU0sqs_EventWriteTransfer
0x180017d6b  jmp     loc_180017E00
0x180017d70  mov     qword ptr [rdx], 0
0x180017d77  cmp     dword ptr [rcx+10h], 0
0x180017d7b  jnz     short loc_180017D94
0x180017d7d  mov     r8, rdx; unsigned __int16 **
0x180017d80  lea     rdx, aCfgIndexCfgPub; "cfg:Index/cfg:PublisherName"
0x180017d87  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017d8c  mov     ebx, eax
0x180017d8e  test    eax, eax
0x180017d90  js      short loc_180017DAD
0x180017d92  jmp     short loc_180017DB5
0x180017d94  xor     ebx, ebx
0x180017d96  cmp     dword ptr [rcx+10h], 1
0x180017d9a  jnz     short loc_180017DE4
0x180017d9c  mov     r8, rdx; unsigned __int16 **
0x180017d9f  lea     rdx, aDcpPublisherna; "dcp:PublisherName"
0x180017da6  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017dab  mov     ebx, eax
0x180017dad  cmp     ebx, 80070057h
0x180017db3  jz      short loc_180017DD3
0x180017db5  test    ebx, ebx
0x180017db7  jz      short loc_180017DE4
0x180017db9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017dc0  jz      short loc_180017E00
0x180017dc2  mov     r9d, ebx
0x180017dc5  lea     r8, aCdiagnosticxml_1; "CDiagnosticXmlParser::get_PublisherName"
0x180017dcc  call    McTemplateU0sq_EventWriteTransfer
0x180017dd1  jmp     short loc_180017E00
0x180017dd3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017dda  jz      short loc_180017E00
0x180017ddc  mov     r9d, 80070057h
0x180017de2  jmp     short loc_180017DC5
0x180017de4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017deb  jz      short loc_180017E00
0x180017ded  lea     r8, aCdiagnosticxml_1; "CDiagnosticXmlParser::get_PublisherName"
0x180017df4  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017dfb  call    McTemplateU0s_EventWriteTransfer
0x180017e00  mov     eax, ebx
0x180017e02  add     rsp, 30h
0x180017e06  pop     rbx
0x180017e07  retn
```
