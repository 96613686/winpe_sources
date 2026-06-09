# CSsl3TlsContext::DigestRemoteCertificate(uchar *,ulong)

- ea: `0x180022aa0`
- end: `0x1800233e6`
- name: `?DigestRemoteCertificate@CSsl3TlsContext@@IEAAKPEAEK@Z`
- size: `2374`
- prototype: `__int64 __fastcall(CSsl3TlsContext *this, unsigned __int8 *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f510`
- `0x18007c870`

## callees

- `0x180014240`
- `0x1800165a4`
- `0x1800214f0`
- `0x180021e64`
- `0x180022aa0`
- `0x18004bca4`
- `0x1800527b8`
- `0x180053df8`
- `0x180057c8c`
- `0x1800597b0`
- `0x180059ba0`
- `0x18005a100`
- `0x18005a160`
- `0x18005f1e4`
- `0x18006fc4c`
- `0x180076894`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800231ef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800231ef`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022f0f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022f0f`
- `ntdll!RtlReleaseResource` at `0x180022f58`
- `ntdll!RtlReleaseResource` at `0x180022f58`
- `ntdll!RtlInitUnicodeString` at `0x18008c74c`
- `ntdll!RtlInitUnicodeString` at `0x18008c759`
- `ntdll!RtlInitUnicodeString` at `0x18008c74c`
- `ntdll!RtlInitUnicodeString` at `0x18008c759`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18002311f`
- `CRYPT32!CertGetIntendedKeyUsage` at `0x18002311f`
- `CRYPT32!CertFreeCertificateContext` at `0x18002303c`
- `CRYPT32!CertFreeCertificateContext` at `0x1800233cd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800233db`
- `CRYPT32!CertFreeCertificateContext` at `0x18002303c`
- `CRYPT32!CertFreeCertificateContext` at `0x1800233cd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800233db`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022bea`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022bea`
- `CRYPT32!CertCreateCertificateContext` at `0x180022ba0`
- `CRYPT32!CertCreateCertificateContext` at `0x180022ba0`
- `CRYPT32!CertCompareCertificateName` at `0x18002302b`
- `CRYPT32!CertCompareCertificateName` at `0x18002302b`

## pseudocode

```c
__int64 __fastcall CSsl3TlsContext::DigestRemoteCertificate(
        CSsl3TlsContext *this,
        unsigned __int8 *a2,
        unsigned int a3,
        __int64 a4)
{
  const CERT_CONTEXT *v4; // rsi
  CSsl3TlsContext *v5; // r12
  unsigned __int16 v6; // r13
  unsigned __int16 v7; // r14
  int v8; // r15d
  unsigned __int8 *v9; // rdx
  int v10; // ebx
  unsigned int v11; // r8d
  __int64 *v12; // rdi
  DWORD v13; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  __int64 v15; // r9
  const CERT_CONTEXT *v16; // r15
  __int64 v17; // r9
  char v18; // r15
  unsigned __int8 v19; // bl
  int v20; // eax
  unsigned int *v21; // rdi
  int v22; // ebx
  int v23; // eax
  char v24; // al
  unsigned __int16 v25; // cx
  unsigned __int16 v26; // ax
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // cx
  unsigned __int16 v29; // cx
  unsigned __int16 v30; // dx
  unsigned int v31; // r15d
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  const WCHAR *v35; // rdx
  const WCHAR *v36; // rbx
  __int64 v37; // rdx
  int v38; // ebx
  int v39; // esi
  __int64 v40; // r14
  _DWORD *v41; // r14
  unsigned int v42; // r13d
  __int64 v43; // rbx
  void *v44; // rcx
  void *v45; // rcx
  const CERT_CONTEXT *v46; // rcx
  struct _SecPkgContext_ApplicationProtocol *v48; // rax
  unsigned int v49; // eax
  unsigned int v50; // esi
  int v51; // r15d
  _DWORD *v52; // rax
  unsigned __int8 *v53; // r12
  _DWORD *v54; // rdi
  const void *v55; // rdx
  size_t v56; // r8
  __int64 v57; // rbx
  unsigned int v58; // eax
  int v59; // esi
  struct _CERT_INFO *pCertInfo; // rdx
  int v61; // ebx
  __int64 v62; // r8
  __int64 v63; // rax
  const unsigned __int16 *v64; // rbx
  const wchar_t *v65; // r9
  __int64 v66; // r9
  struct CCipherSuiteInfo *v67; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v68[8]; // [rsp+30h] [rbp-D8h]
  unsigned __int8 v69; // [rsp+38h] [rbp-D0h]
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-B8h]
  int v71; // [rsp+60h] [rbp-A8h]
  struct _PUBLICKEY *pcbData; // [rsp+68h] [rbp-A0h] BYREF
  BYTE pbKeyUsage[4]; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v74; // [rsp+74h] [rbp-94h]
  unsigned int PublicKeyFromCert; // [rsp+78h] [rbp-90h]
  DWORD v76; // [rsp+7Ch] [rbp-8Ch]
  DWORD v77; // [rsp+80h] [rbp-88h]
  int v78; // [rsp+84h] [rbp-84h]
  unsigned __int8 *v79; // [rsp+88h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-78h] BYREF
  struct _PUBLICKEY *v81; // [rsp+A0h] [rbp-68h]
  const CERT_CONTEXT *v82; // [rsp+A8h] [rbp-60h]
  struct _UNICODE_STRING v83; // [rsp+B0h] [rbp-58h] BYREF
  char v84[8]; // [rsp+C8h] [rbp-40h] BYREF
  int v85; // [rsp+D0h] [rbp-38h]
  int v86; // [rsp+D4h] [rbp-34h]
  __int16 v87; // [rsp+748h] [rbp+640h]
  _WORD v88[16]; // [rsp+74Ah] [rbp+642h]
  unsigned __int16 v89; // [rsp+76Ah] [rbp+662h]
  wchar_t pvData[64]; // [rsp+778h] [rbp+670h] BYREF

  v4 = 0;
  *(_QWORD *)&DestinationString.Length = this;
  v87 = 0;
  v5 = this;
  v89 = 0;
  v6 = 0;
  v7 = 0;
  if ( a3 < 3 )
    goto LABEL_95;
  v8 = a2[2] + (((*a2 << 8) + a2[1]) << 8);
  v78 = v8;
  if ( a3 != v8 + 3 )
    goto LABEL_95;
  if ( !v8 )
  {
    if ( (*((_DWORD *)this + 22) & 0x800A2AAA) == 0 )
    {
      *((_BYTE *)this + 2272) = 1;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
      return 0;
    }
LABEL_95:
    LOBYTE(a4) = 42;
    CSslContext::SetErrorAndFatalAlert(this, 250, 2148074248LL, a4);
    return 2148074248LL;
  }
  v9 = a2 + 3;
  v10 = 0;
  v71 = 0;
  v11 = v8;
  PublicKeyFromCert = 0;
  *(_QWORD *)&v83.Length = v9;
  v74 = v8;
  v81 = 0;
  v82 = 0;
  while ( 2 )
  {
    v79 = v9;
    v12 = qword_1800931C0;
    if ( v11 <= 3 || (v13 = ((v9[1] + (*v9 << 8)) << 8) + v9[2], v76 = v13, v77 = v13 + 3, v11 < v13 + 3) )
    {
      v31 = -2146893048;
      LOBYTE(a4) = 42;
      CSslContext::SetErrorAndFatalAlert(v5, 250, 2148074248LL, a4);
      goto LABEL_59;
    }
    CertificateContext = CertCreateCertificateContext(1u, v9 + 3, v13);
    pCertContext = CertificateContext;
    v16 = CertificateContext;
    if ( !CertificateContext )
    {
      v31 = -2146893048;
      LOBYTE(v15) = 42;
      CSslContext::SetErrorAndFatalAlert(v5, 250, 2148074248LL, v15);
      v4 = 0;
      goto LABEL_59;
    }
    if ( (*((_DWORD *)v5 + 22) & 0xC0C00) == 0 )
      goto LABEL_20;
    if ( v10
      && CertCompareCertificateName(
           CertificateContext->dwCertEncodingType,
           &CertificateContext->pCertInfo->Issuer,
           &CertificateContext->pCertInfo->Subject) )
    {
LABEL_77:
      CertFreeCertificateContext(v16);
      goto LABEL_26;
    }
    LODWORD(pcbData) = 128;
    if ( !CertGetCertificateContextProperty(v16, 0x59u, pvData, (DWORD *)&pcbData)
      || ((unsigned int)pcbData >> 1) - 1 > 0x3F )
    {
LABEL_94:
      v31 = -2146893048;
      LOBYTE(v17) = 43;
      CSslContext::SetErrorAndFatalAlert(v5, 252, 2148074248LL, v17);
      v4 = pCertContext;
      goto LABEL_59;
    }
    if ( 2 * (unsigned __int64)(((unsigned int)pcbData >> 1) - 1) >= 0x80 )
      _report_rangecheckfailure();
    v18 = 0;
    pvData[((unsigned int)pcbData >> 1) - 1] = 0;
    v19 = 0;
    do
    {
      if ( v19 < 0xCu )
      {
        v20 = v7;
        if ( _bittest(&v20, v19) )
        {
          v18 = 1;
          goto LABEL_17;
        }
      }
      if ( wcsicmp((const wchar_t *)v12[2], pvData) )
        goto LABEL_17;
      if ( v19 >= 0xCu )
      {
        v24 = 0;
        goto LABEL_34;
      }
      v23 = v7;
      if ( _bittest(&v23, v19) )
        goto LABEL_33;
      if ( v6 < 0x10u )
      {
        v88[v6] = __ROR2__(qword_1800931C0[10 * v19], 8);
        v6 = ++v87;
        v7 = v89 | (1 << v19);
        v89 = v7;
LABEL_33:
        v24 = 1;
LABEL_34:
        v18 |= v24;
      }
LABEL_17:
      v12 += 10;
      ++v19;
    }
    while ( v12 < (__int64 *)&off_180093580 );
    v5 = *(CSsl3TlsContext **)&DestinationString.Length;
    if ( !v18 )
      goto LABEL_94;
    v16 = pCertContext;
    v4 = 0;
    v10 = v71;
LABEL_20:
    if ( v10 )
      goto LABEL_77;
    pcbData = 0;
    PublicKeyFromCert = GetPublicKeyFromCert(v16, &pcbData, 0);
    if ( PublicKeyFromCert )
    {
      v31 = -2146893048;
      LOBYTE(a4) = 43;
      CSslContext::SetErrorAndFatalAlert(v5, 251, 2148074248LL, a4);
      v4 = pCertContext;
      goto LABEL_59;
    }
    v21 = (unsigned int *)*((_QWORD *)v5 + 1);
    v22 = *((_DWORD *)v5 + 22) & 0x40051555;
    if ( v21 )
    {
      if ( *(_DWORD *)(*((_QWORD *)v5 + 13) + 260LL) )
      {
        v48 = v22
            ? (struct _SecPkgContext_ApplicationProtocol *)(*(__int64 (__fastcall **)(CSsl3TlsContext *))(*(_QWORD *)v5 + 96LL))(v5)
            : 0LL;
        v49 = IsRemoteCertificateBlacklisted(
                *(struct _TLS_PARAMETERS **)(*((_QWORD *)v5 + 13) + 264LL),
                *(_DWORD *)(*((_QWORD *)v5 + 13) + 260LL),
                v16,
                v48,
                (struct CCipherSuiteInfo *)v21,
                v22 != 0,
                v69);
        v50 = v49;
        if ( v49 )
        {
          if ( v49 == -2146893007 )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
            }
            LOBYTE(a4) = 43;
            CSslContext::SetErrorAndFatalAlert(v5, 251, 2148074289LL, a4);
          }
          SPExternalFree(pcbData);
          v31 = v50;
          v4 = pCertContext;
          goto LABEL_59;
        }
      }
      if ( !v22 && v21[9] == 9216 )
      {
        v58 = v21[8];
        switch ( v58 )
        {
          case 0xAE06u:
            goto LABEL_86;
          case 0xA400u:
            v59 = 32;
            goto LABEL_87;
          case 0xAA02u:
LABEL_86:
            v59 = 128;
LABEL_87:
            pCertInfo = v16->pCertInfo;
            *(_DWORD *)pbKeyUsage = 0;
            if ( CertGetIntendedKeyUsage(0x10001u, pCertInfo, pbKeyUsage, 4u) )
            {
              a4 = *(unsigned int *)pbKeyUsage;
              v61 = *(_DWORD *)pbKeyUsage & v59;
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_89c254830434370c9b8c7f7d2950a963_Traceguids,
                  *(unsigned int *)pbKeyUsage,
                  v59);
              }
              if ( !v61 )
              {
                v63 = (*(__int64 (__fastcall **)(CSsl3TlsContext *))(*(_QWORD *)v5 + 352LL))(v5);
                v64 = (const unsigned __int16 *)v63;
                if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v65 = L"NULL";
                  if ( v63 )
                    LODWORD(v65) = v63;
                  WPP_SF_Sdd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    53,
                    (unsigned int)WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids,
                    (_DWORD)v65,
                    v21[8],
                    v21[9]);
                }
                CSchannelTelemetryContext::LogCertKeyUsageError(v21[8], v21[9], v64);
              }
            }
            break;
        }
      }
      v4 = 0;
      v10 = v71;
      v81 = pcbData;
      v82 = v16;
