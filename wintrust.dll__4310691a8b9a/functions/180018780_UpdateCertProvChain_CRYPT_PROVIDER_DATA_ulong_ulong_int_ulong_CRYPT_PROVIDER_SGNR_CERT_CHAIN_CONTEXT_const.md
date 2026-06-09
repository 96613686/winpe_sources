# UpdateCertProvChain(_CRYPT_PROVIDER_DATA *,ulong,ulong *,int,ulong,_CRYPT_PROVIDER_SGNR *,_CERT_CHAIN_CONTEXT const *)

- ea: `0x180018780`
- end: `0x180018bf7`
- name: `?UpdateCertProvChain@@YAHPEAU_CRYPT_PROVIDER_DATA@@KPEAKHKPEAU_CRYPT_PROVIDER_SGNR@@PEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `1143`
- prototype: `__int64 __usercall@<rax>(struct _CRYPT_PROVIDER_DATA *@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, int@<r9d>, unsigned int, struct _CRYPT_PROVIDER_SGNR *, const struct _CERT_CHAIN_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017c20`
- `0x180018090`

## callees

- `0x180018780`
- `0x1800191c0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b97`
- `CRYPT32!CertComparePublicKeyInfo` at `0x1800189c5`
- `CRYPT32!CertComparePublicKeyInfo` at `0x1800189c5`

## pseudocode

```c
__int64 __fastcall UpdateCertProvChain(
        struct _CRYPT_PROVIDER_DATA *a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned int a5,
        struct _CRYPT_PROVIDER_SGNR *a6,
        const struct _CERT_CHAIN_CONTEXT *a7)
{
  const struct _CERT_CHAIN_CONTEXT *v7; // r8
  DWORD v8; // ebx
  __int64 v9; // r12
  unsigned int v10; // r11d
  struct _CRYPT_PROVIDER_FUNCTIONS **p_psPfns; // rdi
  __int64 v13; // rsi
  PCERT_SIMPLE_CHAIN v14; // rbp
  struct _CERT_CHAIN_ELEMENT *v15; // r14
  DWORD dwInfoStatus; // r9d
  DWORD dwErrorStatus; // r15d
  struct _CRYPT_PROVIDER_CERT *v18; // rdi
  int v19; // ecx
  BOOL v20; // eax
  DWORD dwConfidence; // edx
  int v22; // edx
  int v23; // r9d
  PCERT_REVOCATION_INFO pRevocationInfo; // rax
  PFN_PROVIDER_CERTCHKPOLICY_CALL pfnCertCheckPolicy; // rax
  __int64 i; // rbx
  PCERT_TRUST_LIST_INFO pTrustListInfo; // rax
  const CTL_CONTEXT *pCtlContext; // rcx
  DWORD v30; // eax
  int v31; // [rsp+30h] [rbp-48h]
  char v32; // [rsp+34h] [rbp-44h]

  v7 = a7;
  v8 = 0;
  v9 = 0;
  v31 = 0;
  v10 = a4;
LABEL_2:
  if ( (unsigned int)v9 < v7->cChain )
  {
    p_psPfns = &a1->psPfns;
    v13 = 0;
    v14 = v7->rgpChain[v9];
    while ( 1 )
    {
      if ( (unsigned int)v13 >= v14->cElement )
      {
        v9 = (unsigned int)(v9 + 1);
        goto LABEL_2;
      }
      v15 = v14->rgpElement[v13];
      dwInfoStatus = v15->TrustStatus.dwInfoStatus;
      dwErrorStatus = v15->TrustStatus.dwErrorStatus;
      v32 = dwInfoStatus;
      if ( (_DWORD)v9 || (_DWORD)v13 )
      {
        if ( !((unsigned int (__fastcall *)(struct _CRYPT_PROVIDER_DATA *, _QWORD, _QWORD, _QWORD, PCCERT_CONTEXT))(*p_psPfns)->pfnAddCert2Chain)(
                a1,
                a2,
                v10,
                a5,
                v15->pCertContext) )
        {
          a1->dwError = GetLastError();
          v8 = -2146869247;
          goto LABEL_39;
        }
        LOBYTE(dwInfoStatus) = v32;
        v7 = a7;
      }
      v18 = &a6->pasCertChain[a6->csCertChain - 1];
      v18->pChainElement = v15;
      if ( (dwInfoStatus & 8) == 0 || (dwErrorStatus & 8) != 0 )
        break;
      v18->fSelfSigned = 1;
      v19 = 1;
      if ( (_DWORD)v9 != v7->cChain - 1 || (_DWORD)v13 != v14->cElement - 1 || (dwErrorStatus & 0x20) != 0 )
        goto LABEL_11;
      v18->fTrustedRoot = 1;
LABEL_33:
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= 3 )
        {
          v8 = v31;
          LOBYTE(dwInfoStatus) = v32;
          goto LABEL_12;
        }
        if ( CertComparePublicKeyInfo(
               a1->dwEncoding,
               &v18->pCert->pCertInfo->SubjectPublicKeyInfo,
               (PCERT_PUBLIC_KEY_INFO)&(&off_180069030)[6 * i]) )
        {
          break;
        }
      }
      v8 = v31;
      LOBYTE(dwInfoStatus) = v32;
      v18->fTestCert = 1;
      if ( (a1->dwRegPolicySettings & 0x20) != 0 )
        v18->fTrustedRoot = 1;
LABEL_12:
      v20 = (_DWORD)v9 && !(_DWORD)v13;
      dwConfidence = v18->dwConfidence;
      v18->fTrustListSignerCert = v20;
      v18->fIsCyclic = (dwErrorStatus >> 7) & 1;
      if ( (dwErrorStatus & 8) == 0 )
        dwConfidence |= 0x10000000u;
      if ( (dwErrorStatus & 1) == 0 )
        dwConfidence |= 0x1000000u;
      v22 = dwConfidence | 0x100000;
      v18->dwConfidence = v22;
      v23 = dwInfoStatus & 1;
      if ( v23 )
      {
        v22 |= 0x10000u;
        v18->dwConfidence = v22;
      }
      if ( (dwErrorStatus & 8) == 0 && v23 )
        v18->dwConfidence = v22 | 0x1000;
      pRevocationInfo = v15->pRevocationInfo;
      if ( pRevocationInfo )
        v18->dwRevokedReason = pRevocationInfo->dwRevocationResult;
      if ( (dwErrorStatus & 8) != 0 )
      {
        if ( (dwErrorStatus & 0x100000) == 0 || (v8 = -2146893816, (a1->dwProvFlags & 0x2000) == 0) )
          v8 = -2146869244;
        v18->dwError = v8;
        goto LABEL_60;
      }
      if ( (dwErrorStatus & 4) != 0 )
      {
        v18->dwError = -2146762484;
        if ( !v8 )
        {
          v8 = -2146762484;
LABEL_60:
          v31 = v8;
        }
      }
      if ( (_DWORD)v13 == v14->cElement - 1 )
      {
        pTrustListInfo = v14->pTrustListInfo;
        if ( pTrustListInfo )
        {
          pCtlContext = pTrustListInfo->pCtlContext;
          if ( pCtlContext )
          {
            v30 = v14->TrustStatus.dwErrorStatus;
            v18->pCtlContext = pCtlContext;
            if ( (v30 & 0x40000) != 0 )
            {
              v8 = -2146869244;
              v18->dwCtlError = -2146869244;
              v31 = -2146869244;
            }
            else if ( (v30 & 0x20000) != 0 )
            {
              if ( (a1->dwRegPolicySettings & 0x100) == 0 )
                v18->dwCtlError = -2146762495;
            }
            else if ( (v30 & 0x80000) != 0 )
            {
              v18->dwCtlError = -2146762480;
            }
          }
        }
      }
      p_psPfns = &a1->psPfns;
      pfnCertCheckPolicy = a1->psPfns->pfnCertCheckPolicy;
      if ( pfnCertCheckPolicy
        && !((unsigned int (__fastcall *)(struct _CRYPT_PROVIDER_DATA *, _QWORD, _QWORD, _QWORD))pfnCertCheckPolicy)(
              a1,
              a2,
              a4,
              a5) )
      {
        goto LABEL_39;
      }
      v7 = a7;
      v10 = a4;
      v13 = (unsigned int)(v13 + 1);
    }
    v19 = 0;
    v18->fSelfSigned = 0;
LABEL_11:
    v18->fTrustedRoot = 0;
    if ( !v19 )
      goto LABEL_12;
    goto LABEL_33;
  }
