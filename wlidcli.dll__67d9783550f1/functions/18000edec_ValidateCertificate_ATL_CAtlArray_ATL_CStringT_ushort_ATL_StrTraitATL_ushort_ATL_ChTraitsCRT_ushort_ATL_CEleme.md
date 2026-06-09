# ValidateCertificate(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,bool,bool,bool,_CERT_CONTEXT const *,int,IDCRL::_IDCRLCertInfo *)

- ea: `0x18000edec`
- end: `0x18000f844`
- name: `?ValidateCertificate@@YAJPEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@0_N11PEBU_CERT_CONTEXT@@HPEAU_IDCRLCertInfo@IDCRL@@@Z`
- size: `2648`
- prototype: `__int64 __fastcall(int, int, int, int, char, PCCERT_CONTEXT pCertContext, int, void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d5c0`

## callees

- `0x180002da0`
- `0x18000324c`
- `0x1800039e4`
- `0x180008b70`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000cc9c`
- `0x18000d13c`
- `0x18000d3b4`
- `0x18000df8c`
- `0x18000e030`
- `0x18000e448`
- `0x18000e870`
- `0x18000edec`
- `0x180052e48`
- `0x1800530e4`
- `0x180054518`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f16a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f16a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f30b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f523`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f708`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f30b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f523`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eefd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eefd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f558`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000eeef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000f012`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000f54a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000eeef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000f012`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18000f54a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f351`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000f351`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f369`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f380`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f369`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000f380`

## string_xrefs

- `0x18000ee83`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f0fd`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f181`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f22b`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f322`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f474`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f57f`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f607`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f727`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000f71a`: `String copy of thumbprint failed. hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ValidateCertificate(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        char a5,
        PCCERT_CONTEXT pCertContext,
        int a7,
        unsigned __int16 *a8)
{
  const CERT_CONTEXT *v11; // rbx
  unsigned __int16 *v12; // r13
  signed int LastError; // eax
  const wchar_t **v14; // rdi
  unsigned __int8 v15; // dl
  PPTraceStatus *v16; // rcx
  signed int v17; // eax
  const wchar_t *v18; // r12
  int v19; // edi
  struct _FILETIME v20; // rbx
  const wchar_t *v21; // rax
  char v22; // r15
  unsigned int v23; // edi
  _QWORD *v24; // rax
  char v25; // r15
  __int64 v26; // r12
  int RootCAThumbPrint; // eax
  unsigned int v28; // r14d
  __int64 v29; // rdi
  _QWORD *v30; // rax
  unsigned __int16 *v31; // rdx
  __int64 v32; // r8
  int v33; // eax
  int v34; // ebx
  PCCERT_CONTEXT v35; // rbx
  int SubjectName; // eax
  __int64 v37; // rbx
  signed int v38; // eax
  int v39; // eax
  ATL::CStringData *v40; // r15
  unsigned __int64 v41; // r14
  unsigned __int64 v42; // rax
  _BYTE *v43; // r8
  signed int v44; // eax
  unsigned __int16 *v45; // r9
  __int64 v46; // rcx
  unsigned __int16 *v47; // rdx
  unsigned __int16 v48; // r10
  unsigned __int16 *v49; // rax
  unsigned int v50; // ebx
  const unsigned __int16 *v52; // [rsp+20h] [rbp-438h]
  __int64 v53; // [rsp+20h] [rbp-438h]
  int v54; // [rsp+40h] [rbp-418h] BYREF
  char v55; // [rsp+44h] [rbp-414h]
  __int64 v56; // [rsp+48h] [rbp-410h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-408h] BYREF
  void *pvData; // [rsp+58h] [rbp-400h] BYREF
  __int64 v59; // [rsp+60h] [rbp-3F8h] BYREF
  __int64 v60; // [rsp+68h] [rbp-3F0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-3E8h] BYREF
  PCCERT_CONTEXT v62; // [rsp+78h] [rbp-3E0h]
  unsigned __int16 *v63; // [rsp+80h] [rbp-3D8h]
  _QWORD v64[4]; // [rsp+90h] [rbp-3C8h] BYREF
  int v65; // [rsp+B0h] [rbp-3A8h] BYREF
  __int64 v66; // [rsp+B8h] [rbp-3A0h]
  const wil::ResultException *v67; // [rsp+C0h] [rbp-398h] BYREF
  ATL::CAtlException *v68; // [rsp+C8h] [rbp-390h] BYREF
  CPassportException *v69; // [rsp+D0h] [rbp-388h] BYREF
  unsigned __int16 *v70; // [rsp+E0h] [rbp-378h] BYREF
  _BYTE v71[264]; // [rsp+E8h] [rbp-370h] BYREF
  void *v72; // [rsp+1F0h] [rbp-268h] BYREF
  _BYTE v73[264]; // [rsp+1F8h] [rbp-260h] BYREF
  void *Block; // [rsp+300h] [rbp-158h] BYREF
  unsigned __int8 v75[264]; // [rsp+308h] [rbp-150h] BYREF
  unsigned __int8 v76[24]; // [rsp+410h] [rbp-48h] BYREF

  v55 = a4;
  v66 = a2;
  v11 = pCertContext;
  v62 = pCertContext;
  v12 = a8;
  v63 = a8;
  v54 = 0;
  v64[0] = "ValidateCertificate";
  v64[1] = &v54;
  v64[2] = 0;
  v64[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
    "ValidateCertificate",
    (const char *)0x80,
    0,
    v52);
  try
  {
    if ( !a1 || !a2 || !pCertContext || !a8 )
    {
      TracePrintW(
        3u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0x88u,
        L"Invalid parameter");
      v54 = -2147024809;
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
      goto LABEL_95;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v59);
    pcbData = 0;
    pvData = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v60);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v56);
    if ( !CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v54 = LastError;
      LODWORD(v53) = LastError;
      TracePrintW(
        3u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0xA0u,
        L"CertGetCertificateContextProperty failed with hr=0x%x",
        v53);
      v54 = -2146435028;
      ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
      operator delete(0);
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
      goto LABEL_95;
    }
    ATL::CAutoVectorPtr<unsigned char>::Allocate(&pvData, pcbData);
    v14 = (const wchar_t **)pvData;
    if ( !pvData )
    {
      v54 = -2147024882;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0xAAu,
        L"Could not allocate memory for pbKeyProvInfo.");
      ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
      operator delete(0);
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
      goto LABEL_95;
    }
    if ( !CertGetCertificateContextProperty(pCertContext, 2u, pvData, &pcbData) )
    {
      v17 = GetLastError();
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      v54 = v17;
      LODWORD(v53) = v17;
      TracePrintW(
        3u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0xB6u,
        L"CertGetCertificateContextProperty 2 failed with hr=0x%x",
        v53);
      v54 = -2146435028;
      ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
      operator delete(v14);
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
      goto LABEL_95;
    }
    v18 = v14[1];
    LOBYTE(v16) = 5;
    if ( PPTraceStatus::TraceOnFlag(v16, v15) )
    {
      v19 = *((_DWORD *)v14 + 4);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&SystemTimeAsFileTime);
      CertGetSubjectName(pCertContext);
      v20 = SystemTimeAsFileTime;
      v21 = L"null";
      if ( v18 )
        v21 = v18;
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0xC3u,
        L"CSP: %ls, Type: %d, Subject: %hs",
        v21,
        v19,
        SystemTimeAsFileTime);
      ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)&v20 - 24LL));
      v11 = v62;
    }
    if ( *(_QWORD *)(a1 + 8) && !a3 )
    {
      v22 = 0;
      v23 = 0;
      while ( !v22 )
      {
        if ( (unsigned __int64)v23 >= *(_QWORD *)(a1 + 8) )
        {
          v54 = -2146435028;
          ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
          operator delete(pvData);
          ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
          goto LABEL_95;
        }
        if ( v18 )
        {
          if ( *(_QWORD *)ATL::CAtlArray<CPassportStringW,ATL::CElementTraits<CPassportStringW>>::operator[](a1, v23) )
          {
            v24 = (_QWORD *)ATL::CAtlArray<CPassportStringW,ATL::CElementTraits<CPassportStringW>>::operator[](a1, v23);
            if ( !(unsigned int)_o__wcsicmp(v18, *v24) )
            {
              TracePrintW(
                5u,
                "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
                0xCDu,
                L"This certificate matches CSPs given in list");
              v22 = 1;
            }
          }
        }
        ++v23;
      }
      v11 = v62;
    }
    v25 = 0;
    v26 = v66;
    if ( *(_QWORD *)(v66 + 8) )
    {
      RootCAThumbPrint = GetRootCAThumbPrint(v11);
      v54 = RootCAThumbPrint;
      if ( RootCAThumbPrint < 0 )
      {
        LODWORD(v53) = RootCAThumbPrint;
        TracePrintW(
          3u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
          0xDFu,
          L"GetRootCAThumbPrint failed with hr=0x%x",
          v53);
        v54 = -2146435028;
        ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
        operator delete(pvData);
        ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
        CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
        goto LABEL_95;
      }
      v28 = 0;
      v29 = v60;
      while ( !v25 )
      {
        if ( (unsigned __int64)v28 >= *(_QWORD *)(v26 + 8) )
          goto LABEL_51;
        Block = v75;
        ATL::CA2WEX<128>::Init(&Block, v29);
        v30 = (_QWORD *)ATL::CAtlArray<CPassportStringW,ATL::CElementTraits<CPassportStringW>>::operator[](v26, v28);
        v31 = (unsigned __int16 *)Block;
        v32 = *v30 - (_QWORD)Block;
        do
        {
          v33 = *(unsigned __int16 *)((char *)v31 + v32);
          v34 = *v31 - v33;
          if ( v34 )
            break;
          ++v31;
        }
        while ( v33 );
        if ( Block != v75 )
          free(Block);
        if ( !v34 )
        {
          TracePrintW(
            5u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
            0xE8u,
            L"Certificate thumprint is also from the given list");
          v25 = 1;
        }
        ++v28;
      }
      if ( v55 )
        goto LABEL_49;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v35 = v62;
      if ( CompareFileTime(&SystemTimeAsFileTime, &v62->pCertInfo->NotAfter) > 0
        || CompareFileTime(&SystemTimeAsFileTime, &v35->pCertInfo->NotBefore) < 0 )
      {
        goto LABEL_49;
      }
    }
    else
    {
      v29 = v60;
LABEL_51:
      if ( a5 )
      {
LABEL_49:
        v54 = -2146435028;
        ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
        operator delete(pvData);
        ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
        CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
        goto LABEL_95;
      }
      v35 = v62;
    }
    memset_0(a8, 0, 0x108u);
    SubjectName = CertGetSubjectName(v35);
    v54 = SubjectName;
    if ( SubjectName >= 0 )
    {
      v70 = (unsigned __int16 *)v71;
      v37 = v59;
      ATL::CA2WEX<128>::Init(&v70, v59);
      StringCchCopyW(a8 + 36, 0x60u, v70);
      if ( v70 != (unsigned __int16 *)v71 )
        free(v70);
      pcbData = 20;
      if ( CertGetCertificateContextProperty(v62, 3u, v76, &pcbData) )
      {
        v39 = PassportEncode::Base64Encode(v76, 20);
        v54 = v39;
        if ( v39 >= 0 )
        {
          v40 = (ATL::CStringData *)(v56 - 24);
          v41 = *(int *)(v56 - 24 + 8);
          v72 = v73;
          ATL::CA2WEX<128>::Init(&v72, v56);
          v42 = v41;
          v43 = v72;
          if ( v41 <= 0x7FFFFFFE )
          {
            v45 = (unsigned __int16 *)v72;
            v46 = 36;
            v47 = a8;
            do
            {
              if ( !v42 )
                break;
              v48 = *v45;
              if ( !*v45 )
                break;
              ++v45;
              *v47++ = v48;
              --v42;
              --v46;
            }
            while ( v46 );
            v49 = v47 - 1;
            if ( v46 )
              v49 = v47;
            *v49 = 0;
            v44 = v46 == 0 ? 0x8007007A : 0;
          }
          else
          {
            v44 = -2147024809;
            *a8 = 0;
          }
          v54 = v44;
          if ( v43 != v73 )
          {
            free(v43);
            v44 = v54;
          }
          if ( v44 < 0 )
          {
            LODWORD(v53) = v44;
            TracePrintW(
              2u,
              "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
              0x13Au,
              L"String copy of thumbprint failed. hr=0x%x",
              v53);
            v54 = -2146435028;
          }
          ATL::CStringData::Release(v40);
          ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
          operator delete(pvData);
          ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
        }
        else
        {
          LODWORD(v53) = v39;
          TracePrintW(
            2u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
            0x12Fu,
            L"Base64Encode failed for thumbprint. hr=0x%x",
            v53);
          v54 = -2146435028;
          ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
          operator delete(pvData);
          ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
        }
      }
      else
      {
        v38 = GetLastError();
        if ( v38 > 0 )
          v38 = (unsigned __int16)v38 | 0x80070000;
        v54 = v38;
        LODWORD(v53) = v38;
        TracePrintW(
          3u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
          0x127u,
          L"CertGetCertificateContextProperty (CERT_SHA1_HASH_PROP_ID) failed with hr=0x%x",
          v53);
        v54 = -2146435028;
        ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
        operator delete(pvData);
        ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
        CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
      }
    }
    else
    {
      LODWORD(v53) = SubjectName;
      TracePrintW(
        3u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0x10Eu,
        L"CertGetSubjectName failed with hr=0x%x",
        v53);
      v54 = -2146435028;
      ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      operator delete(pvData);
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v64);
    }
  }
  catch ( CPassportException *v69 )
  {
    v54 = *((_DWORD *)v69 + 2);
    if ( v54 >= 0 )
      v54 = -2147418113;
    v12 = v63;
  }
  catch ( ATL::CAtlException *v68 )
  {
    v54 = *(_DWORD *)v68;
    if ( v54 >= 0 )
      v54 = -2147418113;
    v12 = v63;
  }
  catch ( std::bad_alloc )
  {
    v54 = -2147024882;
    v50 = -2147024882;
    v12 = v63;
    goto LABEL_79;
  }
  catch ( long v65 )
  {
    v54 = v65;
    if ( v65 >= 0 )
      v54 = -2147418113;
    v12 = v63;
  }
  catch ( const wil::ResultException *v67 )
  {
    v54 = *((_DWORD *)v67 + 8);
    if ( v54 >= 0 )
      v54 = -2147418113;
    v12 = v63;
  }
LABEL_95:
  v50 = v54;
  if ( v54 < 0 )
LABEL_79:
    memset_0(v12, 0, 0x108u);
  return v50;
}

```

