# GetCertificateFromName

- ea: `0x180003aac`
- end: `0x180003e04`
- name: `GetCertificateFromName`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180001d10`

## callees

- `0x180001a6c`
- `0x180003aac`
- `0x1800070f0`
- `0x180007408`
- `0x18000a044`
- `0x18000a110`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003c87`
- `msvcrt!_wcsicmp` at `0x180003c87`
- `CRYPT32!CertCloseStore` at `0x180003d51`
- `CRYPT32!CertCloseStore` at `0x180003d51`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003ba1`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003d35`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003ba1`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180003d35`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180003ca7`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180003ca7`
- `CRYPT32!CertOpenStore` at `0x180003b2a`
- `CRYPT32!CertOpenStore` at `0x180003b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d9e`

## string_xrefs

- `0x180003b80`: `Unable to open the certificate store...%d`

## pseudocode

```c
__int64 GetCertificateFromName()
{
  HCERTSTORE v0; // rax
  void *v1; // r15
  DWORD v2; // eax
  __int64 v3; // r8
  DWORD v4; // r14d
  const CERT_CONTEXT *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rbx
  DWORD LastError; // eax
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rbx
  DWORD v12; // eax
  __int64 v13; // r8
  __int64 v14; // r8
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v0 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20004u, L"MY");
  v1 = v0;
  if ( v0 )
  {
    v4 = 0;
    v5 = CertEnumCertificatesInStore(v0, 0);
    if ( v5 )
    {
      do
      {
        if ( (unsigned int)CertPropertyToStr(v5, 0) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v6, 0);
          }
          if ( (_QWORD)xmmword_1800146E0 )
          {
            LOWORD(v16) = 0;
            FormatRRASErrorString(&v16, L"Checking certificate:%ws ...", 0);
            ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              &v16);
          }
          if ( (unsigned __int8)IsPrivateKeyPresent(v5) )
            IsCertificateEKUServerAuth(v5);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_d(v7, 50, v9, LastError);
          }
          if ( (_QWORD)xmmword_1800146E0 )
          {
            LOWORD(v16) = 0;
            v10 = GetLastError();
            FormatRRASErrorString(&v16, L"Unable to query current cert name: %d", v10);
            ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              &v16);
          }
        }
        v5 = CertEnumCertificatesInStore(v1, v5);
      }
      while ( v5 );
      v4 = 0;
    }
    if ( !CertCloseStore(v1, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = GetLastError();
        WPP_SF_d(v11, 51, v13, v12);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v16) = 0;
        v14 = GetLastError();
        FormatRRASErrorString(&v16, L"CertCloseStore failed and returned 0x%x", v14);
        goto LABEL_33;
      }
    }
  }
  else
  {
    v2 = GetLastError();
    v4 = v2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v3, v2);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"Unable to open the certificate store...%d", v4);
LABEL_33:
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v16);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180003aac  mov     [rsp-8+arg_18], rbx
0x180003ab1  push    rbp
0x180003ab2  push    rsi
0x180003ab3  push    rdi
0x180003ab4  push    r12
0x180003ab6  push    r13
0x180003ab8  push    r14
0x180003aba  push    r15
0x180003abc  lea     rbp, [rsp-760h]
0x180003ac4  sub     rsp, 860h
0x180003acb  mov     rax, cs:__security_cookie
0x180003ad2  xor     rax, rsp
0x180003ad5  mov     [rbp+790h+var_40], rax
0x180003adc  mov     r12, r8
0x180003adf  mov     [rsp+890h+String2], rcx
0x180003ae4  mov     r13, rdx
0x180003ae7  mov     [rsp+890h+String1], 0
0x180003af0  xor     eax, eax
0x180003af2  mov     [rsp+890h+var_858], 0
0x180003afa  xor     edx, edx; Val
0x180003afc  mov     [rsp+890h+var_840], eax
0x180003b00  mov     r8d, 7FCh; Size
0x180003b06  lea     rcx, [rsp+890h+var_83C]; void *
0x180003b0b  call    memset_0
0x180003b10  xor     edx, edx; dwEncodingType
0x180003b12  lea     rax, aMy; "MY"
0x180003b19  mov     r9d, 20004h; dwFlags
0x180003b1f  mov     [rsp+890h+pvPara], rax; pvPara
0x180003b24  xor     r8d, r8d; hCryptProv
0x180003b27  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180003b2a  call    cs:__imp_CertOpenStore
0x180003b30  mov     r15, rax
0x180003b33  test    rax, rax
0x180003b36  jnz     short loc_180003B94
0x180003b38  call    cs:__imp_GetLastError
0x180003b3e  mov     r14d, eax
0x180003b41  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b48  lea     rsi, WPP_GLOBAL_Control
0x180003b4f  cmp     rcx, rsi
0x180003b52  jz      short loc_180003B70
0x180003b54  test    byte ptr [rcx+1Ch], 40h
0x180003b58  jz      short loc_180003B70
0x180003b5a  cmp     byte ptr [rcx+19h], 1
0x180003b5e  jb      short loc_180003B70
0x180003b60  mov     rcx, [rcx+10h]
0x180003b64  lea     edx, [r15+30h]
0x180003b68  mov     r9d, eax
0x180003b6b  call    WPP_SF_d
0x180003b70  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003b78  jz      loc_180003DD7
0x180003b7e  xor     eax, eax
0x180003b80  lea     rdx, aUnableToOpenTh_0; "Unable to open the certificate store..."...
0x180003b87  mov     word ptr [rsp+890h+var_840], ax
0x180003b8c  mov     r8d, r14d
0x180003b8f  jmp     loc_180003DAE
0x180003b94  xor     r14d, r14d
0x180003b97  xor     edx, edx; pPrevCertContext
0x180003b99  mov     rcx, r15; hCertStore
0x180003b9c  mov     [rsp+890h+var_854], r14d
0x180003ba1  call    cs:__imp_CertEnumCertificatesInStore
0x180003ba7  lea     rsi, WPP_GLOBAL_Control
0x180003bae  mov     rdi, rax
0x180003bb1  test    rax, rax
0x180003bb4  jz      loc_180003D4C
0x180003bba  mov     r14, [rsp+890h+String2]
0x180003bbf  lea     r9, [rsp+890h+var_858]
0x180003bc4  xor     edx, edx; dwFlags
0x180003bc6  lea     r8, [rsp+890h+String1]
0x180003bcb  mov     rcx, rdi; pCertContext
0x180003bce  call    CertPropertyToStr
0x180003bd3  test    eax, eax
0x180003bd5  jz      loc_180003CB3
0x180003bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003be2  mov     rbx, [rsp+890h+String1]
0x180003be7  cmp     rcx, rsi
0x180003bea  jz      short loc_180003C09
0x180003bec  test    byte ptr [rcx+1Ch], 40h
0x180003bf0  jz      short loc_180003C09
0x180003bf2  cmp     byte ptr [rcx+19h], 1
0x180003bf6  jb      short loc_180003C09
0x180003bf8  mov     rcx, [rcx+10h]
0x180003bfc  mov     edx, 31h ; '1'
0x180003c01  mov     r9, rbx
0x180003c04  call    WPP_SF_S
0x180003c09  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003c11  jz      short loc_180003C4D
0x180003c13  xor     eax, eax
0x180003c15  lea     rdx, aCheckingCertif; "Checking certificate:%ws ..."
0x180003c1c  mov     r8, rbx
0x180003c1f  mov     word ptr [rsp+890h+var_840], ax
0x180003c24  lea     rcx, [rsp+890h+var_840]
0x180003c29  call    FormatRRASErrorString
0x180003c2e  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003c35  lea     r8, [rsp+890h+var_840]
0x180003c3a  mov     rcx, cs:gSstpCfgEtwContext
0x180003c41  mov     rax, cs:gSstpCfgTemplateFunc
0x180003c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4d  mov     rcx, rdi
0x180003c50  call    IsPrivateKeyPresent
0x180003c55  test    al, al
0x180003c57  jz      loc_180003D2F
0x180003c5d  lea     rdx, [rsp+890h+String2]
0x180003c62  mov     dword ptr [rsp+890h+String2], 0
0x180003c6a  mov     rcx, rdi; pCertContext
0x180003c6d  call    IsCertificateEKUServerAuth
0x180003c72  mov     eax, dword ptr [rsp+890h+String2]
0x180003c76  dec     eax
0x180003c78  cmp     eax, 1
0x180003c7b  ja      loc_180003D2F
0x180003c81  mov     rdx, r14; String2
0x180003c84  mov     rcx, rbx; String1
0x180003c87  call    cs:__imp__wcsicmp
0x180003c8d  test    eax, eax
0x180003c8f  jnz     loc_180003D2F
0x180003c95  inc     dword ptr [r12]
0x180003c99  cmp     dword ptr [r12], 1
0x180003c9e  jnz     loc_180003D2F
0x180003ca4  mov     rcx, rdi; pCertContext
0x180003ca7  call    cs:__imp_CertDuplicateCertificateContext
0x180003cad  mov     [r13+0], rax
0x180003cb1  jmp     short loc_180003D2F
0x180003cb3  mov     rbx, cs:WPP_GLOBAL_Control
0x180003cba  cmp     rbx, rsi
0x180003cbd  jz      short loc_180003CE5
0x180003cbf  test    byte ptr [rbx+1Ch], 40h
0x180003cc3  jz      short loc_180003CE5
0x180003cc5  cmp     byte ptr [rbx+19h], 1
0x180003cc9  jb      short loc_180003CE5
0x180003ccb  mov     rbx, [rbx+10h]
0x180003ccf  call    cs:__imp_GetLastError
0x180003cd5  mov     edx, 32h ; '2'
0x180003cda  mov     rcx, rbx
0x180003cdd  mov     r9d, eax
0x180003ce0  call    WPP_SF_d
0x180003ce5  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003ced  jz      short loc_180003D2F
0x180003cef  xor     eax, eax
0x180003cf1  mov     word ptr [rsp+890h+var_840], ax
0x180003cf6  call    cs:__imp_GetLastError
0x180003cfc  mov     r8d, eax
0x180003cff  lea     rdx, aUnableToQueryC; "Unable to query current cert name: %d"
0x180003d06  lea     rcx, [rsp+890h+var_840]
0x180003d0b  call    FormatRRASErrorString
0x180003d10  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003d17  lea     r8, [rsp+890h+var_840]
0x180003d1c  mov     rcx, cs:gSstpCfgEtwContext
0x180003d23  mov     rax, cs:gSstpCfgTemplateFunc
0x180003d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d2f  mov     rdx, rdi; pPrevCertContext
0x180003d32  mov     rcx, r15; hCertStore
0x180003d35  call    cs:__imp_CertEnumCertificatesInStore
0x180003d3b  mov     rdi, rax
0x180003d3e  test    rax, rax
0x180003d41  jnz     loc_180003BBF
0x180003d47  mov     r14d, [rsp+890h+var_854]
0x180003d4c  xor     edx, edx; dwFlags
0x180003d4e  mov     rcx, r15; hCertStore
0x180003d51  call    cs:__imp_CertCloseStore
0x180003d57  test    eax, eax
0x180003d59  jnz     short loc_180003DD7
0x180003d5b  mov     rbx, cs:WPP_GLOBAL_Control
0x180003d62  cmp     rbx, rsi
0x180003d65  jz      short loc_180003D8D
0x180003d67  test    byte ptr [rbx+1Ch], 40h
0x180003d6b  jz      short loc_180003D8D
0x180003d6d  cmp     byte ptr [rbx+19h], 1
0x180003d71  jb      short loc_180003D8D
0x180003d73  mov     rbx, [rbx+10h]
0x180003d77  call    cs:__imp_GetLastError
0x180003d7d  mov     edx, 33h ; '3'
0x180003d82  mov     rcx, rbx
0x180003d85  mov     r9d, eax
0x180003d88  call    WPP_SF_d
0x180003d8d  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180003d95  jz      short loc_180003DD7
0x180003d97  xor     eax, eax
0x180003d99  mov     word ptr [rsp+890h+var_840], ax
0x180003d9e  call    cs:__imp_GetLastError
0x180003da4  mov     r8d, eax
0x180003da7  lea     rdx, aCertclosestore; "CertCloseStore failed and returned 0x%x"
0x180003dae  lea     rcx, [rsp+890h+var_840]
0x180003db3  call    FormatRRASErrorString
0x180003db8  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003dbf  lea     r8, [rsp+890h+var_840]
0x180003dc4  mov     rcx, cs:gSstpCfgEtwContext
0x180003dcb  mov     rax, cs:gSstpCfgTemplateFunc
0x180003dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dd7  mov     eax, r14d
0x180003dda  mov     rcx, [rbp+790h+var_40]
0x180003de1  xor     rcx, rsp; StackCookie
0x180003de4  call    __security_check_cookie
0x180003de9  mov     rbx, [rsp+890h+arg_18]
0x180003df1  add     rsp, 860h
0x180003df8  pop     r15
0x180003dfa  pop     r14
0x180003dfc  pop     r13
0x180003dfe  pop     r12
0x180003e00  pop     rdi
0x180003e01  pop     rsi
0x180003e02  pop     rbp
0x180003e03  retn
```
