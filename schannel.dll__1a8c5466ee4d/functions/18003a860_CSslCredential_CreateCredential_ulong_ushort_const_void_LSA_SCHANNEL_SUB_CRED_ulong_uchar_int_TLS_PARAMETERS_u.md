# CSslCredential::CreateCredential(ulong,ushort const *,void *,LSA_SCHANNEL_SUB_CRED *,ulong,uchar,int,_TLS_PARAMETERS *,ulong)

- ea: `0x18003a860`
- end: `0x18003b28e`
- name: `?CreateCredential@CSslCredential@@QEAAKKPEBGPEAXPEAULSA_SCHANNEL_SUB_CRED@@KEHPEAU_TLS_PARAMETERS@@K@Z`
- size: `2606`
- prototype: `unsigned int __usercall@<eax>(CSslCredential *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, void *@<r9>, struct LSA_SCHANNEL_SUB_CRED *, unsigned int, unsigned __int8, int, struct _TLS_PARAMETERS *, unsigned int)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800112c0`
- `0x18003a5e8`
- `0x1800728fc`

## callees

- `0x180011054`
- `0x180013f90`
- `0x180014240`
- `0x180021da8`
- `0x18003a860`
- `0x18003b294`
- `0x18003b73c`
- `0x18003b8f0`
- `0x18003ba3c`
- `0x18003bbe8`
- `0x180041d90`
- `0x18004395c`
- `0x180053350`
- `0x180053df8`
- `0x180057c8c`
- `0x1800580e8`
- `0x1800581a8`
- `0x1800597b0`
- `0x18005a160`
- `0x18005ef44`
- `0x180088a30`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008eddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008eddd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003adc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003b283`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003adc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003b283`
- `ntdll!NtSetInformationThread` at `0x18003aa50`
- `ntdll!NtSetInformationThread` at `0x18003aa50`
- `ntdll!RtlNtStatusToDosError` at `0x18003aa5b`
- `ntdll!RtlNtStatusToDosError` at `0x18008ed1a`
- `ntdll!RtlNtStatusToDosError` at `0x18003aa5b`
- `ntdll!RtlNtStatusToDosError` at `0x18008ed1a`
- `CRYPT32!CertFreeCertificateContext` at `0x18003ae5b`
- `CRYPT32!CertFreeCertificateContext` at `0x18003ae5b`
- `CRYPT32!CertOpenServerOcspResponse` at `0x18008edad`
- `CRYPT32!CertOpenServerOcspResponse` at `0x18008edad`
- `CRYPT32!CertGetPublicKeyLength` at `0x18003afd4`
- `CRYPT32!CertGetPublicKeyLength` at `0x18003afd4`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003a986`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003a986`
- `CRYPT32!CertGetCertificateChain` at `0x18003aae2`
- `CRYPT32!CertGetCertificateChain` at `0x18003aae2`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18003ab55`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18003ab55`
- `bcrypt!BCryptHash` at `0x18003a9e8`
- `bcrypt!BCryptHash` at `0x18003a9e8`

## pseudocode

