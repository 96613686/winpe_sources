# LiteCryptUtilities::DeriveKeyMaterialWithPSha1(unsigned __int64,uchar *,ulong,uchar *,ulong,char const *,ulong,uint,ulong,uchar * *,ulong *)

- ea: `0x180058be8`
- end: `0x180059343`
- name: `?DeriveKeyMaterialWithPSha1@LiteCryptUtilities@@YAJ_KPEAEK1KPEBDKIKPEAPEAEPEAK@Z`
- size: `1883`
- prototype: `int(LiteCryptUtilities *__hidden this, unsigned __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, const char *, unsigned int, unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18005934c`

## callees

- `0x1800039e4`
- `0x18000a1a8`
- `0x18000cc9c`
- `0x18000e870`
- `0x180021a64`
- `0x180021a90`
- `0x180051250`
- `0x1800512f8`
- `0x180053890`
- `0x180058bb4`
- `0x180058be8`
- `0x180059568`
- `0x1800598fc`
- `0x180059b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058d3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058ed5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058fc5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058d3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058ed5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058fc5`
- `CRYPTSP!CryptGenKey` at `0x180058e10`
- `CRYPTSP!CryptGenKey` at `0x180058e10`
- `CRYPTSP!CryptGetKeyParam` at `0x180058e95`
- `CRYPTSP!CryptGetKeyParam` at `0x180058e95`

## string_xrefs

