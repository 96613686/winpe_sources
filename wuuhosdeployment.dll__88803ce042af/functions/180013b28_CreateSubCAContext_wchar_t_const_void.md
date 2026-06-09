# CreateSubCAContext(wchar_t const *,void * *)

- ea: `0x180013b28`
- end: `0x180013cce`
- name: `?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR pszString, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180013914`

## callees

- `0x180005f64`
- `0x18000956c`
- `0x18000a60c`
- `0x180013b28`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c4f`
- `CRYPT32!CryptStringToBinaryW` at `0x180013b8f`
- `CRYPT32!CryptStringToBinaryW` at `0x180013be6`
- `CRYPT32!CryptStringToBinaryW` at `0x180013b8f`
- `CRYPT32!CryptStringToBinaryW` at `0x180013be6`
- `CRYPT32!CertCreateCertificateContext` at `0x180013bfd`
- `CRYPT32!CertCreateCertificateContext` at `0x180013bfd`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180013c31`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180013c31`
- `CRYPT32!CertFreeCertificateContext` at `0x180013c93`
- `CRYPT32!CertFreeCertificateContext` at `0x180013c93`

## string_xrefs

- `0x180013c6c`: `CreateSubCAContext failed`

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
  WUTrace(0, 0, 32, 1);
LABEL_22:
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( v4 )
    CSusBaseAllocTag<942762101>::operator delete(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013b28  mov     [rsp+arg_10], rbx
0x180013b2d  mov     [rsp+arg_18], rbp
0x180013b32  push    rsi
0x180013b33  push    rdi
0x180013b34  push    r12
0x180013b36  push    r14
0x180013b38  push    r15
0x180013b3a  sub     rsp, 50h
0x180013b3e  mov     rax, cs:__security_cookie
0x180013b45  xor     rax, rsp
0x180013b48  mov     [rsp+78h+var_30], rax
0x180013b4d  xor     r12d, r12d
0x180013b50  mov     r15, rdx
0x180013b53  mov     edi, r12d
0x180013b56  mov     [rsp+78h+cbCertEncoded], r12d
0x180013b5b  mov     ebx, r12d
0x180013b5e  mov     ebp, r12d
0x180013b61  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180013b65  mov     r14, rcx
0x180013b68  inc     rsi
0x180013b6b  cmp     [rcx+rsi*2], r12w
0x180013b70  jnz     short loc_180013B68
0x180013b72  xor     r9d, r9d; pbBinary
0x180013b75  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x180013b7a  lea     rax, [rsp+78h+cbCertEncoded]
0x180013b7f  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x180013b84  mov     edx, esi; cchString
0x180013b86  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x180013b8b  lea     r8d, [r9+6]; dwFlags
0x180013b8f  call    cs:__imp_CryptStringToBinaryW
0x180013b95  test    eax, eax
0x180013b97  jnz     short loc_180013BA9
0x180013b99  call    cs:__imp_GetLastError
0x180013b9f  mov     esi, 80070000h
0x180013ba4  jmp     loc_180013C41
0x180013ba9  mov     ecx, [rsp+78h+cbCertEncoded]; unsigned __int64
0x180013bad  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x180013bb2  mov     rbx, rax
0x180013bb5  test    rax, rax
0x180013bb8  jnz     short loc_180013BC4
0x180013bba  mov     edi, 80004003h
0x180013bbf  jmp     loc_180013C6A
0x180013bc4  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x180013bc9  lea     rax, [rsp+78h+cbCertEncoded]
0x180013bce  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x180013bd3  mov     r9, rbx; pbBinary
0x180013bd6  mov     r8d, 6; dwFlags
0x180013bdc  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x180013be1  mov     edx, esi; cchString
0x180013be3  mov     rcx, r14; pszString
0x180013be6  call    cs:__imp_CryptStringToBinaryW
0x180013bec  test    eax, eax
0x180013bee  jz      short loc_180013B99
0x180013bf0  mov     r8d, [rsp+78h+cbCertEncoded]; cbCertEncoded
0x180013bf5  mov     rdx, rbx; pbCertEncoded
0x180013bf8  mov     ecx, 1; dwCertEncodingType
0x180013bfd  call    cs:__imp_CertCreateCertificateContext
0x180013c03  mov     rbp, rax
0x180013c06  mov     esi, 80070000h
0x180013c0b  test    rax, rax
0x180013c0e  jnz     short loc_180013C24
0x180013c10  call    cs:__imp_GetLastError
0x180013c16  movzx   edi, ax
0x180013c19  or      edi, esi
0x180013c1b  test    eax, eax
0x180013c1d  cmovle  edi, eax
0x180013c20  test    edi, edi
0x180013c22  js      short loc_180013C6A
0x180013c24  mov     rcx, [r15]; hCertStore
0x180013c27  xor     r9d, r9d; ppStoreContext
0x180013c2a  mov     rdx, rbp; pCertContext
0x180013c2d  lea     r8d, [r9+1]; dwAddDisposition
0x180013c31  call    cs:__imp_CertAddCertificateContextToStore
0x180013c37  test    eax, eax
0x180013c39  jnz     short loc_180013C66
0x180013c3b  call    cs:__imp_GetLastError
0x180013c41  movzx   ecx, ax
0x180013c44  or      ecx, esi
0x180013c46  test    eax, eax
0x180013c48  cmovle  ecx, eax
0x180013c4b  test    ecx, ecx
0x180013c4d  jns     short loc_180013C61
0x180013c4f  call    cs:__imp_GetLastError
0x180013c55  movzx   edi, ax
0x180013c58  or      edi, esi
0x180013c5a  test    eax, eax
0x180013c5c  cmovle  edi, eax
0x180013c5f  jmp     short loc_180013C66
0x180013c61  mov     edi, 80004005h
0x180013c66  test    edi, edi
0x180013c68  jns     short loc_180013C8B
0x180013c6a  xor     edx, edx
0x180013c6c  lea     rax, aCreatesubcacon; "CreateSubCAContext failed"
0x180013c73  mov     [rsp+78h+pdwSkip], rax
0x180013c78  xor     ecx, ecx
0x180013c7a  mov     dword ptr [rsp+78h+pcbBinary], edi
0x180013c7e  lea     r9d, [rdx+1]
0x180013c82  lea     r8d, [rdx+20h]
0x180013c86  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013c8b  test    rbp, rbp
0x180013c8e  jz      short loc_180013C99
0x180013c90  mov     rcx, rbp; pCertContext
0x180013c93  call    cs:__imp_CertFreeCertificateContext
0x180013c99  test    rbx, rbx
0x180013c9c  jz      short loc_180013CA6
0x180013c9e  mov     rcx, rbx; lpMem
0x180013ca1  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180013ca6  mov     eax, edi
0x180013ca8  mov     rcx, [rsp+78h+var_30]
0x180013cad  xor     rcx, rsp; StackCookie
0x180013cb0  call    __security_check_cookie
0x180013cb5  lea     r11, [rsp+78h+var_28]
0x180013cba  mov     rbx, [r11+40h]
0x180013cbe  mov     rbp, [r11+48h]
0x180013cc2  mov     rsp, r11
0x180013cc5  pop     r15
0x180013cc7  pop     r14
0x180013cc9  pop     r12
0x180013ccb  pop     rdi
0x180013ccc  pop     rsi
0x180013ccd  retn
```
