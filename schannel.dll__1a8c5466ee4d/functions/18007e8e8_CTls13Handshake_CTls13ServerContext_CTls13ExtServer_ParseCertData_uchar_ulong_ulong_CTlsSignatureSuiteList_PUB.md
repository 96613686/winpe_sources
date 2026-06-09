# CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::ParseCertData(uchar *,ulong,ulong,CTlsSignatureSuiteList &,_PUBLICKEY * &,_CERT_CONTEXT const * &)

- ea: `0x18007e8e8`
- end: `0x18007eb0c`
- name: `?ParseCertData@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@IEAAKPEAEKKAEAVCTlsSignatureSuiteList@@AEAPEAU_PUBLICKEY@@AEAPEBU_CERT_CONTEXT@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(int, int, int, int, CTlsSignatureSuiteList *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007eb14`

## callees

- `0x180014240`
- `0x1800214f0`
- `0x18003c430`
- `0x1800527b8`
- `0x180053df8`
- `0x180057c8c`
- `0x18007e8e8`
- `0x180091010`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18007ead6`
- `CRYPT32!CertFreeCertificateContext` at `0x18007ead6`
- `CRYPT32!CertCreateCertificateContext` at `0x18007e916`
- `CRYPT32!CertCreateCertificateContext` at `0x18007e916`
- `CRYPT32!CertCompareCertificateName` at `0x18007e970`
- `CRYPT32!CertCompareCertificateName` at `0x18007e970`

## pseudocode

```c
__int64 __fastcall CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::ParseCertData(
        __int64 a1,
        const BYTE *a2,
        DWORD a3,
        __int64 a4,
        CTlsSignatureSuiteList *a5,
        struct _PUBLICKEY **a6,
        const CERT_CONTEXT **a7)
{
  int v7; // edi
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v10; // rsi
  __int64 v11; // rcx
  struct _CRYPTOAPI_BLOB *pCertInfo; // rdx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  struct _PUBLICKEY **v15; // r14
  const CERT_CONTEXT **v16; // r15
  unsigned int PublicKeyFromCert; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rdi
  unsigned __int8 v21; // r13
  struct CCipherSuiteInfo *v22; // r12
  struct _SecPkgContext_ApplicationProtocol *v23; // rax
  unsigned int v24; // eax
  __int64 v25; // r9
  unsigned int v26; // edi
  unsigned __int8 v28; // [rsp+30h] [rbp-58h]
  struct _PUBLICKEY *v29; // [rsp+98h] [rbp+10h] BYREF

  v7 = a4;
  if ( !a2 || !a3 )
  {
    v11 = *(_QWORD *)(a1 + 8);
    goto LABEL_36;
  }
  CertificateContext = CertCreateCertificateContext(1u, a2, a3);
  v10 = CertificateContext;
  if ( CertificateContext )
  {
    pCertInfo = (struct _CRYPTOAPI_BLOB *)CertificateContext->pCertInfo;
    v29 = 0;
    if ( !pCertInfo )
    {
      LOBYTE(a4) = 42;
      v13 = 250;
LABEL_7:
      v14 = -2146893048;
      CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), v13, 2148074248LL, a4);
LABEL_33:
      CertFreeCertificateContext(v10);
      return v14;
    }
    if ( (!v7 || !CertCompareCertificateName(CertificateContext->dwCertEncodingType, pCertInfo + 3, pCertInfo + 5))
      && !CTlsSignatureSuiteList::AddCertificateSignatureSuite(a5, v10) )
    {
      LOBYTE(a4) = 43;
      v13 = 252;
      goto LABEL_7;
    }
    v14 = 0;
    if ( v7 )
      goto LABEL_33;
    v15 = a6;
    if ( !*a6 )
    {
      v16 = a7;
      if ( !*a7 )
      {
        PublicKeyFromCert = GetPublicKeyFromCert(v10, &v29, 0);
        v19 = *(_QWORD *)(a1 + 8);
        v14 = PublicKeyFromCert;
        if ( PublicKeyFromCert )
        {
          LOBYTE(v18) = 43;
          CSslContext::SetErrorAndFatalAlert(v19, 251, PublicKeyFromCert, v18);
          goto LABEL_31;
        }
        v20 = *(_QWORD *)(v19 + 104);
        if ( v20 )
        {
          v21 = (*(_DWORD *)(v19 + 88) & 0x40051555) != 0;
          if ( !*(_DWORD *)(v20 + 260)
            || ((v22 = *(struct CCipherSuiteInfo **)(v19 + 8), (*(_DWORD *)(v19 + 88) & 0x40051555) == 0)
              ? (v23 = 0)
              : (v23 = (struct _SecPkgContext_ApplicationProtocol *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 96LL))(v19)),
                v24 = IsRemoteCertificateBlacklisted(
                        *(struct _TLS_PARAMETERS **)(v20 + 264),
                        *(_DWORD *)(v20 + 260),
                        v10,
                        v23,
                        v22,
                        v21,
                        v28),
                (v26 = v24) == 0) )
          {
            *v15 = v29;
            *v16 = v10;
            return v14;
          }
          if ( v24 == -2146893007 )
          {
            if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids);
            }
            LOBYTE(v25) = 43;
            CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), 251, 2148074289LL, v25);
          }
          v14 = v26;
          goto LABEL_31;
        }
      }
    }
    v14 = -2146893052;