- `0x1800592a5`: `hr = SafeCopyMemory(spLabelAndSeed, labelLength, pLabel, labelLength)`
- `0x18005928d`: `hr = SafeCopyMemory(static_cast<BYTE*>(spLabelAndSeed) + labelLength, seedLength, pSeed, seedLength)`
- `0x180059270`: `hr = SafeCopyMemory( spAdjustedSecret, adjustedSecretLength, pSecret, secretLength > adjustedSecretLength ? adjustedSecretLength : secretLength)`
- `0x1800591d4`: `hr = SafeCopyMemory(spDerivedKeyBlob+currentKeyFilledLength, adjustedDerviedKeyLength-currentKeyFilledLength, spResultHashBlob, bytesToCopy)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall LiteCryptUtilities::DeriveKeyMaterialWithPSha1(
        LiteCryptUtilities *this,
        const void *a2,
        unsigned __int8 *a3,
        const void *a4,
        unsigned __int8 *SourceSize,
        unsigned int pbData,
        const char *a7,
        ALG_ID Algid,
        unsigned __int8 *a9,
        _QWORD *a10,
        unsigned __int8 **a11)
{
  unsigned int v12; // r14d
  unsigned __int64 v14; // rdx
  const char *v15; // rcx
  unsigned __int8 **v16; // rax
  int v17; // eax
  int v18; // r9d
  unsigned int v19; // r8d
  rsize_t v20; // rbx
  rsize_t v21; // rdi
  char *v22; // r12
  int v23; // r9d
  const char *v24; // rax
  unsigned int v25; // r8d
  LiteCryptUtilities *v26; // r13
  signed int LastError; // eax
  unsigned int v28; // r8d
  const char *v29; // rcx
  unsigned int v30; // ebx
  HLOCAL v31; // rdi
  const BYTE *v32; // rdi
  DWORD v33; // r15d
  char *v34; // r14
  __int64 v35; // r8
  unsigned int v36; // esi
  int v37; // eax
  __int64 v38; // r8
  const char *v39; // rcx
  unsigned int v40; // r8d
  __int64 v41; // r8
  int v42; // eax
  unsigned int v43; // r13d
  unsigned int v44; // ebx
  const unsigned __int16 *dwFlags; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwFlagsb; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v49; // [rsp+30h] [rbp-D0h]
  unsigned int v50[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  DWORD dwDataLen; // [rsp+68h] [rbp-98h]
  DWORD pdwDataLen; // [rsp+6Ch] [rbp-94h] BYREF
  HCRYPTKEY phKey[3]; // [rsp+70h] [rbp-90h] BYREF
  void *Source[3]; // [rsp+88h] [rbp-78h] BYREF
  char *v57; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B0h] [rbp-50h]
  HCRYPTKEY hKey[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v61[3]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v62[3]; // [rsp+E8h] [rbp-18h] BYREF
  int *v63[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v64[10]; // [rsp+120h] [rbp+20h] BYREF
  rsize_t DestinationSize; // [rsp+198h] [rbp+98h] BYREF

  v12 = (unsigned int)a3;
  LODWORD(a7) = 0;
  v64[0] = "LiteCryptUtilities::DeriveKeyMaterialWithPSha1";
  v64[1] = &a7;
  v64[2] = 0;
  v64[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
    (const char *)0x195,
    0,
    dwFlags);
  memset(hKey, 0, sizeof(hKey));
  v57 = 0;
  v59 = 0;
  v58 = 0;
  DestinationSize = 0;
  memset(v62, 0, sizeof(v62));
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v63,
    "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
    (int *)&a7,
    0xBu,
    &qword_180083C10);
  if ( !a4 || !a2 || !v12 || !aWsSecureconver[0] || !a10 || (v16 = a11) == 0 )
  {
    v18 = -2147024809;
    LODWORD(a7) = -2147024809;
    dwFlagsa = "hr = E_INVALIDARG";
    v19 = 428;
    goto LABEL_59;
  }
  *a10 = 0;
  *(_DWORD *)v16 = 0;
  v17 = StringCchLengthA(v15, v14, &DestinationSize);
  LODWORD(a7) = v17;
  if ( v17 < 0 )
  {
    dwFlagsa = "hr = StringCchLengthA(pLabel, INTERNET_MAX_URL_LENGTH, &labelLength)";
    v18 = v17;
    v19 = 437;
LABEL_59:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
      v19,
      v18,
      dwFlagsa);
    goto LABEL_60;
  }
  v20 = DestinationSize;
  v21 = (unsigned int)SourceSize;
  dwDataLen = DestinationSize + (_DWORD)SourceSize;
  v22 = (char *)LocalAlloc(0x40u, (unsigned int)(DestinationSize + (_DWORD)SourceSize));
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v62);
  v62[0] = v22;
  if ( !v22 )
  {
    v23 = -2147024882;
    v24 = "hr = E_OUTOFMEMORY";
    v25 = 443;
LABEL_11:
    LODWORD(a7) = v23;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
      v25,
      v23,
      v24);
    goto LABEL_60;
  }
  if ( memcpy_s_0(v22, v20, "WS-SecureConversation", v20) )
  {
    v23 = -2147418113;
    v24 = "hr = SafeCopyMemory(spLabelAndSeed, labelLength, pLabel, labelLength)";
    v25 = 445;
    goto LABEL_11;
  }
  LODWORD(a7) = 0;
  if ( memcpy_s_0(&v22[v20], v21, a4, v21) )
  {
    v23 = -2147418113;
    v24 = "hr = SafeCopyMemory(static_cast<BYTE*>(spLabelAndSeed) + labelLength, seedLength, pSeed, seedLength)";
    v25 = 446;
    goto LABEL_11;
  }
  LODWORD(a7) = 0;
  *(_QWORD *)v50 = 0;
  v52 = 0;
  v51 = 0;
  pbData = 0;
  pdwDataLen = 4;
  memset(phKey, 0, sizeof(phKey));
  v26 = this;
  if ( !CryptGenKey((HCRYPTPROV)this, Algid, 0, phKey) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(a7) = LastError;
    if ( LastError < 0 )
    {
      v28 = 464;
LABEL_19:
      v29 = "hr = HRESULT_FROM_WIN32(GetLastError())";
LABEL_20:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
        v28,
        LastError,
        v29);
LABEL_21:
      Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>(phKey);
LABEL_22:
      Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
      goto LABEL_60;
    }
  }
  if ( !CryptGetKeyParam(phKey[0], 9u, (BYTE *)&pbData, &pdwDataLen, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(a7) = LastError;
    if ( LastError < 0 )
    {
      v28 = 469;
      goto LABEL_19;
    }
  }
  v30 = pbData >> 3;
  v31 = LocalAlloc(0x40u, pbData >> 3);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v50);
  *(_QWORD *)v50 = v31;
  if ( !v31 )
  {
    LODWORD(a7) = -2147024882;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
      0x1DDu,
      -2147024882,
      "hr = E_OUTOFMEMORY");
    goto LABEL_21;
  }
  v51 = v30;
  memset_0(v31, 0, v30);
  if ( v12 > v30 )
    v12 = v30;
  if ( memcpy_s_0(v31, v30, a2, v12) )
  {
    LODWORD(a7) = -2147418113;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
      0x1E4u,
      -2147418113,
      "hr = SafeCopyMemory( spAdjustedSecret, adjustedSecretLength, pSecret, secretLength > adjustedSecretLength ? adjust"
      "edSecretLength : secretLength)");
    goto LABEL_21;
  }
  LODWORD(a7) = 0;
  LastError = LiteCryptUtilities::ImportRawKeyIntoCSP(
                (HCRYPTPROV)this,
                v31,
                v30,
                Algid,
                dwFlagsb,
                (unsigned int)hKey,
                v49);
  LODWORD(a7) = LastError;
  if ( LastError < 0 )
  {
    v29 = "hr = ImportRawKeyIntoCSP( hProv, spAdjustedSecret, adjustedSecretLength, keyImportAlgId, importFlags, &spSecretKey)";
    v28 = 491;
    goto LABEL_20;
  }
  Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>(phKey);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  v32 = 0;
  *(_QWORD *)v50 = 0;
  v52 = 0;
  v51 = 0;
  v33 = 0;
  LODWORD(a9) = 0;
  v34 = (char *)LocalAlloc(0x40u, v30);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v57);
  v57 = v34;
  if ( !v34 )
  {
    LODWORD(a7) = -2147024882;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
      0x204u,
      -2147024882,
      "hr = E_OUTOFMEMORY");
    goto LABEL_22;
  }
  v58 = v30;
  v36 = 0;
  while ( v36 < v30 )
  {
    LODWORD(DestinationSize) = 0;
    memset(Source, 0, sizeof(Source));
    if ( v32 )
    {
      memset(v61, 0, sizeof(v61));
      *(_QWORD *)v50 = 0;
      v51 = 0;
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v61);
      v61[0] = v32;
      v42 = LiteCryptUtilities::HmacHashHelper((HCRYPTPROV)v26, hKey[0], v41, v32, v33, 0, 0, (BYTE **)v50, &a9);
      LODWORD(a7) = v42;
      if ( v42 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
          "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
          0x22Au,
          v42,
          "hr = HmacHashHelper(hProv, spSecretKey, CALG_SHA1, spAHashPrevious, aHashBlobSize, nullptr, 0, &spAHashBlob, &aHashBlobSize )");
        Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
        goto LABEL_43;
      }
      Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
    }
    else
    {
      v37 = LiteCryptUtilities::HmacHashHelper(
              (HCRYPTPROV)v26,
              hKey[0],
              v35,
              (const BYTE *)v22,
              dwDataLen,
              0,
              0,
              (BYTE **)v50,
              &a9);
      LODWORD(a7) = v37;
      if ( v37 < 0 )
      {
        v39 = "hr = HmacHashHelper(hProv, spSecretKey, CALG_SHA1, spLabelAndSeed, labelAndSeedLength, nullptr, 0, &spAHas"
              "hBlob, &aHashBlobSize )";
        v40 = 539;
LABEL_42:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
          "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
          v40,
          v37,
          v39);
LABEL_43:
        Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
        goto LABEL_22;
      }
    }
    v33 = (unsigned int)a9;
    v32 = *(const BYTE **)v50;
    v37 = LiteCryptUtilities::HmacHashHelper(
            (HCRYPTPROV)v26,
            hKey[0],
            v38,
            *(const BYTE **)v50,
            (DWORD)a9,
            (BYTE *)v22,
            dwDataLen,
            (BYTE **)Source,
            (unsigned __int8 **)&DestinationSize);
    LODWORD(a7) = v37;
    if ( v37 < 0 )
    {
      v39 = "hr = HmacHashHelper(hProv, spSecretKey, CALG_SHA1, spAHashBlob, aHashBlobSize, spLabelAndSeed, labelAndSeedL"
            "ength, &spResultHashBlob, &resultHashSize )";
      v40 = 567;
      goto LABEL_42;
    }
    v43 = v30 - v36;
    if ( v30 - v36 >= (unsigned int)DestinationSize )
      v43 = DestinationSize;
    if ( memcpy_s_0(&v34[v36], v30 - v36, Source[0], v43) )
    {
      LODWORD(a7) = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::DeriveKeyMaterialWithPSha1",
        0x243u,
        -2147418113,
        "hr = SafeCopyMemory(spDerivedKeyBlob+currentKeyFilledLength, adjustedDerviedKeyLength-currentKeyFilledLength, sp"
        "ResultHashBlob, bytesToCopy)");
      goto LABEL_43;
    }
    LODWORD(a7) = 0;
    v36 += v43;
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
    v26 = this;
  }
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  v57 = 0;
  v58 = 0;
  *a10 = v34;
  *(_DWORD *)a11 = v30;
LABEL_60:
  v44 = (unsigned int)a7;
  ErrorVerifier::CheckAgainstList((const char *)v63[3], *v63[2], (unsigned __int64)v63[1], v63[0]);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>(hKey);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
  return v44;
}

```

