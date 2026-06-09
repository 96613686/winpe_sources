# PopulateRenewalChain

- ea: `0x180033630`
- end: `0x180033c22`
- name: `PopulateRenewalChain`
- size: `1522`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180032480`
- `0x1800329f0`

## callees

- `0x18001deb0`
- `0x18001e80c`
- `0x180020dc0`
- `0x180020de8`
- `0x1800215e8`
- `0x18002fc4c`
- `0x180033630`
- `0x180033fc8`
- `0x180035d44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003392b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003392b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033b70`
- `CRYPT32!CryptBinaryToStringW` at `0x1800338cd`
- `CRYPT32!CryptBinaryToStringW` at `0x180033ac2`
- `CRYPT32!CryptBinaryToStringW` at `0x1800338cd`
- `CRYPT32!CryptBinaryToStringW` at `0x180033ac2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180033827`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180033827`
- `CRYPT32!CertFreeCertificateContext` at `0x180033915`
- `CRYPT32!CertFreeCertificateContext` at `0x180033b5b`
- `CRYPT32!CertFreeCertificateContext` at `0x180033915`
- `CRYPT32!CertFreeCertificateContext` at `0x180033b5b`
- `CRYPT32!CertCloseStore` at `0x180033b83`
- `CRYPT32!CertCloseStore` at `0x180033b83`
- `CRYPT32!CertFindCertificateInStore` at `0x180033769`
- `CRYPT32!CertFindCertificateInStore` at `0x18003389b`
- `CRYPT32!CertFindCertificateInStore` at `0x180033769`
- `CRYPT32!CertFindCertificateInStore` at `0x18003389b`
- `CRYPT32!CertOpenStore` at `0x1800336a1`
- `CRYPT32!CertOpenStore` at `0x1800336a1`

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
  __int64 v10; // r12
  DWORD *v11; // rdi
  __int64 i; // rcx
  const CERT_CONTEXT *j; // rsi
  PCCERT_CONTEXT CertificateInStore; // r15
  DWORD *v15; // r14
  DWORD v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  _QWORD *v20; // rcx
  unsigned int v21; // r15d
  WCHAR *v22; // rax
  WCHAR *v23; // rsi
  WCHAR *v24; // r15
  __int64 v25; // r14
  DWORD v26; // eax
  unsigned int v28; // [rsp+30h] [rbp-D0h]
  const CERT_CONTEXT *pCertContext; // [rsp+38h] [rbp-C8h]
  HCERTSTORE hCertStore; // [rsp+40h] [rbp-C0h]
  DWORD *v31; // [rsp+48h] [rbp-B8h]
  BYTE *pbBinary[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 pvFindPara; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v34[20]; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbBinary[120]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = *(_QWORD *)(a1 + 24) == 0;
  pvFindPara = 0;
  *(_OWORD *)pbBinary = 0;
  if ( v1 || !*(_QWORD *)(a1 + 64) )
  {
    v3 = 0;
    v5 = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_77;
    }
    v9 = 35;
    goto LABEL_19;
  }
  hCertStore = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x20000u, *(const void **)(a1 + 64));
  v3 = hCertStore;
  if ( !hCertStore )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v7 = 36;
LABEL_8:
      WPP_SF_d(v6[2], v7, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, LastError);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = SsConvertCryptStringToBinary(*(LPCWSTR *)(a1 + 24), (DWORD *)&pvFindPara);
  v5 = LastError;
  if ( !LastError )
  {
    pCertContext = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( pCertContext )
    {
      v10 = 0;
      v11 = cbBinary;
      v28 = 0;
      for ( i = 20; i; --i )
        *v11++ = 20;
      memset_0(v34, 0, sizeof(v34));
      for ( j = pCertContext; ; j = CertificateInStore )
      {
        if ( (unsigned int)v10 >= 0x14 )
          goto LABEL_51;
        if ( !CertGetCertificateContextProperty(j, 0x40u, &cbBinary[5 * v10 + 20], &cbBinary[v10]) )
          break;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, j);
        }
        LODWORD(pbBinary[0]) = cbBinary[v10];
        pbBinary[1] = (BYTE *)&cbBinary[5 * v10 + 20];
        CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, pbBinary, 0);
        if ( !CertificateInStore )
        {
          v5 = 1168;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids);
          }
          goto LABEL_76;
        }
        v15 = &v34[v10];
        if ( !CryptBinaryToStringW(pbBinary[1], (DWORD)pbBinary[0], 0x4000000Cu, 0, v15) )
        {
          v16 = GetLastError();
          v5 = v16;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_76;
          }
          v18 = 45;
