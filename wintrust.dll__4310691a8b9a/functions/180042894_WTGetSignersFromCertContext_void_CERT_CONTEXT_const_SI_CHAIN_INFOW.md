# WTGetSignersFromCertContext(void *,_CERT_CONTEXT const *,_SI_CHAIN_INFOW *)

- ea: `0x180042894`
- end: `0x180042a43`
- name: `?WTGetSignersFromCertContext@@YAJPEAXPEBU_CERT_CONTEXT@@PEAU_SI_CHAIN_INFOW@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(void *pvPara, PCCERT_CONTEXT pCertContext, struct _SI_CHAIN_INFOW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180043aa0`

## callees

- `0x18002498c`
- `0x180027a14`
- `0x180042894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004293c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004293c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042975`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042975`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042a23`
- `CRYPT32!CertGetCertificateChain` at `0x180042932`
- `CRYPT32!CertGetCertificateChain` at `0x180042932`
- `CRYPT32!CertCloseStore` at `0x180042a02`
- `CRYPT32!CertCloseStore` at `0x180042a02`
- `CRYPT32!CertFreeCertificateChain` at `0x180042a15`
- `CRYPT32!CertFreeCertificateChain` at `0x180042a15`
- `CRYPT32!CertOpenStore` at `0x1800428dc`
- `CRYPT32!CertOpenStore` at `0x1800428dc`

## pseudocode

