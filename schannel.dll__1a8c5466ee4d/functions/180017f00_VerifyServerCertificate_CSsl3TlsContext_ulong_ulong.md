# VerifyServerCertificate(CSsl3TlsContext *,ulong,ulong)

- ea: `0x180017f00`
- end: `0x180018a1f`
- name: `?VerifyServerCertificate@@YAJPEAVCSsl3TlsContext@@KK@Z`
- size: `2847`
- prototype: `__int64 __fastcall(struct CSsl3TlsContext *, DWORD, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018a30`

## callees

- `0x180011054`
- `0x1800165a4`
- `0x180017f00`
- `0x1800214f0`
- `0x180021da8`
- `0x18004bca4`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f1e4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001856b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001866f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001856b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001866f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b5e4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800184da`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800184da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800184fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800184fb`
- `ntdll!NtSetInformationThread` at `0x180018256`
- `ntdll!NtSetInformationThread` at `0x180018256`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800183b0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800183b0`
- `ntdll!RtlReleaseResource` at `0x180018207`
- `ntdll!RtlReleaseResource` at `0x1800183e2`
- `ntdll!RtlReleaseResource` at `0x180018445`
- `ntdll!RtlReleaseResource` at `0x180018207`
- `ntdll!RtlReleaseResource` at `0x1800183e2`
- `ntdll!RtlReleaseResource` at `0x180018445`
- `ntdll!RtlAcquireResourceShared` at `0x18001800c`
- `ntdll!RtlAcquireResourceShared` at `0x18001800c`
- `ntdll!RtlInitUnicodeString` at `0x180018612`
- `ntdll!RtlInitUnicodeString` at `0x18008b694`
- `ntdll!RtlInitUnicodeString` at `0x18008b6a4`
- `ntdll!RtlInitUnicodeString` at `0x18008b7b4`
- `ntdll!RtlInitUnicodeString` at `0x180018612`
- `ntdll!RtlInitUnicodeString` at `0x18008b694`
- `ntdll!RtlInitUnicodeString` at `0x18008b6a4`
- `ntdll!RtlInitUnicodeString` at `0x18008b7b4`
- `ntdll!RtlNtStatusToDosError` at `0x18001826b`
- `ntdll!RtlNtStatusToDosError` at `0x18001826b`
- `CRYPT32!CertOpenStore` at `0x180018066`
- `CRYPT32!CertOpenStore` at `0x180018066`
- `CRYPT32!CertCloseStore` at `0x180018184`
- `CRYPT32!CertCloseStore` at `0x1800184af`
- `CRYPT32!CertCloseStore` at `0x180018530`
- `CRYPT32!CertCloseStore` at `0x180018184`
- `CRYPT32!CertCloseStore` at `0x1800184af`
- `CRYPT32!CertCloseStore` at `0x180018530`
- `CRYPT32!CertFreeCertificateContext` at `0x180018143`
- `CRYPT32!CertFreeCertificateContext` at `0x180018544`
- `CRYPT32!CertFreeCertificateContext` at `0x18001869c`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b5d2`
- `CRYPT32!CertFreeCertificateContext` at `0x180018143`
- `CRYPT32!CertFreeCertificateContext` at `0x180018544`
- `CRYPT32!CertFreeCertificateContext` at `0x18001869c`
- `CRYPT32!CertFreeCertificateContext` at `0x18008b5d2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800180fa`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800180fa`
- `CRYPT32!CertGetCertificateChain` at `0x1800182e1`
- `CRYPT32!CertGetCertificateChain` at `0x1800182e1`
- `CRYPT32!CertFreeCertificateChain` at `0x18001874b`
- `CRYPT32!CertFreeCertificateChain` at `0x18001874b`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180018366`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180018366`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800180d4`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800180d4`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018129`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018647`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800186b6`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018129`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180018647`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800186b6`

## pseudocode

```c
__int64 __fastcall VerifyServerCertificate(struct CSsl3TlsContext *a1, DWORD a2, int a3)
{
  __int64 v4; // r15
  __int64 v5; // rax
  int v6; // edi
  __int64 v7; // rax
  unsigned int v8; // edi
  PCCERT_CONTEXT v9; // r13
  const BYTE *v10; // r14
  HCERTSTORE v11; // r12
  int v12; // r13d
  __int64 v13; // rsi
  unsigned int v14; // edi
  DWORD LastError; // esi
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  const CERT_CONTEXT *v22; // rcx
  int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  __int64 v29; // r9
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  DWORD dwErrorStatus; // edx
  __int64 v34; // rcx
  DWORD dwError; // edi
  DWORD v37; // eax
  __int64 v38; // r9
  int v39; // r14d
  int v40; // r15d
  __int64 v41; // r12
  unsigned int v42; // ebx
  DWORD v43; // eax
  DWORD v44; // eax
  CCipherMill *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  const WCHAR *v49; // rdx
  const WCHAR *v50; // r14
  __int64 v51; // rax
  unsigned int v52; // r15d
  __int64 v53; // rdx
  __int64 v54; // r8
  DWORD v55; // eax
  __int64 v56; // r9
  void *pvPara; // [rsp+20h] [rbp-E0h]
  PCCERT_CONTEXT *ppCertContext; // [rsp+28h] [rbp-D8h]
  int v59; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v60; // [rsp+48h] [rbp-B8h] BYREF
  int v61; // [rsp+50h] [rbp-B0h]
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h] BYREF
  PCCERT_CONTEXT v63; // [rsp+60h] [rbp-A0h]
  int v64; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpString; // [rsp+80h] [rbp-80h]
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+88h] [rbp-78h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp-70h] BYREF
  DWORD dwFlags; // [rsp+94h] [rbp-6Ch]
  __int128 v70; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h]
  __int128 v72; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR v73; // [rsp+C0h] [rbp-40h]
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+C8h] [rbp-38h] BYREF
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+E0h] [rbp-20h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v77[8]; // [rsp+150h] [rbp+50h] BYREF
  int v78; // [rsp+158h] [rbp+58h]
  int v79; // [rsp+15Ch] [rbp+5Ch]
  struct _EVENT_DATA_DESCRIPTOR pvData; // [rsp+7D0h] [rbp+6D0h] BYREF
  _QWORD v81[3]; // [rsp+7E0h] [rbp+6E0h] BYREF

  v64 = a3;
  dwFlags = a2;
  v73 = 0;
  v72 = 0;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset_0(&pChainPara, 0, 0x60u);
  v4 = *((_QWORD *)a1 + 13);
  v81[0] = "1.3.6.1.5.5.7.3.1";
  pChainContext = 0;
  v81[1] = "1.3.6.1.4.1.311.10.3.3";
  v81[2] = "2.16.840.1.113730.4.1";
  v60 = 0;
  v71 = v4;
  v70 = 0;
  if ( !v4 )
    return 2148074244LL;
  *(_QWORD *)&DestinationString.Length = *((_QWORD *)a1 + 232);
  v5 = *(_QWORD *)a1;
  v6 = 0;
  v61 = 0;
  (*(void (__fastcall **)(struct CSsl3TlsContext *, __int64 *))(v5 + 240))(a1, &v60);
  if ( !v60 )
  {
    v9 = 0;
    LastError = -2146893052;
    goto LABEL_52;
  }
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v60 + 40) + 80LL), 1u);
  if ( (*(_BYTE *)(v4 + 220) & 2) != 0 )
    lpString = 0;
  else
    lpString = *(LPCWSTR *)(*(_QWORD *)(v60 + 160) + 264LL);
  v7 = *(_QWORD *)(v60 + 40);
  pCertContext = 0;
  v63 = 0;
  v8 = *(_DWORD *)(v7 + 24);
  v9 = 0;
  v10 = *(const BYTE **)(v7 + 16);
  v11 = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
  if ( !v11 )
  {
    LastError = GetLastError();
    goto LABEL_23;
  }
  v59 = 0;
  *(_QWORD *)&pvData.Size = &v59;
  v12 = 1;
  pvData.Ptr = 4;
  while ( 1 )
  {
    if ( v8 < 4 || (v13 = *(unsigned int *)v10, v14 = v8 - 4, (unsigned int)v13 > v14) )
    {
      LastError = -2146893052;
      CertCloseStore(v11, 0);
      goto LABEL_68;
    }
    if ( !CertAddEncodedCertificateToStore(v11, 1u, v10 + 4, v13, 2u, &pCertContext) )
    {
LABEL_20:
      LastError = GetLastError();
      goto LABEL_21;
    }
    pcbData = 0;
    if ( !CertGetCertificateContextProperty(pCertContext, 0xE697u, 0, &pcbData) )
      break;
LABEL_14:
    v8 = v14 - v13;
    if ( v12 )
    {
      v12 = 0;
      v63 = pCertContext;
    }
    else
    {
      CertFreeCertificateContext(pCertContext);
    }
    pCertContext = 0;
    if ( !v8 )
    {
      LastError = 0;
      CertCloseStore(v11, 0);
      goto LABEL_22;
    }
    v10 += v13 + 4;
  }
  if ( GetLastError() == -2146885628 )
  {
    if ( !CertSetCertificateContextProperty(pCertContext, 0xE697u, 0, &pvData) )
      goto LABEL_20;
    ++v59;
    goto LABEL_14;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, LastError);
