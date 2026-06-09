# _BuildSignerChainForWeakHashCheck

- ea: `0x180045274`
- end: `0x180045388`
- name: `_BuildSignerChainForWeakHashCheck`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ae0`
- `0x1800199d0`

## callees

- `0x18001a0d0`
- `0x180045274`

## import_xrefs

- `CRYPT32!CertAddStoreToCollection` at `0x180045316`
- `CRYPT32!CertAddStoreToCollection` at `0x180045316`
- `CRYPT32!CertGetCertificateChain` at `0x180045366`
- `CRYPT32!CertGetCertificateChain` at `0x180045366`
- `CRYPT32!CertCloseStore` at `0x180045371`
- `CRYPT32!CertCloseStore` at `0x180045371`
- `CRYPT32!CertOpenStore` at `0x1800452ef`
- `CRYPT32!CertOpenStore` at `0x1800452ef`
- `CRYPT32!CertDuplicateStore` at `0x1800452c7`
- `CRYPT32!CertDuplicateStore` at `0x1800452c7`

## pseudocode

```c
PCCERT_CHAIN_CONTEXT __fastcall BuildSignerChainForWeakHashCheck(__int64 a1, CRYPT_PROVIDER_SGNR *a2)
{
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  const CERT_CONTEXT *pCert; // rsi
  HCERTSTORE v5; // rdi
  __int64 i; // rbp
  int dwFlags; // [rsp+28h] [rbp-60h]
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-48h] BYREF
  PCCERT_CHAIN_CONTEXT ppChainContext; // [rsp+A0h] [rbp+18h] BYREF

  ppChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  ProvCertFromChain = WTHelperGetProvCertFromChain(a2, 0);
  if ( ProvCertFromChain )
  {
    pCert = ProvCertFromChain->pCert;
    if ( pCert )
    {
      if ( *(_DWORD *)(a1 + 88) == 1 )
      {
        v5 = CertDuplicateStore(**(HCERTSTORE **)(a1 + 96));
        if ( v5 )
        {
LABEL_9:
          dwFlags = (*(_DWORD *)(a1 + 200) >> 10) & 4;
          pChainPara.cbSize = 32;
          CertGetCertificateChain(0, pCert, 0, v5, &pChainPara, dwFlags, 0, &ppChainContext);
          CertCloseStore(v5, 0);
        }
      }
      else
      {
        v5 = CertOpenStore((LPCSTR)0xB, 0, 0, 0, 0);
        if ( v5 )
        {
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 88); i = (unsigned int)(i + 1) )
            CertAddStoreToCollection(v5, *(HCERTSTORE *)(*(_QWORD *)(a1 + 96) + 8 * i), 1u, 0);
          goto LABEL_9;
        }
      }
    }
  }
  return ppChainContext;
}

```

## disassembly

```asm
0x180045274  mov     r11, rsp
0x180045277  push    rbx
0x180045278  push    rbp
0x180045279  push    rsi
0x18004527a  push    rdi
0x18004527b  sub     rsp, 68h
0x18004527f  mov     rax, rdx
0x180045282  mov     qword ptr [r11+18h], 0
0x18004528a  xorps   xmm0, xmm0
0x18004528d  mov     rbx, rcx
0x180045290  mov     rcx, rax; pSgnr
0x180045293  xor     edx, edx; idxCert
0x180045295  movups  xmmword ptr [rsp+88h+pChainPara.cbSize], xmm0
0x18004529a  movups  xmmword ptr [rsp+88h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x18004529f  call    WTHelperGetProvCertFromChain
0x1800452a4  test    rax, rax
0x1800452a7  jz      loc_180045377
0x1800452ad  mov     rsi, [rax+8]
0x1800452b1  test    rsi, rsi
0x1800452b4  jz      loc_180045377
0x1800452ba  cmp     dword ptr [rbx+58h], 1
0x1800452be  jnz     short loc_1800452DB
0x1800452c0  mov     rcx, [rbx+60h]
0x1800452c4  mov     rcx, [rcx]; hCertStore
0x1800452c7  call    cs:__imp_CertDuplicateStore
0x1800452cd  mov     rdi, rax
0x1800452d0  test    rax, rax
0x1800452d3  jz      loc_180045377
0x1800452d9  jmp     short loc_180045323
0x1800452db  xor     edx, edx; dwEncodingType
0x1800452dd  mov     [rsp+88h+pvPara], 0; pvPara
0x1800452e6  xor     r9d, r9d; dwFlags
0x1800452e9  xor     r8d, r8d; hCryptProv
0x1800452ec  lea     ecx, [rdx+0Bh]; lpszStoreProvider
0x1800452ef  call    cs:__imp_CertOpenStore
0x1800452f5  mov     rdi, rax
0x1800452f8  test    rax, rax
0x1800452fb  jz      short loc_180045377
0x1800452fd  xor     ebp, ebp
0x1800452ff  cmp     [rbx+58h], ebp
0x180045302  jbe     short loc_180045323
0x180045304  mov     rdx, [rbx+60h]
0x180045308  xor     r9d, r9d; dwPriority
0x18004530b  mov     rcx, rdi; hCollectionStore
0x18004530e  mov     rdx, [rdx+rbp*8]; hSiblingStore
0x180045312  lea     r8d, [r9+1]; dwUpdateFlags
0x180045316  call    cs:__imp_CertAddStoreToCollection
0x18004531c  inc     ebp
0x18004531e  cmp     ebp, [rbx+58h]
0x180045321  jb      short loc_180045304
0x180045323  mov     eax, [rbx+0C8h]
0x180045329  lea     rcx, [rsp+88h+arg_10]
0x180045331  mov     [rsp+88h+ppChainContext], rcx; ppChainContext
0x180045336  mov     r9, rdi; hAdditionalStore
0x180045339  shr     eax, 0Ah
0x18004533c  xor     r8d, r8d; pTime
0x18004533f  and     eax, 4
0x180045342  mov     [rsp+88h+pvReserved], 0; pvReserved
0x18004534b  mov     [rsp+88h+dwFlags], eax; dwFlags
0x18004534f  mov     rdx, rsi; pCertContext
0x180045352  lea     rax, [rsp+88h+pChainPara]
0x180045357  mov     [rsp+88h+pChainPara.cbSize], 20h ; ' '
0x18004535f  xor     ecx, ecx; hChainEngine
0x180045361  mov     [rsp+88h+pvPara], rax; pChainPara
0x180045366  call    cs:__imp_CertGetCertificateChain
0x18004536c  xor     edx, edx; dwFlags
0x18004536e  mov     rcx, rdi; hCertStore
0x180045371  call    cs:__imp_CertCloseStore
0x180045377  mov     rax, [rsp+88h+arg_10]
0x18004537f  add     rsp, 68h
0x180045383  pop     rdi
0x180045384  pop     rsi
0x180045385  pop     rbp
0x180045386  pop     rbx
0x180045387  retn
```
