# CDiagnosticXmlParser::get_Version(ushort * *)

- ea: `0x180017ee8`
- end: `0x180017fc0`
- name: `?get_Version@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x180017ee8`

## string_xrefs

- `0x180017f12`: `CDiagnosticXmlParser::get_Version`
- `0x180017f7d`: `CDiagnosticXmlParser::get_Version`
- `0x180017fa5`: `CDiagnosticXmlParser::get_Version`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_Version(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_Version",
        -2147024809,
        (__int64)"Version");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:Version", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Index/cfg:Version", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_Version", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Version");
  return XmlStringElement;
}

```

## disassembly

```asm
0x180017ee8  push    rbx
0x180017eea  sub     rsp, 30h
0x180017eee  test    rdx, rdx
0x180017ef1  jnz     short loc_180017F28
0x180017ef3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017efa  mov     ebx, 80070057h
0x180017eff  jz      loc_180017FB8
0x180017f05  lea     rax, aVersion; "Version"
0x180017f0c  mov     r9d, 80070057h
0x180017f12  lea     r8, aCdiagnosticxml; "CDiagnosticXmlParser::get_Version"
0x180017f19  mov     [rsp+38h+var_18], rax
0x180017f1e  call    McTemplateU0sqs_EventWriteTransfer
0x180017f23  jmp     loc_180017FB8
0x180017f28  mov     qword ptr [rdx], 0
0x180017f2f  cmp     dword ptr [rcx+10h], 0
0x180017f33  jnz     short loc_180017F4C
0x180017f35  mov     r8, rdx; unsigned __int16 **
0x180017f38  lea     rdx, aCfgIndexCfgVer; "cfg:Index/cfg:Version"
0x180017f3f  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017f44  mov     ebx, eax
0x180017f46  test    eax, eax
0x180017f48  js      short loc_180017F65
0x180017f4a  jmp     short loc_180017F6D
0x180017f4c  xor     ebx, ebx
0x180017f4e  cmp     dword ptr [rcx+10h], 1
0x180017f52  jnz     short loc_180017F9C
0x180017f54  mov     r8, rdx; unsigned __int16 **
0x180017f57  lea     rdx, aDcpVersion; "dcp:Version"
0x180017f5e  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017f63  mov     ebx, eax
0x180017f65  cmp     ebx, 80070057h
0x180017f6b  jz      short loc_180017F8B
0x180017f6d  test    ebx, ebx
0x180017f6f  jz      short loc_180017F9C
0x180017f71  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017f78  jz      short loc_180017FB8
0x180017f7a  mov     r9d, ebx
0x180017f7d  lea     r8, aCdiagnosticxml; "CDiagnosticXmlParser::get_Version"
0x180017f84  call    McTemplateU0sq_EventWriteTransfer
0x180017f89  jmp     short loc_180017FB8
0x180017f8b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017f92  jz      short loc_180017FB8
0x180017f94  mov     r9d, 80070057h
0x180017f9a  jmp     short loc_180017F7D
0x180017f9c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017fa3  jz      short loc_180017FB8
0x180017fa5  lea     r8, aCdiagnosticxml; "CDiagnosticXmlParser::get_Version"
0x180017fac  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017fb3  call    McTemplateU0s_EventWriteTransfer
0x180017fb8  mov     eax, ebx
0x180017fba  add     rsp, 30h
0x180017fbe  pop     rbx
0x180017fbf  retn
```