LABEL_21:
  CertCloseStore(v11, 0);
  if ( !LastError )
    goto LABEL_22;
LABEL_68:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v63 )
  {
    CertFreeCertificateContext(v63);
    v63 = 0;
  }
LABEL_22:
  v4 = v71;
  v9 = v63;
LABEL_23:
  if ( LastError )
  {
    LOBYTE(v16) = 42;
    CSslContext::SetErrorAndFatalAlert(a1, 550, LastError, v16);
    goto LABEL_49;
  }
  v17 = *(_QWORD *)(v60 + 160);
  LODWORD(v70) = *(_DWORD *)(v17 + 240);
  *((_QWORD *)&v70 + 1) = *(_QWORD *)(v17 + 232);
  if ( (_DWORD)v70
    && !CertSetCertificateContextProperty(v9, 0x46u, 0, &v70)
    && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v44 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, v44);
  }
  v18 = *(_QWORD *)(v60 + 160);
  v19 = *(_DWORD *)(v18 + 256);
  v20 = *(_QWORD *)(v18 + 248);
  *((_QWORD *)&v70 + 1) = v20;
  LODWORD(v70) = v19;
  if ( v19
    && v20
    && !CertSetCertificateContextProperty(v9, 0x77u, 0, &v70)
    && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v43 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, v43);
  }
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v60 + 40) + 80LL));
  v21 = *((_QWORD *)a1 + 13);
  LastError = 0;
  v60 = 0;
  v6 = 0;
  v61 = 0;
  v22 = *(const CERT_CONTEXT **)(v21 + 816);
  pCertContext = v22;
  if ( LsaTable )
  {
    if ( v22 )
      v23 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &pCertContext, 8u);
    else
      v23 = (*(__int64 (**)(void))(LsaTable + 88))();
    if ( v23 >= 0 )
    {
      v6 = 1;
      v61 = 1;
    }
    if ( RtlNtStatusToDosError(v23) )
    {
      LastError = -2146893052;
      goto LABEL_49;
    }
  }
  memset_0(&pChainPara, 0, 0x60u);
  pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)v81;
  pChainPara.cbSize = 96;
  pChainPara.RequestedUsage.dwType = 1;
  pChainPara.RequestedUsage.Usage.cUsageIdentifier = 3;
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v24, (int)&ChainBuildStart, v25, v26, &pvData);
  if ( !CertGetCertificateChain(0, v9, 0, v9->hCertStore, &pChainPara, dwFlags, 0, &pChainContext) )
  {
    if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v27, (int)&ChainBuildStop, v28, v29, &pvData);
    v55 = GetLastError();
    LOBYTE(v56) = 80;
    LastError = v55;
    CSslContext::SetErrorAndFatalAlert(a1, 551, v55, v56);
    goto LABEL_49;
  }
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v27, (int)&ChainBuildStop, v28, v29, &pvData);
  if ( (*(_BYTE *)(v4 + 220) & 2) == 0 && (!lpString || !lstrlenW(lpString)) )
  {
    LOBYTE(v29) = 80;
    LastError = -2146893022;
    CSslContext::SetErrorAndFatalAlert(a1, 553, 2148074274LL, v29);
    goto LABEL_49;
  }
  v73 = lpString;
  pPolicyPara.pvExtraPolicyPara = &v72;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  v72 = 0x200000018uLL;
  *(_QWORD *)&pPolicyPara.cbSize = 16;
  pPolicyStatus.cbSize = 24;
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v27, (int)&ChainVerifyStart, v28, v29, &pvData);
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v30, (int)&ChainVerifyStop, v31, v32, &pvData);
    v37 = GetLastError();
    LOBYTE(v38) = 80;
    LastError = v37;
    CSslContext::SetErrorAndFatalAlert(a1, 552, v37, v38);
    v9 = v63;
    goto LABEL_49;
  }
  if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v30, (int)&ChainVerifyStop, v31, v32, &pvData);
  (*(void (__fastcall **)(struct CSsl3TlsContext *, __int64 *))(*(_QWORD *)a1 + 240LL))(a1, &v60);
  if ( !v60 )
  {
    LastError = -2146893052;
    goto LABEL_52;
  }
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(*(_QWORD *)(v60 + 40) + 80LL), 1u);
  dwErrorStatus = pChainContext->TrustStatus.dwErrorStatus;
  v34 = *(_QWORD *)(v60 + 40);
  *(_DWORD *)(v34 + 208) = pPolicyStatus.dwError;
  *(_DWORD *)(v34 + 212) = dwErrorStatus;
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v60 + 40) + 80LL));
  v60 = 0;
  if ( (*(_QWORD *)&DestinationString.Length & 0x200000000LL) != 0 )
    goto LABEL_49;
  dwError = pPolicyStatus.dwError;
  if ( pPolicyStatus.dwError == -2146885614 )
  {
    if ( (v64 & 0x800) != 0 )
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_49;
      v46 = 18;
LABEL_132:
      WPP_SF_(*((_QWORD *)v45 + 2), v46, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids);
      goto LABEL_49;
    }
