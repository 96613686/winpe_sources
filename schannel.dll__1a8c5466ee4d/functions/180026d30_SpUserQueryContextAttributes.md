# SpUserQueryContextAttributes

- ea: `0x180026d30`
- end: `0x18002772d`
- name: `SpUserQueryContextAttributes`
- size: `2557`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a65c`
- `0x18000ab10`
- `0x18000ac00`
- `0x180013a00`
- `0x180014270`
- `0x180021da8`
- `0x180025460`
- `0x180025620`
- `0x180026d30`
- `0x180027e10`
- `0x18004d708`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005a160`
- `0x18005c3a0`
- `0x18006b2f8`
- `0x18006c2b8`
- `0x18006c324`
- `0x18006c430`
- `0x18006c4cc`
- `0x18006c624`
- `0x18006c7c8`
- `0x18006c870`
- `0x18006c918`
- `0x18006f3ec`
- `0x18006f530`
- `0x18006f634`
- `0x18006f7a4`
- `0x18006f8b8`
- `0x18006f984`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002746e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ca1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002746e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ca1c`
- `ncrypt!SslLookupCipherSuiteInfo` at `0x180026f8c`
- `ncrypt!SslLookupCipherSuiteInfo` at `0x180027147`
- `ncrypt!SslLookupCipherSuiteInfo` at `0x180026f8c`
- `ncrypt!SslLookupCipherSuiteInfo` at `0x180027147`
- `CRYPT32!CertOpenStore` at `0x180026e5c`
- `CRYPT32!CertOpenStore` at `0x180026e5c`
- `CRYPT32!CertCloseStore` at `0x180026ec4`
- `CRYPT32!CertCloseStore` at `0x18008ca65`
- `CRYPT32!CertCloseStore` at `0x18008ca76`
- `CRYPT32!CertCloseStore` at `0x180026ec4`
- `CRYPT32!CertCloseStore` at `0x18008ca65`
- `CRYPT32!CertCloseStore` at `0x18008ca76`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ca5a`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ca5a`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180026e76`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180026e76`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026eaa`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180026eaa`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18008c988`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18008ca00`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18008c988`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18008ca00`

## pseudocode

```c
__int64 __fastcall SpUserQueryContextAttributes(
        unsigned __int64 a1,
        unsigned int a2,
        struct _SecPkgContext_StreamSizes *a3)
{
  struct CSslUserContext *v6; // rax
  struct CSslUserContext *v7; // rcx
  struct CSslUserContext *v8; // rsi
  CCipherMill *v9; // r10
  HCERTSTORE v10; // rsi
  const CERT_CONTEXT *v11; // rbx
  const CERT_CONTEXT *v12; // rax
  unsigned int v13; // r14d
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned __int16 v24; // ax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int128 *v28; // rax
  __int64 v29; // rcx
  __int128 v30; // xmm0
  DWORD v31; // eax
  unsigned __int8 *v32; // rcx
  DWORD LastError; // eax
  __int64 v34; // rax
  const CERT_CONTEXT *v35; // rbx
  DWORD v36; // eax
  __int64 v37; // rax
  DWORD v38; // eax
  DWORD pcbData[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v40; // [rsp+38h] [rbp-C8h]
  _DWORD pvData[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 pvPara; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v44[2]; // [rsp+64h] [rbp-9Ch] BYREF
  _WORD Src[64]; // [rsp+6Ch] [rbp-94h] BYREF
  _WORD v46[64]; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int v47; // [rsp+16Ch] [rbp+6Ch]
  unsigned int v48; // [rsp+170h] [rbp+70h]
  _WORD v49[64]; // [rsp+174h] [rbp+74h] BYREF
  unsigned int v50; // [rsp+1F4h] [rbp+F4h]
  _DWORD v51[34]; // [rsp+1F8h] [rbp+F8h] BYREF
  _WORD v52[136]; // [rsp+280h] [rbp+180h] BYREF

  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_bbe33ecd4d183e21185aee86644dce59_Traceguids);
  v6 = SslReferenceUserContext(a1, 0);
  v8 = v6;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_bbe33ecd4d183e21185aee86644dce59_Traceguids, v6);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    switch ( a2 )
    {
      case 4u:
        return (unsigned int)SpQueryStreamSizes(v8, a3);
      case 0x64u:
        memset_0(&v43, 0, 0x2A4u);
        v16 = *((_DWORD *)v8 + 6);
        if ( (v16 & 0x3FFC) != 0 && (v16 & 0xF0000) != 0 )
        {
          v17 = 0;
        }
        else if ( (v16 & 0xC0000) != 0 )
        {
          v17 = 65277;
        }
        else if ( (v16 & 0x30000) != 0 )
        {
          v17 = 65279;
        }
        else if ( (v16 & 0x3000) != 0 )
        {
          v17 = 772;
        }
        else if ( (v16 & 0xC00) != 0 )
        {
          v17 = 771;
        }
        else
        {
          v17 = 768;
          if ( (v16 & 0x300) != 0 )
          {
            v17 = 770;
          }
          else if ( (v16 & 0xC0) != 0 )
          {
            v17 = 769;
          }
          else if ( (v16 & 0x30) == 0 )
          {
            v17 = (v16 & 0xC) != 0 ? 2 : 0;
          }
        }
        v13 = SslLookupCipherSuiteInfo(
                *((_QWORD *)v8 + 11),
                v17,
                *((unsigned int *)v8 + 14),
                *((unsigned int *)v8 + 15),
                &v43,
                0);
        if ( !v13 )
        {
          a3->cbTrailer = v43;
          v18 = -1;
          a3->cbMaximumMessage = v44[0];
          a3->cBuffers = v44[1];
          v19 = -1;
          a3->cbHeader = 1;
          do
            v20 = Src[++v19] == 0;
          while ( !v20 );
          memcpy_0(&a3->cbBlockSize, Src, 2LL * (unsigned int)(v19 + 1));
          v21 = -1;
          do
            v20 = v46[++v21] == 0;
          while ( !v20 );
          memcpy_0(&a3[7].cbTrailer, v46, 2LL * (unsigned int)(v21 + 1));
          a3[13].cBuffers = v47;
          a3[13].cbBlockSize = v48;
          v22 = -1;
          do
            v20 = v49[++v22] == 0;
          while ( !v20 );
          memcpy_0(&a3[14], v49, 2LL * (unsigned int)(v22 + 1));
          a3[20].cbMaximumMessage = v50;
          v23 = -1;
          do
            v20 = *((_WORD *)v51 + ++v23) == 0;
          while ( !v20 );
          memcpy_0(&a3[20].cBuffers, v51, 2LL * (unsigned int)(v23 + 1));
          a3[27].cbHeader = v51[32];
          a3[27].cbTrailer = v51[33];
          do
            v20 = v52[++v18] == 0;
          while ( !v20 );
          memcpy_0(&a3[27].cbMaximumMessage, v52, 2LL * (unsigned int)(v18 + 1));
          a3[33].cbBlockSize = *((_DWORD *)v8 + 15);
        }
        return v13;
      case 0x5Au:
        v43 = 1;
        memset_0(v44, 0, 0x324u);
        v24 = ConvertSchannelProtocolToSsl(*((_DWORD *)v8 + 6));
        v13 = SslLookupCipherSuiteInfo(
                *((_QWORD *)v8 + 11),
                v24,
                *((unsigned int *)v8 + 14),
                *((unsigned int *)v8 + 15),
                v44,
                0);
        if ( !v13 )
        {
          a3->cbHeader = *((_DWORD *)v8 + 6);
          v25 = LookupSymmetricCipherAlg((struct _NCRYPT_SSL_CIPHER_SUITE_EX *)&v43);
          a3->cbTrailer = v25;
          if ( v25 - 28672 <= 0xF )
            a3->cbTrailer = 28672;
          a3->cbMaximumMessage = v48;
          v26 = LookupChecksumAlg((struct _NCRYPT_SSL_CIPHER_SUITE_EX *)&v43);
          a3->cBuffers = v26;
          if ( v26 - 36864 <= 0xF )
            a3->cBuffers = 36864;
          a3->cbBlockSize = v51[0];
          v27 = LookupExchangeAlg((struct _NCRYPT_SSL_CIPHER_SUITE_EX *)&v43);
          a3[1].cbHeader = v27;
          if ( v27 - 45056 <= 4 )
            a3[1].cbHeader = 45056;
          v20 = (a3->cbHeader & 0x3000) == 0;
          a3[1].cbTrailer = *((_DWORD *)v8 + 7);
          if ( !v20 )
            a3[1].cbHeader = 44550;
        }
        return v13;
      case 0x1Au:
        return (unsigned int)SpQueryEndpointBindings(v8, (struct _SecPkgContext_Bindings *)a3);
      default:
        switch ( a2 )
        {
          case 0u:
            return (unsigned int)SpQuerySizes(v8, (struct _SecPkgContext_Sizes *)a3);
          case 1u:
            return (unsigned int)SpQueryNames(v8, (struct _SecPkgContext_NamesW *)a3);
          case 2u:
            return (unsigned int)SpQueryLifespan(v8, (struct _SecPkgContext_Lifespan *)a3);
          case 5u:
            return (unsigned int)SpQueryKeyInfo(v8, a3);
          case 7u:
            return (unsigned int)SpQueryProtoInfo(v8, a3);
          case 0xAu:
            return (unsigned int)SpQueryPackageInfo(v7, a3);
          case 0x12u:
            v34 = *((_QWORD *)v8 + 35);
            if ( v34 )
            {
              *(_QWORD *)&a3->cbHeader = v34;
              return 0;
            }
            else
            {
              v13 = -2146893045;
              if ( *((_DWORD *)v8 + 72) )
                return *((unsigned int *)v8 + 72);
            }
            return v13;
          case 0x19u:
            return (unsigned int)SpQueryUniqueBindings(v8, (struct _SecPkgContext_Bindings *)a3);
          case 0x23u:
            if ( v9 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)v9 + 2), 110, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
            v28 = (__int128 *)*((_QWORD *)v8 + 51);
            if ( v28 )
            {
              v29 = 2;
              do
              {
                a3 = (struct _SecPkgContext_StreamSizes *)((char *)a3 + 128);
                v30 = *v28;
                v28 += 8;
                *(_OWORD *)&a3[-7].cBuffers = v30;
                *(_OWORD *)&a3[-6].cbMaximumMessage = *(v28 - 7);
                *(_OWORD *)&a3[-5].cbTrailer = *(v28 - 6);
                *(_OWORD *)&a3[-4].cbHeader = *(v28 - 5);
                *(_OWORD *)&a3[-4].cbBlockSize = *(v28 - 4);
                *(_OWORD *)&a3[-3].cBuffers = *(v28 - 3);
                *(_OWORD *)&a3[-2].cbMaximumMessage = *(v28 - 2);
                *(_OWORD *)&a3[-1].cbTrailer = *(v28 - 1);
                --v29;
              }
              while ( v29 );
              *(_QWORD *)&a3->cbHeader = *(_QWORD *)v28;
            }
            else
            {
              memset_0(a3, 0, 0x108u);
            }
            return 0;
          case 0x24u:
            return (unsigned int)SpQueryNegotiatedTlsExtensions(v8, (struct _SecPkgContext_NegotiatedTlsExtensions *)a3);
          case 0x51u:
            return (unsigned int)SpQueryRemoteCred(v8, a3);
          case 0x53u:
            *(_QWORD *)pcbData = 0;
            if ( v9 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)v9 + 2), 12, WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids);
            if ( !a3 )
              return (unsigned int)-2146892963;
            if ( *((_DWORD *)v8 + 3) )
            {
              pvPara = *(_OWORD *)((char *)v8 + 232);
              if ( *((_QWORD *)&pvPara + 1) )
              {
                v10 = CertOpenStore((LPCSTR)6, 1u, 0, 4u, &pvPara);
                if ( v10 )
                {
                  v11 = 0;
                  while ( 1 )
                  {
                    v12 = CertEnumCertificatesInStore(v10, v11);
                    v11 = v12;
                    if ( !v12 )
                    {
                      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          15,
                          WPP_39e7268a77b0313df132bc71a3d61242_Traceguids);
                      }
                      CertCloseStore(v10, 0);
                      return (unsigned int)-2146893052;
                    }
                    pcbData[0] = 4;
                    pvData[0] = 0;
                    if ( !CertGetCertificateContextProperty(v12, 0xE697u, pvData, pcbData) )
                      break;
                    if ( !pvData[0] )
                    {
                      CertCloseStore(v10, 0);
                      v13 = 0;
                      *(_QWORD *)&a3->cbHeader = v11;
                      return v13;
                    }
                  }
                  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    LastError = GetLastError();
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      14,
                      WPP_39e7268a77b0313df132bc71a3d61242_Traceguids,
                      LastError);
                  }
                  CertFreeCertificateContext(v11);
                  CertCloseStore(v10, 0);
                  return (unsigned int)-2146892963;
                }
                else
                {
                  v31 = GetLastError();
                  if ( v31 == 14 || v31 == 8 )
                  {
                    return (unsigned int)-2146893056;
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        13,
                        WPP_39e7268a77b0313df132bc71a3d61242_Traceguids,
                        v31);
                    }
                    return (unsigned int)-2146893048;
                  }
                }
              }
              return (unsigned int)-2146893042;
            }
            v32 = (unsigned __int8 *)*((_QWORD *)v8 + 19);
            if ( !v32 )
              return (unsigned int)-2146893042;
            v13 = SPLoadCertificate(v32, *((_DWORD *)v8 + 40), (const struct _CERT_CONTEXT **)pcbData);
            if ( !v13 )
            {
              v35 = *(const CERT_CONTEXT **)pcbData;
              if ( *((_QWORD *)v8 + 21) )
              {
                v40 = *((_QWORD *)v8 + 21);
                pcbData[0] = *((_DWORD *)v8 + 44);
                pcbData[1] = 0;
                if ( !CertSetCertificateContextProperty(v35, 0x46u, 0, pcbData)
                  && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v36 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    13,
                    WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids,
                    v36);
                }
              }
              v37 = *((_QWORD *)v8 + 23);
              if ( v37 )
              {
                if ( *((_DWORD *)v8 + 48) )
                {
                  pcbData[0] = *((_DWORD *)v8 + 48);
                  pcbData[1] = 0;
                  v40 = v37;
                  if ( !CertSetCertificateContextProperty(v35, 0x77u, 0, pcbData)
                    && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v38 = GetLastError();
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      14,
                      WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids,
                      v38);
                  }
                }
              }
              *(_QWORD *)&a3->cbHeader = v35;
              v13 = 0;
            }
            break;
          case 0x5Du:
            if ( v9 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)v9 + 2), 94, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
            a3->cbHeader = 0;
            if ( (*((_DWORD *)v8 + 4) & 0x8000LL) == 0 )
              a3->cbHeader = 1;
            a3->cbTrailer = *((_DWORD *)v8 + 84);
            memcpy_0(&a3->cbMaximumMessage, (char *)v8 + 340, *((unsigned int *)v8 + 84));
            return 0;
          case 0x6Cu:
            return (unsigned int)SpQuerySrtpParameters(v8, (struct _SecPkgContext_SrtpParameters *)a3);
          case 0x6Du:
            return (unsigned int)SpQueryTokenBinding(v8, (struct _SecPkgContext_TokenBinding *)a3);
          case 0x6Eu:
            return (unsigned int)SpQueryConnectionInfoEx(v8, (struct _SecPkgContext_ConnectionInfoEx *)a3);
          case 0x6Fu:
            return (unsigned int)SpQueryTokenBindingEKM(v8, (struct _SecPkgContext_KeyingMaterial *)a3);
          case 0x70u:
            return (unsigned int)SpQueryKeyingMaterial(v8, (struct _SecPkgContext_KeyingMaterial_Inproc *)a3);
          case 0x72u:
            if ( v9 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)v9 + 2), 19, WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids);
            return (unsigned int)SpQueryCertificateValidationResult(
                                   *((_QWORD *)v8 + 2),
                                   *((_DWORD *)v8 + 99),
                                   *((_DWORD *)v8 + 98),
                                   (struct _SecPkgContext_CertificateValidationResult *)a3);
          case 0x74u:
            return (unsigned int)SpQueryRemoteCertificateStore(v8, (struct _CRYPTOAPI_BLOB *)a3);
          default:
            if ( v9 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v9 + 2), 20, WPP_c87a45a788bd3ab9f142d4514d1f809e_Traceguids, a2);
            return 2148074242LL;
        }
        return v13;
    }
  }
  return 2148074241LL;
}

