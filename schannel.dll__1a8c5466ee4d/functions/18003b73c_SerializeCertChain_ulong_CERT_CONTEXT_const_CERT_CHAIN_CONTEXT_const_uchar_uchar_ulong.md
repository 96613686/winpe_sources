# SerializeCertChain(ulong,_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,uchar,uchar * *,ulong *)

- ea: `0x18003b73c`
- end: `0x18003b8e9`
- name: `?SerializeCertChain@@YAKKPEBU_CERT_CONTEXT@@PEBU_CERT_CHAIN_CONTEXT@@EPEAPEAEPEAK@Z`
- size: `429`
- prototype: `unsigned int __fastcall(unsigned int, const struct _CERT_CONTEXT *, const struct _CERT_CHAIN_CONTEXT *, unsigned __int8, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a860`

## callees

- `0x180021eb0`
- `0x18003b73c`
- `0x180088a54`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x18003b812`
- `CRYPT32!CertCompareCertificateName` at `0x18003b89a`
- `CRYPT32!CertCompareCertificateName` at `0x18003b812`
- `CRYPT32!CertCompareCertificateName` at `0x18003b89a`

## pseudocode

```c
__int64 __fastcall SerializeCertChain(
        __int64 a1,
        const struct _CERT_CONTEXT *a2,
        const struct _CERT_CHAIN_CONTEXT *a3,
        char a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  DWORD v9; // edi
  unsigned __int8 *v10; // rax
  _BYTE *v11; // rcx
  __int64 v12; // rsi
  PCERT_SIMPLE_CHAIN v13; // rbp
  PCCERT_CONTEXT pCertContext; // r14
  DWORD v15; // ecx
  unsigned __int8 *v16; // rax
  _BYTE *v17; // r14
  __int64 i; // rsi
  PCCERT_CONTEXT v19; // rdi

  if ( !a6 )
    return 2148074244LL;
  if ( a3 )
  {
    v9 = 0;
    v12 = 0;
    v13 = *a3->rgpChain;
    while ( (unsigned int)v12 < v13->cElement )
    {
      pCertContext = v13->rgpElement[v12]->pCertContext;
      if ( (_DWORD)v12 )
      {
        if ( !a4
          && CertCompareCertificateName(
               pCertContext->dwCertEncodingType,
               &pCertContext->pCertInfo->Issuer,
               &pCertContext->pCertInfo->Subject) )
        {
          break;
        }
      }
      v15 = v9 + pCertContext->cbCertEncoded;
      if ( v9 > v15 )
        return 534;
      v12 = (unsigned int)(v12 + 1);
      v9 = v15 + 3;
    }
    if ( !a5 )
      goto LABEL_5;
    if ( *a5 )
    {
      if ( *a6 < v9 )
        return 2148074273LL;
    }
    else
    {
      v16 = (unsigned __int8 *)SPExternalAlloc(v9);
      *a5 = v16;
      if ( !v16 )
        return 2148074240LL;
    }
    *a6 = v9;
    v17 = *a5;
    for ( i = 0; (unsigned int)i < v13->cElement; v17 += v19->cbCertEncoded + 3 )
    {
      v19 = v13->rgpElement[i]->pCertContext;
      if ( (_DWORD)i
        && !a4
        && CertCompareCertificateName(v19->dwCertEncodingType, &v19->pCertInfo->Issuer, &v19->pCertInfo->Subject) )
      {
        break;
      }
      *v17 = BYTE2(v19->cbCertEncoded);
      v17[1] = BYTE1(v19->cbCertEncoded);
      v17[2] = v19->cbCertEncoded;
      memcpy_0(v17 + 3, v19->pbCertEncoded, v19->cbCertEncoded);
      i = (unsigned int)(i + 1);
    }
    return 0;
  }
  v9 = a2->cbCertEncoded + 3;
  if ( a5 )
  {
    if ( !*a5 )
    {
      v10 = (unsigned __int8 *)SPExternalAlloc(v9);
      *a5 = v10;
      if ( !v10 )
        return 2148074240LL;
LABEL_11:
      *a6 = v9;
      v11 = *a5;
      *v11 = BYTE2(a2->cbCertEncoded);
      v11[1] = BYTE1(a2->cbCertEncoded);
      v11[2] = a2->cbCertEncoded;
      memcpy_0(v11 + 3, a2->pbCertEncoded, a2->cbCertEncoded);
      return 0;
    }
    if ( *a6 >= v9 )
      goto LABEL_11;
    return 2148074273LL;
  }
LABEL_5:
  *a6 = v9;
  return 0;
}