LABEL_121:
    LOBYTE(v11) = 43;
    goto LABEL_95;
  }
  if ( pPolicyStatus.dwError == -2146885613 )
  {
    if ( (v64 & 0x1000) != 0 )
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_49;
      v46 = 19;
      goto LABEL_132;
    }
    goto LABEL_121;
  }
  if ( (pPolicyStatus.dwError & 0x1FFF0000) != 0x90000 )
  {
    if ( !pPolicyStatus.dwError )
      goto LABEL_49;
    if ( pPolicyStatus.dwError == -2146762478 )
    {
LABEL_61:
      LastError = -2146893019;
      LOBYTE(v11) = 48;
    }
    else
    {
      switch ( pPolicyStatus.dwError )
      {
        case 0x800B0101:
        case 0x800B0102:
          LastError = -2146893016;
          LOBYTE(v11) = 45;
          break;
        case 0x800B0109:
          goto LABEL_61;
        case 0x800B010C:
          LastError = -2146885616;
          LOBYTE(v11) = 44;
          break;
        case 0x800B010F:
          LastError = -2146893022;
          LOBYTE(v11) = 43;
          break;
        case 0x800B0110:
          LastError = -2146892983;
          LOBYTE(v11) = 43;
          break;
        default:
          LastError = -2146893017;
          LOBYTE(v11) = 46;
          break;
      }
    }
    v59 = (int)v11;
    dwError = LastError;
LABEL_97:
    v47 = (*(__int64 (__fastcall **)(struct CSsl3TlsContext *))(*(_QWORD *)a1 + 352LL))(a1);
    v48 = *((_QWORD *)a1 + 231);
    if ( !*(_WORD *)(v48 + 34) )
    {
      *(_WORD *)(v48 + 34) = 552;
      *(_DWORD *)(v48 + 36) = dwError;
    }
    *((_BYTE *)a1 + 120) = 2;
    v49 = &Class;
    *((_BYTE *)a1 + 121) = (_BYTE)v11;
    v50 = &Class;
    if ( v47 )
      v50 = (const WCHAR *)v47;
    v51 = *((_QWORD *)a1 + 13);
    if ( v51 )
    {
      v52 = *(_DWORD *)(v51 + 276);
      v49 = (const WCHAR *)(v51 + 280);
    }
    else
    {
      v52 = 0;
    }
    if ( (g_dwEventLogging & 4) != 0 )
    {
      DestinationString = 0;
      pvData = 0;
      RtlInitUnicodeString(&DestinationString, v49);
      RtlInitUnicodeString((PUNICODE_STRING)&pvData, v50);
      LODWORD(ppCertContext) = 552;
      LODWORD(pvPara) = (unsigned __int8)v11;
      SchEventWrite(&SSLEVENT_GENERATE_FATAL_ALERT, L"duddu", v52, &DestinationString, pvPara, ppCertContext, &pvData);
    }
    memset_0(v77, 0, 0x680u);
    v53 = *((_QWORD *)a1 + 1);
    if ( v53 )
      v39 = *(_DWORD *)(v53 + 28);
    else
      v39 = 0;
    v40 = *((unsigned __int16 *)a1 + 17);
    v41 = *((_QWORD *)a1 + 232);
    v79 = *((_DWORD *)a1 + 4);
    v78 = v39;
    if ( v53 )
    {
      v54 = *((_QWORD *)a1 + 14);
      if ( v54 )
        CSchannelTelemetryContext::LogKeyExchange(
          (struct CSsl3TlsContext *)((char *)a1 + 144),
          *(_DWORD *)(v53 + 32),
          *(_DWORD *)(*(_QWORD *)(v54 + 40) + 8LL));
    }
    if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
    {
      *((_BYTE *)a1 + 260) = v59;
      *((_DWORD *)a1 + 47) = v79;
      *((_DWORD *)a1 + 64) = dwError;
      *((_DWORD *)a1 + 66) = 552;
      *((_DWORD *)a1 + 46) = v39;
      *((_DWORD *)a1 + 48) = v40;
      *((_QWORD *)a1 + 35) = v41;
      *((_BYTE *)a1 + 169) = 1;
    }
    CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((struct CSsl3TlsContext *)((char *)a1 + 144), L"Fatal Error");
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, dwError);
    pvData = 0;
    v42 = *(_DWORD *)(v71 + 276);
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(v71 + 280));
    if ( (g_dwEventLogging & 1) != 0 )
    {
      if ( dwError == -2146893022 )
      {
        RtlInitUnicodeString((PUNICODE_STRING)&pvData, lpString);
        v9 = v63;
        LODWORD(ppCertContext) = v63->cbCertEncoded;
        SchEventWrite(
          &SSLEVENT_NAME_MISMATCHED_SERVER_CERT,
          L"duub",
          v42,
          &DestinationString,
          &pvData,
          ppCertContext,
          v63->pbCertEncoded);
      }
      else
      {
        v9 = v63;
        switch ( dwError )
        {
          case 0x80090325:
            LODWORD(pvPara) = v63->cbCertEncoded;
            SchEventWrite(&SSLEVENT_UNTRUSTED_SERVER_CERT, L"dub", v42, &DestinationString, pvPara, v63->pbCertEncoded);
            break;
          case 0x80090328:
            LODWORD(pvPara) = v63->cbCertEncoded;
            SchEventWrite(&SSLEVENT_EXPIRED_SERVER_CERT, L"dub", v42, &DestinationString, pvPara, v63->pbCertEncoded);
            break;
          case 0x80092010:
            LODWORD(pvPara) = v63->cbCertEncoded;
            SchEventWrite(&SSLEVENT_REVOKED_SERVER_CERT, L"dub", v42, &DestinationString, pvPara, v63->pbCertEncoded);
            break;
          default:
            LODWORD(ppCertContext) = v63->cbCertEncoded;
            LODWORD(pvPara) = dwError;
            SchEventWrite(
              &SSLEVENT_BOGUS_SERVER_CERT,
              L"dudb",
              v42,
              &DestinationString,
              pvPara,
              ppCertContext,
              v63->pbCertEncoded);
            break;
        }
      }
    }
    else
    {
      v9 = v63;
    }
    goto LABEL_49;
  }
  LODWORD(v11) = 44;
  if ( pPolicyStatus.dwError != -2146885616 )
    LODWORD(v11) = 46;
  LastError = 0;
