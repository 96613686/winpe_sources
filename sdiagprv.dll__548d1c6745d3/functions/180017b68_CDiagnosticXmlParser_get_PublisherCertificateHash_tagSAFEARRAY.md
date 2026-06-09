# CDiagnosticXmlParser::get_PublisherCertificateHash(tagSAFEARRAY * *)

- ea: `0x180017b68`
- end: `0x180017d29`
- name: `?get_PublisherCertificateHash@CDiagnosticXmlParser@@QEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64 this, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001374c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800026b4`
- `0x18001737c`
- `0x180017b68`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180017ce6`
- `OLEAUT32!__imp_SysFreeString` at `0x180017ce6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180017d14`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180017d14`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180017c44`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180017c44`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180017c75`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180017cfe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180017c75`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180017cfe`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180017c28`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180017c28`

## string_xrefs

- `0x180017bb7`: `CDiagnosticXmlParser::get_PublisherCertificateHash`
- `0x180017ca2`: `CDiagnosticXmlParser::get_PublisherCertificateHash`
- `0x180017cca`: `CDiagnosticXmlParser::get_PublisherCertificateHash`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::get_PublisherCertificateHash(__int64 this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *v2; // rdi
  HRESULT v4; // ebx
  __int64 v5; // rdx
  HRESULT v6; // eax
  SAFEARRAY *Vector; // rax
  __int64 v8; // r9
  ULONG cElements; // [rsp+58h] [rbp+28h] BYREF
  void *ppvData; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v2 = 0;
  bstrString = 0;
  ppvData = 0;
  cElements = 0;
  if ( a2 )
  {
    v4 = 0;
    *a2 = 0;
    if ( *(_DWORD *)(this + 16) == 1 )
    {
      v4 = CDiagnosticXmlParser::ReadXmlStringElement(
             (CDiagnosticXmlParser *)this,
             L"dcp:PublisherCertificateHash",
             &bstrString);
      if ( v4 < 0 )
        goto LABEL_15;
      v6 = SDiagPrviBase64Decode(bstrString, 0, 0, &cElements);
      this = 0x80000000LL;
      v4 = v6;
      if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024774 )
        goto LABEL_15;
      Vector = SafeArrayCreateVector(0x11u, 0, cElements);
      v2 = Vector;
      if ( !Vector )
      {
        v4 = -2147024882;
LABEL_17:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_24;
        v8 = (unsigned int)v4;
LABEL_19:
        McTemplateU0sq_EventWriteTransfer(this, v5, "CDiagnosticXmlParser::get_PublisherCertificateHash", v8);
        goto LABEL_24;
      }
      v4 = SafeArrayAccessData(Vector, &ppvData);
      if ( v4 >= 0
        && (v4 = SDiagPrviBase64Decode(bstrString, (unsigned __int8 *)ppvData, cElements, &cElements), v4 >= 0) )
      {
        if ( ppvData )
        {
          SafeArrayUnaccessData(v2);
          ppvData = 0;
        }
        *a2 = v2;
        v2 = 0;
      }
      else
      {
LABEL_15:
        if ( v4 == -2147024809 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
            goto LABEL_24;
          v8 = 2147942487LL;
          goto LABEL_19;
        }
      }
      if ( v4 )
        goto LABEL_17;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(
        this,
        SDIAGPRV_EVENT_DEBUG_SUCCESS,
        "CDiagnosticXmlParser::get_PublisherCertificateHash");
    goto LABEL_24;
  }
  v4 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    return (unsigned int)v4;
  McTemplateU0sqs_EventWriteTransfer(
    this,
    0,
    (unsigned int)"CDiagnosticXmlParser::get_PublisherCertificateHash",
    -2147024809,
    (__int64)"PublisherCertificateHash");
LABEL_24:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( ppvData )
  {
    SafeArrayUnaccessData(v2);
    ppvData = 0;
  }
  if ( v2 )
    SafeArrayDestroy(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017b68  mov     [rsp-18h+arg_0], rbx
0x180017b6d  push    rbp
0x180017b6e  push    rsi
0x180017b6f  push    rdi
0x180017b70  mov     rbp, rsp
0x180017b73  sub     rsp, 30h
0x180017b77  xor     edi, edi
0x180017b79  mov     [rbp+bstrString], 0
0x180017b81  mov     [rbp+ppvData], 0
0x180017b89  mov     rsi, rdx
0x180017b8c  mov     [rbp+cElements], 0
0x180017b93  test    rdx, rdx
0x180017b96  jnz     short loc_180017BCD
0x180017b98  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017b9f  mov     ebx, 80070057h
0x180017ba4  jz      loc_180017D1A
0x180017baa  lea     rax, aPublishercerti; "PublisherCertificateHash"
0x180017bb1  mov     r9d, 80070057h
0x180017bb7  lea     r8, aCdiagnosticxml_7; "CDiagnosticXmlParser::get_PublisherCert"...
0x180017bbe  mov     [rsp+30h+var_10], rax
0x180017bc3  call    McTemplateU0sqs_EventWriteTransfer
0x180017bc8  jmp     loc_180017CDD
0x180017bcd  xor     ebx, ebx
0x180017bcf  mov     [rdx], rbx
0x180017bd2  cmp     dword ptr [rcx+10h], 1
0x180017bd6  jnz     loc_180017CC1
0x180017bdc  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180017be0  lea     rdx, aDcpPublisherce; "dcp:PublisherCertificateHash"
0x180017be7  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x180017bec  mov     ebx, eax
0x180017bee  test    eax, eax
0x180017bf0  js      loc_180017C8A
0x180017bf6  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x180017bfa  lea     r9, [rbp+cElements]; unsigned int *
0x180017bfe  xor     r8d, r8d; unsigned int
0x180017c01  xor     edx, edx; unsigned __int8 *
0x180017c03  call    ?SDiagPrviBase64Decode@@YAJPEAGPEAEIPEAI@Z; SDiagPrviBase64Decode(ushort *,uchar *,uint,uint *)
0x180017c08  mov     ecx, 80000000h
0x180017c0d  mov     ebx, eax
0x180017c0f  add     eax, ecx
0x180017c11  test    ecx, eax
0x180017c13  jnz     short loc_180017C1D
0x180017c15  cmp     ebx, 8007007Ah
0x180017c1b  jnz     short loc_180017C8A
0x180017c1d  mov     r8d, [rbp+cElements]; cElements
0x180017c21  mov     ecx, 11h; vt
0x180017c26  xor     edx, edx; lLbound
0x180017c28  call    cs:__imp_SafeArrayCreateVector
0x180017c2e  mov     rdi, rax
0x180017c31  test    rax, rax
0x180017c34  jnz     short loc_180017C3D
0x180017c36  mov     ebx, 8007000Eh
0x180017c3b  jmp     short loc_180017C96
0x180017c3d  lea     rdx, [rbp+ppvData]; ppvData
0x180017c41  mov     rcx, rdi; psa
0x180017c44  call    cs:__imp_SafeArrayAccessData
0x180017c4a  mov     ebx, eax
0x180017c4c  test    eax, eax
0x180017c4e  js      short loc_180017C8A
0x180017c50  mov     r8d, [rbp+cElements]; unsigned int
0x180017c54  lea     r9, [rbp+cElements]; unsigned int *
0x180017c58  mov     rdx, [rbp+ppvData]; unsigned __int8 *
0x180017c5c  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x180017c60  call    ?SDiagPrviBase64Decode@@YAJPEAGPEAEIPEAI@Z; SDiagPrviBase64Decode(ushort *,uchar *,uint,uint *)
0x180017c65  mov     ebx, eax
0x180017c67  test    eax, eax
0x180017c69  js      short loc_180017C8A
0x180017c6b  cmp     [rbp+ppvData], 0
0x180017c70  jz      short loc_180017C83
0x180017c72  mov     rcx, rdi; psa
0x180017c75  call    cs:__imp_SafeArrayUnaccessData
0x180017c7b  mov     [rbp+ppvData], 0
0x180017c83  mov     [rsi], rdi
0x180017c86  xor     edi, edi
0x180017c88  jmp     short loc_180017C92
0x180017c8a  cmp     ebx, 80070057h
0x180017c90  jz      short loc_180017CB0
0x180017c92  test    ebx, ebx
0x180017c94  jz      short loc_180017CC1
0x180017c96  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017c9d  jz      short loc_180017CDD
0x180017c9f  mov     r9d, ebx
0x180017ca2  lea     r8, aCdiagnosticxml_7; "CDiagnosticXmlParser::get_PublisherCert"...
0x180017ca9  call    McTemplateU0sq_EventWriteTransfer
0x180017cae  jmp     short loc_180017CDD
0x180017cb0  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017cb7  jz      short loc_180017CDD
0x180017cb9  mov     r9d, 80070057h
0x180017cbf  jmp     short loc_180017CA2
0x180017cc1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017cc8  jz      short loc_180017CDD
0x180017cca  lea     r8, aCdiagnosticxml_7; "CDiagnosticXmlParser::get_PublisherCert"...
0x180017cd1  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017cd8  call    McTemplateU0s_EventWriteTransfer
0x180017cdd  mov     rcx, [rbp+bstrString]; bstrString
0x180017ce1  test    rcx, rcx
0x180017ce4  jz      short loc_180017CF4
0x180017ce6  call    cs:__imp_SysFreeString
0x180017cec  mov     [rbp+bstrString], 0
0x180017cf4  cmp     [rbp+ppvData], 0
0x180017cf9  jz      short loc_180017D0C
0x180017cfb  mov     rcx, rdi; psa
0x180017cfe  call    cs:__imp_SafeArrayUnaccessData
0x180017d04  mov     [rbp+ppvData], 0
0x180017d0c  test    rdi, rdi
0x180017d0f  jz      short loc_180017D1A
0x180017d11  mov     rcx, rdi; psa
0x180017d14  call    cs:__imp_SafeArrayDestroy
0x180017d1a  mov     eax, ebx
0x180017d1c  mov     rbx, [rsp+30h+arg_0]
0x180017d21  add     rsp, 30h
0x180017d25  pop     rdi
0x180017d26  pop     rsi
0x180017d27  pop     rbp
0x180017d28  retn
```
