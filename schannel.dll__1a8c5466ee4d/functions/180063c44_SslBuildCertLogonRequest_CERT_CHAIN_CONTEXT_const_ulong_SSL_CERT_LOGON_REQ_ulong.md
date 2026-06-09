# SslBuildCertLogonRequest(_CERT_CHAIN_CONTEXT const *,ulong,_SSL_CERT_LOGON_REQ * *,ulong *)

- ea: `0x180063c44`
- end: `0x180063dbd`
- name: `?SslBuildCertLogonRequest@@YAJPEBU_CERT_CHAIN_CONTEXT@@KPEAPEAU_SSL_CERT_LOGON_REQ@@PEAK@Z`
- size: `377`
- prototype: `__int64 __fastcall(const struct _CERT_CHAIN_CONTEXT *, int, struct _SSL_CERT_LOGON_REQ **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180064bc8`
- `0x1800661d8`

## callees

- `0x180063c44`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063ce8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063ce8`
- `CRYPT32!CertCompareCertificateName` at `0x180063cb0`
- `CRYPT32!CertCompareCertificateName` at `0x180063cb0`

## pseudocode

```c
__int64 __fastcall SslBuildCertLogonRequest(
        const struct _CERT_CHAIN_CONTEXT *a1,
        int a2,
        struct _SSL_CERT_LOGON_REQ **a3,
        unsigned int *a4)
{
  PCERT_SIMPLE_CHAIN v5; // r14
  PCCERT_CONTEXT pCertContext; // r15
  unsigned int v7; // ebx
  __int64 i; // rdi
  DWORD *p_dwCertEncodingType; // rcx
  struct _CRYPTOAPI_BLOB **v10; // rsi
  unsigned int v12; // ebp
  struct _SSL_CERT_LOGON_REQ *v13; // rax
  struct _SSL_CERT_LOGON_REQ *v14; // rsi
  unsigned int v15; // ebx
  unsigned int v16; // r13d
  DWORD v17; // r12d
  __int64 v18; // r15
  PCCERT_CONTEXT v19; // rbx

  v5 = *a1->rgpChain;
  pCertContext = (*v5->rgpElement)->pCertContext;
  v7 = pCertContext->cbCertEncoded + 32;
  if ( pCertContext->cbCertEncoded >= 0xFFFFFFE0 )
    return 534;
  for ( i = 0; (unsigned int)i < v5->cElement; i = (unsigned int)(i + 1) )
  {
    p_dwCertEncodingType = &v5->rgpElement[i]->pCertContext->dwCertEncodingType;
    v10 = (struct _CRYPTOAPI_BLOB **)(p_dwCertEncodingType + 6);
    if ( (_DWORD)i )
    {
      if ( CertCompareCertificateName(*p_dwCertEncodingType, *v10 + 3, *v10 + 5) )
        break;
      v7 += 8;
    }
    if ( v7 + (*v10)[3].cbData < v7 )
      return 3221225621LL;
    v7 += (*v10)[3].cbData;
  }
  v12 = (v7 + 3) & 0xFFFFFFFC;
  v13 = (struct _SSL_CERT_LOGON_REQ *)LocalAlloc(0x40u, v12);
  v14 = v13;
  if ( !v13 )
    return 2148074240LL;
  *(_DWORD *)v13 = 2;
  v15 = 8 * i + 24;
  *((_DWORD *)v13 + 2) = v15;
  *((_DWORD *)v13 + 1) = v12;
  *((_DWORD *)v13 + 3) = pCertContext->cbCertEncoded;
  *((_DWORD *)v13 + 4) = a2 | 0x80;
  memcpy_0((char *)v13 + v15, pCertContext->pbCertEncoded, pCertContext->cbCertEncoded);
  v16 = 0;
  v17 = v15 + pCertContext->cbCertEncoded;
  *((_DWORD *)v14 + 5) = i;
  if ( (_DWORD)i )
  {
    v18 = 0;
    do
    {
      v19 = v5->rgpElement[v18]->pCertContext;
      *((_DWORD *)v14 + 2 * v18 + 6) = v17;
      *((_DWORD *)v14 + 2 * v18 + 7) = v19->pCertInfo->Issuer.cbData;
      memcpy_0((char *)v14 + v17, v19->pCertInfo->Issuer.pbData, v19->pCertInfo->Issuer.cbData);
      ++v16;
      ++v18;
      v17 += v19->pCertInfo->Issuer.cbData;
    }
    while ( v16 < (unsigned int)i );
  }
  *a3 = v14;
  *a4 = v12;
  return 0;
}