```

## disassembly

```asm
0x180026d30  push    rbp
0x180026d32  push    rbx
0x180026d33  push    rsi
0x180026d34  push    rdi
0x180026d35  push    r15
0x180026d37  lea     rbp, [rsp-2A0h]
0x180026d3f  sub     rsp, 3A0h
0x180026d46  mov     rax, cs:__security_cookie
0x180026d4d  xor     rax, rsp
0x180026d50  mov     [rbp+2C0h+var_30], rax
0x180026d57  mov     rdi, r8
0x180026d5a  mov     ebx, edx
0x180026d5c  mov     rsi, rcx
0x180026d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d66  lea     r15, WPP_GLOBAL_Control
0x180026d6d  cmp     rcx, r15
0x180026d70  jz      short loc_180026D7C
0x180026d72  test    byte ptr [rcx+1Ch], 20h
0x180026d76  jnz     loc_18002735E
0x180026d7c  xor     edx, edx; unsigned __int8
0x180026d7e  mov     rcx, rsi; unsigned __int64
0x180026d81  call    ?SslReferenceUserContext@@YAPEAUCSslUserContext@@_KE@Z; SslReferenceUserContext(unsigned __int64,uchar)
0x180026d86  mov     rsi, rax
0x180026d89  mov     r10, cs:WPP_GLOBAL_Control
0x180026d90  cmp     r10, r15
0x180026d93  jz      short loc_180026DA0
0x180026d95  test    byte ptr [r10+1Ch], 4
0x180026d9a  jnz     loc_180027378
0x180026da0  test    rsi, rsi
0x180026da3  jz      loc_1800271EB
0x180026da9  mov     [rsp+3C0h+arg_18], r14
0x180026db1  cmp     ebx, 4
0x180026db4  jz      loc_180026ED2
0x180026dba  cmp     ebx, 64h ; 'd'
0x180026dbd  jz      loc_180026F08
0x180026dc3  cmp     ebx, 5Ah ; 'Z'
0x180026dc6  jz      loc_180027104
0x180026dcc  cmp     ebx, 1Ah
0x180026dcf  jz      loc_1800271DB
0x180026dd5  cmp     ebx, 74h; switch 117 cases
0x180026dd8  ja      def_180026DF7; jumptable 0000000180026DF7 default case, cases 3,4,6,8,9,11-17,19-24,26-34,37-80,82,84-92,94-107,113,115
0x180026dde  lea     rdx, __ImageBase
0x180026de5  movzx   eax, ds:(byte_1800276B8 - 180000000h)[rdx+rbx]
0x180026ded  mov     ecx, ds:(jpt_180026DF7 - 180000000h)[rdx+rax*4]
0x180026df4  add     rcx, rdx; struct CSslUserContext *
0x180026df7  jmp     rcx; switch jump
0x180026df9  mov     qword ptr [rsp+3C0h+pcbData], 0; jumptable 0000000180026DF7 case 83
0x180026e02  cmp     r10, r15
0x180026e05  jz      short loc_180026E12
0x180026e07  test    byte ptr [r10+1Ch], 4
0x180026e0c  jnz     loc_1800273F9
0x180026e12  test    rdi, rdi
0x180026e15  jz      loc_180027499
0x180026e1b  cmp     dword ptr [rsi+0Ch], 0
0x180026e1f  jz      loc_180027302
0x180026e25  cmp     qword ptr [rsi+0F0h], 0
0x180026e2d  movups  xmm0, xmmword ptr [rsi+0E8h]
0x180026e34  movaps  [rsp+3C0h+var_370], xmm0
0x180026e39  jz      loc_180027312
0x180026e3f  lea     rax, [rsp+3C0h+var_370]
0x180026e44  mov     r9d, 4; dwFlags
0x180026e4a  xor     r8d, r8d; hCryptProv
0x180026e4d  mov     [rsp+3C0h+pvPara], rax; pvPara
0x180026e52  mov     edx, 1; dwEncodingType
0x180026e57  mov     ecx, 6; lpszStoreProvider
0x180026e5c  call    cs:__imp_CertOpenStore
0x180026e62  mov     rsi, rax
0x180026e65  test    rax, rax
0x180026e68  jz      loc_1800272D3
0x180026e6e  xor     ebx, ebx
0x180026e70  mov     rdx, rbx; pPrevCertContext
0x180026e73  mov     rcx, rsi; hCertStore
0x180026e76  call    cs:__imp_CertEnumCertificatesInStore
0x180026e7c  mov     rbx, rax
0x180026e7f  test    rax, rax
0x180026e82  jz      loc_1800274A4
0x180026e88  lea     r9, [rsp+3C0h+pcbData]; pcbData
0x180026e8d  mov     [rsp+3C0h+pcbData], 4
0x180026e95  lea     r8, [rsp+3C0h+pvData]; pvData
0x180026e9a  mov     [rsp+3C0h+pvData], 0
0x180026ea2  mov     edx, 0E697h; dwPropId
0x180026ea7  mov     rcx, rax; pCertContext
0x180026eaa  call    cs:__imp_CertGetCertificateContextProperty
0x180026eb0  test    eax, eax
0x180026eb2  jz      loc_180027454
0x180026eb8  cmp     [rsp+3C0h+pvData], 0
0x180026ebd  jnz     short loc_180026E70
0x180026ebf  xor     edx, edx; dwFlags
0x180026ec1  mov     rcx, rsi; hCertStore
0x180026ec4  call    cs:__imp_CertCloseStore
0x180026eca  xor     r14d, r14d
0x180026ecd  mov     [rdi], rbx
0x180026ed0  jmp     short loc_180026EE0
0x180026ed2  mov     rdx, rdi; struct _SecPkgContext_StreamSizes *
0x180026ed5  mov     rcx, rsi; struct CSslUserContext *
0x180026ed8  call    ?SpQueryStreamSizes@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_StreamSizes@@@Z; SpQueryStreamSizes(CSslUserContext *,_SecPkgContext_StreamSizes *)
0x180026edd  mov     r14d, eax
0x180026ee0  mov     eax, r14d
0x180026ee3  mov     r14, [rsp+3C0h+arg_18]
0x180026eeb  mov     rcx, [rbp+2C0h+var_30]
0x180026ef2  xor     rcx, rsp; StackCookie
0x180026ef5  call    __security_check_cookie
0x180026efa  add     rsp, 3A0h
0x180026f01  pop     r15
0x180026f03  pop     rdi
0x180026f04  pop     rsi
0x180026f05  pop     rbx
0x180026f06  pop     rbp
0x180026f07  retn
0x180026f08  xor     edx, edx; Val
0x180026f0a  lea     rcx, [rsp+3C0h+var_360]; void *
0x180026f0f  mov     r8d, 2A4h; Size
0x180026f15  call    memset_0
0x180026f1a  mov     edx, [rsi+18h]
0x180026f1d  test    edx, 3FFCh
0x180026f23  mov     r9d, [rsi+3Ch]
0x180026f27  mov     r8d, [rsi+38h]
0x180026f2b  setnz   cl
0x180026f2e  test    edx, 0F0000h
0x180026f34  setnz   al
0x180026f37  test    al, cl
0x180026f39  jnz     loc_180027343
0x180026f3f  test    edx, 0C0000h
0x180026f45  jnz     loc_18002734A
0x180026f4b  test    edx, 30000h
0x180026f51  jnz     loc_180027339
0x180026f57  test    edx, 3000h
0x180026f5d  jnz     loc_1800271F5
0x180026f63  test    edx, 0C00h
0x180026f69  jz      loc_18002731D
0x180026f6f  mov     eax, 303h
0x180026f74  lea     rcx, [rsp+3C0h+var_360]
0x180026f79  mov     [rsp+3C0h+var_398], 0
0x180026f81  mov     [rsp+3C0h+pvPara], rcx
0x180026f86  mov     edx, eax
0x180026f88  mov     rcx, [rsi+58h]
0x180026f8c  call    cs:__imp_SslLookupCipherSuiteInfo
0x180026f92  mov     r14d, eax
0x180026f95  test    eax, eax
0x180026f97  jnz     loc_180026EE0
0x180026f9d  mov     eax, [rsp+3C0h+var_360]
0x180026fa1  lea     rcx, [rsp+3C0h+Src]
0x180026fa6  mov     [rdi+4], eax
0x180026fa9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180026fb0  mov     eax, [rsp+3C0h+var_35C]
0x180026fb4  mov     [rdi+8], eax
0x180026fb7  mov     eax, [rsp+3C0h+var_358]
0x180026fbb  mov     [rdi+0Ch], eax
0x180026fbe  mov     rax, rbx
0x180026fc1  mov     dword ptr [rdi], 1
0x180026fc7  nop     word ptr [rax+rax+00000000h]
0x180026fd0  cmp     word ptr [rcx+rax*2+2], 0
0x180026fd6  lea     rax, [rax+1]
0x180026fda  jnz     short loc_180026FD0
0x180026fdc  lea     r8d, [rax+1]
0x180026fe0  add     r8, r8; Size
0x180026fe3  lea     rcx, [rdi+10h]; void *
0x180026fe7  lea     rdx, [rsp+3C0h+Src]; Src
0x180026fec  call    memcpy_0
0x180026ff1  lea     rcx, [rbp+2C0h+var_2D4]
0x180026ff5  mov     rax, rbx
0x180026ff8  nop     dword ptr [rax+rax+00000000h]
0x180027000  cmp     word ptr [rcx+rax*2+2], 0
0x180027006  lea     rax, [rax+1]
0x18002700a  jnz     short loc_180027000
0x18002700c  lea     r8d, [rax+1]
0x180027010  add     r8, r8; Size
0x180027013  lea     rcx, [rdi+90h]; void *
0x18002701a  lea     rdx, [rbp+2C0h+var_2D4]; Src
0x18002701e  call    memcpy_0
0x180027023  mov     eax, [rbp+2C0h+var_254]
0x180027026  lea     rcx, [rbp+2C0h+var_24C]
0x18002702a  mov     [rdi+110h], eax
0x180027030  mov     eax, [rbp+2C0h+var_250]
0x180027033  mov     [rdi+114h], eax
0x180027039  mov     rax, rbx
0x18002703c  nop     dword ptr [rax+00h]
0x180027040  cmp     word ptr [rcx+rax*2+2], 0
0x180027046  lea     rax, [rax+1]
0x18002704a  jnz     short loc_180027040
0x18002704c  lea     r8d, [rax+1]
0x180027050  add     r8, r8; Size
0x180027053  lea     rcx, [rdi+118h]; void *
0x18002705a  lea     rdx, [rbp+2C0h+var_24C]; Src
0x18002705e  call    memcpy_0
0x180027063  mov     eax, [rbp+2C0h+var_1CC]
0x180027069  lea     rcx, [rbp+2C0h+var_1C8]
0x180027070  mov     [rdi+198h], eax
0x180027076  mov     rax, rbx
0x180027079  nop     dword ptr [rax+00000000h]
0x180027080  cmp     word ptr [rcx+rax*2+2], 0
0x180027086  lea     rax, [rax+1]
0x18002708a  jnz     short loc_180027080
0x18002708c  lea     r8d, [rax+1]
0x180027090  add     r8, r8; Size
0x180027093  lea     rcx, [rdi+19Ch]; void *
0x18002709a  lea     rdx, [rbp+2C0h+var_1C8]; Src
0x1800270a1  call    memcpy_0
0x1800270a6  mov     eax, [rbp+2C0h+var_148]
0x1800270ac  mov     [rdi+21Ch], eax
0x1800270b2  mov     eax, [rbp+2C0h+var_144]
0x1800270b8  mov     [rdi+220h], eax
0x1800270be  lea     rax, [rbp+2C0h+var_140]
0x1800270c5  nop     word ptr [rax+rax+00000000h]
0x1800270d0  cmp     word ptr [rax+rbx*2+2], 0
0x1800270d6  lea     rbx, [rbx+1]
0x1800270da  jnz     short loc_1800270D0
0x1800270dc  lea     r8d, [rbx+1]
0x1800270e0  add     r8, r8; Size
0x1800270e3  lea     rcx, [rdi+224h]; void *
0x1800270ea  lea     rdx, [rbp+2C0h+var_140]; Src
0x1800270f1  call    memcpy_0
0x1800270f6  mov     eax, [rsi+3Ch]
0x1800270f9  mov     [rdi+2A4h], eax
0x1800270ff  jmp     loc_180026EE0
0x180027104  xor     edx, edx; Val
0x180027106  mov     [rsp+3C0h+var_360], 1
0x18002710e  mov     r8d, 324h; Size
0x180027114  lea     rcx, [rsp+3C0h+var_35C]; void *
0x180027119  call    memset_0
0x18002711e  mov     ecx, [rsi+18h]; unsigned int
0x180027121  call    ?ConvertSchannelProtocolToSsl@@YAGK@Z; ConvertSchannelProtocolToSsl(ulong)
0x180027126  mov     r9d, [rsi+3Ch]
0x18002712a  mov     r8d, [rsi+38h]
0x18002712e  mov     rcx, [rsi+58h]
0x180027132  movzx   edx, ax
0x180027135  lea     rax, [rsp+3C0h+var_35C]
0x18002713a  mov     [rsp+3C0h+var_398], 0
0x180027142  mov     [rsp+3C0h+pvPara], rax
0x180027147  call    cs:__imp_SslLookupCipherSuiteInfo
0x18002714d  mov     r14d, eax
0x180027150  test    eax, eax
0x180027152  jnz     loc_180026EE0
0x180027158  mov     eax, [rsi+18h]
0x18002715b  lea     rcx, [rsp+3C0h+var_360]; struct _NCRYPT_SSL_CIPHER_SUITE_EX *
0x180027160  mov     [rdi], eax
0x180027162  call    ?LookupSymmetricCipherAlg@@YAIPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z; LookupSymmetricCipherAlg(_NCRYPT_SSL_CIPHER_SUITE_EX *)
0x180027167  mov     [rdi+4], eax
0x18002716a  add     eax, 0FFFF9000h
0x18002716f  cmp     eax, 0Fh
0x180027172  jbe     loc_180027625
0x180027178  mov     eax, [rbp+2C0h+var_250]
0x18002717b  lea     rcx, [rsp+3C0h+var_360]; struct _NCRYPT_SSL_CIPHER_SUITE_EX *
0x180027180  mov     [rdi+8], eax
0x180027183  call    ?LookupChecksumAlg@@YAIPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z; LookupChecksumAlg(_NCRYPT_SSL_CIPHER_SUITE_EX *)
0x180027188  mov     [rdi+0Ch], eax
0x18002718b  add     eax, 0FFFF7000h
0x180027190  cmp     eax, 0Fh
0x180027193  jbe     loc_180027631
0x180027199  mov     eax, [rbp+2C0h+var_1C8]
0x18002719f  lea     rcx, [rsp+3C0h+var_360]; struct _NCRYPT_SSL_CIPHER_SUITE_EX *
0x1800271a4  mov     [rdi+10h], eax
0x1800271a7  call    ?LookupExchangeAlg@@YAIPEAU_NCRYPT_SSL_CIPHER_SUITE_EX@@@Z; LookupExchangeAlg(_NCRYPT_SSL_CIPHER_SUITE_EX *)
0x1800271ac  mov     [rdi+14h], eax
0x1800271af  add     eax, 0FFFF5000h
0x1800271b4  cmp     eax, 4
0x1800271b7  jbe     loc_18002763D
0x1800271bd  test    dword ptr [rdi], 3000h
0x1800271c3  mov     eax, [rsi+1Ch]
0x1800271c6  mov     [rdi+18h], eax
0x1800271c9  jz      loc_180026EE0
0x1800271cf  mov     dword ptr [rdi+14h], 0AE06h
0x1800271d6  jmp     loc_180026EE0
0x1800271db  mov     rdx, rdi; struct _SecPkgContext_Bindings *
0x1800271de  mov     rcx, rsi; struct CSslUserContext *
0x1800271e1  call    ?SpQueryEndpointBindings@@YAJPEAUCSslUserContext@@PEAU_SecPkgContext_Bindings@@@Z; SpQueryEndpointBindings(CSslUserContext *,_SecPkgContext_Bindings *)
0x1800271e6  jmp     loc_180026EDD
0x1800271eb  mov     eax, 80090301h
0x1800271f0  jmp     loc_180026EEB
0x1800271f5  mov     eax, 304h
0x1800271fa  jmp     loc_180026F74
0x1800271ff  cmp     r10, r15; jumptable 0000000180026DF7 case 35
0x180027202  jz      short loc_18002720F
0x180027204  test    byte ptr [r10+1Ch], 4
0x180027209  jnz     loc_18002754A
0x18002720f  mov     rax, [rsi+198h]
0x180027216  test    rax, rax
0x180027219  jz      loc_1800272ED
0x18002721f  mov     ecx, 2
0x180027224  lea     rdi, [rdi+80h]
0x18002722b  movups  xmm0, xmmword ptr [rax]
0x18002722e  lea     rax, [rax+80h]
0x180027235  movups  xmmword ptr [rdi-80h], xmm0
0x180027239  movups  xmm1, xmmword ptr [rax-70h]
0x18002723d  movups  xmmword ptr [rdi-70h], xmm1
0x180027241  movups  xmm0, xmmword ptr [rax-60h]
0x180027245  movups  xmmword ptr [rdi-60h], xmm0
0x180027249  movups  xmm1, xmmword ptr [rax-50h]
0x18002724d  movups  xmmword ptr [rdi-50h], xmm1
0x180027251  movups  xmm0, xmmword ptr [rax-40h]
0x180027255  movups  xmmword ptr [rdi-40h], xmm0
0x180027259  movups  xmm1, xmmword ptr [rax-30h]
0x18002725d  movups  xmmword ptr [rdi-30h], xmm1
0x180027261  movups  xmm0, xmmword ptr [rax-20h]
0x180027265  movups  xmmword ptr [rdi-20h], xmm0
0x180027269  movups  xmm1, xmmword ptr [rax-10h]
0x18002726d  movups  xmmword ptr [rdi-10h], xmm1
0x180027271  sub     rcx, 1
0x180027275  jnz     short loc_180027224
0x180027277  mov     rax, [rax]
  ... truncated ...
```