```c
__int64 __fastcall CSslCredential::CreateCredential(
        CSslCredential *this,
        int a2,
        const unsigned __int16 *a3,
        void *a4,
        struct LSA_SCHANNEL_SUB_CRED *a5,
        char a6,
        unsigned __int8 a7,
        int a8,
        struct _TLS_PARAMETERS *a9,
        unsigned int a10)
{
  BOOL v14; // r13d
  __int64 v15; // rcx
  _WORD *v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // rcx
  CCipherMill *v19; // rcx
  const struct _CERT_CONTEXT *v20; // rax
  void **v21; // rbx
  ULONG PublicKeyFromCert; // esi
  NTSTATUS v23; // esi
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  NTSTATUS v27; // eax
  NTSTATUS v28; // r13d
  void *v29; // r14
  const struct _CERT_CHAIN_CONTEXT **v30; // r12
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  char v34; // al
  int v35; // r8d
  int v36; // r9d
  CCipherMill *v37; // rcx
  DWORD dwError; // eax
  unsigned __int8 v39; // r15
  CCipherMill *v40; // rcx
  const struct _CERT_CONTEXT *v41; // rcx
  CCipherMill *v42; // rcx
  DWORD LastError; // eax
  DWORD v45; // eax
  enum _eTlsSignatureAlgorithm v46; // r8d
  struct CEccCurveInfo *v47; // rdx
  unsigned __int8 v48; // cl
  unsigned __int8 v49; // al
  unsigned int *v50; // r9
  const CERT_CONTEXT *v51; // rcx
  __int64 v52; // rdx
  DWORD PublicKeyLength; // eax
  DWORD v54; // eax
  DWORD v55; // eax
  ULONG v56; // eax
  struct _CERT_SERVER_OCSP_RESPONSE_OPEN_PARA *p_pOpenPara; // r8
  HCERT_SERVER_OCSP_RESPONSE v58; // rax
  DWORD v59; // eax
  unsigned __int8 pChainPara; // [rsp+20h] [rbp-168h]
  struct CEccCurveInfo *v61; // [rsp+60h] [rbp-128h] BYREF
  struct CEccCurveInfo *v62; // [rsp+68h] [rbp-120h]
  struct _TLS_PARAMETERS *v63; // [rsp+70h] [rbp-118h]
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+78h] [rbp-110h] BYREF
  int v65[4]; // [rsp+88h] [rbp-100h] BYREF
  __int64 v66; // [rsp+98h] [rbp-F0h]
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+A0h] [rbp-E8h] BYREF
  _CERT_SERVER_OCSP_RESPONSE_OPEN_PARA pOpenPara; // [rsp+B8h] [rbp-D0h] BYREF
  struct _CERT_CHAIN_PARA v69; // [rsp+E0h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR ThreadInformation; // [rsp+140h] [rbp-48h] BYREF

  v63 = a9;
  memset_0(&v69, 0, 0x60u);
  v14 = 0;
  *((_DWORD *)this + 163) = a2;
  v62 = 0;
  v61 = 0;
  v66 = 0;
  pPolicyPara = 0;
  *(_OWORD *)v65 = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  if ( a3 )
  {
    v15 = 2147483646;
    v16 = (_WORD *)((char *)this + 656);
    v17 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*a3 )
        break;
      *v16++ = *a3++;
      --v15;
      --v17;
    }
    while ( v17 );
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
    goto LABEL_9;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids);
LABEL_9:
    v19 = WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 648) )
    return 14;
  if ( a5 )
  {
    if ( (*((_BYTE *)a5 + 48) & 1) != 0 )
      *((_DWORD *)this + 6) |= 0x20u;
    v20 = CertDuplicateCertificateContext(*(PCCERT_CONTEXT *)a5);
    *((_QWORD *)this + 4) = v20;
    if ( !v20 )
    {
      *((_DWORD *)this + 18) = 10004;
      LastError = GetLastError();
      PublicKeyFromCert = LastError;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids, LastError);
      v21 = (void **)((char *)this + 432);
      goto LABEL_58;
    }
    v21 = (void **)((char *)this + 432);
    PublicKeyFromCert = GetPublicKeyFromCert(
                          v20,
                          (struct _PUBLICKEY **)this + 54,
                          (enum _eTlsSignatureAlgorithm *)this + 33);
    if ( PublicKeyFromCert )
    {
      *((_DWORD *)this + 18) = 10005;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_74;
      v52 = 16;
LABEL_120:
      WPP_SF_d(*((_QWORD *)v40 + 2), v52, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids, PublicKeyFromCert);
      goto LABEL_74;
    }
    v23 = BCryptHash(
            49,
            0,
            0,
            *(_QWORD *)(*((_QWORD *)this + 4) + 8LL),
            *(_DWORD *)(*((_QWORD *)this + 4) + 16LL),
            (char *)this + 40,
            20);
    if ( v23 < 0 )
    {
      *((_DWORD *)this + 18) = 10016;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_85d23bd63ce93039b989ce8bab889993_Traceguids,
          (unsigned int)v23);
      v56 = RtlNtStatusToDosError(v23);
    }
    else
    {
      PublicKeyFromCert = CSslCredential::GetPrivateFromCert(this, a4, a5);
      if ( PublicKeyFromCert )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_85d23bd63ce93039b989ce8bab889993_Traceguids,
            PublicKeyFromCert);
        *((_BYTE *)this + 76) = 1;
        goto LABEL_74;
      }
      if ( *((_BYTE *)this + 79) )
      {
        PublicKeyFromCert = GetCertEndpointBindings(
                              *((const struct _CERT_CONTEXT **)this + 4),
                              (unsigned __int8 **)this + 58,
                              (unsigned int *)this + 118);
        if ( PublicKeyFromCert )
        {
          *((_DWORD *)this + 18) = 10015;
          v40 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_74;
          }
          v52 = 19;
          goto LABEL_120;
        }
      }
      ThreadInformation.Ptr = (ULONGLONG)a4;
      if ( LsaTable )
      {
        v27 = a4
            ? NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u)
            : (*(__int64 (**)(void))(LsaTable + 88))();
        v28 = v27;
        PublicKeyFromCert = RtlNtStatusToDosError(v27);
        v14 = v28 >= 0;
        if ( PublicKeyFromCert )
          goto LABEL_74;
      }
      if ( *((_DWORD *)this + 33) != 3 )
        goto LABEL_24;
      PublicKeyLength = CertGetPublicKeyLength(
                          1u,
                          (PCERT_PUBLIC_KEY_INFO)(*(_QWORD *)(*((_QWORD *)this + 4) + 24LL) + 96LL));
      *((_DWORD *)this + 34) = PublicKeyLength;
      if ( PublicKeyLength )
      {
        PublicKeyFromCert = CertGetEccCurveType(*((_QWORD *)this + 4), (char *)this + 140);
        if ( PublicKeyFromCert )
        {
          *((_DWORD *)this + 18) = 10006;
          goto LABEL_74;
        }
LABEL_24:
        if ( (a6 & 1) != 0 || (v29 = 0, a8) )
          v29 = *(void **)(*((_QWORD *)this + 4) + 32LL);
        if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v24, (int)&ChainBuildStart, v25, v26, &ThreadInformation);
        v30 = (const struct _CERT_CHAIN_CONTEXT **)((char *)this + 64);
        if ( !CertGetCertificateChain(
                0,
                *((PCCERT_CONTEXT *)this + 4),
                0,
                v29,
                &v69,
                a6 & 4,
                0,
                (PCCERT_CHAIN_CONTEXT *)this + 8) )
        {
          if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(v31, (int)&ChainBuildStop, v32, v33, &ThreadInformation);
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v54 = GetLastError();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              WPP_85d23bd63ce93039b989ce8bab889993_Traceguids,
              v54,
              a6 & 4);
          }
          *v30 = 0;
          v45 = GetLastError();
          LogGetCertificateChainFailureEvent(
            *((_DWORD *)this + 163),
            (const unsigned __int16 *)this + 328,
            *((_BYTE *)this + 79),
            *((const struct _CERT_CONTEXT **)this + 4),
            v45,
            a6 & 4);
LABEL_43:
          if ( v14 )
          {
            RevertToSelf();
            v14 = 0;
          }
          if ( *((_BYTE *)this + 79) )
          {
            v37 = (CCipherMill *)*v30;
            if ( *v30 )
            {
              if ( (a6 & 0x10) == 0 )
              {
                p_pOpenPara = 0;
                memset(&pOpenPara, 0, sizeof(pOpenPara));
                if ( g_pszOcspReadDirectory )
                {
                  pOpenPara.cbSize = 40;
                  p_pOpenPara = &pOpenPara;
                  pOpenPara.dwFlags = 1;
                  pOpenPara.pwszOcspDirectory = (PWSTR)g_pszOcspReadDirectory;
                }
                v58 = CertOpenServerOcspResponse((PCCERT_CHAIN_CONTEXT)v37, 1u, p_pOpenPara);
                *((_QWORD *)this + 57) = v58;
                if ( !v58
                  && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v59 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    23,
                    WPP_85d23bd63ce93039b989ce8bab889993_Traceguids,
                    v59);
                }
              }
            }
          }
          v39 = (a6 & 8) != 0;
          PublicKeyFromCert = SerializeCertChain(
                                (unsigned int)v37,
                                *((const struct _CERT_CONTEXT **)this + 4),
                                *v30,
                                v39,
                                (unsigned __int8 **)this + 55,
                                (unsigned int *)this + 112);
          if ( PublicKeyFromCert )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_85d23bd63ce93039b989ce8bab889993_Traceguids,
                PublicKeyFromCert);
            }
            *((_DWORD *)this + 18) = 10007;
            goto LABEL_74;
          }
          if ( *((_DWORD *)this + 112) > 0x4000u )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids);
            }
            *((_DWORD *)this + 18) = 10008;
            PublicKeyFromCert = 87;
            goto LABEL_74;
          }
          PublicKeyFromCert = CSslCredential::FillInCredStructWithCertInfo(this);
          if ( PublicKeyFromCert )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                WPP_85d23bd63ce93039b989ce8bab889993_Traceguids,
                PublicKeyFromCert);
            }
            *((_DWORD *)this + 18) = 10009;
            goto LABEL_74;
          }
          CTlsSignatureSuiteList::SetCertificateChainSignatureSuites(
            (CSslCredential *)((char *)this + 512),
            *((const struct _CERT_CONTEXT **)this + 4),
            *v30,
            v39);
          v41 = (const struct _CERT_CONTEXT *)*((_QWORD *)this + 4);
          LODWORD(ThreadInformation.Ptr) = 64;
          PublicKeyFromCert = GetCngHashAndSignatureString(
                                v41,
                                (unsigned __int16 *)this + 136,
                                (unsigned int *)&ThreadInformation,
                                (unsigned __int16 *)this + 72,
                                pChainPara);
          if ( PublicKeyFromCert )
          {
            *((_WORD *)this + 72) = 0;
            *((_WORD *)this + 136) = 0;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids);
            }
          }
          else
          {
            *((_BYTE *)this + 80) = wcscmp_0((const wchar_t *)this + 72, L"SHA1") == 0;
          }
          if ( !a10 )
            goto LABEL_58;
          v46 = *((_DWORD *)this + 33);
          if ( v46 == TlsSignatureAlgorithm_Ecdsa )
          {
            PublicKeyFromCert = CCipherMill::GetCurveInfo(v42, *((_DWORD *)this + 35), &v61);
            if ( PublicKeyFromCert )
            {
              *((_DWORD *)this + 18) = 10018;
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids);
              }
              goto LABEL_74;
            }
            v46 = *((_DWORD *)this + 33);
            v47 = v61;
          }
          else
          {
            v47 = v62;
          }
          v48 = *((_BYTE *)this + 79);
          if ( v48 && v46 == TlsSignatureAlgorithm_Rsa )
          {
            v49 = 1;
          }
          else
          {
            v49 = 0;
            v50 = (unsigned int *)((char *)this + 136);
            if ( v46 == TlsSignatureAlgorithm_Ecdsa )
              goto LABEL_72;
          }
          v50 = (unsigned int *)((char *)this + 428);
LABEL_72:
          if ( IsCertificateBlacklisted(
                 v63,
                 a10,
                 v46,
                 *v50,
                 v47,
                 v49,
                 v48,
                 (const unsigned __int16 *)this + 72,
                 (const unsigned __int16 *)this + 136,
                 0,
                 1u) )
          {
            PublicKeyFromCert = -2146893007;
            *((_DWORD *)this + 18) = 10018;
            goto LABEL_74;
          }
LABEL_58:
          if ( !PublicKeyFromCert )
          {
LABEL_59:
            if ( v14 )
              RevertToSelf();
            return PublicKeyFromCert;
          }
LABEL_74:
          v51 = (const CERT_CONTEXT *)*((_QWORD *)this + 4);
          if ( v51 )
          {
            CertFreeCertificateContext(v51);
            *((_QWORD *)this + 4) = 0;
          }
          if ( *v21 )
          {
            SPExternalFree(*v21);
            *v21 = 0;
          }
          goto LABEL_59;
        }
        v34 = Microsoft_Windows_Schannel_EventsEnableBits;
        if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
        {
          McGenEventWrite_EventWriteTransfer(v31, (int)&ChainBuildStop, v32, v33, &ThreadInformation);
          v34 = Microsoft_Windows_Schannel_EventsEnableBits;
        }
        v65[0] = 24;
        pPolicyPara.pvExtraPolicyPara = v65;
        v65[1] = 2;
        v65[2] = 640;
        pPolicyPara.cbSize = 16;
        if ( (v34 & 1) != 0 )
          McGenEventWrite_EventWriteTransfer((int)v65, (int)&ChainVerifyStart, v32, v33, &ThreadInformation);
        if ( !CertVerifyCertificateChainPolicy((LPCSTR)4, *v30, &pPolicyPara, &pPolicyStatus) )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_35;
          }
          v55 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids, v55);
        }
        v37 = WPP_GLOBAL_Control;
LABEL_35:
        if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
        {
          McGenEventWrite_EventWriteTransfer((int)v37, (int)&ChainVerifyStop, v35, v36, &ThreadInformation);
          v37 = WPP_GLOBAL_Control;
        }
        dwError = pPolicyStatus.dwError;
        if ( pPolicyStatus.dwError )
        {
          if ( v37 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v37 + 2), 22, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids, pPolicyStatus.dwError);
            dwError = pPolicyStatus.dwError;
          }
          LODWORD(v37) = -2146762486;
          if ( dwError == -2146762486 )
            LogIncompleteCertificateChainEvent(
              *((_DWORD *)this + 163),
              (const unsigned __int16 *)this + 328,
              *((_BYTE *)this + 79),
              *((const struct _CERT_CONTEXT **)this + 4),
              0x800B010A);
        }
        goto LABEL_43;
      }
      *((_DWORD *)this + 18) = 10006;
      v56 = GetLastError();
    }
    PublicKeyFromCert = v56;
    goto LABEL_58;
  }
  if ( v19 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)v19 + 2), 14, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids);
  return 87;
}

```

