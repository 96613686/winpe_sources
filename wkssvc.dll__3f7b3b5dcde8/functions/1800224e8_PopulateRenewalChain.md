# PopulateRenewalChain

- ea: `0x1800224e8`
- end: `0x180022ac0`
- name: `PopulateRenewalChain`
- size: `1496`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180021540`
- `0x180021ad0`

## callees

- `0x18001e420`
- `0x18001ed46`
- `0x1800211fc`
- `0x1800224e8`
- `0x180022b54`
- `0x180022b7c`
- `0x180022bbc`
- `0x180023534`
- `0x180023694`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002256c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002256c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022a0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022a0e`
- `CRYPT32!CertOpenStore` at `0x180022559`
- `CRYPT32!CertOpenStore` at `0x180022559`
- `CRYPT32!CertFindCertificateInStore` at `0x180022621`
- `CRYPT32!CertFindCertificateInStore` at `0x180022751`
- `CRYPT32!CertFindCertificateInStore` at `0x180022621`
- `CRYPT32!CertFindCertificateInStore` at `0x180022751`
- `CRYPT32!CertCloseStore` at `0x180022a21`
- `CRYPT32!CertCloseStore` at `0x180022a21`
- `CRYPT32!CertFreeCertificateContext` at `0x1800227c9`
- `CRYPT32!CertFreeCertificateContext` at `0x1800229f9`
- `CRYPT32!CertFreeCertificateContext` at `0x1800227c9`
- `CRYPT32!CertFreeCertificateContext` at `0x1800229f9`
- `CRYPT32!CryptBinaryToStringW` at `0x180022784`
- `CRYPT32!CryptBinaryToStringW` at `0x180022960`
- `CRYPT32!CryptBinaryToStringW` at `0x180022784`
- `CRYPT32!CryptBinaryToStringW` at `0x180022960`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800226dc`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800226dc`

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
      WPP_SF_d(v6[2], v7, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, LastError);
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
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v16);
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
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, *v17);
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
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v16);
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
        WPP_SF_d(v19[2], v20, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v21);
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
              (unsigned int)&WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
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
    WPP_SF_(v8[2], v9, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v27);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800224e8  push    rbp
