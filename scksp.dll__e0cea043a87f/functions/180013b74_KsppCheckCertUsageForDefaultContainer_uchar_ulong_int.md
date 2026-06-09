# KsppCheckCertUsageForDefaultContainer(uchar *,ulong,int *)

- ea: `0x180013b74`
- end: `0x180013c8c`
- name: `?KsppCheckCertUsageForDefaultContainer@@YAKPEAEKPEAH@Z`
- size: `280`
- prototype: `unsigned int __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a59c`

## callees

- `0x18000d9d0`
- `0x180013b74`
- `0x18002b140`
- `0x18003c202`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c13`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180013bcf`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180013c09`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180013bcf`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180013c09`
- `CRYPT32!CertFreeCertificateContext` at `0x180013c6d`
- `CRYPT32!CertFreeCertificateContext` at `0x180013c6d`
- `CRYPT32!CertCreateCertificateContext` at `0x180013ba7`
- `CRYPT32!CertCreateCertificateContext` at `0x180013ba7`

## pseudocode

```c
__int64 __fastcall KsppCheckCertUsageForDefaultContainer(BYTE *pbCertEncoded, DWORD cbCertEncoded, int *a3)
{
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v5; // rbp
  DWORD LastError; // ebx
  struct _CTL_USAGE *v7; // rax
  struct _CTL_USAGE *v8; // rdi
  DWORD cUsageIdentifier; // esi
  LPSTR *rgpszUsageIdentifier; // r12
  const char *v11; // r14
  DWORD pcbUsage; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  pcbUsage = 0;
  CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
  v5 = CertificateContext;
  if ( CertificateContext )
  {
    if ( CertGetEnhancedKeyUsage(CertificateContext, 0, 0, &pcbUsage) )
    {
      v7 = (struct _CTL_USAGE *)MIDL_user_allocate(pcbUsage);
      v8 = v7;
      if ( v7 )
      {
        if ( CertGetEnhancedKeyUsage(v5, 0, v7, &pcbUsage) )
        {
          cUsageIdentifier = v8->cUsageIdentifier;
          LastError = 0;
          if ( v8->cUsageIdentifier )
          {
            rgpszUsageIdentifier = v8->rgpszUsageIdentifier;
            do
            {
              v8->cUsageIdentifier = --cUsageIdentifier;
              v11 = rgpszUsageIdentifier[cUsageIdentifier];
              if ( !strcmp_0("1.3.6.1.4.1.311.20.2.2", v11) || !strcmp_0("1.3.6.1.4.1.311.20.2.1", v11) )
                *a3 = 1;
            }
            while ( cUsageIdentifier );
          }
        }
        else
        {
          LastError = GetLastError();
        }
        CspFreeH(v8);
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CertFreeCertificateContext(v5);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180013b74  mov     [rsp+arg_0], rbx
0x180013b79  mov     [rsp+arg_8], rbp
0x180013b7e  push    rsi
0x180013b7f  push    rdi
0x180013b80  push    r12
0x180013b82  push    r14
0x180013b84  push    r15
0x180013b86  sub     rsp, 20h
0x180013b8a  mov     r15, r8
0x180013b8d  mov     dword ptr [r8], 0
0x180013b94  mov     r8d, edx; cbCertEncoded
0x180013b97  mov     [rsp+48h+pcbUsage], 0
0x180013b9f  mov     rdx, rcx; pbCertEncoded
0x180013ba2  mov     ecx, 10001h; dwCertEncodingType
0x180013ba7  call    cs:__imp_CertCreateCertificateContext
0x180013bad  mov     rbp, rax
0x180013bb0  test    rax, rax
0x180013bb3  jnz     short loc_180013BC2
0x180013bb5  call    cs:__imp_GetLastError
0x180013bbb  mov     ebx, eax
0x180013bbd  jmp     loc_180013C73
0x180013bc2  lea     r9, [rsp+48h+pcbUsage]; pcbUsage
0x180013bc7  xor     r8d, r8d; pUsage
0x180013bca  xor     edx, edx; dwFlags
0x180013bcc  mov     rcx, rbp; pCertContext
0x180013bcf  call    cs:__imp_CertGetEnhancedKeyUsage
0x180013bd5  test    eax, eax
0x180013bd7  jnz     short loc_180013BE6
0x180013bd9  call    cs:__imp_GetLastError
0x180013bdf  mov     ebx, eax
0x180013be1  jmp     loc_180013C6A
0x180013be6  mov     ecx, [rsp+48h+pcbUsage]; size
0x180013bea  call    MIDL_user_allocate
0x180013bef  mov     rdi, rax
0x180013bf2  test    rax, rax
0x180013bf5  jnz     short loc_180013BFC
0x180013bf7  lea     ebx, [rax+8]
0x180013bfa  jmp     short loc_180013C6A
0x180013bfc  lea     r9, [rsp+48h+pcbUsage]; pcbUsage
0x180013c01  mov     r8, rdi; pUsage
0x180013c04  xor     edx, edx; dwFlags
0x180013c06  mov     rcx, rbp; pCertContext
0x180013c09  call    cs:__imp_CertGetEnhancedKeyUsage
0x180013c0f  test    eax, eax
0x180013c11  jnz     short loc_180013C1D
0x180013c13  call    cs:__imp_GetLastError
0x180013c19  mov     ebx, eax
0x180013c1b  jmp     short loc_180013C62
0x180013c1d  mov     esi, [rdi]
0x180013c1f  xor     ebx, ebx
0x180013c21  test    esi, esi
0x180013c23  jz      short loc_180013C62
0x180013c25  mov     r12, [rdi+8]
0x180013c29  dec     esi
0x180013c2b  lea     rcx, Str1; "1.3.6.1.4.1.311.20.2.2"
0x180013c32  mov     [rdi], esi
0x180013c34  mov     r14, [r12+rsi*8]
0x180013c38  mov     rdx, r14; Str2
0x180013c3b  call    strcmp_0
0x180013c40  test    eax, eax
0x180013c42  jz      short loc_180013C57
0x180013c44  mov     rdx, r14; Str2
0x180013c47  lea     rcx, a1361413112021; "1.3.6.1.4.1.311.20.2.1"
0x180013c4e  call    strcmp_0
0x180013c53  test    eax, eax
0x180013c55  jnz     short loc_180013C5E
0x180013c57  mov     dword ptr [r15], 1
0x180013c5e  test    esi, esi
0x180013c60  jnz     short loc_180013C29
0x180013c62  mov     rcx, rdi
0x180013c65  call    CspFreeH
0x180013c6a  mov     rcx, rbp; pCertContext
0x180013c6d  call    cs:__imp_CertFreeCertificateContext
0x180013c73  mov     rbp, [rsp+48h+arg_8]
0x180013c78  mov     eax, ebx
0x180013c7a  mov     rbx, [rsp+48h+arg_0]
0x180013c7f  add     rsp, 20h
0x180013c83  pop     r15
0x180013c85  pop     r14
0x180013c87  pop     r12
0x180013c89  pop     rdi
0x180013c8a  pop     rsi
0x180013c8b  retn
```
