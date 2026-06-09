# _WalkChain(_CRYPT_PROVIDER_DATA *,ulong,ulong *,int,ulong,int,int *)

- ea: `0x180018090`
- end: `0x180018659`
- name: `?_WalkChain@@YAHPEAU_CRYPT_PROVIDER_DATA@@KPEAKHKHPEAH@Z`
- size: `1481`
- prototype: `__int64 __usercall@<rax>(struct _CRYPT_PROVIDER_DATA *@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, int@<r9d>, unsigned int, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800286a0`

## callees

- `0x180018090`
- `0x180018660`
- `0x180018780`
- `0x18004de6a`
- `0x18004de76`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001852c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001852c`
- `CRYPT32!CertAddStoreToCollection` at `0x1800181b7`
- `CRYPT32!CertAddStoreToCollection` at `0x180018602`
- `CRYPT32!CertAddStoreToCollection` at `0x1800181b7`
- `CRYPT32!CertAddStoreToCollection` at `0x180018602`
- `CRYPT32!CertGetCertificateChain` at `0x1800182f3`
- `CRYPT32!CertGetCertificateChain` at `0x180018519`
- `CRYPT32!CertGetCertificateChain` at `0x1800182f3`
- `CRYPT32!CertGetCertificateChain` at `0x180018519`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18001864e`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x18001864e`
- `CRYPT32!CryptQueryObject` at `0x1800185dd`
- `CRYPT32!CryptQueryObject` at `0x1800185dd`
- `CRYPT32!CertCloseStore` at `0x18001838c`
- `CRYPT32!CertCloseStore` at `0x18001860f`
- `CRYPT32!CertCloseStore` at `0x18001838c`
- `CRYPT32!CertCloseStore` at `0x18001860f`
- `CRYPT32!CertFreeCertificateChain` at `0x1800184d3`
- `CRYPT32!CertFreeCertificateChain` at `0x1800184d3`
- `CRYPT32!CertOpenStore` at `0x18001818d`
- `CRYPT32!CertOpenStore` at `0x18001818d`

## pseudocode

```c
__int64 __fastcall _WalkChain(
        struct _CRYPT_PROVIDER_DATA *a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int *a7)
{
  char *pszUsageOID; // r10
  struct _CRYPT_PROVIDER_SGNR *v11; // rdx
  unsigned __int64 v12; // rsi
  int v13; // ebx
  unsigned int updated; // r15d
  HCERTSTORE v15; // r14
  DWORD i; // ebx
  DWORD dwProvFlags; // r8d
  int v18; // edx
  int v19; // edx
  unsigned int v20; // ecx
  int v21; // edx
  DWORD dwFlags; // r12d
  WINTRUST_DATA *pWintrustData; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  struct _FILETIME *v26; // r8
  PCCERT_CHAIN_CONTEXT v27; // rdx
  DWORD v28; // eax
  CERT_USAGE_MATCH *pRequestUsage; // rcx
  PCERT_ENHKEY_USAGE pApplicationUsage; // r8
  unsigned int cUsageIdentifier; // ecx
  __int64 v33; // rax
  const CERT_CHAIN_CONTEXT *v34; // rcx
  struct _FILETIME *v35; // r8
  DWORD v36; // r12d
  DWORD v37; // ebx
  PCCERT_CHAIN_CONTEXT ppChainContext; // [rsp+68h] [rbp-A0h] BYREF
  HCERTSTORE hSiblingStore; // [rsp+70h] [rbp-98h] BYREF
  HCERTCHAINENGINE hChainEngine; // [rsp+78h] [rbp-90h]
  char *v41; // [rsp+80h] [rbp-88h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+88h] [rbp-80h]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+90h] [rbp-78h]
  _QWORD pvObject[2]; // [rsp+98h] [rbp-70h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-10h]
  int v49; // [rsp+160h] [rbp+58h]
  int v50; // [rsp+160h] [rbp+58h]

