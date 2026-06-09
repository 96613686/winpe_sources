# WTHelperIsChainedToMicrosoft

- ea: `0x180039200`
- end: `0x180039373`
- name: `WTHelperIsChainedToMicrosoft`
- size: `371`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, HCERTSTORE hSiblingStore, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039380`

## callees

- `0x1800371fc`
- `0x180039200`
- `0x18004de6a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039344`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18003931e`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18003931e`
- `CRYPT32!CertAddStoreToCollection` at `0x18003929e`
- `CRYPT32!CertAddStoreToCollection` at `0x18003929e`
- `CRYPT32!CertGetCertificateChain` at `0x180039301`
- `CRYPT32!CertGetCertificateChain` at `0x180039301`
- `CRYPT32!CertCloseStore` at `0x180039337`
- `CRYPT32!CertCloseStore` at `0x180039337`
- `CRYPT32!CertFreeCertificateChain` at `0x180039353`
- `CRYPT32!CertFreeCertificateChain` at `0x180039353`
- `CRYPT32!CertOpenStore` at `0x18003927d`
- `CRYPT32!CertOpenStore` at `0x18003927d`

## pseudocode

```c
__int64 __fastcall WTHelperIsChainedToMicrosoft(PCCERT_CONTEXT pCertContext, HCERTSTORE hSiblingStore, int a3)
{
  HCERTSTORE v6; // rax
  void *v7; // rdi
  unsigned int CertificateChain; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+40h] [rbp-49h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+50h] [rbp-39h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+70h] [rbp-19h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+F0h] [rbp+67h] BYREF

  memset_0(&pChainPara.cbSize + 1, 0, 0x5Cu);
  pChainPara.cbSize = 96;
  pChainContext = 0;
  pPolicyPara = 0;
  pPolicyPara.cbSize = 16;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  if ( pCertContext && hSiblingStore )
  {
    v6 = CertOpenStore((LPCSTR)0xB, 0x10001u, 0, 0, 0);
    v7 = v6;
    if ( v6 )
    {
      CertificateChain = CertAddStoreToCollection(v6, hSiblingStore, 0, 0);
      if ( CertificateChain )
      {
        if ( a3 )
        {
          pPolicyPara.dwFlags = 0x10000;
          I_AddResourceStore(1, v9, v7);
          I_AddResourceStore(2, v10, v7);
        }
        CertificateChain = CertGetCertificateChain(0, pCertContext, 0, v7, &pChainPara, 0, 0, &pChainContext);
        if ( CertificateChain )
        {
          CertificateChain = CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus);
          if ( CertificateChain )
            CertificateChain = (pPolicyStatus.dwError & 0x80000000) == 0;
        }
      }
      CertCloseStore(v7, 0);
    }
    else
    {
      CertificateChain = 0;
    }
  }
  else
  {
    CertificateChain = 0;
    SetLastError(0x57u);
  }
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  return CertificateChain;
}