LABEL_41:
          v19 = v16;
          goto LABEL_42;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, *v15);
        }
        v28 += *v15;
        CertFreeCertificateContext(j);
        v10 = (unsigned int)(v10 + 1);
        pCertContext = CertificateInStore;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_56;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, j);
LABEL_51:
        v20 = WPP_GLOBAL_Control;
      }
      if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 )
      {
LABEL_56:
        v21 = v28;
      }
      else
      {
        v21 = v28;
        if ( *((_BYTE *)v20 + 25) >= 2u )
          WPP_SF_Dd(v20[2], 46, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, (unsigned int)v10, v28);
      }
      if ( !(_DWORD)v10 )
      {
        *(_QWORD *)(a1 + 72) = 0;
        goto LABEL_76;
      }
      v22 = (WCHAR *)LocalAlloc(0x40u, 2LL * v21 + 2);
      v23 = v22;
      if ( !v22 )
      {
        v5 = 8;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_76;
        }
        v18 = 47;
        v19 = 8;
LABEL_42:
        WPP_SF_d(v17[2], v18, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v19);
        goto LABEL_76;
      }
      v24 = v22;
      v25 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v25 >= (unsigned int)v10 )
        {
          v23[v28] = 0;
          *(_QWORD *)(a1 + 72) = v23;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              (unsigned int)WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids,
              (_DWORD)v23,
              0);
          }
          goto LABEL_76;
        }
        v31 = &v34[v25];
        if ( !CryptBinaryToStringW((const BYTE *)&cbBinary[5 * v25 + 20], cbBinary[v25], 0x4000000Cu, v24, v31) )
          break;
        v24[*v31] = 58;
        v25 = (unsigned int)(v25 + 1);
        v24 += *v31 + 1;
      }
      v16 = GetLastError();
      v5 = v16;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v18 = 48;
        goto LABEL_41;
      }
LABEL_76:
      CertFreeCertificateContext(pCertContext);
      v3 = hCertStore;
      goto LABEL_77;
    }
    v5 = 1168;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_77;
    }
    v9 = 38;
LABEL_19:
    WPP_SF_(v8[2], v9, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids);
    goto LABEL_77;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v7 = 37;
    goto LABEL_8;
  }
