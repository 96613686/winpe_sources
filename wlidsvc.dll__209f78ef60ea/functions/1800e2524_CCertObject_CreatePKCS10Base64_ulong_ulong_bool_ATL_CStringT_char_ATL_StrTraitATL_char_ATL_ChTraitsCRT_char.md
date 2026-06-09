# CCertObject::CreatePKCS10Base64(ulong,ulong,bool,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x1800e2524`
- end: `0x1800e2e8e`
- name: `?CreatePKCS10Base64@CCertObject@@QEAAJKK_NAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `2410`
- prototype: `__int64 __usercall@<rax>(ATL::CCryptProv *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e22c4`

## callees

- `0x18000c050`
- `0x18000e008`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015fdc`
- `0x1800171f0`
- `0x1800191c0`
- `0x18001921c`
- `0x18001a530`
- `0x18001a9c0`
- `0x180037288`
- `0x180051ccc`
- `0x1800814f8`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800a4778`
- `0x1800e1754`
- `0x1800e2524`
- `0x1800e36cc`
- `0x1800e3708`
- `0x1800e3744`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e271c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e28c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2dce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e271c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e28c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2c53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2dce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e2adf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e2adf`
- `CRYPT32!CryptProtectData` at `0x1800e28b7`
- `CRYPT32!CryptProtectData` at `0x1800e28b7`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800e298d`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800e2a34`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800e298d`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800e2a34`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800e2b59`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800e2c49`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800e2b59`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800e2c49`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x1800e2d09`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x1800e2dc4`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x1800e2d09`
- `CRYPT32!CryptSignAndEncodeCertificate` at `0x1800e2dc4`
- `CRYPTSP!CryptGenKey` at `0x1800e2652`
- `CRYPTSP!CryptGenKey` at `0x1800e2652`
- `CRYPTSP!CryptExportKey` at `0x1800e2712`
- `CRYPTSP!CryptExportKey` at `0x1800e2817`
- `CRYPTSP!CryptExportKey` at `0x1800e2712`
- `CRYPTSP!CryptExportKey` at `0x1800e2817`

## string_xrefs

- `0x1800e259b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2616`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2698`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2753`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e27b7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e285c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2a05`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2b9e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2d76`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2e37`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\cert.cpp`
- `0x1800e2584`: `CCertObject::CreatePKCS10Base64`
- `0x1800e260f`: `CCertObject::CreatePKCS10Base64`
- `0x1800e2691`: `CCertObject::CreatePKCS10Base64`
- `0x1800e274c`: `CCertObject::CreatePKCS10Base64`
- `0x1800e27b0`: `CCertObject::CreatePKCS10Base64`
- `0x1800e2855`: `CCertObject::CreatePKCS10Base64`
- `0x1800e29fe`: `CCertObject::CreatePKCS10Base64`
- `0x1800e2b97`: `CCertObject::CreatePKCS10Base64`
- `0x1800e2d6f`: `CCertObject::CreatePKCS10Base64`
- `0x1800e2e30`: `CCertObject::CreatePKCS10Base64`
- `0x1800e2c00`: `MSIDCRL`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCertObject::CreatePKCS10Base64(const unsigned __int16 **this, int a2, int a3, unsigned __int8 a4)
{
  int v4; // r15d
  PCERT_PUBLIC_KEY_INFO v8; // rdi
  unsigned int v9; // edx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r9
  int inited; // eax
  unsigned int v13; // edx
  const unsigned __int16 *v14; // r9
  signed int LastError; // eax
  signed int v16; // r9d
  signed int v17; // eax
  signed int v18; // r9d
  BYTE *v19; // rcx
  BYTE *v20; // rbx
  signed int v21; // eax
  signed int v22; // r9d
  unsigned int v23; // r8d
  signed int v24; // eax
  int v25; // eax
  signed int v26; // eax
  signed int v27; // r9d
  signed int v28; // eax
  signed int v29; // r9d
  struct CClientConfigDataCacheManager *v30; // rax
  signed int v31; // eax
  signed int v32; // r9d
  unsigned int v33; // r8d
  BYTE *v34; // rcx
  signed int v35; // eax
  signed int v36; // eax
  unsigned __int8 *v37; // rbx
  signed int v38; // eax
  signed int v39; // r9d
  int v40; // eax
  unsigned int v41; // ebx
  unsigned int pbData; // [rsp+20h] [rbp-E0h]
  unsigned int pbDataa; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbEncoded; // [rsp+54h] [rbp-ACh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *pbEncoded; // [rsp+60h] [rbp-A0h] BYREF
  HCRYPTKEY phKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbInfo; // [rsp+70h] [rbp-90h] BYREF
  BYTE *pvStructInfo[2]; // [rsp+78h] [rbp-88h] BYREF
  DATA_BLOB pDataOut; // [rsp+88h] [rbp-78h] BYREF
  __int128 v53; // [rsp+98h] [rbp-68h] BYREF
  DATA_BLOB *p_pDataIn; // [rsp+A8h] [rbp-58h]
  DATA_BLOB pDataIn; // [rsp+B0h] [rbp-50h] BYREF
  PCERT_PUBLIC_KEY_INFO pInfo; // [rsp+C0h] [rbp-40h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER pSignatureAlgorithm; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v58[4]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v59[4]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE *v60; // [rsp+110h] [rbp+10h]
  __int128 v61; // [rsp+118h] [rbp+18h]
  __int128 v62; // [rsp+128h] [rbp+28h]
  __int128 v63; // [rsp+138h] [rbp+38h]
  int v64; // [rsp+148h] [rbp+48h]
  __int128 *v65; // [rsp+150h] [rbp+50h]
  const char *v66[4]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE pvEncoded[256]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v68[256]; // [rsp+280h] [rbp+180h] BYREF

  v4 = a4;
  v45 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v66,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
    783,
    (const char *)&v45,
    "CCertObject::CreatePKCS10Base64",
    L"keySize=%d;keyGenFlags=0x%x");
  pcbInfo = 0;
  v8 = 0;
  pInfo = 0;
  ATL::CCryptProv::Release((ATL::CCryptProv *)this);
  *((_DWORD *)this + 14) = a3;
  if ( (a3 & 0x10) != 0 )
  {
    inited = ATL::CCryptProv::InitVerifyContext((ATL::CCryptProv *)this, v9, v10, (unsigned int)v11);
  }
  else
  {
    inited = ATL::CCryptProv::InitCreateKeySet((ATL::CCryptProv *)this, v9, this[3], v11, pbData);
    v45 = inited;
    if ( inited != -2146893809 )
      goto LABEL_6;
    inited = ATL::CCryptProv::Initialize((ATL::CCryptProv *)this, v13, this[3], v14, pbDataa);
  }
  v45 = inited;
LABEL_6:
  if ( inited < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
      "CCertObject::CreatePKCS10Base64",
      0x32Cu,
      inited,
      "hr");
    goto LABEL_79;
  }
  phKey = 0;
  pbEncoded = (BYTE *)&SmartHCRYPTKEY::`vftable';
  if ( CryptGenKey((HCRYPTPROV)*this, 1u, (a2 << 16) | 1, &phKey) )
    goto LABEL_15;
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError > 0 )
    v16 = (unsigned __int16)LastError | 0x80070000;
  v45 = v16;
  if ( v16 >= 0 )
  {
LABEL_15:
    pcbEncoded = 0;
    pvStructInfo[0] = 0;
    *((_QWORD *)&v53 + 1) = 0;
    LODWORD(v53) = 0;
    LODWORD(p_pDataIn) = 0;
    *(_QWORD *)&pDataIn.cbData = 0;
    pDataIn.pbData = 0;
    *(_QWORD *)&pDataOut.cbData = 0;
    pDataOut.pbData = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&SystemTimeAsFileTime);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(this + 5, &qword_18013DE20);
    if ( !CryptExportKey(phKey, 0, 7u, 0, 0, &pcbEncoded) )
    {
      v17 = GetLastError();
      v18 = v17;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      v45 = v18;
      if ( v18 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
          "CCertObject::CreatePKCS10Base64",
          0x345u,
          v18,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_20:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&SystemTimeAsFileTime);
        CBytePtr::Empty((CBytePtr *)&v53);
        v19 = 0;
LABEL_21:
        operator delete(v19);
        goto LABEL_14;
      }
    }
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(pvStructInfo, pcbEncoded) )
    {
      v45 = -2147024882;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
        "CCertObject::CreatePKCS10Base64",
        0x347u,
        -2147024882,
        "pbKeyblob.Allocate(dwKeyblob)");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&SystemTimeAsFileTime);
      CBytePtr::Empty((CBytePtr *)&v53);
      v19 = pvStructInfo[0];
      goto LABEL_21;
    }
    v20 = pvStructInfo[0];
    if ( !pvStructInfo[0] )
    {
      v45 = -2147024882;
      goto LABEL_20;
    }
    if ( !CryptExportKey(phKey, 0, 7u, 0, pvStructInfo[0], &pcbEncoded) )
    {
      v21 = GetLastError();
      v22 = v21;
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      v45 = v22;
      if ( v22 < 0 )
      {
        v23 = 842;
LABEL_31:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
          "CCertObject::CreatePKCS10Base64",
          v23,
          v22,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_32:
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&SystemTimeAsFileTime);
        CBytePtr::Empty((CBytePtr *)&v53);
        v19 = v20;
        goto LABEL_21;
      }
    }
    pDataIn.cbData = pcbEncoded;
    pDataIn.pbData = v20;
    if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 4 * v4 + 1, &pDataOut) )
    {
      v24 = GetLastError();
      v22 = v24;
      if ( v24 > 0 )
        v22 = (unsigned __int16)v24 | 0x80070000;
      v45 = v22;
      if ( v22 < 0 )
      {
        v23 = 856;
        goto LABEL_31;
      }
    }
    CBytePtr::Attach((CBytePtr *)&v53, pDataOut.pbData, pDataOut.cbData, 1);
    v25 = PassportEncode::Base64Encode(pDataOut.pbData, pDataOut.cbData);
    v45 = v25;
    if ( v25 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
        "CCertObject::CreatePKCS10Base64",
        0x360u,
        v25,
        "hr = PassportEncode::Base64Encode( (void*)dbEncryptedData.pbData, dbEncryptedData.cbData, strBase64Keypair)");
      goto LABEL_32;
    }
    ATL::CSimpleStringT<char,0>::operator=(this + 5, &SystemTimeAsFileTime);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&SystemTimeAsFileTime);
    CBytePtr::Empty((CBytePtr *)&v53);
    operator delete(v20);
    SmartHCRYPTKEY::~SmartHCRYPTKEY((SmartHCRYPTKEY *)&pbEncoded);
    if ( !CryptExportPublicKeyInfo((HCRYPTPROV_OR_NCRYPT_KEY_HANDLE)*this, 1u, 0x10001u, 0, &pcbInfo) )
    {
      v26 = GetLastError();
      v27 = v26;
      if ( v26 > 0 )
        v27 = (unsigned __int16)v26 | 0x80070000;
      v45 = v27;
      if ( v27 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
          "CCertObject::CreatePKCS10Base64",
          0x36Du,
          v27,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
        goto LABEL_79;
      }
    }
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&pInfo, pcbInfo) )
    {
      v45 = -2147024882;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
        "CCertObject::CreatePKCS10Base64",
        0x36Fu,
        -2147024882,
        "spbPublicKeyInfo.Allocate(cbPublicKeyInfo)");
      v8 = pInfo;
      goto LABEL_79;
    }
    v8 = pInfo;
    if ( !CryptExportPublicKeyInfo((HCRYPTPROV_OR_NCRYPT_KEY_HANDLE)*this, 1u, 0x10001u, pInfo, &pcbInfo) )
    {
      v28 = GetLastError();
      v29 = v28;
      if ( v28 > 0 )
        v29 = (unsigned __int16)v28 | 0x80070000;
      v45 = v29;
      if ( v29 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
          "CCertObject::CreatePKCS10Base64",
          0x375u,
          v29,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
        goto LABEL_79;
      }
    }
    memset_0(v59, 0, 0x58u);
    v53 = 0;
    p_pDataIn = 0;
    pDataIn = 0;
    memset_0(pvEncoded, 0, sizeof(pvEncoded));
    memset_0(v68, 0, sizeof(v68));
    pcbEncoded = 0;
    memset(&pSignatureAlgorithm, 0, sizeof(pSignatureAlgorithm));
    pbEncoded = 0;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v30 = CClientConfigDataCacheManager::theConfigDataManager();
    pvStructInfo[0] = (BYTE *)SystemTimeAsFileTime;
    pvStructInfo[0] = (BYTE *)(-10000000LL * *((int *)v30 + 68) + *(_QWORD *)&SystemTimeAsFileTime);
    SystemTimeAsFileTime = (struct _FILETIME)pvStructInfo[0];
    pcbEncoded = 256;
    if ( CryptEncodeObjectEx(1u, "1.2.840.113549.1.9.5", &SystemTimeAsFileTime, 0, 0, pvEncoded, &pcbEncoded) )
      goto LABEL_58;
    v31 = GetLastError();
    v32 = v31;
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    v45 = v32;
    if ( v32 >= 0 )
    {
LABEL_58:
      pDataIn.cbData = pcbEncoded;
      pDataIn.pbData = pvEncoded;
      *(_QWORD *)&v53 = "1.2.840.113549.1.9.5";
      DWORD2(v53) = 1;
      p_pDataIn = &pDataIn;
      v58[1] = 12;
      v58[2] = 16;
      *(_QWORD *)&pDataOut.cbData = 1;
      pvStructInfo[0] = (BYTE *)1;
      v58[0] = "2.5.4.3";
      v58[3] = L"MSIDCRL";
      pDataOut.pbData = (BYTE *)v58;
      pvStructInfo[1] = (BYTE *)&pDataOut;
      pcbEncoded = 256;
      if ( CryptEncodeObjectEx(1u, (LPCSTR)7, pvStructInfo, 0, 0, v68, &pcbEncoded) )
        goto LABEL_63;
      v35 = GetLastError();
      v32 = v35;
      if ( v35 > 0 )
        v32 = (unsigned __int16)v35 | 0x80070000;
      v45 = v32;
      if ( v32 >= 0 )
      {
LABEL_63:
        v59[0] = 0;
        v64 = 1;
        v65 = &v53;
        v59[2] = pcbEncoded;
        v60 = v68;
        v61 = *(_OWORD *)&v8->Algorithm.pszObjId;
        v62 = *(_OWORD *)&v8->Algorithm.Parameters.pbData;
        v63 = *(_OWORD *)&v8->PublicKey.pbData;
        pcbEncoded = 0;
        pSignatureAlgorithm.pszObjId = "1.2.840.113549.1.1.5";
        pSignatureAlgorithm.Parameters = 0;
        if ( CryptSignAndEncodeCertificate(
               (HCRYPTPROV_OR_NCRYPT_KEY_HANDLE)*this,
               1u,
               1u,
               (LPCSTR)4,
               v59,
               &pSignatureAlgorithm,
               0,
               0,
               &pcbEncoded) )
        {
          goto LABEL_82;
        }
        v36 = GetLastError();
        v32 = v36;
        if ( v36 > 0 )
          v32 = (unsigned __int16)v36 | 0x80070000;
        v45 = v32;
        if ( v32 >= 0 )
        {
LABEL_82:
          if ( (unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&pbEncoded, pcbEncoded) )
          {
            v37 = pbEncoded;
            if ( CryptSignAndEncodeCertificate(
                   (HCRYPTPROV_OR_NCRYPT_KEY_HANDLE)*this,
                   1u,
                   1u,
                   (LPCSTR)4,
                   v59,
                   &pSignatureAlgorithm,
                   0,
                   pbEncoded,
                   &pcbEncoded) )
            {
              goto LABEL_75;
            }
            v38 = GetLastError();
            v39 = v38;
            if ( v38 > 0 )
              v39 = (unsigned __int16)v38 | 0x80070000;
            v45 = v39;
            if ( v39 >= 0 )
            {
LABEL_75:
              v40 = PassportEncode::Base64Encode(v37, pcbEncoded);
              v45 = v40;
              if ( v40 < 0 )
                Telemetry::IfFailExit(
                  "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
                  "CCertObject::CreatePKCS10Base64",
                  0x40Fu,
                  v40,
                  "hr = PassportEncode::Base64Encode(pAsn1OnStackPKCS10, cbBlob, strBase64PKCS10)");
            }
            else
            {
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
                "CCertObject::CreatePKCS10Base64",
                0x40Au,
                v39,
                "hr = HRESULT_FROM_WIN32(GetLastError())");
            }
            v34 = v37;
          }
          else
          {
            v45 = -2147024882;
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
              "CCertObject::CreatePKCS10Base64",
              0x3FDu,
              -2147024882,
              "pAsn1OnStackPKCS10.Allocate(cbBlob)");
            v34 = pbEncoded;
          }
          goto LABEL_78;
        }
        v33 = 1019;
      }
      else
      {
        v33 = 987;
      }
    }
    else
    {
      v33 = 943;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
      "CCertObject::CreatePKCS10Base64",
      v33,
      v32,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
    v34 = 0;
LABEL_78:
    operator delete(v34);
    goto LABEL_79;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\cert.cpp",
    "CCertObject::CreatePKCS10Base64",
    0x335u,
    v16,
    "hr = HRESULT_FROM_WIN32(GetLastError())");
