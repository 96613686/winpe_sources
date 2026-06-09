# DriverFinalPolicy

- ea: `0x180028d60`
- end: `0x180029249`
- name: `DriverFinalPolicy`
- size: `1257`
- prototype: `__int64 __fastcall(CRYPT_PROVIDER_DATA *pProvData)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callees

- `0x18000d5ec`
- `0x180014bf0`
- `0x1800197d4`
- `0x18001a0d0`
- `0x18001a3f0`
- `0x18001e4e0`
- `0x18001ee98`
- `0x18001f500`
- `0x18001fd20`
- `0x180023ba4`
- `0x180028d60`
- `0x18002d100`
- `0x180044198`
- `0x18004430c`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029212`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029218`
- `CRYPT32!CertGetNameStringW` at `0x180028fd0`
- `CRYPT32!CertGetNameStringW` at `0x180028fd0`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180028e51`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180028efd`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180028e51`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180028efd`
- `CRYPT32!CertOpenStore` at `0x18002900f`
- `CRYPT32!CertOpenStore` at `0x18002900f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180028fda`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180028fda`

## pseudocode

```c
__int64 __fastcall DriverFinalPolicy(CRYPT_PROVIDER_DATA *pProvData)
{
  CRYPTCATATTRIBUTE *v1; // r13
  bool v2; // cc
  WINTRUST_DATA *pWintrustData; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v6; // rbx
  int v7; // esi
  char v8; // r14
  BOOL v9; // eax
  PCCERT_CHAIN_CONTEXT pChainContext; // rax
  PCERT_SIMPLE_CHAIN v11; // rdx
  unsigned int cElement; // eax
  signed int LastError; // r14d
  DWORD v14; // ecx
  WINTRUST_DATA *v15; // rbx
  int v16; // r15d
  struct DRIVER_VER_INFO_ *pPolicyCallbackData; // rbx
  CRYPT_PROVIDER_SGNR *v18; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  CRYPT_PROVIDER_CERT *v20; // rsi
  const CERT_CONTEXT *pCert; // rcx
  DWORD **p_padwTrustStepErrors; // rsi
  DWORD *padwTrustStepErrors; // rax
  struct _PROVDATA_SIP *pPDSip; // rax
  struct SIP_SUBJECTINFO_ *psSipSubjectInfo; // rax
  struct MS_ADDINFO_FLAT_ *psFlat; // rcx
  struct SIP_INDIRECT_DATA_ *pIndirectData; // r12
  CRYPTCATMEMBER *v28; // rdx
  CRYPTCATATTRIBUTE *v29; // r12
  struct DRIVER_VER_INFO_ *v30; // r9
  struct CRYPTCATATTRIBUTE_ *v31; // rdx
  struct DRIVER_VER_INFO_ *v32; // rcx
  WINTRUST_DATA *v33; // rax
  WINTRUST_DATA *v34; // rcx
  int v35; // ecx
  BYTE *pbValue; // rcx
  CRYPT_PROVIDER_PRIVDATA *ProvPrivateDataFromChain; // rax
  _QWORD *pvProvData; // rdx
  WINTRUST_DATA *v39; // rax
  DWORD dwUIChoice; // ebx
  GUID pgProviderID; // [rsp+30h] [rbp-48h] BYREF
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+40h] [rbp-38h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+50h] [rbp-28h] BYREF
  bool v45; // [rsp+C0h] [rbp+48h] BYREF

  pgProviderID.Data1 = -145692989;
  *(_DWORD *)&pgProviderID.Data2 = 298924270;
  v1 = 0;
  *(_DWORD *)pgProviderID.Data4 = -1073683067;
  v2 = pProvData->cbStruct <= 0xA8;
  *(_DWORD *)&pgProviderID.Data4[4] = -292175281;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyPara = 0;
  if ( v2 )
    goto LABEL_83;
  pWintrustData = pProvData->pWintrustData;
  if ( !pWintrustData || pWintrustData->cbStruct <= 0x38 )
    goto LABEL_83;
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(pProvData, 0, 0, 0);
  v6 = ProvSignerFromChain;
  if ( !ProvSignerFromChain )
    goto LABEL_82;
  if ( ProvSignerFromChain->pChainContext )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca>::GetImpl'::`2'::impl) )
    {
      v7 = 0;
      while ( 1 )
      {
        pPolicyPara.pvExtraPolicyPara = 0;
        pPolicyPara.cbSize = 16;
        memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
        pPolicyStatus.cbSize = 24;
        if ( v7 )
        {
          v8 = 1;
          pPolicyPara.dwFlags = 0x20000;
        }
        else
        {
          v8 = 0;
          pPolicyPara.dwFlags = 0x10000;
        }
        v9 = CertVerifyCertificateChainPolicy((LPCSTR)7, v6->pChainContext, &pPolicyPara, &pPolicyStatus);
        if ( !pPolicyStatus.dwError )
        {
          if ( v9 )
            break;
        }
        if ( !v8 )
        {
          pChainContext = v6->pChainContext;
          v45 = 0;
          if ( pChainContext->cChain )
          {
            v11 = *pChainContext->rgpChain;
            cElement = v11->cElement;
            if ( cElement >= 2 )
            {
              LastError = IsCertPreprod2024Pca(v11->rgpElement[cElement - 2]->pCertContext, &v45);
              if ( LastError < 0 )
                goto LABEL_40;
              if ( v45 && (unsigned int)++v7 < 2 )
                continue;
            }
          }
        }
        goto LABEL_19;
      }
    }
    else
    {
      pPolicyPara.pvExtraPolicyPara = 0;
      memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
      pPolicyStatus.cbSize = 24;
      pPolicyPara.cbSize = 16;
      pPolicyPara.dwFlags = 0x10000;
      if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, v6->pChainContext, &pPolicyPara, &pPolicyStatus)
        || pPolicyStatus.dwError )
      {
LABEL_19:
        v14 = -2146762487;
LABEL_84:
        SetLastError(v14);
        LastError = GetLastError();
        p_padwTrustStepErrors = &pProvData->padwTrustStepErrors;
        goto LABEL_85;
      }
    }
    if ( (unsigned __int8)I_SysDevEvWhqlEnabled()
      && !(unsigned __int8)I_SatisfiesSysDevEvWhqlRequirement((*(*v6->pChainContext->rgpChain)->rgpElement)->pCertContext) )
    {
      v14 = -2146762480;
      goto LABEL_84;
    }
  }
  v15 = pProvData->pWintrustData;
  v16 = 0;
  if ( v15->cbStruct > 0x48 )
    v16 = (v15->dwProvFlags >> 10) & 1;
  pPolicyCallbackData = (struct DRIVER_VER_INFO_ *)v15->pPolicyCallbackData;
  if ( pPolicyCallbackData )
  {
    if ( pPolicyCallbackData->cbStruct <= 0x430 )
      goto LABEL_83;
    pPolicyCallbackData->wszVersion[0] = 0;
    v18 = WTHelperGetProvSignerFromChain(pProvData, 0, 0, 0);
    if ( v18 )
    {
      ProvCertFromChain = WTHelperGetProvCertFromChain(v18, 0);
      v20 = ProvCertFromChain;
      if ( !ProvCertFromChain )
      {
        v14 = -2146869246;
        goto LABEL_84;
      }
      pCert = ProvCertFromChain->pCert;
      if ( pCert )
      {
        CertGetNameStringW(pCert, 4u, 0, 0, pPolicyCallbackData->wszSignedBy, 0x104u);
        pPolicyCallbackData->pcSignerCertContext = CertDuplicateCertificateContext(v20->pCert);
        if ( pPolicyCallbackData->dwReserved1 == 1 && !pPolicyCallbackData->dwReserved2 && pProvData->hMsg )
          pPolicyCallbackData->dwReserved2 = (ULONG_PTR)CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, pProvData->hMsg);
      }
      goto LABEL_37;
    }
