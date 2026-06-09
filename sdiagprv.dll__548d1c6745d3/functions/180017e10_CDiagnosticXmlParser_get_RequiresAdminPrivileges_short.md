# CDiagnosticXmlParser::get_RequiresAdminPrivileges(short *)

- ea: `0x180017e10`
- end: `0x180017ee1`
- name: `?get_RequiresAdminPrivileges@CDiagnosticXmlParser@@QEAAJPEAF@Z`
- size: `209`
- prototype: `__int64 __fastcall(CDiagnosticXmlParser *this, __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001374c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180016e6c`
- `0x180017e10`

## string_xrefs

- `0x180017e2d`: `RequiresAdminPrivileges`
- `0x180017e59`: `cfg:Index/cfg:RequiresAdminPrivileges`
- `0x180017e78`: `dcp:RequiresAdminPrivileges`
- `0x180017e3a`: `CDiagnosticXmlParser::get_RequiresAdminPrivileges`
- `0x180017e9e`: `CDiagnosticXmlParser::get_RequiresAdminPrivileges`
- `0x180017ec6`: `CDiagnosticXmlParser::get_RequiresAdminPrivileges`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_RequiresAdminPrivileges(CDiagnosticXmlParser *this, __int16 *a2)
{
  unsigned int XmlBoolElement; // ebx
  __int64 v3; // rdx
  __int64 v4; // r9

  if ( !a2 )
  {
    XmlBoolElement = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CDiagnosticXmlParser::get_RequiresAdminPrivileges",
        -2147024809,
        (__int64)"RequiresAdminPrivileges");
    return XmlBoolElement;
  }
  if ( *((_DWORD *)this + 4) )
  {
    XmlBoolElement = 0;
    if ( *((_DWORD *)this + 4) != 1 )
      goto LABEL_16;
    XmlBoolElement = CDiagnosticXmlParser::ReadXmlBoolElement(this, L"dcp:RequiresAdminPrivileges", a2);
    goto LABEL_9;
  }
  XmlBoolElement = CDiagnosticXmlParser::ReadXmlBoolElement(this, L"cfg:Index/cfg:RequiresAdminPrivileges", a2);
  if ( (XmlBoolElement & 0x80000000) != 0 )
  {
LABEL_9:
    if ( XmlBoolElement == -2147024809 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return XmlBoolElement;
      v4 = 2147942487LL;
      goto LABEL_13;
    }
  }
  if ( XmlBoolElement )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return XmlBoolElement;
    v4 = XmlBoolElement;
LABEL_13:
    McTemplateU0sq_EventWriteTransfer(this, v3, "CDiagnosticXmlParser::get_RequiresAdminPrivileges", v4);
    return XmlBoolElement;
  }
LABEL_16:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "CDiagnosticXmlParser::get_RequiresAdminPrivileges");
  return XmlBoolElement;
}

```

## disassembly

```asm
0x180017e10  push    rbx
0x180017e12  sub     rsp, 30h
0x180017e16  test    rdx, rdx
0x180017e19  jnz     short loc_180017E50
0x180017e1b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017e22  mov     ebx, 80070057h
0x180017e27  jz      loc_180017ED9
0x180017e2d  lea     rax, aRequiresadminp; "RequiresAdminPrivileges"
0x180017e34  mov     r9d, 80070057h
0x180017e3a  lea     r8, aCdiagnosticxml_8; "CDiagnosticXmlParser::get_RequiresAdmin"...
0x180017e41  mov     [rsp+38h+var_18], rax
0x180017e46  call    McTemplateU0sqs_EventWriteTransfer
0x180017e4b  jmp     loc_180017ED9
0x180017e50  cmp     dword ptr [rcx+10h], 0
0x180017e54  jnz     short loc_180017E6D
0x180017e56  mov     r8, rdx; __int16 *
0x180017e59  lea     rdx, aCfgIndexCfgReq; "cfg:Index/cfg:RequiresAdminPrivileges"
0x180017e60  call    ?ReadXmlBoolElement@CDiagnosticXmlParser@@AEAAJPEBGPEAF@Z; CDiagnosticXmlParser::ReadXmlBoolElement(ushort const *,short *)
0x180017e65  mov     ebx, eax
0x180017e67  test    eax, eax
0x180017e69  js      short loc_180017E86
0x180017e6b  jmp     short loc_180017E8E
0x180017e6d  xor     ebx, ebx
0x180017e6f  cmp     dword ptr [rcx+10h], 1
0x180017e73  jnz     short loc_180017EBD
0x180017e75  mov     r8, rdx; __int16 *
0x180017e78  lea     rdx, aDcpRequiresadm; "dcp:RequiresAdminPrivileges"
0x180017e7f  call    ?ReadXmlBoolElement@CDiagnosticXmlParser@@AEAAJPEBGPEAF@Z; CDiagnosticXmlParser::ReadXmlBoolElement(ushort const *,short *)
0x180017e84  mov     ebx, eax
0x180017e86  cmp     ebx, 80070057h
0x180017e8c  jz      short loc_180017EAC
0x180017e8e  test    ebx, ebx
0x180017e90  jz      short loc_180017EBD
0x180017e92  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017e99  jz      short loc_180017ED9
0x180017e9b  mov     r9d, ebx
0x180017e9e  lea     r8, aCdiagnosticxml_8; "CDiagnosticXmlParser::get_RequiresAdmin"...
0x180017ea5  call    McTemplateU0sq_EventWriteTransfer
0x180017eaa  jmp     short loc_180017ED9
0x180017eac  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017eb3  jz      short loc_180017ED9
0x180017eb5  mov     r9d, 80070057h
0x180017ebb  jmp     short loc_180017E9E
0x180017ebd  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017ec4  jz      short loc_180017ED9
0x180017ec6  lea     r8, aCdiagnosticxml_8; "CDiagnosticXmlParser::get_RequiresAdmin"...
0x180017ecd  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017ed4  call    McTemplateU0s_EventWriteTransfer
0x180017ed9  mov     eax, ebx
0x180017edb  add     rsp, 30h
0x180017edf  pop     rbx
0x180017ee0  retn
```