```

## disassembly

```asm
0x18003b73c  push    rbx
0x18003b73e  push    rbp
0x18003b73f  push    rsi
0x18003b740  push    rdi
0x18003b741  push    r14
0x18003b743  push    r15
0x18003b745  sub     rsp, 28h
0x18003b749  mov     rbx, [rsp+58h+arg_28]
0x18003b751  mov     r15b, r9b
0x18003b754  mov     rbp, rdx
0x18003b757  test    rbx, rbx
0x18003b75a  jnz     short loc_18003B766
0x18003b75c  mov     eax, 80090304h
0x18003b761  jmp     loc_18003B8DC
0x18003b766  test    r8, r8
0x18003b769  jnz     short loc_18003B7DE
0x18003b76b  mov     edi, [rdx+10h]
0x18003b76e  mov     rsi, [rsp+58h+arg_20]
0x18003b776  add     edi, 3
0x18003b779  test    rsi, rsi
0x18003b77c  jnz     short loc_18003B785
0x18003b77e  mov     [rbx], edi
0x18003b780  jmp     loc_18003B8DA
0x18003b785  cmp     qword ptr [rsi], 0
0x18003b789  jnz     short loc_18003B7A4
0x18003b78b  mov     ecx, edi; uBytes
0x18003b78d  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18003b792  mov     [rsi], rax
0x18003b795  test    rax, rax
0x18003b798  jnz     short loc_18003B7B2
0x18003b79a  mov     eax, 80090300h
0x18003b79f  jmp     loc_18003B8DC
0x18003b7a4  cmp     [rbx], edi
0x18003b7a6  jnb     short loc_18003B7B2
0x18003b7a8  mov     eax, 80090321h
0x18003b7ad  jmp     loc_18003B8DC
0x18003b7b2  mov     [rbx], edi
0x18003b7b4  mov     rcx, [rsi]
0x18003b7b7  mov     al, [rbp+12h]
0x18003b7ba  mov     [rcx], al
0x18003b7bc  mov     al, [rbp+11h]
0x18003b7bf  mov     [rcx+1], al
0x18003b7c2  mov     al, [rbp+10h]
0x18003b7c5  mov     [rcx+2], al
0x18003b7c8  add     rcx, 3; void *
0x18003b7cc  mov     r8d, [rbp+10h]; Size
0x18003b7d0  mov     rdx, [rbp+8]; Src
0x18003b7d4  call    memcpy_0
0x18003b7d9  jmp     loc_18003B8DA
0x18003b7de  mov     rax, [r8+10h]
0x18003b7e2  xor     edi, edi
0x18003b7e4  xor     esi, esi
0x18003b7e6  mov     rbp, [rax]
0x18003b7e9  cmp     esi, [rbp+0Ch]
0x18003b7ec  jnb     short loc_18003B837
0x18003b7ee  mov     rax, [rbp+10h]
0x18003b7f2  mov     rcx, [rax+rsi*8]
0x18003b7f6  mov     r14, [rcx+8]
0x18003b7fa  test    esi, esi
0x18003b7fc  jz      short loc_18003B81C
0x18003b7fe  test    r15b, r15b
0x18003b801  jnz     short loc_18003B81C
0x18003b803  mov     rdx, [r14+18h]
0x18003b807  mov     ecx, [r14]; dwCertEncodingType
0x18003b80a  lea     r8, [rdx+50h]; pCertName2
0x18003b80e  add     rdx, 30h ; '0'; pCertName1
0x18003b812  call    cs:__imp_CertCompareCertificateName
0x18003b818  test    eax, eax
0x18003b81a  jnz     short loc_18003B837
0x18003b81c  mov     ecx, [r14+10h]
0x18003b820  add     ecx, edi
0x18003b822  cmp     edi, ecx
0x18003b824  ja      short loc_18003B82D
0x18003b826  inc     esi
0x18003b828  lea     edi, [rcx+3]
0x18003b82b  jmp     short loc_18003B7E9
0x18003b82d  mov     eax, 216h
0x18003b832  jmp     loc_18003B8DC
0x18003b837  mov     rsi, [rsp+58h+arg_20]
0x18003b83f  test    rsi, rsi
0x18003b842  jz      loc_18003B77E
0x18003b848  cmp     qword ptr [rsi], 0
0x18003b84c  jnz     short loc_18003B863
0x18003b84e  mov     ecx, edi; uBytes
0x18003b850  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18003b855  mov     [rsi], rax
0x18003b858  test    rax, rax
0x18003b85b  jz      loc_18003B79A
0x18003b861  jmp     short loc_18003B86B
0x18003b863  cmp     [rbx], edi
0x18003b865  jb      loc_18003B7A8
0x18003b86b  mov     [rbx], edi
0x18003b86d  mov     r14, [rsi]
0x18003b870  xor     esi, esi
0x18003b872  cmp     [rbp+0Ch], esi
0x18003b875  jbe     short loc_18003B8DA
0x18003b877  mov     rax, [rbp+10h]
0x18003b87b  mov     rcx, [rax+rsi*8]
0x18003b87f  mov     rdi, [rcx+8]
0x18003b883  test    esi, esi
0x18003b885  jz      short loc_18003B8A4
0x18003b887  test    r15b, r15b
0x18003b88a  jnz     short loc_18003B8A4
0x18003b88c  mov     rdx, [rdi+18h]
0x18003b890  mov     ecx, [rdi]; dwCertEncodingType
0x18003b892  lea     r8, [rdx+50h]; pCertName2
0x18003b896  add     rdx, 30h ; '0'; pCertName1
0x18003b89a  call    cs:__imp_CertCompareCertificateName
0x18003b8a0  test    eax, eax
0x18003b8a2  jnz     short loc_18003B8DA
0x18003b8a4  mov     al, [rdi+12h]
0x18003b8a7  lea     rbx, [r14+3]
0x18003b8ab  mov     [r14], al
0x18003b8ae  mov     rcx, rbx; void *
0x18003b8b1  mov     al, [rdi+11h]
0x18003b8b4  mov     [r14+1], al
0x18003b8b8  mov     al, [rdi+10h]
0x18003b8bb  mov     [r14+2], al
0x18003b8bf  mov     r8d, [rdi+10h]; Size
0x18003b8c3  mov     rdx, [rdi+8]; Src
0x18003b8c7  call    memcpy_0
0x18003b8cc  mov     r14d, [rdi+10h]
0x18003b8d0  inc     esi
0x18003b8d2  add     r14, rbx
0x18003b8d5  cmp     esi, [rbp+0Ch]
0x18003b8d8  jb      short loc_18003B877
0x18003b8da  xor     eax, eax
0x18003b8dc  add     rsp, 28h
0x18003b8e0  pop     r15
0x18003b8e2  pop     r14
0x18003b8e4  pop     rdi
0x18003b8e5  pop     rsi
0x18003b8e6  pop     rbp
0x18003b8e7  pop     rbx
0x18003b8e8  retn
```
