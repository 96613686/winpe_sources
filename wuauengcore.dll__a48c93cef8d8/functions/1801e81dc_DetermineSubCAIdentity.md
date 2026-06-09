# DetermineSubCAIdentity

- ea: `0x1801e81dc`
- end: `0x1801e88c4`
- name: `DetermineSubCAIdentity`
- size: `1768`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801e99e0`
- `0x1801e9ffc`
- `0x1801ea38c`

## callees

- `0x180113a10`
- `0x180113ae8`
- `0x18011b2b0`
- `0x18012b618`
- `0x1801b339c`
- `0x1801e81dc`
- `0x1801ea930`
- `0x1801eaa3c`
- `0x1801eb57c`
- `0x180238960`
- `0x180238984`
- `0x180241780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e82d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e82ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e82d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e82ed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801e8873`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801e8873`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1801e8659`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1801e8692`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1801e8659`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1801e8692`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1801e82c8`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x1801e82c8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1801e8600`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1801e86ce`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1801e8600`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1801e86ce`

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
  int v26; // eax
  void *v27; // rbx
  unsigned int v28; // ebx
  __int64 v29; // rdi
  __int64 v30; // rdi
  __int64 *v31; // rax
  __int64 v32; // rbx
  struct _CTL_USAGE *v33; // rax
  struct _CTL_USAGE *v34; // rsi
  int v35; // ebx
  const struct std::nothrow_t *v36; // rdx
  WCHAR *v37; // rcx
  WCHAR *v38; // rbx
  WCHAR *v39; // rcx
  WCHAR *v40; // rdi
  DWORD *pcbComputedHash; // [rsp+38h] [rbp-59h]
  char v43; // [rsp+48h] [rbp-49h]
  PCNZWCH lpString1; // [rsp+50h] [rbp-41h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp-39h] BYREF
  void *lpMem; // [rsp+60h] [rbp-31h] BYREF
  __int64 v47; // [rsp+68h] [rbp-29h]
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp-21h]
  void *v49; // [rsp+78h] [rbp-19h]
  __int64 v50; // [rsp+80h] [rbp-11h]
  __int64 v51; // [rsp+88h] [rbp-9h]
  DWORD pcbUsage; // [rsp+90h] [rbp-1h] BYREF
  DWORD v53; // [rsp+94h] [rbp+3h] BYREF
  BYTE Buf2[16]; // [rsp+98h] [rbp+7h] BYREF
  __int128 v55; // [rsp+A8h] [rbp+17h]

  v3 = 0;
  lpMem = a3;
  LODWORD(lpString1) = a2;
  v53 = 32;
  v4 = a3;
  v49 = 0;
  v5 = 0;
  CertHashAlgorithm = 0;
  *(_OWORD *)Buf2 = 0;
  v55 = 0;
  if ( !a1 )
  {
    CertHashAlgorithm = -2147467261;
    goto LABEL_85;
  }
  v7 = **(_QWORD **)(a1 + 16);
  v47 = v7;
  if ( *(_DWORD *)(v7 + 12) != 3 )
  {
    WUTrace(0, 0, 32, 1, 0, L"Cert chain length check failed, length=%d", *(_DWORD *)(v7 + 12));
    v5 = 1;
    goto LABEL_85;
  }
  v51 = *(_QWORD *)(*(_QWORD *)(v7 + 16) + 8LL);
  pCertContext = *(PCCERT_CONTEXT *)(v51 + 8);
  if ( !CryptHashPublicKeyInfo(0, 0x800Cu, 0, 1u, &pCertContext->pCertInfo->SubjectPublicKeyInfo, Buf2, &v53) )
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
    goto LABEL_85;
  }
  CertHashAlgorithm = -2145078525;
  LODWORD(lpString2) = -2145078525;
  if ( v53 != 32 )
    goto LABEL_85;
  v5 = 1;
  pcbUsage = 0;
  v11 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
  {
    v20 = v53;
    v21 = 2;
    do
    {
      v22 = 0;
      while ( memcmp(&qword_1802E7870[6 * v3 + 6 * v22], Buf2, v20) )
      {
        v20 = v53;
        v22 = (unsigned int)(v22 + 1);
        if ( (unsigned int)v22 >= 5 )
          goto LABEL_37;
      }
      v5 = dword_1802E7860[12 * v11 + 12 * v22];
      pcbUsage = dword_1802E7864[12 * v11 + 12 * v22];
LABEL_37:
      v20 = v53;
      v3 += 5;
      v11 += 5;
      --v21;
    }
    while ( v21 );
    goto LABEL_38;
  }
  v12 = v53;
  v13 = 2;
  v43 = 0;
  do
  {
    v14 = 0;
    while ( 1 )
    {
      v50 = v14;
      if ( !memcmp(&qword_1802E7870[6 * v3 + 6 * v14], Buf2, v12) )
        break;
      v12 = v53;
      if ( ++v14 >= 5 )
      {
        v15 = v43;
        goto LABEL_21;
      }
    }
    v15 = 1;
    v43 = 1;
    v5 = dword_1802E7860[12 * v11 + 12 * v50];
    pcbUsage = dword_1802E7864[12 * v11 + 12 * v50];
LABEL_21:
    v12 = v53;
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
      while ( memcmp(&qword_1802E7500[6 * v16 + 6 * v19], Buf2, v53) )
      {
        v19 = (unsigned int)(v19 + 1);
        if ( (unsigned int)v19 >= 9 )
          goto LABEL_29;
      }
      v5 = dword_1802E74F0[12 * v17 + 12 * v19];
      pcbUsage = dword_1802E74F4[12 * v17 + 12 * v19];
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
    v24 = v53;
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
      v26 = HexStringFromBlobAllocW(Buf2, v53, (wchar_t **)&lpMem);
      v27 = lpMem;
      if ( v26 < 0 )
      {
        WUTrace(
          0,
          0,
          32,
          1,
          v26,
          L"Hash of public key doesn't match the known values, but failed to get the hash as hex string.");
      }
      else
      {
        LODWORD(pcbComputedHash) = v53;
        WUTrace(
          0,
          0,
          32,
          1,
          0,
          L"Hash of public key doesn't match the known values, cbKeyId=%d, rgbKeyId=%ws.",
          pcbComputedHash,
          lpMem);
      }
      if ( v27 )
        SusFree(v27);
      goto LABEL_85;
    }
  }
  else
  {
    v25 = pcbUsage;
  }
  if ( !v25 )
  {
    v30 = v47;
    goto LABEL_69;
  }
  v28 = 0;
  v29 = *(_QWORD *)(v51 + 40);
  if ( !*(_DWORD *)v29 )
  {
LABEL_58:
    WUTrace(0, 0, 32, 1, 0, L"EKU not found for SubCA");
LABEL_59:
    CertHashAlgorithm = -2145078525;
    goto LABEL_85;
  }
  while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, *(PCNZCH *)(*(_QWORD *)(v29 + 8) + 8LL * v28), -1) != 2 )
  {
    if ( ++v28 >= *(_DWORD *)v29 )
      goto LABEL_58;
  }
  v30 = v47;
  pcbUsage = 0;
  v31 = *(__int64 **)(v47 + 16);
  v32 = *v31;
  if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(*v31 + 8), 0, 0, &pcbUsage) )
    goto LABEL_6;
  v33 = (struct _CTL_USAGE *)SusAlloc(pcbUsage);
  v49 = v33;
  v34 = v33;
  if ( !v33 )
  {
    CertHashAlgorithm = -2147024882;
    goto LABEL_85;
  }
  if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(v32 + 8), 0, v33, &pcbUsage) )
    goto LABEL_6;
  v35 = 0;
  if ( !v34->cUsageIdentifier )
  {
LABEL_67:
    WUTrace(0, 0, 32, 1, 0, L"EKU not found for leaf cert");
    goto LABEL_59;
  }
  while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, v34->rgpszUsageIdentifier[v35], -1) != 2 )
  {
    if ( ++v35 >= v34->cUsageIdentifier )
      goto LABEL_67;
  }
LABEL_69:
  lpString1 = 0;
  lpString2 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::GetImpl'::`2'::impl) )
  {
    CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&lpString1);
    if ( CertHashAlgorithm >= 0 )
    {
      CertHashAlgorithm = GetCertHashAlgorithm(
                            *(PCCERT_CONTEXT *)(**(_QWORD **)(v30 + 16) + 8LL),
                            (wchar_t **)&lpString2);
      if ( CertHashAlgorithm >= 0 )
      {
        v38 = (WCHAR *)lpString1;
        v40 = (WCHAR *)lpString2;
        if ( CompareStringW(0x7Fu, 0, lpString1, -1, lpString2, -1) == 2 )
          goto LABEL_80;
        WUTrace(0, 0, 32, 1, 0, L"Inconsistent hash algorithm. Leaf:%ws, SubCA:%ws", v40, v38);
        CertHashAlgorithm = -2145078525;
LABEL_94:
        if ( !v40 )
          goto LABEL_74;
        v39 = v40;
        goto LABEL_78;
      }
      if ( lpString2 )
        operator delete((void *)lpString2, v36);
    }
