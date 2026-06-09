# PopulateRenewalChain

- ea: `0x180023e54`
- end: `0x18002448b`
- name: `PopulateRenewalChain`
- size: `1591`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180022dd0`
- `0x1800233b0`

## callees

- `0x18001fbd0`
- `0x1800204f6`
- `0x180022a24`
- `0x180023e54`
- `0x180024520`
- `0x180024550`
- `0x180024594`
- `0x180024f38`
- `0x1800250b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002417a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002417a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024283`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024283`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800243c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800243c6`
- `CRYPT32!CertOpenStore` at `0x180023ec5`
- `CRYPT32!CertOpenStore` at `0x180023ec5`
- `CRYPT32!CertFindCertificateInStore` at `0x180023f99`
- `CRYPT32!CertFindCertificateInStore` at `0x1800240d5`
- `CRYPT32!CertFindCertificateInStore` at `0x180023f99`
- `CRYPT32!CertFindCertificateInStore` at `0x1800240d5`
- `CRYPT32!CertCloseStore` at `0x1800243df`
- `CRYPT32!CertCloseStore` at `0x1800243df`
- `CRYPT32!CertFreeCertificateContext` at `0x180024159`
- `CRYPT32!CertFreeCertificateContext` at `0x1800243ab`
- `CRYPT32!CertFreeCertificateContext` at `0x180024159`
- `CRYPT32!CertFreeCertificateContext` at `0x1800243ab`
- `CRYPT32!CryptBinaryToStringW` at `0x18002410e`
- `CRYPT32!CryptBinaryToStringW` at `0x180024306`
- `CRYPT32!CryptBinaryToStringW` at `0x18002410e`
- `CRYPT32!CryptBinaryToStringW` at `0x180024306`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002405a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002405a`

## pseudocode

