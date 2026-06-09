# DetermineSubCAIdentity

- ea: `0x180011b18`
- end: `0x180012200`
- name: `DetermineSubCAIdentity`
- size: `1768`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180012e10`

## callees

- `0x180005f64`
- `0x18000956c`
- `0x18000a60c`
- `0x18000e594`
- `0x180011b18`
- `0x18001324c`
- `0x180013358`
- `0x180013eac`
- `0x180013f28`
- `0x180042630`
- `0x180042a24`
- `0x180049d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c29`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800121af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800121af`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180011c04`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180011c04`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180011f95`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180011fce`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180011f95`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180011fce`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180011f3c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18001200a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180011f3c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18001200a`

## pseudocode

```c
__int64 __fastcall DetermineSubCAIdentity(__int64 a1, int a2, void *a3)
{
  __int64 v3; // r14
  _DWORD *v4; // r12
  unsigned int v5; // r15d
  signed int CertHashAlgorithm; // esi
  __int64 v7; // rcx
  signed int LastError; // ecx
  signed int v9; // eax
  signed int v10; // eax
  __int64 v11; // rdi
  size_t v12; // r8
  __int64 v13; // r13
  unsigned int v14; // ebx
  char v15; // al
  __int64 v16; // r14
  __int64 v17; // rdi
  __int64 v18; // r12
  __int64 v19; // rbx
  size_t v20; // rdx
  __int64 v21; // r12
  __int64 v22; // rbx
  int v23; // ebx
  size_t v24; // r14
  DWORD v25; // eax
  void *v26; // rbx
  unsigned int v27; // ebx
  __int64 v28; // rdi
  __int64 v29; // rdi
  __int64 *v30; // rax
  __int64 v31; // rbx
  struct _CTL_USAGE *v32; // rax
  struct _CTL_USAGE *v33; // rsi
  int v34; // ebx
  const struct std::nothrow_t *v35; // rdx
  WCHAR *v36; // rcx
  WCHAR *v37; // rbx
  WCHAR *v38; // rcx
  WCHAR *v39; // rdi
  char v41; // [rsp+48h] [rbp-49h]
  PCNZWCH lpString1; // [rsp+50h] [rbp-41h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp-39h] BYREF
  void *lpMem; // [rsp+60h] [rbp-31h] BYREF
  __int64 v45; // [rsp+68h] [rbp-29h]
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp-21h]
  void *v47; // [rsp+78h] [rbp-19h]
  __int64 v48; // [rsp+80h] [rbp-11h]
  __int64 v49; // [rsp+88h] [rbp-9h]
  DWORD pcbUsage; // [rsp+90h] [rbp-1h] BYREF
  DWORD pcbComputedHash; // [rsp+94h] [rbp+3h] BYREF
  BYTE Buf2[16]; // [rsp+98h] [rbp+7h] BYREF
  __int128 v53; // [rsp+A8h] [rbp+17h]

  v3 = 0;
  lpMem = a3;
  LODWORD(lpString1) = a2;
  pcbComputedHash = 32;
  v4 = a3;
  v47 = 0;
  v5 = 0;
  CertHashAlgorithm = 0;
  *(_OWORD *)Buf2 = 0;
  v53 = 0;
  if ( !a1 )
  {
    CertHashAlgorithm = -2147467261;
    goto LABEL_81;
  }
  v7 = **(_QWORD **)(a1 + 16);
  v45 = v7;
  if ( *(_DWORD *)(v7 + 12) != 3 )
  {
    WUTrace(0, 0, 32, 1);
    v5 = 1;
    goto LABEL_81;
  }
  v49 = *(_QWORD *)(*(_QWORD *)(v7 + 16) + 8LL);
  pCertContext = *(PCCERT_CONTEXT *)(v49 + 8);
  if ( !CryptHashPublicKeyInfo(
          0,
          0x800Cu,
          0,
          1u,
          &pCertContext->pCertInfo->SubjectPublicKeyInfo,
          Buf2,
          &pcbComputedHash) )
  {
LABEL_6:
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( v9 >= 0 )
    {
      CertHashAlgorithm = -2147467259;
    }
    else
    {
      v10 = GetLastError();
      CertHashAlgorithm = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        CertHashAlgorithm = v10;
    }
    goto LABEL_81;
  }
  CertHashAlgorithm = -2145078525;
  LODWORD(lpString2) = -2145078525;
  if ( pcbComputedHash != 32 )
    goto LABEL_81;
  v5 = 1;
  pcbUsage = 0;
  v11 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
  {
    v20 = pcbComputedHash;
    v21 = 2;
    do
    {
      v22 = 0;
      while ( memcmp(&qword_180062850[6 * v3 + 6 * v22], Buf2, v20) )
      {
        v20 = pcbComputedHash;
        v22 = (unsigned int)(v22 + 1);
        if ( (unsigned int)v22 >= 5 )
          goto LABEL_37;
      }
      v5 = dword_180062840[12 * v11 + 12 * v22];
      pcbUsage = dword_180062844[12 * v11 + 12 * v22];
LABEL_37:
      v20 = pcbComputedHash;
      v3 += 5;
      v11 += 5;
      --v21;
    }
    while ( v21 );
    goto LABEL_38;
  }
  v12 = pcbComputedHash;
  v13 = 2;
  v41 = 0;
  do
  {
    v14 = 0;
    while ( 1 )
    {
      v48 = v14;
      if ( !memcmp(&qword_180062850[6 * v3 + 6 * v14], Buf2, v12) )
        break;
      v12 = pcbComputedHash;
      if ( ++v14 >= 5 )
      {
        v15 = v41;
        goto LABEL_21;
      }
    }
    v15 = 1;
    v41 = 1;
    v5 = dword_180062840[12 * v11 + 12 * v48];
    pcbUsage = dword_180062844[12 * v11 + 12 * v48];
LABEL_21:
    v12 = pcbComputedHash;
    v3 += 5;
    v11 += 5;
    --v13;
  }
  while ( v13 );
  v16 = 0;
  if ( !v15 )
  {
    v17 = 0;
    v18 = 2;
    do
    {
      v19 = 0;
      while ( memcmp(&qword_1800624E0[6 * v16 + 6 * v19], Buf2, pcbComputedHash) )
      {
        v19 = (unsigned int)(v19 + 1);
        if ( (unsigned int)v19 >= 9 )
          goto LABEL_29;
      }
      v5 = dword_1800624D0[12 * v17 + 12 * v19];
      pcbUsage = dword_1800624D4[12 * v17 + 12 * v19];
LABEL_29:
      v16 += 9;
      v17 += 9;
      --v18;
    }
    while ( v18 );
    CertHashAlgorithm = (int)lpString2;
LABEL_38:
    v4 = lpMem;
  }
  if ( v5 == 1 )
  {
    if ( !(_DWORD)lpString1 || !v4 )
      goto LABEL_48;
    v23 = 0;
    v24 = pcbComputedHash;
    while ( v4[6 * v23 + 2] != 32 || memcmp(*(const void **)&v4[6 * v23 + 4], Buf2, v24) )
    {
      if ( ++v23 >= (unsigned int)lpString1 )
        goto LABEL_48;
    }
    v5 = v4[6 * v23];
    v25 = v4[6 * v23 + 1];
    if ( v5 == 1 )
    {
LABEL_48:
      lpMem = 0;
      HexStringFromBlobAllocW(Buf2, pcbComputedHash, (wchar_t **)&lpMem);
      v26 = lpMem;
      WUTrace(0, 0, 32, 1);
      if ( v26 )
        CSusBaseAllocTag<942762101>::operator delete(v26);
      goto LABEL_81;
    }
  }
  else
  {
    v25 = pcbUsage;
  }
  if ( v25 )
  {
    v27 = 0;
    v28 = *(_QWORD *)(v49 + 40);
    if ( !*(_DWORD *)v28 )
      goto LABEL_55;
    while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, *(PCNZCH *)(*(_QWORD *)(v28 + 8) + 8LL * v27), -1) != 2 )
    {
      if ( ++v27 >= *(_DWORD *)v28 )
        goto LABEL_55;
    }
    v29 = v45;
    pcbUsage = 0;
    v30 = *(__int64 **)(v45 + 16);
    v31 = *v30;
    if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(*v30 + 8), 0, 0, &pcbUsage) )
      goto LABEL_6;
    v32 = (struct _CTL_USAGE *)SusAlloc(pcbUsage);
    v47 = v32;
    v33 = v32;
    if ( !v32 )
    {
      CertHashAlgorithm = -2147024882;
      goto LABEL_81;
    }
    if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(v31 + 8), 0, v32, &pcbUsage) )
      goto LABEL_6;
    v34 = 0;
    if ( !v33->cUsageIdentifier )
    {
LABEL_55:
      WUTrace(0, 0, 32, 1);
      CertHashAlgorithm = -2145078525;
      goto LABEL_81;
    }
    while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, v33->rgpszUsageIdentifier[v34], -1) != 2 )
    {
      if ( ++v34 >= v33->cUsageIdentifier )
        goto LABEL_55;
    }
  }
  else
  {
    v29 = v45;
  }
  lpString1 = 0;
  lpString2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::GetImpl'::`2'::impl) )
  {
    CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&lpString1);
    if ( CertHashAlgorithm >= 0 )
    {
      CertHashAlgorithm = GetCertHashAlgorithm(
                            *(PCCERT_CONTEXT *)(**(_QWORD **)(v29 + 16) + 8LL),
                            (wchar_t **)&lpString2);
      if ( CertHashAlgorithm >= 0 )
      {
        v37 = (WCHAR *)lpString1;
        v39 = (WCHAR *)lpString2;
        if ( CompareStringW(0x7Fu, 0, lpString1, -1, lpString2, -1) == 2 )
          goto LABEL_76;
        WUTrace(0, 0, 32, 1);
        CertHashAlgorithm = -2145078525;
LABEL_90:
        if ( !v39 )
          goto LABEL_70;
        v38 = v39;
        goto LABEL_74;
      }
      if ( lpString2 )
        operator delete((void *)lpString2, v35);
    }
