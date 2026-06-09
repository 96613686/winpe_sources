# DetermineSubCAIdentity

- ea: `0x18008aa28`
- end: `0x18008b1ac`
- name: `DetermineSubCAIdentity`
- size: `1924`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18008b748`

## callees

- `0x180006ac4`
- `0x1800819c0`
- `0x180081a38`
- `0x180081adc`
- `0x18008aa28`
- `0x18008bb84`
- `0x18008bc90`
- `0x18008c7f8`
- `0x18008c874`
- `0x180090bc8`
- `0x18009b050`
- `0x18009b0b8`
- `0x1800a2060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ab36`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008b15b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008b15b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008ae38`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008af96`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008ae38`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008af96`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18008af21`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18008af5a`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18008af21`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18008af5a`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x18008ab11`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x18008ab11`

## string_xrefs

- `0x18008adbd`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
__int64 __fastcall DetermineSubCAIdentity(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // r12
  signed int CertHashAlgorithm; // esi
  __int64 v5; // rcx
  signed int LastError; // ecx
  signed int v7; // eax
  signed int v8; // eax
  char IsEnabled; // al
  size_t v10; // r15
  __int64 v11; // rdi
  __int64 v12; // r13
  size_t v13; // r8
  unsigned int v14; // ebx
  char v15; // al
  __int64 v16; // rdi
  __int64 v17; // r12
  __int64 v18; // r13
  unsigned int v19; // ebx
  int v20; // eax
  size_t v21; // rdx
  __int64 v22; // r13
  unsigned int v23; // ebx
  int v24; // eax
  __int64 v25; // rbx
  _WORD *v26; // rbx
  DWORD v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rdi
  BYTE *v30; // rdx
  _WORD *v31; // rcx
  __int64 v32; // r8
  _WORD *v33; // rcx
  char v34; // al
  __int64 v35; // rdi
  __int64 *v36; // rax
  __int64 v37; // rbx
  struct _CTL_USAGE *v38; // rax
  struct _CTL_USAGE *v39; // rsi
  int v40; // ebx
  void *v41; // rcx
  void *v42; // rbx
  WCHAR *v43; // rcx
  WCHAR *v44; // rdi
  PCERT_PUBLIC_KEY_INFO pInfo; // [rsp+28h] [rbp-69h]
  PCERT_PUBLIC_KEY_INFO pInfoa; // [rsp+28h] [rbp-69h]
  DWORD *pcbComputedHash; // [rsp+38h] [rbp-59h]
  char v49; // [rsp+48h] [rbp-49h]
  int v50; // [rsp+4Ch] [rbp-45h]
  PCNZWCH lpString2; // [rsp+50h] [rbp-41h] BYREF
  void *Block; // [rsp+58h] [rbp-39h] BYREF
  __int64 v53; // [rsp+60h] [rbp-31h]
  size_t Size; // [rsp+68h] [rbp-29h]
  __int64 v55; // [rsp+70h] [rbp-21h]
  PCCERT_CONTEXT pCertContext; // [rsp+78h] [rbp-19h]
  void *lpMem; // [rsp+80h] [rbp-11h]
  __int64 v58; // [rsp+88h] [rbp-9h]
  __int64 v59; // [rsp+90h] [rbp-1h]
  DWORD pcbUsage; // [rsp+98h] [rbp+7h] BYREF
  DWORD v61; // [rsp+9Ch] [rbp+Bh] BYREF
  BYTE Buf2[16]; // [rsp+A0h] [rbp+Fh] BYREF
  __int128 v63; // [rsp+B0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v58 = a3;
  LODWORD(lpString2) = a2;
  v61 = 32;
  v3 = 0;
  lpMem = 0;
  CertHashAlgorithm = 0;
  *(_OWORD *)Buf2 = 0;
  v63 = 0;
  if ( !a1 )
  {
    CertHashAlgorithm = -2147467261;
    goto LABEL_84;
  }
  v5 = **(_QWORD **)(a1 + 16);
  v55 = v5;
  if ( *(_DWORD *)(v5 + 12) != 3 )
  {
    WUTrace(0, 0, 32, 1, 0, L"Cert chain length check failed, length=%d", *(_DWORD *)(v5 + 12));
    LODWORD(v3) = 1;
    goto LABEL_84;
  }
  v59 = *(_QWORD *)(*(_QWORD *)(v5 + 16) + 8LL);
  pCertContext = *(PCCERT_CONTEXT *)(v59 + 8);
  if ( !CryptHashPublicKeyInfo(0, 0x800Cu, 0, 1u, &pCertContext->pCertInfo->SubjectPublicKeyInfo, Buf2, &v61) )
  {
LABEL_6:
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( v7 >= 0 )
    {
      CertHashAlgorithm = -2147467259;
    }
    else
    {
      v8 = GetLastError();
      CertHashAlgorithm = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        CertHashAlgorithm = v8;
    }
    goto LABEL_84;
  }
  CertHashAlgorithm = -2145078525;
  if ( v61 != 32 )
    goto LABEL_84;
  v50 = 1;
  pcbUsage = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl);
  v10 = v61;
  v11 = 0;
  if ( IsEnabled )
  {
    v49 = 0;
    v12 = 2;
    LODWORD(Block) = v61;
    v13 = v61;
    Size = v61;
    do
    {
      v14 = 0;
      while ( 1 )
      {
        v53 = v14;
        if ( !memcmp(&qword_1800D98B0[6 * v3 + 6 * v14], Buf2, v13) )
          break;
        ++v14;
        v13 = v10;
        if ( v14 >= 5 )
        {
          v15 = v49;
          goto LABEL_21;
        }
      }
      v50 = dword_1800D98A0[12 * v11 + 12 * v53];
      v15 = 1;
      v49 = 1;
      pcbUsage = dword_1800D98A4[12 * v11 + 12 * v53];
LABEL_21:
      v3 += 5;
      v11 += 5;
      v13 = v10;
      --v12;
    }
    while ( v12 );
    if ( !v15 )
    {
      v16 = 0;
      v17 = 0;
      v18 = 2;
      do
      {
        v19 = 0;
        while ( 1 )
        {
          v53 = v19;
          if ( !memcmp(&qword_1800D9540[6 * v17 + 6 * v19], Buf2, Size) )
            break;
          if ( ++v19 >= 9 )
            goto LABEL_29;
        }
        v20 = dword_1800D9530[12 * v16 + 12 * v53];
        pcbUsage = dword_1800D9534[12 * v16 + 12 * v53];
        v50 = v20;
LABEL_29:
        v17 += 9;
        v16 += 9;
        --v18;
      }
      while ( v18 );
      LODWORD(v10) = (_DWORD)Block;
    }
  }
  else
  {
    v21 = v61;
    v22 = 2;
    do
    {
      v23 = 0;
      while ( 1 )
      {
        Size = v23;
        if ( !memcmp(&qword_1800D98B0[6 * v3 + 6 * v23], Buf2, v21) )
          break;
        ++v23;
        v21 = v10;
        if ( v23 >= 5 )
          goto LABEL_37;
      }
      v24 = dword_1800D98A0[12 * v11 + 12 * Size];
      pcbUsage = dword_1800D98A4[12 * v11 + 12 * Size];
      v50 = v24;
LABEL_37:
      v3 += 5;
      v11 += 5;
      v21 = v10;
      --v22;
    }
    while ( v22 );
  }
  LODWORD(v3) = v50;
  if ( v50 == 1 )
  {
    if ( !(_DWORD)lpString2 || !v58 )
      goto LABEL_46;
    v25 = 0;
    while ( *(_DWORD *)(v58 + 24 * v25 + 8) != 32
         || memcmp(*(const void **)(v58 + 24 * v25 + 16), Buf2, (unsigned int)v10) )
    {
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= (unsigned int)lpString2 )
      {
        LODWORD(v3) = 1;
        goto LABEL_46;
      }
    }
    LODWORD(v3) = *(_DWORD *)(v58 + 24 * v25);
    v27 = *(_DWORD *)(v58 + 24 * v25 + 4);
    if ( (_DWORD)v3 == 1 )
    {
LABEL_46:
      v26 = SafeSusAllocArray((unsigned int)(2 * v10 + 1), 2u);
      if ( v26 )
      {
        v30 = Buf2;
        v31 = v26;
        if ( (_DWORD)v10 )
        {
          v32 = (unsigned int)v10;
          do
          {
            *v31 = word_1800C72E0[(unsigned __int64)*v30 >> 4];
            v33 = v31 + 1;
            v34 = *v30++;
            *v33 = word_1800C72E0[v34 & 0xF];
            v31 = v33 + 1;
            --v32;
          }
          while ( v32 );
        }
        *v31 = 0;
        LODWORD(pcbComputedHash) = v61;
        WUTrace(
          0,
          0,
          32,
          1,
          0,
          L"Hash of public key doesn't match the known values, cbKeyId=%d, rgbKeyId=%ws.",
          pcbComputedHash,
          v26);
        SusFree(v26);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
          v26 == 0 ? (const char *)0x8007000ELL : 0,
          (int)pInfo);
        LODWORD(pInfoa) = -2147024882;
        WUTrace(
          0,
          0,
          32,
          1,
          pInfoa,
          L"Hash of public key doesn't match the known values, but failed to get the hash as hex string.");
      }
      goto LABEL_84;
    }
  }
  else
  {
    v27 = pcbUsage;
  }
  if ( v27 )
  {
    v28 = 0;
    v29 = *(_QWORD *)(v59 + 40);
    if ( !*(_DWORD *)v29 )
    {
LABEL_53:
      WUTrace(0, 0, 32, 1, 0, L"EKU not found for SubCA");
      goto LABEL_84;
    }
    while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, *(PCNZCH *)(*(_QWORD *)(v29 + 8) + 8LL * v28), -1) != 2 )
    {
      if ( ++v28 >= *(_DWORD *)v29 )
        goto LABEL_53;
    }
    v35 = v55;
    pcbUsage = 0;
    v36 = *(__int64 **)(v55 + 16);
    v37 = *v36;
    if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(*v36 + 8), 0, 0, &pcbUsage) )
      goto LABEL_6;
    v38 = (struct _CTL_USAGE *)SusAlloc(pcbUsage);
    lpMem = v38;
    v39 = v38;
    if ( !v38 )
    {
      CertHashAlgorithm = -2147024882;
      goto LABEL_84;
    }
    if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(v37 + 8), 0, v38, &pcbUsage) )
      goto LABEL_6;
    v40 = 0;
    if ( !v39->cUsageIdentifier )
    {
LABEL_66:
      WUTrace(0, 0, 32, 1, 0, L"EKU not found for leaf cert");
      CertHashAlgorithm = -2145078525;
      goto LABEL_84;
    }
    while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, v39->rgpszUsageIdentifier[v40], -1) != 2 )
    {
      if ( ++v40 >= v39->cUsageIdentifier )
        goto LABEL_66;
    }
  }
  else
  {
    v35 = v55;
  }
  Block = 0;
  lpString2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::GetImpl'::`2'::impl) )
  {
    CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&Block);
    if ( CertHashAlgorithm < 0 )
      goto LABEL_70;
    v42 = Block;
    CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher((const wchar_t *)Block);
    if ( CertHashAlgorithm < 0 )
    {
LABEL_73:
      if ( !v42 )
        goto LABEL_84;
      v41 = v42;
LABEL_71:
      operator delete(v41);
      goto LABEL_84;
    }
    CertHashAlgorithm = GetCertHashAlgorithm(*(PCCERT_CONTEXT *)(**(_QWORD **)(v35 + 16) + 8LL), (wchar_t **)&lpString2);
    if ( CertHashAlgorithm < 0 )
    {
      v43 = (WCHAR *)lpString2;
      if ( !lpString2 )
        goto LABEL_73;
LABEL_77:
      operator delete(v43);
      goto LABEL_73;
    }
    v44 = (WCHAR *)lpString2;
    CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString2);
    if ( CertHashAlgorithm >= 0 )
      goto LABEL_79;