LABEL_82:
    v14 = -2146762496;
    goto LABEL_84;
  }
LABEL_37:
  p_padwTrustStepErrors = &pProvData->padwTrustStepErrors;
  padwTrustStepErrors = pProvData->padwTrustStepErrors;
  if ( padwTrustStepErrors )
    padwTrustStepErrors[36] = 0;
  LastError = checkGetErrorBasedOnStepErrors(pProvData);
  if ( LastError )
  {
LABEL_40:
    v14 = LastError;
    goto LABEL_84;
  }
  pPDSip = pProvData->pPDSip;
  if ( !pPDSip
    || pPDSip->cbStruct <= 0x38
    || (psSipSubjectInfo = pPDSip->psSipSubjectInfo) == 0
    || psSipSubjectInfo->dwUnionChoice != 2
    || (psFlat = psSipSubjectInfo->psFlat) == 0
    || (pIndirectData = psFlat->pIndirectData) == 0
    || (v28 = *(CRYPTCATMEMBER **)&psFlat[1].cbStruct) == 0
    || pProvData->pWintrustData->dwUnionChoice != 2 )
  {
    v33 = pProvData->pWintrustData;
    v29 = 0;
    if ( !v33 || v33->dwUnionChoice != 2 )
      goto LABEL_65;
LABEL_83:
    v14 = 87;
    goto LABEL_84;
  }
  v1 = CryptCATGetAttrInfo(psFlat->pIndirectData, v28, (LPWSTR)L"OSAttr");
  v29 = CryptCATGetCatAttrInfo(pIndirectData, (LPWSTR)L"OSAttr");
  if ( pPolicyCallbackData && !pPolicyCallbackData->dwPlatform && !pPolicyCallbackData->dwVersion && !v16 )
    goto LABEL_65;
  if ( (unsigned int)_ValidCatAttr(v1) )
  {
    v31 = v1;
  }
  else
  {
    if ( !(unsigned int)_ValidCatAttr(v29) && !(unsigned int)_ValidCatAttr(v1) )
    {
LABEL_61:
      v14 = 1151;
      goto LABEL_84;
    }
    v31 = v29;
  }
  v32 = v30;
  if ( !v16 )
    v32 = pPolicyCallbackData;
  if ( !(unsigned int)_CheckVersionAttributeNEW(v32, v31) )
    goto LABEL_61;
