# CXmlValidator::AddSchema(ushort const *,IXMLDOMDocument *)

- ea: `0x1800166e4`
- end: `0x180016851`
- name: `?AddSchema@CXmlValidator@@QEAAJPEBGPEAUIXMLDOMDocument@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64 **this, const unsigned __int16 *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d748`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800032ec`
- `0x18000331c`
- `0x1800166e4`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016768`
- `OLEAUT32!__imp_SysAllocString` at `0x180016768`
- `OLEAUT32!__imp_SysFreeString` at `0x18001683f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001683f`

## string_xrefs

- `0x180016761`: `http://diagnostics.microsoft.com/2007/08/DiagnosticPackageCatalog`
- `0x1800167cf`: `CXmlValidator::AddSchema`
- `0x1800167ff`: `CXmlValidator::AddSchema`
- `0x180016821`: `CXmlValidator::AddSchema`

## pseudocode

```c
__int64 __fastcall CXmlValidator::AddSchema(__int64 **this, const unsigned __int16 *a2, struct IXMLDOMDocument *a3)
{
  OLECHAR *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  BSTR v9; // rax
  __int64 *v10; // rcx
  BSTR v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r9
  struct tagVARIANT v15; // [rsp+30h] [rbp-68h] BYREF
  struct tagVARIANT v16; // [rsp+50h] [rbp-48h] BYREF

  memset(&v15, 0, sizeof(v15));
  v5 = 0;
  v8 = SDiagPrviVariantInit(&v15);
  if ( v8 >= 0 )
  {
    if ( !a3 )
    {
      v8 = -2147024809;
      goto LABEL_17;
    }
    if ( !*this )
    {
      v8 = -2147019873;
      goto LABEL_12;
    }
    v15.vt = 13;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, ULONG *))a3->lpVtbl->QueryInterface)(
           a3,
           &IID_IUnknown,
           &v15.decVal.Lo32);
    if ( v8 >= 0 )
    {
      v9 = SysAllocString(L"http://diagnostics.microsoft.com/2007/08/DiagnosticPackageCatalog");
      v5 = v9;
      if ( !v9 )
      {
        v8 = -2147024882;
        goto LABEL_12;
      }
      v10 = *this;
      v11 = v9;
      v12 = **this;
      v16 = v15;
      v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR, struct tagVARIANT *))(v12 + 56))(v10, v11, &v16);
    }
  }
  if ( v8 == -2147024809 )
  {
    if ( !a3 )
    {
LABEL_17:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sqs_EventWriteTransfer(
          v7,
          v6,
          (unsigned int)"CXmlValidator::AddSchema",
          -2147024809,
          (__int64)"XsdDocument");
      goto LABEL_22;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_22;
    v13 = 2147942487LL;
LABEL_21:
    McTemplateU0sq_EventWriteTransfer(v7, v6, "CXmlValidator::AddSchema", v13);
    goto LABEL_22;
  }
  if ( v8 )
  {
LABEL_12:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_22;
    v13 = (unsigned int)v8;
    goto LABEL_21;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v7, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CXmlValidator::AddSchema");
LABEL_22:
  SDiagPrviVariantClear(&v15);
  if ( v5 )
    SysFreeString(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800166e4  push    rbx
0x1800166e6  push    rsi
0x1800166e7  push    rdi
0x1800166e8  push    r14
0x1800166ea  sub     rsp, 78h
0x1800166ee  mov     r14, rcx
0x1800166f1  xorps   xmm0, xmm0
0x1800166f4  xor     eax, eax
0x1800166f6  lea     rcx, [rsp+98h+var_68]; struct tagVARIANT *
0x1800166fb  movups  xmmword ptr [rsp+98h+var_68], xmm0
0x180016700  mov     qword ptr [rsp+98h+var_68+10h], rax
0x180016705  mov     rsi, r8
0x180016708  xor     edi, edi
0x18001670a  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x18001670f  mov     ebx, eax
0x180016711  test    eax, eax
0x180016713  js      loc_1800167AC
0x180016719  test    rsi, rsi
0x18001671c  jnz     short loc_180016728
0x18001671e  mov     ebx, 80070057h
0x180016723  jmp     loc_1800167E9
0x180016728  cmp     [r14], rdi
0x18001672b  jnz     short loc_180016737
0x18001672d  mov     ebx, 8007139Fh
0x180016732  jmp     loc_1800167B8
0x180016737  mov     eax, 0Dh
0x18001673c  lea     r8, [rsp+98h+var_68+8]
0x180016741  mov     word ptr [rsp+98h+var_68], ax
0x180016746  lea     rdx, IID_IUnknown
0x18001674d  mov     rax, [rsi]
0x180016750  mov     rcx, rsi
0x180016753  mov     rax, [rax]
0x180016756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001675b  mov     ebx, eax
0x18001675d  test    eax, eax
0x18001675f  js      short loc_1800167AC
0x180016761  lea     rcx, aHttpDiagnostic; "http://diagnostics.microsoft.com/2007/0"...
0x180016768  call    cs:__imp_SysAllocString
0x18001676e  mov     rdi, rax
0x180016771  test    rax, rax
0x180016774  jnz     short loc_18001677D
0x180016776  mov     ebx, 8007000Eh
0x18001677b  jmp     short loc_1800167B8
0x18001677d  mov     rcx, [r14]
0x180016780  lea     r8, [rsp+98h+var_48]
0x180016785  movups  xmm0, xmmword ptr [rsp+98h+var_68]
0x18001678a  mov     rdx, rdi
0x18001678d  movsd   xmm1, qword ptr [rsp+98h+var_68+10h]
0x180016793  mov     rax, [rcx]
0x180016796  movaps  [rsp+98h+var_48], xmm0
0x18001679b  movsd   [rsp+98h+var_38], xmm1
0x1800167a1  mov     rax, [rax+38h]
0x1800167a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167aa  mov     ebx, eax
0x1800167ac  cmp     ebx, 80070057h
0x1800167b2  jz      short loc_1800167E4
0x1800167b4  test    ebx, ebx
0x1800167b6  jz      short loc_1800167C6
0x1800167b8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800167bf  jz      short loc_18001682D
0x1800167c1  mov     r9d, ebx
0x1800167c4  jmp     short loc_180016821
0x1800167c6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800167cd  jz      short loc_18001682D
0x1800167cf  lea     r8, aCxmlvalidatorA; "CXmlValidator::AddSchema"
0x1800167d6  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800167dd  call    McTemplateU0s_EventWriteTransfer
0x1800167e2  jmp     short loc_18001682D
0x1800167e4  test    rsi, rsi
0x1800167e7  jnz     short loc_180016812
0x1800167e9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800167f0  jz      short loc_18001682D
0x1800167f2  lea     rax, aXsddocument; "XsdDocument"
0x1800167f9  mov     r9d, 80070057h
0x1800167ff  lea     r8, aCxmlvalidatorA; "CXmlValidator::AddSchema"
0x180016806  mov     [rsp+98h+var_78], rax
0x18001680b  call    McTemplateU0sqs_EventWriteTransfer
0x180016810  jmp     short loc_18001682D
0x180016812  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016819  jz      short loc_18001682D
0x18001681b  mov     r9d, 80070057h
0x180016821  lea     r8, aCxmlvalidatorA; "CXmlValidator::AddSchema"
0x180016828  call    McTemplateU0sq_EventWriteTransfer
0x18001682d  lea     rcx, [rsp+98h+var_68]; struct tagVARIANT *
0x180016832  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x180016837  test    rdi, rdi
0x18001683a  jz      short loc_180016845
0x18001683c  mov     rcx, rdi; bstrString
0x18001683f  call    cs:__imp_SysFreeString
0x180016845  mov     eax, ebx
0x180016847  add     rsp, 78h
0x18001684b  pop     r14
0x18001684d  pop     rdi
0x18001684e  pop     rsi
0x18001684f  pop     rbx
0x180016850  retn
```