LABEL_95:
  v59 = (int)v11;
  if ( pPolicyStatus.dwError )
  {
    LastError = pPolicyStatus.dwError;
    goto LABEL_97;
  }
LABEL_49:
  if ( v60 )
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v60 + 40) + 80LL));
  v6 = v61;
LABEL_52:
  if ( pChainContext )
    CertFreeCertificateChain(pChainContext);
  if ( v9 )
    CertFreeCertificateContext(v9);
  if ( v6 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180017f00  push    rbp
0x180017f02  push    rbx
0x180017f03  push    rsi
0x180017f04  push    r15
0x180017f06  lea     rbp, [rsp-718h]
0x180017f0e  sub     rsp, 818h
0x180017f15  mov     rax, cs:__security_cookie
0x180017f1c  xor     rax, rsp
0x180017f1f  mov     [rbp+730h+var_38], rax
0x180017f26  xorps   xmm0, xmm0
0x180017f29  mov     [rsp+830h+var_7C8], r8d
0x180017f2e  xor     eax, eax
0x180017f30  mov     [rbp+730h+dwFlags], edx
0x180017f33  mov     rbx, rcx
0x180017f36  mov     [rbp+730h+var_770], rax
0x180017f3a  xorps   xmm1, xmm1
0x180017f3d  mov     [rbp+730h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180017f41  xor     edx, edx; Val
0x180017f43  lea     rcx, [rbp+730h+pChainPara]; void *
0x180017f47  mov     r8d, 60h ; '`'; Size
0x180017f4d  movups  [rbp+730h+var_780], xmm0
0x180017f51  movups  xmmword ptr [rbp+730h+pPolicyPara.cbSize], xmm0
0x180017f55  movups  xmmword ptr [rbp+730h+pPolicyStatus.cbSize], xmm1
0x180017f59  call    memset_0
0x180017f5e  mov     r15, [rbx+68h]
0x180017f62  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x180017f69  xor     esi, esi
0x180017f6b  mov     [rbp+730h+var_50], rax
0x180017f72  mov     [rbp+730h+pChainContext], rsi
0x180017f76  lea     rax, a1361413111033; "1.3.6.1.4.1.311.10.3.3"
0x180017f7d  mov     [rbp+730h+var_48], rax
0x180017f84  lea     rax, a21684011137304; "2.16.840.1.113730.4.1"
0x180017f8b  mov     [rbp+730h+var_40], rax
0x180017f92  xorps   xmm0, xmm0
0x180017f95  mov     [rsp+830h+var_7E8], rsi
0x180017f9a  mov     [rbp+730h+var_788], r15
0x180017f9e  movups  [rbp+730h+var_798], xmm0
0x180017fa2  test    r15, r15
0x180017fa5  jz      loc_1800187FB
0x180017fab  mov     rax, [rbx+740h]
0x180017fb2  lea     rdx, [rsp+830h+var_7E8]
0x180017fb7  mov     qword ptr [rsp+830h+DestinationString.Length], rax
0x180017fbc  mov     rcx, rbx
0x180017fbf  mov     rax, [rbx]
0x180017fc2  mov     [rsp+830h+arg_10], rdi
0x180017fca  mov     edi, esi
0x180017fcc  mov     [rsp+830h+var_28], r13
0x180017fd4  mov     [rsp+830h+var_7E0], esi
0x180017fd8  mov     rax, [rax+0F0h]
0x180017fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fe4  mov     rcx, [rsp+830h+var_7E8]
0x180017fe9  test    rcx, rcx
0x180017fec  jz      loc_180018805
0x180017ff2  mov     rcx, [rcx+28h]
0x180017ff6  mov     dl, 1; Wait
0x180017ff8  add     rcx, 50h ; 'P'; Resource
0x180017ffc  mov     [rsp+830h+var_20], r12
0x180018004  mov     [rsp+830h+var_30], r14
0x18001800c  call    cs:__imp_RtlAcquireResourceShared
0x180018012  test    byte ptr [r15+0DCh], 2
0x18001801a  mov     rcx, [rsp+830h+var_7E8]
0x18001801f  jnz     loc_18001816E
0x180018025  mov     rax, [rcx+0A0h]
0x18001802c  mov     rsi, [rax+108h]
0x180018033  mov     [rbp+730h+lpString], rsi
0x180018037  xor     esi, esi
0x180018039  mov     rax, [rcx+28h]
0x18001803d  mov     r9d, 4; dwFlags
0x180018043  xor     r8d, r8d; hCryptProv
0x180018046  mov     [rsp+830h+pCertContext], rsi
0x18001804b  xor     edx, edx; dwEncodingType
0x18001804d  mov     [rsp+830h+var_7D0], rsi
0x180018052  mov     ecx, 2; lpszStoreProvider
0x180018057  mov     [rsp+830h+pvPara], rsi; pvPara
0x18001805c  mov     edi, [rax+18h]
0x18001805f  mov     r13, rsi
0x180018062  mov     r14, [rax+10h]
0x180018066  call    cs:__imp_CertOpenStore
0x18001806c  mov     r12, rax
0x18001806f  test    rax, rax
0x180018072  jz      loc_1800184E2
0x180018078  lea     rax, [rsp+830h+var_7F0]
0x18001807d  mov     [rsp+830h+var_7F0], esi
0x180018081  mov     qword ptr [rbp+730h+pvData+8], rax
0x180018088  mov     r13d, 1
0x18001808e  mov     qword ptr [rbp+730h+pvData], 4
0x180018099  mov     rcx, r12; hCertStore
0x18001809c  cmp     edi, 4
0x18001809f  jb      loc_180018529
0x1800180a5  mov     esi, [r14]
0x1800180a8  add     edi, 0FFFFFFFCh
0x1800180ab  cmp     esi, edi
0x1800180ad  ja      loc_180018529
0x1800180b3  lea     rax, [rsp+830h+pCertContext]
0x1800180b8  mov     r9d, esi; cbCertEncoded
0x1800180bb  mov     [rsp+830h+ppCertContext], rax; ppCertContext
0x1800180c0  lea     r15, [r14+4]
0x1800180c4  mov     r8, r15; pbCertEncoded
0x1800180c7  mov     dword ptr [rsp+830h+pvPara], 2; dwAddDisposition
0x1800180cf  mov     edx, 1; dwCertEncodingType
0x1800180d4  call    cs:__imp_CertAddEncodedCertificateToStore
0x1800180da  test    eax, eax
0x1800180dc  jz      loc_180018177
0x1800180e2  mov     rcx, [rsp+830h+pCertContext]; pCertContext
0x1800180e7  lea     r9, [rbp+730h+pcbData]; pcbData
0x1800180eb  xor     r14d, r14d
0x1800180ee  xor     r8d, r8d; pvData
0x1800180f1  mov     edx, 0E697h; dwPropId
0x1800180f6  mov     [rbp+730h+pcbData], r14d
0x1800180fa  call    cs:__imp_CertGetCertificateContextProperty
0x180018100  test    eax, eax
0x180018102  jnz     short loc_180018137
0x180018104  call    cs:__imp_GetLastError
0x18001810a  cmp     eax, 80092004h
0x18001810f  jnz     loc_180018812
0x180018115  mov     rcx, [rsp+830h+pCertContext]; pCertContext
0x18001811a  lea     r9, [rbp+730h+pvData]; pvData
0x180018121  xor     r8d, r8d; dwFlags
0x180018124  mov     edx, 0E697h; dwPropId
0x180018129  call    cs:__imp_CertSetCertificateContextProperty
0x18001812f  test    eax, eax
0x180018131  jz      short loc_180018177
0x180018133  inc     [rsp+830h+var_7F0]
0x180018137  sub     edi, esi
0x180018139  test    r13d, r13d
0x18001813c  jnz     short loc_18001815F
0x18001813e  mov     rcx, [rsp+830h+pCertContext]; pCertContext
0x180018143  call    cs:__imp_CertFreeCertificateContext
0x180018149  mov     [rsp+830h+pCertContext], r14
0x18001814e  test    edi, edi
0x180018150  jz      loc_1800184A7
0x180018156  lea     r14, [r15+rsi]
0x18001815a  jmp     loc_180018099
0x18001815f  mov     rax, [rsp+830h+pCertContext]
0x180018164  mov     r13d, r14d
0x180018167  mov     [rsp+830h+var_7D0], rax
0x18001816c  jmp     short loc_180018149
0x18001816e  mov     [rbp+730h+lpString], rsi
0x180018172  jmp     loc_180018039
0x180018177  call    cs:__imp_GetLastError
0x18001817d  mov     esi, eax
0x18001817f  xor     edx, edx; dwFlags
0x180018181  mov     rcx, r12; hCertStore
0x180018184  call    cs:__imp_CertCloseStore
0x18001818a  test    esi, esi
0x18001818c  jnz     loc_180018536
0x180018192  mov     r15, [rbp+730h+var_788]
0x180018196  mov     r13, [rsp+830h+var_7D0]
0x18001819b  test    esi, esi
0x18001819d  jnz     loc_180018858
0x1800181a3  mov     rax, [rsp+830h+var_7E8]
0x1800181a8  mov     rax, [rax+0A0h]
0x1800181af  mov     ecx, [rax+0F0h]
0x1800181b5  mov     dword ptr [rbp+730h+var_798], ecx
0x1800181b8  mov     rax, [rax+0E8h]
0x1800181bf  mov     qword ptr [rbp+730h+var_798+8], rax
0x1800181c3  test    ecx, ecx
0x1800181c5  jnz     loc_1800186A7
0x1800181cb  lea     r14, WPP_GLOBAL_Control
0x1800181d2  mov     rax, [rsp+830h+var_7E8]
0x1800181d7  mov     rcx, [rax+0A0h]
0x1800181de  mov     eax, [rcx+100h]
0x1800181e4  mov     rdx, [rcx+0F8h]
0x1800181eb  mov     qword ptr [rbp+730h+var_798+8], rdx
0x1800181ef  mov     dword ptr [rbp+730h+var_798], eax
0x1800181f2  test    eax, eax
0x1800181f4  jnz     loc_18001862F
0x1800181fa  mov     rax, [rsp+830h+var_7E8]
0x1800181ff  mov     rcx, [rax+28h]
0x180018203  add     rcx, 50h ; 'P'; Resource
0x180018207  call    cs:__imp_RtlReleaseResource
0x18001820d  mov     rax, [rbx+68h]
0x180018211  xor     esi, esi
0x180018213  mov     [rsp+830h+var_7E8], rsi
0x180018218  mov     edi, esi
0x18001821a  mov     [rsp+830h+var_7E0], esi
0x18001821e  mov     rcx, [rax+330h]
0x180018225  mov     rax, cs:LsaTable
0x18001822c  mov     [rsp+830h+pCertContext], rcx
0x180018231  test    rax, rax
0x180018234  jz      short loc_180018279
0x180018236  test    rcx, rcx
0x180018239  jz      loc_180018550
0x18001823f  mov     r9d, 8; ThreadInformationLength
0x180018245  lea     r8, [rsp+830h+pCertContext]; ThreadInformation
0x18001824a  mov     edx, 5; ThreadInformationClass
0x18001824f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180018256  call    cs:__imp_NtSetInformationThread
0x18001825c  test    eax, eax
0x18001825e  js      short loc_180018269
0x180018260  mov     edi, 1
0x180018265  mov     [rsp+830h+var_7E0], edi
0x180018269  mov     ecx, eax; Status
0x18001826b  call    cs:__imp_RtlNtStatusToDosError
0x180018271  test    eax, eax
0x180018273  jnz     loc_180018870
0x180018279  xor     edx, edx; Val
0x18001827b  lea     rcx, [rbp+730h+pChainPara]; void *
0x18001827f  mov     r8d, 60h ; '`'; Size
0x180018285  call    memset_0
0x18001828a  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x180018291  lea     rax, [rbp+730h+var_50]
0x180018298  mov     [rbp+730h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18001829c  mov     [rbp+730h+pChainPara.cbSize], 60h ; '`'
0x1800182a3  mov     [rbp+730h+pChainPara.RequestedUsage.dwType], 1
0x1800182aa  mov     [rbp+730h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], 3
0x1800182b1  jnz     loc_18001887A
0x1800182b7  mov     r9, [r13+20h]; hAdditionalStore
0x1800182bb  lea     rax, [rbp+730h+pChainContext]
0x1800182bf  mov     [rsp+830h+ppChainContext], rax; ppChainContext
0x1800182c4  xor     r8d, r8d; pTime
0x1800182c7  mov     eax, [rbp+730h+dwFlags]
0x1800182ca  mov     rdx, r13; pCertContext
0x1800182cd  mov     [rsp+830h+pvReserved], rsi; pvReserved
0x1800182d2  xor     ecx, ecx; hChainEngine
0x1800182d4  mov     dword ptr [rsp+830h+ppCertContext], eax; dwFlags
0x1800182d8  lea     rax, [rbp+730h+pChainPara]
0x1800182dc  mov     [rsp+830h+pvPara], rax; pChainPara
0x1800182e1  call    cs:__imp_CertGetCertificateChain
0x1800182e7  test    eax, eax
0x1800182e9  jz      loc_180018897
0x1800182ef  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x1800182f6  jnz     loc_1800188C2
0x1800182fc  test    byte ptr [r15+0DCh], 2
0x180018304  jz      loc_1800184EF
0x18001830a  mov     rax, [rbp+730h+lpString]
0x18001830e  xorps   xmm0, xmm0
0x180018311  mov     [rbp+730h+var_770], rax
0x180018315  lea     rax, [rbp+730h+var_780]
0x180018319  mov     [rbp+730h+pPolicyPara.pvExtraPolicyPara], rax
0x18001831d  xor     eax, eax
0x18001831f  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x180018326  movups  xmmword ptr [rbp+730h+pPolicyStatus.cbSize], xmm0
0x18001832a  mov     qword ptr [rbp+730h+var_780+8], rsi
0x18001832e  mov     dword ptr [rbp+730h+var_780], 18h
0x180018335  mov     dword ptr [rbp+730h+var_780+4], 2
0x18001833c  mov     qword ptr [rbp+730h+pPolicyPara.cbSize], 10h
0x180018344  mov     [rbp+730h+pPolicyStatus.pvExtraPolicyStatus], rax
0x180018348  mov     [rbp+730h+pPolicyStatus.cbSize], 18h
0x18001834f  jnz     loc_1800188DF
0x180018355  mov     rdx, [rbp+730h+pChainContext]; pChainContext
0x180018359  lea     r9, [rbp+730h+pPolicyStatus]; pPolicyStatus
0x18001835d  lea     r8, [rbp+730h+pPolicyPara]; pPolicyPara
0x180018361  mov     ecx, 4; pszPolicyOID
0x180018366  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18001836c  test    eax, eax
0x18001836e  jz      loc_18001855E
0x180018374  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18001837b  jnz     loc_180018919
0x180018381  mov     rax, [rbx]
0x180018384  lea     rdx, [rsp+830h+var_7E8]
0x180018389  mov     rcx, rbx
0x18001838c  mov     rax, [rax+0F0h]
0x180018393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018398  mov     rcx, [rsp+830h+var_7E8]
0x18001839d  test    rcx, rcx
0x1800183a0  jz      loc_18001870F
0x1800183a6  mov     rcx, [rcx+28h]
0x1800183aa  mov     dl, 1; Wait
0x1800183ac  add     rcx, 50h ; 'P'; Resource
0x1800183b0  call    cs:__imp_RtlAcquireResourceExclusive
0x1800183b6  mov     rax, [rbp+730h+pChainContext]
0x1800183ba  mov     edx, [rax+4]
0x1800183bd  mov     rax, [rsp+830h+var_7E8]
0x1800183c2  mov     rcx, [rax+28h]
0x1800183c6  mov     eax, [rbp+730h+pPolicyStatus.dwError]
0x1800183c9  mov     [rcx+0D0h], eax
0x1800183cf  mov     [rcx+0D4h], edx
0x1800183d5  mov     rax, [rsp+830h+var_7E8]
0x1800183da  mov     rcx, [rax+28h]
0x1800183de  add     rcx, 50h ; 'P'; Resource
0x1800183e2  call    cs:__imp_RtlReleaseResource
0x1800183e8  mov     rax, 200000000h
0x1800183f2  mov     [rsp+830h+var_7E8], rsi
0x1800183f7  test    qword ptr [rsp+830h+DestinationString.Length], rax
0x1800183fc  jnz     short loc_180018433
0x1800183fe  mov     edi, [rbp+730h+pPolicyStatus.dwError]
0x180018401  cmp     edi, 80092012h
0x180018407  jz      loc_180018936
0x18001840d  cmp     edi, 80092013h
0x180018413  jz      loc_180018719
0x180018419  mov     eax, edi
0x18001841b  and     eax, 1FFF0000h
0x180018420  cmp     eax, 90000h
0x180018425  jz      loc_18001896C
0x18001842b  test    edi, edi
0x18001842d  jnz     loc_1800184BA
0x180018433  mov     rcx, [rsp+830h+var_7E8]
0x180018438  test    rcx, rcx
0x18001843b  jz      short loc_18001844B
0x18001843d  mov     rcx, [rcx+28h]
0x180018441  add     rcx, 50h ; 'P'; Resource
0x180018445  call    cs:__imp_RtlReleaseResource
0x18001844b  mov     edi, [rsp+830h+var_7E0]
0x18001844f  mov     r12, [rsp+830h+var_20]
0x180018457  mov     r14, [rsp+830h+var_30]
0x18001845f  mov     rcx, [rbp+730h+pChainContext]; pChainContext
0x180018463  test    rcx, rcx
0x180018466  jnz     loc_18001874B
0x18001846c  test    r13, r13
  ... truncated ...
```
