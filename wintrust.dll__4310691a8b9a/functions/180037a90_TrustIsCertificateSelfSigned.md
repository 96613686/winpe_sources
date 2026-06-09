# TrustIsCertificateSelfSigned

- ea: `0x180037a90`
- end: `0x180037af8`
- name: `TrustIsCertificateSelfSigned`
- size: `104`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pIssuer, DWORD dwCertEncodingType)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180037a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037aea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037aea`
- `CRYPT32!CertCompareCertificateName` at `0x180037ab3`
- `CRYPT32!CertCompareCertificateName` at `0x180037ab3`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x180037ad0`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x180037ad0`

## pseudocode

```c
_BOOL8 __fastcall TrustIsCertificateSelfSigned(PCCERT_CONTEXT pIssuer, DWORD dwCertEncodingType, int a3)
{
  DWORD pdwFlags; // [rsp+30h] [rbp+8h] BYREF

  if ( !pIssuer || a3 )
  {
    SetLastError(0x57u);
  }
  else if ( CertCompareCertificateName(dwCertEncodingType, &pIssuer->pCertInfo->Issuer, &pIssuer->pCertInfo->Subject) )
  {
    pdwFlags = 1;
    if ( CertVerifySubjectCertificateContext(pIssuer, pIssuer, &pdwFlags) )
      return (pdwFlags & 1) == 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180037a90  push    rbx
0x180037a92  sub     rsp, 20h
0x180037a96  mov     eax, edx
0x180037a98  mov     rbx, rcx
0x180037a9b  test    rcx, rcx
0x180037a9e  jz      short loc_180037AE5
0x180037aa0  test    r8d, r8d
0x180037aa3  jnz     short loc_180037AE5
0x180037aa5  mov     rdx, [rcx+18h]
0x180037aa9  mov     ecx, eax; dwCertEncodingType
0x180037aab  lea     r8, [rdx+50h]; pCertName2
0x180037aaf  add     rdx, 30h ; '0'; pCertName1
0x180037ab3  call    cs:__imp_CertCompareCertificateName
0x180037ab9  test    eax, eax
0x180037abb  jz      short loc_180037AF0
0x180037abd  lea     r8, [rsp+28h+pdwFlags]; pdwFlags
0x180037ac2  mov     [rsp+28h+pdwFlags], 1
0x180037aca  mov     rdx, rbx; pIssuer
0x180037acd  mov     rcx, rbx; pSubject
0x180037ad0  call    cs:__imp_CertVerifySubjectCertificateContext
0x180037ad6  test    eax, eax
0x180037ad8  jz      short loc_180037AF0
0x180037ada  mov     eax, [rsp+28h+pdwFlags]
0x180037ade  not     eax
0x180037ae0  and     eax, 1
0x180037ae3  jmp     short loc_180037AF2
0x180037ae5  mov     ecx, 57h ; 'W'; dwErrCode
0x180037aea  call    cs:__imp_SetLastError
0x180037af0  xor     eax, eax
0x180037af2  add     rsp, 20h
0x180037af6  pop     rbx
0x180037af7  retn
```
