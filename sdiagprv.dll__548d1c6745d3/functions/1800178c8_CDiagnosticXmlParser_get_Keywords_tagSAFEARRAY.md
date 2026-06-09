# CDiagnosticXmlParser::get_Keywords(tagSAFEARRAY * *)

- ea: `0x1800178c8`
- end: `0x1800179a0`
- name: `?get_Keywords@CDiagnosticXmlParser@@QEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CDiagnosticXmlParser *this, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001374c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180017080`
- `0x1800178c8`

## string_xrefs

- `0x1800178f2`: `CDiagnosticXmlParser::get_Keywords`
- `0x18001795d`: `CDiagnosticXmlParser::get_Keywords`
- `0x180017985`: `CDiagnosticXmlParser::get_Keywords`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_Keywords(CDiagnosticXmlParser *this, struct tagSAFEARRAY **a2)
{
  unsigned int XmlStringArrayElement; // ebx
  __int64 v3; // rdx
  __int64 v4; // r9

  if ( !a2 )
  {
    XmlStringArrayElement = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CDiagnosticXmlParser::get_Keywords",
        -2147024809,
        (__int64)"Keywords");
    return XmlStringArrayElement;
  }
  *a2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    XmlStringArrayElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlStringArrayElement = CDiagnosticXmlParser::ReadXmlStringArrayElement(this, L"dcp:Keyword", a2);
    goto LABEL_9;
  }
  XmlStringArrayElement = CDiagnosticXmlParser::ReadXmlStringArrayElement(this, L"cfg:Index/cfg:Keyword", a2);
  if ( (XmlStringArrayElement & 0x80000000) != 0 )
  {
LABEL_9:
    if ( XmlStringArrayElement == -2147024809 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return XmlStringArrayElement;
      v4 = 2147942487LL;
      goto LABEL_13;
    }
  }
  if ( XmlStringArrayElement )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return XmlStringArrayElement;
    v4 = XmlStringArrayElement;
LABEL_13:
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_Keywords", v4);
    return XmlStringArrayElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Keywords");
  return XmlStringArrayElement;
}

```

## disassembly

```asm
0x1800178c8  push    rbx
0x1800178ca  sub     rsp, 30h
0x1800178ce  test    rdx, rdx
0x1800178d1  jnz     short loc_180017908
0x1800178d3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800178da  mov     ebx, 80070057h
0x1800178df  jz      loc_180017998
0x1800178e5  lea     rax, aKeywords; "Keywords"
0x1800178ec  mov     r9d, 80070057h
0x1800178f2  lea     r8, aCdiagnosticxml_11; "CDiagnosticXmlParser::get_Keywords"
0x1800178f9  mov     [rsp+38h+var_18], rax
0x1800178fe  call    McTemplateU0sqs_EventWriteTransfer
0x180017903  jmp     loc_180017998
0x180017908  mov     qword ptr [rdx], 0
0x18001790f  cmp     dword ptr [rcx+10h], 0
0x180017913  jnz     short loc_18001792C
0x180017915  mov     r8, rdx; struct tagSAFEARRAY **
0x180017918  lea     rdx, aCfgIndexCfgKey; "cfg:Index/cfg:Keyword"
0x18001791f  call    ?ReadXmlStringArrayElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAUtagSAFEARRAY@@@Z; CDiagnosticXmlParser::ReadXmlStringArrayElement(ushort const *,tagSAFEARRAY * *)
0x180017924  mov     ebx, eax
0x180017926  test    eax, eax
0x180017928  js      short loc_180017945
0x18001792a  jmp     short loc_18001794D
0x18001792c  xor     ebx, ebx
0x18001792e  cmp     dword ptr [rcx+10h], 1
0x180017932  jnz     short loc_18001797C
0x180017934  mov     r8, rdx; struct tagSAFEARRAY **
0x180017937  lea     rdx, aDcpKeyword; "dcp:Keyword"
0x18001793e  call    ?ReadXmlStringArrayElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAUtagSAFEARRAY@@@Z; CDiagnosticXmlParser::ReadXmlStringArrayElement(ushort const *,tagSAFEARRAY * *)
0x180017943  mov     ebx, eax
0x180017945  cmp     ebx, 80070057h
0x18001794b  jz      short loc_18001796B
0x18001794d  test    ebx, ebx
0x18001794f  jz      short loc_18001797C
0x180017951  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017958  jz      short loc_180017998
0x18001795a  mov     r9d, ebx
0x18001795d  lea     r8, aCdiagnosticxml_11; "CDiagnosticXmlParser::get_Keywords"
0x180017964  call    McTemplateU0sq_EventWriteTransfer
0x180017969  jmp     short loc_180017998
0x18001796b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017972  jz      short loc_180017998
0x180017974  mov     r9d, 80070057h
0x18001797a  jmp     short loc_18001795D
0x18001797c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017983  jz      short loc_180017998
0x180017985  lea     r8, aCdiagnosticxml_11; "CDiagnosticXmlParser::get_Keywords"
0x18001798c  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017993  call    McTemplateU0s_EventWriteTransfer
0x180017998  mov     eax, ebx
0x18001799a  add     rsp, 30h
0x18001799e  pop     rbx
0x18001799f  retn
```
