# CDiagnosticXmlParser::get_PrivacyUrl(ushort * *)

- ea: `0x180017a88`
- end: `0x180017b60`
- name: `?get_PrivacyUrl@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z`
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
- `0x180017a88`

## string_xrefs

- `0x180017ab2`: `CDiagnosticXmlParser::get_PrivacyUrl`
- `0x180017b1d`: `CDiagnosticXmlParser::get_PrivacyUrl`
- `0x180017b45`: `CDiagnosticXmlParser::get_PrivacyUrl`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_PrivacyUrl(CDiagnosticXmlParser *this, unsigned __int16 **a2)
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
        (unsigned int)"CDiagnosticXmlParser::get_PrivacyUrl",
        -2147024809,
        (__int64)"PrivacyUrl");
    return XmlStringElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"dcp:PrivacyUrl", a2);
    goto LABEL_9;
  }
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(this, L"cfg:Index/cfg:PrivacyUrl", a2);
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
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_PrivacyUrl", v4);
    return XmlStringElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_PrivacyUrl");
  return XmlStringElement;
}

```

## disassembly

```asm
0x180017a88  push    rbx
0x180017a8a  sub     rsp, 30h
0x180017a8e  test    rdx, rdx
0x180017a91  jnz     short loc_180017AC8
0x180017a93  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017a9a  mov     ebx, 80070057h
0x180017a9f  jz      loc_180017B58
0x180017aa5  lea     rax, aPrivacyurl; "PrivacyUrl"
0x180017aac  mov     r9d, 80070057h
0x180017ab2  lea     r8, aCdiagnosticxml_14; "CDiagnosticXmlParser::get_PrivacyUrl"
0x180017ab9  mov     [rsp+38h+var_18], rax
0x180017abe  call    McTemplateU0sqs_EventWriteTransfer
0x180017ac3  jmp     loc_180017B58
0x180017ac8  mov     qword ptr [rdx], 0
0x180017acf  cmp     dword ptr [rcx+10h], 0
0x180017ad3  jnz     short loc_180017AEC
0x180017ad5  mov     r8, rdx; unsigned __int16 **
0x180017ad8  lea     rdx, aCfgIndexCfgPri; "cfg:Index/cfg:PrivacyUrl"
0x180017adf  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017ae4  mov     ebx, eax
0x180017ae6  test    eax, eax
0x180017ae8  js      short loc_180017B05
0x180017aea  jmp     short loc_180017B0D
0x180017aec  xor     ebx, ebx
0x180017aee  cmp     dword ptr [rcx+10h], 1
0x180017af2  jnz     short loc_180017B3C
0x180017af4  mov     r8, rdx; unsigned __int16 **
0x180017af7  lea     rdx, aDcpPrivacyurl; "dcp:PrivacyUrl"
0x180017afe  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017b03  mov     ebx, eax
0x180017b05  cmp     ebx, 80070057h
0x180017b0b  jz      short loc_180017B2B
0x180017b0d  test    ebx, ebx
0x180017b0f  jz      short loc_180017B3C
0x180017b11  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017b18  jz      short loc_180017B58
0x180017b1a  mov     r9d, ebx
0x180017b1d  lea     r8, aCdiagnosticxml_14; "CDiagnosticXmlParser::get_PrivacyUrl"
0x180017b24  call    McTemplateU0sq_EventWriteTransfer
0x180017b29  jmp     short loc_180017B58
0x180017b2b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017b32  jz      short loc_180017B58
0x180017b34  mov     r9d, 80070057h
0x180017b3a  jmp     short loc_180017B1D
0x180017b3c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017b43  jz      short loc_180017B58
0x180017b45  lea     r8, aCdiagnosticxml_14; "CDiagnosticXmlParser::get_PrivacyUrl"
0x180017b4c  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017b53  call    McTemplateU0s_EventWriteTransfer
0x180017b58  mov     eax, ebx
0x180017b5a  add     rsp, 30h
0x180017b5e  pop     rbx
0x180017b5f  retn
```
