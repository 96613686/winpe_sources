# FindDefaultMachineCred(CCredentialGroup * *,ulong,_LUID *,void *,ulong,ushort const *)

- ea: `0x1800106e0`
- end: `0x18001104b`
- name: `?FindDefaultMachineCred@@YAKPEAPEAVCCredentialGroup@@KPEAU_LUID@@PEAXKPEBG@Z`
- size: `2411`
- prototype: `unsigned int __fastcall(struct CCredentialGroup **, unsigned int, struct _LUID *, void *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b800`

## callees

- `0x1800106e0`
- `0x180011054`
- `0x1800110b0`
- `0x1800110e4`
- `0x1800112c0`
- `0x180014240`
- `0x180021da8`
- `0x180021e64`
- `0x180021eb0`
- `0x180057c8c`
- `0x180057cb4`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f1e4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010e08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a84d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180010820`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180010852`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180010820`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180010852`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010863`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010863`
- `ntdll!RtlEnterCriticalSection` at `0x180010db5`
- `ntdll!RtlEnterCriticalSection` at `0x180010db5`
- `ntdll!RtlLeaveCriticalSection` at `0x18008a9ea`
- `ntdll!RtlLeaveCriticalSection` at `0x18008a9ea`
- `ntdll!RtlInitUnicodeString` at `0x180010bf2`
- `ntdll!RtlInitUnicodeString` at `0x180010bf2`
- `CRYPT32!CertOpenStore` at `0x1800108a4`
- `CRYPT32!CertOpenStore` at `0x1800108a4`
- `CRYPT32!CertCloseStore` at `0x180011027`
- `CRYPT32!CertCloseStore` at `0x180011027`
- `CRYPT32!CertFreeCertificateContext` at `0x180011017`
- `CRYPT32!CertFreeCertificateContext` at `0x180011017`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180010904`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180010904`
- `CRYPT32!CertFindExtension` at `0x180010ae7`
- `CRYPT32!CertFindExtension` at `0x180010ae7`
- `CRYPT32!CertGetCertificateChain` at `0x1800109b8`
- `CRYPT32!CertGetCertificateChain` at `0x1800109b8`
- `CRYPT32!CertFreeCertificateChain` at `0x180010ac9`
- `CRYPT32!CertFreeCertificateChain` at `0x180010b49`
- `CRYPT32!CertFreeCertificateChain` at `0x18008a8f2`
- `CRYPT32!CertFreeCertificateChain` at `0x180010ac9`
- `CRYPT32!CertFreeCertificateChain` at `0x180010b49`
- `CRYPT32!CertFreeCertificateChain` at `0x18008a8f2`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180010a64`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180010a64`
- `CRYPT32!CryptDecodeObject` at `0x18008a944`
- `CRYPT32!CryptDecodeObject` at `0x18008a944`

## pseudocode