```

## disassembly

```asm
0x180063c44  mov     [rsp+arg_0], rbx
0x180063c49  mov     [rsp+arg_18], r9
0x180063c4e  mov     [rsp+arg_10], r8
0x180063c53  push    rbp
0x180063c54  push    rsi
0x180063c55  push    rdi
0x180063c56  push    r12
0x180063c58  push    r13
0x180063c5a  push    r14
0x180063c5c  push    r15
0x180063c5e  sub     rsp, 20h
0x180063c62  mov     rax, [rcx+10h]
0x180063c66  mov     r12d, edx
0x180063c69  mov     r14, [rax]
0x180063c6c  mov     rax, [r14+10h]
0x180063c70  mov     rcx, [rax]
0x180063c73  mov     r15, [rcx+8]
0x180063c77  mov     ebx, [r15+10h]
0x180063c7b  add     ebx, 20h ; ' '
0x180063c7e  cmp     ebx, 20h ; ' '
0x180063c81  jb      loc_180063DA3
0x180063c87  xor     edi, edi
0x180063c89  cmp     edi, [r14+0Ch]
0x180063c8d  jnb     short loc_180063CD9
0x180063c8f  mov     rax, [r14+10h]
0x180063c93  mov     rcx, [rax+rdi*8]
0x180063c97  mov     rcx, [rcx+8]
0x180063c9b  lea     rsi, [rcx+18h]
0x180063c9f  test    edi, edi
0x180063ca1  jz      short loc_180063CBD
0x180063ca3  mov     rdx, [rsi]
0x180063ca6  mov     ecx, [rcx]; dwCertEncodingType
0x180063ca8  lea     r8, [rdx+50h]; pCertName2
0x180063cac  add     rdx, 30h ; '0'; pCertName1
0x180063cb0  call    cs:__imp_CertCompareCertificateName
0x180063cb6  test    eax, eax
0x180063cb8  jnz     short loc_180063CD9
0x180063cba  add     ebx, 8
0x180063cbd  mov     rax, [rsi]
0x180063cc0  mov     eax, [rax+30h]
0x180063cc3  add     eax, ebx
0x180063cc5  cmp     eax, ebx
0x180063cc7  jb      short loc_180063CCF
0x180063cc9  mov     ebx, eax
0x180063ccb  inc     edi
0x180063ccd  jmp     short loc_180063C89
0x180063ccf  mov     eax, 0C0000095h
0x180063cd4  jmp     loc_180063DA8
0x180063cd9  lea     eax, [rbx+3]
0x180063cdc  mov     ecx, 40h ; '@'; uFlags
0x180063ce1  and     eax, 0FFFFFFFCh
0x180063ce4  mov     edx, eax; uBytes
0x180063ce6  mov     ebp, eax
0x180063ce8  call    cs:__imp_LocalAlloc
0x180063cee  mov     rsi, rax
0x180063cf1  test    rax, rax
0x180063cf4  jnz     short loc_180063D00
0x180063cf6  mov     eax, 80090300h
0x180063cfb  jmp     loc_180063DA8
0x180063d00  mov     dword ptr [rax], 2
0x180063d06  lea     ebx, ds:18h[rdi*8]
0x180063d0d  mov     [rax+8], ebx
0x180063d10  bts     r12d, 7
0x180063d15  mov     [rax+4], ebp
0x180063d18  mov     eax, [r15+10h]
0x180063d1c  mov     [rsi+0Ch], eax
0x180063d1f  mov     [rsi+10h], r12d
0x180063d23  mov     r8d, [r15+10h]; Size
0x180063d27  mov     rdx, [r15+8]; Src
0x180063d2b  mov     ecx, ebx
0x180063d2d  add     rcx, rsi; void *
0x180063d30  call    memcpy_0
0x180063d35  mov     r12d, [r15+10h]
0x180063d39  xor     r13d, r13d
0x180063d3c  add     r12d, ebx
0x180063d3f  mov     [rsi+14h], edi
0x180063d42  test    edi, edi
0x180063d44  jz      short loc_180063D90
0x180063d46  xor     r15d, r15d
0x180063d49  mov     rax, [r14+10h]
0x180063d4d  mov     rcx, [rax+r15*8]
0x180063d51  mov     rbx, [rcx+8]
0x180063d55  mov     [rsi+r15*8+18h], r12d
0x180063d5a  mov     rax, [rbx+18h]
0x180063d5e  mov     ecx, [rax+30h]
0x180063d61  mov     [rsi+r15*8+1Ch], ecx
0x180063d66  mov     rdx, [rbx+18h]
0x180063d6a  mov     ecx, r12d
0x180063d6d  add     rcx, rsi; void *
0x180063d70  mov     r8d, [rdx+30h]; Size
0x180063d74  mov     rdx, [rdx+38h]; Src
0x180063d78  call    memcpy_0
0x180063d7d  mov     rax, [rbx+18h]
0x180063d81  inc     r13d
0x180063d84  inc     r15
0x180063d87  add     r12d, [rax+30h]
0x180063d8b  cmp     r13d, edi
0x180063d8e  jb      short loc_180063D49
0x180063d90  mov     rax, [rsp+58h+arg_10]
0x180063d95  mov     [rax], rsi
0x180063d98  mov     rax, [rsp+58h+arg_18]
0x180063d9d  mov     [rax], ebp
0x180063d9f  xor     eax, eax
0x180063da1  jmp     short loc_180063DA8
0x180063da3  mov     eax, 216h
0x180063da8  mov     rbx, [rsp+58h+arg_0]
0x180063dad  add     rsp, 20h
0x180063db1  pop     r15
0x180063db3  pop     r14
0x180063db5  pop     r13
0x180063db7  pop     r12
0x180063db9  pop     rdi
0x180063dba  pop     rsi
0x180063dbb  pop     rbp
0x180063dbc  retn
```
