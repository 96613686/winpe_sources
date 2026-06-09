# _BuildChainForPubKeyParaInheritance(_CRYPT_PROVIDER_DATA *,_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x18001ed58`
- end: `0x18001ee92`
- name: `?_BuildChainForPubKeyParaInheritance@@YAHPEAU_CRYPT_PROVIDER_DATA@@PEBU_CERT_CONTEXT@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `314`
- prototype: `int(struct _CRYPT_PROVIDER_DATA *, const struct _CERT_CONTEXT *, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010350`
- `0x180010930`
- `0x180011884`

## callees

- `0x18001ed58`

## import_xrefs

- `CRYPT32!CertAddStoreToCollection` at `0x18001edcb`
- `CRYPT32!CertAddStoreToCollection` at `0x18001edcb`
- `CRYPT32!CertGetCertificateChain` at `0x18001ee3d`
- `CRYPT32!CertGetCertificateChain` at `0x18001ee3d`
- `CRYPT32!CertCloseStore` at `0x18001ee61`
- `CRYPT32!CertCloseStore` at `0x18001ee61`
- `CRYPT32!CertFreeCertificateChain` at `0x18001ee8a`
- `CRYPT32!CertFreeCertificateChain` at `0x18001ee8a`
- `CRYPT32!CertOpenStore` at `0x18001eda0`
- `CRYPT32!CertOpenStore` at `0x18001eda0`
- `CRYPT32!CertDuplicateStore` at `0x18001ede5`
- `CRYPT32!CertDuplicateStore` at `0x18001ede5`

## pseudocode

```c
__int64 __fastcall _BuildChainForPubKeyParaInheritance(
        struct _CRYPT_PROVIDER_DATA *a1,
        const struct _CERT_CONTEXT *a2,
        const struct _CERT_CHAIN_CONTEXT **a3)
{
  bool v3; // zf
  HCERTSTORE v7; // rbx
  unsigned __int64 i; // rbp
  unsigned int v9; // edi
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-38h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+80h] [rbp+8h] BYREF

  v3 = a1->chStores == 1;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainContext = 0;
  if ( !v3 )
  {
    v7 = CertOpenStore((LPCSTR)0xB, 0, 0, 0, 0);
    if ( v7 )
    {
      for ( i = 0; i < a1->chStores; CertAddStoreToCollection(v7, a1->pahStores[i++], 1u, 0) )
        ;
      goto LABEL_7;
    }
    return 0;
  }
  v7 = CertDuplicateStore(*a1->pahStores);
  if ( !v7 )
    return 0;
LABEL_7:
  v9 = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  pChainPara.cbSize = 32;
  if ( CertGetCertificateChain(0, a2, 0, v7, &pChainPara, 4u, 0, &pChainContext) )
  {
    if ( a3 )
      *a3 = pChainContext;
    else
      CertFreeCertificateChain(pChainContext);
    v9 = 1;
  }
  CertCloseStore(v7, 0);
  return v9;
}