```c
__int64 __fastcall FindDefaultMachineCred(
        struct CCredentialGroup **a1,
        unsigned int a2,
        struct _LUID *a3,
        void *a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  const WCHAR *v6; // rdi
  PCCERT_CONTEXT v7; // r14
  HCERTSTORE v8; // r15
  WCHAR *v9; // rax
  WCHAR *v10; // r12
  DWORD v11; // eax
  int v12; // r13d
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  char v21; // al
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  __int64 dwError; // r9
  PCERT_EXTENSION Extension; // rax
  CCipherMill *v27; // rcx
  CCipherMill *v28; // rcx
  DWORD v29; // ebx
  CSslCredManager *v31; // rdi
  CCredentialGroup *v32; // rax
  CCredentialGroup *v33; // rax
  struct CCredentialGroup *v34; // rsi
  CSslCredManager **v35; // r8
  DWORD LastError; // eax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  int v40; // ecx
  DWORD v41; // eax
  __int64 v42; // rdx
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  DWORD nSize; // [rsp+40h] [rbp-248h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+48h] [rbp-240h] BYREF
  DWORD pcbStructInfo; // [rsp+50h] [rbp-238h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-234h]
  PCWSTR SourceString; // [rsp+58h] [rbp-230h]
  __int128 v50; // [rsp+60h] [rbp-228h] BYREF
  WCHAR *v51; // [rsp+70h] [rbp-218h]
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+78h] [rbp-210h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+88h] [rbp-200h] BYREF
  void *v54; // [rsp+A0h] [rbp-1E8h]
  struct _LUID *v55; // [rsp+A8h] [rbp-1E0h]
  struct CCredentialGroup **v56; // [rsp+B0h] [rbp-1D8h]
  _BYTE v57[56]; // [rsp+B8h] [rbp-1D0h] BYREF
  _CERT_CHAIN_PARA pChainPara; // [rsp+F0h] [rbp-198h] BYREF
  __int128 v59; // [rsp+110h] [rbp-178h]
  __int128 v60; // [rsp+120h] [rbp-168h]
  __int128 v61; // [rsp+130h] [rbp-158h]
  __int128 v62; // [rsp+140h] [rbp-148h]
  _DWORD v63[2]; // [rsp+150h] [rbp-138h] BYREF
  _BYTE *v64; // [rsp+158h] [rbp-130h]
  __int128 v65; // [rsp+160h] [rbp-128h]
  __int128 v66; // [rsp+170h] [rbp-118h]
  __int128 v67; // [rsp+180h] [rbp-108h]
  __int128 v68; // [rsp+190h] [rbp-F8h]
  __int128 v69; // [rsp+1A0h] [rbp-E8h]
  __int128 v70; // [rsp+1B0h] [rbp-D8h]
  _UNICODE_STRING DestinationString; // [rsp+1C0h] [rbp-C8h] BYREF
  _QWORD v72[3]; // [rsp+1D0h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v73; // [rsp+1E8h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v74; // [rsp+1F8h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v75; // [rsp+208h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v76; // [rsp+218h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+228h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v78; // [rsp+238h] [rbp-50h] BYREF

  v6 = a6;
  v55 = a3;
  v48 = a2;
  v56 = a1;
  SourceString = a6;
  v51 = 0;
  v50 = 0;
  pPolicyPara = 0;
  v54 = a4;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset_0(&pChainPara, 0, 0x60u);
  pChainContext = 0;
  v7 = 0;
  memset_0(v63, 0, 0x70u);
  nSize = 0;
  v8 = 0;
  v72[0] = "1.3.6.1.5.5.7.3.1";
  v72[1] = "1.3.6.1.4.1.311.10.3.3";
  v72[2] = "2.16.840.1.113730.4.1";
  memset(v57, 0, sizeof(v57));
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
  nSize = 0;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) && GetLastError() != 234 )
  {
    v10 = 0;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_100;
    LastError = GetLastError();
    v37 = 26;
    goto LABEL_99;
  }
  v9 = (WCHAR *)SPExternalAlloc(2 * nSize);
  v10 = v9;
  if ( !v9 )
  {
    v29 = -2146893056;
    goto LABEL_47;
  }
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v9, &nSize) )
  {
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_100;
    LastError = GetLastError();
    v37 = 27;
LABEL_99:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids, LastError);
LABEL_100:
    v29 = -2146893022;
    goto LABEL_47;
  }
  v11 = lstrlenW(v10);
  nSize = v11;
  if ( v11 )
  {
    v38 = v11 - 1;
    if ( v10[v38] == 46 )
      v10[(unsigned int)v38] = 0;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids, v10);
  v8 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x2C000u, L"MY");
  if ( !v8 )
  {
    GetLastError();
    v29 = GetLastError();
    if ( !v29 )
      goto LABEL_73;
LABEL_47:
    if ( (g_dwEventLogging & 1) != 0 )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, v6);
      SchEventWrite(&SSLEVENT_NO_DEFAULT_SERVER_CRED, L"du", a5, &DestinationString);
    }
    if ( v10 )
      goto LABEL_73;
    goto LABEL_50;
  }
  v12 = 0;
  v13 = 0;
LABEL_9:
  if ( v13 >= 2 )
  {
    v6 = SourceString;
    v29 = -2146893042;
    goto LABEL_47;
  }
  v7 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                v7 = CertEnumCertificatesInStore(v8, v7);
                if ( !v7 )
                {
                  ++v13;
                  goto LABEL_9;
                }
                *(_OWORD *)&pChainPara.cbSize = 0;
                pChainPara.cbSize = 96;
                *(&pChainPara.RequestedUsage.Usage.cUsageIdentifier + 1) = 0;
                pChainPara.RequestedUsage.dwType = 1;
                pChainPara.RequestedUsage.Usage.cUsageIdentifier = 3;
                pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)v72;
                v59 = 0;
                v60 = 0;
                v61 = 0;
                v62 = 0;
                if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
                  McGenEventWrite_EventWriteTransfer(v15, (int)&ChainBuildStart, v16, v17, &v73);
                if ( CertGetCertificateChain(0, v7, 0, 0, &pChainPara, 0x90000004, 0, &pChainContext) )
                  break;
                if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
                  McGenEventWrite_EventWriteTransfer(v18, (int)&ChainBuildStop, v19, v20, &v74);
                if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v41 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    29,
                    WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids,
                    v41);
                }
              }
              v21 = Microsoft_Windows_Schannel_EventsEnableBits;
              if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
              {
                McGenEventWrite_EventWriteTransfer(v18, (int)&ChainBuildStop, v19, v20, &v75);
                v21 = Microsoft_Windows_Schannel_EventsEnableBits;
              }
              v50 = 0x200000018uLL;
              pPolicyPara.pvExtraPolicyPara = &v50;
              memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
              v51 = v10;
              pPolicyStatus.cbSize = 24;
              pPolicyPara.cbSize = 16;
              pPolicyPara.dwFlags = v13 != 0 ? 7 : 0;
              if ( (v21 & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(-v13, (int)&ChainVerifyStart, v19, v20, &v76);
              if ( CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
                break;
              if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(v22, (int)&ChainVerifyStop, v23, v24, &v77);
              GetLastError();
              CertFreeCertificateChain(pChainContext);
            }
            if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
              McGenEventWrite_EventWriteTransfer(v22, (int)&ChainVerifyStop, v23, v24, &v78);
            dwError = pPolicyStatus.dwError;
            if ( pPolicyStatus.dwError == -2146885614 )
              break;
            if ( pPolicyStatus.dwError == -2146885613 )
            {
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v42 = 19;
LABEL_104:
                WPP_SF_(*((_QWORD *)v28 + 2), v42, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids);
                goto LABEL_30;
              }
              goto LABEL_30;
            }
            if ( (pPolicyStatus.dwError & 0x1FFF0000) == 0x90000 )
            {
              if ( !pPolicyStatus.dwError )
                goto LABEL_30;
            }
            else
            {
              if ( !pPolicyStatus.dwError )
                goto LABEL_30;
              if ( pPolicyStatus.dwError == -2146762478 )
              {
LABEL_38:
                dwError = 2148074277LL;
              }
              else
              {
                switch ( pPolicyStatus.dwError )
                {
                  case 0x800B0101:
                  case 0x800B0102:
                    dwError = 2148074280LL;
                    break;
                  case 0x800B0109:
                    goto LABEL_38;
                  case 0x800B010C:
                    dwError = 2148081680LL;
                    break;
                  case 0x800B010F:
                    dwError = 2148074274LL;
                    break;
                  case 0x800B0110:
                    dwError = 2148074313LL;
                    break;
                  default:
                    dwError = 2148074279LL;
                    break;
                }
              }
            }
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids,
                dwError);
            }
            CertFreeCertificateChain(pChainContext);
          }
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v42 = 18;
            goto LABEL_104;
          }
LABEL_30:
          CertFreeCertificateChain(pChainContext);
          Extension = CertFindExtension("2.5.29.19", v7->pCertInfo->cExtension, v7->pCertInfo->rgExtension);
          if ( !Extension )
            break;
          cbData = Extension->Value.cbData;
          pbData = Extension->Value.pbData;
          *(_QWORD *)&DestinationString.Length = 0;
          LODWORD(DestinationString.Buffer) = 0;
          pcbStructInfo = 12;
          if ( !CryptDecodeObject(1u, (LPCSTR)0xF, pbData, cbData, 0, &DestinationString, &pcbStructInfo) )
            break;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
            v27 = WPP_GLOBAL_Control;
          }
          v12 = 1;
          if ( v13 )
          {
            if ( v27 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 4) == 0 )
              goto LABEL_59;
            v39 = 33;
            goto LABEL_125;
          }
          if ( v27 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 )
          {
            v14 = 32;
            goto LABEL_14;
          }
        }
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
          v27 = WPP_GLOBAL_Control;
        }
        if ( !v13 )
          break;
        if ( v12 != 1 )
        {
          if ( v27 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 4) == 0 )
            goto LABEL_59;
          v39 = 37;
          goto LABEL_125;
        }
        if ( v27 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 )
        {
          v14 = 36;
LABEL_14:
          WPP_SF_(*((_QWORD *)v27 + 2), v14, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
        }
      }
      if ( v27 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 4) == 0 )
        goto LABEL_59;
      v39 = 35;
LABEL_125:
      WPP_SF_(*((_QWORD *)v27 + 2), v39, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
LABEL_59:
      v31 = CSslCredManager::m_pCredManager;
      v64 = v57;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v69 = 0;
      v70 = 0;
      memset(&v57[8], 0, 48);
      v63[0] = 4;
      v63[1] = 1;
      *(_QWORD *)v57 = v7;
      CSslCredManager::DbgDumpSchannelCred(v27, (struct LSA_SCHANNEL_CRED *)v63);
      if ( LsaTable )
        v32 = (CCredentialGroup *)(*(__int64 (__fastcall **)(__int64))(LsaTable + 40))(976);
      else
        v32 = (CCredentialGroup *)LocalAlloc(0x40u, 0x3D0u);
      if ( v32 )
      {
        v33 = CCredentialGroup::CCredentialGroup(v32);
        v34 = v33;
        if ( v33 )
          break;
      }
    }
    if ( !CCredentialGroup::InitializeCredentialGroup(v33, v48, v55, v54, (struct LSA_SCHANNEL_CRED *)v63, SourceString) )
      break;
    (*(void (__fastcall **)(struct CCredentialGroup *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 1);
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v31 + 8));
  v35 = (CSslCredManager **)*((_QWORD *)v31 + 7);
  if ( *v35 != (CSslCredManager *)((char *)v31 + 48) )
    __fastfail(3u);
  *((_QWORD *)v34 + 9) = (char *)v31 + 48;
  *((_QWORD *)v34 + 10) = v35;
  *v35 = (struct CCredentialGroup *)((char *)v34 + 72);
  *((_QWORD *)v31 + 7) = (char *)v34 + 72;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v31 + 8));
  _InterlockedIncrement((volatile signed __int32 *)v34 + 22);
  *v56 = v34;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids);
  v29 = 0;
LABEL_73:
  SPExternalFree(v10);
LABEL_50:
  if ( v7 )
    CertFreeCertificateContext(v7);
  if ( v8 )
    CertCloseStore(v8, 0);
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (v40 = *((_DWORD *)WPP_GLOBAL_Control + 7), (v40 & 1) != 0) && v29 || (v40 & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids, v29, v29);
  }
  return v29;
}

```