```c
__int64 __fastcall WTGetSignersFromCertContext(void *pvPara, PCCERT_CONTEXT pCertContext, struct _SI_CHAIN_INFOW *a3)
{
  int v6; // edi
  HCERTSTORE v7; // rax
  void *v8; // rbp
  PCERT_SIMPLE_CHAIN *rgpChain; // rcx
  HLOCAL v10; // rax
  PCCERT_CHAIN_CONTEXT v11; // r10
  __int64 v12; // rsi
  unsigned int v13; // eax
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-48h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+A0h] [rbp+18h] BYREF

  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  if ( !a3 )
    return 2147942487LL;
  v6 = 0;
  v7 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, pvPara);
  v8 = v7;
  if ( v7 )
  {
    pChainPara.cbSize = 32;
    pChainPara.RequestedUsage.dwType = 0;
    if ( CertGetCertificateChain((HCERTCHAINENGINE)1, pCertContext, 0, v7, &pChainPara, 0x400000C0u, 0, &pChainContext) )
    {
      rgpChain = pChainContext->rgpChain;
      if ( (*rgpChain)->cElement )
      {
        v10 = LocalAlloc(0x40u, 48LL * (*rgpChain)->cElement);
        *((_QWORD *)a3 + 3) = v10;
        if ( v10 )
        {
          v11 = pChainContext;
          v12 = 0;
          *((_DWORD *)a3 + 8) = (*pChainContext->rgpChain)->cElement;
          while ( 1 )
          {
            v13 = *((_DWORD *)a3 + 8);
            if ( (unsigned int)v12 >= v13 )
              break;
            v6 = FillSignerInfoFromCert((*v11->rgpChain)->rgpElement[v12]->pCertContext);
            if ( v6 < 0 )
              goto LABEL_16;
            v11 = pChainContext;
            v12 = (unsigned int)(v12 + 1);
          }
          *((_DWORD *)a3 + 9) = SIPolicyRootCertHashToKnownRoot(
                                  *(void **)(*((_QWORD *)a3 + 3) + 48LL * (v13 - 1) + 8),
                                  *(unsigned int *)(*((_QWORD *)a3 + 3) + 48LL * (v13 - 1) + 4));
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = -2147467259;
      }
    }
    else
    {
      GetLastError();
    }
LABEL_16:
    CertCloseStore(v8, 0);
  }
  else
  {
    GetLastError();
  }
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v6 < 0 )
  {
    LocalFree(*((HLOCAL *)a3 + 3));
    *((_QWORD *)a3 + 3) = 0;
    *((_DWORD *)a3 + 8) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180042894  mov     rax, rsp
0x180042897  push    rbx
0x180042898  push    rbp
0x180042899  push    rsi
0x18004289a  push    rdi
0x18004289b  sub     rsp, 68h
0x18004289f  mov     qword ptr [rax+18h], 0
0x1800428a7  xorps   xmm0, xmm0
0x1800428aa  mov     rbx, r8
0x1800428ad  mov     rsi, rdx
0x1800428b0  movups  xmmword ptr [rax-48h], xmm0
0x1800428b4  movups  xmmword ptr [rax-38h], xmm0
0x1800428b8  test    r8, r8
0x1800428bb  jnz     short loc_1800428C7
0x1800428bd  mov     eax, 80070057h
0x1800428c2  jmp     loc_180042A3A
0x1800428c7  mov     [rsp+88h+pvPara], rcx; pvPara
0x1800428cc  xor     edi, edi
0x1800428ce  xor     r9d, r9d; dwFlags
0x1800428d1  xor     r8d, r8d; hCryptProv
0x1800428d4  mov     edx, 10001h; dwEncodingType
0x1800428d9  lea     ecx, [rdi+1]; lpszStoreProvider
0x1800428dc  call    cs:__imp_CertOpenStore
0x1800428e2  mov     rbp, rax
0x1800428e5  test    rax, rax
0x1800428e8  jnz     short loc_1800428F5
0x1800428ea  call    cs:__imp_GetLastError
0x1800428f0  jmp     loc_180042A08
0x1800428f5  xor     r8d, r8d; pTime
0x1800428f8  mov     [rsp+88h+pChainPara.cbSize], 20h ; ' '
0x180042900  lea     rax, [rsp+88h+pChainContext]
0x180042908  mov     [rsp+88h+pChainPara.RequestedUsage.dwType], edi
0x18004290c  mov     [rsp+88h+ppChainContext], rax; ppChainContext
0x180042911  mov     r9, rbp; hAdditionalStore
0x180042914  mov     [rsp+88h+pvReserved], rdi; pvReserved
0x180042919  lea     rax, [rsp+88h+pChainPara]
0x18004291e  lea     ecx, [r8+1]; hChainEngine
0x180042922  mov     [rsp+88h+dwFlags], 400000C0h; dwFlags
0x18004292a  mov     rdx, rsi; pCertContext
0x18004292d  mov     [rsp+88h+pvPara], rax; pChainPara
0x180042932  call    cs:__imp_CertGetCertificateChain
0x180042938  test    eax, eax
0x18004293a  jnz     short loc_180042947
0x18004293c  call    cs:__imp_GetLastError
0x180042942  jmp     loc_1800429FD
0x180042947  mov     rax, [rsp+88h+pChainContext]
0x18004294f  mov     rcx, [rax+10h]
0x180042953  mov     rax, [rcx]
0x180042956  cmp     [rax+0Ch], edi
0x180042959  jnz     short loc_180042965
0x18004295b  mov     edi, 80004005h
0x180042960  jmp     loc_1800429FD
0x180042965  mov     eax, [rax+0Ch]
0x180042968  mov     ecx, 40h ; '@'; uFlags
0x18004296d  lea     rdx, [rax+rax*2]
0x180042971  shl     rdx, 4; uBytes
0x180042975  call    cs:__imp_LocalAlloc
0x18004297b  mov     [rbx+18h], rax
0x18004297f  test    rax, rax
0x180042982  jnz     short loc_18004298B
0x180042984  mov     edi, 8007000Eh
0x180042989  jmp     short loc_1800429FD
0x18004298b  mov     r10, [rsp+88h+pChainContext]
0x180042993  xor     esi, esi
0x180042995  mov     rax, [r10+10h]
0x180042999  mov     rcx, [rax]
0x18004299c  mov     eax, [rcx+0Ch]
0x18004299f  mov     [rbx+20h], eax
0x1800429a2  mov     eax, [rbx+20h]
0x1800429a5  mov     r9, [rbx+18h]
0x1800429a9  cmp     esi, eax
0x1800429ab  jnb     short loc_1800429E2
0x1800429ad  mov     rax, [r10+10h]
0x1800429b1  lea     rdx, [rsi+rsi*2]
0x1800429b5  shl     rdx, 4
0x1800429b9  add     rdx, r9
0x1800429bc  mov     rcx, [rax]
0x1800429bf  mov     rax, [rcx+10h]
0x1800429c3  mov     rcx, [rax+rsi*8]
0x1800429c7  mov     rcx, [rcx+8]; pCertContext
0x1800429cb  call    FillSignerInfoFromCert
0x1800429d0  mov     edi, eax
0x1800429d2  test    eax, eax
0x1800429d4  js      short loc_1800429FD
0x1800429d6  mov     r10, [rsp+88h+pChainContext]
0x1800429de  inc     esi
0x1800429e0  jmp     short loc_1800429A2
0x1800429e2  dec     eax
0x1800429e4  lea     rcx, [rax+rax*2]
0x1800429e8  add     rcx, rcx
0x1800429eb  mov     edx, [r9+rcx*8+4]; Size
0x1800429f0  mov     rcx, [r9+rcx*8+8]; Buf2
0x1800429f5  call    SIPolicyRootCertHashToKnownRoot
0x1800429fa  mov     [rbx+24h], eax
0x1800429fd  xor     edx, edx; dwFlags
0x1800429ff  mov     rcx, rbp; hCertStore
0x180042a02  call    cs:__imp_CertCloseStore
0x180042a08  mov     rcx, [rsp+88h+pChainContext]; pChainContext
0x180042a10  test    rcx, rcx
0x180042a13  jz      short loc_180042A1B
0x180042a15  call    cs:__imp_CertFreeCertificateChain
0x180042a1b  test    edi, edi
0x180042a1d  jns     short loc_180042A38
0x180042a1f  mov     rcx, [rbx+18h]; hMem
0x180042a23  call    cs:__imp_LocalFree
0x180042a29  mov     qword ptr [rbx+18h], 0
0x180042a31  mov     dword ptr [rbx+20h], 0
0x180042a38  mov     eax, edi
0x180042a3a  add     rsp, 68h
0x180042a3e  pop     rdi
0x180042a3f  pop     rsi
0x180042a40  pop     rbp
0x180042a41  pop     rbx
0x180042a42  retn
```