LABEL_26:
      ++v10;
      v11 = -3 - v76 + v74;
      v71 = v10;
      v74 = v11;
      if ( v11 )
      {
        v9 = &v79[v77];
        continue;
      }
      if ( (*((_DWORD *)v5 + 22) & 0xC0C00) != 0 )
      {
        if ( !v6 || !v7 )
          goto LABEL_45;
        v25 = *((_WORD *)v5 + 1114);
        v26 = CTlsSignatureSuiteList::RsaSha256Flags;
        if ( (v25 & CTlsSignatureSuiteList::RsaSha256Flags) == 0 )
          v26 = 0;
        v27 = v25 | v26;
        v28 = CTlsSignatureSuiteList::RsaSha384Flags;
        if ( (v27 & CTlsSignatureSuiteList::RsaSha384Flags) == 0 )
          v28 = 0;
        v29 = v27 | v28;
        v30 = (v29 & CTlsSignatureSuiteList::RsaSha512Flags) != 0 ? CTlsSignatureSuiteList::RsaSha512Flags : 0;
        if ( ((unsigned __int16)~(v30 | v29) & v7) != 0 )
        {
LABEL_45:
          v31 = -2146893048;
          v32 = (*(__int64 (__fastcall **)(CSsl3TlsContext *))(*(_QWORD *)v5 + 352LL))(v5);
          v33 = *((_QWORD *)v5 + 231);
          if ( !*(_WORD *)(v33 + 34) )
          {
            *(_WORD *)(v33 + 34) = 252;
            *(_DWORD *)(v33 + 36) = -2146893048;
          }
          v34 = *((_QWORD *)v5 + 13);
          v35 = &Class;
          *((_WORD *)v5 + 60) = 10242;
          v36 = &Class;
          if ( v32 )
            v36 = (const WCHAR *)v32;
          if ( v34 )
          {
            LODWORD(v4) = *(_DWORD *)(v34 + 276);
            v35 = (const WCHAR *)(v34 + 280);
          }
          if ( (g_dwEventLogging & 4) != 0 )
          {
            DestinationString = 0;
            v83 = 0;
            RtlInitUnicodeString(&DestinationString, v35);
            RtlInitUnicodeString(&v83, v36);
            *(_DWORD *)v68 = 252;
            LODWORD(v67) = 40;
            SchEventWrite(
              &SSLEVENT_GENERATE_FATAL_ALERT,
              L"duddu",
              (unsigned int)v4,
              &DestinationString,
              v67,
              *(_QWORD *)v68,
              &v83);
          }
          memset_0(v84, 0, 0x680u);
          v37 = *((_QWORD *)v5 + 1);
          if ( v37 )
            v38 = *(_DWORD *)(v37 + 28);
          else
            v38 = 0;
          v39 = *((unsigned __int16 *)v5 + 17);
          v40 = *((_QWORD *)v5 + 232);
          v86 = *((_DWORD *)v5 + 4);
          v85 = v38;
          if ( v37 )
          {
            v62 = *((_QWORD *)v5 + 14);
            if ( v62 )
              CSchannelTelemetryContext::LogKeyExchange(
                (CSsl3TlsContext *)((char *)v5 + 144),
                *(_DWORD *)(v37 + 32),
                *(_DWORD *)(*(_QWORD *)(v62 + 40) + 8LL));
          }
          if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
          {
            *((_DWORD *)v5 + 47) = v86;
            *((_BYTE *)v5 + 260) = 40;
            *((_DWORD *)v5 + 64) = -2146893048;
            *((_DWORD *)v5 + 66) = 252;
            *((_DWORD *)v5 + 46) = v38;
            *((_DWORD *)v5 + 48) = v39;
            *((_QWORD *)v5 + 35) = v40;
            *((_BYTE *)v5 + 169) = 1;
          }
          CSchannelTelemetryContext::LogDebugTraceHandshakeInfo((CSsl3TlsContext *)((char *)v5 + 144), L"Fatal Error");
          v4 = 0;
          goto LABEL_59;
        }
      }
      v51 = v78;
      v42 = v78 + v10;
      if ( LsaTable )
        v52 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(v42);
      else
        v52 = LocalAlloc(0x40u, v42);
      v41 = v52;
      if ( v52 )
      {
        v53 = *(unsigned __int8 **)&v83.Length;
        v54 = v52;
        do
        {
          v55 = v53 + 3;
          v56 = v53[2] + ((v53[1] + (*v53 << 8)) << 8);
          *v54 = v56;
          v51 += -3 - v56;
          v57 = (unsigned int)v56;
          v53 += (unsigned int)(v56 + 3);
          memcpy_0(v54 + 1, v55, v56);
          v54 = (_DWORD *)((char *)v54 + v57 + 4);
        }
        while ( v51 );
        v5 = *(CSsl3TlsContext **)&DestinationString.Length;
        v4 = 0;
        v31 = PublicKeyFromCert;
      }
      else
      {
        v4 = 0;
        v31 = 14;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_0a0227a0bafb31ee031925f0a4bfd03a_Traceguids);
      SPExternalFree(pcbData);
      v31 = -1073741595;
      LOBYTE(v66) = 80;
      CSslContext::SetErrorAndFatalAlert(v5, 254, 3221225701LL, v66);
      v4 = pCertContext;
