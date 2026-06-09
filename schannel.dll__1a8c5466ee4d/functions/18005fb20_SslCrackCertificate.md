# SslCrackCertificate

- ea: `0x18005fb20`
- end: `0x18005fd9c`
- name: `SslCrackCertificate`
- size: `636`
- prototype: `BOOL __stdcall(PUCHAR pbCertificate, DWORD cbCertificate, DWORD dwFlags, PX509Certificate *ppCertificate)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180014240`
- `0x180021eb0`
- `0x180025c38`
- `0x180053df8`
- `0x18005fb20`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fbd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fbd2`
- `CRYPT32!CertFreeCertificateContext` at `0x18005fbdb`
- `CRYPT32!CertFreeCertificateContext` at `0x18005fd89`
- `CRYPT32!CertFreeCertificateContext` at `0x18005fbdb`
- `CRYPT32!CertFreeCertificateContext` at `0x18005fd89`
- `CRYPT32!CertCreateCertificateContext` at `0x18005fb97`
- `CRYPT32!CertCreateCertificateContext` at `0x18005fb97`
- `CRYPT32!CertNameToStrA` at `0x18005fbc6`
- `CRYPT32!CertNameToStrA` at `0x18005fc20`
- `CRYPT32!CertNameToStrA` at `0x18005fcb2`
- `CRYPT32!CertNameToStrA` at `0x18005fcd8`
- `CRYPT32!CertNameToStrA` at `0x18005fbc6`
- `CRYPT32!CertNameToStrA` at `0x18005fc20`
- `CRYPT32!CertNameToStrA` at `0x18005fcb2`
- `CRYPT32!CertNameToStrA` at `0x18005fcd8`

## pseudocode

```c
BOOL __stdcall SslCrackCertificate(
        PUCHAR pbCertificate,
        DWORD cbCertificate,
        DWORD dwFlags,
        PX509Certificate *ppCertificate)
{
  char v6; // si
  __int64 v8; // rcx
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v10; // rdi
  struct _X509Certificate *v11; // rbx
  DWORD v12; // ebp
  PctPublicKey *pPublicKey; // rcx
  BOOL result; // eax
  DWORD v15; // eax
  __int64 csz; // rsi
  struct _X509Certificate *v17; // rax
  size_t cbData; // r8
  PCERT_INFO pCertInfo; // rdx
  CHAR *pszIssuer; // r9
  PctPublicKey *v21; // rax
  PctPublicKey *v22; // rsi
  struct _PUBLICKEY *v23; // r8
  __int64 v24; // rdx
  int v25; // ecx
  DWORD v26; // eax
  DWORD v27; // eax
  struct _PUBLICKEY *v28; // [rsp+30h] [rbp-38h] BYREF

  v6 = dwFlags;
  if ( !(unsigned int)SchannelInit(1) )
    return 0;
  if ( (v6 & 2) != 0 )
  {
    if ( cbCertificate < 0x12 )
      return 0;
    v8 = *(_QWORD *)(pbCertificate + 4) - 0x6669747265630B04LL;
    if ( *(_QWORD *)(pbCertificate + 4) == 0x6669747265630B04LL )
    {
      v8 = *((unsigned int *)pbCertificate + 3) - 1952539497LL;
      if ( *((_DWORD *)pbCertificate + 3) == 1952539497 )
        v8 = pbCertificate[16] - 101LL;
    }
    if ( !v8 )
    {
      pbCertificate += 17;
      cbCertificate -= 17;
    }
  }
  CertificateContext = CertCreateCertificateContext(1u, pbCertificate, cbCertificate);
  v10 = CertificateContext;
  if ( !CertificateContext )
  {
    GetLastError();
    return 0;
  }
  v11 = 0;
  v12 = CertNameToStrA(
          CertificateContext->dwCertEncodingType,
          &CertificateContext->pCertInfo->Subject,
          0x20000003u,
          0,
          0);
  if ( !v12 )
    goto LABEL_12;
  v15 = CertNameToStrA(v10->dwCertEncodingType, &v10->pCertInfo->Issuer, 0x20000003u, 0, 0);
  csz = v15;
  if ( !v15 )
    goto LABEL_12;
  v17 = (struct _X509Certificate *)SPExternalAlloc(v12 + v15 + 66);
  v11 = v17;
  if ( !v17 )
    goto LABEL_13;
  v17->pPublicKey = 0;
  v17->pszSubject = (char *)&v17[1] + csz;
  cbData = 16;
  v17->pszIssuer = (PSTR)&v17[1];
  v17->Version = v10->pCertInfo->dwVersion;
  pCertInfo = v10->pCertInfo;
  if ( pCertInfo->SerialNumber.cbData <= 0x10 )
    cbData = pCertInfo->SerialNumber.cbData;
  memcpy_0(v17->SerialNumber, pCertInfo->SerialNumber.pbData, cbData);
  pszIssuer = v11->pszIssuer;
  v11->ValidFrom = v10->pCertInfo->NotBefore;
  v11->ValidUntil = v10->pCertInfo->NotAfter;
  if ( !CertNameToStrA(v10->dwCertEncodingType, &v10->pCertInfo->Issuer, 0x20000003u, pszIssuer, csz)
    || !CertNameToStrA(v10->dwCertEncodingType, &v10->pCertInfo->Subject, 0x20000003u, v11->pszSubject, v12) )
  {
LABEL_12:
    GetLastError();
    goto LABEL_13;
  }
  v28 = 0;
  v21 = (PctPublicKey *)SPExternalAlloc(0x20u);
  v11->pPublicKey = v21;
  if ( !v21
    || (v21->Type = 0,
        v11->pPublicKey->cbKey = 20,
        v22 = v11->pPublicKey,
        *(_DWORD *)v22->pKey = 826364754,
        GetPublicKeyFromCert(v10, &v28, 0)) )
  {
LABEL_13:
    CertFreeCertificateContext(v10);
    if ( v11 )
    {
      pPublicKey = v11->pPublicKey;
      if ( pPublicKey )
        SPExternalFree(pPublicKey);
      SPExternalFree(v11);
    }
    return 0;
  }
  v23 = v28;
  v24 = *(_QWORD *)v28;
  v25 = *(_DWORD *)(*(_QWORD *)v28 + 4LL);
  v22[1].Type = *(_DWORD *)(*(_QWORD *)v28 + 12LL) >> 3;
  v26 = *(_DWORD *)(v24 + 12) >> 3;
  if ( v25 == 41984 )
  {
    v22[1].cbKey = *(_DWORD *)(v24 + 12);
    *(_DWORD *)v22[1].pKey = v26 - 1;
    v27 = *(_DWORD *)(v24 + 16);
  }
  else
  {
    v22[1].cbKey = v26;
    *(_DWORD *)v22[1].pKey = (v26 >> 3) - 1;
    v27 = 0;
  }
  v22[2].Type = v27;
  SPExternalFree(v23);
  CertFreeCertificateContext(v10);
  result = 1;
  *ppCertificate = v11;
  return result;
}