  memset_0(&pChainPara, 0, 0x60u);
  pszUsageOID = 0;
  v11 = &a1->pasSigners[(unsigned __int64)a2];
  ppChainContext = 0;
  v41 = 0;
  if ( a4 )
    v12 = (unsigned __int64)&v11->pasCounterSigners[(unsigned __int64)a5];
  else
    v12 = (unsigned __int64)v11;
  if ( *(_DWORD *)(v12 + 12) != 1 || (pCertContext = *(PCCERT_CONTEXT *)(*(_QWORD *)(v12 + 16) + 8LL)) == 0 )
  {
    hChainEngine = 0;
    v15 = 0;
    v37 = -2146869246;
    goto LABEL_77;
  }
  v13 = 0;
  updated = 1;
  v49 = 0;
  if ( a4 || (a1->dwProvFlags & 0x100000) == 0 )
  {
    pChainPara.cbSize = 96;
    if ( a4 && *(_DWORD *)(v12 + 24) == 16 )
    {
      pszUsageOID = "1.3.6.1.5.5.7.3.8";
      goto LABEL_9;
    }
  }
  else
  {
    v13 = 1;
    pChainPara.cbSize = 96;
    v49 = 1;
  }
  pRequestUsage = a1->pRequestUsage;
  if ( pRequestUsage )
  {
    pChainPara.RequestedUsage = *pRequestUsage;
    goto LABEL_10;
  }
  pszUsageOID = a1->pszUsageOID;
LABEL_9:
  v41 = pszUsageOID;
LABEL_10:
  if ( (a1->dwProvFlags & 4) == 0 && pszUsageOID )
  {
    pChainPara.RequestedUsage.dwType = 0;
    pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = &v41;
    pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
  }
  hChainEngine = GetChainEngine(a1);
  v15 = CertOpenStore((LPCSTR)0xB, 0, 0, 0, 0);
  if ( v15 )
  {
    for ( i = 0; i < a1->chStores; ++i )
      CertAddStoreToCollection(v15, a1->pahStores[i], 1u, 0);
    v13 = v49;
    if ( v49 )
    {
      pvObject[1] = qword_180056550;
      hSiblingStore = 0;
      pvObject[0] = 1801;
      if ( CryptQueryObject(2u, pvObject, 2u, 2u, 0, 0, 0, 0, &hSiblingStore, 0, 0) )
      {
        if ( hSiblingStore )
        {
          CertAddStoreToCollection(v15, hSiblingStore, 1u, 0);
          CertCloseStore(hSiblingStore, 0);
        }
      }
    }
  }
  dwProvFlags = a1->dwProvFlags;
  v18 = 0;
  if ( (dwProvFlags & 0x10010) == 0 )
  {
    if ( (dwProvFlags & 0x20000) != 0 )
    {
      v19 = 0x10000000;
      goto LABEL_27;
    }
    if ( (dwProvFlags & 0x40000) != 0 )
    {
      v19 = 0x20000000;
      goto LABEL_27;
    }
    if ( (dwProvFlags & 0x80000) == 0 )
    {
      if ( (dwProvFlags & 0x20) != 0 )
      {
        v19 = 0x10000000;
        goto LABEL_27;
      }
      if ( (dwProvFlags & 0x40) != 0 )
      {
        v19 = 0x20000000;
        goto LABEL_27;
      }
      if ( (dwProvFlags & 0x80u) == 0 )
      {
        if ( a1->pWintrustData->fdwRevocationChecks == 1 )
        {
          v19 = 0x20000000;
          goto LABEL_27;
        }
        if ( a4 && *(_DWORD *)(v12 + 24) == 16 )
        {
          v19 = 0x40000000;
          if ( (a1->dwRegPolicySettings & 0x20000) != 0 )
          {
            v18 = 0;
            goto LABEL_28;
          }
LABEL_27:
          v18 = v19 | 0x8000000;
          goto LABEL_28;
        }
        if ( (a1->dwRegPolicySettings & 0x200) != 0 )
          goto LABEL_28;
      }
    }
    v19 = 0x40000000;
    goto LABEL_27;
  }
LABEL_28:
  if ( a1->pWintrustData->dwUnionChoice - 4 > 1 )
    v18 |= 1u;
  v20 = v18 | 0x80000004;
  if ( (dwProvFlags & 0x1000) == 0 )
    v20 = v18;
  v21 = v20 | 0x1000;
  if ( (dwProvFlags & 0x2000) == 0 )
    v21 = v20;
  if ( (dwProvFlags & 0x4000) != 0 )
    v21 |= 0x4000u;
  dwFlags = v21 | 0xC0;
  if ( !v13 )
    dwFlags = v21;
  if ( a6 && *a7 )
    dwFlags |= 0x200u;
  pWintrustData = a1[1].pWintrustData;
  if ( pWintrustData )
  {
    v24 = *(_QWORD *)&pWintrustData->dwUIChoice;
    v25 = v46;
    if ( v24 )
      v25 = v24;
    v46 = v25;
  }
  v26 = (struct _FILETIME *)(v12 + 4);
  if ( !*(_QWORD *)(v12 + 4) )
    v26 = 0;
  if ( !CertGetCertificateChain(hChainEngine, pCertContext, v26, v15, &pChainPara, dwFlags, 0, &ppChainContext) )
  {
LABEL_76:
    v37 = -2146869247;
    a1->dwError = GetLastError();
LABEL_77:
    *(_DWORD *)(v12 + 40) = v37;
    a1->padwTrustStepErrors[34] = v37;
    *a3 = 1;
    updated = 0;
    goto LABEL_50;
  }
  if ( !a6 || *a7 )
    goto LABEL_47;
  v27 = ppChainContext;
  pChainContext = ppChainContext;
  pApplicationUsage = (*(*ppChainContext->rgpChain)->rgpElement)->pApplicationUsage;
  pvObject[0] = pApplicationUsage;
  if ( pApplicationUsage )
  {
    cUsageIdentifier = pApplicationUsage->cUsageIdentifier;
    v33 = 0;
    LODWORD(hSiblingStore) = pApplicationUsage->cUsageIdentifier;
    while ( 1 )
    {
      v50 = v33;
      if ( (unsigned int)v33 >= cUsageIdentifier )
      {
        v27 = pChainContext;
        goto LABEL_48;
      }
      if ( !strcmp_0(pApplicationUsage->rgpszUsageIdentifier[v33], "1.3.6.1.4.1.311.10.3.13") )
        break;
      cUsageIdentifier = (unsigned int)hSiblingStore;
      v33 = (unsigned int)(v50 + 1);
      pApplicationUsage = (PCERT_ENHKEY_USAGE)pvObject[0];
    }
    v34 = pChainContext;
    *a7 = 1;
    CertFreeCertificateChain(v34);
    v35 = (struct _FILETIME *)(v12 + 4);
    v36 = dwFlags | 0x200;
    ppChainContext = 0;
    if ( !*(_QWORD *)(v12 + 4) )
      v35 = 0;
    if ( !CertGetCertificateChain(hChainEngine, pCertContext, v35, v15, &pChainPara, v36, 0, &ppChainContext) )
      goto LABEL_76;
LABEL_47:
    v27 = ppChainContext;
  }
LABEL_48:
  *(_QWORD *)(v12 + 56) = v27;
  v28 = a1->dwProvFlags;
  if ( (v28 & 2) != 0 )
    a1->dwProvFlags = v28 | 0x80000000;
  else
    updated = UpdateCertProvChain(a1, a2, a3, a4, a5, (struct _CRYPT_PROVIDER_SGNR *)v12, ppChainContext);
LABEL_50:
  if ( hChainEngine )
    CertFreeCertificateChainEngine(hChainEngine);
  if ( v15 )
    CertCloseStore(v15, 0);
  return updated;
}

