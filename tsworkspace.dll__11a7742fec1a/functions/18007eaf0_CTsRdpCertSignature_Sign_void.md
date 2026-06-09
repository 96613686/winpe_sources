# CTsRdpCertSignature::Sign(void)

- ea: `0x18007eaf0`
- end: `0x18007f245`
- name: `?Sign@CTsRdpCertSignature@@UEAAJXZ`
- size: `1877`
- prototype: `__int64 __fastcall(CTsRdpCertSignature *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x18001c6e4`
- `0x18007d718`
- `0x18007d7f8`
- `0x18007eaf0`
- `0x180088bec`
- `0x180088e00`

## import_xrefs

- `msvcrt!wcstombs_s` at `0x18007ee60`
- `msvcrt!wcstombs_s` at `0x18007ef31`
- `msvcrt!wcstombs_s` at `0x18007ee60`
- `msvcrt!wcstombs_s` at `0x18007ef31`
- `msvcrt!malloc` at `0x18007ed17`
- `msvcrt!malloc` at `0x18007eebd`
- `msvcrt!malloc` at `0x18007ed17`
- `msvcrt!malloc` at `0x18007eebd`
- `msvcrt!free` at `0x18007f1b0`
- `msvcrt!free` at `0x18007f1be`
- `msvcrt!free` at `0x18007f1b0`
- `msvcrt!free` at `0x18007f1be`
- `CRYPT32!CryptSignMessage` at `0x18007efde`
- `CRYPT32!CryptSignMessage` at `0x18007f0ec`
- `CRYPT32!CryptSignMessage` at `0x18007efde`
- `CRYPT32!CryptSignMessage` at `0x18007f0ec`
- `CRYPT32!CertFreeCertificateChain` at `0x18007f1a2`
- `CRYPT32!CertFreeCertificateChain` at `0x18007f1a2`
- `ADVAPI32!RegQueryValueExW` at `0x18007ed03`
- `ADVAPI32!RegQueryValueExW` at `0x18007ed92`
- `ADVAPI32!RegQueryValueExW` at `0x18007ed03`
- `ADVAPI32!RegQueryValueExW` at `0x18007ed92`
- `ADVAPI32!RegCloseKey` at `0x18007f22b`
- `ADVAPI32!RegCloseKey` at `0x18007f22b`
- `ADVAPI32!RegOpenKeyExW` at `0x18007ecd3`
- `ADVAPI32!RegOpenKeyExW` at `0x18007ecd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f152`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f16a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f16a`

## string_xrefs

- `0x18007f1fc`: `attempt to sign with missing certificate/data`
- `0x18007eb98`: `attempt to sign with invalid signer certificate`
- `0x18007ecc5`: `System\CurrentControlSet\Services\TScPubRPC`
- `0x18007ee3f`: `HashAlgorithm registry type is incorrect`

## pseudocode

```c
__int64 __fastcall CTsRdpCertSignature::Sign(CTsRdpCertSignature *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  signed int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v8; // r15
  void *v9; // r12
  CTsRdpCertSignature *v10; // rcx
  unsigned int v11; // eax
  CTsRdpCertSignature *v12; // rcx
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  unsigned int v16; // eax
  LSTATUS v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // esi
  CHAR *v23; // rax
  signed int LastError; // eax
  unsigned int v25; // ebx
  unsigned int v26; // eax
  signed int v27; // eax
  void *v28; // rsi
  unsigned int v29; // eax
  signed int v30; // eax
  unsigned int v31; // ebx
  unsigned int v32; // eax
  signed int v33; // eax
  unsigned int v34; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-A1h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-A1h]
  size_t PtNumOfCharConverted; // [rsp+40h] [rbp-89h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+48h] [rbp-81h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-79h] BYREF
  struct _CERT_CONTEXT **v41; // [rsp+58h] [rbp-71h] BYREF
  BYTE *rgpbToBeSigned[2]; // [rsp+60h] [rbp-69h] BYREF
  _CRYPT_SIGN_MESSAGE_PARA pSignPara; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v44; // [rsp+130h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+138h] [rbp+6Fh] BYREF
  DWORD pcbSignedBlob; // [rsp+140h] [rbp+77h] BYREF
  DWORD Type; // [rsp+148h] [rbp+7Fh] BYREF

  memset_0(&pSignPara, 0, sizeof(pSignPara));
  v2 = *((_QWORD *)this + 7);
  pcbSignedBlob = 0;
  pChainContext = 0;
  v44 = 0;
  v41 = 0;
  cbData = 0;
  hKey = 0;
  if ( v2 && *((_DWORD *)this + 6) )
  {
    if ( !(unsigned int)TsCryptIsValidRdpSignEndCertificate(v2, &Type) )
    {
      v6 = -2147024883;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"attempt to sign with invalid signer certificate",
          -2147024883);
      }
      goto LABEL_97;
    }
    v8 = 0;
    v9 = 0;
    if ( (int)TsCryptConstructCertChain(*((PCCERT_CONTEXT *)this + 7), v3, v4, v5, 0, 0, &pChainContext) < 0 )
    {
      v6 = -2147023728;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(lpcbData) = -2147023728;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v11,
          (__int64)"Unable to construct cert chain for signing",
          lpcbData);
      }