0x1800224ea  push    rbx
0x1800224eb  push    rsi
0x1800224ec  push    rdi
0x1800224ed  push    r12
0x1800224ef  push    r13
0x1800224f1  push    r14
0x1800224f3  push    r15
0x1800224f5  lea     rbp, [rsp-1B8h]
0x1800224fd  sub     rsp, 2B8h
0x180022504  mov     rax, cs:__security_cookie
0x18002250b  xor     rax, rsp
0x18002250e  mov     [rbp+1F0h+var_50], rax
0x180022515  cmp     qword ptr [rcx+18h], 0
0x18002251a  xorps   xmm0, xmm0
0x18002251d  xorps   xmm1, xmm1
0x180022520  mov     r13, rcx
0x180022523  movups  [rsp+2F0h+pvFindPara], xmm0
0x180022528  movups  xmmword ptr [rsp+2F0h+pbBinary], xmm1
0x18002252d  jz      loc_180022A88
0x180022533  mov     rax, [rcx+40h]
0x180022537  test    rax, rax
0x18002253a  jz      loc_180022A88
0x180022540  xor     r8d, r8d; hCryptProv
0x180022543  mov     [rsp+2F0h+pvPara], rax; pvPara
0x180022548  mov     edi, 10001h
0x18002254d  mov     r9d, 28000h; dwFlags
0x180022553  mov     edx, edi; dwEncodingType
0x180022555  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180022559  call    cs:__imp_CertOpenStore
0x18002255f  mov     [rsp+2F0h+hCertStore], rax
0x180022564  mov     rsi, rax
0x180022567  test    rax, rax
0x18002256a  jnz     short loc_1800225BA
0x18002256c  call    cs:__imp_GetLastError
0x180022572  mov     ebx, eax
0x180022574  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002257b  lea     rdi, WPP_GLOBAL_Control
0x180022582  cmp     rcx, rdi
0x180022585  jz      loc_180022A04
0x18002258b  test    byte ptr [rcx+1Ch], 2
0x18002258f  jz      loc_180022A04
0x180022595  cmp     byte ptr [rcx+19h], 1
0x180022599  jb      loc_180022A04
0x18002259f  lea     edx, [rsi+39h]
0x1800225a2  mov     rcx, [rcx+10h]
0x1800225a6  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800225ad  mov     r9d, eax
0x1800225b0  call    WPP_SF_d
0x1800225b5  jmp     loc_180022A04
0x1800225ba  mov     rcx, [r13+18h]; pszString
0x1800225be  lea     rdx, [rsp+2F0h+pvFindPara]; pcbBinary
0x1800225c3  call    LmConvertCryptStringToBinary
0x1800225c8  mov     ebx, eax
0x1800225ca  test    eax, eax
0x1800225cc  jz      short loc_180022600
0x1800225ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800225d5  lea     rdi, WPP_GLOBAL_Control
0x1800225dc  cmp     rcx, rdi
0x1800225df  jz      loc_180022A04
0x1800225e5  test    byte ptr [rcx+1Ch], 2
0x1800225e9  jz      loc_180022A04
0x1800225ef  cmp     byte ptr [rcx+19h], 1
0x1800225f3  jb      loc_180022A04
0x1800225f9  mov     edx, 3Ah ; ':'
0x1800225fe  jmp     short loc_1800225A2
0x180022600  lea     rax, [rsp+2F0h+pvFindPara]
0x180022605  mov     [rsp+2F0h+pPrevCertContext], 0; pPrevCertContext
0x18002260e  mov     r9d, 10000h; dwFindType
0x180022614  mov     [rsp+2F0h+pvPara], rax; pvFindPara
0x180022619  xor     r8d, r8d; dwFindFlags
0x18002261c  mov     edx, edi; dwCertEncodingType
0x18002261e  mov     rcx, rsi; hCertStore
0x180022621  call    cs:__imp_CertFindCertificateInStore
0x180022627  mov     [rsp+2F0h+pCertContext], rax
0x18002262c  test    rax, rax
0x18002262f  jnz     short loc_180022679
0x180022631  mov     ebx, 490h
0x180022636  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002263d  lea     rdi, WPP_GLOBAL_Control
0x180022644  cmp     rcx, rdi
0x180022647  jz      loc_180022A04
0x18002264d  test    byte ptr [rcx+1Ch], 2
0x180022651  jz      loc_180022A04
0x180022657  cmp     byte ptr [rcx+19h], 1
0x18002265b  jb      loc_180022A04
0x180022661  lea     edx, [rax+3Bh]
0x180022664  mov     rcx, [rcx+10h]
0x180022668  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002266f  call    WPP_SF_
0x180022674  jmp     loc_180022A04
0x180022679  xor     esi, esi
0x18002267b  lea     rdi, [rsp+2F0h+cbBinary]
0x180022680  xor     r12d, r12d
0x180022683  mov     [rsp+2F0h+var_2C0], esi
0x180022687  xor     edx, edx; Val
0x180022689  mov     [rsp+2F0h+var_2BC], r12d
0x18002268e  lea     eax, [rsi+14h]
0x180022691  mov     ecx, eax
0x180022693  lea     r8d, [rsi+50h]; Size
0x180022697  rep stosd
0x180022699  lea     rcx, [rbp+1F0h+var_230]; void *
0x18002269d  call    memset_0
0x1800226a2  mov     r14, [rsp+2F0h+pCertContext]
0x1800226a7  lea     rdi, WPP_GLOBAL_Control
0x1800226ae  cmp     esi, 14h
0x1800226b1  jnb     loc_1800228A0
0x1800226b7  lea     rcx, [rbp+1F0h+var_1E0]
0x1800226bb  mov     edx, 40h ; '@'; dwPropId
0x1800226c0  lea     rax, [rsi+rsi*4]
0x1800226c4  lea     rax, [rcx+rax*4]
0x1800226c8  mov     rcx, r14; pCertContext
0x1800226cb  lea     r9, [rsp+2F0h+cbBinary]
0x1800226d0  mov     [rsp+2F0h+var_2B8], rax
0x1800226d5  mov     r8, rax; pvData
0x1800226d8  lea     r9, [r9+rsi*4]; pcbData
0x1800226dc  call    cs:__imp_CertGetCertificateContextProperty
0x1800226e2  test    eax, eax
0x1800226e4  jz      loc_180022870
0x1800226ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800226f1  cmp     rcx, rdi
0x1800226f4  jz      short loc_18002271A
0x1800226f6  test    byte ptr [rcx+1Ch], 2
0x1800226fa  jz      short loc_18002271A
0x1800226fc  cmp     byte ptr [rcx+19h], 2
0x180022700  jb      short loc_18002271A
0x180022702  mov     rcx, [rcx+10h]
0x180022706  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002270d  mov     edx, 3Fh ; '?'
0x180022712  mov     r9, r14
0x180022715  call    WPP_SF_q
0x18002271a  mov     eax, [rsp+rsi*4+2F0h+cbBinary]
0x18002271e  mov     r9d, 10000h; dwFindType
0x180022724  mov     rcx, [rsp+2F0h+hCertStore]; hCertStore
0x180022729  xor     r8d, r8d; dwFindFlags
0x18002272c  mov     dword ptr [rsp+2F0h+pbBinary], eax
0x180022730  mov     rax, [rsp+2F0h+var_2B8]
0x180022735  mov     [rsp+2F0h+pbBinary+8], rax
0x18002273a  lea     edx, [r9+1]; dwCertEncodingType
0x18002273e  lea     rax, [rsp+2F0h+pbBinary]
0x180022743  mov     [rsp+2F0h+pPrevCertContext], 0; pPrevCertContext
0x18002274c  mov     [rsp+2F0h+pvPara], rax; pvFindPara
0x180022751  call    cs:__imp_CertFindCertificateInStore
0x180022757  mov     [rsp+2F0h+var_2B8], rax
0x18002275c  test    rax, rax
0x18002275f  jz      loc_18002282D
0x180022765  mov     edx, dword ptr [rsp+2F0h+pbBinary]; cbBinary
0x180022769  lea     rax, [rbp+1F0h+var_230]
0x18002276d  mov     rcx, [rsp+2F0h+pbBinary+8]; pbBinary
0x180022772  lea     r15, [rax+rsi*4]
0x180022776  xor     r9d, r9d; pszString
0x180022779  mov     [rsp+2F0h+pvPara], r15; pcchString
0x18002277e  mov     r8d, 4000000Ch; dwFlags
0x180022784  call    cs:__imp_CryptBinaryToStringW
0x18002278a  test    eax, eax
0x18002278c  jz      short loc_1800227E4
0x18002278e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022795  cmp     rcx, rdi
0x180022798  jz      short loc_1800227BE
0x18002279a  test    byte ptr [rcx+1Ch], 2
0x18002279e  jz      short loc_1800227BE
0x1800227a0  cmp     byte ptr [rcx+19h], 2
0x1800227a4  jb      short loc_1800227BE
0x1800227a6  mov     r9d, [r15]
0x1800227a9  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800227b0  mov     rcx, [rcx+10h]
0x1800227b4  mov     edx, 41h ; 'A'
0x1800227b9  call    WPP_SF_d
0x1800227be  add     r12d, [r15]
0x1800227c1  mov     rcx, r14; pCertContext
0x1800227c4  mov     [rsp+2F0h+var_2BC], r12d
0x1800227c9  call    cs:__imp_CertFreeCertificateContext
0x1800227cf  mov     r14, [rsp+2F0h+var_2B8]
0x1800227d4  inc     esi
0x1800227d6  mov     [rsp+2F0h+var_2C0], esi
0x1800227da  mov     [rsp+2F0h+pCertContext], r14
0x1800227df  jmp     loc_1800226AE
0x1800227e4  call    cs:__imp_GetLastError
0x1800227ea  mov     ebx, eax
0x1800227ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800227f3  cmp     rcx, rdi
0x1800227f6  jz      loc_1800229EF
0x1800227fc  test    byte ptr [rcx+1Ch], 2
0x180022800  jz      loc_1800229EF
0x180022806  cmp     byte ptr [rcx+19h], 1
0x18002280a  jb      loc_1800229EF
0x180022810  mov     edx, 42h ; 'B'
0x180022815  mov     r9d, eax
0x180022818  mov     rcx, [rcx+10h]
0x18002281c  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180022823  call    WPP_SF_d
0x180022828  jmp     loc_1800229EF
0x18002282d  mov     ebx, 490h
0x180022832  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022839  cmp     rcx, rdi
0x18002283c  jz      loc_1800229EF
0x180022842  test    byte ptr [rcx+1Ch], 2
0x180022846  jz      loc_1800229EF
0x18002284c  cmp     byte ptr [rcx+19h], 1
0x180022850  jb      loc_1800229EF
0x180022856  mov     rcx, [rcx+10h]
0x18002285a  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180022861  mov     edx, 40h ; '@'
0x180022866  call    WPP_SF_
0x18002286b  jmp     loc_1800229EF
0x180022870  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022877  cmp     rcx, rdi
0x18002287a  jz      short loc_1800228C9
0x18002287c  test    byte ptr [rcx+1Ch], 2
0x180022880  jz      short loc_1800228A7
0x180022882  cmp     byte ptr [rcx+19h], 2
0x180022886  jb      short loc_1800228A7
0x180022888  mov     rcx, [rcx+10h]
0x18002288c  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180022893  mov     edx, 3Eh ; '>'
0x180022898  mov     r9, r14
0x18002289b  call    WPP_SF_q
0x1800228a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228a7  cmp     rcx, rdi; __annotation("TMF:",
0x1800228aa  jz      short loc_1800228C9
0x1800228ac  test    byte ptr [rcx+1Ch], 2
0x1800228b0  jz      short loc_1800228C9
0x1800228b2  cmp     byte ptr [rcx+19h], 2
0x1800228b6  jb      short loc_1800228C9
0x1800228b8  mov     rcx, [rcx+10h]
0x1800228bc  mov     r9d, esi
0x1800228bf  mov     dword ptr [rsp+2F0h+pvPara], r12d
0x1800228c4  call    WPP_SF_Dd
0x1800228c9  test    esi, esi
0x1800228cb  jnz     short loc_1800228DA
0x1800228cd  mov     qword ptr [r13+48h], 0
0x1800228d5  jmp     loc_1800229EF
0x1800228da  lea     rdx, ds:2[r12*2]; uBytes
0x1800228e2  mov     ecx, 40h ; '@'; uFlags
0x1800228e7  call    cs:__imp_LocalAlloc
0x1800228ed  mov     rsi, rax
0x1800228f0  test    rax, rax
0x1800228f3  jnz     short loc_180022927
0x1800228f5  lea     ebx, [rax+8]
0x1800228f8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800228ff  cmp     rcx, rdi
0x180022902  jz      loc_1800229EF
0x180022908  test    byte ptr [rcx+1Ch], 2
0x18002290c  jz      loc_1800229EF
0x180022912  cmp     byte ptr [rcx+19h], 1
0x180022916  jb      loc_1800229EF
0x18002291c  lea     edx, [rax+44h]
0x18002291f  mov     r9d, ebx
0x180022922  jmp     loc_180022818
0x180022927  mov     r12, rsi
0x18002292a  xor     r15d, r15d
0x18002292d  cmp     r15d, [rsp+2F0h+var_2C0]
0x180022932  jnb     short loc_1800229AF
0x180022934  mov     edx, [rsp+r15*4+2F0h+cbBinary]; cbBinary
0x180022939  lea     rax, [r15+r15*4]
0x18002293d  lea     r8, [rbp+1F0h+var_230]
0x180022941  mov     r9, r12; pszString
0x180022944  lea     r8, [r8+r15*4]
0x180022948  mov     [rsp+2F0h+var_2B8], r8
0x18002294d  lea     rcx, [rbp+1F0h+var_1E0]
0x180022951  mov     [rsp+2F0h+pvPara], r8; pcchString
0x180022956  lea     rcx, [rcx+rax*4]; pbBinary
0x18002295a  mov     r8d, 4000000Ch; dwFlags
0x180022960  call    cs:__imp_CryptBinaryToStringW
0x180022966  test    eax, eax
0x180022968  jz      short loc_180022985
0x18002296a  mov     rcx, [rsp+2F0h+var_2B8]
0x18002296f  mov     eax, [rcx]
0x180022971  mov     word ptr [r12+rax*2], 3Ah ; ':'
0x180022978  mov     eax, [rcx]
0x18002297a  inc     eax
0x18002297c  inc     r15d
0x18002297f  lea     r12, [r12+rax*2]
0x180022983  jmp     short loc_18002292D
0x180022985  call    cs:__imp_GetLastError
0x18002298b  mov     ebx, eax
0x18002298d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022994  cmp     rcx, rdi
0x180022997  jz      short loc_1800229EF
0x180022999  test    byte ptr [rcx+1Ch], 2
0x18002299d  jz      short loc_1800229EF
0x18002299f  cmp     byte ptr [rcx+19h], 1
0x1800229a3  jb      short loc_1800229EF
0x1800229a5  mov     edx, 45h ; 'E'
0x1800229aa  jmp     loc_180022815
0x1800229af  mov     edx, [rsp+2F0h+var_2BC]
0x1800229b3  xor     eax, eax
0x1800229b5  mov     [rsi+rdx*2], ax
0x1800229b9  mov     [r13+48h], rsi
0x1800229bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800229c4  cmp     rcx, rdi
0x1800229c7  jz      short loc_1800229EF
0x1800229c9  test    byte ptr [rcx+1Ch], 2
0x1800229cd  jz      short loc_1800229EF
0x1800229cf  cmp     byte ptr [rcx+19h], 2
0x1800229d3  jb      short loc_1800229EF
0x1800229d5  mov     rcx, [rcx+10h]
0x1800229d9  lea     edx, [rax+46h]
0x1800229dc  mov     r9, rsi
0x1800229df  mov     dword ptr [rsp+2F0h+pvPara], eax
  ... truncated ...
```
