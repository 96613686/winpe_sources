# AACertUtil::GetCertContextChainFromString(ushort *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x180006448`
- end: `0x18000696b`
- name: `?GetCertContextChainFromString@AACertUtil@@SAJPEAGPEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `1315`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, PCCERT_CHAIN_CONTEXT *ppChainContext)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800041a4`

## callees

- `0x1800022e6`
- `0x18000277c`
- `0x1800054b8`
- `0x180005658`
- `0x180006318`
- `0x180006448`
- `0x180006974`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180006867`
- `CRYPT32!CertCloseStore` at `0x180006867`
- `CRYPT32!CertOpenStore` at `0x180006503`
- `CRYPT32!CertOpenStore` at `0x180006503`
- `CRYPT32!CertFreeCertificateContext` at `0x180006857`
- `CRYPT32!CertFreeCertificateContext` at `0x180006857`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000676e`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18000676e`
- `CRYPT32!CryptStringToBinaryW` at `0x1800066aa`
- `CRYPT32!CryptStringToBinaryW` at `0x180006711`
- `CRYPT32!CryptStringToBinaryW` at `0x1800066aa`
- `CRYPT32!CryptStringToBinaryW` at `0x180006711`
- `KERNEL32!GetLastError` at `0x180006511`
- `KERNEL32!GetLastError` at `0x1800066b4`
- `KERNEL32!GetLastError` at `0x18000671d`
- `KERNEL32!GetLastError` at `0x180006778`
- `KERNEL32!GetLastError` at `0x180006511`
- `KERNEL32!GetLastError` at `0x1800066b4`
- `KERNEL32!GetLastError` at `0x18000671d`
- `KERNEL32!GetLastError` at `0x180006778`
- `KERNEL32!LocalFree` at `0x180006735`
- `KERNEL32!LocalFree` at `0x180006795`
- `KERNEL32!LocalFree` at `0x1800067ae`
- `KERNEL32!LocalFree` at `0x18000683f`
- `KERNEL32!LocalFree` at `0x180006848`
- `KERNEL32!LocalFree` at `0x180006735`
- `KERNEL32!LocalFree` at `0x180006795`
- `KERNEL32!LocalFree` at `0x1800067ae`
- `KERNEL32!LocalFree` at `0x18000683f`
- `KERNEL32!LocalFree` at `0x180006848`
- `KERNEL32!LocalAlloc` at `0x180006597`
- `KERNEL32!LocalAlloc` at `0x1800066d9`
- `KERNEL32!LocalAlloc` at `0x180006597`
- `KERNEL32!LocalAlloc` at `0x1800066d9`

## string_xrefs

- `0x1800064eb`: `TSG-TEMP-STORE`
- `0x180006559`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall AACertUtil::GetCertContextChainFromString(
        unsigned __int16 *Src,
        PCCERT_CHAIN_CONTEXT *ppChainContext)
{
  HCERTSTORE v4; // r15
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  signed int SimpleChains; // ebx
  signed int LastError; // eax
  __int64 v10; // rax
  SIZE_T v11; // rbx
  wchar_t *v12; // rax
  wchar_t *v13; // r14
  wchar_t **v14; // r8
  unsigned int v15; // r14d
  wchar_t *i; // rcx
  signed int v17; // eax
  HLOCAL v18; // rdi
  signed int v19; // eax
  PCCERT_CONTEXT *p_pCertContext; // rcx
  signed int v21; // eax
  wchar_t *v22; // rsi
  _QWORD *v23; // rcx
  int v24; // edx
  const wchar_t *v25; // r9
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-8h] BYREF
  DWORD pcbBinary; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v30; // [rsp+A0h] [rbp+50h] BYREF
  wchar_t *v31; // [rsp+A8h] [rbp+58h]

  pCertContext = 0;
  hMem = 0;
  v4 = 0;
  v30 = 0;
  if ( !Src )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 36;
    v7 = L"pszString";
LABEL_6:
    WPP_SF_S(v5[2], v6, WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids, v7);
LABEL_7:
    SimpleChains = -2147024809;
    goto LABEL_68;
  }
  if ( !ppChainContext )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 37;
    v7 = L"pChainContext";
    goto LABEL_6;
  }
  v4 = CertOpenStore((LPCSTR)2, 0, 0, 0x2000u, L"TSG-TEMP-STORE");
  if ( v4 )
    goto LABEL_21;
  LastError = GetLastError();
  SimpleChains = LastError;
  if ( LastError > 0 )
    SimpleChains = (unsigned __int16)LastError | 0x80070000;
  if ( SimpleChains >= 0 )
  {
LABEL_21:
    v10 = -1;
    do
      ++v10;
    while ( Src[v10] );
    v11 = 2 * v10 + 2;
    v12 = (wchar_t *)LocalAlloc(0x40u, v11);
    v31 = v12;
    v13 = v12;
    if ( v12 )
    {
      memcpy_0(v12, Src, v11);
      SimpleChains = AACertUtil::GetSimpleChains(v13, (unsigned __int16 ***)&hMem, &v30);
      if ( SimpleChains >= 0 )
      {
        v15 = 0;
        if ( v30 )
        {
LABEL_35:
          for ( i = (wchar_t *)*((_QWORD *)hMem + v15); ; i = 0 )
          {
            v22 = wcstok_mvcrt_legacy_two_parameter_form(i, L";", v14);
            if ( !v22 )
            {
              if ( ++v15 < v30 )
                goto LABEL_35;
              goto LABEL_58;
            }
            pcbBinary = 0;
            if ( !CryptStringToBinaryW(v22, 0, 0, 0, &pcbBinary, 0, 0) )
            {
              v17 = GetLastError();
              SimpleChains = v17;
              if ( v17 > 0 )
                SimpleChains = (unsigned __int16)v17 | 0x80070000;
              if ( SimpleChains < 0 )
              {
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v24 = 41;
LABEL_79:
                  v25 = L"CryptStringToBinary";
                  goto LABEL_63;
                }
                goto LABEL_64;
              }
            }
            v18 = LocalAlloc(0x40u, pcbBinary);
            if ( !v18 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  42,
                  WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids,
                  L"pbBinary");
              }
              SimpleChains = -2147024882;
              goto LABEL_64;
            }
            if ( !CryptStringToBinaryW(v22, 0, 0, (BYTE *)v18, &pcbBinary, 0, 0) )
            {
              v19 = GetLastError();
              SimpleChains = v19;
              if ( v19 > 0 )
                SimpleChains = (unsigned __int16)v19 | 0x80070000;
              LocalFree(v18);
              v18 = 0;
              if ( SimpleChains < 0 )
              {
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v24 = 43;
                  goto LABEL_79;
                }
                goto LABEL_64;
              }
            }
            p_pCertContext = &pCertContext;
            if ( pCertContext )
              p_pCertContext = 0;
            if ( !CertAddEncodedCertificateToStore(v4, 0x10001u, (const BYTE *)v18, pcbBinary, 2u, p_pCertContext) )
            {
              v21 = GetLastError();
              SimpleChains = v21;
              if ( v21 > 0 )
                SimpleChains = (unsigned __int16)v21 | 0x80070000;
              if ( v18 )
              {
                LocalFree(v18);
                v18 = 0;
              }
              if ( SimpleChains < 0 )
                break;
            }
            if ( v18 )
              LocalFree(v18);
          }
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v24 = 44;
            v25 = L"CertAddEncodedCertificateToStore";
            goto LABEL_63;
          }
        }
        else
        {
LABEL_58:
          SimpleChains = AACertUtil::GetCertContextChainFromCertContext(pCertContext, v4, ppChainContext);
          if ( SimpleChains < 0 )
          {
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = 45;
              v25 = L"CAAQuarantineUtil::GetCertContextChainFromCertContext";
LABEL_63:
              WPP_SF_Sd(
                v23[2],
                v24,
                (unsigned int)WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids,
                (_DWORD)v25,
                SimpleChains);
            }
          }
        }
LABEL_64:
        v13 = v31;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids,
          (unsigned int)L"GetSimpleChains",
          SimpleChains);
      }
      if ( hMem )
        LocalFree(hMem);
      LocalFree(v13);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids,
          L"pszStringTmp");
      }
      SimpleChains = -2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids,
      (unsigned int)L"CertOpenStore",
      SimpleChains);
  }
LABEL_68:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v4 )
    CertCloseStore(v4, 0);
  if ( SimpleChains < 0 )
    return (unsigned int)-2147001872;
  return (unsigned int)SimpleChains;
}

```

