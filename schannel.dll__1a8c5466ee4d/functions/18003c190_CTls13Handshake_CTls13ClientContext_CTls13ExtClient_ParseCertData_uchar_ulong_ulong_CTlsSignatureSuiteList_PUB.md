# CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ParseCertData(uchar *,ulong,ulong,CTlsSignatureSuiteList &,_PUBLICKEY * &,_CERT_CONTEXT const * &)

- ea: `0x18003c190`
- end: `0x18003c422`
- name: `?ParseCertData@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@IEAAKPEAEKKAEAVCTlsSignatureSuiteList@@AEAPEAU_PUBLICKEY@@AEAPEBU_CERT_CONTEXT@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(__int64, const BYTE *, DWORD, __int64, CTlsSignatureSuiteList *, struct _PUBLICKEY **, const CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003bc90`

## callees

- `0x180014240`
- `0x1800214f0`
- `0x18003c190`
- `0x18003c430`
- `0x1800527b8`
- `0x180053df8`
- `0x180057c8c`
- `0x180091010`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18003c329`
- `CRYPT32!CertFreeCertificateContext` at `0x18003c329`
- `CRYPT32!CertCreateCertificateContext` at `0x18003c1b9`
- `CRYPT32!CertCreateCertificateContext` at `0x18003c1b9`
- `CRYPT32!CertCompareCertificateName` at `0x18003c206`
- `CRYPT32!CertCompareCertificateName` at `0x18003c206`

## pseudocode

```c
__int64 __fastcall CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::ParseCertData(
        __int64 a1,
        const BYTE *a2,
        DWORD a3,
        __int64 a4,
        CTlsSignatureSuiteList *a5,
        struct _PUBLICKEY **a6,
        const CERT_CONTEXT **a7)
{
  int v7; // esi
  PCCERT_CONTEXT CertificateContext; // rax
  __int64 v10; // r9
  const CERT_CONTEXT *v11; // rbx
  struct _CRYPTOAPI_BLOB *pCertInfo; // rdx
  __int64 v13; // r9
  unsigned int v14; // edi
  struct _PUBLICKEY **v15; // r14
  const CERT_CONTEXT **v16; // r15
  unsigned int PublicKeyFromCert; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rsi
  unsigned __int8 v21; // r13
  struct CCipherSuiteInfo *v22; // r12
  struct _SecPkgContext_ApplicationProtocol *v23; // rax
  unsigned int v24; // esi
  __int64 v25; // r9
  unsigned __int8 v27; // [rsp+30h] [rbp-38h]
  struct _PUBLICKEY *v28; // [rsp+78h] [rbp+10h] BYREF

  v7 = a4;
  if ( a2 && a3 )
  {
    CertificateContext = CertCreateCertificateContext(1u, a2, a3);
    v11 = CertificateContext;
    if ( CertificateContext )
    {
      pCertInfo = (struct _CRYPTOAPI_BLOB *)CertificateContext->pCertInfo;
      v28 = 0;
      if ( pCertInfo )
      {
        if ( v7 && CertCompareCertificateName(CertificateContext->dwCertEncodingType, pCertInfo + 3, pCertInfo + 5)
          || CTlsSignatureSuiteList::AddCertificateSignatureSuite(a5, v11) )
        {
          v14 = 0;
          if ( !v7 )
          {
            v15 = a6;
            if ( *a6 || (v16 = a7, *a7) )
            {
              v14 = -2146893052;
            }
            else
            {
              PublicKeyFromCert = GetPublicKeyFromCert(v11, &v28, 0);
              v19 = *(_QWORD *)(a1 + 8);
              v14 = PublicKeyFromCert;
              if ( PublicKeyFromCert )
              {
                LOBYTE(v18) = 43;
                CSslContext::SetErrorAndFatalAlert(v19, 251, PublicKeyFromCert, v18);
              }
              else
              {
                v20 = *(_QWORD *)(v19 + 104);
                if ( v20 )
                {
                  v21 = (*(_DWORD *)(v19 + 88) & 0x40051555) != 0;
                  if ( *(_DWORD *)(v20 + 260) <= PublicKeyFromCert
                    || ((v22 = *(struct CCipherSuiteInfo **)(v19 + 8), (*(_DWORD *)(v19 + 88) & 0x40051555) != 0)
                      ? (v23 = (struct _SecPkgContext_ApplicationProtocol *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 96LL))(v19))
                      : (v23 = 0),
                        (v24 = IsRemoteCertificateBlacklisted(
                                 *(struct _TLS_PARAMETERS **)(v20 + 264),
                                 *(_DWORD *)(v20 + 260),
                                 v11,
                                 v23,
                                 v22,
                                 v21,
                                 v27)) == 0) )
                  {
                    *v15 = v28;
                    *v16 = v11;
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
                  v14 = v24;
                }
                else
                {
                  v14 = -2146893052;
                }
              }
              if ( v28 )
                SPExternalFree(v28);
            }
          }
        }
        else
        {
          v14 = -2146893048;
          LOBYTE(v13) = 43;
          CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), 252, 2148074248LL, v13);
        }
      }
      else
      {
        v14 = -2146893048;
        LOBYTE(v10) = 42;
        CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), 250, 2148074248LL, v10);
      }
      CertFreeCertificateContext(v11);
      return v14;
    }
    LOBYTE(v10) = 42;
    CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), 250, 2148074248LL, v10);
    return 2148074248LL;
  }
  else
  {
    LOBYTE(a4) = 42;
    CSslContext::SetErrorAndFatalAlert(*(_QWORD *)(a1 + 8), 250, 2148074248LL, a4);
    return 2148074248LL;
  }
}