LABEL_77:
  if ( *((_QWORD *)&pvFindPara + 1) )
    LocalFree(*((HLOCAL *)&pvFindPara + 1));
  if ( v3 )
  {
    if ( !CertCloseStore(v3, 2u) )
    {
      v26 = GetLastError();
      v5 = v26;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids, v26);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180033630  push    rbp
0x180033632  push    rbx
0x180033633  push    rsi
0x180033634  push    rdi
0x180033635  push    r12
0x180033637  push    r13
0x180033639  push    r14
0x18003363b  push    r15
0x18003363d  lea     rbp, [rsp-1B8h]
0x180033645  sub     rsp, 2B8h
0x18003364c  mov     rax, cs:__security_cookie
0x180033653  xor     rax, rsp
0x180033656  mov     [rbp+1F0h+var_50], rax
0x18003365d  cmp     qword ptr [rcx+18h], 0
0x180033662  xorps   xmm0, xmm0
0x180033665  xorps   xmm1, xmm1
0x180033668  mov     r13, rcx
0x18003366b  movups  [rsp+2F0h+pvFindPara], xmm0
0x180033670  movups  xmmword ptr [rsp+2F0h+pbBinary], xmm1
0x180033675  jz      loc_180033BEA
0x18003367b  mov     rax, [rcx+40h]
0x18003367f  test    rax, rax
0x180033682  jz      loc_180033BEA
0x180033688  xor     r8d, r8d; hCryptProv
0x18003368b  mov     [rsp+2F0h+pvPara], rax; pvPara
0x180033690  mov     edi, 10001h
0x180033695  mov     r9d, 20000h; dwFlags
0x18003369b  mov     edx, edi; dwEncodingType
0x18003369d  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x1800336a1  call    cs:__imp_CertOpenStore
0x1800336a7  mov     [rsp+2F0h+hCertStore], rax
0x1800336ac  mov     rsi, rax
0x1800336af  test    rax, rax
0x1800336b2  jnz     short loc_180033702
0x1800336b4  call    cs:__imp_GetLastError
0x1800336ba  mov     ebx, eax
0x1800336bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336c3  lea     rdi, WPP_GLOBAL_Control
0x1800336ca  cmp     rcx, rdi
0x1800336cd  jz      loc_180033B66
0x1800336d3  test    byte ptr [rcx+1Ch], 1
0x1800336d7  jz      loc_180033B66
0x1800336dd  cmp     byte ptr [rcx+19h], 1
0x1800336e1  jb      loc_180033B66
0x1800336e7  lea     edx, [rsi+24h]
0x1800336ea  mov     rcx, [rcx+10h]
0x1800336ee  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800336f5  mov     r9d, eax
0x1800336f8  call    WPP_SF_d
0x1800336fd  jmp     loc_180033B66
0x180033702  mov     rcx, [r13+18h]; pszString
0x180033706  lea     rdx, [rsp+2F0h+pvFindPara]; pcbBinary
0x18003370b  call    SsConvertCryptStringToBinary
0x180033710  mov     ebx, eax
0x180033712  test    eax, eax
0x180033714  jz      short loc_180033748
0x180033716  mov     rcx, cs:WPP_GLOBAL_Control
0x18003371d  lea     rdi, WPP_GLOBAL_Control
0x180033724  cmp     rcx, rdi
0x180033727  jz      loc_180033B66
0x18003372d  test    byte ptr [rcx+1Ch], 1
0x180033731  jz      loc_180033B66
0x180033737  cmp     byte ptr [rcx+19h], 1
0x18003373b  jb      loc_180033B66
0x180033741  mov     edx, 25h ; '%'
0x180033746  jmp     short loc_1800336EA
0x180033748  lea     rax, [rsp+2F0h+pvFindPara]
0x18003374d  mov     [rsp+2F0h+pPrevCertContext], 0; pPrevCertContext
0x180033756  mov     r9d, 10000h; dwFindType
0x18003375c  mov     [rsp+2F0h+pvPara], rax; pvFindPara
0x180033761  xor     r8d, r8d; dwFindFlags
0x180033764  mov     edx, edi; dwCertEncodingType
0x180033766  mov     rcx, rsi; hCertStore
0x180033769  call    cs:__imp_CertFindCertificateInStore
0x18003376f  mov     [rsp+2F0h+pCertContext], rax
0x180033774  test    rax, rax
0x180033777  jnz     short loc_1800337C1
0x180033779  mov     ebx, 490h
0x18003377e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033785  lea     rdi, WPP_GLOBAL_Control
0x18003378c  cmp     rcx, rdi
0x18003378f  jz      loc_180033B66
0x180033795  test    byte ptr [rcx+1Ch], 1
0x180033799  jz      loc_180033B66
0x18003379f  cmp     byte ptr [rcx+19h], 1
0x1800337a3  jb      loc_180033B66
0x1800337a9  lea     edx, [rax+26h]
0x1800337ac  mov     rcx, [rcx+10h]
0x1800337b0  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800337b7  call    WPP_SF_
0x1800337bc  jmp     loc_180033B66
0x1800337c1  xor     r12d, r12d
0x1800337c4  lea     rdi, [rbp+1F0h+cbBinary]
0x1800337c8  xor     r15d, r15d
0x1800337cb  xor     edx, edx; Val
0x1800337cd  mov     [rsp+2F0h+var_2C0], r15d
0x1800337d2  lea     eax, [r12+14h]
0x1800337d7  mov     ecx, eax
0x1800337d9  lea     r8d, [r12+50h]; Size
0x1800337de  rep stosd
0x1800337e0  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800337e5  call    memset_0
0x1800337ea  mov     rsi, [rsp+2F0h+pCertContext]
0x1800337ef  lea     rdi, WPP_GLOBAL_Control
0x1800337f6  cmp     r12d, 14h
0x1800337fa  jnb     loc_1800339E7
0x180033800  lea     rcx, [rbp+1F0h+var_1E0]
0x180033804  mov     edx, 40h ; '@'; dwPropId
0x180033809  lea     r15, [rbp+1F0h+cbBinary]
0x18003380d  lea     rax, [r12+r12*4]
0x180033811  lea     rax, [rcx+rax*4]
0x180033815  mov     rcx, rsi; pCertContext
0x180033818  lea     r15, [r15+r12*4]
0x18003381c  mov     [rsp+2F0h+var_2A8], rax
0x180033821  mov     r9, r15; pcbData
0x180033824  mov     r8, rax; pvData
0x180033827  call    cs:__imp_CertGetCertificateContextProperty
0x18003382d  test    eax, eax
0x18003382f  jz      loc_1800339B7
0x180033835  mov     rcx, cs:WPP_GLOBAL_Control
0x18003383c  cmp     rcx, rdi
0x18003383f  jz      short loc_180033865
0x180033841  test    byte ptr [rcx+1Ch], 1
0x180033845  jz      short loc_180033865
0x180033847  cmp     byte ptr [rcx+19h], 2
0x18003384b  jb      short loc_180033865
0x18003384d  mov     rcx, [rcx+10h]
0x180033851  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180033858  mov     edx, 2Ah ; '*'
0x18003385d  mov     r9, rsi
0x180033860  call    WPP_SF_q
0x180033865  mov     eax, [r15]
0x180033868  mov     r9d, 10000h; dwFindType
0x18003386e  mov     rcx, [rsp+2F0h+hCertStore]; hCertStore
0x180033873  xor     r8d, r8d; dwFindFlags
0x180033876  mov     dword ptr [rsp+2F0h+pbBinary], eax
0x18003387a  mov     rax, [rsp+2F0h+var_2A8]
0x18003387f  mov     [rsp+2F0h+pbBinary+8], rax
0x180033884  lea     edx, [r9+1]; dwCertEncodingType
0x180033888  lea     rax, [rsp+2F0h+pbBinary]
0x18003388d  mov     [rsp+2F0h+pPrevCertContext], 0; pPrevCertContext
0x180033896  mov     [rsp+2F0h+pvPara], rax; pvFindPara
0x18003389b  call    cs:__imp_CertFindCertificateInStore
0x1800338a1  mov     r15, rax
0x1800338a4  test    rax, rax
0x1800338a7  jz      loc_180033974
0x1800338ad  mov     edx, dword ptr [rsp+2F0h+pbBinary]; cbBinary
0x1800338b1  lea     rax, [rsp+2F0h+var_280]
0x1800338b6  mov     rcx, [rsp+2F0h+pbBinary+8]; pbBinary
0x1800338bb  lea     r14, [rax+r12*4]
0x1800338bf  xor     r9d, r9d; pszString
0x1800338c2  mov     [rsp+2F0h+pvPara], r14; pcchString
0x1800338c7  mov     r8d, 4000000Ch; dwFlags
0x1800338cd  call    cs:__imp_CryptBinaryToStringW
0x1800338d3  test    eax, eax
0x1800338d5  jz      short loc_18003392B
0x1800338d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338de  cmp     rcx, rdi
0x1800338e1  jz      short loc_180033907
0x1800338e3  test    byte ptr [rcx+1Ch], 1
0x1800338e7  jz      short loc_180033907
0x1800338e9  cmp     byte ptr [rcx+19h], 2
0x1800338ed  jb      short loc_180033907
0x1800338ef  mov     r9d, [r14]
0x1800338f2  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800338f9  mov     rcx, [rcx+10h]
0x1800338fd  mov     edx, 2Ch ; ','
0x180033902  call    WPP_SF_d
0x180033907  mov     eax, [rsp+2F0h+var_2C0]
0x18003390b  mov     rcx, rsi; pCertContext
0x18003390e  add     eax, [r14]
0x180033911  mov     [rsp+2F0h+var_2C0], eax
0x180033915  call    cs:__imp_CertFreeCertificateContext
0x18003391b  inc     r12d
0x18003391e  mov     [rsp+2F0h+pCertContext], r15
0x180033923  mov     rsi, r15
0x180033926  jmp     loc_1800337F6
0x18003392b  call    cs:__imp_GetLastError
0x180033931  mov     ebx, eax
0x180033933  mov     rcx, cs:WPP_GLOBAL_Control
0x18003393a  cmp     rcx, rdi
0x18003393d  jz      loc_180033B51
0x180033943  test    byte ptr [rcx+1Ch], 1
0x180033947  jz      loc_180033B51
0x18003394d  cmp     byte ptr [rcx+19h], 1
0x180033951  jb      loc_180033B51
0x180033957  mov     edx, 2Dh ; '-'
0x18003395c  mov     r9d, eax
0x18003395f  mov     rcx, [rcx+10h]
0x180033963  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x18003396a  call    WPP_SF_d
0x18003396f  jmp     loc_180033B51
0x180033974  mov     ebx, 490h
0x180033979  mov     rcx, cs:WPP_GLOBAL_Control
0x180033980  cmp     rcx, rdi
0x180033983  jz      loc_180033B51
0x180033989  test    byte ptr [rcx+1Ch], 1
0x18003398d  jz      loc_180033B51
0x180033993  cmp     byte ptr [rcx+19h], 1
0x180033997  jb      loc_180033B51
0x18003399d  mov     rcx, [rcx+10h]
0x1800339a1  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800339a8  mov     edx, 2Bh ; '+'
0x1800339ad  call    WPP_SF_
0x1800339b2  jmp     loc_180033B51
0x1800339b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339be  cmp     rcx, rdi
0x1800339c1  jz      short loc_180033A23
0x1800339c3  test    byte ptr [rcx+1Ch], 1
0x1800339c7  jz      short loc_1800339EE
0x1800339c9  cmp     byte ptr [rcx+19h], 2
0x1800339cd  jb      short loc_1800339EE
0x1800339cf  mov     rcx, [rcx+10h]
0x1800339d3  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x1800339da  mov     edx, 29h ; ')'
0x1800339df  mov     r9, rsi
0x1800339e2  call    WPP_SF_q
0x1800339e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339ee  cmp     rcx, rdi
0x1800339f1  jz      short loc_180033A23
0x1800339f3  test    byte ptr [rcx+1Ch], 1
0x1800339f7  jz      short loc_180033A23
0x1800339f9  cmp     byte ptr [rcx+19h], 2
0x1800339fd  mov     r15d, [rsp+2F0h+var_2C0]
0x180033a02  jb      short loc_180033A28
0x180033a04  mov     rcx, [rcx+10h]
0x180033a08  lea     r8, WPP_3d8d68fd59dd345388a9abd81eb39218_Traceguids
0x180033a0f  mov     edx, 2Eh ; '.'
0x180033a14  mov     dword ptr [rsp+2F0h+pvPara], r15d
0x180033a19  mov     r9d, r12d
0x180033a1c  call    WPP_SF_Dd
0x180033a21  jmp     short loc_180033A28
0x180033a23  mov     r15d, [rsp+2F0h+var_2C0]
0x180033a28  test    r12d, r12d
0x180033a2b  jnz     short loc_180033A3A
0x180033a2d  mov     qword ptr [r13+48h], 0
0x180033a35  jmp     loc_180033B51
0x180033a3a  mov     eax, r15d
0x180033a3d  mov     ecx, 40h ; '@'; uFlags
0x180033a42  lea     rdx, ds:2[rax*2]; uBytes
0x180033a4a  call    cs:__imp_LocalAlloc
0x180033a50  mov     rsi, rax
0x180033a53  test    rax, rax
0x180033a56  jnz     short loc_180033A8A
0x180033a58  lea     ebx, [rax+8]
0x180033a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a62  cmp     rcx, rdi
0x180033a65  jz      loc_180033B51
0x180033a6b  test    byte ptr [rcx+1Ch], 1
0x180033a6f  jz      loc_180033B51
0x180033a75  cmp     byte ptr [rcx+19h], 1
0x180033a79  jb      loc_180033B51
0x180033a7f  lea     edx, [rax+2Fh]
0x180033a82  mov     r9d, ebx
0x180033a85  jmp     loc_18003395F
0x180033a8a  mov     r15, rsi
0x180033a8d  xor     r14d, r14d
0x180033a90  cmp     r14d, r12d
0x180033a93  jnb     short loc_180033B11
0x180033a95  mov     edx, [rbp+r14*4+1F0h+cbBinary]; cbBinary
0x180033a9a  lea     rax, [r14+r14*4]
0x180033a9e  lea     r8, [rsp+2F0h+var_280]
0x180033aa3  mov     r9, r15; pszString
0x180033aa6  lea     r8, [r8+r14*4]
0x180033aaa  mov     [rsp+2F0h+var_2A8], r8
0x180033aaf  lea     rcx, [rbp+1F0h+var_1E0]
0x180033ab3  mov     [rsp+2F0h+pvPara], r8; pcchString
0x180033ab8  lea     rcx, [rcx+rax*4]; pbBinary
0x180033abc  mov     r8d, 4000000Ch; dwFlags
0x180033ac2  call    cs:__imp_CryptBinaryToStringW
0x180033ac8  test    eax, eax
0x180033aca  jz      short loc_180033AE7
0x180033acc  mov     rcx, [rsp+2F0h+var_2A8]
0x180033ad1  mov     eax, [rcx]
0x180033ad3  mov     word ptr [r15+rax*2], 3Ah ; ':'
0x180033ada  mov     eax, [rcx]
0x180033adc  inc     eax
0x180033ade  inc     r14d
0x180033ae1  lea     r15, [r15+rax*2]
0x180033ae5  jmp     short loc_180033A90
0x180033ae7  call    cs:__imp_GetLastError
0x180033aed  mov     ebx, eax
0x180033aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180033af6  cmp     rcx, rdi
0x180033af9  jz      short loc_180033B51
0x180033afb  test    byte ptr [rcx+1Ch], 1
0x180033aff  jz      short loc_180033B51
0x180033b01  cmp     byte ptr [rcx+19h], 1
0x180033b05  jb      short loc_180033B51
0x180033b07  mov     edx, 30h ; '0'
0x180033b0c  jmp     loc_18003395C
0x180033b11  mov     edx, [rsp+2F0h+var_2C0]
0x180033b15  xor     eax, eax
0x180033b17  mov     [rsi+rdx*2], ax
0x180033b1b  mov     [r13+48h], rsi
0x180033b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b26  cmp     rcx, rdi
0x180033b29  jz      short loc_180033B51
0x180033b2b  test    byte ptr [rcx+1Ch], 1
0x180033b2f  jz      short loc_180033B51
  ... truncated ...
```