LABEL_87:
      if ( pChainContext )
        CertFreeCertificateChain(pChainContext);
      if ( v8 )
        free(v8);
      if ( v9 )
        free(v9);
      goto LABEL_97;
    }
    v6 = CTsRdpCertSignature::CertChainContextToArray(v10, pChainContext, &v44, (const struct _CERT_CONTEXT ***)&v41);
    if ( v6 < 0 )
    {
      v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 21;
      v15 = "CertChainContextToArray failed";
      goto LABEL_18;
    }
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\TScPubRPC", 0, 0x20019u, &hKey) )
      goto LABEL_56;
    cbData = 0;
    if ( RegQueryValueExW(hKey, L"HashAlgorithm", 0, 0, 0, &cbData) )
      goto LABEL_56;
    Type = 0;
    v8 = malloc(cbData);
    if ( !v8 )
    {
      v6 = -2147024882;
      v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(lpcbDataa) = -2147024882;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v16,
          (__int64)"could not allocate bHashAlgorithm",
          lpcbDataa);
      }
      goto LABEL_84;
    }
    v17 = RegQueryValueExW(hKey, L"HashAlgorithm", 0, &Type, (LPBYTE)v8, &cbData);
    v6 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( v6 < 0 )
      {
        v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_84;
        }
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 23;
        v15 = "RegQueryValueEx failed";