LABEL_71:
    v37 = (WCHAR *)lpString1;
    if ( !lpString1 )
      goto LABEL_85;
    goto LABEL_72;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&lpString1);
  if ( CertHashAlgorithm < 0 )
    goto LABEL_71;
  v38 = (WCHAR *)lpString1;
  CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString1);
  if ( CertHashAlgorithm < 0 )
  {
LABEL_74:
    if ( !v38 )
      goto LABEL_85;
    v37 = v38;
LABEL_72:
    operator delete(v37, v36);
    goto LABEL_85;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(*(PCCERT_CONTEXT *)(**(_QWORD **)(v30 + 16) + 8LL), (wchar_t **)&lpString2);
  if ( CertHashAlgorithm < 0 )
  {
    v39 = (WCHAR *)lpString2;
    if ( !lpString2 )
      goto LABEL_74;
LABEL_78:
    operator delete(v39, v36);
    goto LABEL_74;
  }
  v40 = (WCHAR *)lpString2;
  CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString2);
  if ( CertHashAlgorithm < 0 )
    goto LABEL_94;
LABEL_80:
  if ( v40 )
    operator delete(v40, v36);
  if ( v38 )
    operator delete(v38, v36);
  CertHashAlgorithm = 0;
LABEL_85:
  SusFree(v49);
  if ( CertHashAlgorithm < 0 )
  {
    v5 = 0;
    WUTrace("DetermineSubCAIdentity", 1679, 32, 1, CertHashAlgorithm, L"Method failed");
  }
  return v5;
}

