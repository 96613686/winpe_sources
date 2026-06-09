# GetSignersFromCertContext

- ea: `0x18004d044`
- end: `0x18004d244`
- name: `GetSignersFromCertContext`
- size: `512`
- prototype: `__int64 __fastcall(void *pvPara, PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004cac8`

## callees

- `0x180027a14`
- `0x18004cb48`
- `0x18004d044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d10e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d10e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d169`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d169`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d224`
- `CRYPT32!CertGetCertificateChain` at `0x18004d104`
- `CRYPT32!CertGetCertificateChain` at `0x18004d104`
- `CRYPT32!CertCloseStore` at `0x18004d203`
- `CRYPT32!CertCloseStore` at `0x18004d203`
- `CRYPT32!CertFreeCertificateChain` at `0x18004d216`
- `CRYPT32!CertFreeCertificateChain` at `0x18004d216`
- `CRYPT32!CertOpenStore` at `0x18004d08f`
- `CRYPT32!CertOpenStore` at `0x18004d08f`

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
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+40h] [rbp-48h] BYREF
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
                v6 = FillSignerInfoFromCert_0((*v16->rgpChain)->rgpElement[v17]->pCertContext);
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
0x18004d044  mov     rax, rsp
0x18004d047  mov     [rax+18h], r8
0x18004d04b  push    rbx
0x18004d04c  push    rbp
0x18004d04d  push    rsi
0x18004d04e  push    rdi
0x18004d04f  sub     rsp, 68h
0x18004d053  mov     qword ptr [rax+18h], 0
0x18004d05b  xorps   xmm0, xmm0
0x18004d05e  mov     rdi, r9
0x18004d061  mov     rbx, rdx
0x18004d064  movups  xmmword ptr [rax-48h], xmm0
0x18004d068  movups  xmmword ptr [rax-38h], xmm0
0x18004d06c  test    r9, r9
0x18004d06f  jnz     short loc_18004D07B
0x18004d071  mov     ebx, 0C00000F1h
0x18004d076  jmp     loc_18004D220
0x18004d07b  xor     r9d, r9d; dwFlags
0x18004d07e  mov     [rsp+88h+pvPara], rcx; pvPara
0x18004d083  xor     r8d, r8d; hCryptProv
0x18004d086  mov     edx, 10001h; dwEncodingType
0x18004d08b  lea     ecx, [r9+1]; lpszStoreProvider
0x18004d08f  call    cs:__imp_CertOpenStore
0x18004d095  mov     rbp, rax
0x18004d098  test    rax, rax
0x18004d09b  jnz     short loc_18004D0BF
0x18004d09d  call    cs:__imp_GetLastError
0x18004d0a3  mov     ebx, eax
0x18004d0a5  test    eax, eax
0x18004d0a7  jle     short loc_18004D0B2
0x18004d0a9  movzx   ebx, ax
0x18004d0ac  or      ebx, 80070000h
0x18004d0b2  btr     ebx, 1Ch
0x18004d0b6  bts     ebx, 1Eh
0x18004d0ba  jmp     loc_18004D209
0x18004d0bf  xor     r8d, r8d; pTime
0x18004d0c2  mov     [rsp+88h+pChainPara.cbSize], 20h ; ' '
0x18004d0ca  lea     rax, [rsp+88h+pChainContext]
0x18004d0d2  mov     [rsp+88h+pChainPara.RequestedUsage.dwType], 0
0x18004d0da  mov     [rsp+88h+ppChainContext], rax; ppChainContext
0x18004d0df  mov     r9, rbp; hAdditionalStore
0x18004d0e2  mov     [rsp+88h+pvReserved], 0; pvReserved
0x18004d0eb  lea     rax, [rsp+88h+pChainPara]
0x18004d0f0  lea     ecx, [r8+1]; hChainEngine
0x18004d0f4  mov     [rsp+88h+dwFlags], 400000C0h; dwFlags
0x18004d0fc  mov     rdx, rbx; pCertContext
0x18004d0ff  mov     [rsp+88h+pvPara], rax; pChainPara
0x18004d104  call    cs:__imp_CertGetCertificateChain
0x18004d10a  test    eax, eax
0x18004d10c  jnz     short loc_18004D130
0x18004d10e  call    cs:__imp_GetLastError
0x18004d114  mov     ebx, eax
0x18004d116  test    eax, eax
0x18004d118  jle     short loc_18004D123
0x18004d11a  movzx   ebx, ax
0x18004d11d  or      ebx, 80070000h
0x18004d123  btr     ebx, 1Ch
0x18004d127  bts     ebx, 1Eh
0x18004d12b  jmp     loc_18004D1FE
0x18004d130  mov     rax, [rsp+88h+pChainContext]
0x18004d138  mov     rcx, [rax+10h]
0x18004d13c  mov     rax, [rcx]
0x18004d13f  cmp     dword ptr [rax+0Ch], 0
0x18004d143  jnz     short loc_18004D14F
0x18004d145  mov     ebx, 0C0000001h
0x18004d14a  jmp     loc_18004D1FE
0x18004d14f  test    byte ptr [rax+4], 1Ch
0x18004d153  jnz     loc_18004D1F9
0x18004d159  mov     eax, [rax+0Ch]
0x18004d15c  mov     ecx, 40h ; '@'; uFlags
0x18004d161  lea     rdx, [rax+rax*2]
0x18004d165  shl     rdx, 4; uBytes
0x18004d169  call    cs:__imp_LocalAlloc
0x18004d16f  mov     [rdi+18h], rax
0x18004d173  test    rax, rax
0x18004d176  jnz     short loc_18004D17F
0x18004d178  mov     ebx, 0C0000017h
0x18004d17d  jmp     short loc_18004D1FE
0x18004d17f  mov     r9, [rsp+88h+pChainContext]
0x18004d187  xor     esi, esi
0x18004d189  mov     rax, [r9+10h]
0x18004d18d  mov     rcx, [rax]
0x18004d190  mov     eax, [rcx+0Ch]
0x18004d193  mov     [rdi+20h], eax
0x18004d196  test    eax, eax
0x18004d198  jz      short loc_18004D1D7
0x18004d19a  mov     rax, [r9+10h]
0x18004d19e  lea     rdx, [rsi+rsi*2]
0x18004d1a2  shl     rdx, 4
0x18004d1a6  add     rdx, [rdi+18h]
0x18004d1aa  mov     rcx, [rax]
0x18004d1ad  mov     rax, [rcx+10h]
0x18004d1b1  mov     rcx, [rax+rsi*8]
0x18004d1b5  mov     rcx, [rcx+8]; pCertContext
0x18004d1b9  call    FillSignerInfoFromCert_0
0x18004d1be  mov     ebx, eax
0x18004d1c0  test    eax, eax
0x18004d1c2  js      short loc_18004D1FE
0x18004d1c4  mov     eax, [rdi+20h]
0x18004d1c7  inc     esi
0x18004d1c9  cmp     esi, eax
0x18004d1cb  jnb     short loc_18004D1D9
0x18004d1cd  mov     r9, [rsp+88h+pChainContext]
0x18004d1d5  jmp     short loc_18004D19A
0x18004d1d7  xor     ebx, ebx
0x18004d1d9  mov     rcx, [rdi+18h]
0x18004d1dd  dec     eax
0x18004d1df  lea     rax, [rax+rax*2]
0x18004d1e3  add     rax, rax
0x18004d1e6  mov     edx, [rcx+rax*8+4]; Size
0x18004d1ea  mov     rcx, [rcx+rax*8+8]; Buf2
0x18004d1ef  call    SIPolicyRootCertHashToKnownRoot
0x18004d1f4  mov     [rdi+24h], eax
0x18004d1f7  jmp     short loc_18004D1FE
0x18004d1f9  mov     ebx, 0C0000428h
0x18004d1fe  xor     edx, edx; dwFlags
0x18004d200  mov     rcx, rbp; hCertStore
0x18004d203  call    cs:__imp_CertCloseStore
0x18004d209  mov     rcx, [rsp+88h+pChainContext]; pChainContext
0x18004d211  test    rcx, rcx
0x18004d214  jz      short loc_18004D21C
0x18004d216  call    cs:__imp_CertFreeCertificateChain
0x18004d21c  test    ebx, ebx
0x18004d21e  jns     short loc_18004D239
0x18004d220  mov     rcx, [rdi+18h]; hMem
0x18004d224  call    cs:__imp_LocalFree
0x18004d22a  mov     qword ptr [rdi+18h], 0
0x18004d232  mov     dword ptr [rdi+20h], 0
0x18004d239  mov     eax, ebx
0x18004d23b  add     rsp, 68h
0x18004d23f  pop     rdi
0x18004d240  pop     rsi
0x18004d241  pop     rbp
0x18004d242  pop     rbx
0x18004d243  retn
```
