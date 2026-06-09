# CXmlValidator::CreateInstance(CXmlValidator * *)

- ea: `0x180016858`
- end: `0x1800169c7`
- name: `?CreateInstance@CXmlValidator@@SAJPEAPEAV1@@Z`
- size: `367`
- prototype: `__int64 __fastcall(struct CXmlValidator **, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d748`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000d21c`
- `0x180016858`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800168ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800168ef`

## string_xrefs

- `0x18001688e`: `CXmlValidator::CreateInstance`
- `0x180016938`: `CXmlValidator::CreateInstance`
- `0x18001694f`: `CXmlValidator::CreateInstance`
- `0x180016973`: `CXmlValidator::CreateInstance`
- `0x180016991`: `CXmlValidator::CreateInstance`
- `0x180016881`: `XmlValidator`

## pseudocode

```c
__int64 __fastcall CXmlValidator::CreateInstance(struct CXmlValidator **a1, int a2)
{
  HRESULT Instance; // edi
  LPVOID *ppv; // rax
  __int64 v5; // rcx
  struct CXmlValidator *v6; // rbx
  __int64 v7; // rdx

  if ( !a1 )
  {
    Instance = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        0,
        a2,
        (unsigned int)"CXmlValidator::CreateInstance",
        -2147024809,
        (__int64)"XmlValidator");
    return (unsigned int)Instance;
  }
  *a1 = 0;
  ppv = (LPVOID *)operator new(8u);
  v6 = (struct CXmlValidator *)ppv;
  if ( !ppv )
  {
    v6 = 0;
    Instance = -2147024882;
    goto LABEL_18;
  }
  *ppv = 0;
  Instance = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v6 + 120LL))(*(_QWORD *)v6, 0xFFFFFFFFLL);
    if ( Instance >= 0 )
    {
      *a1 = v6;
      goto LABEL_10;
    }
  }
  if ( Instance == -2147024882 )
  {
LABEL_18:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    {
LABEL_21:
      if ( !v6 )
        return (unsigned int)Instance;
LABEL_22:
      CXmlValidator::`scalar deleting destructor'(v6);
      return (unsigned int)Instance;
    }
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "CXmlValidator::CreateInstance");
LABEL_20:
    if ( Instance >= 0 )
      return (unsigned int)Instance;
    goto LABEL_21;
  }
  if ( Instance == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v5, v7, "CXmlValidator::CreateInstance", 2147942487LL);
    goto LABEL_22;
  }
LABEL_10:
  if ( Instance )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v5, v7, "CXmlValidator::CreateInstance", (unsigned int)Instance);
    goto LABEL_20;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CXmlValidator::CreateInstance");
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180016858  mov     [rsp+arg_8], rbx
0x18001685d  mov     [rsp+arg_10], rsi
0x180016862  push    rdi
0x180016863  sub     rsp, 30h
0x180016867  mov     rsi, rcx
0x18001686a  test    rcx, rcx
0x18001686d  jnz     short loc_1800168A4
0x18001686f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016876  mov     edi, 80070057h
0x18001687b  jz      loc_1800169B5
0x180016881  lea     rax, aXmlvalidator; "XmlValidator"
0x180016888  mov     r9d, 80070057h
0x18001688e  lea     r8, aCxmlvalidatorC; "CXmlValidator::CreateInstance"
0x180016895  mov     [rsp+38h+ppv], rax
0x18001689a  call    McTemplateU0sqs_EventWriteTransfer
0x18001689f  jmp     loc_1800169B5
0x1800168a4  mov     qword ptr [rcx], 0
0x1800168ab  mov     ecx, 8; Size
0x1800168b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800168b5  mov     [rsp+38h+arg_0], rax
0x1800168ba  mov     rbx, rax
0x1800168bd  test    rax, rax
0x1800168c0  jz      loc_180016981
0x1800168c6  mov     qword ptr [rax], 0
0x1800168cd  test    rax, rax
0x1800168d0  jz      loc_180016983
0x1800168d6  xor     edx, edx; pUnkOuter
0x1800168d8  mov     [rsp+38h+ppv], rax; ppv
0x1800168dd  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x1800168e4  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x1800168eb  lea     r8d, [rdx+1]; dwClsContext
0x1800168ef  call    cs:__imp_CoCreateInstance
0x1800168f5  mov     edi, eax
0x1800168f7  test    eax, eax
0x1800168f9  js      short loc_180016918
0x1800168fb  mov     rcx, [rbx]
0x1800168fe  or      edx, 0FFFFFFFFh
0x180016901  mov     rax, [rcx]
0x180016904  mov     rax, [rax+78h]
0x180016908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001690d  mov     edi, eax
0x18001690f  test    eax, eax
0x180016911  js      short loc_180016918
0x180016913  mov     [rsi], rbx
0x180016916  jmp     short loc_180016928
0x180016918  cmp     edi, 8007000Eh
0x18001691e  jz      short loc_180016988
0x180016920  cmp     edi, 80070057h
0x180016926  jz      short loc_180016964
0x180016928  test    edi, edi
0x18001692a  jz      short loc_180016946
0x18001692c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016933  jz      short loc_1800169A4
0x180016935  mov     r9d, edi
0x180016938  lea     r8, aCxmlvalidatorC; "CXmlValidator::CreateInstance"
0x18001693f  call    McTemplateU0sq_EventWriteTransfer
0x180016944  jmp     short loc_1800169A4
0x180016946  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18001694d  jz      short loc_1800169B5
0x18001694f  lea     r8, aCxmlvalidatorC; "CXmlValidator::CreateInstance"
0x180016956  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18001695d  call    McTemplateU0s_EventWriteTransfer
0x180016962  jmp     short loc_1800169B5
0x180016964  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001696b  jz      short loc_1800169AD
0x18001696d  mov     r9d, 80070057h
0x180016973  lea     r8, aCxmlvalidatorC; "CXmlValidator::CreateInstance"
0x18001697a  call    McTemplateU0sq_EventWriteTransfer
0x18001697f  jmp     short loc_1800169AD
0x180016981  xor     ebx, ebx
0x180016983  mov     edi, 8007000Eh
0x180016988  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001698f  jz      short loc_1800169A8
0x180016991  lea     r8, aCxmlvalidatorC; "CXmlValidator::CreateInstance"
0x180016998  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18001699f  call    McTemplateU0s_EventWriteTransfer
0x1800169a4  test    edi, edi
0x1800169a6  jns     short loc_1800169B5
0x1800169a8  test    rbx, rbx
0x1800169ab  jz      short loc_1800169B5
0x1800169ad  mov     rcx, rbx; this
0x1800169b0  call    ??_GCXmlValidator@@QEAAPEAXI@Z; CXmlValidator::`scalar deleting destructor'(uint)
0x1800169b5  mov     rbx, [rsp+38h+arg_8]
0x1800169ba  mov     eax, edi
0x1800169bc  mov     rsi, [rsp+38h+arg_10]
0x1800169c1  add     rsp, 30h
0x1800169c5  pop     rdi
0x1800169c6  retn
```