```

## disassembly

```asm
0x1801e81dc  mov     rax, rsp
0x1801e81df  mov     [rax+10h], rbx
0x1801e81e3  mov     [rax+18h], rsi
0x1801e81e7  mov     [rax+20h], rdi
0x1801e81eb  push    rbp
0x1801e81ec  push    r12
0x1801e81ee  push    r13
0x1801e81f0  push    r14
0x1801e81f2  push    r15
0x1801e81f4  lea     rbp, [rax-5Fh]
0x1801e81f8  sub     rsp, 0C0h
0x1801e81ff  mov     rax, cs:__security_cookie
0x1801e8206  xor     rax, rsp
0x1801e8209  mov     [rbp+57h+var_30], rax
0x1801e820d  xor     r14d, r14d
0x1801e8210  mov     [rbp+57h+lpMem], r8
0x1801e8214  mov     dword ptr [rbp+57h+lpString1], edx
0x1801e8217  xorps   xmm0, xmm0
0x1801e821a  mov     [rbp+57h+var_54], 20h ; ' '
0x1801e8221  mov     r12, r8
0x1801e8224  mov     [rbp+57h+var_70], r14
0x1801e8228  mov     r15d, r14d
0x1801e822b  mov     esi, r14d
0x1801e822e  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x1801e8232  movups  [rbp+57h+var_40], xmm0
0x1801e8236  test    rcx, rcx
0x1801e8239  jnz     short loc_1801E8245
0x1801e823b  mov     esi, 80004003h
0x1801e8240  jmp     loc_1801E87AB
0x1801e8245  mov     rax, [rcx+10h]
0x1801e8249  mov     r9d, 1; dwCertEncodingType
0x1801e824f  mov     rcx, [rax]
0x1801e8252  mov     [rbp+57h+var_80], rcx
0x1801e8256  mov     eax, [rcx+0Ch]
0x1801e8259  cmp     eax, 3
0x1801e825c  jz      short loc_1801E828B
0x1801e825e  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x1801e8262  lea     r8d, [r9+1Fh]
0x1801e8266  lea     rax, aCertChainLengt; "Cert chain length check failed, length="...
0x1801e826d  xor     edx, edx
0x1801e826f  mov     [rsp+0E0h+pbComputedHash], rax
0x1801e8274  xor     ecx, ecx
0x1801e8276  mov     [rsp+0E0h+pInfo], r14
0x1801e827b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e8280  mov     r15d, 1
0x1801e8286  jmp     loc_1801E87AB
0x1801e828b  mov     rax, [rcx+10h]
0x1801e828f  xor     r8d, r8d; dwFlags
0x1801e8292  lea     rcx, [rbp+57h+var_54]
0x1801e8296  mov     edx, 800Ch; Algid
0x1801e829b  mov     [rsp+0E0h+pcbComputedHash], rcx; pcbComputedHash
0x1801e82a0  lea     rcx, [rbp+57h+Buf2]
0x1801e82a4  mov     [rsp+0E0h+pbComputedHash], rcx; pbComputedHash
0x1801e82a9  xor     ecx, ecx; hCryptProv
0x1801e82ab  mov     rax, [rax+8]
0x1801e82af  mov     [rbp+57h+var_60], rax
0x1801e82b3  mov     rax, [rax+8]
0x1801e82b7  mov     [rbp+57h+pCertContext], rax
0x1801e82bb  mov     rax, [rax+18h]
0x1801e82bf  add     rax, 60h ; '`'
0x1801e82c3  mov     [rsp+0E0h+pInfo], rax; pInfo
0x1801e82c8  call    cs:__imp_CryptHashPublicKeyInfo
0x1801e82ce  test    eax, eax
0x1801e82d0  jnz     short loc_1801E830C
0x1801e82d2  call    cs:__imp_GetLastError
0x1801e82d8  mov     ecx, eax
0x1801e82da  mov     ebx, 80070000h
0x1801e82df  movzx   eax, ax
0x1801e82e2  or      eax, ebx
0x1801e82e4  test    ecx, ecx
0x1801e82e6  cmovle  eax, ecx
0x1801e82e9  test    eax, eax
0x1801e82eb  jns     short loc_1801E8302
0x1801e82ed  call    cs:__imp_GetLastError
0x1801e82f3  movzx   esi, ax
0x1801e82f6  or      esi, ebx
0x1801e82f8  test    eax, eax
0x1801e82fa  cmovle  esi, eax
0x1801e82fd  jmp     loc_1801E87AB
0x1801e8302  mov     esi, 80004005h
0x1801e8307  jmp     loc_1801E87AB
0x1801e830c  cmp     [rbp+57h+var_54], 20h ; ' '
0x1801e8310  mov     esi, 8024B303h
0x1801e8315  mov     dword ptr [rbp+57h+lpString2], esi
0x1801e8318  jnz     loc_1801E87AB
0x1801e831e  mov     r15d, 1
0x1801e8324  mov     [rbp+57h+pcbUsage], r14d
0x1801e8328  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x1801e832f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x1801e8334  mov     rdi, r14
0x1801e8337  test    al, al
0x1801e8339  jz      loc_1801E844F
0x1801e833f  mov     r8d, [rbp+57h+var_54]; Size
0x1801e8343  lea     r13d, [r15+1]
0x1801e8347  mov     [rbp+57h+var_A0], r14b
0x1801e834b  lea     rdx, qword_1802E7870
0x1801e8352  xor     ebx, ebx
0x1801e8354  mov     eax, ebx
0x1801e8356  mov     [rbp+57h+var_68], rax
0x1801e835a  add     rax, r14
0x1801e835d  lea     rcx, [rax+rax*2]
0x1801e8361  shl     rcx, 4
0x1801e8365  add     rcx, rdx; Buf1
0x1801e8368  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1801e836c  call    memcmp
0x1801e8371  test    eax, eax
0x1801e8373  jz      short loc_1801E838C
0x1801e8375  mov     r8d, [rbp+57h+var_54]
0x1801e8379  lea     rdx, qword_1802E7870
0x1801e8380  inc     ebx
0x1801e8382  cmp     ebx, 5
0x1801e8385  jb      short loc_1801E8354
0x1801e8387  mov     al, [rbp+57h+var_A0]
0x1801e838a  jmp     short loc_1801E83B8
0x1801e838c  mov     rax, [rbp+57h+var_68]
0x1801e8390  lea     rdx, __ImageBase
0x1801e8397  add     rax, rdi
0x1801e839a  lea     rcx, [rax+rax*2]
0x1801e839e  mov     al, 1
0x1801e83a0  add     rcx, rcx
0x1801e83a3  mov     [rbp+57h+var_A0], al
0x1801e83a6  mov     r15d, ds:rva dword_1802E7860[rdx+rcx*8]
0x1801e83ae  mov     ecx, ds:rva dword_1802E7864[rdx+rcx*8]
0x1801e83b5  mov     [rbp+57h+pcbUsage], ecx
0x1801e83b8  mov     r8d, [rbp+57h+var_54]
0x1801e83bc  lea     rdx, qword_1802E7870
0x1801e83c3  add     r14, 5
0x1801e83c7  add     rdi, 5
0x1801e83cb  sub     r13, 1
0x1801e83cf  jnz     short loc_1801E8352
0x1801e83d1  xor     r14d, r14d
0x1801e83d4  test    al, al
0x1801e83d6  jnz     loc_1801E84D6
0x1801e83dc  mov     edi, r14d
0x1801e83df  lea     r12d, [r14+2]
0x1801e83e3  lea     rsi, __ImageBase
0x1801e83ea  xor     ebx, ebx
0x1801e83ec  mov     r8d, [rbp+57h+var_54]; Size
0x1801e83f0  lea     rax, [r14+rbx]
0x1801e83f4  lea     rcx, [rax+rax*2]
0x1801e83f8  shl     rcx, 4
0x1801e83fc  lea     rax, qword_1802E7500
0x1801e8403  add     rcx, rax; Buf1
0x1801e8406  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1801e840a  call    memcmp
0x1801e840f  test    eax, eax
0x1801e8411  jz      short loc_1801E841C
0x1801e8413  inc     ebx
0x1801e8415  cmp     ebx, 9
0x1801e8418  jb      short loc_1801E83EC
0x1801e841a  jmp     short loc_1801E8439
0x1801e841c  lea     rax, [rdi+rbx]
0x1801e8420  lea     rcx, [rax+rax*2]
0x1801e8424  add     rcx, rcx
0x1801e8427  mov     eax, ds:rva dword_1802E74F4[rsi+rcx*8]
0x1801e842e  mov     r15d, ds:rva dword_1802E74F0[rsi+rcx*8]
0x1801e8436  mov     [rbp+57h+pcbUsage], eax
0x1801e8439  add     r14, 9
0x1801e843d  add     rdi, 9
0x1801e8441  sub     r12, 1
0x1801e8445  jnz     short loc_1801E83EA
0x1801e8447  mov     esi, dword ptr [rbp+57h+lpString2]
0x1801e844a  jmp     loc_1801E84CF
0x1801e844f  mov     edx, [rbp+57h+var_54]
0x1801e8452  lea     r8, qword_1802E7870
0x1801e8459  mov     r12d, 2
0x1801e845f  xor     ebx, ebx
0x1801e8461  lea     rax, [r14+rbx]
0x1801e8465  lea     rcx, [rax+rax*2]
0x1801e8469  shl     rcx, 4
0x1801e846d  add     rcx, r8; Buf1
0x1801e8470  mov     r8, rdx; Size
0x1801e8473  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1801e8477  call    memcmp
0x1801e847c  test    eax, eax
0x1801e847e  jz      short loc_1801E8493
0x1801e8480  mov     edx, [rbp+57h+var_54]
0x1801e8483  lea     r8, qword_1802E7870
0x1801e848a  inc     ebx
0x1801e848c  cmp     ebx, 5
0x1801e848f  jb      short loc_1801E8461
0x1801e8491  jmp     short loc_1801E84B7
0x1801e8493  lea     rax, [rdi+rbx]
0x1801e8497  lea     rcx, [rax+rax*2]
0x1801e849b  add     rcx, rcx
0x1801e849e  lea     rdx, __ImageBase
0x1801e84a5  mov     eax, ds:rva dword_1802E7864[rdx+rcx*8]
0x1801e84ac  mov     r15d, ds:rva dword_1802E7860[rdx+rcx*8]
0x1801e84b4  mov     [rbp+57h+pcbUsage], eax
0x1801e84b7  mov     edx, [rbp+57h+var_54]
0x1801e84ba  lea     r8, qword_1802E7870
0x1801e84c1  add     r14, 5
0x1801e84c5  add     rdi, 5
0x1801e84c9  sub     r12, 1
0x1801e84cd  jnz     short loc_1801E845F
0x1801e84cf  mov     r12, [rbp+57h+lpMem]
0x1801e84d3  xor     r14d, r14d
0x1801e84d6  cmp     r15d, 1
0x1801e84da  jnz     loc_1801E85B0
0x1801e84e0  mov     r13d, dword ptr [rbp+57h+lpString1]
0x1801e84e4  test    r13d, r13d
0x1801e84e7  jz      short loc_1801E8537
0x1801e84e9  test    r12, r12
0x1801e84ec  jz      short loc_1801E8537
0x1801e84ee  mov     ebx, r14d
0x1801e84f1  mov     r14d, [rbp+57h+var_54]
0x1801e84f5  mov     eax, ebx
0x1801e84f7  lea     rdi, [rax+rax*2]
0x1801e84fb  cmp     dword ptr [r12+rdi*8+8], 20h ; ' '
0x1801e8501  jnz     short loc_1801E8518
0x1801e8503  mov     rcx, [r12+rdi*8+10h]; Buf1
0x1801e8508  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1801e850c  mov     r8, r14; Size
0x1801e850f  call    memcmp
0x1801e8514  test    eax, eax
0x1801e8516  jz      short loc_1801E8521
0x1801e8518  inc     ebx
0x1801e851a  cmp     ebx, r13d
0x1801e851d  jb      short loc_1801E84F5
0x1801e851f  jmp     short loc_1801E8534
0x1801e8521  mov     r15d, [r12+rdi*8]
0x1801e8525  mov     eax, [r12+rdi*8+4]
0x1801e852a  cmp     r15d, 1
0x1801e852e  jnz     loc_1801E85B5
0x1801e8534  xor     r14d, r14d
0x1801e8537  mov     edx, [rbp+57h+var_54]; unsigned int
0x1801e853a  lea     r8, [rbp+57h+lpMem]; wchar_t **
0x1801e853e  lea     rcx, [rbp+57h+Buf2]; unsigned __int8 *
0x1801e8542  mov     [rbp+57h+lpMem], r14
0x1801e8546  call    ?HexStringFromBlobAllocW@@YAJPEBEKPEAPEA_W@Z; HexStringFromBlobAllocW(uchar const *,ulong,wchar_t * *)
0x1801e854b  mov     rbx, [rbp+57h+lpMem]
0x1801e854f  xor     edx, edx
0x1801e8551  lea     r9d, [rdx+1]
0x1801e8555  lea     r8d, [rdx+20h]
0x1801e8559  test    eax, eax
0x1801e855b  js      short loc_1801E8583
0x1801e855d  mov     eax, [rbp+57h+var_54]
0x1801e8560  xor     ecx, ecx
0x1801e8562  mov     [rsp+0E0h+var_A8], rbx
0x1801e8567  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x1801e856b  lea     rax, aHashOfPublicKe_0; "Hash of public key doesn't match the kn"...
0x1801e8572  mov     [rsp+0E0h+pbComputedHash], rax
0x1801e8577  mov     [rsp+0E0h+pInfo], r14
0x1801e857c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e8581  jmp     short loc_1801E859A
0x1801e8583  lea     rcx, aHashOfPublicKe; "Hash of public key doesn't match the kn"...
0x1801e858a  mov     [rsp+0E0h+pbComputedHash], rcx
0x1801e858f  xor     ecx, ecx
0x1801e8591  mov     dword ptr [rsp+0E0h+pInfo], eax
0x1801e8595  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e859a  test    rbx, rbx
0x1801e859d  jz      loc_1801E87AB
0x1801e85a3  mov     rcx, rbx; lpMem
0x1801e85a6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801e85ab  jmp     loc_1801E87AB
0x1801e85b0  mov     eax, [rbp+57h+pcbUsage]
0x1801e85b3  jmp     short loc_1801E85B8
0x1801e85b5  xor     r14d, r14d
0x1801e85b8  or      r12d, 0FFFFFFFFh
0x1801e85bc  mov     r13d, 7Fh
0x1801e85c2  test    eax, eax
0x1801e85c4  jz      loc_1801E86EB
0x1801e85ca  mov     rdi, [rbp+57h+var_60]
0x1801e85ce  mov     ebx, r14d
0x1801e85d1  mov     rdi, [rdi+28h]
0x1801e85d5  cmp     [rdi], r14d
0x1801e85d8  jbe     short loc_1801E8611
0x1801e85da  mov     rax, [rdi+8]
0x1801e85de  lea     r8, a1361413117661; "1.3.6.1.4.1.311.76.6.1"
0x1801e85e5  mov     ecx, ebx
0x1801e85e7  mov     r9d, r12d; cchCount1
0x1801e85ea  mov     dword ptr [rsp+0E0h+pbComputedHash], r12d; cchCount2
0x1801e85ef  mov     edx, 1; dwCmpFlags
0x1801e85f4  mov     rax, [rax+rcx*8]
0x1801e85f8  mov     ecx, r13d; Locale
0x1801e85fb  mov     [rsp+0E0h+pInfo], rax; lpString2
0x1801e8600  call    cs:__imp_CompareStringA
0x1801e8606  cmp     eax, 2
0x1801e8609  jz      short loc_1801E863D
0x1801e860b  inc     ebx
0x1801e860d  cmp     ebx, [rdi]
0x1801e860f  jb      short loc_1801E85DA
0x1801e8611  lea     rax, aEkuNotFoundFor_0; "EKU not found for SubCA"
0x1801e8618  xor     edx, edx
0x1801e861a  mov     [rsp+0E0h+pbComputedHash], rax
0x1801e861f  xor     ecx, ecx
0x1801e8621  mov     [rsp+0E0h+pInfo], r14
0x1801e8626  lea     r9d, [rdx+1]
0x1801e862a  lea     r8d, [rdx+20h]
0x1801e862e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e8633  mov     esi, 8024B303h
0x1801e8638  jmp     loc_1801E87AB
0x1801e863d  mov     rdi, [rbp+57h+var_80]
0x1801e8641  lea     r9, [rbp+57h+pcbUsage]; pcbUsage
0x1801e8645  mov     [rbp+57h+pcbUsage], r14d
0x1801e8649  xor     r8d, r8d; pUsage
0x1801e864c  xor     edx, edx; dwFlags
0x1801e864e  mov     rax, [rdi+10h]
0x1801e8652  mov     rbx, [rax]
0x1801e8655  mov     rcx, [rbx+8]; pCertContext
  ... truncated ...
```
