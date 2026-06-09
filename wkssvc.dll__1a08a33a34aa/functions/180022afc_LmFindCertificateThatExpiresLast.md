# LmFindCertificateThatExpiresLast

- ea: `0x180022afc`
- end: `0x180022bf5`
- name: `LmFindCertificateThatExpiresLast`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180022510`
- `0x180023930`

## callees

- `0x180022afc`
- `0x180022bfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022ba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022ba9`
- `CRYPT32!CertOpenStore` at `0x180022b34`
- `CRYPT32!CertOpenStore` at `0x180022b34`
- `CRYPT32!CertFindCertificateInStore` at `0x180022b7f`
- `CRYPT32!CertFindCertificateInStore` at `0x180022b7f`

## pseudocode

```c
__int64 __fastcall LmFindCertificateThatExpiresLast(const void *a1, const void *a2, _QWORD *a3)
{
  HCERTSTORE v5; // r15
  unsigned int Thumbprint; // ebx
  const CERT_CONTEXT *pPrevCertContext; // rsi
  FILETIME NotAfter; // rbp
  PCCERT_CONTEXT CertificateInStore; // rax
  PCERT_INFO pCertInfo; // rdx

  v5 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, a1);
  if ( v5 )
  {
    pPrevCertContext = 0;
    Thumbprint = 1168;
    NotAfter = 0;
    while ( 1 )
    {
      CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x80004u, a2, pPrevCertContext);
      pPrevCertContext = CertificateInStore;
      if ( !CertificateInStore )
        break;
      pCertInfo = CertificateInStore->pCertInfo;
      if ( *(_QWORD *)&pCertInfo->NotAfter > *(unsigned __int64 *)&NotAfter )
      {
        NotAfter = pCertInfo->NotAfter;
        Thumbprint = LmGetThumbprint(CertificateInStore);
        if ( Thumbprint )
          return Thumbprint;
      }
    }
    *a3 = 0;
  }
  else
  {
    return GetLastError();
  }
  return Thumbprint;
}

```

## disassembly

```asm
0x180022afc  mov     rax, rsp
0x180022aff  mov     [rax+8], rbx
0x180022b03  mov     [rax+10h], rbp
0x180022b07  push    rsi
0x180022b08  push    rdi
0x180022b09  push    r12
0x180022b0b  push    r14
0x180022b0d  push    r15
0x180022b0f  sub     rsp, 30h
0x180022b13  xor     edi, edi
0x180022b15  mov     [rax-38h], rcx
0x180022b19  mov     r14, r8
0x180022b1c  mov     [rax+20h], rdi
0x180022b20  mov     r12, rdx
0x180022b23  mov     r9d, 28000h; dwFlags
0x180022b29  xor     r8d, r8d; hCryptProv
0x180022b2c  mov     edx, 10001h; dwEncodingType
0x180022b31  lea     ecx, [rdi+0Ah]; lpszStoreProvider
0x180022b34  call    cs:__imp_CertOpenStore
0x180022b3b  nop     dword ptr [rax+rax+00h]
0x180022b40  mov     r15, rax
0x180022b43  test    rax, rax
0x180022b46  jnz     short loc_180022B5B
0x180022b48  call    cs:__imp_GetLastError
0x180022b4f  nop     dword ptr [rax+rax+00h]
0x180022b54  mov     ebx, eax
0x180022b56  jmp     loc_180022BDB
0x180022b5b  xor     esi, esi
0x180022b5d  mov     ebx, 490h
0x180022b62  xor     ebp, ebp
0x180022b64  mov     [rsp+58h+pPrevCertContext], rsi; pPrevCertContext
0x180022b69  mov     r9d, 80004h; dwFindType
0x180022b6f  xor     r8d, r8d; dwFindFlags
0x180022b72  mov     [rsp+58h+pvFindPara], r12; pvFindPara
0x180022b77  mov     edx, 10001h; dwCertEncodingType
0x180022b7c  mov     rcx, r15; hCertStore
0x180022b7f  call    cs:__imp_CertFindCertificateInStore
0x180022b86  nop     dword ptr [rax+rax+00h]
0x180022b8b  mov     rsi, rax
0x180022b8e  test    rax, rax
0x180022b91  jz      short loc_180022BD8
0x180022b93  mov     rdx, [rax+18h]
0x180022b97  cmp     [rdx+48h], rbp
0x180022b9b  jbe     short loc_180022B64
0x180022b9d  mov     rbp, [rdx+48h]
0x180022ba1  test    rdi, rdi
0x180022ba4  jz      short loc_180022BBE
0x180022ba6  mov     rcx, rdi; hMem
0x180022ba9  call    cs:__imp_LocalFree
0x180022bb0  nop     dword ptr [rax+rax+00h]
0x180022bb5  mov     [rsp+58h+arg_18], 0
0x180022bbe  lea     rdx, [rsp+58h+arg_18]
0x180022bc3  mov     rcx, rsi; pCertContext
0x180022bc6  call    LmGetThumbprint
0x180022bcb  mov     ebx, eax
0x180022bcd  test    eax, eax
0x180022bcf  jnz     short loc_180022BDB
0x180022bd1  mov     rdi, [rsp+58h+arg_18]
0x180022bd6  jmp     short loc_180022B64
0x180022bd8  mov     [r14], rdi
0x180022bdb  mov     rbp, [rsp+58h+arg_8]
0x180022be0  mov     eax, ebx
0x180022be2  mov     rbx, [rsp+58h+arg_0]
0x180022be7  add     rsp, 30h
0x180022beb  pop     r15
0x180022bed  pop     r14
0x180022bef  pop     r12
0x180022bf1  pop     rdi
0x180022bf2  pop     rsi
0x180022bf3  retn
```