## disassembly

```asm
0x180006448  push    rbp
0x18000644a  push    rbx
0x18000644b  push    rsi
0x18000644c  push    rdi
0x18000644d  push    r13
0x18000644f  push    r14
0x180006451  push    r15
0x180006453  mov     rbp, rsp
0x180006456  sub     rsp, 50h
0x18000645a  xor     esi, esi
0x18000645c  mov     r13, rdx
0x18000645f  mov     [rbp+pCertContext], rsi
0x180006463  mov     rdi, rcx
0x180006466  mov     [rbp+hMem], rsi
0x18000646a  mov     r15d, esi
0x18000646d  mov     [rbp+arg_10], esi
0x180006470  test    rcx, rcx
0x180006473  jnz     short loc_1800064B8
0x180006475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000647c  lea     rax, WPP_GLOBAL_Control
0x180006483  cmp     rcx, rax
0x180006486  jz      short loc_1800064AE
0x180006488  test    byte ptr [rcx+1Ch], 8
0x18000648c  jz      short loc_1800064AE
0x18000648e  cmp     byte ptr [rcx+19h], 2
0x180006492  jb      short loc_1800064AE
0x180006494  lea     edx, [rdi+24h]
0x180006497  lea     r9, aPszstring; "pszString"
0x18000649e  mov     rcx, [rcx+10h]
0x1800064a2  lea     r8, WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids
0x1800064a9  call    WPP_SF_S
0x1800064ae  mov     ebx, 80070057h
0x1800064b3  jmp     loc_18000684E
0x1800064b8  test    r13, r13
0x1800064bb  jnz     short loc_1800064E9
0x1800064bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064c4  lea     rax, WPP_GLOBAL_Control
0x1800064cb  cmp     rcx, rax
0x1800064ce  jz      short loc_1800064AE
0x1800064d0  test    byte ptr [rcx+1Ch], 8
0x1800064d4  jz      short loc_1800064AE
0x1800064d6  cmp     byte ptr [rcx+19h], 2
0x1800064da  jb      short loc_1800064AE
0x1800064dc  lea     edx, [r13+25h]
0x1800064e0  lea     r9, aPchaincontext; "pChainContext"
0x1800064e7  jmp     short loc_18000649E
0x1800064e9  xor     edx, edx; dwEncodingType
0x1800064eb  lea     rax, aTsgTempStore; "TSG-TEMP-STORE"
0x1800064f2  mov     r9d, 2000h; dwFlags
0x1800064f8  mov     [rsp+50h+pvPara], rax; pvPara
0x1800064fd  xor     r8d, r8d; hCryptProv
0x180006500  lea     ecx, [rdx+2]; lpszStoreProvider
0x180006503  call    cs:__imp_CertOpenStore
0x180006509  mov     r15, rax
0x18000650c  test    rax, rax
0x18000650f  jnz     short loc_18000657A
0x180006511  call    cs:__imp_GetLastError
0x180006517  mov     ebx, eax
0x180006519  test    eax, eax
0x18000651b  jle     short loc_180006526
0x18000651d  movzx   ebx, ax
0x180006520  or      ebx, 80070000h
0x180006526  test    ebx, ebx
0x180006528  jns     short loc_18000657A
0x18000652a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006531  lea     rax, WPP_GLOBAL_Control
0x180006538  cmp     rcx, rax
0x18000653b  jz      loc_18000684E
0x180006541  test    byte ptr [rcx+1Ch], 8
0x180006545  jz      loc_18000684E
0x18000654b  cmp     byte ptr [rcx+19h], 2
0x18000654f  jb      loc_18000684E
0x180006555  mov     rcx, [rcx+10h]
0x180006559  lea     r9, aCertopenstore; "CertOpenStore"
0x180006560  mov     edx, 26h ; '&'
0x180006565  mov     dword ptr [rsp+50h+pvPara], ebx
0x180006569  lea     r8, WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids
0x180006570  call    WPP_SF_Sd
0x180006575  jmp     loc_18000684E
0x18000657a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000657e  inc     rax
0x180006581  cmp     [rdi+rax*2], si
0x180006585  jnz     short loc_18000657E
0x180006587  lea     rbx, ds:2[rax*2]
0x18000658f  mov     ecx, 40h ; '@'; uFlags
0x180006594  mov     rdx, rbx; uBytes
0x180006597  call    cs:__imp_LocalAlloc
0x18000659d  mov     [rbp+arg_18], rax
0x1800065a1  mov     r14, rax
0x1800065a4  test    rax, rax
0x1800065a7  jnz     short loc_1800065ED
0x1800065a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065b0  lea     rax, WPP_GLOBAL_Control
0x1800065b7  cmp     rcx, rax
0x1800065ba  jz      short loc_1800065E3
0x1800065bc  test    byte ptr [rcx+1Ch], 8
0x1800065c0  jz      short loc_1800065E3
0x1800065c2  cmp     byte ptr [rcx+19h], 2
0x1800065c6  jb      short loc_1800065E3
0x1800065c8  mov     rcx, [rcx+10h]
0x1800065cc  lea     edx, [r14+27h]
0x1800065d0  lea     r9, aPszstringtmp; "pszStringTmp"
0x1800065d7  lea     r8, WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids
0x1800065de  call    WPP_SF_S
0x1800065e3  mov     ebx, 8007000Eh
0x1800065e8  jmp     loc_18000684E
0x1800065ed  mov     r8, rbx; Size
0x1800065f0  mov     rdx, rdi; Src
0x1800065f3  mov     rcx, r14; void *
0x1800065f6  call    memcpy_0
0x1800065fb  lea     r8, [rbp+arg_10]; unsigned int *
0x1800065ff  mov     rcx, r14; Str
0x180006602  lea     rdx, [rbp+hMem]; unsigned __int16 ***
0x180006606  call    ?GetSimpleChains@AACertUtil@@CAJPEAGPEAPEAPEAGPEAK@Z; AACertUtil::GetSimpleChains(ushort *,ushort * * *,ulong *)
0x18000660b  mov     ebx, eax
0x18000660d  test    eax, eax
0x18000660f  jns     short loc_180006661
0x180006611  mov     rcx, cs:WPP_GLOBAL_Control
0x180006618  lea     rax, WPP_GLOBAL_Control
0x18000661f  cmp     rcx, rax
0x180006622  jz      loc_180006833
0x180006628  test    byte ptr [rcx+1Ch], 8
0x18000662c  jz      loc_180006833
0x180006632  cmp     byte ptr [rcx+19h], 2
0x180006636  jb      loc_180006833
0x18000663c  mov     rcx, [rcx+10h]
0x180006640  lea     r9, aGetsimplechain; "GetSimpleChains"
0x180006647  mov     edx, 28h ; '('
0x18000664c  mov     dword ptr [rsp+50h+pvPara], ebx
0x180006650  lea     r8, WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids
0x180006657  call    WPP_SF_Sd
0x18000665c  jmp     loc_180006833
0x180006661  mov     r14d, esi
0x180006664  cmp     [rbp+arg_10], esi
0x180006667  jbe     loc_1800067DB
0x18000666d  mov     rax, [rbp+hMem]
0x180006671  mov     ecx, r14d
0x180006674  mov     rcx, [rax+rcx*8]
0x180006678  jmp     loc_1800067B6
0x18000667d  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x180006686  lea     rax, [rbp+pcbBinary]
0x18000668a  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x180006693  xor     r9d, r9d; pbBinary
0x180006696  xor     r8d, r8d; dwFlags
0x180006699  mov     [rsp+50h+pvPara], rax; pcbBinary
0x18000669e  xor     edx, edx; cchString
0x1800066a0  mov     [rbp+pcbBinary], 0
0x1800066a7  mov     rcx, rsi; pszString
0x1800066aa  call    cs:__imp_CryptStringToBinaryW
0x1800066b0  test    eax, eax
0x1800066b2  jnz     short loc_1800066D1
0x1800066b4  call    cs:__imp_GetLastError
0x1800066ba  mov     ebx, eax
0x1800066bc  test    eax, eax
0x1800066be  jle     short loc_1800066C9
0x1800066c0  movzx   ebx, ax
0x1800066c3  or      ebx, 80070000h
0x1800066c9  test    ebx, ebx
0x1800066cb  js      loc_180006888
0x1800066d1  mov     edx, [rbp+pcbBinary]; uBytes
0x1800066d4  mov     ecx, 40h ; '@'; uFlags
0x1800066d9  call    cs:__imp_LocalAlloc
0x1800066df  mov     rdi, rax
0x1800066e2  test    rax, rax
0x1800066e5  jz      loc_180006926
0x1800066eb  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x1800066f4  lea     rax, [rbp+pcbBinary]
0x1800066f8  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x180006701  mov     r9, rdi; pbBinary
0x180006704  xor     r8d, r8d; dwFlags
0x180006707  mov     [rsp+50h+pvPara], rax; pcbBinary
0x18000670c  xor     edx, edx; cchString
0x18000670e  mov     rcx, rsi; pszString
0x180006711  call    cs:__imp_CryptStringToBinaryW
0x180006717  xor     esi, esi
0x180006719  test    eax, eax
0x18000671b  jnz     short loc_180006746
0x18000671d  call    cs:__imp_GetLastError
0x180006723  mov     ebx, eax
0x180006725  test    eax, eax
0x180006727  jle     short loc_180006732
0x180006729  movzx   ebx, ax
0x18000672c  or      ebx, 80070000h
0x180006732  mov     rcx, rdi; hMem
0x180006735  call    cs:__imp_LocalFree
0x18000673b  mov     rdi, rsi
0x18000673e  test    ebx, ebx
0x180006740  js      loc_1800068B8
0x180006746  cmp     [rbp+pCertContext], rsi
0x18000674a  lea     rcx, [rbp+pCertContext]
0x18000674e  mov     r9d, [rbp+pcbBinary]; cbCertEncoded
0x180006752  mov     r8, rdi; pbCertEncoded
0x180006755  cmovnz  rcx, rsi
0x180006759  mov     edx, 10001h; dwCertEncodingType
0x18000675e  mov     [rsp+50h+pdwSkip], rcx; ppCertContext
0x180006763  mov     rcx, r15; hCertStore
0x180006766  mov     dword ptr [rsp+50h+pvPara], 2; dwAddDisposition
0x18000676e  call    cs:__imp_CertAddEncodedCertificateToStore
0x180006774  test    eax, eax
0x180006776  jnz     short loc_1800067A6
0x180006778  call    cs:__imp_GetLastError
0x18000677e  mov     ebx, eax
0x180006780  test    eax, eax
0x180006782  jle     short loc_18000678D
0x180006784  movzx   ebx, ax
0x180006787  or      ebx, 80070000h
0x18000678d  test    rdi, rdi
0x180006790  jz      short loc_18000679E
0x180006792  mov     rcx, rdi; hMem
0x180006795  call    cs:__imp_LocalFree
0x18000679b  mov     rdi, rsi
0x18000679e  test    ebx, ebx
0x1800067a0  js      loc_1800068EA
0x1800067a6  test    rdi, rdi
0x1800067a9  jz      short loc_1800067B4
0x1800067ab  mov     rcx, rdi; hMem
0x1800067ae  call    cs:__imp_LocalFree
0x1800067b4  xor     ecx, ecx; String
0x1800067b6  lea     rdx, Delimiter; ";"
0x1800067bd  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800067c2  mov     rsi, rax
0x1800067c5  test    rax, rax
0x1800067c8  jnz     loc_18000667D
0x1800067ce  inc     r14d
0x1800067d1  cmp     r14d, [rbp+arg_10]
0x1800067d5  jb      loc_18000666D
0x1800067db  mov     rcx, [rbp+pCertContext]; pCertContext
0x1800067df  mov     r8, r13; ppChainContext
0x1800067e2  mov     rdx, r15; hAdditionalStore
0x1800067e5  call    ?GetCertContextChainFromCertContext@AACertUtil@@SAJPEBU_CERT_CONTEXT@@PEAXPEAPEBU_CERT_CHAIN_CONTEXT@@@Z; AACertUtil::GetCertContextChainFromCertContext(_CERT_CONTEXT const *,void *,_CERT_CHAIN_CONTEXT const * *)
0x1800067ea  mov     ebx, eax
0x1800067ec  test    eax, eax
0x1800067ee  jns     short loc_18000682F
0x1800067f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067f7  lea     rax, WPP_GLOBAL_Control
0x1800067fe  cmp     rcx, rax
0x180006801  jz      short loc_18000682F
0x180006803  test    byte ptr [rcx+1Ch], 8
0x180006807  jz      short loc_18000682F
0x180006809  cmp     byte ptr [rcx+19h], 2
0x18000680d  jb      short loc_18000682F
0x18000680f  mov     edx, 2Dh ; '-'
0x180006814  lea     r9, aCaaquarantineu; "CAAQuarantineUtil::GetCertContextChainF"...
0x18000681b  mov     rcx, [rcx+10h]
0x18000681f  lea     r8, WPP_16ff08ea05dc369e4cbb6ae311253e82_Traceguids
0x180006826  mov     dword ptr [rsp+50h+pvPara], ebx
0x18000682a  call    WPP_SF_Sd
0x18000682f  mov     r14, [rbp+arg_18]
0x180006833  mov     rax, [rbp+hMem]
0x180006837  test    rax, rax
0x18000683a  jz      short loc_180006845
0x18000683c  mov     rcx, rax; hMem
0x18000683f  call    cs:__imp_LocalFree
0x180006845  mov     rcx, r14; hMem
0x180006848  call    cs:__imp_LocalFree
0x18000684e  mov     rcx, [rbp+pCertContext]; pCertContext
0x180006852  test    rcx, rcx
0x180006855  jz      short loc_18000685D
0x180006857  call    cs:__imp_CertFreeCertificateContext
0x18000685d  test    r15, r15
0x180006860  jz      short loc_18000686D
0x180006862  xor     edx, edx; dwFlags
0x180006864  mov     rcx, r15; hCertStore
0x180006867  call    cs:__imp_CertCloseStore
0x18000686d  mov     eax, 800759F0h
0x180006872  test    ebx, ebx
0x180006874  cmovs   ebx, eax
0x180006877  mov     eax, ebx
0x180006879  add     rsp, 50h
0x18000687d  pop     r15
0x18000687f  pop     r14
0x180006881  pop     r13
0x180006883  pop     rdi
0x180006884  pop     rsi
0x180006885  pop     rbx
0x180006886  pop     rbp
0x180006887  retn
0x180006888  mov     rcx, cs:WPP_GLOBAL_Control
0x18000688f  lea     rax, WPP_GLOBAL_Control
0x180006896  cmp     rcx, rax
0x180006899  jz      short loc_18000682F
0x18000689b  test    byte ptr [rcx+1Ch], 8
0x18000689f  jz      short loc_18000682F
0x1800068a1  cmp     byte ptr [rcx+19h], 2
0x1800068a5  jb      short loc_18000682F
0x1800068a7  mov     edx, 29h ; ')'
0x1800068ac  lea     r9, aCryptstringtob; "CryptStringToBinary"
0x1800068b3  jmp     loc_18000681B
0x1800068b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068bf  lea     rax, WPP_GLOBAL_Control
0x1800068c6  cmp     rcx, rax
0x1800068c9  jz      loc_18000682F
0x1800068cf  test    byte ptr [rcx+1Ch], 8
0x1800068d3  jz      loc_18000682F
0x1800068d9  cmp     byte ptr [rcx+19h], 2
0x1800068dd  jb      loc_18000682F
0x1800068e3  mov     edx, 2Bh ; '+'
0x1800068e8  jmp     short loc_1800068AC
0x1800068ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068f1  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