```

## disassembly

```asm
0x18003c190  push    rbp
0x18003c192  push    rsi
0x18003c193  sub     rsp, 58h
0x18003c197  mov     esi, r9d
0x18003c19a  mov     rbp, rcx
0x18003c19d  test    rdx, rdx
0x18003c1a0  jz      loc_18003C342
0x18003c1a6  test    r8d, r8d
0x18003c1a9  jz      loc_18003C342
0x18003c1af  mov     ecx, 1; dwCertEncodingType
0x18003c1b4  mov     [rsp+68h+arg_0], rbx
0x18003c1b9  call    cs:__imp_CertCreateCertificateContext
0x18003c1bf  mov     rbx, rax
0x18003c1c2  test    rax, rax
0x18003c1c5  jz      loc_18003C382
0x18003c1cb  mov     rdx, [rax+18h]
0x18003c1cf  mov     [rsp+68h+arg_10], rdi
0x18003c1d7  mov     [rsp+68h+var_18], r13
0x18003c1dc  mov     [rsp+68h+var_20], r14
0x18003c1e1  mov     [rsp+68h+var_28], r15
0x18003c1e6  mov     [rsp+68h+arg_8], 0
0x18003c1ef  test    rdx, rdx
0x18003c1f2  jz      loc_18003C30D
0x18003c1f8  test    esi, esi
0x18003c1fa  jz      short loc_18003C210
0x18003c1fc  mov     ecx, [rax]; dwCertEncodingType
0x18003c1fe  lea     r8, [rdx+50h]; pCertName2
0x18003c202  add     rdx, 30h ; '0'; pCertName1
0x18003c206  call    cs:__imp_CertCompareCertificateName
0x18003c20c  test    eax, eax
0x18003c20e  jnz     short loc_18003C228
0x18003c210  mov     rcx, [rsp+68h+arg_20]; this
0x18003c218  mov     rdx, rbx; struct _CERT_CONTEXT *
0x18003c21b  call    ?AddCertificateSignatureSuite@CTlsSignatureSuiteList@@QEAAEPEBU_CERT_CONTEXT@@@Z; CTlsSignatureSuiteList::AddCertificateSignatureSuite(_CERT_CONTEXT const *)
0x18003c220  test    al, al
0x18003c222  jz      loc_18003C3AA
0x18003c228  xor     edi, edi
0x18003c22a  test    esi, esi
0x18003c22c  jnz     loc_18003C326
0x18003c232  mov     r14, [rsp+68h+arg_28]
0x18003c23a  cmp     [r14], rdi
0x18003c23d  jnz     loc_18003C365
0x18003c243  mov     r15, [rsp+68h+arg_30]
0x18003c24b  cmp     [r15], rdi
0x18003c24e  jnz     loc_18003C365
0x18003c254  xor     r8d, r8d; enum _eTlsSignatureAlgorithm *
0x18003c257  lea     rdx, [rsp+68h+arg_8]; struct _PUBLICKEY **
0x18003c25c  mov     rcx, rbx; struct _CERT_CONTEXT *
0x18003c25f  call    ?GetPublicKeyFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_PUBLICKEY@@PEAW4_eTlsSignatureAlgorithm@@@Z; GetPublicKeyFromCert(_CERT_CONTEXT const *,_PUBLICKEY * *,_eTlsSignatureAlgorithm *)
0x18003c264  mov     rcx, [rbp+8]
0x18003c268  mov     edi, eax
0x18003c26a  test    eax, eax
0x18003c26c  jnz     loc_18003C3C8
0x18003c272  mov     rsi, [rcx+68h]
0x18003c276  test    rsi, rsi
0x18003c279  jz      loc_18003C36C
0x18003c27f  mov     eax, [rcx+58h]
0x18003c282  and     eax, 40051555h
0x18003c287  setnbe  r13b
0x18003c28b  cmp     [rsi+104h], edi
0x18003c291  jbe     short loc_18003C2DD
0x18003c293  mov     [rsp+68h+arg_18], r12
0x18003c29b  mov     r12, [rcx+8]
0x18003c29f  test    eax, eax
0x18003c2a1  jnz     loc_18003C331
0x18003c2a7  xor     eax, eax
0x18003c2a9  mov     edx, [rsi+104h]; unsigned int
0x18003c2af  mov     r9, rax; struct _SecPkgContext_ApplicationProtocol *
0x18003c2b2  mov     rcx, [rsi+108h]; struct _TLS_PARAMETERS *
0x18003c2b9  mov     r8, rbx; pCertContext
0x18003c2bc  mov     [rsp+68h+var_40], r13b; unsigned __int8
0x18003c2c1  mov     [rsp+68h+var_48], r12; struct CCipherSuiteInfo *
0x18003c2c6  call    ?IsRemoteCertificateBlacklisted@@YAJPEAU_TLS_PARAMETERS@@KPEBU_CERT_CONTEXT@@PEAU_SecPkgContext_ApplicationProtocol@@PEAVCCipherSuiteInfo@@EE@Z; IsRemoteCertificateBlacklisted(_TLS_PARAMETERS *,ulong,_CERT_CONTEXT const *,_SecPkgContext_ApplicationProtocol *,CCipherSuiteInfo *,uchar,uchar)
0x18003c2cb  mov     r12, [rsp+68h+arg_18]
0x18003c2d3  mov     esi, eax
0x18003c2d5  test    eax, eax
0x18003c2d7  jnz     loc_18003C3DA
0x18003c2dd  mov     rax, [rsp+68h+arg_8]
0x18003c2e2  mov     [r14], rax
0x18003c2e5  mov     [r15], rbx
0x18003c2e8  mov     r15, [rsp+68h+var_28]
0x18003c2ed  mov     eax, edi
0x18003c2ef  mov     rdi, [rsp+68h+arg_10]
0x18003c2f7  mov     r14, [rsp+68h+var_20]
0x18003c2fc  mov     r13, [rsp+68h+var_18]
0x18003c301  mov     rbx, [rsp+68h+arg_0]
0x18003c306  add     rsp, 58h
0x18003c30a  pop     rsi
0x18003c30b  pop     rbp
0x18003c30c  retn
0x18003c30d  mov     rcx, [rbp+8]
0x18003c311  mov     edi, 80090308h
0x18003c316  mov     r8d, edi
0x18003c319  mov     r9b, 2Ah ; '*'
0x18003c31c  mov     edx, 0FAh
0x18003c321  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c326  mov     rcx, rbx; pCertContext
0x18003c329  call    cs:__imp_CertFreeCertificateContext
0x18003c32f  jmp     short loc_18003C2E8
0x18003c331  mov     rax, [rcx]
0x18003c334  mov     rax, [rax+60h]
0x18003c338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c33d  jmp     loc_18003C2A9
0x18003c342  mov     rcx, [rcx+8]
0x18003c346  mov     r9b, 2Ah ; '*'
0x18003c349  mov     edx, 0FAh
0x18003c34e  mov     r8d, 80090308h
0x18003c354  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c359  mov     eax, 80090308h
0x18003c35e  add     rsp, 58h
0x18003c362  pop     rsi
0x18003c363  pop     rbp
0x18003c364  retn
0x18003c365  mov     edi, 80090304h
0x18003c36a  jmp     short loc_18003C326
0x18003c36c  mov     edi, 80090304h
0x18003c371  mov     rcx, [rsp+68h+arg_8]; void *
0x18003c376  test    rcx, rcx
0x18003c379  jz      short loc_18003C326
0x18003c37b  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18003c380  jmp     short loc_18003C326
0x18003c382  mov     rcx, [rbp+8]
0x18003c386  mov     r9b, 2Ah ; '*'
0x18003c389  mov     edx, 0FAh
0x18003c38e  mov     r8d, 80090308h
0x18003c394  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c399  mov     rbx, [rsp+68h+arg_0]
0x18003c39e  mov     eax, 80090308h
0x18003c3a3  add     rsp, 58h
0x18003c3a7  pop     rsi
0x18003c3a8  pop     rbp
0x18003c3a9  retn
0x18003c3aa  mov     rcx, [rbp+8]
0x18003c3ae  mov     edi, 80090308h
0x18003c3b3  mov     r8d, edi
0x18003c3b6  mov     r9b, 2Bh ; '+'
0x18003c3b9  mov     edx, 0FCh
0x18003c3be  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c3c3  jmp     loc_18003C326
0x18003c3c8  mov     r9b, 2Bh ; '+'
0x18003c3cb  mov     r8d, eax
0x18003c3ce  mov     edx, 0FBh
0x18003c3d3  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18003c3d8  jmp     short loc_18003C371
0x18003c3da  cmp     esi, 80090331h
0x18003c3e0  jnz     loc_18008EF25
0x18003c3e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c3ed  lea     rax, WPP_GLOBAL_Control
0x18003c3f4  cmp     rcx, rax
0x18003c3f7  jz      loc_18008EF0E
0x18003c3fd  test    byte ptr [rcx+1Ch], 1
0x18003c401  jz      loc_18008EF0E
0x18003c407  mov     rcx, [rcx+10h]
0x18003c40b  lea     r8, WPP_ca7b144d2da03908b1ea89985908c21d_Traceguids
0x18003c412  mov     edx, 0Ch
0x18003c417  call    WPP_SF_
0x18003c41c  nop
0x18003c41d  jmp     loc_18008EF0E
0x18008ef0e  mov     rcx, [rbp+8]
0x18008ef12  mov     r9b, 2Bh ; '+'
0x18008ef15  mov     edx, 0FBh
0x18008ef1a  mov     r8d, 80090331h
0x18008ef20  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18008ef25  mov     edi, esi
0x18008ef27  jmp     loc_18003C371
```