LABEL_31:
    if ( v29 )
      SPExternalFree(v29);
    goto LABEL_33;
  }
  v11 = *(_QWORD *)(a1 + 8);
LABEL_36:
  LOBYTE(a4) = 42;
  CSslContext::SetErrorAndFatalAlert(v11, 250, 2148074248LL, a4);
  return 2148074248LL;
}

```

## disassembly

```asm
0x18007e8e8  push    rbx
0x18007e8ea  push    rbp
0x18007e8eb  push    rsi
0x18007e8ec  push    rdi
0x18007e8ed  push    r12
0x18007e8ef  push    r13
0x18007e8f1  push    r14
0x18007e8f3  push    r15
0x18007e8f5  sub     rsp, 48h
0x18007e8f9  mov     edi, r9d
0x18007e8fc  mov     rbp, rcx
0x18007e8ff  test    rdx, rdx
0x18007e902  jz      loc_18007EAE0
0x18007e908  test    r8d, r8d
0x18007e90b  jz      loc_18007EAE0
0x18007e911  mov     ecx, 1; dwCertEncodingType
0x18007e916  call    cs:__imp_CertCreateCertificateContext
0x18007e91c  mov     rsi, rax
0x18007e91f  test    rax, rax
0x18007e922  jnz     short loc_18007E92D
0x18007e924  mov     rcx, [rbp+8]
0x18007e928  jmp     loc_18007EAE4
0x18007e92d  mov     rdx, [rax+18h]
0x18007e931  mov     [rsp+88h+arg_8], 0
0x18007e93d  test    rdx, rdx
0x18007e940  jnz     short loc_18007E962
0x18007e942  mov     r9b, 2Ah ; '*'
0x18007e945  mov     edx, 0FAh
0x18007e94a  mov     rcx, [rbp+8]
0x18007e94e  mov     edi, 80090308h
0x18007e953  mov     r8d, edi
0x18007e956  mov     ebx, edi
0x18007e958  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18007e95d  jmp     loc_18007EAD3
0x18007e962  test    edi, edi
0x18007e964  jz      short loc_18007E97A
0x18007e966  mov     ecx, [rax]; dwCertEncodingType
0x18007e968  lea     r8, [rdx+50h]; pCertName2
0x18007e96c  add     rdx, 30h ; '0'; pCertName1
0x18007e970  call    cs:__imp_CertCompareCertificateName
0x18007e976  test    eax, eax
0x18007e978  jnz     short loc_18007E998
0x18007e97a  mov     rcx, [rsp+88h+arg_20]; this
0x18007e982  mov     rdx, rsi; struct _CERT_CONTEXT *
0x18007e985  call    ?AddCertificateSignatureSuite@CTlsSignatureSuiteList@@QEAAEPEBU_CERT_CONTEXT@@@Z; CTlsSignatureSuiteList::AddCertificateSignatureSuite(_CERT_CONTEXT const *)
0x18007e98a  test    al, al
0x18007e98c  jnz     short loc_18007E998
0x18007e98e  mov     r9b, 2Bh ; '+'
0x18007e991  mov     edx, 0FCh
0x18007e996  jmp     short loc_18007E94A
0x18007e998  xor     ebx, ebx
0x18007e99a  test    edi, edi
0x18007e99c  jnz     loc_18007EAD3
0x18007e9a2  mov     r14, [rsp+88h+arg_28]
0x18007e9aa  cmp     [r14], rbx
0x18007e9ad  jnz     loc_18007EABC
0x18007e9b3  mov     r15, [rsp+88h+arg_30]
0x18007e9bb  cmp     [r15], rbx
0x18007e9be  jnz     loc_18007EABC
0x18007e9c4  xor     r8d, r8d; enum _eTlsSignatureAlgorithm *
0x18007e9c7  lea     rdx, [rsp+88h+arg_8]; struct _PUBLICKEY **
0x18007e9cf  mov     rcx, rsi; struct _CERT_CONTEXT *
0x18007e9d2  call    ?GetPublicKeyFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_PUBLICKEY@@PEAW4_eTlsSignatureAlgorithm@@@Z; GetPublicKeyFromCert(_CERT_CONTEXT const *,_PUBLICKEY * *,_eTlsSignatureAlgorithm *)
0x18007e9d7  mov     rcx, [rbp+8]
0x18007e9db  mov     ebx, eax
0x18007e9dd  test    eax, eax
0x18007e9df  jz      short loc_18007E9F6
0x18007e9e1  mov     r9b, 2Bh ; '+'
0x18007e9e4  mov     r8d, eax
0x18007e9e7  mov     edx, 0FBh
0x18007e9ec  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18007e9f1  jmp     loc_18007EAC1
0x18007e9f6  mov     rdi, [rcx+68h]
0x18007e9fa  test    rdi, rdi
0x18007e9fd  jz      loc_18007EABC
0x18007ea03  mov     eax, [rcx+58h]
0x18007ea06  and     eax, 40051555h
0x18007ea0b  setnbe  r13b
0x18007ea0f  cmp     dword ptr [rdi+104h], 0
0x18007ea16  jbe     loc_18007EAAC
0x18007ea1c  mov     r12, [rcx+8]
0x18007ea20  test    eax, eax
0x18007ea22  jz      short loc_18007EA32
0x18007ea24  mov     rax, [rcx]
0x18007ea27  mov     rax, [rax+60h]
0x18007ea2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea30  jmp     short loc_18007EA34
0x18007ea32  xor     eax, eax
0x18007ea34  mov     edx, [rdi+104h]; unsigned int
0x18007ea3a  mov     r9, rax; struct _SecPkgContext_ApplicationProtocol *
0x18007ea3d  mov     rcx, [rdi+108h]; struct _TLS_PARAMETERS *
0x18007ea44  mov     r8, rsi; pCertContext
0x18007ea47  mov     [rsp+88h+var_60], r13b; unsigned __int8
0x18007ea4c  mov     [rsp+88h+var_68], r12; struct CCipherSuiteInfo *
0x18007ea51  call    ?IsRemoteCertificateBlacklisted@@YAJPEAU_TLS_PARAMETERS@@KPEBU_CERT_CONTEXT@@PEAU_SecPkgContext_ApplicationProtocol@@PEAVCCipherSuiteInfo@@EE@Z; IsRemoteCertificateBlacklisted(_TLS_PARAMETERS *,ulong,_CERT_CONTEXT const *,_SecPkgContext_ApplicationProtocol *,CCipherSuiteInfo *,uchar,uchar)
0x18007ea56  mov     edi, eax
0x18007ea58  test    eax, eax
0x18007ea5a  jz      short loc_18007EAAC
0x18007ea5c  cmp     eax, 80090331h
0x18007ea61  jnz     short loc_18007EAA8
0x18007ea63  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ea6a  lea     rax, WPP_GLOBAL_Control
0x18007ea71  cmp     rcx, rax
0x18007ea74  jz      short loc_18007EA91
0x18007ea76  test    byte ptr [rcx+1Ch], 1
0x18007ea7a  jz      short loc_18007EA91
0x18007ea7c  mov     rcx, [rcx+10h]
0x18007ea80  lea     r8, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids
0x18007ea87  mov     edx, 0Ch
0x18007ea8c  call    WPP_SF_
0x18007ea91  mov     rcx, [rbp+8]
0x18007ea95  mov     r9b, 2Bh ; '+'
0x18007ea98  mov     edx, 0FBh
0x18007ea9d  mov     r8d, 80090331h
0x18007eaa3  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18007eaa8  mov     ebx, edi
0x18007eaaa  jmp     short loc_18007EAC1
0x18007eaac  mov     rax, [rsp+88h+arg_8]
0x18007eab4  mov     [r14], rax
0x18007eab7  mov     [r15], rsi
0x18007eaba  jmp     short loc_18007EADC
0x18007eabc  mov     ebx, 80090304h
0x18007eac1  mov     rcx, [rsp+88h+arg_8]; void *
0x18007eac9  test    rcx, rcx
0x18007eacc  jz      short loc_18007EAD3
0x18007eace  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18007ead3  mov     rcx, rsi; pCertContext
0x18007ead6  call    cs:__imp_CertFreeCertificateContext
0x18007eadc  mov     eax, ebx
0x18007eade  jmp     short loc_18007EAFB
0x18007eae0  mov     rcx, [rcx+8]
0x18007eae4  mov     edi, 80090308h
0x18007eae9  mov     r9b, 2Ah ; '*'
0x18007eaec  mov     r8d, edi
0x18007eaef  mov     edx, 0FAh
0x18007eaf4  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18007eaf9  mov     eax, edi
0x18007eafb  add     rsp, 48h
0x18007eaff  pop     r15
0x18007eb01  pop     r14
0x18007eb03  pop     r13
0x18007eb05  pop     r12
0x18007eb07  pop     rdi
0x18007eb08  pop     rsi
0x18007eb09  pop     rbp
0x18007eb0a  pop     rbx
0x18007eb0b  retn
```