LABEL_59:
      v41 = 0;
      v42 = 0;
    }
    break;
  }
  v43 = *(_QWORD *)(*((_QWORD *)v5 + 14) + 40LL);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v43 + 80), 1u);
  v44 = *(void **)(v43 + 16);
  if ( v44 )
    SPExternalFree(v44);
  v45 = *(void **)(v43 + 32);
  *(_QWORD *)(v43 + 16) = v41;
  *(_DWORD *)(v43 + 24) = v42;
  if ( v45 )
    SPExternalFree(v45);
  v46 = *(const CERT_CONTEXT **)(v43 + 40);
  *(_QWORD *)(v43 + 32) = v81;
  if ( v46 )
    CertFreeCertificateContext(v46);
  *(_QWORD *)(v43 + 40) = v82;
  RtlReleaseResource((PRTL_RESOURCE)(v43 + 80));
  if ( v4 )
    CertFreeCertificateContext(v4);
  return v31;
}

```

## disassembly

```asm
0x180022aa0  mov     r11, rsp
0x180022aa3  push    rbp
0x180022aa4  push    rsi
0x180022aa5  push    r12
0x180022aa7  push    r13
0x180022aa9  push    r14
0x180022aab  push    r15
0x180022aad  lea     rbp, [r11-738h]
0x180022ab4  sub     rsp, 808h
0x180022abb  mov     rax, cs:__security_cookie
0x180022ac2  xor     rax, rsp
0x180022ac5  mov     [rbp+730h+var_40], rax
0x180022acc  xor     esi, esi
0x180022ace  mov     qword ptr [rbp+730h+DestinationString.Length], rcx
0x180022ad2  mov     [rbp+730h+var_F0], si
0x180022ad9  mov     r12, rcx
0x180022adc  mov     [rbp+730h+var_CE], si
0x180022ae3  mov     r13d, esi
0x180022ae6  mov     r14d, esi
0x180022ae9  cmp     r8d, 3
0x180022aed  jb      loc_18002318B
0x180022af3  movzx   eax, byte ptr [rdx]
0x180022af6  movzx   r15d, byte ptr [rdx+1]
0x180022afb  shl     eax, 8
0x180022afe  add     r15d, eax
0x180022b01  movzx   eax, byte ptr [rdx+2]
0x180022b05  shl     r15d, 8
0x180022b09  add     r15d, eax
0x180022b0c  mov     [rsp+830h+var_7B4], r15d
0x180022b11  lea     eax, [r15+3]
0x180022b15  cmp     r8d, eax
0x180022b18  jnz     loc_18002318B
0x180022b1e  test    r15d, r15d
0x180022b21  jz      loc_18002323C
0x180022b27  mov     [r11+18h], rbx
0x180022b2b  add     rdx, 3
0x180022b2f  mov     ebx, esi
0x180022b31  mov     [r11-38h], rdi
0x180022b35  mov     dword ptr [rsp+830h+var_7D8], ebx
0x180022b39  mov     r8d, r15d
0x180022b3c  mov     qword ptr [rsp+830h+var_7E0], rsi
0x180022b41  mov     [rsp+830h+var_7C0], esi
0x180022b45  mov     qword ptr [rbp+730h+var_788.Length], rdx
0x180022b49  mov     [rsp+830h+var_7C4], r15d
0x180022b4e  mov     [rbp+730h+var_798], rsi
0x180022b52  mov     [rbp+730h+var_790], rsi
0x180022b56  mov     [rbp+730h+var_7B0], rdx
0x180022b5a  lea     rdi, qword_1800931C0
0x180022b61  cmp     r8d, 3
0x180022b65  jbe     loc_18002339B
0x180022b6b  movzx   eax, byte ptr [rdx+1]
0x180022b6f  movzx   ecx, byte ptr [rdx]
0x180022b72  shl     ecx, 8
0x180022b75  add     ecx, eax
0x180022b77  movzx   eax, byte ptr [rdx+2]
0x180022b7b  shl     ecx, 8
0x180022b7e  add     eax, ecx
0x180022b80  mov     [rsp+830h+var_7BC], eax
0x180022b84  lea     ecx, [rax+3]
0x180022b87  mov     [rsp+830h+var_7B8], ecx
0x180022b8b  cmp     r8d, ecx
0x180022b8e  jb      loc_18002339B
0x180022b94  add     rdx, 3; pbCertEncoded
0x180022b98  mov     r8d, eax; cbCertEncoded
0x180022b9b  mov     ecx, 1; dwCertEncodingType
0x180022ba0  call    cs:__imp_CertCreateCertificateContext
0x180022ba6  mov     [rsp+830h+pCertContext], rax
0x180022bab  mov     r15, rax
0x180022bae  test    rax, rax
0x180022bb1  jz      loc_1800231A8
0x180022bb7  test    dword ptr [r12+58h], 0C0C00h
0x180022bc0  jz      loc_180022C80
0x180022bc6  test    ebx, ebx
0x180022bc8  jnz     loc_18002301D
0x180022bce  lea     r9, [rsp+830h+pcbData]; pcbData
0x180022bd3  mov     [rsp+830h+pcbData], 80h
0x180022bdb  lea     r8, [rbp+730h+pvData]; pvData
0x180022be2  mov     edx, 59h ; 'Y'; dwPropId
0x180022be7  mov     rcx, r15; pCertContext
0x180022bea  call    cs:__imp_CertGetCertificateContextProperty
0x180022bf0  test    eax, eax
0x180022bf2  jz      loc_180023168
0x180022bf8  mov     ecx, [rsp+830h+pcbData]
0x180022bfc  shr     ecx, 1
0x180022bfe  lea     eax, [rcx-1]
0x180022c01  cmp     eax, 3Fh ; '?'
0x180022c04  ja      loc_180023168
0x180022c0a  dec     ecx
0x180022c0c  add     rcx, rcx
0x180022c0f  cmp     rcx, 80h
0x180022c16  jnb     loc_1800232C1
0x180022c1c  xor     r15b, r15b
0x180022c1f  mov     [rbp+rcx+730h+pvData], si
0x180022c27  xor     bl, bl
0x180022c29  lea     r12, off_180093580
0x180022c30  movzx   esi, bl
0x180022c33  cmp     bl, 0Ch
0x180022c36  jnb     short loc_180022C45
0x180022c38  movzx   eax, r14w
0x180022c3c  bt      eax, esi
0x180022c3f  jb      loc_180022D2D
0x180022c45  mov     rcx, [rdi+10h]; String1
0x180022c49  lea     rdx, [rbp+730h+pvData]; String2
0x180022c50  call    _wcsicmp
0x180022c55  test    eax, eax
0x180022c57  jz      loc_180022D35
0x180022c5d  add     rdi, 50h ; 'P'
0x180022c61  inc     bl
0x180022c63  cmp     rdi, r12
0x180022c66  jb      short loc_180022C30
0x180022c68  mov     r12, qword ptr [rbp+730h+DestinationString.Length]
0x180022c6c  test    r15b, r15b
0x180022c6f  jz      loc_180023168
0x180022c75  mov     r15, [rsp+830h+pCertContext]
0x180022c7a  xor     esi, esi
0x180022c7c  mov     ebx, dword ptr [rsp+830h+var_7D8]
0x180022c80  test    ebx, ebx
0x180022c82  jnz     loc_180023039
0x180022c88  xor     r8d, r8d; enum _eTlsSignatureAlgorithm *
0x180022c8b  mov     qword ptr [rsp+830h+pcbData], rsi
0x180022c90  lea     rdx, [rsp+830h+pcbData]; struct _PUBLICKEY **
0x180022c95  mov     rcx, r15; struct _CERT_CONTEXT *
0x180022c98  call    ?GetPublicKeyFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_PUBLICKEY@@PEAW4_eTlsSignatureAlgorithm@@@Z; GetPublicKeyFromCert(_CERT_CONTEXT const *,_PUBLICKEY * *,_eTlsSignatureAlgorithm *)
0x180022c9d  mov     [rsp+830h+var_7C0], eax
0x180022ca1  test    eax, eax
0x180022ca3  jnz     loc_18002320F
0x180022ca9  mov     ebx, [r12+58h]
0x180022cae  mov     rdi, [r12+8]
0x180022cb3  and     ebx, 40051555h
0x180022cb9  setnbe  sil
0x180022cbd  test    rdi, rdi
0x180022cc0  jz      loc_1800232C7
0x180022cc6  mov     rax, [r12+68h]
0x180022ccb  cmp     dword ptr [rax+104h], 0
0x180022cd2  ja      loc_180022F9B
0x180022cd8  test    ebx, ebx
0x180022cda  jz      loc_1800230E3
0x180022ce0  mov     rax, qword ptr [rsp+830h+pcbData]
0x180022ce5  xor     esi, esi
0x180022ce7  mov     ebx, dword ptr [rsp+830h+var_7D8]
0x180022ceb  mov     [rbp+730h+var_798], rax
0x180022cef  mov     [rbp+730h+var_790], r15
0x180022cf3  mov     r8d, [rsp+830h+var_7C4]
0x180022cf8  inc     ebx
0x180022cfa  mov     eax, 0FFFFFFFDh
0x180022cff  mov     [rsp+830h+pCertContext], rsi
0x180022d04  sub     eax, [rsp+830h+var_7BC]
0x180022d08  add     r8d, eax
0x180022d0b  mov     dword ptr [rsp+830h+var_7D8], ebx
0x180022d0f  mov     [rsp+830h+var_7C4], r8d
0x180022d14  test    r8d, r8d
0x180022d17  jz      loc_180022DAA
0x180022d1d  mov     eax, [rsp+830h+var_7B8]
0x180022d21  mov     rdx, [rbp+730h+var_7B0]
0x180022d25  add     rdx, rax
0x180022d28  jmp     loc_180022B56
0x180022d2d  mov     r15b, 1
0x180022d30  jmp     loc_180022C5D
0x180022d35  cmp     bl, 0Ch
0x180022d38  jnb     loc_18002328C
0x180022d3e  movzx   eax, r14w
0x180022d42  bt      eax, esi
0x180022d45  jb      short loc_180022DA0
0x180022d47  cmp     r13w, 10h
0x180022d4c  jnb     loc_180023232
0x180022d52  movzx   eax, bl
0x180022d55  lea     rcx, [rax+rax*4]
0x180022d59  add     rcx, rcx
0x180022d5c  lea     rax, qword_1800931C0
0x180022d63  movzx   edx, word ptr [rax+rcx*8]
0x180022d67  movzx   eax, r13w
0x180022d6b  ror     dx, 8
0x180022d6f  mov     [rbp+rax*2+730h+var_EE], dx
0x180022d77  movzx   r13d, [rbp+730h+var_F0]
0x180022d7f  movzx   eax, [rbp+730h+var_CE]
0x180022d86  inc     r13w
0x180022d8a  bts     eax, esi
0x180022d8d  mov     [rbp+730h+var_F0], r13w
0x180022d95  movzx   r14d, ax
0x180022d99  mov     [rbp+730h+var_CE], ax
0x180022da0  mov     al, 1
0x180022da2  or      r15b, al
0x180022da5  jmp     loc_180022C5D
0x180022daa  test    dword ptr [r12+58h], 0C0C00h
0x180022db3  jz      loc_180023047
0x180022db9  test    r13w, r13w
0x180022dbd  jz      short loc_180022E19
0x180022dbf  test    r14w, r14w
0x180022dc3  jz      short loc_180022E19
0x180022dc5  movzx   ecx, word ptr [r12+8B4h]
0x180022dce  movzx   eax, cs:?RsaSha256Flags@CTlsSignatureSuiteList@@0GA; ushort CTlsSignatureSuiteList::RsaSha256Flags
0x180022dd5  test    ax, cx
0x180022dd8  jz      loc_180023303
0x180022dde  or      ax, cx
0x180022de1  movzx   ecx, cs:?RsaSha384Flags@CTlsSignatureSuiteList@@0GA; ushort CTlsSignatureSuiteList::RsaSha384Flags
0x180022de8  test    cx, ax
0x180022deb  jz      loc_18002330A
0x180022df1  or      cx, ax
0x180022df4  movzx   eax, cs:?RsaSha512Flags@CTlsSignatureSuiteList@@0GA; ushort CTlsSignatureSuiteList::RsaSha512Flags
0x180022dfb  test    ax, cx
0x180022dfe  jz      loc_1800231E0
0x180022e04  mov     edx, eax
0x180022e06  movzx   ecx, cx
0x180022e09  or      ecx, edx
0x180022e0b  movzx   eax, r14w
0x180022e0f  not     ecx
0x180022e11  test    eax, ecx
0x180022e13  jz      loc_180023047
0x180022e19  mov     rax, [r12]
0x180022e1d  mov     rcx, r12
0x180022e20  mov     r15d, 80090308h
0x180022e26  mov     rax, [rax+160h]
0x180022e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e32  mov     rcx, rax
0x180022e35  mov     edi, 0FCh
0x180022e3a  mov     rax, [r12+738h]
0x180022e42  cmp     word ptr [rax+22h], 0
0x180022e47  jnz     short loc_180022E51
0x180022e49  mov     [rax+22h], di
0x180022e4d  mov     [rax+24h], r15d
0x180022e51  mov     rax, [r12+68h]
0x180022e56  lea     rdx, Class
0x180022e5d  test    rcx, rcx
0x180022e60  mov     word ptr [r12+78h], 2802h
0x180022e68  mov     rbx, rdx
0x180022e6b  cmovnz  rbx, rcx
0x180022e6f  test    rax, rax
0x180022e72  jz      short loc_180022E81
0x180022e74  mov     esi, [rax+114h]
0x180022e7a  lea     rdx, [rax+118h]; SourceString
0x180022e81  test    cs:?g_dwEventLogging@@3KA, 4; ulong g_dwEventLogging
0x180022e88  jnz     loc_18008C73A
0x180022e8e  xor     edx, edx; Val
0x180022e90  lea     rcx, [rbp+730h+var_770]; void *
0x180022e94  mov     r8d, 680h; Size
0x180022e9a  call    memset_0
0x180022e9f  mov     rdx, [r12+8]
0x180022ea4  test    rdx, rdx
0x180022ea7  jz      loc_180023161
0x180022ead  mov     ebx, [rdx+1Ch]
0x180022eb0  mov     eax, [r12+10h]
0x180022eb5  movzx   esi, word ptr [r12+22h]
0x180022ebb  mov     r14, [r12+740h]
0x180022ec3  mov     [rbp+730h+var_768+4], eax
0x180022ec6  mov     [rbp+730h+var_768], ebx
0x180022ec9  test    rdx, rdx
0x180022ecc  jnz     loc_180023311
0x180022ed2  cmp     cs:?s_IsTelemetryGloballyInitialized@CTelemetryContext@@1_NA, 0; bool CTelemetryContext::s_IsTelemetryGloballyInitialized
0x180022ed9  lea     rcx, [r12+90h]; this
0x180022ee1  jnz     loc_18002333C
0x180022ee7  lea     rdx, aFatalError; "Fatal Error"
0x180022eee  call    ?LogDebugTraceHandshakeInfo@CSchannelTelemetryContext@@QEAAXQEAG@Z; CSchannelTelemetryContext::LogDebugTraceHandshakeInfo(ushort * const)
0x180022ef3  mov     rsi, [rsp+830h+pCertContext]
0x180022ef8  mov     r14, qword ptr [rsp+830h+var_7E0]
0x180022efd  mov     r13d, r14d
0x180022f00  mov     rax, [r12+70h]
0x180022f05  mov     dl, 1; Wait
0x180022f07  mov     rbx, [rax+28h]
0x180022f0b  lea     rcx, [rbx+50h]; Resource
0x180022f0f  call    cs:__imp_RtlAcquireResourceExclusive
0x180022f15  mov     rcx, [rbx+10h]; void *
0x180022f19  test    rcx, rcx
0x180022f1c  jnz     loc_1800233B9
0x180022f22  mov     rcx, [rbx+20h]; void *
0x180022f26  mov     [rbx+10h], r14
0x180022f2a  mov     [rbx+18h], r13d
0x180022f2e  test    rcx, rcx
0x180022f31  jnz     loc_1800233C3
0x180022f37  mov     rcx, [rbx+28h]; pCertContext
0x180022f3b  mov     rax, [rbp+730h+var_798]
0x180022f3f  mov     [rbx+20h], rax
0x180022f43  test    rcx, rcx
0x180022f46  jnz     loc_1800233CD
0x180022f4c  mov     rax, [rbp+730h+var_790]
0x180022f50  lea     rcx, [rbx+50h]; Resource
0x180022f54  mov     [rbx+28h], rax
0x180022f58  call    cs:__imp_RtlReleaseResource
0x180022f5e  test    rsi, rsi
0x180022f61  jnz     loc_1800233D8
0x180022f67  mov     rbx, [rsp+830h+arg_10]
0x180022f6f  mov     eax, r15d
0x180022f72  mov     rdi, [rsp+800h]
0x180022f7a  mov     rcx, [rbp+730h+var_40]
0x180022f81  xor     rcx, rsp; StackCookie
0x180022f84  call    __security_check_cookie
0x180022f89  add     rsp, 808h
0x180022f90  pop     r15
0x180022f92  pop     r14
0x180022f94  pop     r13
0x180022f96  pop     r12
0x180022f98  pop     rsi
0x180022f99  pop     rbp
0x180022f9a  retn
0x180022f9b  test    ebx, ebx
0x180022f9d  jnz     loc_1800231CB
0x180022fa3  xor     eax, eax
0x180022fa5  mov     rcx, [r12+68h]
0x180022faa  mov     r9, rax; struct _SecPkgContext_ApplicationProtocol *
0x180022fad  mov     [rsp+830h+var_808], sil; unsigned __int8
0x180022fb2  mov     r8, r15; pCertContext
  ... truncated ...
```