LABEL_18:
        LODWORD(lpcbData) = v6;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v13,
          (__int64)v15,
          lpcbData);
        goto LABEL_84;
      }
      goto LABEL_56;
    }
    PtNumOfCharConverted = 0;
    if ( Type != 1 )
    {
      v6 = -2147024809;
      v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(lpcbData) = -2147024809;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          v18,
          (__int64)"HashAlgorithm registry type is incorrect",
          lpcbData);
      }
      goto LABEL_84;
    }
    if ( wcstombs_s(&PtNumOfCharConverted, 0, 0, (const wchar_t *)v8, cbData) )
    {
      v6 = -2147467259;
      v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 25;
    }
    else
    {
      v9 = malloc(PtNumOfCharConverted);
      if ( !v9 )
      {
        v6 = -2147024882;
        v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(lpcbData) = -2147024882;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
            v21,
            (__int64)"could not allocate bHashAlgorithmA",
            lpcbData);
        }
        goto LABEL_84;
      }
      if ( !wcstombs_s(&PtNumOfCharConverted, (char *)v9, PtNumOfCharConverted, (const wchar_t *)v8, cbData) )
      {
LABEL_56:
        v22 = v44;
        pSignPara.cbSize = 120;
        pSignPara.dwMsgEncodingType = 65537;
        pSignPara.pSigningCert = *v41;
        v23 = "2.16.840.1.101.3.4.2.1";
        if ( v9 )
          v23 = (CHAR *)v9;
        pSignPara.rgpMsgCert = (PCCERT_CONTEXT *)v41;
        pSignPara.HashAlgorithm.pszObjId = v23;
        rgpbToBeSigned[0] = *((BYTE **)this + 2);
        pSignPara.cMsgCert = v44;
        if ( !CryptSignMessage(&pSignPara, 1, 1u, (const BYTE **)rgpbToBeSigned, (DWORD *)this + 6, 0, &pcbSignedBlob) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v25 = LastError;
            if ( LastError > 0 )
              v25 = (unsigned __int16)LastError | 0x80070000;
            v26 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
              v26,
              v25);
          }
          v27 = GetLastError();
          v6 = v27;
          if ( v27 > 0 )
            v6 = (unsigned __int16)v27 | 0x80070000;
          goto LABEL_85;
        }
        v28 = (void *)PAL_System_MemAlloc(pcbSignedBlob);
        if ( v28 )
        {
          if ( CryptSignMessage(
                 &pSignPara,
                 1,
                 1u,
                 (const BYTE **)rgpbToBeSigned,
                 (DWORD *)this + 6,
                 (BYTE *)v28,
                 &pcbSignedBlob) )
          {
            v6 = 0;
            *((_DWORD *)this + 10) = pcbSignedBlob;
            *((_QWORD *)this + 4) = v28;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v30 = GetLastError();
              v31 = v30;
              if ( v30 > 0 )
                v31 = (unsigned __int16)v30 | 0x80070000;
              v32 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
                v32,
                v31);
            }
            v33 = GetLastError();
            v6 = v33;
            if ( v33 > 0 )
              v6 = (unsigned __int16)v33 | 0x80070000;
            LocalFree(v28);
          }
        }
        else
        {
          v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v29 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
              v29,
              (__int64)"pbSignedBlob");
          }
          v6 = -2147024882;
        }
LABEL_84:
        v22 = v44;
LABEL_85:
        if ( v41 )
          CTsRdpCertSignature::FreeCertArray(v12, v22, (const struct _CERT_CONTEXT **)v41);
        goto LABEL_87;
      }
      v6 = -2147467259;
      v12 = (CTsRdpCertSignature *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 27;
    }
    LODWORD(lpcbData) = -2147467259;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
      v19,
      (__int64)"wcstombs_s failed",
      lpcbData);
    goto LABEL_84;
  }
  v6 = -2147023728;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v6;
  }
  v34 = RdpWppGetCurrentThreadActivityIdPrefix();
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    18,
    (unsigned int)WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
    v34,
    (__int64)"attempt to sign with missing certificate/data",
    -2147023728);