## disassembly

```asm
0x1800106e0  push    rsi
0x1800106e2  push    rdi
0x1800106e3  push    r14
0x1800106e5  push    r15
0x1800106e7  sub     rsp, 268h
0x1800106ee  mov     rax, cs:__security_cookie
0x1800106f5  xor     rax, rsp
0x1800106f8  mov     [rsp+288h+var_40], rax
0x180010700  mov     rdi, [rsp+288h+arg_28]
0x180010708  xorps   xmm0, xmm0
0x18001070b  xor     eax, eax
0x18001070d  mov     [rsp+288h+var_1E0], r8
0x180010715  mov     [rsp+288h+var_234], edx
0x180010719  xorps   xmm1, xmm1
0x18001071c  mov     [rsp+288h+var_1D8], rcx
0x180010724  xor     edx, edx; Val
0x180010726  mov     r8d, 60h ; '`'; Size
0x18001072c  mov     [rsp+288h+SourceString], rdi
0x180010731  lea     rcx, [rsp+288h+pChainPara]; void *
0x180010739  mov     [rsp+288h+var_218], rax
0x18001073e  movups  [rsp+288h+var_228], xmm0
0x180010743  mov     [rsp+288h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18001074b  movups  xmmword ptr [rsp+288h+pPolicyPara.cbSize], xmm0
0x180010750  mov     [rsp+288h+var_1E8], r9
0x180010758  movups  xmmword ptr [rsp+288h+pPolicyStatus.cbSize], xmm1
0x180010760  call    memset_0
0x180010765  xor     edx, edx; Val
0x180010767  mov     [rsp+288h+pChainContext], 0
0x180010770  mov     r8d, 70h ; 'p'; Size
0x180010776  lea     rcx, [rsp+288h+var_138]; void *
0x18001077e  xor     r14d, r14d
0x180010781  call    memset_0
0x180010786  xor     eax, eax
0x180010788  mov     [rsp+288h+nSize], r14d
0x18001078d  mov     [rsp+288h+var_1A0], rax
0x180010795  xorps   xmm0, xmm0
0x180010798  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x18001079f  xor     r15d, r15d
0x1800107a2  mov     [rsp+288h+var_B8], rax
0x1800107aa  lea     rax, a1361413111033; "1.3.6.1.4.1.311.10.3.3"
0x1800107b1  mov     [rsp+288h+var_B0], rax
0x1800107b9  lea     rax, a21684011137304; "2.16.840.1.113730.4.1"
0x1800107c0  mov     [rsp+288h+var_A8], rax
0x1800107c8  movups  [rsp+288h+var_1D0], xmm0
0x1800107d0  movups  [rsp+288h+var_1C0], xmm0
0x1800107d8  movups  [rsp+288h+var_1B0], xmm0
0x1800107e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107e7  lea     rsi, WPP_GLOBAL_Control
0x1800107ee  cmp     rcx, rsi
0x1800107f1  jnz     loc_180010E5D
0x1800107f7  mov     [rsp+288h+var_28], rbx
0x1800107ff  lea     r8, [rsp+288h+nSize]; nSize
0x180010804  mov     [rsp+288h+var_30], r12
0x18001080c  xor     edx, edx; lpBuffer
0x18001080e  mov     ecx, 3; NameType
0x180010813  mov     [rsp+288h+var_38], r13
0x18001081b  mov     [rsp+288h+nSize], r14d
0x180010820  call    cs:__imp_GetComputerNameExW
0x180010826  test    eax, eax
0x180010828  jz      loc_180010E81
0x18001082e  mov     ecx, [rsp+288h+nSize]
0x180010832  add     ecx, ecx; uBytes
0x180010834  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180010839  mov     r12, rax
0x18001083c  test    rax, rax
0x18001083f  jz      loc_180010EBF
0x180010845  lea     r8, [rsp+288h+nSize]; nSize
0x18001084a  mov     rdx, rax; lpBuffer
0x18001084d  mov     ecx, 3; NameType
0x180010852  call    cs:__imp_GetComputerNameExW
0x180010858  test    eax, eax
0x18001085a  jz      loc_180010EC9
0x180010860  mov     rcx, r12; lpString
0x180010863  call    cs:__imp_lstrlenW
0x180010869  mov     [rsp+288h+nSize], eax
0x18001086d  test    eax, eax
0x18001086f  jnz     loc_180010EE8
0x180010875  mov     rcx, cs:WPP_GLOBAL_Control
0x18001087c  cmp     rcx, rsi
0x18001087f  jnz     loc_180010F04
0x180010885  lea     rax, aMy; "MY"
0x18001088c  mov     r9d, 2C000h; dwFlags
0x180010892  xor     r8d, r8d; hCryptProv
0x180010895  mov     [rsp+288h+pvPara], rax; pvPara
0x18001089a  mov     edx, 1; dwEncodingType
0x18001089f  mov     ecx, 0Ah; lpszStoreProvider
0x1800108a4  call    cs:__imp_CertOpenStore
0x1800108aa  mov     r15, rax
0x1800108ad  test    rax, rax
0x1800108b0  jz      loc_180010E3A
0x1800108b6  xor     r13d, r13d
0x1800108b9  xor     ebx, ebx
0x1800108bb  cmp     ebx, 2
0x1800108be  jnb     loc_180010BC9
0x1800108c4  xor     r14d, r14d
0x1800108c7  jmp     short loc_1800108FE
0x1800108c9  cmp     rcx, rsi
0x1800108cc  lea     rsi, WPP_GLOBAL_Control
0x1800108d3  jz      short loc_1800108FE
0x1800108d5  test    byte ptr [rcx+1Ch], 4
0x1800108d9  lea     rsi, WPP_GLOBAL_Control
0x1800108e0  jz      short loc_1800108FE
0x1800108e2  mov     edx, 20h ; ' '
0x1800108e7  mov     rcx, [rcx+10h]
0x1800108eb  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x1800108f2  call    WPP_SF_
0x1800108f7  lea     rsi, WPP_GLOBAL_Control
0x1800108fe  mov     rdx, r14; pPrevCertContext
0x180010901  mov     rcx, r15; hCertStore
0x180010904  call    cs:__imp_CertEnumCertificatesInStore
0x18001090a  mov     r14, rax
0x18001090d  test    rax, rax
0x180010910  jz      loc_180010BC2
0x180010916  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18001091d  lea     rax, [rsp+288h+var_B8]
0x180010925  xorps   xmm0, xmm0
0x180010928  movups  xmmword ptr [rsp+288h+pChainPara.cbSize], xmm0
0x180010930  mov     [rsp+288h+pChainPara.cbSize], 60h ; '`'
0x18001093b  movups  xmmword ptr [rsp+288h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], xmm0
0x180010943  mov     [rsp+288h+pChainPara.RequestedUsage.dwType], 1
0x18001094e  mov     [rsp+288h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], 3
0x180010959  mov     [rsp+288h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x180010961  movups  [rsp+288h+var_178], xmm0
0x180010969  movups  [rsp+288h+var_168], xmm0
0x180010971  movups  [rsp+288h+var_158], xmm0
0x180010979  movups  [rsp+288h+var_148], xmm0
0x180010981  jnz     loc_180010F2B
0x180010987  lea     rax, [rsp+288h+pChainContext]
0x18001098c  xor     edi, edi
0x18001098e  mov     [rsp+288h+ppChainContext], rax; ppChainContext
0x180010993  xor     r9d, r9d; hAdditionalStore
0x180010996  mov     [rsp+288h+pvReserved], rdi; pvReserved
0x18001099b  lea     rax, [rsp+288h+pChainPara]
0x1800109a3  mov     [rsp+288h+dwFlags], 90000004h; dwFlags
0x1800109ab  xor     r8d, r8d; pTime
0x1800109ae  mov     rdx, r14; pCertContext
0x1800109b1  mov     [rsp+288h+pvPara], rax; pChainPara
0x1800109b6  xor     ecx, ecx; hChainEngine
0x1800109b8  call    cs:__imp_CertGetCertificateChain
0x1800109be  test    eax, eax
0x1800109c0  jz      loc_180010F49
0x1800109c6  mov     eax, cs:Microsoft_Windows_Schannel_EventsEnableBits
0x1800109cc  test    al, 1
0x1800109ce  jnz     loc_180010F75
0x1800109d4  xor     ecx, ecx
0x1800109d6  mov     qword ptr [rsp+288h+var_228+8], rdi
0x1800109db  mov     [rsp+288h+pPolicyStatus.pvExtraPolicyStatus], rcx
0x1800109e3  xorps   xmm0, xmm0
0x1800109e6  lea     rcx, [rsp+288h+var_228]
0x1800109eb  mov     dword ptr [rsp+288h+var_228], 18h
0x1800109f3  mov     [rsp+288h+pPolicyPara.pvExtraPolicyPara], rcx
0x1800109fb  mov     ecx, ebx
0x1800109fd  neg     ecx; int
0x1800109ff  mov     dword ptr [rsp+288h+var_228+4], 2
0x180010a07  movups  xmmword ptr [rsp+288h+pPolicyStatus.cbSize], xmm0
0x180010a0f  sbb     edx, edx
0x180010a11  mov     [rsp+288h+var_218], r12
0x180010a16  and     edx, 7
0x180010a19  mov     [rsp+288h+pPolicyStatus.cbSize], 18h
0x180010a24  mov     [rsp+288h+pPolicyPara.cbSize], 10h
0x180010a2c  mov     [rsp+288h+pPolicyPara.dwFlags], edx
0x180010a30  test    al, 1
0x180010a32  jz      short loc_180010A4D
0x180010a34  lea     rax, [rsp+288h+var_70]
0x180010a3c  lea     rdx, ChainVerifyStart; int
0x180010a43  mov     [rsp+288h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x180010a48  call    McGenEventWrite_EventWriteTransfer
0x180010a4d  mov     rdx, [rsp+288h+pChainContext]; pChainContext
0x180010a52  lea     r9, [rsp+288h+pPolicyStatus]; pPolicyStatus
0x180010a5a  lea     r8, [rsp+288h+pPolicyPara]; pPolicyPara
0x180010a5f  mov     ecx, 4; pszPolicyOID
0x180010a64  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180010a6a  test    eax, eax
0x180010a6c  jz      loc_180010B31
0x180010a72  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x180010a79  jnz     loc_180010FB7
0x180010a7f  mov     r9d, [rsp+288h+pPolicyStatus.dwError]
0x180010a87  cmp     r9d, 80092012h
0x180010a8e  jz      loc_180010FD5
0x180010a94  cmp     r9d, 80092013h
0x180010a9b  jz      loc_180010B9C
0x180010aa1  mov     eax, r9d
0x180010aa4  and     eax, 1FFF0000h
0x180010aa9  cmp     eax, 90000h
0x180010aae  jz      loc_180010E2C
0x180010ab4  test    r9d, r9d
0x180010ab7  jnz     loc_180010B54
0x180010abd  lea     rsi, WPP_GLOBAL_Control
0x180010ac4  mov     rcx, [rsp+288h+pChainContext]; pChainContext
0x180010ac9  call    cs:__imp_CertFreeCertificateChain
0x180010acf  mov     rdx, [r14+18h]
0x180010ad3  lea     rcx, pszObjId; "2.5.29.19"
0x180010ada  mov     r8, [rdx+0C8h]; rgExtensions
0x180010ae1  mov     edx, [rdx+0C0h]; cExtensions
0x180010ae7  call    cs:__imp_CertFindExtension
0x180010aed  test    rax, rax
0x180010af0  jnz     loc_18008A8FE
0x180010af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180010afd  cmp     rcx, rsi
0x180010b00  jz      loc_18008A957
0x180010b06  test    byte ptr [rcx+1Ch], 4
0x180010b0a  jz      loc_18008A957
0x180010b10  mov     rcx, [rcx+10h]
0x180010b14  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180010b1b  mov     edx, 22h ; '"'
0x180010b20  call    WPP_SF_
0x180010b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b2c  jmp     loc_18008A957
0x180010b31  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x180010b38  jnz     loc_180010F99
0x180010b3e  call    cs:__imp_GetLastError
0x180010b44  mov     rcx, [rsp+288h+pChainContext]; pChainContext
0x180010b49  call    cs:__imp_CertFreeCertificateChain
0x180010b4f  jmp     loc_1800108FE
0x180010b54  cmp     r9d, 800B0112h
0x180010b5b  jnz     loc_18008A893
0x180010b61  mov     r9d, 80090325h; jumptable 000000018008A8B4 case -2146762487
0x180010b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b6e  cmp     rcx, rsi
0x180010b71  jz      loc_18008A8ED
0x180010b77  test    byte ptr [rcx+1Ch], 2
0x180010b7b  jz      loc_18008A8ED
0x180010b81  mov     rcx, [rcx+10h]
0x180010b85  lea     r8, WPP_d41a78d040ed38824cec345dbaaf9814_Traceguids
0x180010b8c  mov     edx, 1Eh
0x180010b91  call    WPP_SF_d
0x180010b96  nop
0x180010b97  jmp     loc_18008A8ED
0x180010b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ba3  lea     rsi, WPP_GLOBAL_Control
0x180010baa  cmp     rcx, rsi
0x180010bad  jz      loc_180010AC4
0x180010bb3  test    byte ptr [rcx+1Ch], 2
0x180010bb7  jz      loc_180010AC4
0x180010bbd  jmp     loc_18008A878
0x180010bc2  inc     ebx
0x180010bc4  jmp     loc_1800108BB
0x180010bc9  mov     rdi, [rsp+288h+SourceString]
0x180010bce  mov     ebx, 8009030Eh
0x180010bd3  test    cs:?g_dwEventLogging@@3KA, 1; ulong g_dwEventLogging
0x180010bda  jz      short loc_180010C1B
0x180010bdc  xorps   xmm0, xmm0
0x180010bdf  lea     rcx, [rsp+288h+DestinationString]; DestinationString
0x180010be7  mov     rdx, rdi; SourceString
0x180010bea  movups  xmmword ptr [rsp+288h+DestinationString.Length], xmm0
0x180010bf2  call    cs:__imp_RtlInitUnicodeString
0x180010bf8  mov     r8d, [rsp+288h+arg_20]
0x180010c00  lea     r9, [rsp+288h+DestinationString]
0x180010c08  lea     rdx, aDu; "du"
0x180010c0f  lea     rcx, SSLEVENT_NO_DEFAULT_SERVER_CRED; struct _EVENT_DESCRIPTOR *
0x180010c16  call    ?SchEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SchEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180010c1b  test    r12, r12
0x180010c1e  jnz     loc_180010E50
0x180010c24  test    r14, r14
0x180010c27  jnz     loc_180011014
0x180010c2d  test    r15, r15
0x180010c30  jnz     loc_180011022
0x180010c36  mov     rax, cs:WPP_GLOBAL_Control
0x180010c3d  cmp     rax, rsi
0x180010c40  jnz     loc_180011032
0x180010c46  mov     r13, [rsp+288h+var_38]
0x180010c4e  mov     eax, ebx
0x180010c50  mov     rbx, [rsp+288h+var_28]
0x180010c58  mov     r12, [rsp+288h+var_30]
0x180010c60  mov     rcx, [rsp+288h+var_40]
0x180010c68  xor     rcx, rsp; StackCookie
0x180010c6b  call    __security_check_cookie
0x180010c70  add     rsp, 268h
0x180010c77  pop     r15
0x180010c79  pop     r14
0x180010c7b  pop     rdi
0x180010c7c  pop     rsi
0x180010c7d  retn
0x180010c7e  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180010c85  cmp     rcx, rsi
0x180010c88  jnz     loc_180010DD3
0x180010c8e  mov     r13d, 1
0x180010c94  test    ebx, ebx
0x180010c96  jz      loc_1800108C9
0x180010c9c  cmp     rcx, rsi
0x180010c9f  jnz     loc_180011000
0x180010ca5  mov     rdi, cs:?m_pCredManager@CSslCredManager@@0PEAV1@EA; CSslCredManager * CSslCredManager::m_pCredManager
0x180010cac  lea     rax, [rsp+288h+var_1D0]
0x180010cb4  xorps   xmm0, xmm0
0x180010cb7  mov     [rsp+288h+var_130], rax
0x180010cbf  xorps   xmm1, xmm1
0x180010cc2  movaps  [rsp+288h+var_128], xmm0
0x180010cca  lea     rdx, [rsp+288h+var_138]; struct LSA_SCHANNEL_CRED *
0x180010cd2  movaps  [rsp+288h+var_118], xmm0
0x180010cda  movaps  [rsp+288h+var_108], xmm0
0x180010ce2  movaps  [rsp+288h+var_F8], xmm0
0x180010cea  movaps  [rsp+288h+var_E8], xmm0
0x180010cf2  movaps  [rsp+288h+var_D8], xmm0
0x180010cfa  movdqu  [rsp+288h+var_1D0+8], xmm0
0x180010d03  mov     dword ptr [rsp+288h+var_138], 4
0x180010d0e  movdqu  [rsp+288h+var_1C0+8], xmm1
0x180010d17  mov     [rsp+288h+var_134], 1
0x180010d22  movdqu  [rsp+288h+var_1B0+8], xmm0
0x180010d2b  mov     qword ptr [rsp+288h+var_1D0], r14
0x180010d33  call    ?DbgDumpSchannelCred@CSslCredManager@@AEAAXPEAULSA_SCHANNEL_CRED@@@Z; CSslCredManager::DbgDumpSchannelCred(LSA_SCHANNEL_CRED *)
  ... truncated ...
```