LABEL_65:
  v34 = pProvData[1].pWintrustData;
  if ( v34 )
  {
    v35 = (int)v34->pPolicyCallbackData;
    if ( (v35 & 0x40000004) != 0 && (v35 & 0xA0000000) == 0x20000000 && (v35 & 5) != 1 )
      goto LABEL_82;
  }
  if ( pPolicyCallbackData
    && !pPolicyCallbackData->wszVersion[0]
    && (v1 && v1->cbValue && (pbValue = v1->pbValue) != 0 || v29 && v29->cbValue && (pbValue = v29->pbValue) != 0) )
  {
    CopyBytesToMaxPathString(pbValue);
  }
  ProvPrivateDataFromChain = WTHelperGetProvPrivateDataFromChain(pProvData, &pgProviderID);
  if ( !ProvPrivateDataFromChain )
    goto LABEL_86;
  pvProvData = ProvPrivateDataFromChain->pvProvData;
  if ( !pvProvData || !pvProvData[12] )
    goto LABEL_86;
  v39 = pProvData->pWintrustData;
  dwUIChoice = v39->dwUIChoice;
  v39->dwUIChoice = 2;
  LastError = ((__int64 (__fastcall *)(CRYPT_PROVIDER_DATA *))pvProvData[12])(pProvData);
  pProvData->pWintrustData->dwUIChoice = dwUIChoice;
LABEL_85:
  if ( LastError != 87 )
LABEL_86:
    (*p_padwTrustStepErrors)[36] = LastError;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180028d60  push    rbp
