# TsCryptDeleteCertificate

- ea: `0x18003e520`
- end: `0x18003e5f2`
- name: `TsCryptDeleteCertificate`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003860`
- `0x18002b830`

## callees

- `0x18003e520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e5af`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18003e5c9`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18003e5c9`
- `CRYPT32!CertCloseStore` at `0x18003e5da`
- `CRYPT32!CertCloseStore` at `0x18003e5da`
- `CRYPT32!CertFindCertificateInStore` at `0x18003e5a4`
- `CRYPT32!CertFindCertificateInStore` at `0x18003e5a4`
- `CRYPT32!CertOpenStore` at `0x18003e553`
- `CRYPT32!CertOpenStore` at `0x18003e553`

## pseudocode

```c
__int64 __fastcall TsCryptDeleteCertificate(const void *a1, __int64 a2, int a3)
{
  HCERTSTORE v5; // rdi
  signed int v6; // eax
  unsigned int v7; // ebx
  const CERT_CONTEXT *CertificateInStore; // rax
  signed int LastError; // eax
  __int128 pvFindPara; // [rsp+30h] [rbp-18h] BYREF

  pvFindPara = 0;
  v5 = CertOpenStore("System", 0, 0, 0x24000u, a1);
  if ( v5 )
  {
    LODWORD(pvFindPara) = a3;
    *((_QWORD *)&pvFindPara + 1) = a2;
    CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( CertificateInStore && CertDeleteCertificateFromStore(CertificateInStore) )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CertCloseStore(v5, 0);
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x18003e520  mov     rax, rsp
0x18003e523  mov     [rax+8], rbx
0x18003e527  mov     [rax+10h], rsi
0x18003e52b  push    rdi
0x18003e52c  sub     rsp, 40h
0x18003e530  mov     ebx, r8d
0x18003e533  mov     [rax-28h], rcx
0x18003e537  mov     rsi, rdx
0x18003e53a  lea     rcx, szStoreProvider; "System"
0x18003e541  xorps   xmm0, xmm0
0x18003e544  xor     r8d, r8d; hCryptProv
0x18003e547  xor     edx, edx; dwEncodingType
0x18003e549  mov     r9d, 24000h; dwFlags
0x18003e54f  movups  xmmword ptr [rax-18h], xmm0
0x18003e553  call    cs:__imp_CertOpenStore
0x18003e559  mov     rdi, rax
0x18003e55c  test    rax, rax
0x18003e55f  jnz     short loc_18003E578
0x18003e561  call    cs:__imp_GetLastError
0x18003e567  mov     ebx, eax
0x18003e569  test    eax, eax
0x18003e56b  jle     short loc_18003E5E0
0x18003e56d  movzx   ebx, ax
0x18003e570  or      ebx, 80070000h
0x18003e576  jmp     short loc_18003E5E0
0x18003e578  mov     r9d, 10000h; dwFindType
0x18003e57e  mov     [rsp+48h+pPrevCertContext], 0; pPrevCertContext
0x18003e587  lea     rax, [rsp+48h+var_18]
0x18003e58c  mov     [rsp+48h+var_18], ebx
0x18003e590  xor     r8d, r8d; dwFindFlags
0x18003e593  mov     [rsp+48h+var_10], rsi
0x18003e598  mov     rcx, rdi; hCertStore
0x18003e59b  mov     [rsp+48h+pvFindPara], rax; pvFindPara
0x18003e5a0  lea     edx, [r9+1]; dwCertEncodingType
0x18003e5a4  call    cs:__imp_CertFindCertificateInStore
0x18003e5aa  test    rax, rax
0x18003e5ad  jnz     short loc_18003E5C6
0x18003e5af  call    cs:__imp_GetLastError
0x18003e5b5  mov     ebx, eax
0x18003e5b7  test    eax, eax
0x18003e5b9  jle     short loc_18003E5D5
0x18003e5bb  movzx   ebx, ax
0x18003e5be  or      ebx, 80070000h
0x18003e5c4  jmp     short loc_18003E5D5
0x18003e5c6  mov     rcx, rax; pCertContext
0x18003e5c9  call    cs:__imp_CertDeleteCertificateFromStore
0x18003e5cf  test    eax, eax
0x18003e5d1  jz      short loc_18003E5AF
0x18003e5d3  xor     ebx, ebx
0x18003e5d5  xor     edx, edx; dwFlags
0x18003e5d7  mov     rcx, rdi; hCertStore
0x18003e5da  call    cs:__imp_CertCloseStore
0x18003e5e0  mov     rsi, [rsp+48h+arg_8]
0x18003e5e5  mov     eax, ebx
0x18003e5e7  mov     rbx, [rsp+48h+arg_0]
0x18003e5ec  add     rsp, 40h
0x18003e5f0  pop     rdi
0x18003e5f1  retn
```
