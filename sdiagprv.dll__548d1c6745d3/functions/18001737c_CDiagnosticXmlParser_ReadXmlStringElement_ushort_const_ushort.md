# CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)

- ea: `0x18001737c`
- end: `0x180017540`
- name: `?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z`
- size: `452`
- prototype: `__int64 __fastcall(CDiagnosticXmlParser *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001374c`
- `0x180017548`
- `0x180017628`
- `0x180017708`
- `0x1800177e8`
- `0x1800179a8`
- `0x180017a88`
- `0x180017b68`
- `0x180017d30`
- `0x180017ee8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18001737c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800173e7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800173e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180017512`
- `OLEAUT32!__imp_SysFreeString` at `0x180017512`

## string_xrefs

- `0x1800173be`: `CDiagnosticXmlParser::ReadXmlStringElement`
- `0x180017403`: `CDiagnosticXmlParser::ReadXmlStringElement`
- `0x180017496`: `CDiagnosticXmlParser::ReadXmlStringElement`
- `0x1800174bf`: `CDiagnosticXmlParser::ReadXmlStringElement`
- `0x1800174dd`: `CDiagnosticXmlParser::ReadXmlStringElement`
- `0x180017503`: `CDiagnosticXmlParser::ReadXmlStringElement`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::ReadXmlStringElement(
        CDiagnosticXmlParser *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  CDiagnosticXmlParser *v4; // rbx
  unsigned int v5; // ebx
  OLECHAR *v6; // rdi
  BSTR v7; // rax
  int v8; // eax
  CDiagnosticXmlParser *v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  v4 = this;
  if ( a2 )
  {
    if ( !a3 )
    {
      v6 = 0;
      v5 = -2147024809;
      goto LABEL_17;
    }
    v7 = SysAllocString(a2);
    v6 = v7;
    if ( !v7 )
    {
      v5 = -2147024882;
      goto LABEL_8;
    }
    if ( (*(int (__fastcall **)(_QWORD, BSTR, CDiagnosticXmlParser **))(**((_QWORD **)v4 + 1) + 296LL))(
           *((_QWORD *)v4 + 1),
           v7,
           &v10) >= 0
      && (this = v10) != 0 )
    {
      v8 = (*(__int64 (__fastcall **)(CDiagnosticXmlParser *, unsigned __int16 **))(*(_QWORD *)v10 + 208LL))(v10, a3);
      v5 = v8;
      if ( v8 < 0 )
      {
        if ( v8 == -2147024882 )
        {
LABEL_8:
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0s_EventWriteTransfer(
              this,
              SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
              "CDiagnosticXmlParser::ReadXmlStringElement");
LABEL_10:
          if ( !v6 )
            goto LABEL_29;
          goto LABEL_28;
        }
        if ( v8 == -2147024809 )
        {
LABEL_17:
          if ( a3 )
          {
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
              McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticXmlParser::ReadXmlStringElement", 2147942487LL);
          }
          else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          {
            McTemplateU0sqs_EventWriteTransfer(
              (_DWORD)this,
              (_DWORD)a2,
              (unsigned int)"CDiagnosticXmlParser::ReadXmlStringElement",
              -2147024809,
              (__int64)"Value");
          }
          goto LABEL_10;
        }
      }
      if ( !v8 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(
            this,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "CDiagnosticXmlParser::ReadXmlStringElement");
LABEL_28:
        SysFreeString(v6);
        goto LABEL_29;
      }
    }
    else
    {
      v5 = -2147024637;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticXmlParser::ReadXmlStringElement", v5);
    goto LABEL_28;
  }
  v5 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    return v5;
  McTemplateU0sqs_EventWriteTransfer(
    (_DWORD)this,
    0,
    (unsigned int)"CDiagnosticXmlParser::ReadXmlStringElement",
    -2147024809,
    (__int64)"FieldName");
LABEL_29:
  if ( v10 )
    (*(void (__fastcall **)(CDiagnosticXmlParser *))(*(_QWORD *)v10 + 16LL))(v10);
  return v5;
}

```

## disassembly

```asm
0x18001737c  mov     r11, rsp
0x18001737f  mov     [r11+8], rbx
0x180017383  mov     [r11+18h], rsi
0x180017387  push    rdi
0x180017388  sub     rsp, 30h
0x18001738c  mov     qword ptr [r11+10h], 0
0x180017394  mov     rsi, r8
0x180017397  mov     rbx, rcx
0x18001739a  test    rdx, rdx
0x18001739d  jnz     short loc_1800173D3
0x18001739f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800173a6  mov     ebx, 80070057h
0x1800173ab  jz      loc_18001752E
0x1800173b1  lea     rax, aFieldname; "FieldName"
0x1800173b8  mov     r9d, 80070057h
0x1800173be  lea     r8, aCdiagnosticxml_6; "CDiagnosticXmlParser::ReadXmlStringElem"...
0x1800173c5  mov     [r11-18h], rax
0x1800173c9  call    McTemplateU0sqs_EventWriteTransfer
0x1800173ce  jmp     loc_180017518
0x1800173d3  test    rsi, rsi
0x1800173d6  jnz     short loc_1800173E4
0x1800173d8  xor     edi, edi
0x1800173da  mov     ebx, 80070057h
0x1800173df  jmp     loc_18001747B
0x1800173e4  mov     rcx, rdx; psz
0x1800173e7  call    cs:__imp_SysAllocString
0x1800173ed  mov     rdi, rax
0x1800173f0  test    rax, rax
0x1800173f3  jnz     short loc_180017424
0x1800173f5  mov     ebx, 8007000Eh
0x1800173fa  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017401  jz      short loc_180017416
0x180017403  lea     r8, aCdiagnosticxml_6; "CDiagnosticXmlParser::ReadXmlStringElem"...
0x18001740a  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180017411  call    McTemplateU0s_EventWriteTransfer
0x180017416  test    rdi, rdi
0x180017419  jz      loc_180017518
0x18001741f  jmp     loc_18001750F
0x180017424  mov     rcx, [rbx+8]
0x180017428  lea     r8, [rsp+38h+arg_8]
0x18001742d  mov     rdx, rdi
0x180017430  mov     rax, [rcx]
0x180017433  mov     rax, [rax+128h]
0x18001743a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001743f  test    eax, eax
0x180017441  js      loc_1800174F2
0x180017447  mov     rcx, [rsp+38h+arg_8]
0x18001744c  test    rcx, rcx
0x18001744f  jz      loc_1800174F2
0x180017455  mov     rax, [rcx]
0x180017458  mov     rdx, rsi
0x18001745b  mov     rax, [rax+0D0h]
0x180017462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017467  mov     ebx, eax
0x180017469  test    eax, eax
0x18001746b  jns     short loc_1800174D0
0x18001746d  cmp     eax, 8007000Eh
0x180017472  jz      short loc_1800173FA
0x180017474  cmp     eax, 80070057h
0x180017479  jnz     short loc_1800174D0
0x18001747b  test    rsi, rsi
0x18001747e  jnz     short loc_1800174AC
0x180017480  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017487  jz      short loc_180017416
0x180017489  lea     rax, aValue; "Value"
0x180017490  mov     r9d, 80070057h
0x180017496  lea     r8, aCdiagnosticxml_6; "CDiagnosticXmlParser::ReadXmlStringElem"...
0x18001749d  mov     [rsp+38h+var_18], rax
0x1800174a2  call    McTemplateU0sqs_EventWriteTransfer
0x1800174a7  jmp     loc_180017416
0x1800174ac  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800174b3  jz      loc_180017416
0x1800174b9  mov     r9d, 80070057h
0x1800174bf  lea     r8, aCdiagnosticxml_6; "CDiagnosticXmlParser::ReadXmlStringElem"...
0x1800174c6  call    McTemplateU0sq_EventWriteTransfer
0x1800174cb  jmp     loc_180017416
0x1800174d0  test    ebx, ebx
0x1800174d2  jnz     short loc_1800174F7
0x1800174d4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800174db  jz      short loc_18001750F
0x1800174dd  lea     r8, aCdiagnosticxml_6; "CDiagnosticXmlParser::ReadXmlStringElem"...
0x1800174e4  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800174eb  call    McTemplateU0s_EventWriteTransfer
0x1800174f0  jmp     short loc_18001750F
0x1800174f2  mov     ebx, 80070103h
0x1800174f7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800174fe  jz      short loc_18001750F
0x180017500  mov     r9d, ebx
0x180017503  lea     r8, aCdiagnosticxml_6; "CDiagnosticXmlParser::ReadXmlStringElem"...
0x18001750a  call    McTemplateU0sq_EventWriteTransfer
0x18001750f  mov     rcx, rdi; bstrString
0x180017512  call    cs:__imp_SysFreeString
0x180017518  mov     rcx, [rsp+38h+arg_8]
0x18001751d  test    rcx, rcx
0x180017520  jz      short loc_18001752E
0x180017522  mov     rax, [rcx]
0x180017525  mov     rax, [rax+10h]
0x180017529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001752e  mov     rsi, [rsp+38h+arg_10]
0x180017533  mov     eax, ebx
0x180017535  mov     rbx, [rsp+38h+arg_0]
0x18001753a  add     rsp, 30h
0x18001753e  pop     rdi
0x18001753f  retn
```