LABEL_14:
  SmartHCRYPTKEY::~SmartHCRYPTKEY((SmartHCRYPTKEY *)&pbEncoded);
LABEL_79:
  v41 = v45;
  operator delete(v8);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v66);
  return v41;
}

```

## disassembly

```asm
0x1800e2524  mov     [rsp-8+arg_18], rbx
0x1800e2529  push    rbp
0x1800e252a  push    rsi
0x1800e252b  push    rdi
0x1800e252c  push    r12
0x1800e252e  push    r13
0x1800e2530  push    r14
0x1800e2532  push    r15
0x1800e2534  lea     rbp, [rsp-290h]
0x1800e253c  sub     rsp, 390h
0x1800e2543  mov     rax, cs:__security_cookie
0x1800e254a  xor     rax, rsp
0x1800e254d  mov     [rbp+2C0h+var_40], rax
0x1800e2554  movzx   r15d, r9b
0x1800e2558  mov     ebx, r8d
0x1800e255b  mov     r14d, edx
0x1800e255e  mov     rsi, rcx
0x1800e2561  mov     r12, [rbp+2C0h+arg_20]
0x1800e2568  xor     r13d, r13d
0x1800e256b  mov     [rsp+3C0h+var_370], r13d
0x1800e2570  mov     dword ptr [rsp+3C0h+pbEncoded], ebx
0x1800e2574  mov     dword ptr [rsp+3C0h+pDataOut], edx
0x1800e2578  lea     rax, aKeysizeDKeygen; "keySize=%d;keyGenFlags=0x%x"
0x1800e257f  mov     [rsp+3C0h+pdwDataLen], rax
0x1800e2584  lea     rax, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
0x1800e258b  mov     [rsp+3C0h+pbData], rax; unsigned int
0x1800e2590  lea     r9, [rsp+3C0h+var_370]
0x1800e2595  mov     r8d, 30Fh
0x1800e259b  lea     rdx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e25a2  lea     rcx, [rbp+2C0h+var_260]
0x1800e25a6  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800e25ab  nop
0x1800e25ac  mov     [rsp+3C0h+pcbInfo], r13d
0x1800e25b1  mov     edi, r13d
0x1800e25b4  mov     [rbp+2C0h+pInfo], r13
0x1800e25b8  mov     rcx, rsi; this
0x1800e25bb  call    ?Release@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::Release(void)
0x1800e25c0  mov     [rsi+38h], ebx
0x1800e25c3  mov     rcx, rsi; this
0x1800e25c6  test    bl, 10h
0x1800e25c9  jz      short loc_1800E25D2
0x1800e25cb  call    ?InitVerifyContext@CCryptProv@ATL@@QEAAJKPEBGK@Z; ATL::CCryptProv::InitVerifyContext(ulong,ushort const *,ulong)
0x1800e25d0  jmp     short loc_1800E25F2
0x1800e25d2  mov     r8, [rsi+18h]; unsigned __int16 *
0x1800e25d6  call    ?InitCreateKeySet@CCryptProv@ATL@@QEAAJKPEBG0K@Z; ATL::CCryptProv::InitCreateKeySet(ulong,ushort const *,ushort const *,ulong)
0x1800e25db  mov     [rsp+3C0h+var_370], eax
0x1800e25df  cmp     eax, 8009000Fh
0x1800e25e4  jnz     short loc_1800E25F6
0x1800e25e6  mov     r8, [rsi+18h]; unsigned __int16 *
0x1800e25ea  mov     rcx, rsi; this
0x1800e25ed  call    ?Initialize@CCryptProv@ATL@@QEAAJKPEBG0K@Z; ATL::CCryptProv::Initialize(ulong,ushort const *,ushort const *,ulong)
0x1800e25f2  mov     [rsp+3C0h+var_370], eax
0x1800e25f6  test    eax, eax
0x1800e25f8  jns     short loc_1800E2627
0x1800e25fa  lea     r8, aHr; "hr"
0x1800e2601  mov     [rsp+3C0h+pbData], r8; char *
0x1800e2606  mov     r9d, eax; int
0x1800e2609  mov     r8d, 32Ch; unsigned int
0x1800e260f  lea     rdx, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
0x1800e2616  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e261d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e2622  jmp     loc_1800E2E4C
0x1800e2627  xor     eax, eax
0x1800e2629  mov     [rsp+3C0h+phKey], rax
0x1800e262e  lea     rax, ??_7SmartHCRYPTKEY@@6B@; const SmartHCRYPTKEY::`vftable'
0x1800e2635  mov     [rsp+3C0h+var_360], rax
0x1800e263a  shl     r14d, 10h
0x1800e263e  or      r14d, 1
0x1800e2642  lea     r9, [rsp+3C0h+phKey]; phKey
0x1800e2647  mov     r8d, r14d; dwFlags
0x1800e264a  mov     edx, 1; Algid
0x1800e264f  mov     rcx, [rsi]; hProv
0x1800e2652  call    cs:__imp_CryptGenKey
0x1800e2658  mov     ebx, 80070000h
0x1800e265d  test    eax, eax
0x1800e265f  jnz     short loc_1800E26B4
0x1800e2661  call    cs:__imp_GetLastError
0x1800e2667  mov     r9d, eax
0x1800e266a  test    eax, eax
0x1800e266c  jle     short loc_1800E2675
0x1800e266e  movzx   r9d, ax
0x1800e2672  or      r9d, ebx; int
0x1800e2675  mov     [rsp+3C0h+var_370], r9d
0x1800e267a  test    r9d, r9d
0x1800e267d  jns     short loc_1800E26B4
0x1800e267f  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800e2686  mov     [rsp+3C0h+pbData], rax; char *
0x1800e268b  mov     r8d, 335h; unsigned int
0x1800e2691  lea     rdx, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
0x1800e2698  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e269f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e26a4  nop
0x1800e26a5  lea     rcx, [rsp+3C0h+var_360]; this
0x1800e26aa  call    ??1SmartHCRYPTKEY@@UEAA@XZ; SmartHCRYPTKEY::~SmartHCRYPTKEY(void)
0x1800e26af  jmp     loc_1800E2E4C
0x1800e26b4  mov     [rsp+3C0h+pcbEncoded], r13d
0x1800e26b9  mov     [rsp+3C0h+pvStructInfo], r13
0x1800e26be  mov     qword ptr [rbp+2C0h+var_328+8], r13
0x1800e26c2  mov     dword ptr [rbp+2C0h+var_328], r13d
0x1800e26c6  mov     dword ptr [rbp+2C0h+var_318], r13d
0x1800e26ca  mov     qword ptr [rbp+2C0h+pDataIn.cbData], r13
0x1800e26ce  mov     [rbp+2C0h+pDataIn.pbData], r13
0x1800e26d2  mov     qword ptr [rbp+2C0h+var_338.cbData], r13
0x1800e26d6  mov     [rbp+2C0h+var_338.pbData], r13
0x1800e26da  lea     rcx, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e26df  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e26e4  nop
0x1800e26e5  lea     rdx, qword_18013DE20
0x1800e26ec  lea     rcx, [rsi+28h]
0x1800e26f0  call    ??4?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(ushort const *)
0x1800e26f5  lea     rax, [rsp+3C0h+pcbEncoded]
0x1800e26fa  mov     [rsp+3C0h+pdwDataLen], rax; pdwDataLen
0x1800e26ff  mov     [rsp+3C0h+pbData], r13; pbData
0x1800e2704  xor     r9d, r9d; dwFlags
0x1800e2707  xor     edx, edx; hExpKey
0x1800e2709  lea     r8d, [r9+7]; dwBlobType
0x1800e270d  mov     rcx, [rsp+3C0h+phKey]; hKey
0x1800e2712  call    cs:__imp_CryptExportKey
0x1800e2718  test    eax, eax
0x1800e271a  jnz     short loc_1800E2781
0x1800e271c  call    cs:__imp_GetLastError
0x1800e2722  mov     r9d, eax
0x1800e2725  test    eax, eax
0x1800e2727  jle     short loc_1800E2730
0x1800e2729  movzx   r9d, ax
0x1800e272d  or      r9d, ebx; int
0x1800e2730  mov     [rsp+3C0h+var_370], r9d
0x1800e2735  test    r9d, r9d
0x1800e2738  jns     short loc_1800E2781
0x1800e273a  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800e2741  mov     [rsp+3C0h+pbData], rax; char *
0x1800e2746  mov     r8d, 345h; unsigned int
0x1800e274c  lea     rdx, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
0x1800e2753  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e275a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e275f  nop
0x1800e2760  lea     rcx, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e2765  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e276a  nop
0x1800e276b  lea     rcx, [rbp+2C0h+var_328]; this
0x1800e276f  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800e2774  nop
0x1800e2775  xor     ecx, ecx; Block
0x1800e2777  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e277c  jmp     loc_1800E26A5
0x1800e2781  mov     edx, [rsp+3C0h+pcbEncoded]
0x1800e2785  lea     rcx, [rsp+3C0h+pvStructInfo]
0x1800e278a  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x1800e278f  test    al, al
0x1800e2791  jnz     short loc_1800E27E0
0x1800e2793  mov     r9d, 8007000Eh; int
0x1800e2799  mov     [rsp+3C0h+var_370], r9d
0x1800e279e  lea     rax, aPbkeyblobAlloc; "pbKeyblob.Allocate(dwKeyblob)"
0x1800e27a5  mov     [rsp+3C0h+pbData], rax; char *
0x1800e27aa  mov     r8d, 347h; unsigned int
0x1800e27b0  lea     rdx, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
0x1800e27b7  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e27be  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e27c3  nop
0x1800e27c4  lea     rcx, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e27c9  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e27ce  nop
0x1800e27cf  lea     rcx, [rbp+2C0h+var_328]; this
0x1800e27d3  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800e27d8  nop
0x1800e27d9  mov     rcx, [rsp+3C0h+pvStructInfo]
0x1800e27de  jmp     short loc_1800E2777
0x1800e27e0  mov     rbx, [rsp+3C0h+pvStructInfo]
0x1800e27e5  test    rbx, rbx
0x1800e27e8  jnz     short loc_1800E27FA
0x1800e27ea  mov     r9d, 8007000Eh
0x1800e27f0  mov     [rsp+3C0h+var_370], r9d
0x1800e27f5  jmp     loc_1800E2760
0x1800e27fa  lea     rax, [rsp+3C0h+pcbEncoded]
0x1800e27ff  mov     [rsp+3C0h+pdwDataLen], rax; pdwDataLen
0x1800e2804  mov     [rsp+3C0h+pbData], rbx; pbData
0x1800e2809  xor     r9d, r9d; dwFlags
0x1800e280c  xor     edx, edx; hExpKey
0x1800e280e  lea     r8d, [r9+7]; dwBlobType
0x1800e2812  mov     rcx, [rsp+3C0h+phKey]; hKey
0x1800e2817  call    cs:__imp_CryptExportKey
0x1800e281d  test    eax, eax
0x1800e281f  jnz     short loc_1800E2886
0x1800e2821  call    cs:__imp_GetLastError
0x1800e2827  mov     r9d, eax
0x1800e282a  test    eax, eax
0x1800e282c  jle     short loc_1800E2839
0x1800e282e  movzx   r9d, ax
0x1800e2832  or      r9d, 80070000h; int
0x1800e2839  mov     [rsp+3C0h+var_370], r9d
0x1800e283e  test    r9d, r9d
0x1800e2841  jns     short loc_1800E2886
0x1800e2843  mov     r8d, 34Ah; unsigned int
0x1800e2849  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800e2850  mov     [rsp+3C0h+pbData], rax; char *
0x1800e2855  lea     rdx, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
0x1800e285c  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e2863  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800e2868  nop
0x1800e2869  lea     rcx, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e286e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e2873  nop
0x1800e2874  lea     rcx, [rbp+2C0h+var_328]; this
0x1800e2878  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800e287d  nop
0x1800e287e  mov     rcx, rbx
0x1800e2881  jmp     loc_1800E2777
0x1800e2886  mov     eax, [rsp+3C0h+pcbEncoded]
0x1800e288a  mov     [rbp+2C0h+pDataIn.cbData], eax
0x1800e288d  mov     [rbp+2C0h+pDataIn.pbData], rbx
0x1800e2891  lea     eax, ds:1[r15*4]
0x1800e2899  lea     rcx, [rbp+2C0h+var_338]
0x1800e289d  mov     [rsp+3C0h+pDataOut], rcx; pDataOut
0x1800e28a2  mov     dword ptr [rsp+3C0h+pdwDataLen], eax; dwFlags
0x1800e28a6  mov     [rsp+3C0h+pbData], r13; pPromptStruct
0x1800e28ab  xor     r9d, r9d; pvReserved
0x1800e28ae  xor     r8d, r8d; pOptionalEntropy
0x1800e28b1  xor     edx, edx; szDataDescr
0x1800e28b3  lea     rcx, [rbp+2C0h+pDataIn]; pDataIn
0x1800e28b7  call    cs:__imp_CryptProtectData
0x1800e28bd  test    eax, eax
0x1800e28bf  jnz     short loc_1800E28EE
0x1800e28c1  call    cs:__imp_GetLastError
0x1800e28c7  mov     r9d, eax
0x1800e28ca  test    eax, eax
0x1800e28cc  jle     short loc_1800E28D9
0x1800e28ce  movzx   r9d, ax
0x1800e28d2  or      r9d, 80070000h
0x1800e28d9  mov     [rsp+3C0h+var_370], r9d
0x1800e28de  test    r9d, r9d
0x1800e28e1  jns     short loc_1800E28EE
0x1800e28e3  mov     r8d, 358h
0x1800e28e9  jmp     loc_1800E2849
0x1800e28ee  mov     r15d, 1
0x1800e28f4  mov     r9b, r15b; bool
0x1800e28f7  mov     r8d, [rbp+2C0h+var_338.cbData]; unsigned int
0x1800e28fb  mov     rdx, [rbp+2C0h+var_338.pbData]; unsigned __int8 *
0x1800e28ff  lea     rcx, [rbp+2C0h+var_328]; this
0x1800e2903  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x1800e2908  lea     r8, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e290d  mov     edx, [rbp+2C0h+var_338.cbData]; int
0x1800e2910  mov     rcx, [rbp+2C0h+var_338.pbData]; unsigned __int8 *
0x1800e2914  call    ?Base64Encode@PassportEncode@@YAJPEBXKAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; PassportEncode::Base64Encode(void const *,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x1800e2919  mov     [rsp+3C0h+var_370], eax
0x1800e291d  test    eax, eax
0x1800e291f  jns     short loc_1800E293B
0x1800e2921  lea     rcx, aHrPassportenco; "hr = PassportEncode::Base64Encode( (voi"...
0x1800e2928  mov     [rsp+3C0h+pbData], rcx
0x1800e292d  mov     r9d, eax
0x1800e2930  mov     r8d, 360h
0x1800e2936  jmp     loc_1800E2855
0x1800e293b  lea     rdx, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e2940  lea     rcx, [rsi+28h]
0x1800e2944  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x1800e2949  nop
0x1800e294a  lea     rcx, [rsp+3C0h+SystemTimeAsFileTime]
0x1800e294f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800e2954  nop
0x1800e2955  lea     rcx, [rbp+2C0h+var_328]; this
0x1800e2959  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x1800e295e  nop
0x1800e295f  mov     rcx, rbx; Block
0x1800e2962  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e2967  nop
0x1800e2968  lea     rcx, [rsp+3C0h+var_360]; this
0x1800e296d  call    ??1SmartHCRYPTKEY@@UEAA@XZ; SmartHCRYPTKEY::~SmartHCRYPTKEY(void)
0x1800e2972  lea     rax, [rsp+3C0h+pcbInfo]
0x1800e2977  mov     [rsp+3C0h+pbData], rax; pcbInfo
0x1800e297c  xor     r9d, r9d; pInfo
0x1800e297f  mov     ebx, 10001h
0x1800e2984  mov     r8d, ebx; dwCertEncodingType
0x1800e2987  mov     edx, r15d; dwKeySpec
0x1800e298a  mov     rcx, [rsi]; hCryptProvOrNCryptKey
0x1800e298d  call    cs:__imp_CryptExportPublicKeyInfo
0x1800e2993  test    eax, eax
0x1800e2995  jnz     short loc_1800E29D0
0x1800e2997  call    cs:__imp_GetLastError
0x1800e299d  mov     r9d, eax
0x1800e29a0  test    eax, eax
0x1800e29a2  jle     short loc_1800E29AF
0x1800e29a4  movzx   r9d, ax
0x1800e29a8  or      r9d, 80070000h
0x1800e29af  mov     [rsp+3C0h+var_370], r9d
0x1800e29b4  test    r9d, r9d
0x1800e29b7  jns     short loc_1800E29D0
0x1800e29b9  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800e29c0  mov     [rsp+3C0h+pbData], rax
0x1800e29c5  mov     r8d, 36Dh
0x1800e29cb  jmp     loc_1800E260F
0x1800e29d0  mov     edx, [rsp+3C0h+pcbInfo]
0x1800e29d4  lea     rcx, [rbp+2C0h+pInfo]
0x1800e29d8  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x1800e29dd  test    al, al
0x1800e29df  jnz     short loc_1800E2A1A
0x1800e29e1  mov     r9d, 8007000Eh; int
0x1800e29e7  mov     [rsp+3C0h+var_370], r9d
0x1800e29ec  lea     rax, aSpbpublickeyin; "spbPublicKeyInfo.Allocate(cbPublicKeyIn"...
0x1800e29f3  mov     [rsp+3C0h+pbData], rax; char *
0x1800e29f8  mov     r8d, 36Fh; unsigned int
0x1800e29fe  lea     rdx, aCcertobjectCre; "CCertObject::CreatePKCS10Base64"
  ... truncated ...
```