LABEL_93:
    if ( !v44 )
      goto LABEL_73;
    v43 = v44;
    goto LABEL_77;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&Block);
  if ( CertHashAlgorithm < 0 )
  {
LABEL_70:
    v41 = Block;
    if ( !Block )
      goto LABEL_84;
    goto LABEL_71;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(*(PCCERT_CONTEXT *)(**(_QWORD **)(v35 + 16) + 8LL), (wchar_t **)&lpString2);
  if ( CertHashAlgorithm < 0 )
  {
    if ( lpString2 )
      operator delete((void *)lpString2);
    goto LABEL_70;
  }
  v42 = Block;
  v44 = (WCHAR *)lpString2;
  if ( CompareStringW(0x7Fu, 0, (PCNZWCH)Block, -1, lpString2, -1) != 2 )
  {
    WUTrace(0, 0, 32, 1, 0, L"Inconsistent hash algorithm. Leaf:%ws, SubCA:%ws", v44, v42);
    CertHashAlgorithm = -2145078525;
    goto LABEL_93;
  }
LABEL_79:
  if ( v44 )
    operator delete(v44);
  if ( v42 )
    operator delete(v42);
  CertHashAlgorithm = 0;
LABEL_84:
  SusFree(lpMem);
  if ( CertHashAlgorithm < 0 )
  {
    LODWORD(pInfo) = CertHashAlgorithm;
    LODWORD(v3) = 0;
    WUTrace("DetermineSubCAIdentity", 1679, 32, 1, pInfo, L"Method failed");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008aa28  mov     rax, rsp
0x18008aa2b  mov     [rax+10h], rbx
0x18008aa2f  mov     [rax+18h], rsi
0x18008aa33  mov     [rax+20h], rdi
0x18008aa37  push    rbp
0x18008aa38  push    r12
0x18008aa3a  push    r13
0x18008aa3c  push    r14
0x18008aa3e  push    r15
0x18008aa40  lea     rbp, [rax-5Fh]
0x18008aa44  sub     rsp, 0C0h
0x18008aa4b  mov     rax, cs:__security_cookie
0x18008aa52  xor     rax, rsp
0x18008aa55  mov     [rbp+57h+var_28], rax
0x18008aa59  xor     r13d, r13d
0x18008aa5c  mov     [rbp+57h+var_60], r8
0x18008aa60  mov     dword ptr [rbp+57h+lpString2], edx
0x18008aa63  xorps   xmm0, xmm0
0x18008aa66  mov     [rbp+57h+var_4C], 20h ; ' '
0x18008aa6d  mov     r12d, r13d
0x18008aa70  mov     [rbp+57h+lpMem], r13
0x18008aa74  mov     esi, r13d
0x18008aa77  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x18008aa7b  movups  [rbp+57h+var_38], xmm0
0x18008aa7f  test    rcx, rcx
0x18008aa82  jnz     short loc_18008AA8E
0x18008aa84  mov     esi, 80004003h
0x18008aa89  jmp     loc_18008B093
0x18008aa8e  mov     rax, [rcx+10h]
0x18008aa92  mov     r9d, 1; dwCertEncodingType
0x18008aa98  mov     rcx, [rax]
0x18008aa9b  mov     [rbp+57h+var_78], rcx
0x18008aa9f  mov     eax, [rcx+0Ch]
0x18008aaa2  cmp     eax, 3
0x18008aaa5  jz      short loc_18008AAD4
0x18008aaa7  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x18008aaab  lea     r8d, [r9+1Fh]
0x18008aaaf  lea     rax, aCertChainLengt; "Cert chain length check failed, length="...
0x18008aab6  xor     edx, edx
0x18008aab8  mov     [rsp+0E0h+pbComputedHash], rax
0x18008aabd  xor     ecx, ecx
0x18008aabf  mov     [rsp+0E0h+pInfo], r13
0x18008aac4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008aac9  mov     r12d, 1
0x18008aacf  jmp     loc_18008B093
0x18008aad4  mov     rax, [rcx+10h]
0x18008aad8  xor     r8d, r8d; dwFlags
0x18008aadb  lea     rcx, [rbp+57h+var_4C]
0x18008aadf  mov     edx, 800Ch; Algid
0x18008aae4  mov     [rsp+0E0h+pcbComputedHash], rcx; pcbComputedHash
0x18008aae9  lea     rcx, [rbp+57h+Buf2]
0x18008aaed  mov     [rsp+0E0h+pbComputedHash], rcx; pbComputedHash
0x18008aaf2  xor     ecx, ecx; hCryptProv
0x18008aaf4  mov     rax, [rax+8]
0x18008aaf8  mov     [rbp+57h+var_58], rax
0x18008aafc  mov     rax, [rax+8]
0x18008ab00  mov     [rbp+57h+pCertContext], rax
0x18008ab04  mov     rax, [rax+18h]
0x18008ab08  add     rax, 60h ; '`'
0x18008ab0c  mov     [rsp+0E0h+pInfo], rax; int
0x18008ab11  call    cs:__imp_CryptHashPublicKeyInfo
0x18008ab17  test    eax, eax
0x18008ab19  jnz     short loc_18008AB55
0x18008ab1b  call    cs:__imp_GetLastError
0x18008ab21  mov     ecx, eax
0x18008ab23  mov     ebx, 80070000h
0x18008ab28  movzx   eax, ax
0x18008ab2b  or      eax, ebx
0x18008ab2d  test    ecx, ecx
0x18008ab2f  cmovle  eax, ecx
0x18008ab32  test    eax, eax
0x18008ab34  jns     short loc_18008AB4B
0x18008ab36  call    cs:__imp_GetLastError
0x18008ab3c  movzx   esi, ax
0x18008ab3f  or      esi, ebx
0x18008ab41  test    eax, eax
0x18008ab43  cmovle  esi, eax
0x18008ab46  jmp     loc_18008B093
0x18008ab4b  mov     esi, 80004005h
0x18008ab50  jmp     loc_18008B093
0x18008ab55  cmp     [rbp+57h+var_4C], 20h ; ' '
0x18008ab59  mov     esi, 8024B303h
0x18008ab5e  jnz     loc_18008B093
0x18008ab64  mov     [rbp+57h+var_9C], 1
0x18008ab6b  mov     [rbp+57h+pcbUsage], r13d
0x18008ab6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x18008ab76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x18008ab7b  mov     r15d, [rbp+57h+var_4C]
0x18008ab7f  mov     rdi, r13
0x18008ab82  mov     r14d, 2
0x18008ab88  test    al, al
0x18008ab8a  jz      loc_18008ACB5
0x18008ab90  mov     [rbp+57h+var_A0], r13b
0x18008ab94  lea     rdx, qword_1800D98B0
0x18008ab9b  mov     r13d, r14d
0x18008ab9e  mov     dword ptr [rbp+57h+Block], r15d
0x18008aba2  mov     r8d, r15d; Size
0x18008aba5  mov     [rbp+57h+Size], r15
0x18008aba9  xor     ebx, ebx
0x18008abab  mov     eax, ebx
0x18008abad  mov     [rbp+57h+var_88], rax
0x18008abb1  add     rax, r12
0x18008abb4  lea     rcx, [rax+rax*2]
0x18008abb8  shl     rcx, 4
0x18008abbc  add     rcx, rdx; Buf1
0x18008abbf  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18008abc3  call    memcmp
0x18008abc8  test    eax, eax
0x18008abca  jz      short loc_18008ABE2
0x18008abcc  inc     ebx
0x18008abce  lea     rdx, qword_1800D98B0
0x18008abd5  mov     r8, r15
0x18008abd8  cmp     ebx, 5
0x18008abdb  jb      short loc_18008ABAB
0x18008abdd  mov     al, [rbp+57h+var_A0]
0x18008abe0  jmp     short loc_18008AC10
0x18008abe2  mov     rax, [rbp+57h+var_88]
0x18008abe6  lea     rdx, __ImageBase
0x18008abed  add     rax, rdi
0x18008abf0  lea     rcx, [rax+rax*2]
0x18008abf4  add     rcx, rcx
0x18008abf7  mov     eax, ds:rva dword_1800D98A0[rdx+rcx*8]
0x18008abfe  mov     ecx, ds:rva dword_1800D98A4[rdx+rcx*8]
0x18008ac05  mov     [rbp+57h+var_9C], eax
0x18008ac08  mov     al, 1
0x18008ac0a  mov     [rbp+57h+var_A0], al
0x18008ac0d  mov     [rbp+57h+pcbUsage], ecx
0x18008ac10  add     r12, 5
0x18008ac14  lea     rdx, qword_1800D98B0
0x18008ac1b  add     rdi, 5
0x18008ac1f  mov     r8, r15
0x18008ac22  sub     r13, 1
0x18008ac26  jnz     short loc_18008ABA9
0x18008ac28  xor     r13d, r13d
0x18008ac2b  test    al, al
0x18008ac2d  jnz     loc_18008AD3F
0x18008ac33  mov     edi, r13d
0x18008ac36  lea     r15, __ImageBase
0x18008ac3d  mov     r12d, r13d
0x18008ac40  mov     r13, r14
0x18008ac43  xor     ebx, ebx
0x18008ac45  mov     r8, [rbp+57h+Size]; Size
0x18008ac49  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18008ac4d  mov     eax, ebx
0x18008ac4f  mov     [rbp+57h+var_88], rax
0x18008ac53  add     rax, r12
0x18008ac56  lea     rcx, [rax+rax*2]
0x18008ac5a  shl     rcx, 4
0x18008ac5e  lea     rax, qword_1800D9540
0x18008ac65  add     rcx, rax; Buf1
0x18008ac68  call    memcmp
0x18008ac6d  test    eax, eax
0x18008ac6f  jz      short loc_18008AC7A
0x18008ac71  inc     ebx
0x18008ac73  cmp     ebx, 9
0x18008ac76  jb      short loc_18008AC45
0x18008ac78  jmp     short loc_18008AC9E
0x18008ac7a  mov     rax, [rbp+57h+var_88]
0x18008ac7e  add     rax, rdi
0x18008ac81  lea     rcx, [rax+rax*2]
0x18008ac85  add     rcx, rcx
0x18008ac88  mov     eax, ds:rva dword_1800D9530[r15+rcx*8]
0x18008ac90  mov     ecx, ds:rva dword_1800D9534[r15+rcx*8]
0x18008ac98  mov     [rbp+57h+pcbUsage], ecx
0x18008ac9b  mov     [rbp+57h+var_9C], eax
0x18008ac9e  add     r12, 9
0x18008aca2  add     rdi, 9
0x18008aca6  sub     r13, 1
0x18008acaa  jnz     short loc_18008AC43
0x18008acac  mov     r15d, dword ptr [rbp+57h+Block]
0x18008acb0  jmp     loc_18008AD3C
0x18008acb5  mov     rdx, r15
0x18008acb8  lea     r8, qword_1800D98B0
0x18008acbf  mov     r13, r14
0x18008acc2  xor     ebx, ebx
0x18008acc4  mov     eax, ebx
0x18008acc6  mov     [rbp+57h+Size], rax
0x18008acca  add     rax, r12
0x18008accd  lea     rcx, [rax+rax*2]
0x18008acd1  shl     rcx, 4
0x18008acd5  add     rcx, r8; Buf1
0x18008acd8  mov     r8, rdx; Size
0x18008acdb  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18008acdf  call    memcmp
0x18008ace4  test    eax, eax
0x18008ace6  jz      short loc_18008ACFB
0x18008ace8  inc     ebx
0x18008acea  lea     r8, qword_1800D98B0
0x18008acf1  mov     rdx, r15
0x18008acf4  cmp     ebx, 5
0x18008acf7  jb      short loc_18008ACC4
0x18008acf9  jmp     short loc_18008AD24
0x18008acfb  mov     rax, [rbp+57h+Size]
0x18008acff  lea     rdx, __ImageBase
0x18008ad06  add     rax, rdi
0x18008ad09  lea     rcx, [rax+rax*2]
0x18008ad0d  add     rcx, rcx
0x18008ad10  mov     eax, ds:rva dword_1800D98A0[rdx+rcx*8]
0x18008ad17  mov     ecx, ds:rva dword_1800D98A4[rdx+rcx*8]
0x18008ad1e  mov     [rbp+57h+pcbUsage], ecx
0x18008ad21  mov     [rbp+57h+var_9C], eax
0x18008ad24  add     r12, 5
0x18008ad28  lea     r8, qword_1800D98B0
0x18008ad2f  add     rdi, 5
0x18008ad33  mov     rdx, r15
0x18008ad36  sub     r13, 1
0x18008ad3a  jnz     short loc_18008ACC2
0x18008ad3c  xor     r13d, r13d
0x18008ad3f  mov     r12d, [rbp+57h+var_9C]
0x18008ad43  cmp     r12d, 1
0x18008ad47  jnz     loc_18008AEFD
0x18008ad4d  cmp     dword ptr [rbp+57h+lpString2], r13d
0x18008ad51  jbe     short loc_18008AD90
0x18008ad53  mov     r13, [rbp+57h+var_60]
0x18008ad57  test    r13, r13
0x18008ad5a  jz      short loc_18008AD8D
0x18008ad5c  xor     ebx, ebx
0x18008ad5e  mov     r12d, r15d
0x18008ad61  lea     rdi, [rbx+rbx*2]
0x18008ad65  cmp     dword ptr [r13+rdi*8+8], 20h ; ' '
0x18008ad6b  jnz     short loc_18008AD82
0x18008ad6d  mov     rcx, [r13+rdi*8+10h]; Buf1
0x18008ad72  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18008ad76  mov     r8, r12; Size
0x18008ad79  call    memcmp
0x18008ad7e  test    eax, eax
0x18008ad80  jz      short loc_18008ADE3
0x18008ad82  inc     ebx
0x18008ad84  cmp     ebx, dword ptr [rbp+57h+lpString2]
0x18008ad87  jb      short loc_18008AD61
0x18008ad89  mov     r12d, [rbp+57h+var_9C]
0x18008ad8d  xor     r13d, r13d
0x18008ad90  lea     ecx, ds:1[r15*2]; unsigned __int64
0x18008ad98  mov     rdx, r14; unsigned __int64
0x18008ad9b  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18008ada0  mov     rbx, rax
0x18008ada3  neg     rax
0x18008ada6  sbb     edi, edi
0x18008ada8  not     edi
0x18008adaa  and     edi, 8007000Eh
0x18008adb0  test    rbx, rbx
0x18008adb3  jnz     loc_18008AE74
0x18008adb9  mov     rcx, [rbp+5Fh]; this
0x18008adbd  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18008adc4  mov     r9d, edi; char *
0x18008adc7  mov     edx, 0E8h; void *
0x18008adcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008add1  lea     rax, aHashOfPublicKe; "Hash of public key doesn't match the kn"...
0x18008add8  mov     [rsp+0E0h+pbComputedHash], rax
0x18008addd  mov     dword ptr [rsp+0E0h+pInfo], edi
0x18008ade1  jmp     short loc_18008AE5E
0x18008ade3  mov     r12d, [r13+rdi*8+0]
0x18008ade8  mov     eax, [r13+rdi*8+4]
0x18008aded  cmp     r12d, 1
0x18008adf1  jz      short loc_18008AD8D
0x18008adf3  xor     r13d, r13d
0x18008adf6  or      r15d, 0FFFFFFFFh
0x18008adfa  test    eax, eax
0x18008adfc  jz      loc_18008AFD3
0x18008ae02  mov     rdi, [rbp+57h+var_58]
0x18008ae06  mov     ebx, r13d
0x18008ae09  mov     rdi, [rdi+28h]
0x18008ae0d  cmp     [rdi], r13d
0x18008ae10  jbe     short loc_18008AE4D
0x18008ae12  mov     rax, [rdi+8]
0x18008ae16  lea     r8, String1; "1.3.6.1.4.1.311.76.6.1"
0x18008ae1d  mov     ecx, ebx
0x18008ae1f  mov     edx, 1; dwCmpFlags
0x18008ae24  mov     dword ptr [rsp+0E0h+pbComputedHash], r15d; cchCount2
0x18008ae29  mov     r9d, r15d; cchCount1
0x18008ae2c  mov     rax, [rax+rcx*8]
0x18008ae30  lea     ecx, [rdx+7Eh]; Locale
0x18008ae33  mov     [rsp+0E0h+pInfo], rax; lpString2
0x18008ae38  call    cs:__imp_CompareStringA
0x18008ae3e  cmp     eax, r14d
0x18008ae41  jz      loc_18008AF05
0x18008ae47  inc     ebx
0x18008ae49  cmp     ebx, [rdi]
0x18008ae4b  jb      short loc_18008AE12
0x18008ae4d  lea     rax, aEkuNotFoundFor_0; "EKU not found for SubCA"
0x18008ae54  mov     [rsp+0E0h+pbComputedHash], rax
0x18008ae59  mov     [rsp+0E0h+pInfo], r13
0x18008ae5e  xor     edx, edx
0x18008ae60  xor     ecx, ecx
0x18008ae62  lea     r9d, [rdx+1]
0x18008ae66  lea     r8d, [rdx+20h]
0x18008ae6a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18008ae6f  jmp     loc_18008B093
0x18008ae74  lea     rdx, [rbp+57h+Buf2]
0x18008ae78  mov     rcx, rbx
0x18008ae7b  test    r15d, r15d
0x18008ae7e  jz      short loc_18008AEBE
0x18008ae80  mov     r8d, r15d
0x18008ae83  lea     r9, __ImageBase
0x18008ae8a  movzx   eax, byte ptr [rdx]
0x18008ae8d  shr     rax, 4
0x18008ae91  movzx   eax, ds:rva word_1800C72E0[r9+rax*2]
0x18008ae9a  mov     [rcx], ax
0x18008ae9d  add     rcx, r14
0x18008aea0  movzx   eax, byte ptr [rdx]
  ... truncated ...
```