```c
__int64 __fastcall PopulateRenewalChain(__int64 a1)
{
  bool v1; // zf
  void *v3; // rsi
  DWORD LastError; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rsi
  DWORD *v11; // rdi
  __int64 v12; // r12
  __int64 i; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  const CERT_CONTEXT *v16; // r14
  DWORD *v17; // r15
  DWORD v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  _QWORD *v22; // rcx
  WCHAR *v23; // rax
  WCHAR *v24; // rsi
  WCHAR *v25; // r12
  __int64 v26; // r15
  DWORD v27; // eax
  unsigned int v29; // [rsp+30h] [rbp-D0h]
  int v30; // [rsp+34h] [rbp-CCh]
  PCCERT_CONTEXT CertificateInStore; // [rsp+38h] [rbp-C8h]
  DWORD *v32; // [rsp+38h] [rbp-C8h]
  const CERT_CONTEXT *pCertContext; // [rsp+40h] [rbp-C0h]
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-B8h]
  BYTE *pbBinary[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pvFindPara; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbBinary[20]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v38[120]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = *(_QWORD *)(a1 + 24) == 0;
  pvFindPara = 0;
  *(_OWORD *)pbBinary = 0;
  if ( v1 || !*(_QWORD *)(a1 + 64) )
  {
    v3 = 0;
    v5 = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_76;
    }
    v9 = 56;
    goto LABEL_19;
  }
  hCertStore = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, *(const void **)(a1 + 64));
  v3 = hCertStore;
  if ( !hCertStore )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v7 = 57;
LABEL_8:
      WPP_SF_d(v6[2], v7, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, LastError);
      goto LABEL_76;
    }
    goto LABEL_76;
  }
  LastError = LmConvertCryptStringToBinary(*(LPCWSTR *)(a1 + 24), (DWORD *)&pvFindPara);
  v5 = LastError;
  if ( !LastError )
  {
    pCertContext = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( pCertContext )
    {
      v10 = 0;
      v11 = cbBinary;
      v12 = 0;
      v29 = 0;
      v30 = 0;
      for ( i = 20; i; --i )
        *v11++ = 20;
      memset_0(v38, 0, 0x50u);
      v16 = pCertContext;
      while ( 1 )
      {
        if ( (unsigned int)v10 >= 0x14 )
          goto LABEL_51;
        if ( !CertGetCertificateContextProperty(v16, 0x40u, &v38[5 * v10 + 20], &cbBinary[v10]) )
          break;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v16);
        }
        LODWORD(pbBinary[0]) = cbBinary[v10];
        pbBinary[1] = (BYTE *)&v38[5 * v10 + 20];
        CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, pbBinary, 0);
        if ( !CertificateInStore )
        {
          v5 = 1168;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
          }
          goto LABEL_75;
        }
        v17 = &v38[v10];
        if ( !CryptBinaryToStringW(pbBinary[1], (DWORD)pbBinary[0], 0x4000000Cu, 0, v17) )
        {
          v18 = GetLastError();
          v5 = v18;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_75;
          }
          v20 = 66;
LABEL_41:
          v21 = v18;
          goto LABEL_42;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, *v17);
        }
        v12 = *v17 + (unsigned int)v12;
        v30 = v12;
        CertFreeCertificateContext(v16);
        v16 = CertificateInStore;
        v10 = (unsigned int)(v10 + 1);
        v29 = v10;
        pCertContext = CertificateInStore;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v16);
LABEL_51:
          v22 = WPP_GLOBAL_Control;
        }
        if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 && *((_BYTE *)v22 + 25) >= 2u )
          WPP_SF_Dd(v22[2], v14, v15, (unsigned int)v10, v12);
      }
      if ( !(_DWORD)v10 )
      {
        *(_QWORD *)(a1 + 72) = 0;
        goto LABEL_75;
      }
      v23 = (WCHAR *)LocalAlloc(0x40u, 2 * v12 + 2);
      v24 = v23;
      if ( !v23 )
      {
        v5 = 8;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_75;
        }
        v20 = 68;
        v21 = 8;
LABEL_42:
        WPP_SF_d(v19[2], v20, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v21);
        goto LABEL_75;
      }
      v25 = v23;
      v26 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v26 >= v29 )
        {
          v24[v30] = 0;
          *(_QWORD *)(a1 + 72) = v24;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              70,
              (unsigned int)&WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
              (_DWORD)v24,
              0);
          }
          goto LABEL_75;
        }
        v32 = &v38[v26];
        if ( !CryptBinaryToStringW((const BYTE *)&v38[5 * v26 + 20], cbBinary[v26], 0x4000000Cu, v25, v32) )
          break;
        v25[*v32] = 58;
        v26 = (unsigned int)(v26 + 1);
        v25 += *v32 + 1;
      }
      v18 = GetLastError();
      v5 = v18;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v20 = 69;
        goto LABEL_41;
      }
LABEL_75:
      CertFreeCertificateContext(pCertContext);
      v3 = hCertStore;
      goto LABEL_76;
    }
    v5 = 1168;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_76;
    }
    v9 = 59;
LABEL_19:
    WPP_SF_(v8[2], v9, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
    goto LABEL_76;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v7 = 58;
    goto LABEL_8;
  }
LABEL_76:
  if ( *((_QWORD *)&pvFindPara + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara + 1));
  if ( v3 )
  {
    if ( !CertCloseStore(v3, 2u) )
    {
      v27 = GetLastError();
      v5 = v27;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, v27);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180023e54  push    rbp
0x180023e56  push    rbx
0x180023e57  push    rsi
0x180023e58  push    rdi
0x180023e59  push    r12
0x180023e5b  push    r13
0x180023e5d  push    r14
0x180023e5f  push    r15
0x180023e61  lea     rbp, [rsp-1B8h]
0x180023e69  sub     rsp, 2B8h
0x180023e70  mov     rax, cs:__security_cookie
0x180023e77  xor     rax, rsp
0x180023e7a  mov     [rbp+1F0h+var_50], rax
0x180023e81  cmp     qword ptr [rcx+18h], 0
0x180023e86  xorps   xmm0, xmm0
0x180023e89  xorps   xmm1, xmm1
0x180023e8c  mov     r13, rcx
0x180023e8f  movups  [rsp+2F0h+pvFindPara], xmm0
0x180023e94  movups  xmmword ptr [rsp+2F0h+pbBinary], xmm1
0x180023e99  jz      loc_180024453
0x180023e9f  mov     rax, [rcx+40h]
0x180023ea3  test    rax, rax
0x180023ea6  jz      loc_180024453
0x180023eac  xor     r8d, r8d; hCryptProv
0x180023eaf  mov     [rsp+2F0h+pvPara], rax; pvPara
0x180023eb4  mov     edi, 10001h
0x180023eb9  mov     r9d, 28000h; dwFlags
0x180023ebf  mov     edx, edi; dwEncodingType
0x180023ec1  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180023ec5  call    cs:__imp_CertOpenStore
0x180023ecc  nop     dword ptr [rax+rax+00h]
0x180023ed1  mov     [rsp+2F0h+hCertStore], rax
0x180023ed6  mov     rsi, rax
0x180023ed9  test    rax, rax
0x180023edc  jnz     short loc_180023F32
0x180023ede  call    cs:__imp_GetLastError
0x180023ee5  nop     dword ptr [rax+rax+00h]
0x180023eea  mov     ebx, eax
0x180023eec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023ef3  lea     rdi, WPP_GLOBAL_Control
0x180023efa  cmp     rcx, rdi
0x180023efd  jz      loc_1800243BC
0x180023f03  test    byte ptr [rcx+1Ch], 2
0x180023f07  jz      loc_1800243BC
0x180023f0d  cmp     byte ptr [rcx+19h], 1
0x180023f11  jb      loc_1800243BC
0x180023f17  lea     edx, [rsi+39h]
0x180023f1a  mov     rcx, [rcx+10h]
0x180023f1e  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023f25  mov     r9d, eax
0x180023f28  call    WPP_SF_d
0x180023f2d  jmp     loc_1800243BC
0x180023f32  mov     rcx, [r13+18h]; pszString
0x180023f36  lea     rdx, [rsp+2F0h+pvFindPara]; pcbBinary
0x180023f3b  call    LmConvertCryptStringToBinary
0x180023f40  mov     ebx, eax
0x180023f42  test    eax, eax
0x180023f44  jz      short loc_180023F78
0x180023f46  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023f4d  lea     rdi, WPP_GLOBAL_Control
0x180023f54  cmp     rcx, rdi
0x180023f57  jz      loc_1800243BC
0x180023f5d  test    byte ptr [rcx+1Ch], 2
0x180023f61  jz      loc_1800243BC
0x180023f67  cmp     byte ptr [rcx+19h], 1
0x180023f6b  jb      loc_1800243BC
0x180023f71  mov     edx, 3Ah ; ':'
0x180023f76  jmp     short loc_180023F1A
0x180023f78  lea     rax, [rsp+2F0h+pvFindPara]
0x180023f7d  mov     [rsp+2F0h+pPrevCertContext], 0; pPrevCertContext
0x180023f86  mov     r9d, 10000h; dwFindType
0x180023f8c  mov     [rsp+2F0h+pvPara], rax; pvFindPara
0x180023f91  xor     r8d, r8d; dwFindFlags
0x180023f94  mov     edx, edi; dwCertEncodingType
0x180023f96  mov     rcx, rsi; hCertStore
0x180023f99  call    cs:__imp_CertFindCertificateInStore
0x180023fa0  nop     dword ptr [rax+rax+00h]
0x180023fa5  mov     [rsp+2F0h+pCertContext], rax
0x180023faa  test    rax, rax
0x180023fad  jnz     short loc_180023FF7
0x180023faf  mov     ebx, 490h
0x180023fb4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023fbb  lea     rdi, WPP_GLOBAL_Control
0x180023fc2  cmp     rcx, rdi
0x180023fc5  jz      loc_1800243BC
0x180023fcb  test    byte ptr [rcx+1Ch], 2
0x180023fcf  jz      loc_1800243BC
0x180023fd5  cmp     byte ptr [rcx+19h], 1
0x180023fd9  jb      loc_1800243BC
0x180023fdf  lea     edx, [rax+3Bh]
0x180023fe2  mov     rcx, [rcx+10h]
0x180023fe6  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023fed  call    WPP_SF_
0x180023ff2  jmp     loc_1800243BC
0x180023ff7  xor     esi, esi
0x180023ff9  lea     rdi, [rsp+2F0h+cbBinary]
0x180023ffe  xor     r12d, r12d
0x180024001  mov     [rsp+2F0h+var_2C0], esi
0x180024005  xor     edx, edx; Val
0x180024007  mov     [rsp+2F0h+var_2BC], r12d
0x18002400c  lea     eax, [rsi+14h]
0x18002400f  mov     ecx, eax
0x180024011  lea     r8d, [rsi+50h]; Size
0x180024015  rep stosd
0x180024017  lea     rcx, [rbp+1F0h+var_230]; void *
0x18002401b  call    memset_0
0x180024020  mov     r14, [rsp+2F0h+pCertContext]
0x180024025  lea     rdi, WPP_GLOBAL_Control
0x18002402c  cmp     esi, 14h
0x18002402f  jnb     loc_18002423C
0x180024035  lea     rcx, [rbp+1F0h+var_1E0]
0x180024039  mov     edx, 40h ; '@'; dwPropId
0x18002403e  lea     rax, [rsi+rsi*4]
0x180024042  lea     rax, [rcx+rax*4]
0x180024046  mov     rcx, r14; pCertContext
0x180024049  lea     r9, [rsp+2F0h+cbBinary]
0x18002404e  mov     [rsp+2F0h+var_2B8], rax
0x180024053  mov     r8, rax; pvData
0x180024056  lea     r9, [r9+rsi*4]; pcbData
0x18002405a  call    cs:__imp_CertGetCertificateContextProperty
0x180024061  nop     dword ptr [rax+rax+00h]
0x180024066  test    eax, eax
0x180024068  jz      loc_18002420C
0x18002406e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024075  cmp     rcx, rdi
0x180024078  jz      short loc_18002409E
0x18002407a  test    byte ptr [rcx+1Ch], 2
0x18002407e  jz      short loc_18002409E
0x180024080  cmp     byte ptr [rcx+19h], 2
0x180024084  jb      short loc_18002409E
0x180024086  mov     rcx, [rcx+10h]
0x18002408a  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180024091  mov     edx, 3Fh ; '?'
0x180024096  mov     r9, r14
0x180024099  call    WPP_SF_q
0x18002409e  mov     eax, [rsp+rsi*4+2F0h+cbBinary]
0x1800240a2  mov     r9d, 10000h; dwFindType
0x1800240a8  mov     rcx, [rsp+2F0h+hCertStore]; hCertStore
0x1800240ad  xor     r8d, r8d; dwFindFlags
0x1800240b0  mov     dword ptr [rsp+2F0h+pbBinary], eax
0x1800240b4  mov     rax, [rsp+2F0h+var_2B8]
0x1800240b9  mov     [rsp+2F0h+pbBinary+8], rax
0x1800240be  lea     edx, [r9+1]; dwCertEncodingType
0x1800240c2  lea     rax, [rsp+2F0h+pbBinary]
0x1800240c7  mov     [rsp+2F0h+pPrevCertContext], 0; pPrevCertContext
0x1800240d0  mov     [rsp+2F0h+pvPara], rax; pvFindPara
0x1800240d5  call    cs:__imp_CertFindCertificateInStore
0x1800240dc  nop     dword ptr [rax+rax+00h]
0x1800240e1  mov     [rsp+2F0h+var_2B8], rax
0x1800240e6  test    rax, rax
0x1800240e9  jz      loc_1800241C9
0x1800240ef  mov     edx, dword ptr [rsp+2F0h+pbBinary]; cbBinary
0x1800240f3  lea     rax, [rbp+1F0h+var_230]
0x1800240f7  mov     rcx, [rsp+2F0h+pbBinary+8]; pbBinary
0x1800240fc  lea     r15, [rax+rsi*4]
0x180024100  xor     r9d, r9d; pszString
0x180024103  mov     [rsp+2F0h+pvPara], r15; pcchString
0x180024108  mov     r8d, 4000000Ch; dwFlags
0x18002410e  call    cs:__imp_CryptBinaryToStringW
0x180024115  nop     dword ptr [rax+rax+00h]
0x18002411a  test    eax, eax
0x18002411c  jz      short loc_18002417A
0x18002411e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024125  cmp     rcx, rdi
0x180024128  jz      short loc_18002414E
0x18002412a  test    byte ptr [rcx+1Ch], 2
0x18002412e  jz      short loc_18002414E
0x180024130  cmp     byte ptr [rcx+19h], 2
0x180024134  jb      short loc_18002414E
0x180024136  mov     r9d, [r15]
0x180024139  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180024140  mov     rcx, [rcx+10h]
0x180024144  mov     edx, 41h ; 'A'
0x180024149  call    WPP_SF_d
0x18002414e  add     r12d, [r15]
0x180024151  mov     rcx, r14; pCertContext
0x180024154  mov     [rsp+2F0h+var_2BC], r12d
0x180024159  call    cs:__imp_CertFreeCertificateContext
0x180024160  nop     dword ptr [rax+rax+00h]
0x180024165  mov     r14, [rsp+2F0h+var_2B8]
0x18002416a  inc     esi
0x18002416c  mov     [rsp+2F0h+var_2C0], esi
0x180024170  mov     [rsp+2F0h+pCertContext], r14
0x180024175  jmp     loc_18002402C
0x18002417a  call    cs:__imp_GetLastError
0x180024181  nop     dword ptr [rax+rax+00h]
0x180024186  mov     ebx, eax
0x180024188  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002418f  cmp     rcx, rdi
0x180024192  jz      loc_1800243A1
0x180024198  test    byte ptr [rcx+1Ch], 2
0x18002419c  jz      loc_1800243A1
0x1800241a2  cmp     byte ptr [rcx+19h], 1
0x1800241a6  jb      loc_1800243A1
0x1800241ac  mov     edx, 42h ; 'B'
0x1800241b1  mov     r9d, eax
0x1800241b4  mov     rcx, [rcx+10h]
0x1800241b8  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800241bf  call    WPP_SF_d
0x1800241c4  jmp     loc_1800243A1
0x1800241c9  mov     ebx, 490h
0x1800241ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800241d5  cmp     rcx, rdi
0x1800241d8  jz      loc_1800243A1
0x1800241de  test    byte ptr [rcx+1Ch], 2
0x1800241e2  jz      loc_1800243A1
0x1800241e8  cmp     byte ptr [rcx+19h], 1
0x1800241ec  jb      loc_1800243A1
0x1800241f2  mov     rcx, [rcx+10h]
0x1800241f6  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x1800241fd  mov     edx, 40h ; '@'
0x180024202  call    WPP_SF_
0x180024207  jmp     loc_1800243A1
0x18002420c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024213  cmp     rcx, rdi
0x180024216  jz      short loc_180024265
0x180024218  test    byte ptr [rcx+1Ch], 2
0x18002421c  jz      short loc_180024243
0x18002421e  cmp     byte ptr [rcx+19h], 2
0x180024222  jb      short loc_180024243
0x180024224  mov     rcx, [rcx+10h]
0x180024228  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x18002422f  mov     edx, 3Eh ; '>'
0x180024234  mov     r9, r14
0x180024237  call    WPP_SF_q
0x18002423c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024243  cmp     rcx, rdi; __annotation("TMF:",
0x180024246  jz      short loc_180024265
0x180024248  test    byte ptr [rcx+1Ch], 2
0x18002424c  jz      short loc_180024265
0x18002424e  cmp     byte ptr [rcx+19h], 2
0x180024252  jb      short loc_180024265
0x180024254  mov     rcx, [rcx+10h]
0x180024258  mov     r9d, esi
0x18002425b  mov     dword ptr [rsp+2F0h+pvPara], r12d
0x180024260  call    WPP_SF_Dd
0x180024265  test    esi, esi
0x180024267  jnz     short loc_180024276
0x180024269  mov     qword ptr [r13+48h], 0
0x180024271  jmp     loc_1800243A1
0x180024276  lea     rdx, ds:2[r12*2]; uBytes
0x18002427e  mov     ecx, 40h ; '@'; uFlags
0x180024283  call    cs:__imp_LocalAlloc
0x18002428a  nop     dword ptr [rax+rax+00h]
0x18002428f  mov     rsi, rax
0x180024292  test    rax, rax
0x180024295  jnz     short loc_1800242C9
0x180024297  lea     ebx, [rax+8]
0x18002429a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800242a1  cmp     rcx, rdi
0x1800242a4  jz      loc_1800243A1
0x1800242aa  test    byte ptr [rcx+1Ch], 2
0x1800242ae  jz      loc_1800243A1
0x1800242b4  cmp     byte ptr [rcx+19h], 1
0x1800242b8  jb      loc_1800243A1
0x1800242be  lea     edx, [rax+44h]
0x1800242c1  mov     r9d, ebx
0x1800242c4  jmp     loc_1800241B4
0x1800242c9  mov     r12, rsi
0x1800242cc  xor     r15d, r15d
0x1800242cf  cmp     r15d, [rsp+2F0h+var_2C0]
0x1800242d4  jnb     loc_180024361
0x1800242da  mov     edx, [rsp+r15*4+2F0h+cbBinary]; cbBinary
0x1800242df  lea     rax, [r15+r15*4]
0x1800242e3  lea     r8, [rbp+1F0h+var_230]
0x1800242e7  mov     r9, r12; pszString
0x1800242ea  lea     r8, [r8+r15*4]
0x1800242ee  mov     [rsp+2F0h+var_2B8], r8
0x1800242f3  lea     rcx, [rbp+1F0h+var_1E0]
0x1800242f7  mov     [rsp+2F0h+pvPara], r8; pcchString
0x1800242fc  lea     rcx, [rcx+rax*4]; pbBinary
0x180024300  mov     r8d, 4000000Ch; dwFlags
0x180024306  call    cs:__imp_CryptBinaryToStringW
0x18002430d  nop     dword ptr [rax+rax+00h]
0x180024312  test    eax, eax
0x180024314  jz      short loc_180024331
0x180024316  mov     rcx, [rsp+2F0h+var_2B8]
0x18002431b  mov     eax, [rcx]
0x18002431d  mov     word ptr [r12+rax*2], 3Ah ; ':'
0x180024324  mov     eax, [rcx]
0x180024326  inc     eax
0x180024328  inc     r15d
0x18002432b  lea     r12, [r12+rax*2]
0x18002432f  jmp     short loc_1800242CF
0x180024331  call    cs:__imp_GetLastError
0x180024338  nop     dword ptr [rax+rax+00h]
0x18002433d  mov     ebx, eax
0x18002433f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024346  cmp     rcx, rdi
0x180024349  jz      short loc_1800243A1
0x18002434b  test    byte ptr [rcx+1Ch], 2
0x18002434f  jz      short loc_1800243A1
0x180024351  cmp     byte ptr [rcx+19h], 1
0x180024355  jb      short loc_1800243A1
0x180024357  mov     edx, 45h ; 'E'
0x18002435c  jmp     loc_1800241B1
0x180024361  mov     edx, [rsp+2F0h+var_2BC]
0x180024365  xor     eax, eax
0x180024367  mov     [rsi+rdx*2], ax
0x18002436b  mov     [r13+48h], rsi
  ... truncated ...
```