## disassembly

```asm
0x18000edec  mov     r11, rsp
0x18000edef  mov     [r11+18h], rbx
0x18000edf3  mov     [r11+20h], rsi
0x18000edf7  push    rdi
0x18000edf8  push    r12
0x18000edfa  push    r13
0x18000edfc  push    r14
0x18000edfe  push    r15
0x18000ee00  sub     rsp, 430h
0x18000ee07  mov     rax, cs:__security_cookie
0x18000ee0e  xor     rax, rsp
0x18000ee11  mov     [rsp+458h+var_30], rax
0x18000ee19  mov     [rsp+458h+var_414], r9b
0x18000ee1e  mov     r15b, r8b
0x18000ee21  mov     rdi, rdx
0x18000ee24  mov     [rsp+458h+var_3A0], rdx
0x18000ee2c  mov     r14, rcx
0x18000ee2f  mov     rbx, [rsp+458h+pCertContext]
0x18000ee37  mov     [rsp+458h+var_3E0], rbx
0x18000ee3c  mov     r13, [rsp+458h+arg_38]
0x18000ee44  mov     [rsp+458h+var_3D8], r13
0x18000ee4c  xor     esi, esi
0x18000ee4e  mov     [rsp+458h+var_418], esi
0x18000ee52  lea     rdx, aValidatecertif; "ValidateCertificate"
0x18000ee59  mov     [r11-3C8h], rdx
0x18000ee60  lea     rax, [rsp+458h+var_418]
0x18000ee65  mov     [r11-3C0h], rax
0x18000ee6c  mov     [r11-3B8h], rsi
0x18000ee73  mov     [r11-3B0h], rsi
0x18000ee7a  xor     r9d, r9d; unsigned int
0x18000ee7d  mov     r8d, 80h; char *
0x18000ee83  lea     r12, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000ee8a  mov     rcx, r12; this
0x18000ee8d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000ee92  nop
0x18000ee93  test    r14, r14
0x18000ee96  jz      loc_18000F7B0
0x18000ee9c  test    rdi, rdi
0x18000ee9f  jz      loc_18000F7B0
0x18000eea5  test    rbx, rbx
0x18000eea8  jz      loc_18000F7B0
0x18000eeae  test    r13, r13
0x18000eeb1  jz      loc_18000F7B0
0x18000eeb7  lea     rcx, [rsp+458h+var_3F8]
0x18000eebc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000eec1  nop
0x18000eec2  mov     [rsp+458h+pcbData], esi
0x18000eec6  mov     [rsp+458h+pvData], rsi
0x18000eecb  lea     rcx, [rsp+458h+var_3F0]
0x18000eed0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000eed5  nop
0x18000eed6  lea     rcx, [rsp+458h+var_410]
0x18000eedb  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000eee0  nop
0x18000eee1  lea     r9, [rsp+458h+pcbData]; pcbData
0x18000eee6  xor     r8d, r8d; pvData
0x18000eee9  lea     edx, [rsi+2]; dwPropId
0x18000eeec  mov     rcx, rbx; pCertContext
0x18000eeef  call    cs:__imp_CertGetCertificateContextProperty
0x18000eef5  test    eax, eax
0x18000eef7  jnz     loc_18000EF81
0x18000eefd  call    cs:__imp_GetLastError
0x18000ef03  test    eax, eax
0x18000ef05  jle     short loc_18000EF0F
0x18000ef07  movzx   eax, ax
0x18000ef0a  or      eax, 80070000h
0x18000ef0f  mov     [rsp+458h+var_418], eax
0x18000ef13  mov     dword ptr [rsp+458h+var_438], eax
0x18000ef17  lea     r9, aCertgetcertifi_2; "CertGetCertificateContextProperty faile"...
0x18000ef1e  mov     r8d, 0A0h; unsigned int
0x18000ef24  mov     rdx, r12; char *
0x18000ef27  mov     ecx, 3; unsigned __int8
0x18000ef2c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000ef31  mov     [rsp+458h+var_418], 8010002Ch
0x18000ef39  mov     rcx, [rsp+458h+var_410]
0x18000ef3e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ef42  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ef47  nop
0x18000ef48  mov     rcx, [rsp+458h+var_3F0]
0x18000ef4d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ef51  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ef56  nop
0x18000ef57  xor     ecx, ecx; Block
0x18000ef59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ef5e  nop
0x18000ef5f  mov     rcx, [rsp+458h+var_3F8]
0x18000ef64  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ef68  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ef6d  nop
0x18000ef6e  lea     rcx, [rsp+458h+var_3C8]
0x18000ef76  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000ef7b  nop
0x18000ef7c  jmp     loc_18000F7EB
0x18000ef81  mov     edx, [rsp+458h+pcbData]
0x18000ef85  lea     rcx, [rsp+458h+pvData]
0x18000ef8a  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18000ef8f  mov     rdi, [rsp+458h+pvData]
0x18000ef94  test    rdi, rdi
0x18000ef97  jnz     short loc_18000F002
0x18000ef99  mov     [rsp+458h+var_418], 8007000Eh
0x18000efa1  lea     r9, aCouldNotAlloca_1; "Could not allocate memory for pbKeyProv"...
0x18000efa8  mov     r8d, 0AAh; unsigned int
0x18000efae  mov     rdx, r12; char *
0x18000efb1  lea     ecx, [rdi+2]; unsigned __int8
0x18000efb4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000efb9  nop
0x18000efba  mov     rcx, [rsp+458h+var_410]
0x18000efbf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000efc3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000efc8  nop
0x18000efc9  mov     rcx, [rsp+458h+var_3F0]
0x18000efce  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000efd2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000efd7  nop
0x18000efd8  xor     ecx, ecx; Block
0x18000efda  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000efdf  nop
0x18000efe0  mov     rcx, [rsp+458h+var_3F8]
0x18000efe5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000efe9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000efee  nop
0x18000efef  lea     rcx, [rsp+458h+var_3C8]
0x18000eff7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000effc  nop
0x18000effd  jmp     loc_18000F7EB
0x18000f002  lea     r9, [rsp+458h+pcbData]; pcbData
0x18000f007  mov     r8, rdi; pvData
0x18000f00a  mov     edx, 2; dwPropId
0x18000f00f  mov     rcx, rbx; pCertContext
0x18000f012  call    cs:__imp_CertGetCertificateContextProperty
0x18000f018  test    eax, eax
0x18000f01a  jnz     loc_18000F0A5
0x18000f020  call    cs:__imp_GetLastError
0x18000f026  test    eax, eax
0x18000f028  jle     short loc_18000F032
0x18000f02a  movzx   eax, ax
0x18000f02d  or      eax, 80070000h
0x18000f032  mov     [rsp+458h+var_418], eax
0x18000f036  mov     dword ptr [rsp+458h+var_438], eax
0x18000f03a  lea     r9, aCertgetcertifi; "CertGetCertificateContextProperty 2 fai"...
0x18000f041  mov     r8d, 0B6h; unsigned int
0x18000f047  mov     rdx, r12; char *
0x18000f04a  mov     ecx, 3; unsigned __int8
0x18000f04f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f054  mov     [rsp+458h+var_418], 8010002Ch
0x18000f05c  mov     rcx, [rsp+458h+var_410]
0x18000f061  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f065  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f06a  nop
0x18000f06b  mov     rcx, [rsp+458h+var_3F0]
0x18000f070  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f074  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f079  nop
0x18000f07a  mov     rcx, rdi; Block
0x18000f07d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f082  nop
0x18000f083  mov     rcx, [rsp+458h+var_3F8]
0x18000f088  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f08c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f091  nop
0x18000f092  lea     rcx, [rsp+458h+var_3C8]
0x18000f09a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000f09f  nop
0x18000f0a0  jmp     loc_18000F7EB
0x18000f0a5  mov     r12, [rdi+8]
0x18000f0a9  mov     cl, 5; this
0x18000f0ab  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18000f0b0  test    al, al
0x18000f0b2  jz      short loc_18000F11D
0x18000f0b4  mov     edi, [rdi+10h]
0x18000f0b7  lea     rcx, [rsp+458h+SystemTimeAsFileTime]
0x18000f0bc  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000f0c1  nop
0x18000f0c2  lea     rdx, [rsp+458h+SystemTimeAsFileTime]
0x18000f0c7  mov     rcx, rbx; pCertContext
0x18000f0ca  call    ?CertGetSubjectName@@YAJPEBU_CERT_CONTEXT@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CertGetSubjectName(_CERT_CONTEXT const *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18000f0cf  mov     rbx, qword ptr [rsp+458h+SystemTimeAsFileTime.dwLowDateTime]
0x18000f0d4  lea     rax, aNull; "null"
0x18000f0db  test    r12, r12
0x18000f0de  cmovnz  rax, r12
0x18000f0e2  mov     [rsp+458h+var_428], rbx
0x18000f0e7  mov     [rsp+458h+var_430], edi
0x18000f0eb  mov     [rsp+458h+var_438], rax
0x18000f0f0  lea     r9, aCspLsTypeDSubj; "CSP: %ls, Type: %d, Subject: %hs"
0x18000f0f7  mov     r8d, 0C3h; unsigned int
0x18000f0fd  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000f104  mov     ecx, 5; unsigned __int8
0x18000f109  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f10e  nop
0x18000f10f  lea     rcx, [rbx-18h]; this
0x18000f113  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f118  mov     rbx, [rsp+458h+var_3E0]
0x18000f11d  cmp     [r14+8], rsi
0x18000f121  jz      loc_18000F1EF
0x18000f127  test    r15b, r15b
0x18000f12a  jnz     loc_18000F1EF
0x18000f130  mov     r15b, sil
0x18000f133  mov     edi, esi
0x18000f135  test    r15b, r15b
0x18000f138  jnz     loc_18000F1EA
0x18000f13e  mov     ebx, edi
0x18000f140  cmp     rbx, [r14+8]
0x18000f144  jnb     short loc_18000F197
0x18000f146  test    r12, r12
0x18000f149  jz      short loc_18000F193
0x18000f14b  mov     edx, ebx
0x18000f14d  mov     rcx, r14
0x18000f150  call    ??A?$CAtlArray@VCPassportStringW@@V?$CElementTraits@VCPassportStringW@@@ATL@@@ATL@@QEAAAEAVCPassportStringW@@_K@Z; ATL::CAtlArray<CPassportStringW,ATL::CElementTraits<CPassportStringW>>::operator[](unsigned __int64)
0x18000f155  cmp     [rax], rsi
0x18000f158  jz      short loc_18000F193
0x18000f15a  mov     edx, ebx
0x18000f15c  mov     rcx, r14
0x18000f15f  call    ??A?$CAtlArray@VCPassportStringW@@V?$CElementTraits@VCPassportStringW@@@ATL@@@ATL@@QEAAAEAVCPassportStringW@@_K@Z; ATL::CAtlArray<CPassportStringW,ATL::CElementTraits<CPassportStringW>>::operator[](unsigned __int64)
0x18000f164  mov     rdx, [rax]
0x18000f167  mov     rcx, r12
0x18000f16a  call    cs:__imp__o__wcsicmp
0x18000f170  test    eax, eax
0x18000f172  jnz     short loc_18000F193
0x18000f174  lea     r9, aThisCertificat; "This certificate matches CSPs given in "...
0x18000f17b  mov     r8d, 0CDh; unsigned int
0x18000f181  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000f188  lea     ecx, [rax+5]; unsigned __int8
0x18000f18b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f190  mov     r15b, 1
0x18000f193  inc     edi
0x18000f195  jmp     short loc_18000F135
0x18000f197  mov     [rsp+458h+var_418], 8010002Ch
0x18000f19f  mov     rcx, [rsp+458h+var_410]
0x18000f1a4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f1a8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f1ad  nop
0x18000f1ae  mov     rcx, [rsp+458h+var_3F0]
0x18000f1b3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f1b7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f1bc  nop
0x18000f1bd  mov     rcx, [rsp+458h+pvData]; Block
0x18000f1c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f1c7  nop
0x18000f1c8  mov     rcx, [rsp+458h+var_3F8]
0x18000f1cd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f1d1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f1d6  nop
0x18000f1d7  lea     rcx, [rsp+458h+var_3C8]
0x18000f1df  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000f1e4  nop
0x18000f1e5  jmp     loc_18000F7EB
0x18000f1ea  mov     rbx, [rsp+458h+var_3E0]
0x18000f1ef  mov     r15b, sil
0x18000f1f2  mov     r12, [rsp+458h+var_3A0]
0x18000f1fa  cmp     [r12+8], rsi
0x18000f1ff  jz      loc_18000F3DC
0x18000f205  lea     rdx, [rsp+458h+var_3F0]
0x18000f20a  mov     rcx, rbx; pCertContext
0x18000f20d  call    ?GetRootCAThumbPrint@@YAJPEBU_CERT_CONTEXT@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; GetRootCAThumbPrint(_CERT_CONTEXT const *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)
0x18000f212  mov     [rsp+458h+var_418], eax
0x18000f216  test    eax, eax
0x18000f218  jns     short loc_18000F28F
0x18000f21a  mov     dword ptr [rsp+458h+var_438], eax
0x18000f21e  lea     r9, aGetrootcathumb; "GetRootCAThumbPrint failed with hr=0x%x"
0x18000f225  mov     r8d, 0DFh; unsigned int
0x18000f22b  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000f232  mov     ecx, 3; unsigned __int8
0x18000f237  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f23c  mov     [rsp+458h+var_418], 8010002Ch
0x18000f244  mov     rcx, [rsp+458h+var_410]
0x18000f249  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f24d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f252  nop
0x18000f253  mov     rcx, [rsp+458h+var_3F0]
0x18000f258  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f25c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f261  nop
0x18000f262  mov     rcx, [rsp+458h+pvData]; Block
0x18000f267  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f26c  nop
0x18000f26d  mov     rcx, [rsp+458h+var_3F8]
0x18000f272  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f276  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f27b  nop
0x18000f27c  lea     rcx, [rsp+458h+var_3C8]
0x18000f284  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000f289  nop
0x18000f28a  jmp     loc_18000F7EB
0x18000f28f  mov     r14d, esi
0x18000f292  mov     rdi, [rsp+458h+var_3F0]
0x18000f297  test    r15b, r15b
0x18000f29a  jnz     loc_18000F33C
0x18000f2a0  mov     ebx, r14d
0x18000f2a3  cmp     rbx, [r12+8]
0x18000f2a8  jnb     loc_18000F3E1
0x18000f2ae  lea     rax, [rsp+458h+var_150]
0x18000f2b6  mov     [rsp+458h+Block], rax
0x18000f2be  mov     rdx, rdi
0x18000f2c1  lea     rcx, [rsp+458h+Block]
0x18000f2c9  call    ?Init@?$CA2WEX@$0IA@@ATL@@AEAAXPEBDI@Z; ATL::CA2WEX<128>::Init(char const *,uint)
0x18000f2ce  nop
0x18000f2cf  mov     edx, ebx
0x18000f2d1  mov     rcx, r12
0x18000f2d4  call    ??A?$CAtlArray@VCPassportStringW@@V?$CElementTraits@VCPassportStringW@@@ATL@@@ATL@@QEAAAEAVCPassportStringW@@_K@Z; ATL::CAtlArray<CPassportStringW,ATL::CElementTraits<CPassportStringW>>::operator[](unsigned __int64)
0x18000f2d9  mov     rcx, [rsp+458h+Block]; Block
  ... truncated ...
```
