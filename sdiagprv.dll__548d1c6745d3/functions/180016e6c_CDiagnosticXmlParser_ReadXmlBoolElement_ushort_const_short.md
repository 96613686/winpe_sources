# CDiagnosticXmlParser::ReadXmlBoolElement(ushort const *,short *)

- ea: `0x180016e6c`
- end: `0x180017078`
- name: `?ReadXmlBoolElement@CDiagnosticXmlParser@@AEAAJPEBGPEAF@Z`
- size: `524`
- prototype: `__int64 __fastcall(CDiagnosticXmlParser *this, const unsigned __int16 *, __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017e10`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180016e6c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016f0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f0c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017031`
- `OLEAUT32!__imp_SysFreeString` at `0x180017041`
- `OLEAUT32!__imp_SysFreeString` at `0x180017031`
- `OLEAUT32!__imp_SysFreeString` at `0x180017041`
- `OLEAUT32!__imp_VarBoolFromStr` at `0x180016fa7`
- `OLEAUT32!__imp_VarBoolFromStr` at `0x180016fa7`

## string_xrefs

- `0x180016eb6`: `CDiagnosticXmlParser::ReadXmlBoolElement`
- `0x180016ef6`: `CDiagnosticXmlParser::ReadXmlBoolElement`
- `0x180016f28`: `CDiagnosticXmlParser::ReadXmlBoolElement`
- `0x180016fd8`: `CDiagnosticXmlParser::ReadXmlBoolElement`
- `0x180017000`: `CDiagnosticXmlParser::ReadXmlBoolElement`
- `0x180017022`: `CDiagnosticXmlParser::ReadXmlBoolElement`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::ReadXmlBoolElement(
        CDiagnosticXmlParser *this,
        const unsigned __int16 *a2,
        __int16 *a3)
{
  CDiagnosticXmlParser *v4; // rbx
  HRESULT v5; // ebx
  OLECHAR *v6; // rdi
  BSTR v7; // rax
  LPCOLESTR strIn; // [rsp+48h] [rbp+10h] BYREF
  CDiagnosticXmlParser *v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  strIn = 0;
  v4 = this;
  if ( a2 )
  {
    if ( !a3 )
    {
      v6 = 0;
      v5 = -2147024809;
      goto LABEL_6;
    }
    v7 = SysAllocString(a2);
    v6 = v7;
    if ( !v7 )
    {
      v5 = -2147024882;
      goto LABEL_11;
    }
    if ( (*(int (__fastcall **)(_QWORD, BSTR, CDiagnosticXmlParser **))(**((_QWORD **)v4 + 1) + 296LL))(
           *((_QWORD *)v4 + 1),
           v7,
           &v10) >= 0
      && (this = v10) != 0 )
    {
      v5 = (*(__int64 (__fastcall **)(CDiagnosticXmlParser *, LPCOLESTR *))(*(_QWORD *)v10 + 208LL))(v10, &strIn);
      if ( v5 < 0 || (v5 = VarBoolFromStr(strIn, 0x7Fu, 0x80000000, a3), v5 < 0) )
      {
        if ( v5 == -2147024882 )
        {
LABEL_11:
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0s_EventWriteTransfer(
              this,
              SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
              "CDiagnosticXmlParser::ReadXmlBoolElement");
LABEL_13:
          if ( !v6 )
            goto LABEL_30;
LABEL_29:
          SysFreeString(v6);
          goto LABEL_30;
        }
        if ( v5 == -2147024809 )
        {
LABEL_6:
          if ( a3 )
          {
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
              McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticXmlParser::ReadXmlBoolElement", 2147942487LL);
          }
          else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          {
            McTemplateU0sqs_EventWriteTransfer(
              (_DWORD)this,
              (_DWORD)a2,
              (unsigned int)"CDiagnosticXmlParser::ReadXmlBoolElement",
              -2147024809,
              (__int64)"Value");
          }
          goto LABEL_13;
        }
      }
      if ( !v5 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(
            this,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "CDiagnosticXmlParser::ReadXmlBoolElement");
        goto LABEL_29;
      }
    }
    else
    {
      v5 = -2147024637;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticXmlParser::ReadXmlBoolElement", (unsigned int)v5);
    goto LABEL_29;
  }
  v5 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    return (unsigned int)v5;
  McTemplateU0sqs_EventWriteTransfer(
    (_DWORD)this,
    0,
    (unsigned int)"CDiagnosticXmlParser::ReadXmlBoolElement",
    -2147024809,
    (__int64)"FieldName");
LABEL_30:
  if ( strIn )
  {
    SysFreeString((BSTR)strIn);
    strIn = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(CDiagnosticXmlParser *))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016e6c  mov     r11, rsp
0x180016e6f  mov     [r11+8], rbx
0x180016e73  mov     [r11+18h], rsi
0x180016e77  push    rdi
0x180016e78  sub     rsp, 30h
0x180016e7c  mov     qword ptr [r11+20h], 0
0x180016e84  mov     rsi, r8
0x180016e87  mov     qword ptr [r11+10h], 0
0x180016e8f  mov     rbx, rcx
0x180016e92  test    rdx, rdx
0x180016e95  jnz     short loc_180016ECB
0x180016e97  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016e9e  mov     ebx, 80070057h
0x180016ea3  jz      loc_180017066
0x180016ea9  lea     rax, aFieldname; "FieldName"
0x180016eb0  mov     r9d, 80070057h
0x180016eb6  lea     r8, aCdiagnosticxml_5; "CDiagnosticXmlParser::ReadXmlBoolElemen"...
0x180016ebd  mov     [r11-18h], rax
0x180016ec1  call    McTemplateU0sqs_EventWriteTransfer
0x180016ec6  jmp     loc_180017037
0x180016ecb  test    rsi, rsi
0x180016ece  jnz     short loc_180016F09
0x180016ed0  xor     edi, edi
0x180016ed2  mov     ebx, 80070057h
0x180016ed7  test    rsi, rsi
0x180016eda  jnz     loc_180016FED
0x180016ee0  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016ee7  jz      short loc_180016F3B
0x180016ee9  lea     rax, aValue; "Value"
0x180016ef0  mov     r9d, 80070057h
0x180016ef6  lea     r8, aCdiagnosticxml_5; "CDiagnosticXmlParser::ReadXmlBoolElemen"...
0x180016efd  mov     [rsp+38h+var_18], rax
0x180016f02  call    McTemplateU0sqs_EventWriteTransfer
0x180016f07  jmp     short loc_180016F3B
0x180016f09  mov     rcx, rdx; psz
0x180016f0c  call    cs:__imp_SysAllocString
0x180016f12  mov     rdi, rax
0x180016f15  test    rax, rax
0x180016f18  jnz     short loc_180016F49
0x180016f1a  mov     ebx, 8007000Eh
0x180016f1f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016f26  jz      short loc_180016F3B
0x180016f28  lea     r8, aCdiagnosticxml_5; "CDiagnosticXmlParser::ReadXmlBoolElemen"...
0x180016f2f  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180016f36  call    McTemplateU0s_EventWriteTransfer
0x180016f3b  test    rdi, rdi
0x180016f3e  jz      loc_180017037
0x180016f44  jmp     loc_18001702E
0x180016f49  mov     rcx, [rbx+8]
0x180016f4d  lea     r8, [rsp+38h+arg_18]
0x180016f52  mov     rdx, rdi
0x180016f55  mov     rax, [rcx]
0x180016f58  mov     rax, [rax+128h]
0x180016f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f64  test    eax, eax
0x180016f66  js      loc_180017011
0x180016f6c  mov     rcx, [rsp+38h+arg_18]
0x180016f71  test    rcx, rcx
0x180016f74  jz      loc_180017011
0x180016f7a  mov     rax, [rcx]
0x180016f7d  lea     rdx, [rsp+38h+strIn]
0x180016f82  mov     rax, [rax+0D0h]
0x180016f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f8e  mov     ebx, eax
0x180016f90  test    eax, eax
0x180016f92  js      short loc_180016FB3
0x180016f94  mov     rcx, [rsp+38h+strIn]; strIn
0x180016f99  mov     r9, rsi; pboolOut
0x180016f9c  mov     edx, 7Fh; lcid
0x180016fa1  mov     r8d, 80000000h; dwFlags
0x180016fa7  call    cs:__imp_VarBoolFromStr
0x180016fad  mov     ebx, eax
0x180016faf  test    eax, eax
0x180016fb1  jns     short loc_180016FCB
0x180016fb3  cmp     ebx, 8007000Eh
0x180016fb9  jz      loc_180016F1F
0x180016fbf  cmp     ebx, 80070057h
0x180016fc5  jz      loc_180016ED7
0x180016fcb  test    ebx, ebx
0x180016fcd  jnz     short loc_180017016
0x180016fcf  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180016fd6  jz      short loc_18001702E
0x180016fd8  lea     r8, aCdiagnosticxml_5; "CDiagnosticXmlParser::ReadXmlBoolElemen"...
0x180016fdf  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180016fe6  call    McTemplateU0s_EventWriteTransfer
0x180016feb  jmp     short loc_18001702E
0x180016fed  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016ff4  jz      loc_180016F3B
0x180016ffa  mov     r9d, 80070057h
0x180017000  lea     r8, aCdiagnosticxml_5; "CDiagnosticXmlParser::ReadXmlBoolElemen"...
0x180017007  call    McTemplateU0sq_EventWriteTransfer
0x18001700c  jmp     loc_180016F3B
0x180017011  mov     ebx, 80070103h
0x180017016  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001701d  jz      short loc_18001702E
0x18001701f  mov     r9d, ebx
0x180017022  lea     r8, aCdiagnosticxml_5; "CDiagnosticXmlParser::ReadXmlBoolElemen"...
0x180017029  call    McTemplateU0sq_EventWriteTransfer
0x18001702e  mov     rcx, rdi; bstrString
0x180017031  call    cs:__imp_SysFreeString
0x180017037  mov     rcx, [rsp+38h+strIn]; bstrString
0x18001703c  test    rcx, rcx
0x18001703f  jz      short loc_180017050
0x180017041  call    cs:__imp_SysFreeString
0x180017047  mov     [rsp+38h+strIn], 0
0x180017050  mov     rcx, [rsp+38h+arg_18]
0x180017055  test    rcx, rcx
0x180017058  jz      short loc_180017066
0x18001705a  mov     rax, [rcx]
0x18001705d  mov     rax, [rax+10h]
0x180017061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017066  mov     rsi, [rsp+38h+arg_10]
0x18001706b  mov     eax, ebx
0x18001706d  mov     rbx, [rsp+38h+arg_0]
0x180017072  add     rsp, 30h
0x180017076  pop     rdi
0x180017077  retn
```