```

## disassembly

```asm
0x18001ed58  mov     rax, rsp
0x18001ed5b  mov     [rax+10h], rbx
0x18001ed5f  mov     [rax+18h], rbp
0x18001ed63  push    rsi
0x18001ed64  push    rdi
0x18001ed65  push    r14
0x18001ed67  sub     rsp, 60h
0x18001ed6b  cmp     dword ptr [rcx+58h], 1
0x18001ed6f  xorps   xmm0, xmm0
0x18001ed72  movups  xmmword ptr [rax-38h], xmm0
0x18001ed76  mov     rsi, r8
0x18001ed79  mov     r14, rdx
0x18001ed7c  movups  xmmword ptr [rax-28h], xmm0
0x18001ed80  mov     rdi, rcx
0x18001ed83  mov     qword ptr [rax+8], 0
0x18001ed8b  jz      short loc_18001EDDE
0x18001ed8d  xor     edx, edx; dwEncodingType
0x18001ed8f  mov     qword ptr [rax-58h], 0
0x18001ed97  xor     r9d, r9d; dwFlags
0x18001ed9a  xor     r8d, r8d; hCryptProv
0x18001ed9d  lea     ecx, [rdx+0Bh]; lpszStoreProvider
0x18001eda0  call    cs:__imp_CertOpenStore
0x18001eda6  mov     rbx, rax
0x18001eda9  test    rax, rax
0x18001edac  jz      loc_18001EE7E
0x18001edb2  xor     ebp, ebp
0x18001edb4  cmp     [rdi+58h], ebp
0x18001edb7  jbe     short loc_18001EDF7
0x18001edb9  mov     rdx, [rdi+60h]
0x18001edbd  xor     r9d, r9d; dwPriority
0x18001edc0  mov     rcx, rbx; hCollectionStore
0x18001edc3  mov     rdx, [rdx+rbp*8]; hSiblingStore
0x18001edc7  lea     r8d, [r9+1]; dwUpdateFlags
0x18001edcb  call    cs:__imp_CertAddStoreToCollection
0x18001edd1  mov     eax, [rdi+58h]
0x18001edd4  inc     rbp
0x18001edd7  cmp     rbp, rax
0x18001edda  jb      short loc_18001EDB9
0x18001eddc  jmp     short loc_18001EDF7
0x18001edde  mov     rcx, [rcx+60h]
0x18001ede2  mov     rcx, [rcx]; hCertStore
0x18001ede5  call    cs:__imp_CertDuplicateStore
0x18001edeb  mov     rbx, rax
0x18001edee  test    rax, rax
0x18001edf1  jz      loc_18001EE7E
0x18001edf7  xorps   xmm0, xmm0
0x18001edfa  lea     rax, [rsp+78h+pChainContext]
0x18001ee02  mov     [rsp+78h+ppChainContext], rax; ppChainContext
0x18001ee07  xor     edi, edi
0x18001ee09  mov     [rsp+78h+pvReserved], rdi; pvReserved
0x18001ee0e  lea     rax, [rsp+78h+var_38]
0x18001ee13  movups  xmmword ptr [rsp+78h+var_38.cbSize], xmm0
0x18001ee18  mov     [rsp+78h+dwFlags], 4; dwFlags
0x18001ee20  mov     r9, rbx; hAdditionalStore
0x18001ee23  xor     r8d, r8d; pTime
0x18001ee26  mov     [rsp+78h+pChainPara], rax; pChainPara
0x18001ee2b  mov     rdx, r14; pCertContext
0x18001ee2e  mov     [rsp+78h+var_38.cbSize], 20h ; ' '
0x18001ee36  xor     ecx, ecx; hChainEngine
0x18001ee38  movups  xmmword ptr [rsp+78h+var_38.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18001ee3d  call    cs:__imp_CertGetCertificateChain
0x18001ee43  test    eax, eax
0x18001ee45  jz      short loc_18001EE5C
0x18001ee47  test    rsi, rsi
0x18001ee4a  jz      short loc_18001EE82
0x18001ee4c  mov     rax, [rsp+78h+pChainContext]
0x18001ee54  mov     [rsi], rax
0x18001ee57  mov     edi, 1
0x18001ee5c  xor     edx, edx; dwFlags
0x18001ee5e  mov     rcx, rbx; hCertStore
0x18001ee61  call    cs:__imp_CertCloseStore
0x18001ee67  mov     eax, edi
0x18001ee69  lea     r11, [rsp+78h+var_18]
0x18001ee6e  mov     rbx, [r11+28h]
0x18001ee72  mov     rbp, [r11+30h]
0x18001ee76  mov     rsp, r11
0x18001ee79  pop     r14
0x18001ee7b  pop     rdi
0x18001ee7c  pop     rsi
0x18001ee7d  retn
0x18001ee7e  xor     eax, eax
0x18001ee80  jmp     short loc_18001EE69
0x18001ee82  mov     rcx, [rsp+78h+pChainContext]; pChainContext
0x18001ee8a  call    cs:__imp_CertFreeCertificateChain
0x18001ee90  jmp     short loc_18001EE57
```
