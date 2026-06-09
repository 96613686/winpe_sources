# GetSignersFromCertContext

- ea: `0x18003d080`
- end: `0x18003d280`
- name: `GetSignersFromCertContext`
- size: `512`
- prototype: `__int64 __fastcall(void *pvPara, PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003cb04`

## callees

- `0x18003c710`
- `0x18003cb84`
- `0x18003d080`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d260`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d1a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d14a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d14a`
- `CRYPT32!CertFreeCertificateChain` at `0x18003d252`
- `CRYPT32!CertFreeCertificateChain` at `0x18003d252`
- `CRYPT32!CertCloseStore` at `0x18003d23f`
- `CRYPT32!CertCloseStore` at `0x18003d23f`
- `CRYPT32!CertOpenStore` at `0x18003d0cb`
- `CRYPT32!CertOpenStore` at `0x18003d0cb`
- `CRYPT32!CertGetCertificateChain` at `0x18003d140`
- `CRYPT32!CertGetCertificateChain` at `0x18003d140`

## pseudocode

```c
__int64 __fastcall GetSignersFromCertContext(void *pvPara, PCCERT_CONTEXT pCertContext, __int64 a3, __int64 a4)
{
  signed int v6; // ebx
  HCERTSTORE v7; // rax
  void *v8; // rbp
  signed int v9; // eax
  unsigned int v10; // ebx
  signed int LastError; // eax
  unsigned int v12; // ebx
  PCERT_SIMPLE_CHAIN *rgpChain; // rcx
  PCERT_SIMPLE_CHAIN v14; // rax
  HLOCAL v15; // rax
  PCCERT_CHAIN_CONTEXT v16; // r9
  __int64 v17; // rsi
  DWORD cElement; // eax
  _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-48h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+A0h] [rbp+18h] BYREF

  pChainContext = 0;
  memset(&pChainPara, 0, sizeof(pChainPara));
  if ( !a4 )
  {
    v6 = -1073741583;
LABEL_27:
    LocalFree(*(HLOCAL *)(a4 + 24));
    *(_QWORD *)(a4 + 24) = 0;
    *(_DWORD *)(a4 + 32) = 0;
    return (unsigned int)v6;
  }
  v7 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, pvPara);
  v8 = v7;
  if ( v7 )
  {
    pChainPara.cbSize = 32;
    pChainPara.RequestedUsage.dwType = 0;
    if ( CertGetCertificateChain((HCERTCHAINENGINE)1, pCertContext, 0, v7, &pChainPara, 0x400000C0u, 0, &pChainContext) )
    {
      rgpChain = pChainContext->rgpChain;
      v14 = *rgpChain;
      if ( (*rgpChain)->cElement )
      {
        if ( (v14->TrustStatus.dwErrorStatus & 0x1C) != 0 )
        {
          v6 = -1073740760;
        }
        else
        {
          v15 = LocalAlloc(0x40u, 48LL * v14->cElement);
          *(_QWORD *)(a4 + 24) = v15;
          if ( v15 )
          {
            v16 = pChainContext;
            v17 = 0;
            cElement = (*pChainContext->rgpChain)->cElement;
            *(_DWORD *)(a4 + 32) = cElement;
            if ( cElement )
            {
              while ( 1 )
              {
                v6 = FillSignerInfoFromCert((*v16->rgpChain)->rgpElement[v17]->pCertContext);
                if ( v6 < 0 )
                  break;
                cElement = *(_DWORD *)(a4 + 32);
                v17 = (unsigned int)(v17 + 1);
                if ( (unsigned int)v17 >= cElement )
                  goto LABEL_21;
                v16 = pChainContext;
              }
            }
            else
            {
              v6 = 0;
LABEL_21:
              *(_DWORD *)(a4 + 36) = SIPolicyRootCertHashToKnownRoot(
                                       *(void **)(*(_QWORD *)(a4 + 24) + 48LL * (cElement - 1) + 8),
                                       *(unsigned int *)(*(_QWORD *)(a4 + 24) + 48LL * (cElement - 1) + 4));
            }
          }
          else
          {
            v6 = -1073741801;
          }
        }
      }
      else
      {
        v6 = -1073741823;
      }
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v6 = v12 & 0xAFFFFFFF | 0x40000000;
    }
    CertCloseStore(v8, 0);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v6 = v10 & 0xAFFFFFFF | 0x40000000;
  }
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v6 < 0 )
    goto LABEL_27;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003d080  mov     rax, rsp
0x18003d083  mov     [rax+18h], r8
0x18003d087  push    rbx
0x18003d088  push    rbp
0x18003d089  push    rsi
0x18003d08a  push    rdi
0x18003d08b  sub     rsp, 68h
0x18003d08f  mov     qword ptr [rax+18h], 0
0x18003d097  xorps   xmm0, xmm0
0x18003d09a  mov     rdi, r9
0x18003d09d  mov     rbx, rdx
0x18003d0a0  movups  xmmword ptr [rax-48h], xmm0
0x18003d0a4  movups  xmmword ptr [rax-38h], xmm0
0x18003d0a8  test    r9, r9
0x18003d0ab  jnz     short loc_18003D0B7
0x18003d0ad  mov     ebx, 0C00000F1h
0x18003d0b2  jmp     loc_18003D25C
0x18003d0b7  xor     r9d, r9d; dwFlags
0x18003d0ba  mov     [rsp+88h+pvPara], rcx; pvPara
0x18003d0bf  xor     r8d, r8d; hCryptProv
0x18003d0c2  mov     edx, 10001h; dwEncodingType
0x18003d0c7  lea     ecx, [r9+1]; lpszStoreProvider
0x18003d0cb  call    cs:__imp_CertOpenStore
0x18003d0d1  mov     rbp, rax
0x18003d0d4  test    rax, rax
0x18003d0d7  jnz     short loc_18003D0FB
0x18003d0d9  call    cs:__imp_GetLastError
0x18003d0df  mov     ebx, eax
0x18003d0e1  test    eax, eax
0x18003d0e3  jle     short loc_18003D0EE
0x18003d0e5  movzx   ebx, ax
0x18003d0e8  or      ebx, 80070000h
0x18003d0ee  btr     ebx, 1Ch
0x18003d0f2  bts     ebx, 1Eh
0x18003d0f6  jmp     loc_18003D245
0x18003d0fb  xor     r8d, r8d; pTime
0x18003d0fe  mov     [rsp+88h+pChainPara.cbSize], 20h ; ' '
0x18003d106  lea     rax, [rsp+88h+pChainContext]
0x18003d10e  mov     [rsp+88h+pChainPara.RequestedUsage.dwType], 0
0x18003d116  mov     [rsp+88h+ppChainContext], rax; ppChainContext
0x18003d11b  mov     r9, rbp; hAdditionalStore
0x18003d11e  mov     [rsp+88h+pvReserved], 0; pvReserved
0x18003d127  lea     rax, [rsp+88h+pChainPara]
0x18003d12c  lea     ecx, [r8+1]; hChainEngine
0x18003d130  mov     [rsp+88h+dwFlags], 400000C0h; dwFlags
0x18003d138  mov     rdx, rbx; pCertContext
0x18003d13b  mov     [rsp+88h+pvPara], rax; pChainPara
0x18003d140  call    cs:__imp_CertGetCertificateChain
0x18003d146  test    eax, eax
0x18003d148  jnz     short loc_18003D16C
0x18003d14a  call    cs:__imp_GetLastError
0x18003d150  mov     ebx, eax
0x18003d152  test    eax, eax
0x18003d154  jle     short loc_18003D15F
0x18003d156  movzx   ebx, ax
0x18003d159  or      ebx, 80070000h
0x18003d15f  btr     ebx, 1Ch
0x18003d163  bts     ebx, 1Eh
0x18003d167  jmp     loc_18003D23A
0x18003d16c  mov     rax, [rsp+88h+pChainContext]
0x18003d174  mov     rcx, [rax+10h]
0x18003d178  mov     rax, [rcx]
0x18003d17b  cmp     dword ptr [rax+0Ch], 0
0x18003d17f  jnz     short loc_18003D18B
0x18003d181  mov     ebx, 0C0000001h
0x18003d186  jmp     loc_18003D23A
0x18003d18b  test    byte ptr [rax+4], 1Ch
0x18003d18f  jnz     loc_18003D235
0x18003d195  mov     eax, [rax+0Ch]
0x18003d198  mov     ecx, 40h ; '@'; uFlags
0x18003d19d  lea     rdx, [rax+rax*2]
0x18003d1a1  shl     rdx, 4; uBytes
0x18003d1a5  call    cs:__imp_LocalAlloc
0x18003d1ab  mov     [rdi+18h], rax
0x18003d1af  test    rax, rax
0x18003d1b2  jnz     short loc_18003D1BB
0x18003d1b4  mov     ebx, 0C0000017h
0x18003d1b9  jmp     short loc_18003D23A
0x18003d1bb  mov     r9, [rsp+88h+pChainContext]
0x18003d1c3  xor     esi, esi
0x18003d1c5  mov     rax, [r9+10h]
0x18003d1c9  mov     rcx, [rax]
0x18003d1cc  mov     eax, [rcx+0Ch]
0x18003d1cf  mov     [rdi+20h], eax
0x18003d1d2  test    eax, eax
0x18003d1d4  jz      short loc_18003D213
0x18003d1d6  mov     rax, [r9+10h]
0x18003d1da  lea     rdx, [rsi+rsi*2]
0x18003d1de  shl     rdx, 4
0x18003d1e2  add     rdx, [rdi+18h]
0x18003d1e6  mov     rcx, [rax]
0x18003d1e9  mov     rax, [rcx+10h]
0x18003d1ed  mov     rcx, [rax+rsi*8]
0x18003d1f1  mov     rcx, [rcx+8]; pCertContext
0x18003d1f5  call    FillSignerInfoFromCert
0x18003d1fa  mov     ebx, eax
0x18003d1fc  test    eax, eax
0x18003d1fe  js      short loc_18003D23A
0x18003d200  mov     eax, [rdi+20h]
0x18003d203  inc     esi
0x18003d205  cmp     esi, eax
0x18003d207  jnb     short loc_18003D215
0x18003d209  mov     r9, [rsp+88h+pChainContext]
0x18003d211  jmp     short loc_18003D1D6
0x18003d213  xor     ebx, ebx
0x18003d215  mov     rcx, [rdi+18h]
0x18003d219  dec     eax
0x18003d21b  lea     rax, [rax+rax*2]
0x18003d21f  add     rax, rax
0x18003d222  mov     edx, [rcx+rax*8+4]; Size
0x18003d226  mov     rcx, [rcx+rax*8+8]; Buf2
0x18003d22b  call    SIPolicyRootCertHashToKnownRoot
0x18003d230  mov     [rdi+24h], eax
0x18003d233  jmp     short loc_18003D23A
0x18003d235  mov     ebx, 0C0000428h
0x18003d23a  xor     edx, edx; dwFlags
0x18003d23c  mov     rcx, rbp; hCertStore
0x18003d23f  call    cs:__imp_CertCloseStore
0x18003d245  mov     rcx, [rsp+88h+pChainContext]; pChainContext
0x18003d24d  test    rcx, rcx
0x18003d250  jz      short loc_18003D258
0x18003d252  call    cs:__imp_CertFreeCertificateChain
0x18003d258  test    ebx, ebx
0x18003d25a  jns     short loc_18003D275
0x18003d25c  mov     rcx, [rdi+18h]; hMem
0x18003d260  call    cs:__imp_LocalFree
0x18003d266  mov     qword ptr [rdi+18h], 0
0x18003d26e  mov     dword ptr [rdi+20h], 0
0x18003d275  mov     eax, ebx
0x18003d277  add     rsp, 68h
0x18003d27b  pop     rdi
0x18003d27c  pop     rsi
0x18003d27d  pop     rbp
0x18003d27e  pop     rbx
0x18003d27f  retn
```
