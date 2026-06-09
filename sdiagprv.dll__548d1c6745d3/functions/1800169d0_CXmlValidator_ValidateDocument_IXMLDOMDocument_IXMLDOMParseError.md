# CXmlValidator::ValidateDocument(IXMLDOMDocument *,IXMLDOMParseError * *)

- ea: `0x1800169d0`
- end: `0x180016bf7`
- name: `?ValidateDocument@CXmlValidator@@QEAAJPEAUIXMLDOMDocument@@PEAPEAUIXMLDOMParseError@@@Z`
- size: `551`
- prototype: `__int64 __fastcall(CXmlValidator *__hidden this, struct IXMLDOMDocument *, struct IXMLDOMParseError **)`
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
- `0x1800169d0`
- `0x180019010`

## string_xrefs

- `0x180016b30`: `CXmlValidator::ValidateDocument`
- `0x180016b7c`: `CXmlValidator::ValidateDocument`
- `0x180016b99`: `CXmlValidator::ValidateDocument`
- `0x180016b53`: `XmlDocument`

## pseudocode

```c
__int64 __fastcall CXmlValidator::ValidateDocument(
        CXmlValidator *this,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMParseError **a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, ULONG *); // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  const char *v12; // rax
  __int64 *v14; // [rsp+30h] [rbp-40h] BYREF
  struct tagVARIANT v15; // [rsp+38h] [rbp-38h] BYREF
  struct tagVARIANT v16; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  v17 = 0;
  memset(&v15, 0, sizeof(v15));
  v14 = 0;
  v8 = SDiagPrviVariantInit(&v15);
  if ( v8 >= 0 )
  {
    if ( !a2 )
    {
      v8 = -2147024809;
LABEL_21:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_30;
      v12 = "XmlDocument";
LABEL_26:
      McTemplateU0sqs_EventWriteTransfer(
        v7,
        v6,
        (unsigned int)"CXmlValidator::ValidateDocument",
        -2147024809,
        (__int64)v12);
      goto LABEL_30;
    }
    if ( !a3 )
    {
      v8 = -2147024809;
      goto LABEL_24;
    }
    *a3 = 0;
    if ( !*(_QWORD *)this )
    {
      v8 = -2147019873;
LABEL_16:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_30;
      v11 = (unsigned int)v8;
      goto LABEL_29;
    }
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, __int64 **))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IXMLDOMDocument2,
           &v14);
    if ( v8 >= 0 )
    {
      v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, ULONG *))this;
      v15.vt = 13;
      v8 = (**v9)(v9, &IID_IUnknown, (ULONG *)&v15.cyVal);
      if ( v8 >= 0 )
      {
        v10 = *v14;
        v16 = v15;
        v8 = (*(__int64 (__fastcall **)(__int64 *, struct tagVARIANT *))(v10 + 624))(v14, &v16);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v14 + 632))(v14, &v17);
          if ( v8 == 1 )
          {
            v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMParseError **))v17)(
                   v17,
                   &IID_IXMLDOMParseError,
                   a3);
            if ( v8 >= 0 )
            {
              v8 = -2147023431;
              goto LABEL_16;
            }
          }
        }
      }
    }
  }
  if ( v8 == -2147024809 )
  {
    if ( !a2 )
      goto LABEL_21;
    if ( !a3 )
    {
LABEL_24:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_30;
      v12 = "ParseError";
      goto LABEL_26;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v11 = 2147942487LL;
LABEL_29:
      McTemplateU0sq_EventWriteTransfer(v7, v6, "CXmlValidator::ValidateDocument", v11);
    }
  }
  else
  {
    if ( v8 )
      goto LABEL_16;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(v7, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CXmlValidator::ValidateDocument");
  }
LABEL_30:
  SDiagPrviVariantClear(&v15);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800169d0  mov     [rsp-18h+arg_0], rbx
0x1800169d5  mov     [rsp-18h+arg_8], rsi
0x1800169da  push    rbp
0x1800169db  push    rdi
0x1800169dc  push    r14
0x1800169de  mov     rbp, rsp
0x1800169e1  sub     rsp, 70h
0x1800169e5  xor     eax, eax
0x1800169e7  mov     r14, rcx
0x1800169ea  xorps   xmm0, xmm0
0x1800169ed  mov     qword ptr [rbp+var_38+10h], rax
0x1800169f1  lea     rcx, [rbp+var_38]; struct tagVARIANT *
0x1800169f5  mov     [rbp+arg_18], rax
0x1800169f9  movups  xmmword ptr [rbp+var_38], xmm0
0x1800169fd  mov     [rbp+var_40], rax
0x180016a01  mov     rdi, r8
0x180016a04  mov     rsi, rdx
0x180016a07  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x180016a0c  mov     ebx, eax
0x180016a0e  test    eax, eax
0x180016a10  js      loc_180016B09
0x180016a16  test    rsi, rsi
0x180016a19  jnz     short loc_180016A25
0x180016a1b  mov     ebx, 80070057h
0x180016a20  jmp     loc_180016B4A
0x180016a25  test    rdi, rdi
0x180016a28  jnz     short loc_180016A34
0x180016a2a  mov     ebx, 80070057h
0x180016a2f  jmp     loc_180016B61
0x180016a34  mov     qword ptr [rdi], 0
0x180016a3b  cmp     qword ptr [r14], 0
0x180016a3f  jnz     short loc_180016A4B
0x180016a41  mov     ebx, 8007139Fh
0x180016a46  jmp     loc_180016B15
0x180016a4b  mov     rax, [rsi]
0x180016a4e  lea     r8, [rbp+var_40]
0x180016a52  lea     rdx, IID_IXMLDOMDocument2
0x180016a59  mov     rcx, rsi
0x180016a5c  mov     rax, [rax]
0x180016a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a64  mov     ebx, eax
0x180016a66  test    eax, eax
0x180016a68  js      loc_180016B09
0x180016a6e  mov     rcx, [r14]
0x180016a71  lea     r8, [rbp+var_38+8]
0x180016a75  mov     eax, 0Dh
0x180016a7a  lea     rdx, IID_IUnknown
0x180016a81  mov     word ptr [rbp+var_38], ax
0x180016a85  mov     rax, [rcx]
0x180016a88  mov     rax, [rax]
0x180016a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a90  mov     ebx, eax
0x180016a92  test    eax, eax
0x180016a94  js      short loc_180016B09
0x180016a96  mov     rcx, [rbp+var_40]
0x180016a9a  lea     rdx, [rbp+var_20]
0x180016a9e  movups  xmm0, xmmword ptr [rbp+var_38]
0x180016aa2  movsd   xmm1, qword ptr [rbp+var_38+10h]
0x180016aa7  mov     rax, [rcx]
0x180016aaa  movaps  [rbp+var_20], xmm0
0x180016aae  movsd   [rbp+var_10], xmm1
0x180016ab3  mov     rax, [rax+270h]
0x180016aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016abf  mov     ebx, eax
0x180016ac1  test    eax, eax
0x180016ac3  js      short loc_180016B09
0x180016ac5  mov     rcx, [rbp+var_40]
0x180016ac9  lea     rdx, [rbp+arg_18]
0x180016acd  mov     rax, [rcx]
0x180016ad0  mov     rax, [rax+278h]
0x180016ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016adc  mov     ebx, eax
0x180016ade  cmp     eax, 1
0x180016ae1  jnz     short loc_180016B09
0x180016ae3  mov     rcx, [rbp+arg_18]
0x180016ae7  lea     rdx, IID_IXMLDOMParseError
0x180016aee  mov     r8, rdi
0x180016af1  mov     rax, [rcx]
0x180016af4  mov     rax, [rax]
0x180016af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016afc  mov     ebx, eax
0x180016afe  test    eax, eax
0x180016b00  js      short loc_180016B09
0x180016b02  mov     ebx, 800705B9h
0x180016b07  jmp     short loc_180016B15
0x180016b09  cmp     ebx, 80070057h
0x180016b0f  jz      short loc_180016B45
0x180016b11  test    ebx, ebx
0x180016b13  jz      short loc_180016B27
0x180016b15  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016b1c  jz      loc_180016BA5
0x180016b22  mov     r9d, ebx
0x180016b25  jmp     short loc_180016B99
0x180016b27  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180016b2e  jz      short loc_180016BA5
0x180016b30  lea     r8, aCxmlvalidatorV; "CXmlValidator::ValidateDocument"
0x180016b37  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180016b3e  call    McTemplateU0s_EventWriteTransfer
0x180016b43  jmp     short loc_180016BA5
0x180016b45  test    rsi, rsi
0x180016b48  jnz     short loc_180016B5C
0x180016b4a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016b51  jz      short loc_180016BA5
0x180016b53  lea     rax, aXmldocument; "XmlDocument"
0x180016b5a  jmp     short loc_180016B71
0x180016b5c  test    rdi, rdi
0x180016b5f  jnz     short loc_180016B8A
0x180016b61  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016b68  jz      short loc_180016BA5
0x180016b6a  lea     rax, aParseerror; "ParseError"
0x180016b71  mov     r9d, 80070057h
0x180016b77  mov     [rsp+70h+var_50], rax
0x180016b7c  lea     r8, aCxmlvalidatorV; "CXmlValidator::ValidateDocument"
0x180016b83  call    McTemplateU0sqs_EventWriteTransfer
0x180016b88  jmp     short loc_180016BA5
0x180016b8a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016b91  jz      short loc_180016BA5
0x180016b93  mov     r9d, 80070057h
0x180016b99  lea     r8, aCxmlvalidatorV; "CXmlValidator::ValidateDocument"
0x180016ba0  call    McTemplateU0sq_EventWriteTransfer
0x180016ba5  lea     rcx, [rbp+var_38]; struct tagVARIANT *
0x180016ba9  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x180016bae  mov     rcx, [rbp+arg_18]
0x180016bb2  test    rcx, rcx
0x180016bb5  jz      short loc_180016BCB
0x180016bb7  mov     rax, [rcx]
0x180016bba  mov     rax, [rax+10h]
0x180016bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bc3  mov     [rbp+arg_18], 0
0x180016bcb  mov     rcx, [rbp+var_40]
0x180016bcf  test    rcx, rcx
0x180016bd2  jz      short loc_180016BE0
0x180016bd4  mov     rax, [rcx]
0x180016bd7  mov     rax, [rax+10h]
0x180016bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016be0  lea     r11, [rsp+70h+var_s0]
0x180016be5  mov     eax, ebx
0x180016be7  mov     rbx, [r11+20h]
0x180016beb  mov     rsi, [r11+28h]
0x180016bef  mov     rsp, r11
0x180016bf2  pop     r14
0x180016bf4  pop     rdi
0x180016bf5  pop     rbp
0x180016bf6  retn
```