```

## disassembly

```asm
0x18005fb20  push    rbx
0x18005fb22  push    rbp
0x18005fb23  push    rsi
0x18005fb24  push    rdi
0x18005fb25  push    r14
0x18005fb27  sub     rsp, 40h
0x18005fb2b  mov     rbx, rcx
0x18005fb2e  mov     r14, r9
0x18005fb31  mov     ecx, 1; int
0x18005fb36  mov     esi, r8d
0x18005fb39  mov     edi, edx
0x18005fb3b  call    ?SchannelInit@@YAHH@Z; SchannelInit(int)
0x18005fb40  test    eax, eax
0x18005fb42  jz      loc_18005FBFC
0x18005fb48  test    sil, 2
0x18005fb4c  jz      short loc_18005FB8C
0x18005fb4e  cmp     edi, 12h
0x18005fb51  jb      loc_18005FBFC
0x18005fb57  mov     rcx, [rbx+4]
0x18005fb5b  sub     rcx, cs:qword_180099710
0x18005fb62  jnz     short loc_18005FB80
0x18005fb64  mov     ecx, [rbx+0Ch]
0x18005fb67  mov     eax, cs:dword_180099718
0x18005fb6d  sub     rcx, rax
0x18005fb70  jnz     short loc_18005FB80
0x18005fb72  movzx   ecx, byte ptr [rbx+10h]
0x18005fb76  movzx   eax, cs:byte_18009971C
0x18005fb7d  sub     rcx, rax
0x18005fb80  test    rcx, rcx
0x18005fb83  jnz     short loc_18005FB8C
0x18005fb85  add     rbx, 11h
0x18005fb89  add     edi, 0FFFFFFEFh
0x18005fb8c  mov     r8d, edi; cbCertEncoded
0x18005fb8f  mov     rdx, rbx; pbCertEncoded
0x18005fb92  mov     ecx, 1; dwCertEncodingType
0x18005fb97  call    cs:__imp_CertCreateCertificateContext
0x18005fb9d  mov     rdi, rax
0x18005fba0  test    rax, rax
0x18005fba3  jnz     short loc_18005FBAD
0x18005fba5  call    cs:__imp_GetLastError
0x18005fbab  jmp     short loc_18005FBFC
0x18005fbad  mov     rdx, [rax+18h]
0x18005fbb1  xor     ebx, ebx
0x18005fbb3  mov     ecx, [rax]; dwCertEncodingType
0x18005fbb5  add     rdx, 50h ; 'P'; pName
0x18005fbb9  xor     r9d, r9d; psz
0x18005fbbc  mov     [rsp+68h+csz], ebx; csz
0x18005fbc0  mov     r8d, 20000003h; dwStrType
0x18005fbc6  call    cs:__imp_CertNameToStrA
0x18005fbcc  mov     ebp, eax
0x18005fbce  test    eax, eax
0x18005fbd0  jnz     short loc_18005FC09
0x18005fbd2  call    cs:__imp_GetLastError
0x18005fbd8  mov     rcx, rdi; pCertContext
0x18005fbdb  call    cs:__imp_CertFreeCertificateContext
0x18005fbe1  test    rbx, rbx
0x18005fbe4  jz      short loc_18005FBFC
0x18005fbe6  mov     rcx, [rbx+38h]; void *
0x18005fbea  test    rcx, rcx
0x18005fbed  jz      short loc_18005FBF4
0x18005fbef  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18005fbf4  mov     rcx, rbx; void *
0x18005fbf7  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18005fbfc  xor     eax, eax
0x18005fbfe  add     rsp, 40h
0x18005fc02  pop     r14
0x18005fc04  pop     rdi
0x18005fc05  pop     rsi
0x18005fc06  pop     rbp
0x18005fc07  pop     rbx
0x18005fc08  retn
0x18005fc09  mov     rdx, [rdi+18h]
0x18005fc0d  xor     r9d, r9d; psz
0x18005fc10  mov     ecx, [rdi]; dwCertEncodingType
0x18005fc12  add     rdx, 30h ; '0'; pName
0x18005fc16  mov     r8d, 20000003h; dwStrType
0x18005fc1c  mov     [rsp+68h+csz], ebx; csz
0x18005fc20  call    cs:__imp_CertNameToStrA
0x18005fc26  mov     esi, eax
0x18005fc28  test    eax, eax
0x18005fc2a  jz      short loc_18005FBD2
0x18005fc2c  lea     ecx, [rsi+42h]
0x18005fc2f  add     ecx, ebp; uBytes
0x18005fc31  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005fc36  mov     rbx, rax
0x18005fc39  test    rax, rax
0x18005fc3c  jz      short loc_18005FBD8
0x18005fc3e  mov     qword ptr [rax+38h], 0
0x18005fc46  lea     rcx, [rbx+40h]
0x18005fc4a  add     rcx, rsi
0x18005fc4d  add     rax, 40h ; '@'
0x18005fc51  mov     [rbx+30h], rcx
0x18005fc55  mov     r8d, 10h
0x18005fc5b  mov     [rbx+28h], rax
0x18005fc5f  mov     rax, [rdi+18h]
0x18005fc63  mov     ecx, [rax]
0x18005fc65  mov     [rbx], ecx
0x18005fc67  mov     rdx, [rdi+18h]
0x18005fc6b  cmp     [rdx+8], r8d
0x18005fc6f  ja      short loc_18005FC75
0x18005fc71  mov     r8d, [rdx+8]; Size
0x18005fc75  mov     rdx, [rdx+10h]; Src
0x18005fc79  lea     rcx, [rbx+4]; void *
0x18005fc7d  call    memcpy_0
0x18005fc82  mov     rax, [rdi+18h]
0x18005fc86  mov     r8d, 20000003h; dwStrType
0x18005fc8c  mov     r9, [rbx+28h]; psz
0x18005fc90  mov     [rsp+68h+csz], esi; csz
0x18005fc94  mov     rcx, [rax+40h]
0x18005fc98  mov     [rbx+18h], rcx
0x18005fc9c  mov     rax, [rdi+18h]
0x18005fca0  mov     rcx, [rax+48h]
0x18005fca4  mov     [rbx+20h], rcx
0x18005fca8  mov     rdx, [rdi+18h]
0x18005fcac  mov     ecx, [rdi]; dwCertEncodingType
0x18005fcae  add     rdx, 30h ; '0'; pName
0x18005fcb2  call    cs:__imp_CertNameToStrA
0x18005fcb8  test    eax, eax
0x18005fcba  jz      loc_18005FBD2
0x18005fcc0  mov     rdx, [rdi+18h]
0x18005fcc4  mov     r8d, 20000003h; dwStrType
0x18005fcca  mov     r9, [rbx+30h]; psz
0x18005fcce  add     rdx, 50h ; 'P'; pName
0x18005fcd2  mov     ecx, [rdi]; dwCertEncodingType
0x18005fcd4  mov     [rsp+68h+csz], ebp; csz
0x18005fcd8  call    cs:__imp_CertNameToStrA
0x18005fcde  test    eax, eax
0x18005fce0  jz      loc_18005FBD2
0x18005fce6  mov     ecx, 20h ; ' '; uBytes
0x18005fceb  mov     [rsp+68h+var_38], 0
0x18005fcf4  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005fcf9  mov     [rbx+38h], rax
0x18005fcfd  test    rax, rax
0x18005fd00  jz      loc_18005FBD8
0x18005fd06  mov     dword ptr [rax], 0
0x18005fd0c  lea     rdx, [rsp+68h+var_38]; struct _PUBLICKEY **
0x18005fd11  mov     rax, [rbx+38h]
0x18005fd15  xor     r8d, r8d; enum _eTlsSignatureAlgorithm *
0x18005fd18  mov     rcx, rdi; struct _CERT_CONTEXT *
0x18005fd1b  mov     dword ptr [rax+4], 14h
0x18005fd22  mov     rsi, [rbx+38h]
0x18005fd26  mov     dword ptr [rsi+8], 31415352h
0x18005fd2d  call    ?GetPublicKeyFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_PUBLICKEY@@PEAW4_eTlsSignatureAlgorithm@@@Z; GetPublicKeyFromCert(_CERT_CONTEXT const *,_PUBLICKEY * *,_eTlsSignatureAlgorithm *)
0x18005fd32  test    eax, eax
0x18005fd34  jnz     loc_18005FBD8
0x18005fd3a  mov     r8, [rsp+68h+var_38]
0x18005fd3f  mov     rdx, [r8]
0x18005fd42  mov     eax, [rdx+0Ch]
0x18005fd45  mov     ecx, [rdx+4]
0x18005fd48  shr     eax, 3
0x18005fd4b  mov     [rsi+0Ch], eax
0x18005fd4e  mov     r9d, [rdx+0Ch]
0x18005fd52  mov     eax, r9d
0x18005fd55  shr     eax, 3
0x18005fd58  cmp     ecx, 0A400h
0x18005fd5e  jnz     short loc_18005FD6E
0x18005fd60  dec     eax
0x18005fd62  mov     [rsi+10h], r9d
0x18005fd66  mov     [rsi+14h], eax
0x18005fd69  mov     eax, [rdx+10h]
0x18005fd6c  jmp     short loc_18005FD7B
0x18005fd6e  mov     [rsi+10h], eax
0x18005fd71  shr     eax, 3
0x18005fd74  dec     eax
0x18005fd76  mov     [rsi+14h], eax
0x18005fd79  xor     eax, eax
0x18005fd7b  mov     rcx, r8; void *
0x18005fd7e  mov     [rsi+18h], eax
0x18005fd81  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18005fd86  mov     rcx, rdi; pCertContext
0x18005fd89  call    cs:__imp_CertFreeCertificateContext
0x18005fd8f  mov     eax, 1
0x18005fd94  mov     [r14], rbx
0x18005fd97  jmp     loc_18005FBFE
```