## disassembly

```asm
0x18003a860  mov     [rsp+arg_8], rbx
0x18003a865  mov     [rsp+arg_10], rsi
0x18003a86a  push    rdi
0x18003a86b  push    r12
0x18003a86d  push    r13
0x18003a86f  push    r14
0x18003a871  push    r15
0x18003a873  sub     rsp, 160h
0x18003a87a  mov     rax, cs:__security_cookie
0x18003a881  xor     rax, rsp
0x18003a884  mov     [rsp+188h+var_38], rax
0x18003a88c  mov     rax, [rsp+188h+arg_40]
0x18003a894  mov     ebx, edx
0x18003a896  mov     r14, [rsp+188h+arg_20]
0x18003a89e  xor     edx, edx; Val
0x18003a8a0  mov     rsi, r8
0x18003a8a3  mov     [rsp+188h+var_118], rax
0x18003a8a8  mov     rdi, rcx
0x18003a8ab  mov     r15, r9
0x18003a8ae  lea     rcx, [rsp+188h+var_A8]; void *
0x18003a8b6  lea     r8d, [rdx+60h]; Size
0x18003a8ba  call    memset_0
0x18003a8bf  xor     r13d, r13d
0x18003a8c2  mov     [rdi+28Ch], ebx
0x18003a8c8  lea     r12, WPP_85d23bd63ce93039b989ce8bab889993_Traceguids
0x18003a8cf  mov     eax, r13d
0x18003a8d2  mov     [rsp+188h+var_120], rax
0x18003a8d7  xorps   xmm0, xmm0
0x18003a8da  mov     [rsp+188h+var_128], rax
0x18003a8df  xorps   xmm1, xmm1
0x18003a8e2  mov     [rsp+188h+var_F0], rax
0x18003a8ea  lea     rbx, WPP_GLOBAL_Control
0x18003a8f1  mov     [rsp+188h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18003a8f9  movups  xmmword ptr [rsp+188h+pPolicyPara.cbSize], xmm0
0x18003a8fe  movups  xmmword ptr [rsp+188h+var_100], xmm1
0x18003a906  movups  xmmword ptr [rsp+188h+pPolicyStatus.cbSize], xmm0
0x18003a90e  test    rsi, rsi
0x18003a911  jz      loc_18003AE7C
0x18003a917  mov     ecx, 7FFFFFFEh
0x18003a91c  lea     rax, [rdi+290h]
0x18003a923  mov     edx, 104h
0x18003a928  test    rcx, rcx
0x18003a92b  jz      short loc_18003A94C
0x18003a92d  movzx   r8d, word ptr [rsi]
0x18003a931  test    r8w, r8w
0x18003a935  jz      short loc_18003A94C
0x18003a937  mov     [rax], r8w
0x18003a93b  add     rsi, 2
0x18003a93f  add     rax, 2
0x18003a943  dec     rcx
0x18003a946  sub     rdx, 1
0x18003a94a  jnz     short loc_18003A928
0x18003a94c  test    rdx, rdx
0x18003a94f  lea     rcx, [rax-2]
0x18003a953  cmovnz  rcx, rax
0x18003a957  mov     [rcx], r13w
0x18003a95b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a962  cmp     [rdi+288h], r13b
0x18003a969  jz      loc_18003AEAC
0x18003a96f  test    r14, r14
0x18003a972  jz      loc_18003AEB6
0x18003a978  test    byte ptr [r14+30h], 1
0x18003a97d  jnz     loc_18003AEE0
0x18003a983  mov     rcx, [r14]; pCertContext
0x18003a986  call    cs:__imp_CertDuplicateCertificateContext
0x18003a98c  mov     [rdi+20h], rax
0x18003a990  test    rax, rax
0x18003a993  jz      loc_18003AD42
0x18003a999  lea     r12, [rdi+84h]
0x18003a9a0  mov     rcx, rax; struct _CERT_CONTEXT *
0x18003a9a3  lea     rbx, [rdi+1B0h]
0x18003a9aa  mov     r8, r12; enum _eTlsSignatureAlgorithm *
0x18003a9ad  mov     rdx, rbx; struct _PUBLICKEY **
0x18003a9b0  call    ?GetPublicKeyFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_PUBLICKEY@@PEAW4_eTlsSignatureAlgorithm@@@Z; GetPublicKeyFromCert(_CERT_CONTEXT const *,_PUBLICKEY * *,_eTlsSignatureAlgorithm *)
0x18003a9b5  mov     esi, eax
0x18003a9b7  test    eax, eax
0x18003a9b9  jnz     loc_18003AF0C
0x18003a9bf  mov     r9, [rdi+20h]
0x18003a9c3  lea     rax, [rdi+28h]
0x18003a9c7  mov     dword ptr [rsp+188h+pvReserved], 14h
0x18003a9cf  lea     ecx, [rsi+31h]
0x18003a9d2  mov     qword ptr [rsp+188h+dwFlags], rax
0x18003a9d7  xor     r8d, r8d
0x18003a9da  xor     edx, edx
0x18003a9dc  mov     eax, [r9+10h]
0x18003a9e0  mov     r9, [r9+8]
0x18003a9e4  mov     dword ptr [rsp+188h+pChainPara], eax
0x18003a9e8  call    cs:__imp_BCryptHash
0x18003a9ee  mov     esi, eax
0x18003a9f0  test    eax, eax
0x18003a9f2  js      loc_18003AF3E
0x18003a9f8  mov     r8, r14; struct LSA_SCHANNEL_SUB_CRED *
0x18003a9fb  mov     rdx, r15; void *
0x18003a9fe  mov     rcx, rdi; this
0x18003aa01  call    ?GetPrivateFromCert@CSslCredential@@AEAAKPEAXPEAULSA_SCHANNEL_SUB_CRED@@@Z; CSslCredential::GetPrivateFromCert(void *,LSA_SCHANNEL_SUB_CRED *)
0x18003aa06  mov     esi, eax
0x18003aa08  test    eax, eax
0x18003aa0a  jnz     loc_18003AF84
0x18003aa10  cmp     [rdi+4Fh], r13b
0x18003aa14  jnz     loc_18003AC11
0x18003aa1a  mov     rax, cs:LsaTable
0x18003aa21  mov     qword ptr [rsp+188h+ThreadInformation], r15
0x18003aa29  test    rax, rax
0x18003aa2c  jz      short loc_18003AA72
0x18003aa2e  test    r15, r15
0x18003aa31  jz      loc_18003AE6E
0x18003aa37  mov     r9d, 8; ThreadInformationLength
0x18003aa3d  lea     r8, [rsp+188h+ThreadInformation]; ThreadInformation
0x18003aa45  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003aa4c  lea     edx, [r9-3]; ThreadInformationClass
0x18003aa50  call    cs:__imp_NtSetInformationThread
0x18003aa56  mov     ecx, eax; Status
0x18003aa58  mov     r13d, eax
0x18003aa5b  call    cs:__imp_RtlNtStatusToDosError
0x18003aa61  not     r13d
0x18003aa64  mov     esi, eax
0x18003aa66  shr     r13d, 1Fh
0x18003aa6a  test    eax, eax
0x18003aa6c  jnz     loc_18003AE4E
0x18003aa72  cmp     dword ptr [r12], 3
0x18003aa77  jz      loc_18003AFC3
0x18003aa7d  mov     r15d, dword ptr [rsp+188h+arg_28]
0x18003aa85  test    r15b, 1
0x18003aa89  jnz     loc_18003B00E
0x18003aa8f  xor     r14d, r14d
0x18003aa92  cmp     [rsp+188h+arg_38], r14d
0x18003aa9a  jnz     loc_18003B00E
0x18003aaa0  mov     esi, r15d
0x18003aaa3  and     esi, 4
0x18003aaa6  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18003aaad  jnz     loc_18003B01B
0x18003aab3  mov     rdx, [rdi+20h]; pCertContext
0x18003aab7  lea     rax, [rsp+188h+var_A8]
0x18003aabf  lea     r12, [rdi+40h]
0x18003aac3  mov     r9, r14; hAdditionalStore
0x18003aac6  mov     [rsp+188h+ppChainContext], r12; ppChainContext
0x18003aacb  xor     r8d, r8d; pTime
0x18003aace  mov     [rsp+188h+pvReserved], 0; pvReserved
0x18003aad7  xor     ecx, ecx; hChainEngine
0x18003aad9  mov     [rsp+188h+dwFlags], esi; dwFlags
0x18003aadd  mov     [rsp+188h+pChainPara], rax; pChainPara
0x18003aae2  call    cs:__imp_CertGetCertificateChain
0x18003aae8  test    eax, eax
0x18003aaea  jz      loc_18003AD6A
0x18003aaf0  mov     eax, cs:Microsoft_Windows_Schannel_EventsEnableBits
0x18003aaf6  test    al, 1
0x18003aaf8  jnz     loc_18003B08F
0x18003aafe  mov     [rsp+188h+var_100], 18h
0x18003ab09  lea     rcx, [rsp+188h+var_100]; int
0x18003ab11  mov     [rsp+188h+pPolicyPara.pvExtraPolicyPara], rcx
0x18003ab19  mov     [rsp+188h+var_100+4], 2
0x18003ab24  mov     [rsp+188h+var_100+8], 280h
0x18003ab2f  mov     [rsp+188h+pPolicyPara.cbSize], 10h
0x18003ab37  test    al, 1
0x18003ab39  jnz     loc_18003B0B3
0x18003ab3f  mov     rdx, [r12]; pChainContext
0x18003ab43  lea     r9, [rsp+188h+pPolicyStatus]; pPolicyStatus
0x18003ab4b  lea     r8, [rsp+188h+pPolicyPara]; pPolicyPara
0x18003ab50  mov     ecx, 4; pszPolicyOID
0x18003ab55  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18003ab5b  test    eax, eax
0x18003ab5d  jz      loc_18003B0D1
0x18003ab63  lea     r14, WPP_GLOBAL_Control
0x18003ab6a  mov     rcx, cs:WPP_GLOBAL_Control; int
0x18003ab71  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18003ab78  jnz     loc_18003B11C
0x18003ab7e  mov     eax, [rsp+188h+pPolicyStatus.dwError]
0x18003ab85  test    eax, eax
0x18003ab87  jz      short loc_18003ABA5
0x18003ab89  cmp     rcx, r14
0x18003ab8c  jz      short loc_18003AB98
0x18003ab8e  test    byte ptr [rcx+1Ch], 1
0x18003ab92  jnz     loc_18003B141
0x18003ab98  mov     ecx, 800B010Ah; unsigned int
0x18003ab9d  cmp     eax, ecx
0x18003ab9f  jz      loc_18003B165
0x18003aba5  test    r13d, r13d
0x18003aba8  jnz     loc_18003ADC3
0x18003abae  cmp     byte ptr [rdi+4Fh], 0
0x18003abb2  jnz     loc_18008ED3F
0x18003abb8  mov     r8, [r12]; struct _CERT_CHAIN_CONTEXT *
0x18003abbc  lea     rax, [rdi+1B8h]
0x18003abc3  mov     rdx, [rdi+20h]; struct _CERT_CONTEXT *
0x18003abc7  lea     r14, [rdi+1C0h]
0x18003abce  shr     r15d, 3
0x18003abd2  and     r15b, 1
0x18003abd6  mov     qword ptr [rsp+188h+dwFlags], r14; unsigned int *
0x18003abdb  mov     r9b, r15b; unsigned __int8
0x18003abde  mov     [rsp+188h+pChainPara], rax; unsigned __int8
0x18003abe3  call    ?SerializeCertChain@@YAKKPEBU_CERT_CONTEXT@@PEBU_CERT_CHAIN_CONTEXT@@EPEAPEAEPEAK@Z; SerializeCertChain(ulong,_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,uchar,uchar * *,ulong *)
0x18003abe8  mov     esi, eax
0x18003abea  test    eax, eax
0x18003abec  jz      short loc_18003AC5F
0x18003abee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003abf5  lea     rax, WPP_GLOBAL_Control
0x18003abfc  cmp     rcx, rax
0x18003abff  jnz     loc_18003B188
0x18003ac05  mov     dword ptr [rdi+48h], 2717h
0x18003ac0c  jmp     loc_18003AE4E
0x18003ac11  mov     rcx, [rdi+20h]; struct _CERT_CONTEXT *
0x18003ac15  lea     r8, [rdi+1D8h]; unsigned int *
0x18003ac1c  lea     rdx, [rdi+1D0h]; unsigned __int8 **
0x18003ac23  call    ?GetCertEndpointBindings@@YAKPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; GetCertEndpointBindings(_CERT_CONTEXT const *,uchar * *,ulong *)
0x18003ac28  mov     esi, eax
0x18003ac2a  test    eax, eax
0x18003ac2c  jz      loc_18003AA1A
0x18003ac32  mov     dword ptr [rdi+48h], 271Fh
0x18003ac39  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac40  lea     rax, WPP_GLOBAL_Control
0x18003ac47  cmp     rcx, rax
0x18003ac4a  jz      loc_18003AE4E
0x18003ac50  test    byte ptr [rcx+1Ch], 1
0x18003ac54  jnz     loc_18008ECFA
0x18003ac5a  jmp     loc_18003AE4E
0x18003ac5f  cmp     dword ptr [r14], 4000h
0x18003ac66  ja      loc_18003B1AF
0x18003ac6c  mov     rcx, rdi; this
0x18003ac6f  call    ?FillInCredStructWithCertInfo@CSslCredential@@QEAAKXZ; CSslCredential::FillInCredStructWithCertInfo(void)
0x18003ac74  mov     esi, eax
0x18003ac76  test    eax, eax
0x18003ac78  jnz     loc_18003B1EB
0x18003ac7e  mov     r8, [r12]; struct _CERT_CHAIN_CONTEXT *
0x18003ac82  lea     rcx, [rdi+200h]; this
0x18003ac89  mov     rdx, [rdi+20h]; struct _CERT_CONTEXT *
0x18003ac8d  mov     r9b, r15b; unsigned __int8
0x18003ac90  call    ?SetCertificateChainSignatureSuites@CTlsSignatureSuiteList@@QEAAXPEBU_CERT_CONTEXT@@PEBU_CERT_CHAIN_CONTEXT@@E@Z; CTlsSignatureSuiteList::SetCertificateChainSignatureSuites(_CERT_CONTEXT const *,_CERT_CHAIN_CONTEXT const *,uchar)
0x18003ac95  mov     rcx, [rdi+20h]; struct _CERT_CONTEXT *
0x18003ac99  lea     r15, [rdi+90h]
0x18003aca0  lea     r12, [rdi+110h]
0x18003aca7  mov     dword ptr [rsp+188h+ThreadInformation], 40h ; '@'
0x18003acb2  mov     r9, r15; unsigned __int16 *
0x18003acb5  lea     r8, [rsp+188h+ThreadInformation]; unsigned int *
0x18003acbd  mov     rdx, r12; unsigned __int16 *
0x18003acc0  call    ?GetCngHashAndSignatureString@@YAKPEBU_CERT_CONTEXT@@PEAGPEAK1E@Z; GetCngHashAndSignatureString(_CERT_CONTEXT const *,ushort *,ulong *,ushort *,uchar)
0x18003acc5  mov     esi, eax
0x18003acc7  test    eax, eax
0x18003acc9  jz      loc_18003B24E
0x18003accf  xor     eax, eax
0x18003acd1  mov     [r15], ax
0x18003acd5  mov     [r12], ax
0x18003acda  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18003ace1  lea     rax, WPP_GLOBAL_Control
0x18003ace8  cmp     rcx, rax
0x18003aceb  jnz     loc_18003B22A
0x18003acf1  mov     r14d, [rsp+188h+arg_48]
0x18003acf9  test    r14d, r14d
0x18003acfc  jnz     loc_18003ADD1
0x18003ad02  test    esi, esi
0x18003ad04  jnz     loc_18003AE4E
0x18003ad0a  test    r13d, r13d
0x18003ad0d  jnz     loc_18003B283
0x18003ad13  mov     eax, esi
0x18003ad15  mov     rcx, [rsp+188h+var_38]
0x18003ad1d  xor     rcx, rsp; StackCookie
0x18003ad20  call    __security_check_cookie
0x18003ad25  lea     r11, [rsp+188h+var_28]
0x18003ad2d  mov     rbx, [r11+38h]
0x18003ad31  mov     rsi, [r11+40h]
0x18003ad35  mov     rsp, r11
0x18003ad38  pop     r15
0x18003ad3a  pop     r14
0x18003ad3c  pop     r13
0x18003ad3e  pop     r12
0x18003ad40  pop     rdi
0x18003ad41  retn
0x18003ad42  mov     dword ptr [rdi+48h], 2714h
0x18003ad49  call    cs:__imp_GetLastError
0x18003ad4f  mov     esi, eax
0x18003ad51  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad58  cmp     rcx, rbx
0x18003ad5b  jnz     loc_18003AEE9
0x18003ad61  lea     rbx, [rdi+1B0h]
0x18003ad68  jmp     short loc_18003AD02
0x18003ad6a  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18003ad71  jnz     loc_18003B039
0x18003ad77  mov     rax, cs:WPP_GLOBAL_Control
0x18003ad7e  lea     r14, WPP_GLOBAL_Control
0x18003ad85  cmp     rax, r14
0x18003ad88  jnz     loc_18003B057
0x18003ad8e  mov     qword ptr [r12], 0
0x18003ad96  call    cs:__imp_GetLastError
0x18003ad9c  mov     r9, [rdi+20h]; struct _CERT_CONTEXT *
0x18003ada0  lea     rdx, [rdi+290h]; unsigned __int16 *
0x18003ada7  mov     r8b, [rdi+4Fh]; unsigned __int8
0x18003adab  mov     ecx, [rdi+28Ch]; unsigned int
0x18003adb1  mov     [rsp+188h+dwFlags], esi; unsigned int
0x18003adb5  mov     dword ptr [rsp+188h+pChainPara], eax; unsigned int
0x18003adb9  call    ?LogGetCertificateChainFailureEvent@@YAXKPEBGEPEBU_CERT_CONTEXT@@KK@Z; LogGetCertificateChainFailureEvent(ulong,ushort const *,uchar,_CERT_CONTEXT const *,ulong,ulong)
0x18003adbe  jmp     loc_18003ABA5
0x18003adc3  call    cs:__imp_RevertToSelf
0x18003adc9  xor     r13d, r13d
0x18003adcc  jmp     loc_18003ABAE
0x18003add1  mov     r8d, [rdi+84h]; enum _eTlsSignatureAlgorithm
0x18003add8  cmp     r8d, 3
0x18003addc  jz      loc_18008EE25
0x18003ade2  mov     rdx, [rsp+188h+var_120]
0x18003ade7  mov     cl, [rdi+4Fh]
0x18003adea  test    cl, cl
0x18003adec  jnz     loc_18003B26A
0x18003adf2  xor     eax, eax
  ... truncated ...
```