## disassembly

```asm
0x180058be8  mov     [rsp-8+arg_8], rbx
0x180058bed  mov     [rsp-8+hProv], rcx
0x180058bf2  push    rbp
0x180058bf3  push    rsi
0x180058bf4  push    rdi
0x180058bf5  push    r12
0x180058bf7  push    r13
0x180058bf9  push    r14
0x180058bfb  push    r15
0x180058bfd  lea     rbp, [rsp-40h]
0x180058c02  sub     rsp, 140h
0x180058c09  mov     rsi, r9
0x180058c0c  mov     r14d, r8d
0x180058c0f  mov     r15, rdx
0x180058c12  xor     ebx, ebx
0x180058c14  mov     dword ptr [rbp+70h+arg_30], ebx
0x180058c1a  lea     rdi, aLitecryptutili_1; "LiteCryptUtilities::DeriveKeyMaterialWi"...
0x180058c21  mov     [rbp+70h+var_50], rdi
0x180058c25  lea     rax, [rbp+70h+arg_30]
0x180058c2c  mov     [rbp+70h+var_48], rax
0x180058c30  mov     [rbp+70h+var_40], rbx
0x180058c34  mov     [rbp+70h+var_38], rbx
0x180058c38  xor     r9d, r9d; unsigned int
0x180058c3b  mov     r8d, 195h; char *
0x180058c41  mov     rdx, rdi; char *
0x180058c44  lea     r12, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058c4b  mov     rcx, r12; this
0x180058c4e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180058c53  nop
0x180058c54  mov     [rbp+70h+hKey], rbx
0x180058c58  mov     [rbp+70h+var_A8], rbx
0x180058c5c  mov     [rbp+70h+var_B0], rbx
0x180058c60  mov     [rbp+70h+var_D0], rbx
0x180058c64  mov     [rbp+70h+var_C0], rbx
0x180058c68  mov     [rbp+70h+var_C8], rbx
0x180058c6c  mov     [rbp+70h+DestinationSize], rbx
0x180058c73  mov     [rbp+70h+var_88], rbx
0x180058c77  mov     [rbp+70h+var_78], rbx
0x180058c7b  mov     [rbp+70h+var_80], rbx
0x180058c7f  lea     rax, qword_180083C10
0x180058c86  mov     qword ptr [rsp+170h+dwFlags], rax; int *
0x180058c8b  lea     r9d, [rbx+0Bh]; unsigned __int64
0x180058c8f  lea     r8, [rbp+70h+arg_30]; int *
0x180058c96  mov     rdx, rdi; char *
0x180058c99  lea     rcx, [rbp+70h+var_70]; this
0x180058c9d  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180058ca2  nop
0x180058ca3  test    rsi, rsi
0x180058ca6  jz      loc_1800592B7
0x180058cac  test    r15, r15
0x180058caf  jz      loc_1800592B7
0x180058cb5  test    r14d, r14d
0x180058cb8  jz      loc_1800592B7
0x180058cbe  cmp     byte ptr cs:aWsSecureconver, bl; "WS-SecureConversation"
0x180058cc4  jz      loc_1800592B7
0x180058cca  mov     r13, [rbp+70h+arg_48]
0x180058cd1  test    r13, r13
0x180058cd4  jz      loc_1800592B7
0x180058cda  mov     rax, [rbp+70h+arg_50]
0x180058ce1  test    rax, rax
0x180058ce4  jz      loc_1800592B7
0x180058cea  mov     [r13+0], rbx
0x180058cee  mov     [rax], ebx
0x180058cf0  lea     r8, [rbp+70h+DestinationSize]; unsigned __int64 *
0x180058cf7  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180058cfc  mov     dword ptr [rbp+70h+arg_30], eax
0x180058d02  test    eax, eax
0x180058d04  jns     short loc_180058D20
0x180058d06  lea     r8, aHrStringcchlen; "hr = StringCchLengthA(pLabel, INTERNET_"...
0x180058d0d  mov     qword ptr [rsp+170h+dwFlags], r8
0x180058d12  mov     r9d, eax
0x180058d15  mov     r8d, 1B5h
0x180058d1b  jmp     loc_1800592D6
0x180058d20  mov     rbx, [rbp+70h+DestinationSize]
0x180058d27  mov     edi, dword ptr [rbp+70h+SourceSize]
0x180058d2d  lea     eax, [rbx+rdi]
0x180058d30  mov     [rsp+170h+dwDataLen], eax
0x180058d34  mov     edx, eax; uBytes
0x180058d36  mov     ecx, 40h ; '@'; uFlags
0x180058d3b  call    cs:__imp_LocalAlloc
0x180058d41  mov     r12, rax
0x180058d44  lea     rcx, [rbp+70h+var_88]
0x180058d48  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180058d4d  mov     [rbp+70h+var_88], r12
0x180058d51  test    r12, r12
0x180058d54  jnz     short loc_180058D88
0x180058d56  mov     r9d, 8007000Eh
0x180058d5c  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180058d63  mov     r8d, 1BBh
0x180058d69  mov     dword ptr [rbp+70h+arg_30], r9d
0x180058d70  mov     qword ptr [rsp+170h+dwFlags], rax
0x180058d75  lea     rdx, aLitecryptutili_1; "LiteCryptUtilities::DeriveKeyMaterialWi"...
0x180058d7c  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058d83  jmp     loc_1800592DC
0x180058d88  mov     r9, rbx; SourceSize
0x180058d8b  lea     r8, aWsSecureconver; "WS-SecureConversation"
0x180058d92  mov     rdx, rbx; DestinationSize
0x180058d95  mov     rcx, r12; Destination
0x180058d98  call    memcpy_s_0
0x180058d9d  test    eax, eax
0x180058d9f  jnz     loc_18005929F
0x180058da5  mov     dword ptr [rbp+70h+arg_30], eax
0x180058dab  mov     rdx, rdi; DestinationSize
0x180058dae  lea     rcx, [r12+rbx]; Destination
0x180058db2  mov     r9, rdi; SourceSize
0x180058db5  mov     r8, rsi; Source
0x180058db8  call    memcpy_s_0
0x180058dbd  xor     ebx, ebx
0x180058dbf  test    eax, eax
0x180058dc1  jnz     loc_180059287
0x180058dc7  mov     dword ptr [rbp+70h+arg_30], ebx
0x180058dcd  mov     qword ptr [rsp+170h+var_120], rbx
0x180058dd2  mov     [rsp+170h+var_110], rbx
0x180058dd7  mov     [rsp+170h+var_118], rbx
0x180058ddc  mov     dword ptr [rbp+70h+pbData], ebx
0x180058de2  mov     [rsp+170h+pdwDataLen], 4
0x180058dea  mov     [rsp+170h+phKey], rbx
0x180058def  mov     [rbp+70h+var_F0], rbx
0x180058df3  mov     [rsp+170h+var_F8], rbx
0x180058df8  lea     r9, [rsp+170h+phKey]; phKey
0x180058dfd  xor     r8d, r8d; dwFlags
0x180058e00  mov     edx, [rbp+70h+Algid]; Algid
0x180058e06  mov     r13, [rbp+70h+hProv]
0x180058e0d  mov     rcx, r13; hProv
0x180058e10  call    cs:__imp_CryptGenKey
0x180058e16  mov     edi, 80070000h
0x180058e1b  test    eax, eax
0x180058e1d  jnz     short loc_180058E7B
0x180058e1f  call    cs:__imp_GetLastError
0x180058e25  test    eax, eax
0x180058e27  jle     short loc_180058E2E
0x180058e29  movzx   eax, ax
0x180058e2c  or      eax, edi
0x180058e2e  mov     dword ptr [rbp+70h+arg_30], eax
0x180058e34  test    eax, eax
0x180058e36  jns     short loc_180058E7B
0x180058e38  mov     r8d, 1D0h; unsigned int
0x180058e3e  lea     rcx, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180058e45  mov     qword ptr [rsp+170h+dwFlags], rcx; char *
0x180058e4a  mov     r9d, eax; int
0x180058e4d  lea     rdx, aLitecryptutili_1; "LiteCryptUtilities::DeriveKeyMaterialWi"...
0x180058e54  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058e5b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180058e60  nop
0x180058e61  lea     rcx, [rsp+170h+phKey]
0x180058e66  call    ??1?$Auto@_KV?$CryptKeyFunctor@_K@@VDummyContext@@@@QEAA@XZ; Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>(void)
0x180058e6b  nop
0x180058e6c  lea     rcx, [rsp+170h+var_120]
0x180058e71  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180058e76  jmp     loc_1800592E1
0x180058e7b  mov     [rsp+170h+dwFlags], ebx; unsigned int
0x180058e7f  lea     r9, [rsp+170h+pdwDataLen]; pdwDataLen
0x180058e84  lea     r8, [rbp+70h+pbData]; pbData
0x180058e8b  mov     edx, 9; dwParam
0x180058e90  mov     rcx, [rsp+170h+phKey]; hKey
0x180058e95  call    cs:__imp_CryptGetKeyParam
0x180058e9b  test    eax, eax
0x180058e9d  jnz     short loc_180058EC3
0x180058e9f  call    cs:__imp_GetLastError
0x180058ea5  test    eax, eax
0x180058ea7  jle     short loc_180058EAE
0x180058ea9  movzx   eax, ax
0x180058eac  or      eax, edi
0x180058eae  mov     dword ptr [rbp+70h+arg_30], eax
0x180058eb4  test    eax, eax
0x180058eb6  jns     short loc_180058EC3
0x180058eb8  mov     r8d, 1D5h
0x180058ebe  jmp     loc_180058E3E
0x180058ec3  mov     ebx, dword ptr [rbp+70h+pbData]
0x180058ec9  shr     ebx, 3
0x180058ecc  mov     esi, ebx
0x180058ece  mov     edx, ebx; uBytes
0x180058ed0  mov     ecx, 40h ; '@'; uFlags
0x180058ed5  call    cs:__imp_LocalAlloc
0x180058edb  mov     rdi, rax
0x180058ede  lea     rcx, [rsp+170h+var_120]
0x180058ee3  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180058ee8  mov     qword ptr [rsp+170h+var_120], rdi
0x180058eed  test    rdi, rdi
0x180058ef0  jnz     short loc_180058F16
0x180058ef2  mov     r9d, 8007000Eh
0x180058ef8  mov     dword ptr [rbp+70h+arg_30], r9d
0x180058eff  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180058f06  mov     qword ptr [rsp+170h+dwFlags], rax
0x180058f0b  mov     r8d, 1DDh
0x180058f11  jmp     loc_180058E4D
0x180058f16  mov     [rsp+170h+var_118], rsi
0x180058f1b  mov     r8, rsi; Size
0x180058f1e  xor     edx, edx; Val
0x180058f20  mov     rcx, rdi; void *
0x180058f23  call    memset_0
0x180058f28  cmp     r14d, ebx
0x180058f2b  cmova   r14d, ebx
0x180058f2f  mov     r9d, r14d; SourceSize
0x180058f32  mov     r8, r15; Source
0x180058f35  mov     rdx, rsi; DestinationSize
0x180058f38  mov     rcx, rdi; Destination
0x180058f3b  call    memcpy_s_0
0x180058f40  xor     r14d, r14d
0x180058f43  test    eax, eax
0x180058f45  jnz     loc_180059263
0x180058f4b  mov     dword ptr [rbp+70h+arg_30], r14d
0x180058f52  lea     rax, [rbp+70h+hKey]
0x180058f56  mov     [rsp+170h+var_148], rax; unsigned int
0x180058f5b  mov     r9d, [rbp+70h+Algid]; unsigned int
0x180058f62  mov     r8d, ebx; DestinationSize
0x180058f65  mov     rdx, rdi; Source
0x180058f68  mov     rcx, r13; hProv
0x180058f6b  call    ?ImportRawKeyIntoCSP@LiteCryptUtilities@@YAJ_KPEBEKIKPEA_K@Z; LiteCryptUtilities::ImportRawKeyIntoCSP(unsigned __int64,uchar const *,ulong,uint,ulong,unsigned __int64 *)
0x180058f70  mov     dword ptr [rbp+70h+arg_30], eax
0x180058f76  test    eax, eax
0x180058f78  jns     short loc_180058F8C
0x180058f7a  lea     rcx, aHrImportrawkey_0; "hr = ImportRawKeyIntoCSP( hProv, spAdju"...
0x180058f81  mov     r8d, 1EBh
0x180058f87  jmp     loc_180058E45
0x180058f8c  lea     rcx, [rsp+170h+phKey]
0x180058f91  call    ??1?$Auto@_KV?$CryptKeyFunctor@_K@@VDummyContext@@@@QEAA@XZ; Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>(void)
0x180058f96  nop
0x180058f97  lea     rcx, [rsp+170h+var_120]
0x180058f9c  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180058fa1  mov     rdi, r14
0x180058fa4  mov     qword ptr [rsp+170h+var_120], r14
0x180058fa9  mov     [rsp+170h+var_110], r14
0x180058fae  mov     [rsp+170h+var_118], r14
0x180058fb3  mov     r15d, r14d
0x180058fb6  mov     dword ptr [rbp+70h+arg_40], r14d
0x180058fbd  mov     rdx, rsi; uBytes
0x180058fc0  mov     ecx, 40h ; '@'; uFlags
0x180058fc5  call    cs:__imp_LocalAlloc
0x180058fcb  mov     r14, rax
0x180058fce  lea     rcx, [rbp+70h+var_D0]
0x180058fd2  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180058fd7  mov     [rbp+70h+var_D0], r14
0x180058fdb  xor     ecx, ecx
0x180058fdd  test    r14, r14
0x180058fe0  jnz     short loc_18005901A
0x180058fe2  mov     r9d, 8007000Eh; int
0x180058fe8  mov     dword ptr [rbp+70h+arg_30], r9d
0x180058fef  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180058ff6  mov     qword ptr [rsp+170h+dwFlags], rax; char *
0x180058ffb  mov     r8d, 204h; unsigned int
0x180059001  lea     rdx, aLitecryptutili_1; "LiteCryptUtilities::DeriveKeyMaterialWi"...
0x180059008  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005900f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180059014  nop
0x180059015  jmp     loc_180058E6C
0x18005901a  mov     [rbp+70h+var_C8], rsi
0x18005901e  mov     esi, ecx
0x180059020  cmp     esi, ebx
0x180059022  jnb     loc_180059234
0x180059028  mov     dword ptr [rbp+70h+DestinationSize], ecx
0x18005902e  mov     [rbp+70h+Source], rcx
0x180059032  mov     [rbp+70h+var_D8], rcx
0x180059036  mov     [rbp+70h+var_E0], rcx
0x18005903a  test    rdi, rdi
0x18005903d  jnz     short loc_1800590BA
0x18005903f  lea     rax, [rbp+70h+arg_40]
0x180059046  mov     [rsp+170h+var_130], rax; unsigned __int8 **
0x18005904b  lea     rax, [rsp+170h+var_120]
0x180059050  mov     qword ptr [rsp+170h+var_138], rax; unsigned int
0x180059055  mov     dword ptr [rsp+170h+var_140], ecx; DWORD
0x180059059  mov     [rsp+170h+var_148], rcx; BYTE *
0x18005905e  mov     eax, [rsp+170h+dwDataLen]
0x180059062  mov     [rsp+170h+dwFlags], eax; dwDataLen
0x180059066  mov     r9, r12; unsigned int
0x180059069  mov     rdx, [rbp+70h+hKey]; hKey
0x18005906d  mov     rcx, r13; hProv
0x180059070  call    ?HmacHashHelper@LiteCryptUtilities@@YAJ_K0IPEAEK1KPEAPEAEPEAK@Z; LiteCryptUtilities::HmacHashHelper(unsigned __int64,unsigned __int64,uint,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180059075  mov     dword ptr [rbp+70h+arg_30], eax
0x18005907b  test    eax, eax
0x18005907d  jns     loc_18005912F
0x180059083  lea     rcx, aHrHmachashhelp; "hr = HmacHashHelper(hProv, spSecretKey,"...
0x18005908a  mov     r8d, 21Bh; unsigned int
0x180059090  mov     r9d, eax; int
0x180059093  mov     qword ptr [rsp+170h+dwFlags], rcx; char *
0x180059098  lea     rdx, aLitecryptutili_1; "LiteCryptUtilities::DeriveKeyMaterialWi"...
0x18005909f  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800590a6  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800590ab  nop
0x1800590ac  lea     rcx, [rbp+70h+Source]
0x1800590b0  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x1800590b5  jmp     loc_180059015
0x1800590ba  mov     [rbp+70h+var_A0], rcx
0x1800590be  mov     [rbp+70h+var_90], rcx
0x1800590c2  mov     [rbp+70h+var_98], rcx
0x1800590c6  mov     qword ptr [rsp+170h+var_120], rcx
0x1800590cb  mov     [rsp+170h+var_118], rcx
0x1800590d0  lea     rcx, [rbp+70h+var_A0]
0x1800590d4  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x1800590d9  mov     [rbp+70h+var_A0], rdi
0x1800590dd  lea     rax, [rbp+70h+arg_40]
0x1800590e4  mov     [rsp+170h+var_130], rax; unsigned __int8 **
0x1800590e9  lea     rax, [rsp+170h+var_120]
0x1800590ee  mov     qword ptr [rsp+170h+var_138], rax; unsigned int
0x1800590f3  mov     dword ptr [rsp+170h+var_140], 0; DWORD
0x1800590fb  mov     [rsp+170h+var_148], 0; BYTE *
0x180059104  mov     [rsp+170h+dwFlags], r15d; dwDataLen
0x180059109  mov     r9, rdi; unsigned int
0x18005910c  mov     rdx, [rbp+70h+hKey]; hKey
0x180059110  mov     rcx, r13; hProv
  ... truncated ...
```