0x180028d62  push    rbx
0x180028d63  push    rsi
0x180028d64  push    rdi
0x180028d65  push    r12
0x180028d67  push    r13
0x180028d69  push    r14
0x180028d6b  push    r15
0x180028d6d  mov     rbp, rsp
0x180028d70  sub     rsp, 78h
0x180028d74  xor     eax, eax
0x180028d76  mov     [rbp+pgProviderID.Data1], 0F750E6C3h
0x180028d7d  xorps   xmm0, xmm0
0x180028d80  mov     dword ptr [rbp+pgProviderID.Data2], 11D138EEh
0x180028d87  xor     r13d, r13d
0x180028d8a  mov     dword ptr [rbp+pgProviderID.Data4], 0C000E585h
0x180028d91  cmp     dword ptr [rcx], 0A8h
0x180028d97  mov     rdi, rcx
0x180028d9a  mov     dword ptr [rbp+pgProviderID.Data4+4], 0EE95C24Fh
0x180028da1  movups  xmmword ptr [rbp+pPolicyStatus.cbSize], xmm0
0x180028da5  mov     [rbp+pPolicyStatus.pvExtraPolicyStatus], rax
0x180028da9  movups  xmmword ptr [rbp+pPolicyPara.cbSize], xmm0
0x180028dad  jbe     loc_18002920D
0x180028db3  mov     rax, [rcx+8]
0x180028db7  test    rax, rax
0x180028dba  jz      loc_18002920D
0x180028dc0  cmp     dword ptr [rax], 38h ; '8'
0x180028dc3  jbe     loc_18002920D
0x180028dc9  xor     r9d, r9d; idxCounterSigner
0x180028dcc  xor     r8d, r8d; fCounterSigner
0x180028dcf  xor     edx, edx; idxSigner
0x180028dd1  call    WTHelperGetProvSignerFromChain
0x180028dd6  mov     rbx, rax
0x180028dd9  test    rax, rax
0x180028ddc  jz      loc_180029206
0x180028de2  lea     r12d, [r13+1]
0x180028de6  cmp     [rax+38h], r13
0x180028dea  jz      loc_180028F3F
0x180028df0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca> `wil::Feature<__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca>::GetImpl(void)'::`2'::impl
0x180028df7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Wintrust2024PreprodPca>::__private_IsEnabled(void)
0x180028dfc  test    al, al
0x180028dfe  jz      loc_180028EC8
0x180028e04  mov     esi, r13d
0x180028e07  xor     eax, eax
0x180028e09  mov     [rbp+pPolicyPara.pvExtraPolicyPara], r13
0x180028e0d  mov     [rbp+pPolicyStatus.pvExtraPolicyStatus], rax
0x180028e11  xorps   xmm0, xmm0
0x180028e14  mov     [rbp+pPolicyPara.cbSize], 10h
0x180028e1b  movups  xmmword ptr [rbp+pPolicyStatus.cbSize], xmm0
0x180028e1f  mov     [rbp+pPolicyStatus.cbSize], 18h
0x180028e26  test    esi, esi
0x180028e28  jz      short loc_180028E36
0x180028e2a  mov     r14b, r12b
0x180028e2d  mov     [rbp+pPolicyPara.dwFlags], 20000h
0x180028e34  jmp     short loc_180028E40
0x180028e36  mov     r14b, r13b
0x180028e39  mov     [rbp+pPolicyPara.dwFlags], 10000h
0x180028e40  mov     rdx, [rbx+38h]; pChainContext
0x180028e44  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x180028e48  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x180028e4c  mov     ecx, 7; pszPolicyOID
0x180028e51  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180028e57  cmp     [rbp+pPolicyStatus.dwError], r13d
0x180028e5b  jnz     short loc_180028E65
0x180028e5d  test    eax, eax
0x180028e5f  jnz     loc_180028F0D
0x180028e65  test    r14b, r14b
0x180028e68  jnz     short loc_180028EBE
0x180028e6a  mov     rax, [rbx+38h]
0x180028e6e  mov     [rbp+arg_0], r13b
0x180028e72  cmp     [rax+0Ch], r13d
0x180028e76  jbe     short loc_180028EBE
0x180028e78  mov     rax, [rax+10h]
0x180028e7c  mov     rdx, [rax]
0x180028e7f  mov     eax, [rdx+0Ch]
0x180028e82  cmp     eax, 2
0x180028e85  jb      short loc_180028EBE
0x180028e87  add     eax, 0FFFFFFFEh
0x180028e8a  mov     ecx, eax
0x180028e8c  mov     rax, [rdx+10h]
0x180028e90  lea     rdx, [rbp+arg_0]; bool *
0x180028e94  mov     rcx, [rax+rcx*8]
0x180028e98  mov     rcx, [rcx+8]; struct _CERT_CONTEXT *
0x180028e9c  call    ?IsCertPreprod2024Pca@@YAJPEBU_CERT_CONTEXT@@PEA_N@Z; IsCertPreprod2024Pca(_CERT_CONTEXT const *,bool *)
0x180028ea1  mov     r14d, eax
0x180028ea4  test    eax, eax
0x180028ea6  js      loc_18002903B
0x180028eac  cmp     [rbp+arg_0], r13b
0x180028eb0  jz      short loc_180028EBE
0x180028eb2  add     esi, r12d
0x180028eb5  cmp     esi, 2
0x180028eb8  jb      loc_180028E07
0x180028ebe  mov     ecx, 800B0109h
0x180028ec3  jmp     loc_180029212
0x180028ec8  xor     eax, eax
0x180028eca  mov     [rbp+pPolicyPara.pvExtraPolicyPara], r13
0x180028ece  xorps   xmm0, xmm0
0x180028ed1  mov     [rbp+pPolicyStatus.pvExtraPolicyStatus], rax
0x180028ed5  movups  xmmword ptr [rbp+pPolicyStatus.cbSize], xmm0
0x180028ed9  mov     [rbp+pPolicyStatus.cbSize], 18h
0x180028ee0  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x180028ee4  mov     [rbp+pPolicyPara.cbSize], 10h
0x180028eeb  lea     ecx, [rax+7]; pszPolicyOID
0x180028eee  mov     [rbp+pPolicyPara.dwFlags], 10000h
0x180028ef5  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x180028ef9  mov     rdx, [rbx+38h]; pChainContext
0x180028efd  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180028f03  test    eax, eax
0x180028f05  jz      short loc_180028EBE
0x180028f07  cmp     [rbp+pPolicyStatus.dwError], r13d
0x180028f0b  jnz     short loc_180028EBE
0x180028f0d  call    I_SysDevEvWhqlEnabled
0x180028f12  test    al, al
0x180028f14  jz      short loc_180028F3F
0x180028f16  mov     rax, [rbx+38h]
0x180028f1a  mov     rcx, [rax+10h]
0x180028f1e  mov     rax, [rcx]
0x180028f21  mov     rcx, [rax+10h]
0x180028f25  mov     rcx, [rcx]
0x180028f28  mov     rcx, [rcx+8]; pCertContext
0x180028f2c  call    I_SatisfiesSysDevEvWhqlRequirement
0x180028f31  test    al, al
0x180028f33  jnz     short loc_180028F3F
0x180028f35  mov     ecx, 800B0110h
0x180028f3a  jmp     loc_180029212
0x180028f3f  mov     rbx, [rdi+8]
0x180028f43  mov     r15d, r13d
0x180028f46  cmp     dword ptr [rbx], 48h ; 'H'
0x180028f49  jbe     short loc_180028F56
0x180028f4b  mov     r15d, [rbx+48h]
0x180028f4f  shr     r15d, 0Ah
0x180028f53  and     r15d, r12d
0x180028f56  mov     rbx, [rbx+8]
0x180028f5a  test    rbx, rbx
0x180028f5d  jz      loc_180029019
0x180028f63  cmp     dword ptr [rbx], 430h
0x180028f69  jbe     loc_18002920D
0x180028f6f  xor     r9d, r9d; idxCounterSigner
0x180028f72  mov     [rbx+20h], r13w
0x180028f77  xor     r8d, r8d; fCounterSigner
0x180028f7a  xor     edx, edx; idxSigner
0x180028f7c  mov     rcx, rdi; pProvData
0x180028f7f  call    WTHelperGetProvSignerFromChain
0x180028f84  test    rax, rax
0x180028f87  jz      loc_180029206
0x180028f8d  xor     edx, edx; idxCert
0x180028f8f  mov     rcx, rax; pSgnr
0x180028f92  call    WTHelperGetProvCertFromChain
0x180028f97  mov     rsi, rax
0x180028f9a  test    rax, rax
0x180028f9d  jnz     short loc_180028FA9
0x180028f9f  mov     ecx, 80096002h
0x180028fa4  jmp     loc_180029212
0x180028fa9  mov     rcx, [rax+8]; pCertContext
0x180028fad  test    rcx, rcx
0x180028fb0  jz      short loc_180029019
0x180028fb2  xor     r9d, r9d; pvTypePara
0x180028fb5  mov     [rsp+78h+cchNameString], 104h; cchNameString
0x180028fbd  lea     rax, [rbx+228h]
0x180028fc4  xor     r8d, r8d; dwFlags
0x180028fc7  mov     [rsp+78h+pszNameString], rax; pszNameString
0x180028fcc  lea     edx, [r9+4]; dwType
0x180028fd0  call    cs:__imp_CertGetNameStringW
0x180028fd6  mov     rcx, [rsi+8]; pCertContext
0x180028fda  call    cs:__imp_CertDuplicateCertificateContext
0x180028fe0  mov     [rbx+430h], rax
0x180028fe7  cmp     [rbx+8], r12
0x180028feb  jnz     short loc_180029019
0x180028fed  cmp     [rbx+10h], r13
0x180028ff1  jnz     short loc_180029019
0x180028ff3  mov     rax, [rdi+70h]
0x180028ff7  test    rax, rax
0x180028ffa  jz      short loc_180029019
0x180028ffc  xor     r9d, r9d; dwFlags
0x180028fff  mov     [rsp+78h+pszNameString], rax; pvPara
0x180029004  xor     r8d, r8d; hCryptProv
0x180029007  mov     edx, 10001h; dwEncodingType
0x18002900c  mov     rcx, r12; lpszStoreProvider
0x18002900f  call    cs:__imp_CertOpenStore
0x180029015  mov     [rbx+10h], rax
0x180029019  lea     rsi, [rdi+50h]
0x18002901d  mov     rax, [rsi]
0x180029020  test    rax, rax
0x180029023  jz      short loc_18002902C
0x180029025  mov     [rax+90h], r13d
0x18002902c  mov     rcx, rdi
0x18002902f  call    checkGetErrorBasedOnStepErrors
0x180029034  mov     r14d, eax
0x180029037  test    eax, eax
0x180029039  jz      short loc_180029043
0x18002903b  mov     ecx, r14d
0x18002903e  jmp     loc_180029212
0x180029043  mov     rax, [rdi+0A0h]
0x18002904a  test    rax, rax
0x18002904d  jz      loc_180029133
0x180029053  cmp     dword ptr [rax], 38h ; '8'
0x180029056  jbe     loc_180029133
0x18002905c  mov     rax, [rax+28h]
0x180029060  test    rax, rax
0x180029063  jz      loc_180029133
0x180029069  cmp     dword ptr [rax+68h], 2
0x18002906d  jnz     loc_180029133
0x180029073  mov     rcx, [rax+70h]
0x180029077  test    rcx, rcx
0x18002907a  jz      loc_180029133
0x180029080  mov     r12, [rcx+8]
0x180029084  test    r12, r12
0x180029087  jz      loc_180029133
0x18002908d  mov     rdx, [rcx+10h]; pCatMember
0x180029091  test    rdx, rdx
0x180029094  jz      loc_180029133
0x18002909a  mov     rax, [rdi+8]
0x18002909e  cmp     dword ptr [rax+20h], 2
0x1800290a2  jnz     loc_180029133
0x1800290a8  lea     r8, pwszReferenceTag; "OSAttr"
0x1800290af  mov     rcx, r12; hCatalog
0x1800290b2  call    CryptCATGetAttrInfo
0x1800290b7  lea     rdx, pwszReferenceTag; "OSAttr"
0x1800290be  mov     rcx, r12; hCatalog
0x1800290c1  mov     r13, rax
0x1800290c4  call    CryptCATGetCatAttrInfo
0x1800290c9  xor     r9d, r9d
0x1800290cc  mov     r12, rax
0x1800290cf  test    rbx, rbx
0x1800290d2  jz      short loc_1800290E5
0x1800290d4  cmp     [rbx+18h], r9d
0x1800290d8  jnz     short loc_1800290E5
0x1800290da  cmp     [rbx+1Ch], r9d
0x1800290de  jnz     short loc_1800290E5
0x1800290e0  test    r15d, r15d
0x1800290e3  jz      short loc_18002914C
0x1800290e5  mov     rcx, r13; struct CRYPTCATATTRIBUTE_ *
0x1800290e8  call    ?_ValidCatAttr@@YAHPEAUCRYPTCATATTRIBUTE_@@@Z; _ValidCatAttr(CRYPTCATATTRIBUTE_ *)
0x1800290ed  test    eax, eax
0x1800290ef  jz      short loc_18002910C
0x1800290f1  mov     rdx, r13; struct CRYPTCATATTRIBUTE_ *
0x1800290f4  mov     rcx, r9
0x1800290f7  test    r15d, r15d
0x1800290fa  cmovz   rcx, rbx; struct DRIVER_VER_INFO_ *
0x1800290fe  call    ?_CheckVersionAttributeNEW@@YAHPEAUDRIVER_VER_INFO_@@PEAUCRYPTCATATTRIBUTE_@@@Z; _CheckVersionAttributeNEW(DRIVER_VER_INFO_ *,CRYPTCATATTRIBUTE_ *)
0x180029103  xor     r9d, r9d
0x180029106  test    eax, eax
0x180029108  jz      short loc_180029124
0x18002910a  jmp     short loc_18002914C
0x18002910c  mov     rcx, r12; struct CRYPTCATATTRIBUTE_ *
0x18002910f  call    ?_ValidCatAttr@@YAHPEAUCRYPTCATATTRIBUTE_@@@Z; _ValidCatAttr(CRYPTCATATTRIBUTE_ *)
0x180029114  test    eax, eax
0x180029116  jnz     short loc_18002912E
0x180029118  mov     rcx, r13; struct CRYPTCATATTRIBUTE_ *
0x18002911b  call    ?_ValidCatAttr@@YAHPEAUCRYPTCATATTRIBUTE_@@@Z; _ValidCatAttr(CRYPTCATATTRIBUTE_ *)
0x180029120  test    eax, eax
0x180029122  jnz     short loc_18002912E
0x180029124  mov     ecx, 47Fh
0x180029129  jmp     loc_180029212
0x18002912e  mov     rdx, r12
0x180029131  jmp     short loc_1800290F4
0x180029133  mov     rax, [rdi+8]
0x180029137  xor     r9d, r9d
0x18002913a  mov     r12, r13
0x18002913d  test    rax, rax
0x180029140  jz      short loc_18002914C
0x180029142  cmp     dword ptr [rax+20h], 2
0x180029146  jz      loc_18002920D
0x18002914c  mov     rcx, [rdi+0E8h]
0x180029153  test    rcx, rcx
0x180029156  jz      short loc_18002917D
0x180029158  mov     ecx, [rcx+8]
0x18002915b  test    ecx, 40000004h
0x180029161  jz      short loc_18002917D
0x180029163  mov     eax, ecx
0x180029165  and     eax, 0A0000000h
0x18002916a  cmp     eax, 20000000h
0x18002916f  jnz     short loc_18002917D
0x180029171  and     cl, 5
0x180029174  cmp     cl, 1
0x180029177  jnz     loc_180029206
0x18002917d  test    rbx, rbx
0x180029180  jz      short loc_1800291BF
0x180029182  lea     r8, [rbx+20h]
0x180029186  cmp     [r8], r9w
0x18002918a  jnz     short loc_1800291BF
0x18002918c  test    r13, r13
0x18002918f  jz      short loc_1800291A2
0x180029191  mov     edx, [r13+14h]
0x180029195  test    edx, edx
0x180029197  jz      short loc_1800291A2
0x180029199  mov     rcx, [r13+18h]
0x18002919d  test    rcx, rcx
0x1800291a0  jnz     short loc_1800291BA
0x1800291a2  test    r12, r12
0x1800291a5  jz      short loc_1800291BF
0x1800291a7  mov     edx, [r12+14h]
0x1800291ac  test    edx, edx
0x1800291ae  jz      short loc_1800291BF
0x1800291b0  mov     rcx, [r12+18h]; Src
0x1800291b5  test    rcx, rcx
0x1800291b8  jz      short loc_1800291BF
0x1800291ba  call    CopyBytesToMaxPathString
0x1800291bf  lea     rdx, [rbp+pgProviderID]; pgProviderID
0x1800291c3  mov     rcx, rdi; pProvData
  ... truncated ...
```