LABEL_67:
    v36 = (WCHAR *)lpString1;
    if ( !lpString1 )
      goto LABEL_81;
    goto LABEL_68;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&lpString1);
  if ( CertHashAlgorithm < 0 )
    goto LABEL_67;
  v37 = (WCHAR *)lpString1;
  CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString1);
  if ( CertHashAlgorithm < 0 )
  {
LABEL_70:
    if ( !v37 )
      goto LABEL_81;
    v36 = v37;
LABEL_68:
    operator delete(v36, v35);
    goto LABEL_81;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(*(PCCERT_CONTEXT *)(**(_QWORD **)(v29 + 16) + 8LL), (wchar_t **)&lpString2);
  if ( CertHashAlgorithm < 0 )
  {
    v38 = (WCHAR *)lpString2;
    if ( !lpString2 )
      goto LABEL_70;
LABEL_74:
    operator delete(v38, v35);
    goto LABEL_70;
  }
  v39 = (WCHAR *)lpString2;
  CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString2);
  if ( CertHashAlgorithm < 0 )
    goto LABEL_90;
LABEL_76:
  if ( v39 )
    operator delete(v39, v35);
  if ( v37 )
    operator delete(v37, v35);
  CertHashAlgorithm = 0;
LABEL_81:
  CSusBaseAllocTag<942762101>::operator delete(v47);
  if ( CertHashAlgorithm < 0 )
  {
    v5 = 0;
    WUTrace("DetermineSubCAIdentity", 1679, 32, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180011b18  mov     rax, rsp
0x180011b1b  mov     [rax+10h], rbx
0x180011b1f  mov     [rax+18h], rsi
0x180011b23  mov     [rax+20h], rdi
0x180011b27  push    rbp
0x180011b28  push    r12
0x180011b2a  push    r13
0x180011b2c  push    r14
0x180011b2e  push    r15
0x180011b30  lea     rbp, [rax-5Fh]
0x180011b34  sub     rsp, 0C0h
0x180011b3b  mov     rax, cs:__security_cookie
0x180011b42  xor     rax, rsp
0x180011b45  mov     [rbp+57h+var_30], rax
0x180011b49  xor     r14d, r14d
0x180011b4c  mov     [rbp+57h+lpMem], r8
0x180011b50  mov     dword ptr [rbp+57h+lpString1], edx
0x180011b53  xorps   xmm0, xmm0
0x180011b56  mov     [rbp+57h+var_54], 20h ; ' '
0x180011b5d  mov     r12, r8
0x180011b60  mov     [rbp+57h+var_70], r14
0x180011b64  mov     r15d, r14d
0x180011b67  mov     esi, r14d
0x180011b6a  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x180011b6e  movups  [rbp+57h+var_40], xmm0
0x180011b72  test    rcx, rcx
0x180011b75  jnz     short loc_180011B81
0x180011b77  mov     esi, 80004003h
0x180011b7c  jmp     loc_1800120E7
0x180011b81  mov     rax, [rcx+10h]
0x180011b85  mov     r9d, 1; dwCertEncodingType
0x180011b8b  mov     rcx, [rax]
0x180011b8e  mov     [rbp+57h+var_80], rcx
0x180011b92  mov     eax, [rcx+0Ch]
0x180011b95  cmp     eax, 3
0x180011b98  jz      short loc_180011BC7
0x180011b9a  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x180011b9e  lea     r8d, [r9+1Fh]
0x180011ba2  lea     rax, aCertChainLengt; "Cert chain length check failed, length="...
0x180011ba9  xor     edx, edx
0x180011bab  mov     [rsp+0E0h+pbComputedHash], rax
0x180011bb0  xor     ecx, ecx
0x180011bb2  mov     [rsp+0E0h+pInfo], r14
0x180011bb7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011bbc  mov     r15d, 1
0x180011bc2  jmp     loc_1800120E7
0x180011bc7  mov     rax, [rcx+10h]
0x180011bcb  xor     r8d, r8d; dwFlags
0x180011bce  lea     rcx, [rbp+57h+var_54]
0x180011bd2  mov     edx, 800Ch; Algid
0x180011bd7  mov     [rsp+0E0h+pcbComputedHash], rcx; pcbComputedHash
0x180011bdc  lea     rcx, [rbp+57h+Buf2]
0x180011be0  mov     [rsp+0E0h+pbComputedHash], rcx; pbComputedHash
0x180011be5  xor     ecx, ecx; hCryptProv
0x180011be7  mov     rax, [rax+8]
0x180011beb  mov     [rbp+57h+var_60], rax
0x180011bef  mov     rax, [rax+8]
0x180011bf3  mov     [rbp+57h+pCertContext], rax
0x180011bf7  mov     rax, [rax+18h]
0x180011bfb  add     rax, 60h ; '`'
0x180011bff  mov     [rsp+0E0h+pInfo], rax; pInfo
0x180011c04  call    cs:__imp_CryptHashPublicKeyInfo
0x180011c0a  test    eax, eax
0x180011c0c  jnz     short loc_180011C48
0x180011c0e  call    cs:__imp_GetLastError
0x180011c14  mov     ecx, eax
0x180011c16  mov     ebx, 80070000h
0x180011c1b  movzx   eax, ax
0x180011c1e  or      eax, ebx
0x180011c20  test    ecx, ecx
0x180011c22  cmovle  eax, ecx
0x180011c25  test    eax, eax
0x180011c27  jns     short loc_180011C3E
0x180011c29  call    cs:__imp_GetLastError
0x180011c2f  movzx   esi, ax
0x180011c32  or      esi, ebx
0x180011c34  test    eax, eax
0x180011c36  cmovle  esi, eax
0x180011c39  jmp     loc_1800120E7
0x180011c3e  mov     esi, 80004005h
0x180011c43  jmp     loc_1800120E7
0x180011c48  cmp     [rbp+57h+var_54], 20h ; ' '
0x180011c4c  mov     esi, 8024B303h
0x180011c51  mov     dword ptr [rbp+57h+lpString2], esi
0x180011c54  jnz     loc_1800120E7
0x180011c5a  mov     r15d, 1
0x180011c60  mov     [rbp+57h+pcbUsage], r14d
0x180011c64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x180011c6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x180011c70  mov     rdi, r14
0x180011c73  test    al, al
0x180011c75  jz      loc_180011D8B
0x180011c7b  mov     r8d, [rbp+57h+var_54]; Size
0x180011c7f  lea     r13d, [r15+1]
0x180011c83  mov     [rbp+57h+var_A0], r14b
0x180011c87  lea     rdx, qword_180062850
0x180011c8e  xor     ebx, ebx
0x180011c90  mov     eax, ebx
0x180011c92  mov     [rbp+57h+var_68], rax
0x180011c96  add     rax, r14
0x180011c99  lea     rcx, [rax+rax*2]
0x180011c9d  shl     rcx, 4
0x180011ca1  add     rcx, rdx; Buf1
0x180011ca4  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180011ca8  call    memcmp
0x180011cad  test    eax, eax
0x180011caf  jz      short loc_180011CC8
0x180011cb1  mov     r8d, [rbp+57h+var_54]
0x180011cb5  lea     rdx, qword_180062850
0x180011cbc  inc     ebx
0x180011cbe  cmp     ebx, 5
0x180011cc1  jb      short loc_180011C90
0x180011cc3  mov     al, [rbp+57h+var_A0]
0x180011cc6  jmp     short loc_180011CF4
0x180011cc8  mov     rax, [rbp+57h+var_68]
0x180011ccc  lea     rdx, __ImageBase
0x180011cd3  add     rax, rdi
0x180011cd6  lea     rcx, [rax+rax*2]
0x180011cda  mov     al, 1
0x180011cdc  add     rcx, rcx
0x180011cdf  mov     [rbp+57h+var_A0], al
0x180011ce2  mov     r15d, ds:rva dword_180062840[rdx+rcx*8]
0x180011cea  mov     ecx, ds:rva dword_180062844[rdx+rcx*8]
0x180011cf1  mov     [rbp+57h+pcbUsage], ecx
0x180011cf4  mov     r8d, [rbp+57h+var_54]
0x180011cf8  lea     rdx, qword_180062850
0x180011cff  add     r14, 5
0x180011d03  add     rdi, 5
0x180011d07  sub     r13, 1
0x180011d0b  jnz     short loc_180011C8E
0x180011d0d  xor     r14d, r14d
0x180011d10  test    al, al
0x180011d12  jnz     loc_180011E12
0x180011d18  mov     edi, r14d
0x180011d1b  lea     r12d, [r14+2]
0x180011d1f  lea     rsi, __ImageBase
0x180011d26  xor     ebx, ebx
0x180011d28  mov     r8d, [rbp+57h+var_54]; Size
0x180011d2c  lea     rax, [r14+rbx]
0x180011d30  lea     rcx, [rax+rax*2]
0x180011d34  shl     rcx, 4
0x180011d38  lea     rax, qword_1800624E0
0x180011d3f  add     rcx, rax; Buf1
0x180011d42  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180011d46  call    memcmp
0x180011d4b  test    eax, eax
0x180011d4d  jz      short loc_180011D58
0x180011d4f  inc     ebx
0x180011d51  cmp     ebx, 9
0x180011d54  jb      short loc_180011D28
0x180011d56  jmp     short loc_180011D75
0x180011d58  lea     rax, [rdi+rbx]
0x180011d5c  lea     rcx, [rax+rax*2]
0x180011d60  add     rcx, rcx
0x180011d63  mov     eax, ds:rva dword_1800624D4[rsi+rcx*8]
0x180011d6a  mov     r15d, ds:rva dword_1800624D0[rsi+rcx*8]
0x180011d72  mov     [rbp+57h+pcbUsage], eax
0x180011d75  add     r14, 9
0x180011d79  add     rdi, 9
0x180011d7d  sub     r12, 1
0x180011d81  jnz     short loc_180011D26
0x180011d83  mov     esi, dword ptr [rbp+57h+lpString2]
0x180011d86  jmp     loc_180011E0B
0x180011d8b  mov     edx, [rbp+57h+var_54]
0x180011d8e  lea     r8, qword_180062850
0x180011d95  mov     r12d, 2
0x180011d9b  xor     ebx, ebx
0x180011d9d  lea     rax, [r14+rbx]
0x180011da1  lea     rcx, [rax+rax*2]
0x180011da5  shl     rcx, 4
0x180011da9  add     rcx, r8; Buf1
0x180011dac  mov     r8, rdx; Size
0x180011daf  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180011db3  call    memcmp
0x180011db8  test    eax, eax
0x180011dba  jz      short loc_180011DCF
0x180011dbc  mov     edx, [rbp+57h+var_54]
0x180011dbf  lea     r8, qword_180062850
0x180011dc6  inc     ebx
0x180011dc8  cmp     ebx, 5
0x180011dcb  jb      short loc_180011D9D
0x180011dcd  jmp     short loc_180011DF3
0x180011dcf  lea     rax, [rdi+rbx]
0x180011dd3  lea     rcx, [rax+rax*2]
0x180011dd7  add     rcx, rcx
0x180011dda  lea     rdx, __ImageBase
0x180011de1  mov     eax, ds:rva dword_180062844[rdx+rcx*8]
0x180011de8  mov     r15d, ds:rva dword_180062840[rdx+rcx*8]
0x180011df0  mov     [rbp+57h+pcbUsage], eax
0x180011df3  mov     edx, [rbp+57h+var_54]
0x180011df6  lea     r8, qword_180062850
0x180011dfd  add     r14, 5
0x180011e01  add     rdi, 5
0x180011e05  sub     r12, 1
0x180011e09  jnz     short loc_180011D9B
0x180011e0b  mov     r12, [rbp+57h+lpMem]
0x180011e0f  xor     r14d, r14d
0x180011e12  cmp     r15d, 1
0x180011e16  jnz     loc_180011EEC
0x180011e1c  mov     r13d, dword ptr [rbp+57h+lpString1]
0x180011e20  test    r13d, r13d
0x180011e23  jz      short loc_180011E73
0x180011e25  test    r12, r12
0x180011e28  jz      short loc_180011E73
0x180011e2a  mov     ebx, r14d
0x180011e2d  mov     r14d, [rbp+57h+var_54]
0x180011e31  mov     eax, ebx
0x180011e33  lea     rdi, [rax+rax*2]
0x180011e37  cmp     dword ptr [r12+rdi*8+8], 20h ; ' '
0x180011e3d  jnz     short loc_180011E54
0x180011e3f  mov     rcx, [r12+rdi*8+10h]; Buf1
0x180011e44  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180011e48  mov     r8, r14; Size
0x180011e4b  call    memcmp
0x180011e50  test    eax, eax
0x180011e52  jz      short loc_180011E5D
0x180011e54  inc     ebx
0x180011e56  cmp     ebx, r13d
0x180011e59  jb      short loc_180011E31
0x180011e5b  jmp     short loc_180011E70
0x180011e5d  mov     r15d, [r12+rdi*8]
0x180011e61  mov     eax, [r12+rdi*8+4]
0x180011e66  cmp     r15d, 1
0x180011e6a  jnz     loc_180011EF1
0x180011e70  xor     r14d, r14d
0x180011e73  mov     edx, [rbp+57h+var_54]; unsigned int
0x180011e76  lea     r8, [rbp+57h+lpMem]; wchar_t **
0x180011e7a  lea     rcx, [rbp+57h+Buf2]; unsigned __int8 *
0x180011e7e  mov     [rbp+57h+lpMem], r14
0x180011e82  call    ?HexStringFromBlobAllocW@@YAJPEBEKPEAPEA_W@Z; HexStringFromBlobAllocW(uchar const *,ulong,wchar_t * *)
0x180011e87  mov     rbx, [rbp+57h+lpMem]
0x180011e8b  xor     edx, edx
0x180011e8d  lea     r9d, [rdx+1]
0x180011e91  lea     r8d, [rdx+20h]
0x180011e95  test    eax, eax
0x180011e97  js      short loc_180011EBF
0x180011e99  mov     eax, [rbp+57h+var_54]
0x180011e9c  xor     ecx, ecx
0x180011e9e  mov     [rsp+0E0h+var_A8], rbx
0x180011ea3  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x180011ea7  lea     rax, aHashOfPublicKe_0; "Hash of public key doesn't match the kn"...
0x180011eae  mov     [rsp+0E0h+pbComputedHash], rax
0x180011eb3  mov     [rsp+0E0h+pInfo], r14
0x180011eb8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011ebd  jmp     short loc_180011ED6
0x180011ebf  lea     rcx, aHashOfPublicKe; "Hash of public key doesn't match the kn"...
0x180011ec6  mov     [rsp+0E0h+pbComputedHash], rcx
0x180011ecb  xor     ecx, ecx
0x180011ecd  mov     dword ptr [rsp+0E0h+pInfo], eax
0x180011ed1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011ed6  test    rbx, rbx
0x180011ed9  jz      loc_1800120E7
0x180011edf  mov     rcx, rbx; lpMem
0x180011ee2  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180011ee7  jmp     loc_1800120E7
0x180011eec  mov     eax, [rbp+57h+pcbUsage]
0x180011eef  jmp     short loc_180011EF4
0x180011ef1  xor     r14d, r14d
0x180011ef4  or      r12d, 0FFFFFFFFh
0x180011ef8  mov     r13d, 7Fh
0x180011efe  test    eax, eax
0x180011f00  jz      loc_180012027
0x180011f06  mov     rdi, [rbp+57h+var_60]
0x180011f0a  mov     ebx, r14d
0x180011f0d  mov     rdi, [rdi+28h]
0x180011f11  cmp     [rdi], r14d
0x180011f14  jbe     short loc_180011F4D
0x180011f16  mov     rax, [rdi+8]
0x180011f1a  lea     r8, String1; "1.3.6.1.4.1.311.76.6.1"
0x180011f21  mov     ecx, ebx
0x180011f23  mov     r9d, r12d; cchCount1
0x180011f26  mov     dword ptr [rsp+0E0h+pbComputedHash], r12d; cchCount2
0x180011f2b  mov     edx, 1; dwCmpFlags
0x180011f30  mov     rax, [rax+rcx*8]
0x180011f34  mov     ecx, r13d; Locale
0x180011f37  mov     [rsp+0E0h+pInfo], rax; lpString2
0x180011f3c  call    cs:__imp_CompareStringA
0x180011f42  cmp     eax, 2
0x180011f45  jz      short loc_180011F79
0x180011f47  inc     ebx
0x180011f49  cmp     ebx, [rdi]
0x180011f4b  jb      short loc_180011F16
0x180011f4d  lea     rax, aEkuNotFoundFor_0; "EKU not found for SubCA"
0x180011f54  xor     edx, edx
0x180011f56  mov     [rsp+0E0h+pbComputedHash], rax
0x180011f5b  xor     ecx, ecx
0x180011f5d  mov     [rsp+0E0h+pInfo], r14
0x180011f62  lea     r9d, [rdx+1]
0x180011f66  lea     r8d, [rdx+20h]
0x180011f6a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011f6f  mov     esi, 8024B303h
0x180011f74  jmp     loc_1800120E7
0x180011f79  mov     rdi, [rbp+57h+var_80]
0x180011f7d  lea     r9, [rbp+57h+pcbUsage]; pcbUsage
0x180011f81  mov     [rbp+57h+pcbUsage], r14d
0x180011f85  xor     r8d, r8d; pUsage
0x180011f88  xor     edx, edx; dwFlags
0x180011f8a  mov     rax, [rdi+10h]
0x180011f8e  mov     rbx, [rax]
0x180011f91  mov     rcx, [rbx+8]; pCertContext
  ... truncated ...
```
