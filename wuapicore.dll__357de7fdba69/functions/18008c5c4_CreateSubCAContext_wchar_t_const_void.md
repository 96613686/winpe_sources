# CreateSubCAContext(wchar_t const *,void * *)

- ea: `0x18008c5c4`
- end: `0x18008c76a`
- name: `?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR pszString, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18008c3b0`

## callees

- `0x1800819c0`
- `0x180081a38`
- `0x18008c5c4`
- `0x180090bc8`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c6d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c6eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c6d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c6eb`
- `CRYPT32!CertFreeCertificateContext` at `0x18008c72f`
- `CRYPT32!CertFreeCertificateContext` at `0x18008c72f`
- `CRYPT32!CertCreateCertificateContext` at `0x18008c699`
- `CRYPT32!CertCreateCertificateContext` at `0x18008c699`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18008c6cd`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18008c6cd`
- `CRYPT32!CryptStringToBinaryW` at `0x18008c62b`
- `CRYPT32!CryptStringToBinaryW` at `0x18008c682`
- `CRYPT32!CryptStringToBinaryW` at `0x18008c62b`
- `CRYPT32!CryptStringToBinaryW` at `0x18008c682`

## string_xrefs

- `0x18008c708`: `CreateSubCAContext failed`

## pseudocode

```c
__int64 __fastcall CreateSubCAContext(LPCWSTR pszString, void **a2)
{
  signed int v3; // edi
  BYTE *v4; // rbx
  const CERT_CONTEXT *CertificateContext; // rbp
  __int64 v6; // rsi
  signed int v8; // eax
  signed int LastError; // eax
  signed int v10; // ecx
  signed int v11; // eax
  DWORD *pcbBinary; // [rsp+20h] [rbp-58h]
  DWORD cbCertEncoded; // [rsp+40h] [rbp-38h] BYREF

  v3 = 0;
  cbCertEncoded = 0;
  v4 = 0;
  CertificateContext = 0;
  v6 = -1;
  do
    ++v6;
  while ( pszString[v6] );
  if ( !CryptStringToBinaryW(pszString, v6, 6u, 0, &cbCertEncoded, 0, 0) )
    goto LABEL_13;
  v4 = (BYTE *)SusAlloc(cbCertEncoded);
  if ( v4 )
  {
    if ( !CryptStringToBinaryW(pszString, v6, 6u, v4, &cbCertEncoded, 0, 0) )
    {
LABEL_13:
      LastError = GetLastError();
      v10 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v10 = LastError;
      if ( v10 >= 0 )
      {
        v3 = -2147467259;
      }
      else
      {
        v11 = GetLastError();
        v3 = (unsigned __int16)v11 | 0x80070000;
        if ( v11 <= 0 )
          v3 = v11;
      }
LABEL_20:
      if ( v3 >= 0 )
        goto LABEL_22;
      goto LABEL_21;
    }
    CertificateContext = CertCreateCertificateContext(1u, v4, cbCertEncoded);
    if ( CertificateContext )
      goto LABEL_29;
    v8 = GetLastError();
    v3 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v3 = v8;
    if ( v3 >= 0 )
    {
LABEL_29:
      if ( CertAddCertificateContextToStore(*a2, CertificateContext, 1u, 0) )
        goto LABEL_20;
      goto LABEL_13;
    }
  }
  else
  {
    v3 = -2147467261;
  }
LABEL_21:
  LODWORD(pcbBinary) = v3;
  WUTrace(0, 0, 32, 1, pcbBinary, L"CreateSubCAContext failed");
LABEL_22:
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( v4 )
    SusFree(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008c5c4  mov     [rsp+arg_10], rbx
0x18008c5c9  mov     [rsp+arg_18], rbp
0x18008c5ce  push    rsi
0x18008c5cf  push    rdi
0x18008c5d0  push    r12
0x18008c5d2  push    r14
0x18008c5d4  push    r15
0x18008c5d6  sub     rsp, 50h
0x18008c5da  mov     rax, cs:__security_cookie
0x18008c5e1  xor     rax, rsp
0x18008c5e4  mov     [rsp+78h+var_30], rax
0x18008c5e9  xor     r12d, r12d
0x18008c5ec  mov     r15, rdx
0x18008c5ef  mov     edi, r12d
0x18008c5f2  mov     [rsp+78h+cbCertEncoded], r12d
0x18008c5f7  mov     ebx, r12d
0x18008c5fa  mov     ebp, r12d
0x18008c5fd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008c601  mov     r14, rcx
0x18008c604  inc     rsi
0x18008c607  cmp     [rcx+rsi*2], r12w
0x18008c60c  jnz     short loc_18008C604
0x18008c60e  xor     r9d, r9d; pbBinary
0x18008c611  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x18008c616  lea     rax, [rsp+78h+cbCertEncoded]
0x18008c61b  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x18008c620  mov     edx, esi; cchString
0x18008c622  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x18008c627  lea     r8d, [r9+6]; dwFlags
0x18008c62b  call    cs:__imp_CryptStringToBinaryW
0x18008c631  test    eax, eax
0x18008c633  jnz     short loc_18008C645
0x18008c635  call    cs:__imp_GetLastError
0x18008c63b  mov     esi, 80070000h
0x18008c640  jmp     loc_18008C6DD
0x18008c645  mov     ecx, [rsp+78h+cbCertEncoded]; unsigned __int64
0x18008c649  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18008c64e  mov     rbx, rax
0x18008c651  test    rax, rax
0x18008c654  jnz     short loc_18008C660
0x18008c656  mov     edi, 80004003h
0x18008c65b  jmp     loc_18008C706
0x18008c660  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x18008c665  lea     rax, [rsp+78h+cbCertEncoded]
0x18008c66a  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x18008c66f  mov     r9, rbx; pbBinary
0x18008c672  mov     r8d, 6; dwFlags
0x18008c678  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x18008c67d  mov     edx, esi; cchString
0x18008c67f  mov     rcx, r14; pszString
0x18008c682  call    cs:__imp_CryptStringToBinaryW
0x18008c688  test    eax, eax
0x18008c68a  jz      short loc_18008C635
0x18008c68c  mov     r8d, [rsp+78h+cbCertEncoded]; cbCertEncoded
0x18008c691  mov     rdx, rbx; pbCertEncoded
0x18008c694  mov     ecx, 1; dwCertEncodingType
0x18008c699  call    cs:__imp_CertCreateCertificateContext
0x18008c69f  mov     rbp, rax
0x18008c6a2  mov     esi, 80070000h
0x18008c6a7  test    rax, rax
0x18008c6aa  jnz     short loc_18008C6C0
0x18008c6ac  call    cs:__imp_GetLastError
0x18008c6b2  movzx   edi, ax
0x18008c6b5  or      edi, esi
0x18008c6b7  test    eax, eax
0x18008c6b9  cmovle  edi, eax
0x18008c6bc  test    edi, edi
0x18008c6be  js      short loc_18008C706
0x18008c6c0  mov     rcx, [r15]; hCertStore
0x18008c6c3  xor     r9d, r9d; ppStoreContext
0x18008c6c6  mov     rdx, rbp; pCertContext
0x18008c6c9  lea     r8d, [r9+1]; dwAddDisposition
0x18008c6cd  call    cs:__imp_CertAddCertificateContextToStore
0x18008c6d3  test    eax, eax
0x18008c6d5  jnz     short loc_18008C702
0x18008c6d7  call    cs:__imp_GetLastError
0x18008c6dd  movzx   ecx, ax
0x18008c6e0  or      ecx, esi
0x18008c6e2  test    eax, eax
0x18008c6e4  cmovle  ecx, eax
0x18008c6e7  test    ecx, ecx
0x18008c6e9  jns     short loc_18008C6FD
0x18008c6eb  call    cs:__imp_GetLastError
0x18008c6f1  movzx   edi, ax
0x18008c6f4  or      edi, esi
0x18008c6f6  test    eax, eax
0x18008c6f8  cmovle  edi, eax
0x18008c6fb  jmp     short loc_18008C702
0x18008c6fd  mov     edi, 80004005h
0x18008c702  test    edi, edi
0x18008c704  jns     short loc_18008C727
0x18008c706  xor     edx, edx
0x18008c708  lea     rax, aCreatesubcacon; "CreateSubCAContext failed"
0x18008c70f  mov     [rsp+78h+pdwSkip], rax
0x18008c714  xor     ecx, ecx
0x18008c716  mov     dword ptr [rsp+78h+pcbBinary], edi
0x18008c71a  lea     r9d, [rdx+1]
0x18008c71e  lea     r8d, [rdx+20h]
0x18008c722  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008c727  test    rbp, rbp
0x18008c72a  jz      short loc_18008C735
0x18008c72c  mov     rcx, rbp; pCertContext
0x18008c72f  call    cs:__imp_CertFreeCertificateContext
0x18008c735  test    rbx, rbx
0x18008c738  jz      short loc_18008C742
0x18008c73a  mov     rcx, rbx; lpMem
0x18008c73d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18008c742  mov     eax, edi
0x18008c744  mov     rcx, [rsp+78h+var_30]
0x18008c749  xor     rcx, rsp; StackCookie
0x18008c74c  call    __security_check_cookie
0x18008c751  lea     r11, [rsp+78h+var_28]
0x18008c756  mov     rbx, [r11+40h]
0x18008c75a  mov     rbp, [r11+48h]
0x18008c75e  mov     rsp, r11
0x18008c761  pop     r15
0x18008c763  pop     r14
0x18008c765  pop     r12
0x18008c767  pop     rdi
0x18008c768  pop     rsi
0x18008c769  retn
```