LABEL_39:
  if ( v8 == -2146762484 )
  {
    if ( !(unsigned int)_CheckTrustedCodeHash(a1) )
      return 1;
  }
  else if ( !v8 )
  {
    return 1;
  }
  a6->dwError = v8;
  a1->padwTrustStepErrors[34] = v8;
  *a3 = 1;
  return 0;
}

```

## disassembly

```asm
0x180018780  mov     [rsp+arg_0], rbx
0x180018785  mov     [rsp+arg_18], r9d
0x18001878a  mov     [rsp+arg_10], r8
0x18001878f  mov     [rsp+arg_8], edx
0x180018793  push    rbp
0x180018794  push    rsi
0x180018795  push    rdi
0x180018796  push    r12
0x180018798  push    r13
0x18001879a  push    r14
0x18001879c  push    r15
0x18001879e  sub     rsp, 40h
0x1800187a2  mov     r8, [rsp+78h+arg_30]
0x1800187aa  lea     r10, off_180069030; "1.2.840.113549.1.1.1"
0x1800187b1  xor     eax, eax
0x1800187b3  xor     ebx, ebx
0x1800187b5  mov     [rsp+78h+var_40], eax
0x1800187b9  xor     r12d, r12d
0x1800187bc  mov     [rsp+78h+var_48], ebx
0x1800187c0  mov     r11d, r9d
0x1800187c3  mov     r13, rcx
0x1800187c6  cmp     r12d, [r8+0Ch]
0x1800187ca  jnb     loc_180018A09
0x1800187d0  mov     rax, [r8+10h]
0x1800187d4  lea     rdi, [r13+40h]
0x1800187d8  xor     esi, esi
0x1800187da  mov     rbp, [rax+r12*8]
0x1800187de  mov     rdx, rdi
0x1800187e1  cmp     esi, [rbp+0Ch]
0x1800187e4  jnb     loc_180018A49
0x1800187ea  mov     rax, [rbp+10h]
0x1800187ee  mov     r14, [rax+rsi*8]
0x1800187f2  mov     r9d, [r14+14h]
0x1800187f6  mov     r15d, [r14+10h]
0x1800187fa  mov     [rsp+78h+var_44], r9d
0x1800187ff  test    r12d, r12d
0x180018802  jnz     short loc_180018808
0x180018804  test    esi, esi
0x180018806  jz      short loc_180018851
0x180018808  mov     rax, [rdx]
0x18001880b  mov     r8d, r11d
0x18001880e  mov     r9d, [rsp+78h+arg_20]
0x180018816  mov     rcx, r13
0x180018819  mov     edx, [rsp+78h+arg_8]
0x180018820  mov     r10, [rax+28h]
0x180018824  mov     rax, [r14+8]
0x180018828  mov     [rsp+78h+var_58], rax
0x18001882d  mov     rax, r10
0x180018830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018835  test    eax, eax
0x180018837  jz      loc_180018B97
0x18001883d  mov     r9d, [rsp+78h+var_44]
0x180018842  lea     r10, off_180069030; "1.2.840.113549.1.1.1"
0x180018849  mov     r8, [rsp+78h+arg_30]
0x180018851  mov     rdx, [rsp+78h+arg_28]
0x180018859  mov     eax, [rdx+0Ch]
0x18001885c  dec     eax
0x18001885e  imul    rdi, rax, 58h ; 'X'
0x180018862  add     rdi, [rdx+10h]
0x180018866  test    r9b, 8
0x18001886a  setnz   cl
0x18001886d  test    r15b, 8
0x180018871  mov     [rdi+50h], r14
0x180018875  setz    al
0x180018878  test    al, cl
0x18001887a  jnz     loc_18001896A
0x180018880  xor     ecx, ecx
0x180018882  mov     [rdi+18h], ecx
0x180018885  mov     dword ptr [rdi+14h], 0
0x18001888c  test    ecx, ecx
0x18001888e  jnz     loc_18001899F
0x180018894  test    r12d, r12d
0x180018897  jnz     loc_180018B07
0x18001889d  xor     eax, eax
0x18001889f  mov     edx, [rdi+24h]
0x1800188a2  mov     r8d, r15d
0x1800188a5  mov     [rdi+38h], eax
0x1800188a8  mov     eax, r15d
0x1800188ab  shr     eax, 7
0x1800188ae  and     eax, 1
0x1800188b1  mov     [rdi+4Ch], eax
0x1800188b4  and     r8d, 8
0x1800188b8  jnz     short loc_1800188BE
0x1800188ba  bts     edx, 1Ch
0x1800188be  mov     eax, edx
0x1800188c0  bts     eax, 18h
0x1800188c4  test    r15b, 1
0x1800188c8  cmovz   edx, eax
0x1800188cb  bts     edx, 14h
0x1800188cf  mov     [rdi+24h], edx
0x1800188d2  and     r9d, 1
0x1800188d6  jnz     loc_180018AEB
0x1800188dc  test    r8d, r8d
0x1800188df  jz      loc_180018AC8
0x1800188e5  mov     rax, [r14+18h]
0x1800188e9  test    rax, rax
0x1800188ec  jz      short loc_1800188F4
0x1800188ee  mov     eax, [rax+4]
0x1800188f1  mov     [rdi+20h], eax
0x1800188f4  test    r8d, r8d
0x1800188f7  jnz     loc_180018B19
0x1800188fd  test    r15b, 4
0x180018901  jnz     loc_180018B3C
0x180018907  mov     eax, [rbp+0Ch]
0x18001890a  dec     eax
0x18001890c  cmp     esi, eax
0x18001890e  jz      loc_180018A51
0x180018914  mov     rax, [r13+40h]
0x180018918  lea     rdi, [r13+40h]
0x18001891c  mov     rax, [rax+60h]
0x180018920  test    rax, rax
0x180018923  jz      short loc_18001894C
0x180018925  mov     r9d, [rsp+78h+arg_20]
0x18001892d  mov     rcx, r13
0x180018930  mov     r8d, [rsp+78h+arg_18]
0x180018938  mov     edx, [rsp+78h+arg_8]
0x18001893f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018944  test    eax, eax
0x180018946  jz      loc_180018A09
0x18001894c  mov     r8, [rsp+78h+arg_30]
0x180018954  lea     r10, off_180069030; "1.2.840.113549.1.1.1"
0x18001895b  mov     r11d, [rsp+78h+arg_18]
0x180018963  inc     esi
0x180018965  jmp     loc_1800187DE
0x18001896a  mov     dword ptr [rdi+18h], 1
0x180018971  mov     ecx, 1
0x180018976  mov     eax, [r8+0Ch]
0x18001897a  dec     eax
0x18001897c  cmp     r12d, eax
0x18001897f  jnz     loc_180018885
0x180018985  mov     eax, [rbp+0Ch]
0x180018988  dec     eax
0x18001898a  cmp     esi, eax
0x18001898c  jnz     loc_180018885
0x180018992  test    r15b, 20h
0x180018996  jnz     loc_180018885
0x18001899c  mov     [rdi+14h], ecx
0x18001899f  xor     ebx, ebx
0x1800189a1  cmp     ebx, 3
0x1800189a4  jnb     loc_180018ADD
0x1800189aa  mov     rax, [rdi+8]
0x1800189ae  lea     r8, [rbx+rbx*2]
0x1800189b2  mov     ecx, [r13+68h]; dwCertEncodingType
0x1800189b6  shl     r8, 4
0x1800189ba  add     r8, r10; pPublicKey2
0x1800189bd  mov     rdx, [rax+18h]
0x1800189c1  add     rdx, 60h ; '`'; pPublicKey1
0x1800189c5  call    cs:__imp_CertComparePublicKeyInfo
0x1800189cb  test    eax, eax
0x1800189cd  jnz     short loc_1800189DA
0x1800189cf  inc     ebx
0x1800189d1  lea     r10, off_180069030; "1.2.840.113549.1.1.1"
0x1800189d8  jmp     short loc_1800189A1
0x1800189da  mov     ebx, [rsp+78h+var_48]
0x1800189de  mov     r9d, [rsp+78h+var_44]
0x1800189e3  mov     dword ptr [rdi+1Ch], 1
0x1800189ea  test    byte ptr [r13+38h], 20h
0x1800189ef  mov     [rsp+78h+var_40], 1
0x1800189f7  jz      loc_180018894
0x1800189fd  mov     dword ptr [rdi+14h], 1
0x180018a04  jmp     loc_180018894
0x180018a09  cmp     [rsp+78h+var_40], 0
0x180018a0e  jnz     loc_180018BAB
0x180018a14  cmp     ebx, 800B010Eh
0x180018a1a  jz      loc_180018AF7
0x180018a20  cmp     ebx, 800B010Ch
0x180018a26  jz      short loc_180018A91
0x180018a28  test    ebx, ebx
0x180018a2a  jnz     short loc_180018A9D
0x180018a2c  mov     eax, 1
0x180018a31  mov     rbx, [rsp+78h+arg_0]
0x180018a39  add     rsp, 40h
0x180018a3d  pop     r15
0x180018a3f  pop     r14
0x180018a41  pop     r13
0x180018a43  pop     r12
0x180018a45  pop     rdi
0x180018a46  pop     rsi
0x180018a47  pop     rbp
0x180018a48  retn
0x180018a49  inc     r12d
0x180018a4c  jmp     loc_1800187C6
0x180018a51  mov     rax, [rbp+18h]
0x180018a55  test    rax, rax
0x180018a58  jz      loc_180018914
0x180018a5e  mov     rcx, [rax+10h]
0x180018a62  test    rcx, rcx
0x180018a65  jz      loc_180018914
0x180018a6b  mov     eax, [rbp+4]
0x180018a6e  mov     [rdi+40h], rcx
0x180018a72  bt      eax, 12h
0x180018a76  jnb     loc_180018B61
0x180018a7c  mov     ebx, 80096004h
0x180018a81  mov     dword ptr [rdi+48h], 80096004h
0x180018a88  mov     [rsp+78h+var_48], ebx
0x180018a8c  jmp     loc_180018914
0x180018a91  mov     rcx, r13; struct _CRYPT_PROVIDER_DATA *
0x180018a94  call    ?_CheckTrustedCodeHash@@YAJPEAU_CRYPT_PROVIDER_DATA@@@Z; _CheckTrustedCodeHash(_CRYPT_PROVIDER_DATA *)
0x180018a99  test    eax, eax
0x180018a9b  jz      short loc_180018A2C
0x180018a9d  mov     r8, [rsp+78h+arg_28]
0x180018aa5  mov     [r8+28h], ebx
0x180018aa9  mov     rax, [r13+50h]
0x180018aad  mov     [rax+88h], ebx
0x180018ab3  mov     rax, [rsp+78h+arg_10]
0x180018abb  mov     dword ptr [rax], 1
0x180018ac1  xor     eax, eax
0x180018ac3  jmp     loc_180018A31
0x180018ac8  test    r9d, r9d
0x180018acb  jz      loc_1800188E5
0x180018ad1  bts     edx, 0Ch
0x180018ad5  mov     [rdi+24h], edx
0x180018ad8  jmp     loc_1800188E5
0x180018add  mov     ebx, [rsp+78h+var_48]
0x180018ae1  mov     r9d, [rsp+78h+var_44]
0x180018ae6  jmp     loc_180018894
0x180018aeb  bts     edx, 10h
0x180018aef  mov     [rdi+24h], edx
0x180018af2  jmp     loc_1800188DC
0x180018af7  mov     rax, [r13+8]
0x180018afb  cmp     dword ptr [rax+1Ch], 1
0x180018aff  jnz     loc_180018A2C
0x180018b05  jmp     short loc_180018A9D
0x180018b07  test    esi, esi
0x180018b09  jnz     loc_18001889D
0x180018b0f  mov     eax, 1
0x180018b14  jmp     loc_18001889F
0x180018b19  bt      r15d, 14h
0x180018b1e  jnb     short loc_180018B32
0x180018b20  test    dword ptr [r13+0C8h], 2000h
0x180018b2b  mov     ebx, 80090008h
0x180018b30  jnz     short loc_180018B37
0x180018b32  mov     ebx, 80096004h
0x180018b37  mov     [rdi+28h], ebx
0x180018b3a  jmp     short loc_180018B58
0x180018b3c  mov     dword ptr [rdi+28h], 800B010Ch
0x180018b43  test    ebx, ebx
0x180018b45  jz      short loc_180018B53
0x180018b47  cmp     ebx, 800B010Eh
0x180018b4d  jnz     loc_180018907
0x180018b53  mov     ebx, 800B010Ch
0x180018b58  mov     [rsp+78h+var_48], ebx
0x180018b5c  jmp     loc_180018907
0x180018b61  bt      eax, 11h
0x180018b65  jnb     short loc_180018B81
0x180018b67  test    dword ptr [r13+38h], 100h
0x180018b6f  jnz     loc_180018914
0x180018b75  mov     dword ptr [rdi+48h], 800B0101h
0x180018b7c  jmp     loc_180018914
0x180018b81  bt      eax, 13h
0x180018b85  jnb     loc_180018914
0x180018b8b  mov     dword ptr [rdi+48h], 800B0110h
0x180018b92  jmp     loc_180018914
0x180018b97  call    cs:__imp_GetLastError
0x180018b9d  mov     [r13+30h], eax
0x180018ba1  mov     ebx, 80096001h
0x180018ba6  jmp     loc_180018A09
0x180018bab  cmp     ebx, 4
0x180018bae  jz      short loc_180018BBC
0x180018bb0  cmp     ebx, 800B010Eh
0x180018bb6  jnz     loc_180018A20
0x180018bbc  mov     r8, [rsp+78h+arg_28]
0x180018bc4  xor     edx, edx
0x180018bc6  cmp     [r8+0Ch], edx
0x180018bca  jbe     loc_180018A2C
0x180018bd0  mov     eax, edx
0x180018bd2  inc     edx
0x180018bd4  imul    rcx, rax, 58h ; 'X'
0x180018bd8  mov     rax, [r8+10h]
0x180018bdc  mov     dword ptr [rcx+rax+28h], 0
0x180018be4  mov     dword ptr [rcx+rax+20h], 0
0x180018bec  cmp     edx, [r8+0Ch]
0x180018bf0  jb      short loc_180018BD0
0x180018bf2  jmp     loc_180018A2C
```
