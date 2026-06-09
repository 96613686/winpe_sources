# CDiagnosticXmlParser::CreateInstance(IXMLDOMNode *,CDiagnosticXmlParser * *)

- ea: `0x180016c78`
- end: `0x180016e65`
- name: `?CreateInstance@CDiagnosticXmlParser@@SAJPEAUIXMLDOMNode@@PEAPEAV1@@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct CDiagnosticXmlParser **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001374c`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180016c78`
- `0x1800180ca`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016e2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180016e2a`

## string_xrefs

- `0x180016d8c`: `PackageConfiguration`
- `0x180016ce4`: `CDiagnosticXmlParser::CreateInstance`
- `0x180016dcc`: `CDiagnosticXmlParser::CreateInstance`
- `0x180016e14`: `CDiagnosticXmlParser::CreateInstance`
- `0x180016cd2`: `DiagnosticXmlParser`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::CreateInstance(struct IXMLDOMNode *a1, struct CDiagnosticXmlParser **a2)
{
  _QWORD *v2; // rdi
  int v5; // ebx
  const char *v6; // rax
  _QWORD *v7; // rax
  int v8; // eax
  __int64 v9; // r9
  __int64 *v10; // rdx
  wchar_t *String1; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v13; // [rsp+60h] [rbp+18h]

  v2 = 0;
  String1 = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return (unsigned int)v5;
    v6 = "Node";
    goto LABEL_9;
  }
  if ( !a2 )
    goto LABEL_5;
  *a2 = 0;
  v7 = operator new(0x18u);
  v13 = v7;
  v2 = v7;
  if ( !v7 )
  {
    v2 = 0;
    v5 = -2147024882;
    goto LABEL_28;
  }
  v7[1] = 0;
  *v7 = &CDiagnosticXmlParser::`vftable';
  v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, _QWORD *))a1->lpVtbl->QueryInterface)(
         a1,
         &IID_IXMLDOMNode,
         v7 + 1);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(*(_QWORD *)v2[1] + 328LL))(v2[1], &String1);
    if ( v5 >= 0 )
    {
      if ( !wcscmp_0(String1, L"DiagnosticPackage") )
      {
        v8 = 1;
      }
      else
      {
        v8 = wcscmp_0(String1, L"PackageConfiguration");
        if ( v8 )
        {
LABEL_5:
          v5 = -2147024809;
          goto LABEL_6;
        }
      }
      *((_DWORD *)v2 + 4) = v8;
      *a2 = (struct CDiagnosticXmlParser *)v2;
      goto LABEL_19;
    }
  }
  if ( v5 == -2147024882 )
  {
LABEL_28:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_31;
    v10 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_30;
  }
  if ( v5 != -2147024809 )
  {
LABEL_19:
    if ( v5 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_31;
      v9 = (unsigned int)v5;
LABEL_22:
      McTemplateU0sq_EventWriteTransfer(a1, a2, "CDiagnosticXmlParser::CreateInstance", v9);
      goto LABEL_31;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_31;
    v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_30:
    McTemplateU0s_EventWriteTransfer(a1, v10, "CDiagnosticXmlParser::CreateInstance");
    goto LABEL_31;
  }
LABEL_6:
  if ( a2 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_31;
    v9 = 2147942487LL;
    goto LABEL_22;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v6 = "DiagnosticXmlParser";
LABEL_9:
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      (unsigned int)"CDiagnosticXmlParser::CreateInstance",
      -2147024809,
      (__int64)v6);
  }
LABEL_31:
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v5 < 0 && v2 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016c78  mov     [rsp+arg_8], rbx
0x180016c7d  push    rsi
0x180016c7e  push    rdi
0x180016c7f  push    r14
0x180016c81  sub     rsp, 30h
0x180016c85  xor     edi, edi
0x180016c87  mov     rsi, rdx
0x180016c8a  mov     [rsp+48h+String1], rdi
0x180016c8f  mov     rbx, rcx
0x180016c92  test    rcx, rcx
0x180016c95  jnz     short loc_180016CB2
0x180016c97  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016c9e  mov     ebx, 80070057h
0x180016ca3  jz      loc_180016E55
0x180016ca9  lea     rax, aNode; "Node"
0x180016cb0  jmp     short loc_180016CD9
0x180016cb2  test    rsi, rsi
0x180016cb5  jnz     short loc_180016CF5
0x180016cb7  mov     ebx, 80070057h
0x180016cbc  test    rsi, rsi
0x180016cbf  jnz     loc_180016DEC
0x180016cc5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016ccc  jz      loc_180016E20
0x180016cd2  lea     rax, aDiagnosticxmlp; "DiagnosticXmlParser"
0x180016cd9  mov     r9d, 80070057h
0x180016cdf  mov     [rsp+48h+var_28], rax
0x180016ce4  lea     r8, aCdiagnosticxml_4; "CDiagnosticXmlParser::CreateInstance"
0x180016ceb  call    McTemplateU0sqs_EventWriteTransfer
0x180016cf0  jmp     loc_180016E20
0x180016cf5  mov     ecx, 18h; Size
0x180016cfa  mov     [rdx], rdi
0x180016cfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016d02  mov     [rsp+48h+arg_10], rax
0x180016d07  mov     rdi, rax
0x180016d0a  test    rax, rax
0x180016d0d  jz      loc_180016DFD
0x180016d13  mov     qword ptr [rdi+8], 0
0x180016d1b  lea     rax, ??_7CDiagnosticXmlParser@@6B@; const CDiagnosticXmlParser::`vftable'
0x180016d22  mov     [rdi], rax
0x180016d25  test    rdi, rdi
0x180016d28  jz      loc_180016DFF
0x180016d2e  mov     rax, [rbx]
0x180016d31  lea     r8, [rdi+8]
0x180016d35  lea     rdx, IID_IXMLDOMNode
0x180016d3c  mov     rcx, rbx
0x180016d3f  mov     rax, [rax]
0x180016d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d47  mov     ebx, eax
0x180016d49  test    eax, eax
0x180016d4b  js      short loc_180016DA8
0x180016d4d  mov     rcx, [rdi+8]
0x180016d51  lea     rdx, [rsp+48h+String1]
0x180016d56  mov     rax, [rcx]
0x180016d59  mov     rax, [rax+148h]
0x180016d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d65  mov     ebx, eax
0x180016d67  test    eax, eax
0x180016d69  js      short loc_180016DA8
0x180016d6b  mov     rcx, [rsp+48h+String1]; String1
0x180016d70  lea     rdx, aDiagnosticpack; "DiagnosticPackage"
0x180016d77  call    wcscmp_0
0x180016d7c  test    eax, eax
0x180016d7e  jnz     short loc_180016D87
0x180016d80  mov     eax, 1
0x180016d85  jmp     short loc_180016DA0
0x180016d87  mov     rcx, [rsp+48h+String1]; String1
0x180016d8c  lea     rdx, aPackageconfigu; "PackageConfiguration"
0x180016d93  call    wcscmp_0
0x180016d98  test    eax, eax
0x180016d9a  jnz     loc_180016CB7
0x180016da0  mov     [rdi+10h], eax
0x180016da3  mov     [rsi], rdi
0x180016da6  jmp     short loc_180016DBC
0x180016da8  cmp     ebx, 8007000Eh
0x180016dae  jz      short loc_180016E04
0x180016db0  cmp     ebx, 80070057h
0x180016db6  jz      loc_180016CBC
0x180016dbc  test    ebx, ebx
0x180016dbe  jz      short loc_180016DDA
0x180016dc0  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016dc7  jz      short loc_180016E20
0x180016dc9  mov     r9d, ebx
0x180016dcc  lea     r8, aCdiagnosticxml_4; "CDiagnosticXmlParser::CreateInstance"
0x180016dd3  call    McTemplateU0sq_EventWriteTransfer
0x180016dd8  jmp     short loc_180016E20
0x180016dda  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180016de1  jz      short loc_180016E20
0x180016de3  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180016dea  jmp     short loc_180016E14
0x180016dec  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016df3  jz      short loc_180016E20
0x180016df5  mov     r9d, 80070057h
0x180016dfb  jmp     short loc_180016DCC
0x180016dfd  xor     edi, edi
0x180016dff  mov     ebx, 8007000Eh
0x180016e04  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016e0b  jz      short loc_180016E20
0x180016e0d  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180016e14  lea     r8, aCdiagnosticxml_4; "CDiagnosticXmlParser::CreateInstance"
0x180016e1b  call    McTemplateU0s_EventWriteTransfer
0x180016e20  mov     rcx, [rsp+48h+String1]; bstrString
0x180016e25  test    rcx, rcx
0x180016e28  jz      short loc_180016E39
0x180016e2a  call    cs:__imp_SysFreeString
0x180016e30  mov     [rsp+48h+String1], 0
0x180016e39  test    ebx, ebx
0x180016e3b  jns     short loc_180016E55
0x180016e3d  test    rdi, rdi
0x180016e40  jz      short loc_180016E55
0x180016e42  mov     rax, [rdi]
0x180016e45  mov     edx, 1
0x180016e4a  mov     rcx, rdi
0x180016e4d  mov     rax, [rax]
0x180016e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e55  mov     eax, ebx
0x180016e57  mov     rbx, [rsp+48h+arg_8]
0x180016e5c  add     rsp, 30h
0x180016e60  pop     r14
0x180016e62  pop     rdi
0x180016e63  pop     rsi
0x180016e64  retn
```