```

## disassembly

```asm
0x180039200  mov     [rsp-8+arg_8], rbx
0x180039205  mov     [rsp-8+arg_10], rsi
0x18003920a  push    rbp
0x18003920b  push    rdi
0x18003920c  push    r14
0x18003920e  lea     rbp, [rsp-47h]
0x180039213  sub     rsp, 0D0h
0x18003921a  mov     rbx, rdx
0x18003921d  mov     esi, r8d
0x180039220  xor     edx, edx; Val
0x180039222  mov     r14, rcx
0x180039225  lea     rcx, [rbp+57h+pChainPara+4]; void *
0x180039229  lea     r8d, [rdx+5Ch]; Size
0x18003922d  call    memset_0
0x180039232  xor     eax, eax
0x180039234  mov     [rbp+57h+pChainPara.cbSize], 60h ; '`'
0x18003923b  mov     [rbp+57h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18003923f  xorps   xmm0, xmm0
0x180039242  mov     [rbp+57h+pChainContext], rax
0x180039246  xorps   xmm1, xmm1
0x180039249  movups  xmmword ptr [rbp+57h+pPolicyPara.cbSize], xmm0
0x18003924d  mov     [rbp+57h+pPolicyPara.cbSize], 10h
0x180039254  movups  xmmword ptr [rbp+57h+pPolicyStatus.cbSize], xmm1
0x180039258  test    r14, r14
0x18003925b  jz      loc_18003933F
0x180039261  test    rbx, rbx
0x180039264  jz      loc_18003933F
0x18003926a  xor     r9d, r9d; dwFlags
0x18003926d  mov     [rsp+0E0h+pvPara], rax; pvPara
0x180039272  xor     r8d, r8d; hCryptProv
0x180039275  lea     ecx, [rax+0Bh]; lpszStoreProvider
0x180039278  mov     edx, 10001h; dwEncodingType
0x18003927d  call    cs:__imp_CertOpenStore
0x180039283  mov     rdi, rax
0x180039286  test    rax, rax
0x180039289  jnz     short loc_180039292
0x18003928b  xor     ebx, ebx
0x18003928d  jmp     loc_18003934A
0x180039292  xor     r9d, r9d; dwPriority
0x180039295  xor     r8d, r8d; dwUpdateFlags
0x180039298  mov     rdx, rbx; hSiblingStore
0x18003929b  mov     rcx, rdi; hCollectionStore
0x18003929e  call    cs:__imp_CertAddStoreToCollection
0x1800392a4  mov     ebx, eax
0x1800392a6  test    eax, eax
0x1800392a8  jz      loc_180039332
0x1800392ae  test    esi, esi
0x1800392b0  jz      short loc_1800392D3
0x1800392b2  mov     r8, rdi
0x1800392b5  mov     [rbp+57h+pPolicyPara.dwFlags], 10000h
0x1800392bc  mov     ecx, 1
0x1800392c1  call    I_AddResourceStore
0x1800392c6  mov     r8, rdi
0x1800392c9  mov     ecx, 2
0x1800392ce  call    I_AddResourceStore
0x1800392d3  lea     rax, [rbp+57h+pChainContext]
0x1800392d7  mov     r9, rdi; hAdditionalStore
0x1800392da  mov     [rsp+0E0h+ppChainContext], rax; ppChainContext
0x1800392df  xor     r8d, r8d; pTime
0x1800392e2  mov     [rsp+0E0h+pvReserved], 0; pvReserved
0x1800392eb  lea     rax, [rbp+57h+pChainPara]
0x1800392ef  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x1800392f7  mov     rdx, r14; pCertContext
0x1800392fa  xor     ecx, ecx; hChainEngine
0x1800392fc  mov     [rsp+0E0h+pvPara], rax; pChainPara
0x180039301  call    cs:__imp_CertGetCertificateChain
0x180039307  mov     ebx, eax
0x180039309  test    eax, eax
0x18003930b  jz      short loc_180039332
0x18003930d  mov     rdx, [rbp+57h+pChainContext]; pChainContext
0x180039311  lea     r9, [rbp+57h+pPolicyStatus]; pPolicyStatus
0x180039315  lea     r8, [rbp+57h+pPolicyPara]; pPolicyPara
0x180039319  mov     ecx, 7; pszPolicyOID
0x18003931e  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180039324  mov     ebx, eax
0x180039326  test    eax, eax
0x180039328  jz      short loc_180039332
0x18003932a  xor     ebx, ebx
0x18003932c  cmp     [rbp+57h+pPolicyStatus.dwError], ebx
0x18003932f  setnl   bl
0x180039332  xor     edx, edx; dwFlags
0x180039334  mov     rcx, rdi; hCertStore
0x180039337  call    cs:__imp_CertCloseStore
0x18003933d  jmp     short loc_18003934A
0x18003933f  xor     ebx, ebx
0x180039341  lea     ecx, [rbx+57h]; dwErrCode
0x180039344  call    cs:__imp_SetLastError
0x18003934a  mov     rcx, [rbp+57h+pChainContext]; pChainContext
0x18003934e  test    rcx, rcx
0x180039351  jz      short loc_180039359
0x180039353  call    cs:__imp_CertFreeCertificateChain
0x180039359  lea     r11, [rsp+0E0h+var_10]
0x180039361  mov     eax, ebx
0x180039363  mov     rbx, [r11+28h]
0x180039367  mov     rsi, [r11+30h]
0x18003936b  mov     rsp, r11
0x18003936e  pop     r14
0x180039370  pop     rdi
0x180039371  pop     rbp
0x180039372  retn
```