LABEL_97:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007eaf0  push    rbp
0x18007eaf2  push    rbx
0x18007eaf3  push    rsi
0x18007eaf4  push    rdi
0x18007eaf5  push    r12
0x18007eaf7  push    r14
0x18007eaf9  push    r15
0x18007eafb  lea     rbp, [rsp-27h]
0x18007eb00  sub     rsp, 0F0h
0x18007eb07  xor     edx, edx; Val
0x18007eb09  mov     rdi, rcx
0x18007eb0c  lea     rcx, [rbp+57h+pSignPara]; void *
0x18007eb10  lea     r8d, [rdx+78h]; Size
0x18007eb14  call    memset_0
0x18007eb19  mov     rcx, [rdi+38h]
0x18007eb1d  xor     esi, esi
0x18007eb1f  mov     [rbp+57h+arg_10], esi
0x18007eb22  mov     [rsp+120h+pChainContext], rsi
0x18007eb27  mov     [rbp+57h+arg_0], esi
0x18007eb2a  mov     [rbp+57h+var_C8], rsi
0x18007eb2e  mov     [rbp+57h+cbData], esi
0x18007eb31  mov     [rbp+57h+hKey], rsi
0x18007eb35  test    rcx, rcx
0x18007eb38  jz      loc_18007F1C6
0x18007eb3e  lea     r14, [rdi+18h]
0x18007eb42  cmp     [r14], esi
0x18007eb45  jz      loc_18007F1C6
0x18007eb4b  lea     rdx, [rbp+57h+Type]
0x18007eb4f  call    TsCryptIsValidRdpSignEndCertificate
0x18007eb54  test    eax, eax
0x18007eb56  jnz     short loc_18007EBA4
0x18007eb58  mov     ebx, 8007000Dh
0x18007eb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eb64  lea     rax, WPP_GLOBAL_Control
0x18007eb6b  cmp     rcx, rax
0x18007eb6e  jz      loc_18007F222
0x18007eb74  test    byte ptr [rcx+1Ch], 8
0x18007eb78  jz      loc_18007F222
0x18007eb7e  cmp     byte ptr [rcx+19h], 2
0x18007eb82  jb      loc_18007F222
0x18007eb88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007eb8d  lea     edx, [rsi+13h]
0x18007eb90  mov     dword ptr [rsp+120h+lpcbData], 8007000Dh
0x18007eb98  lea     rcx, aAttemptToSignW; "attempt to sign with invalid signer cer"...
0x18007eb9f  jmp     loc_18007F203
0x18007eba4  mov     rcx, [rdi+38h]; pCertContext
0x18007eba8  lea     rax, [rsp+120h+pChainContext]
0x18007ebad  mov     [rsp+120h+pcbSignedBlob], rax; __int64
0x18007ebb2  mov     r15, rsi
0x18007ebb5  mov     [rsp+120h+lpcbData], rsi; hAdditionalStore
0x18007ebba  mov     r12, rsi
0x18007ebbd  mov     dword ptr [rsp+120h+phkResult], esi; DWORD
0x18007ebc1  call    TsCryptConstructCertChain
0x18007ebc6  test    eax, eax
0x18007ebc8  jns     short loc_18007EC37
0x18007ebca  mov     ebx, 80070490h
0x18007ebcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ebd6  lea     rax, WPP_GLOBAL_Control
0x18007ebdd  cmp     rcx, rax
0x18007ebe0  jz      loc_18007F196
0x18007ebe6  test    byte ptr [rcx+1Ch], 8
0x18007ebea  jz      loc_18007F196
0x18007ebf0  cmp     byte ptr [rcx+19h], 2
0x18007ebf4  jb      loc_18007F196
0x18007ebfa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ebff  lea     rcx, aUnableToConstr; "Unable to construct cert chain for sign"...
0x18007ec06  mov     dword ptr [rsp+120h+lpcbData], 80070490h
0x18007ec0e  mov     [rsp+120h+phkResult], rcx
0x18007ec13  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x18007ec1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec21  mov     edx, 14h
0x18007ec26  mov     r9d, eax
0x18007ec29  mov     rcx, [rcx+10h]
0x18007ec2d  call    WPP_SF_DsD
0x18007ec32  jmp     loc_18007F196
0x18007ec37  mov     rdx, [rsp+120h+pChainContext]; struct _CERT_CHAIN_CONTEXT *
0x18007ec3c  lea     r9, [rbp+57h+var_C8]; struct _CERT_CONTEXT ***
0x18007ec40  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x18007ec44  call    ?CertChainContextToArray@CTsRdpCertSignature@@AEAAJPEBU_CERT_CHAIN_CONTEXT@@PEAKPEAPEAPEBU_CERT_CONTEXT@@@Z; CTsRdpCertSignature::CertChainContextToArray(_CERT_CHAIN_CONTEXT const *,ulong *,_CERT_CONTEXT const * * *)
0x18007ec49  mov     ebx, eax
0x18007ec4b  test    eax, eax
0x18007ec4d  jns     short loc_18007ECB3
0x18007ec4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec56  lea     rax, WPP_GLOBAL_Control
0x18007ec5d  cmp     rcx, rax
0x18007ec60  jz      loc_18007F17E
0x18007ec66  test    byte ptr [rcx+1Ch], 8
0x18007ec6a  jz      loc_18007F17E
0x18007ec70  cmp     byte ptr [rcx+19h], 2
0x18007ec74  jb      loc_18007F17E
0x18007ec7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ec7f  mov     edx, 15h
0x18007ec84  lea     rcx, aCertchainconte; "CertChainContextToArray failed"
0x18007ec8b  mov     dword ptr [rsp+120h+lpcbData], ebx
0x18007ec8f  mov     [rsp+120h+phkResult], rcx
0x18007ec94  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x18007ec9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eca2  mov     r9d, eax
0x18007eca5  mov     rcx, [rcx+10h]
0x18007eca9  call    WPP_SF_DsD
0x18007ecae  jmp     loc_18007F17E
0x18007ecb3  lea     rax, [rbp+57h+hKey]
0x18007ecb7  mov     r9d, 20019h; samDesired
0x18007ecbd  xor     r8d, r8d; ulOptions
0x18007ecc0  mov     [rsp+120h+phkResult], rax; phkResult
0x18007ecc5  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\TS"...
0x18007eccc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ecd3  call    cs:__imp_RegOpenKeyExW
0x18007ecd9  test    eax, eax
0x18007ecdb  jnz     loc_18007EF7A
0x18007ece1  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ece5  lea     rax, [rbp+57h+cbData]
0x18007ece9  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18007ecee  lea     rdx, aHashalgorithm; "HashAlgorithm"
0x18007ecf5  xor     r9d, r9d; lpType
0x18007ecf8  mov     [rsp+120h+phkResult], rsi; lpData
0x18007ecfd  xor     r8d, r8d; lpReserved
0x18007ed00  mov     [rbp+57h+cbData], esi
0x18007ed03  call    cs:__imp_RegQueryValueExW
0x18007ed09  test    eax, eax
0x18007ed0b  jnz     loc_18007EF7A
0x18007ed11  mov     ecx, [rbp+57h+cbData]; Size
0x18007ed14  mov     [rbp+57h+Type], esi
0x18007ed17  call    cs:__imp_malloc
0x18007ed1d  mov     r15, rax
0x18007ed20  test    rax, rax
0x18007ed23  jnz     short loc_18007ED72
0x18007ed25  mov     ebx, 8007000Eh
0x18007ed2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed31  lea     rax, WPP_GLOBAL_Control
0x18007ed38  cmp     rcx, rax
0x18007ed3b  jz      loc_18007F17E
0x18007ed41  test    byte ptr [rcx+1Ch], 8
0x18007ed45  jz      loc_18007F17E
0x18007ed4b  cmp     byte ptr [rcx+19h], 2
0x18007ed4f  jb      loc_18007F17E
0x18007ed55  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ed5a  lea     edx, [r15+16h]
0x18007ed5e  mov     dword ptr [rsp+120h+lpcbData], 8007000Eh
0x18007ed66  lea     rcx, aCouldNotAlloca_0; "could not allocate bHashAlgorithm"
0x18007ed6d  jmp     loc_18007EC8F
0x18007ed72  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ed76  lea     rax, [rbp+57h+cbData]
0x18007ed7a  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18007ed7f  lea     r9, [rbp+57h+Type]; lpType
0x18007ed83  xor     r8d, r8d; lpReserved
0x18007ed86  mov     [rsp+120h+phkResult], r15; lpData
0x18007ed8b  lea     rdx, aHashalgorithm; "HashAlgorithm"
0x18007ed92  call    cs:__imp_RegQueryValueExW
0x18007ed98  mov     ebx, eax
0x18007ed9a  test    eax, eax
0x18007ed9c  jz      short loc_18007EDF2
0x18007ed9e  jle     short loc_18007EDA9
0x18007eda0  movzx   ebx, ax
0x18007eda3  or      ebx, 80070000h
0x18007eda9  test    ebx, ebx
0x18007edab  jns     loc_18007EF7A
0x18007edb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007edb8  lea     rax, WPP_GLOBAL_Control
0x18007edbf  cmp     rcx, rax
0x18007edc2  jz      loc_18007F17E
0x18007edc8  test    byte ptr [rcx+1Ch], 8
0x18007edcc  jz      loc_18007F17E
0x18007edd2  cmp     byte ptr [rcx+19h], 2
0x18007edd6  jb      loc_18007F17E
0x18007eddc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ede1  mov     edx, 17h
0x18007ede6  lea     rcx, aRegqueryvaluee; "RegQueryValueEx failed"
0x18007eded  jmp     loc_18007EC8B
0x18007edf2  cmp     [rbp+57h+Type], 1
0x18007edf6  mov     [rsp+120h+PtNumOfCharConverted], rsi
0x18007edfb  jz      short loc_18007EE4B
0x18007edfd  mov     ebx, 80070057h
0x18007ee02  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ee09  lea     rax, WPP_GLOBAL_Control
0x18007ee10  cmp     rcx, rax
0x18007ee13  jz      loc_18007F17E
0x18007ee19  test    byte ptr [rcx+1Ch], 8
0x18007ee1d  jz      loc_18007F17E
0x18007ee23  cmp     byte ptr [rcx+19h], 2
0x18007ee27  jb      loc_18007F17E
0x18007ee2d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ee32  mov     edx, 18h
0x18007ee37  mov     dword ptr [rsp+120h+lpcbData], 80070057h
0x18007ee3f  lea     rcx, aHashalgorithmR; "HashAlgorithm registry type is incorrec"...
0x18007ee46  jmp     loc_18007EC8F
0x18007ee4b  mov     eax, [rbp+57h+cbData]
0x18007ee4e  lea     rcx, [rsp+120h+PtNumOfCharConverted]; PtNumOfCharConverted
0x18007ee53  mov     r9, r15; Src
0x18007ee56  mov     [rsp+120h+phkResult], rax; MaxCountInBytes
0x18007ee5b  xor     r8d, r8d; DstSizeInBytes
0x18007ee5e  xor     edx, edx; Dst
0x18007ee60  call    cs:__imp_wcstombs_s
0x18007ee66  test    eax, eax
0x18007ee68  jz      short loc_18007EEB8
0x18007ee6a  mov     ebx, 80004005h
0x18007ee6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ee76  lea     rax, WPP_GLOBAL_Control
0x18007ee7d  cmp     rcx, rax
0x18007ee80  jz      loc_18007F17E
0x18007ee86  test    byte ptr [rcx+1Ch], 8
0x18007ee8a  jz      loc_18007F17E
0x18007ee90  cmp     byte ptr [rcx+19h], 2
0x18007ee94  jb      loc_18007F17E
0x18007ee9a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ee9f  mov     edx, 19h
0x18007eea4  mov     dword ptr [rsp+120h+lpcbData], 80004005h
0x18007eeac  lea     rcx, aWcstombsSFaile; "wcstombs_s failed"
0x18007eeb3  jmp     loc_18007EC8F
0x18007eeb8  mov     rcx, [rsp+120h+PtNumOfCharConverted]; Size
0x18007eebd  call    cs:__imp_malloc
0x18007eec3  mov     r12, rax
0x18007eec6  test    rax, rax
0x18007eec9  jnz     short loc_18007EF19
0x18007eecb  mov     ebx, 8007000Eh
0x18007eed0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eed7  lea     rax, WPP_GLOBAL_Control
0x18007eede  cmp     rcx, rax
0x18007eee1  jz      loc_18007F17E
0x18007eee7  test    byte ptr [rcx+1Ch], 8
0x18007eeeb  jz      loc_18007F17E
0x18007eef1  cmp     byte ptr [rcx+19h], 2
0x18007eef5  jb      loc_18007F17E
0x18007eefb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ef00  lea     edx, [r12+1Ah]
0x18007ef05  mov     dword ptr [rsp+120h+lpcbData], 8007000Eh
0x18007ef0d  lea     rcx, aCouldNotAlloca; "could not allocate bHashAlgorithmA"
0x18007ef14  jmp     loc_18007EC8F
0x18007ef19  mov     eax, [rbp+57h+cbData]
0x18007ef1c  lea     rcx, [rsp+120h+PtNumOfCharConverted]; PtNumOfCharConverted
0x18007ef21  mov     r8, [rsp+120h+PtNumOfCharConverted]; DstSizeInBytes
0x18007ef26  mov     r9, r15; Src
0x18007ef29  mov     rdx, r12; Dst
0x18007ef2c  mov     [rsp+120h+phkResult], rax; MaxCountInBytes
0x18007ef31  call    cs:__imp_wcstombs_s
0x18007ef37  test    eax, eax
0x18007ef39  jz      short loc_18007EF7A
0x18007ef3b  mov     ebx, 80004005h
0x18007ef40  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ef47  lea     rax, WPP_GLOBAL_Control
0x18007ef4e  cmp     rcx, rax
0x18007ef51  jz      loc_18007F17E
0x18007ef57  test    byte ptr [rcx+1Ch], 8
0x18007ef5b  jz      loc_18007F17E
0x18007ef61  cmp     byte ptr [rcx+19h], 2
0x18007ef65  jb      loc_18007F17E
0x18007ef6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ef70  mov     edx, 1Bh
0x18007ef75  jmp     loc_18007EEA4
0x18007ef7a  mov     rcx, [rbp+57h+var_C8]
0x18007ef7e  lea     r9, [rbp+57h+rgpbToBeSigned]; rgpbToBeSigned
0x18007ef82  mov     esi, [rbp+57h+arg_0]
0x18007ef85  mov     edx, 1; fDetachedSignature
0x18007ef8a  mov     [rbp+57h+pSignPara.cbSize], 78h ; 'x'
0x18007ef91  test    r12, r12
0x18007ef94  mov     [rbp+57h+pSignPara.dwMsgEncodingType], 10001h
0x18007ef9b  mov     r8d, edx; cToBeSigned
0x18007ef9e  mov     rax, [rcx]
0x18007efa1  mov     [rbp+57h+pSignPara.pSigningCert], rax
0x18007efa5  lea     rax, a21684011013421; "2.16.840.1.101.3.4.2.1"
0x18007efac  cmovnz  rax, r12
0x18007efb0  mov     [rbp+57h+pSignPara.rgpMsgCert], rcx
0x18007efb4  mov     [rbp+57h+pSignPara.HashAlgorithm.pszObjId], rax
0x18007efb8  lea     rcx, [rbp+57h+pSignPara]; pSignPara
0x18007efbc  mov     rax, [rdi+10h]
0x18007efc0  mov     [rbp+57h+rgpbToBeSigned], rax
0x18007efc4  lea     rax, [rbp+57h+arg_10]
0x18007efc8  mov     [rsp+120h+pcbSignedBlob], rax; pcbSignedBlob
0x18007efcd  mov     [rsp+120h+lpcbData], 0; pbSignedBlob
0x18007efd6  mov     [rsp+120h+phkResult], r14; rgcbToBeSigned
0x18007efdb  mov     [rbp+57h+pSignPara.cMsgCert], esi
0x18007efde  call    cs:__imp_CryptSignMessage
0x18007efe4  test    eax, eax
0x18007efe6  jnz     short loc_18007F062
0x18007efe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007efef  lea     rax, WPP_GLOBAL_Control
0x18007eff6  cmp     rcx, rax
0x18007eff9  jz      short loc_18007F044
0x18007effb  test    byte ptr [rcx+1Ch], 8
0x18007efff  jz      short loc_18007F044
0x18007f001  cmp     byte ptr [rcx+19h], 2
0x18007f005  jb      short loc_18007F044
0x18007f007  call    cs:__imp_GetLastError
0x18007f00d  mov     ebx, eax
0x18007f00f  test    eax, eax
0x18007f011  jle     short loc_18007F01C
0x18007f013  movzx   ebx, ax
0x18007f016  or      ebx, 80070000h
0x18007f01c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007f021  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f028  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x18007f02f  mov     edx, 1Ch
0x18007f034  mov     dword ptr [rsp+120h+phkResult], ebx
0x18007f038  mov     r9d, eax
0x18007f03b  mov     rcx, [rcx+10h]
0x18007f03f  call    WPP_SF_Dd
0x18007f044  call    cs:__imp_GetLastError
0x18007f04a  mov     ebx, eax
0x18007f04c  test    eax, eax
0x18007f04e  jle     loc_18007F181
  ... truncated ...
```