```

## disassembly

```asm
0x180018090  mov     rax, rsp
0x180018093  mov     [rax+18h], r8
0x180018097  mov     [rax+10h], edx
0x18001809a  push    rbp
0x18001809b  push    r14
0x18001809d  lea     rbp, [rax-38h]
0x1800180a1  sub     rsp, 128h
0x1800180a8  mov     [rax+8], rbx
0x1800180ac  mov     r8d, 60h ; '`'; Size
0x1800180b2  mov     [rax-18h], rsi
0x1800180b6  mov     [rax-20h], rdi
0x1800180ba  mov     rdi, rcx
0x1800180bd  mov     [rax-28h], r12
0x1800180c1  lea     rcx, [rbp+30h+pChainPara]; void *
0x1800180c5  mov     ebx, edx
0x1800180c7  xor     edx, edx; Val
0x1800180c9  mov     [rax-30h], r13
0x1800180cd  mov     r13d, r9d
0x1800180d0  call    memset_0
0x1800180d5  xor     r12d, r12d
0x1800180d8  mov     edx, ebx
0x1800180da  shl     rdx, 6
0x1800180de  mov     r10d, r12d
0x1800180e1  add     rdx, [rdi+80h]
0x1800180e8  mov     [rsp+130h+var_D0], r12
0x1800180ed  mov     [rsp+130h+var_B8], r12
0x1800180f2  test    r13d, r13d
0x1800180f5  jnz     loc_180018400
0x1800180fb  mov     rsi, rdx
0x1800180fe  cmp     dword ptr [rsi+0Ch], 1
0x180018102  mov     [rsp+130h+var_30], r15
0x18001810a  jnz     loc_180018633
0x180018110  mov     rax, [rsi+10h]
0x180018114  mov     rax, [rax+8]
0x180018118  mov     [rbp+30h+pCertContext], rax
0x18001811c  test    rax, rax
0x18001811f  jz      loc_180018633
0x180018125  mov     ebx, r12d
0x180018128  mov     r15d, 1
0x18001812e  mov     [rbp+30h+arg_18], ebx
0x180018131  test    r13d, r13d
0x180018134  jz      loc_1800183A8
0x18001813a  mov     [rbp+30h+pChainPara.cbSize], 60h ; '`'
0x180018141  test    r13d, r13d
0x180018144  jz      loc_1800183C5
0x18001814a  cmp     dword ptr [rsi+18h], 10h
0x18001814e  jnz     loc_1800183C5
0x180018154  lea     r10, a136155738; "1.3.6.1.5.5.7.3.8"
0x18001815b  mov     [rsp+130h+var_B8], r10
0x180018160  mov     eax, [rdi+0C8h]
0x180018166  test    al, 4
0x180018168  jz      loc_1800183E1
0x18001816e  mov     rcx, rdi; struct _CRYPT_PROVIDER_DATA *
0x180018171  call    ?GetChainEngine@@YAPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z; GetChainEngine(_CRYPT_PROVIDER_DATA *)
0x180018176  xor     r9d, r9d; dwFlags
0x180018179  mov     [rsp+130h+hChainEngine], rax
0x18001817e  xor     r8d, r8d; hCryptProv
0x180018181  mov     [rsp+130h+pvPara], r12; pvPara
0x180018186  xor     edx, edx; dwEncodingType
0x180018188  mov     ecx, 0Bh; lpszStoreProvider
0x18001818d  call    cs:__imp_CertOpenStore
0x180018193  mov     r14, rax
0x180018196  test    rax, rax
0x180018199  jz      short loc_1800181CF
0x18001819b  mov     ebx, r12d
0x18001819e  cmp     [rdi+58h], r12d
0x1800181a2  jbe     short loc_1800181C4
0x1800181a4  mov     rdx, [rdi+60h]
0x1800181a8  xor     r9d, r9d; dwPriority
0x1800181ab  mov     eax, ebx
0x1800181ad  mov     r8d, r15d; dwUpdateFlags
0x1800181b0  mov     rcx, r14; hCollectionStore
0x1800181b3  mov     rdx, [rdx+rax*8]; hSiblingStore
0x1800181b7  call    cs:__imp_CertAddStoreToCollection
0x1800181bd  inc     ebx
0x1800181bf  cmp     ebx, [rdi+58h]
0x1800181c2  jb      short loc_1800181A4
0x1800181c4  mov     ebx, [rbp+30h+arg_18]
0x1800181c7  test    ebx, ebx
0x1800181c9  jnz     loc_18001858D
0x1800181cf  mov     r8d, [rdi+0C8h]
0x1800181d6  mov     edx, r12d
0x1800181d9  test    r8d, 10010h
0x1800181e0  jnz     short loc_180018244
0x1800181e2  bt      r8d, 11h
0x1800181e7  jb      loc_180018629
0x1800181ed  bt      r8d, 12h
0x1800181f2  jb      loc_180018583
0x1800181f8  bt      r8d, 13h
0x1800181fd  jb      short loc_180018234
0x1800181ff  test    r8b, 20h
0x180018203  jnz     loc_180018579
0x180018209  test    r8b, 40h
0x18001820d  jnz     short loc_18001823B
0x18001820f  test    r8b, r8b
0x180018212  js      short loc_180018234
0x180018214  mov     rax, [rdi+8]
0x180018218  cmp     [rax+1Ch], r15d
0x18001821c  jz      loc_18001849A
0x180018222  test    r13d, r13d
0x180018225  jnz     loc_180018554
0x18001822b  test    dword ptr [rdi+38h], 200h
0x180018232  jnz     short loc_180018244
0x180018234  mov     edx, 40000000h
0x180018239  jmp     short loc_180018240
0x18001823b  mov     edx, 20000000h
0x180018240  bts     edx, 1Bh
0x180018244  mov     rax, [rdi+8]
0x180018248  mov     ecx, [rax+20h]
0x18001824b  sub     ecx, 4
0x18001824e  cmp     ecx, r15d
0x180018251  jbe     short loc_180018256
0x180018253  or      edx, r15d
0x180018256  mov     ecx, edx
0x180018258  or      ecx, 80000004h
0x18001825e  bt      r8d, 0Ch
0x180018263  cmovnb  ecx, edx
0x180018266  mov     edx, ecx
0x180018268  bts     edx, 0Ch
0x18001826c  bt      r8d, 0Dh
0x180018271  cmovnb  edx, ecx
0x180018274  mov     eax, edx
0x180018276  bts     eax, 0Eh
0x18001827a  bt      r8d, 0Eh
0x18001827f  cmovb   edx, eax
0x180018282  mov     r12d, edx
0x180018285  or      r12d, 0C0h
0x18001828c  test    ebx, ebx
0x18001828e  cmovz   r12d, edx
0x180018292  xor     ebx, ebx
0x180018294  cmp     [rbp+30h+arg_28], ebx
0x180018297  jnz     loc_180018484
0x18001829d  mov     rcx, [rdi+0E8h]
0x1800182a4  test    rcx, rcx
0x1800182a7  jz      short loc_1800182BC
0x1800182a9  mov     rcx, [rcx+18h]
0x1800182ad  mov     rax, [rbp+30h+var_40]
0x1800182b1  test    rcx, rcx
0x1800182b4  cmovnz  rax, rcx
0x1800182b8  mov     [rbp+30h+var_40], rax
0x1800182bc  mov     rdx, [rbp+30h+pCertContext]; pCertContext
0x1800182c0  lea     r8, [rsi+4]
0x1800182c4  mov     rcx, [rsp+130h+hChainEngine]; hChainEngine
0x1800182c9  xor     eax, eax
0x1800182cb  cmp     [rsi+4], rax
0x1800182cf  mov     r9, r14; hAdditionalStore
0x1800182d2  cmovz   r8, rax; pTime
0x1800182d6  lea     rax, [rsp+130h+var_D0]
0x1800182db  mov     [rsp+130h+ppChainContext], rax; ppChainContext
0x1800182e0  lea     rax, [rbp+30h+pChainPara]
0x1800182e4  mov     [rsp+130h+pvReserved], rbx; pvReserved
0x1800182e9  mov     [rsp+130h+dwFlags], r12d; dwFlags
0x1800182ee  mov     [rsp+130h+pvPara], rax; pChainPara
0x1800182f3  call    cs:__imp_CertGetCertificateChain
0x1800182f9  test    eax, eax
0x1800182fb  jz      loc_180018527
0x180018301  cmp     [rbp+30h+arg_28], ebx
0x180018304  jnz     loc_180018410
0x18001830a  mov     rdx, [rsp+130h+var_D0]
0x18001830f  mov     [rsi+38h], rdx
0x180018313  mov     eax, [rdi+0C8h]
0x180018319  test    al, 2
0x18001831b  jnz     loc_18001861A
0x180018321  mov     rax, [rsp+130h+var_D0]
0x180018326  mov     r9d, r13d; int
0x180018329  mov     r8, [rbp+30h+arg_10]; unsigned int *
0x18001832d  mov     rcx, rdi; struct _CRYPT_PROVIDER_DATA *
0x180018330  mov     edx, [rbp+30h+arg_8]; unsigned int
0x180018333  mov     [rsp+130h+pvReserved], rax; struct _CERT_CHAIN_CONTEXT *
0x180018338  mov     eax, [rbp+30h+arg_20]
0x18001833b  mov     qword ptr [rsp+130h+dwFlags], rsi; struct _CRYPT_PROVIDER_SGNR *
0x180018340  mov     dword ptr [rsp+130h+pvPara], eax; unsigned int
0x180018344  call    ?UpdateCertProvChain@@YAHPEAU_CRYPT_PROVIDER_DATA@@KPEAKHKPEAU_CRYPT_PROVIDER_SGNR@@PEBU_CERT_CHAIN_CONTEXT@@@Z; UpdateCertProvChain(_CRYPT_PROVIDER_DATA *,ulong,ulong *,int,ulong,_CRYPT_PROVIDER_SGNR *,_CERT_CHAIN_CONTEXT const *)
0x180018349  mov     r15d, eax
0x18001834c  mov     rax, [rsp+130h+hChainEngine]
0x180018351  mov     r13, [rsp+130h+var_28]
0x180018359  mov     r12, [rsp+130h+var_20]
0x180018361  mov     rdi, [rsp+130h+var_18]
0x180018369  mov     rsi, [rsp+120h]
0x180018371  mov     rbx, [rsp+130h+arg_0]
0x180018379  test    rax, rax
0x18001837c  jnz     loc_18001864B
0x180018382  test    r14, r14
0x180018385  jz      short loc_180018392
0x180018387  xor     edx, edx; dwFlags
0x180018389  mov     rcx, r14; hCertStore
0x18001838c  call    cs:__imp_CertCloseStore
0x180018392  mov     eax, r15d
0x180018395  mov     r15, [rsp+130h+var_30]
0x18001839d  add     rsp, 128h
0x1800183a4  pop     r14
0x1800183a6  pop     rbp
0x1800183a7  retn
0x1800183a8  test    dword ptr [rdi+0C8h], 100000h
0x1800183b2  jz      loc_18001813A
0x1800183b8  mov     ebx, r15d
0x1800183bb  mov     [rbp+30h+pChainPara.cbSize], 60h ; '`'
0x1800183c2  mov     [rbp+30h+arg_18], ebx
0x1800183c5  mov     rcx, [rdi+0D0h]
0x1800183cc  test    rcx, rcx
0x1800183cf  jnz     loc_1800184A4
0x1800183d5  mov     r10, [rdi+0A8h]
0x1800183dc  jmp     loc_18001815B
0x1800183e1  test    r10, r10
0x1800183e4  jz      loc_18001816E
0x1800183ea  lea     rax, [rsp+130h+var_B8]
0x1800183ef  mov     [rbp+30h+pChainPara.RequestedUsage.dwType], r12d
0x1800183f3  mov     [rbp+30h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x1800183f7  mov     [rbp+30h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], r15d
0x1800183fb  jmp     loc_18001816E
0x180018400  mov     esi, [rbp+30h+arg_20]
0x180018403  shl     rsi, 6
0x180018407  add     rsi, [rdx+30h]
0x18001840b  jmp     loc_1800180FE
0x180018410  mov     rax, [rbp+30h+arg_30]
0x180018414  cmp     [rax], ebx
0x180018416  jnz     loc_18001830A
0x18001841c  mov     rdx, [rsp+130h+var_D0]
0x180018421  mov     [rbp+30h+pChainContext], rdx
0x180018425  mov     rax, [rdx+10h]
0x180018429  mov     rcx, [rax]
0x18001842c  mov     rax, [rcx+10h]
0x180018430  mov     rcx, [rax]
0x180018433  mov     r8, [rcx+28h]
0x180018437  mov     [rbp+30h+pvObject], r8
0x18001843b  test    r8, r8
0x18001843e  jz      loc_18001830F
0x180018444  mov     ecx, [r8]
0x180018447  xor     eax, eax
0x180018449  mov     dword ptr [rsp+130h+hSiblingStore], ecx
0x18001844d  mov     [rbp+30h+arg_18], eax
0x180018450  cmp     eax, ecx
0x180018452  jnb     short loc_18001847B
0x180018454  mov     rcx, [r8+8]
0x180018458  lea     rdx, a13614131110313; "1.3.6.1.4.1.311.10.3.13"
0x18001845f  mov     rcx, [rcx+rax*8]; Str1
0x180018463  call    strcmp_0
0x180018468  test    eax, eax
0x18001846a  jz      short loc_1800184C8
0x18001846c  mov     eax, [rbp+30h+arg_18]
0x18001846f  mov     ecx, dword ptr [rsp+130h+hSiblingStore]
0x180018473  inc     eax
0x180018475  mov     r8, [rbp+30h+pvObject]
0x180018479  jmp     short loc_18001844D
0x18001847b  mov     rdx, [rbp+30h+pChainContext]
0x18001847f  jmp     loc_18001830F
0x180018484  mov     rax, [rbp+30h+arg_30]
0x180018488  cmp     [rax], ebx
0x18001848a  jz      loc_18001829D
0x180018490  bts     r12d, 9
0x180018495  jmp     loc_18001829D
0x18001849a  mov     edx, 20000000h
0x18001849f  jmp     loc_180018240
0x1800184a4  mov     eax, [rcx]
0x1800184a6  mov     [rbp+30h+pChainPara.RequestedUsage.dwType], eax
0x1800184a9  mov     eax, [rcx+4]
0x1800184ac  mov     dword ptr [rbp+30h+pChainPara.RequestedUsage+4], eax
0x1800184af  mov     eax, [rcx+8]
0x1800184b2  mov     [rbp+30h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], eax
0x1800184b5  mov     eax, [rcx+0Ch]
0x1800184b8  mov     dword ptr [rbp+30h+pChainPara.RequestedUsage.Usage+4], eax
0x1800184bb  mov     rax, [rcx+10h]
0x1800184bf  mov     [rbp+30h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x1800184c3  jmp     loc_180018160
0x1800184c8  mov     rax, [rbp+30h+arg_30]
0x1800184cc  mov     rcx, [rbp+30h+pChainContext]; pChainContext
0x1800184d0  mov     [rax], r15d
0x1800184d3  call    cs:__imp_CertFreeCertificateChain
0x1800184d9  mov     rdx, [rbp+30h+pCertContext]; pCertContext
0x1800184dd  lea     r8, [rsi+4]
0x1800184e1  mov     rcx, [rsp+130h+hChainEngine]; hChainEngine
0x1800184e6  xor     eax, eax
0x1800184e8  bts     r12d, 9
0x1800184ed  mov     [rsp+130h+var_D0], rbx
0x1800184f2  cmp     [r8], rax
0x1800184f5  mov     r9, r14; hAdditionalStore
0x1800184f8  cmovz   r8, rax; pTime
0x1800184fc  lea     rax, [rsp+130h+var_D0]
0x180018501  mov     [rsp+130h+ppChainContext], rax; ppChainContext
0x180018506  lea     rax, [rbp+30h+pChainPara]
0x18001850a  mov     [rsp+130h+pvReserved], rbx; pvReserved
0x18001850f  mov     [rsp+130h+dwFlags], r12d; dwFlags
0x180018514  mov     [rsp+130h+pvPara], rax; pChainPara
0x180018519  call    cs:__imp_CertGetCertificateChain
0x18001851f  test    eax, eax
0x180018521  jnz     loc_18001830A
0x180018527  mov     ebx, 80096001h
0x18001852c  call    cs:__imp_GetLastError
0x180018532  mov     [rdi+30h], eax
0x180018535  xor     r12d, r12d
0x180018538  mov     [rsi+28h], ebx
0x18001853b  mov     rax, [rdi+50h]
0x18001853f  mov     [rax+88h], ebx
0x180018545  mov     rax, [rbp+30h+arg_10]
0x180018549  mov     [rax], r15d
0x18001854c  mov     r15d, r12d
0x18001854f  jmp     loc_18001834C
0x180018554  cmp     dword ptr [rsi+18h], 10h
0x180018558  jnz     loc_18001822B
0x18001855e  test    dword ptr [rdi+38h], 20000h
  ... truncated ...
```
