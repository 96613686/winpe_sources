# CTransport::ObtainResponse(void)

- ea: `0x18006c3f4`
- end: `0x18006ccc1`
- name: `?ObtainResponse@CTransport@@QEAAJXZ`
- size: `2253`
- prototype: `__int64 __fastcall(CTransport *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800ee3d0`

## callees

- `0x1800017a4`
- `0x18000bdcc`
- `0x18000bff0`
- `0x18000e008`
- `0x18000ed04`
- `0x1800151c4`
- `0x18001647c`
- `0x180017bf0`
- `0x18001925c`
- `0x180019690`
- `0x18002dfcc`
- `0x18003b1e0`
- `0x18003c814`
- `0x180046aa4`
- `0x18004add0`
- `0x18004d8c4`
- `0x18005538c`
- `0x18006c3f4`
- `0x180080670`
- `0x18008593c`
- `0x180087cbc`
- `0x18008b65c`
- `0x1800a404c`
- `0x1800d5f70`
- `0x1800dbc84`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c7fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006c7fa`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006c76a`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006c76a`
- `WINHTTP!WinHttpQueryHeaders` at `0x18006c5a7`
- `WINHTTP!WinHttpQueryHeaders` at `0x18006c5a7`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18006c652`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18006c695`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18006c652`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18006c695`
- `WINHTTP!WinHttpReadData` at `0x18006c716`
- `WINHTTP!WinHttpReadData` at `0x18006c716`

## string_xrefs

- `0x18006c477`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006c4f7`: `OnInternetEvent REQUEST_COMPLETE detected, processing results.`
- `0x18006c9ae`: `Response size (%ld) is outside acceptable range - discarding.`
- `0x18006c72b`: `WinHttpReadData bytes read %d.`
- `0x18006c967`: `WinHttpReadData failed 0x%x`
- `0x18006c80c`: `Read total %d characters.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTransport::ObtainResponse(CTransport *this)
{
  _QWORD *v2; // rax
  __int64 v3; // rax
  int Error; // r14d
  __int64 TraceRequest; // rax
  _BYTE *v6; // rax
  __int64 v7; // rax
  int v8; // ecx
  unsigned int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // ebx
  _BYTE *v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  bool v26; // zf
  __int64 v27; // rax
  int v28; // eax
  DWORD v29; // ebx
  _QWORD *v30; // rbx
  __int64 v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  DWORD *v36; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // rdi
  __int64 v39; // rax
  int v40; // eax
  LPDWORD lpdwBufferLength; // [rsp+20h] [rbp-59h]
  LPDWORD lpdwBufferLengtha; // [rsp+20h] [rbp-59h]
  LPDWORD lpdwBufferLengthb; // [rsp+20h] [rbp-59h]
  int lpdwBufferLengthc; // [rsp+20h] [rbp-59h]
  int lpdwBufferLengthd; // [rsp+20h] [rbp-59h]
  LPDWORD lpdwBufferLengthe; // [rsp+20h] [rbp-59h]
  LPDWORD lpdwIndex; // [rsp+28h] [rbp-51h]
  DWORD dwSupportedSchemes; // [rsp+40h] [rbp-39h] BYREF
  __int64 v50; // [rsp+48h] [rbp-31h] BYREF
  int Buffer; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwFirstScheme[2]; // [rsp+58h] [rbp-21h] BYREF
  char v53; // [rsp+60h] [rbp-19h]
  __int64 v54; // [rsp+68h] [rbp-11h] BYREF
  __time64_t Time; // [rsp+70h] [rbp-9h] BYREF
  __int64 v56; // [rsp+78h] [rbp-1h] BYREF
  char v57; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD dwBufferLength; // [rsp+E0h] [rbp+67h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+E8h] [rbp+6Fh] BYREF
  int v61; // [rsp+F0h] [rbp+77h] BYREF
  __int64 pdwAuthTarget; // [rsp+F8h] [rbp+7Fh] BYREF

  v61 = 3;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  Time = 0;
  dwBufferLength = 0;
  dwNumberOfBytesRead = 0;
  Buffer = 0;
  Time = *(_QWORD *)ATL::CTime::GetTickCount(&pdwAuthTarget);
  v2 = (_QWORD *)ATL::CTime::FormatGmt(&Time);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
    0x358u,
    L"Current time is %s.",
    *v2);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pdwAuthTarget);
  v3 = *((_QWORD *)this + 7);
  if ( !v3 )
  {
    Error = -2147418113;
    goto LABEL_54;
  }
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
    0x361u,
    L"ObtainResponse on 0x%p, m_pIdentity=0x%p ",
    this,
    *(_QWORD *)(v3 + 24));
  TraceRequest = WlidsvcUtil::GetTraceRequest(&pdwAuthTarget, *((_QWORD *)this + 7) + 32LL);
  ATL::CSimpleStringT<char,0>::operator=(&v54, TraceRequest);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pdwAuthTarget);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
    0x36Cu,
    L"OnInternetEvent REQUEST_COMPLETE detected, processing results.");
  if ( !*((_QWORD *)this + 5) )
  {
    v6 = operator new[](0x20000u, (const struct std::nothrow_t *)std::nothrow);
    *((_QWORD *)this + 5) = v6;
    if ( !v6 )
    {
      Error = -2147024882;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x374u,
        L"Out of memory allocating response buffer.");
      v7 = WlidsvcUtil::FormatFileAndLine(
             &pdwAuthTarget,
             "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
             885);
      ATL::CSimpleStringT<char,0>::operator=(&v50, v7);
      goto LABEL_38;
    }
    *((_DWORD *)this + 12) = 0;
    *v6 = 0;
  }
  v61 = 4;
  dwBufferLength = 4;
  if ( WinHttpQueryHeaders(*((HINTERNET *)this + 2), 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
  {
    dwSupportedSchemes = 0;
    dwFirstScheme[0] = 0;
    LODWORD(pdwAuthTarget) = 0;
    LODWORD(lpdwBufferLengtha) = Buffer;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x38Du,
      L"WinHttpQueryHeaders returns %d.",
      lpdwBufferLengtha);
    v8 = Buffer;
    *((_DWORD *)this + 21) = Buffer;
    if ( v8 == 200 )
      goto LABEL_20;
    if ( v8 == 401 )
    {
      LODWORD(lpdwBufferLength) = 401;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x39Au,
        L"The server requires authentication. Status %d.",
        lpdwBufferLength);
      if ( !WinHttpQueryAuthSchemes(
              *((HINTERNET *)this + 2),
              &dwSupportedSchemes,
              dwFirstScheme,
              (LPDWORD)&pdwAuthTarget) )
        goto LABEL_20;
      v9 = 931;
      goto LABEL_16;
    }
    if ( v8 != 407 )
    {
      LODWORD(lpdwBufferLength) = v8;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x3BCu,
        L"Error. Status code %d returned.",
        lpdwBufferLength);
      goto LABEL_20;
    }
    LODWORD(lpdwBufferLength) = 407;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x3ABu,
      L"The proxy requires authentication. Status %d.",
      lpdwBufferLength);
    if ( WinHttpQueryAuthSchemes(*((HINTERNET *)this + 2), &dwSupportedSchemes, dwFirstScheme, (LPDWORD)&pdwAuthTarget) )
    {
      v9 = 948;
LABEL_16:
      LODWORD(lpdwIndex) = dwFirstScheme[0];
      LODWORD(lpdwBufferLength) = dwSupportedSchemes;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        v9,
        L"SupportedSchemes %d, FirstScheme %d, Target %d.",
        lpdwBufferLength,
        lpdwIndex,
        pdwAuthTarget);
      goto LABEL_20;
    }
    do
    {
LABEL_20:
      dwBufferLength = 0;
      dwNumberOfBytesRead = 0;
      if ( !WinHttpQueryDataAvailable(*((HINTERNET *)this + 2), &dwBufferLength) )
      {
        Error = ATL::AtlHresultFromLastError();
        LODWORD(lpdwBufferLength) = Error;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
          0x3D4u,
          L"WinHttpQueryDataAvailable failed 0x%x",
          lpdwBufferLength);
        v11 = WlidsvcUtil::FormatFileAndLine(
                &pdwAuthTarget,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
                981);
        ATL::CSimpleStringT<char,0>::operator=(&v50, v11);
        goto LABEL_38;
      }
      LODWORD(lpdwBufferLength) = dwBufferLength;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x3D8u,
        L"WinHttpQueryDataAvailable bytes available %d.",
        lpdwBufferLength);
      v10 = *((int *)this + 12);
      if ( (unsigned int)v10 + dwBufferLength >= 0x20000 )
      {
        Error = -2147186550;
        LODWORD(lpdwBufferLengthb) = v10 + dwBufferLength;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
          0x3DDu,
          L"Response size (%ld) is outside acceptable range - discarding.",
          lpdwBufferLengthb);
        v24 = WlidsvcUtil::FormatFileAndLine(
                &pdwAuthTarget,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
                990);
        ATL::CSimpleStringT<char,0>::operator=(&v50, v24);
        goto LABEL_38;
      }
      if ( !WinHttpReadData(
              *((HINTERNET *)this + 2),
              (LPVOID)(*((_QWORD *)this + 5) + v10),
              dwBufferLength,
              &dwNumberOfBytesRead) )
      {
        Error = ATL::AtlHresultFromLastError();
        LODWORD(lpdwBufferLengthb) = Error;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
          0x3EAu,
          L"WinHttpReadData failed 0x%x",
          lpdwBufferLengthb);
        v23 = WlidsvcUtil::FormatFileAndLine(
                &pdwAuthTarget,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
                1003);
        ATL::CSimpleStringT<char,0>::operator=(&v50, v23);
        goto LABEL_38;
      }
      LODWORD(lpdwBufferLengthb) = dwNumberOfBytesRead;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x3EFu,
        L"WinHttpReadData bytes read %d.",
        lpdwBufferLengthb);
      *((_DWORD *)this + 12) += dwNumberOfBytesRead;
      *(_BYTE *)(*((int *)this + 12) + *((_QWORD *)this + 5)) = 0;
    }
    while ( dwNumberOfBytesRead );
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
    if ( (Microsoft_Windows_LiveIdEnableBits & 1) != 0 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
      McTemplateU0qq_EventWriteTransfer(v15, v14, v12, v13);
    }
    v16 = *((_DWORD *)this + 24);
    *((_DWORD *)this + 18) = GetTickCount64() - v16;
    lpdwBufferLengthc = *((_DWORD *)this + 12);
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x3FEu,
      L"Read total %d characters.");
    v17 = (_BYTE *)*((_QWORD *)this + 5);
    if ( v17 && *v17 )
    {
      v61 = 5;
      CSingleIdentity::SetRequestStatus(*(CSingleIdentity **)(*((_QWORD *)this + 7) + 24LL), -2147186656);
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 7) + 40LL))(
              *((_QWORD *)this + 7),
              *((_QWORD *)this + 5),
              *((unsigned int *)this + 12),
              &v61);
      Error = v18;
      if ( v18 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 8LL))(*((_QWORD *)this + 7));
        goto LABEL_52;
      }
      lpdwBufferLengthd = v18;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x414u,
        L"Unable to parse response (0x%x).");
      if ( Error == -2147188477 )
      {
        v19 = CTransport::LogResponseHeaders(this, *((void **)this + 2));
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x418,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
            (const char *)(unsigned int)v19,
            lpdwBufferLengthd);
      }
      v20 = WlidsvcUtil::FormatFileAndLine(
              &pdwAuthTarget,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
              1051);
      ATL::CSimpleStringT<char,0>::operator=(&v50, v20);
    }
    else
    {
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x402u,
        L"Empty response received from server.");
      v21 = CTransport::LogResponseHeaders(this, *((void **)this + 2));
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x403,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
          (const char *)(unsigned int)v21,
          lpdwBufferLengthc);
      Error = -2147186582;
      v22 = WlidsvcUtil::FormatFileAndLine(
              &pdwAuthTarget,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
              1030);
      ATL::CSimpleStringT<char,0>::operator=(&v50, v22);
    }
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
    LODWORD(lpdwBufferLengtha) = Error;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x3C3u,
      L"WinHttpQueryHeaders failed 0x%x",
      lpdwBufferLengtha);
    v25 = WlidsvcUtil::FormatFileAndLine(
            &pdwAuthTarget,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
            964);
    ATL::CSimpleStringT<char,0>::operator=(&v50, v25);
  }
LABEL_38:
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pdwAuthTarget);
  if ( !*(_QWORD *)(*((_QWORD *)this + 7) + 24LL) )
    goto LABEL_52;
  v26 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NoNetworkOnMSA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NoNetworkOnMSA>::GetImpl'::`2'::impl) == 0;
  v27 = *(_QWORD *)(*((_QWORD *)this + 7) + 24LL);
  if ( v26 )
  {
    if ( !v27 )
    {
      Error = -2147418113;
      goto LABEL_52;
    }
    *(_QWORD *)dwFirstScheme = v27 + 16;
    v53 = 0;
    Error = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(dwFirstScheme);
    if ( Error >= 0 )
    {
      CSingleIdentity::SetRequestStatus(*(CSingleIdentity **)(*((_QWORD *)this + 7) + 24LL), -2147186656);
      v37 = (_QWORD *)*((_QWORD *)this + 7);
      v38 = v37[3];
      v39 = (*(__int64 (__fastcall **)(_QWORD *, DWORD *))(*v37 + 16LL))(v37, &dwSupportedSchemes);
      LODWORD(v37) = (unsigned __int16)CPPCRLBaseRequest::GetPassportRequestPort(v37, v39);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
        &pdwAuthTarget,
        *((_QWORD *)this + 5));
      CSingleIdentity::SetExtendedError(
        v38,
        v61,
        Error,
        (unsigned int)&v50,
        (__int64)&v54,
        (__int64)&pdwAuthTarget,
        (_DWORD)v37);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pdwAuthTarget);
    }
    v36 = dwFirstScheme;
  }
  else
  {
    v56 = v27 + 16;
    v57 = 0;
    v28 = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v56);
    v29 = v28;
    if ( v28 < 0 )
    {
      LODWORD(lpdwIndex) = Error;
      LODWORD(lpdwBufferLength) = v28;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x43Eu,
        L"Failed to acquire identity lock in ObtainResponse, hrLock=0x%x, hr=0x%x.",
        lpdwBufferLength,
        lpdwIndex);
      if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
      {
        *(_QWORD *)dwFirstScheme = 0x1000000;
        LODWORD(pdwAuthTarget) = Error;
        dwSupportedSchemes = v29;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v33,
          (__int64)byte_18019B169,
          v34,
          v35,
          (__int64)&dwSupportedSchemes,
          (__int64)&pdwAuthTarget,
          (__int64)dwFirstScheme);
      }
    }
    else
    {
      CSingleIdentity::SetRequestStatus(*(CSingleIdentity **)(*((_QWORD *)this + 7) + 24LL), -2147186656);
      v30 = (_QWORD *)*((_QWORD *)this + 7);
      v31 = v30[3];
      v32 = (*(__int64 (__fastcall **)(_QWORD *, DWORD *))(*v30 + 16LL))(v30, &dwSupportedSchemes);
      LODWORD(v30) = (unsigned __int16)CPPCRLBaseRequest::GetPassportRequestPort(v30, v32);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
        &pdwAuthTarget,
        *((_QWORD *)this + 5));
      CSingleIdentity::SetExtendedError(
        v31,
        v61,
        Error,
        (unsigned int)&v50,
        (__int64)&v54,
        (__int64)&pdwAuthTarget,
        (_DWORD)v30);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pdwAuthTarget);
    }
    v36 = (DWORD *)&v56;
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v36);
LABEL_52:
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
    0x469u,
    L"this=0x%p, m_pIdentity=0x%p",
    this,
    *(_QWORD *)(*((_QWORD *)this + 7) + 24LL));
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::SetZeroMemory(*((_QWORD *)this + 7) + 32LL);
  v40 = CTransport::CloseAllInternet(this, 0);
  if ( v40 < 0 )
  {
    LODWORD(lpdwBufferLengthe) = v40;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x475u,
      L"Problem trying to close down WinInet (0x%x).",
      lpdwBufferLengthe);
  }
LABEL_54:
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006c3f4  push    rbp
0x18006c3f6  push    rbx
0x18006c3f7  push    rsi
0x18006c3f8  push    rdi
0x18006c3f9  push    r12
0x18006c3fb  push    r13
0x18006c3fd  push    r14
0x18006c3ff  push    r15
0x18006c401  lea     rbp, [rsp-1Fh]
0x18006c406  sub     rsp, 98h
0x18006c40d  mov     rsi, rcx
0x18006c410  mov     [rbp+57h+arg_10], 3
0x18006c417  lea     rcx, [rbp+57h+var_68]
0x18006c41b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006c420  nop
0x18006c421  lea     rcx, [rbp+57h+var_88]
0x18006c425  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006c42a  nop
0x18006c42b  xor     r12d, r12d
0x18006c42e  mov     [rbp+57h+Time], r12
0x18006c432  mov     [rbp+57h+dwBufferLength], r12d
0x18006c436  mov     [rbp+57h+dwNumberOfBytesRead], r12d
0x18006c43a  mov     [rbp+57h+Buffer], r12d
0x18006c43e  lea     rcx, [rbp+57h+pdwAuthTarget]
0x18006c442  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18006c447  mov     rcx, [rax]
0x18006c44a  mov     [rbp+57h+Time], rcx
0x18006c44e  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x18006c455  lea     rdx, [rbp+57h+pdwAuthTarget]
0x18006c459  lea     rcx, [rbp+57h+Time]; Time
0x18006c45d  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x18006c462  mov     rcx, [rax]
0x18006c465  mov     [rsp+0D0h+lpdwBufferLength], rcx
0x18006c46a  lea     r9, aCurrentTimeIsS; "Current time is %s."
0x18006c471  mov     r8d, 358h; unsigned int
0x18006c477  lea     r13, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006c47e  mov     rdx, r13; char *
0x18006c481  lea     edi, [r12+5]
0x18006c486  mov     ecx, edi; unsigned __int8
0x18006c488  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c48d  lea     rcx, [rbp+57h+pdwAuthTarget]
0x18006c491  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006c496  mov     rax, [rsi+38h]
0x18006c49a  test    rax, rax
0x18006c49d  jnz     short loc_18006C4AA
0x18006c49f  mov     r14d, 8000FFFFh
0x18006c4a5  jmp     loc_18006CC97
0x18006c4aa  mov     rax, [rax+18h]
0x18006c4ae  mov     [rsp+0D0h+lpdwIndex], rax
0x18006c4b3  mov     [rsp+0D0h+lpdwBufferLength], rsi
0x18006c4b8  lea     r9, aObtainresponse; "ObtainResponse on 0x%p, m_pIdentity=0x%"...
0x18006c4bf  mov     r8d, 361h; unsigned int
0x18006c4c5  mov     rdx, r13; char *
0x18006c4c8  mov     ecx, edi; unsigned __int8
0x18006c4ca  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c4cf  mov     rdx, [rsi+38h]
0x18006c4d3  add     rdx, 20h ; ' '
0x18006c4d7  lea     rcx, [rbp+57h+pdwAuthTarget]
0x18006c4db  call    ?GetTraceRequest@WlidsvcUtil@@SA?AV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEBV?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@@Z; WlidsvcUtil::GetTraceRequest(CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x18006c4e0  nop
0x18006c4e1  mov     rdx, rax
0x18006c4e4  lea     rcx, [rbp+57h+var_68]
0x18006c4e8  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x18006c4ed  nop
0x18006c4ee  lea     rcx, [rbp+57h+pdwAuthTarget]
0x18006c4f2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006c4f7  lea     r9, aOninterneteven; "OnInternetEvent REQUEST_COMPLETE detect"...
0x18006c4fe  mov     r8d, 36Ch; unsigned int
0x18006c504  mov     rdx, r13; char *
0x18006c507  mov     ecx, edi; unsigned __int8
0x18006c509  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c50e  mov     ebx, 20000h
0x18006c513  cmp     [rsi+28h], r12
0x18006c517  jnz     short loc_18006C57E
0x18006c519  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006c520  mov     ecx, ebx; unsigned __int64
0x18006c522  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006c527  mov     [rsi+28h], rax
0x18006c52b  test    rax, rax
0x18006c52e  jnz     short loc_18006C577
0x18006c530  mov     r14d, 8007000Eh
0x18006c536  lea     r9, aOutOfMemoryAll; "Out of memory allocating response buffe"...
0x18006c53d  mov     r8d, 374h; unsigned int
0x18006c543  mov     rdx, r13; char *
0x18006c546  lea     r15d, [rax+2]
0x18006c54a  mov     ecx, r15d; unsigned __int8
0x18006c54d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c552  mov     r8d, 375h
0x18006c558  mov     rdx, r13
0x18006c55b  lea     rcx, [rbp+57h+pdwAuthTarget]
0x18006c55f  call    ?FormatFileAndLine@WlidsvcUtil@@SA?AV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEBDI@Z; WlidsvcUtil::FormatFileAndLine(char const *,uint)
0x18006c564  nop
0x18006c565  mov     rdx, rax
0x18006c568  lea     rcx, [rbp+57h+var_88]
0x18006c56c  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x18006c571  nop
0x18006c572  jmp     loc_18006CA32
0x18006c577  mov     [rsi+30h], r12d
0x18006c57b  mov     [rax], r12b
0x18006c57e  mov     eax, 4
0x18006c583  mov     [rbp+57h+arg_10], eax
0x18006c586  mov     [rbp+57h+dwBufferLength], eax
0x18006c589  mov     [rsp+0D0h+lpdwIndex], r12; lpdwIndex
0x18006c58e  lea     rax, [rbp+57h+dwBufferLength]
0x18006c592  mov     [rsp+0D0h+lpdwBufferLength], rax; lpdwBufferLength
0x18006c597  lea     r9, [rbp+57h+Buffer]; lpBuffer
0x18006c59b  xor     r8d, r8d; pwszName
0x18006c59e  mov     edx, 20000013h; dwInfoLevel
0x18006c5a3  mov     rcx, [rsi+10h]; hRequest
0x18006c5a7  call    cs:__imp_WinHttpQueryHeaders
0x18006c5ad  test    eax, eax
0x18006c5af  jz      loc_18006C9E8
0x18006c5b5  mov     [rbp+57h+dwSupportedSchemes], r12d
0x18006c5b9  mov     [rbp+57h+dwFirstScheme], r12d
0x18006c5bd  mov     dword ptr [rbp+57h+pdwAuthTarget], r12d
0x18006c5c1  mov     eax, [rbp+57h+Buffer]
0x18006c5c4  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax
0x18006c5c8  lea     r9, aWinhttpqueryhe_1; "WinHttpQueryHeaders returns %d."
0x18006c5cf  mov     r8d, 38Dh; unsigned int
0x18006c5d5  mov     rdx, r13; char *
0x18006c5d8  mov     ecx, edi; unsigned __int8
0x18006c5da  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c5df  mov     ecx, [rbp+57h+Buffer]
0x18006c5e2  mov     [rsi+54h], ecx
0x18006c5e5  mov     eax, ecx
0x18006c5e7  mov     r15d, 2
0x18006c5ed  sub     eax, 0C8h
0x18006c5f2  jz      loc_18006C75A
0x18006c5f8  sub     eax, 0C9h
0x18006c5fd  mov     rdx, r13; char *
0x18006c600  jz      short loc_18006C668
0x18006c602  cmp     eax, 6
0x18006c605  jz      short loc_18006C625
0x18006c607  mov     dword ptr [rsp+0D0h+lpdwBufferLength], ecx
0x18006c60b  lea     r9, aErrorStatusCod; "Error. Status code %d returned."
0x18006c612  mov     r8d, 3BCh; unsigned int
0x18006c618  mov     ecx, r15d; unsigned __int8
0x18006c61b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c620  jmp     loc_18006C75A
0x18006c625  mov     dword ptr [rsp+0D0h+lpdwBufferLength], 197h
0x18006c62d  lea     r9, aTheProxyRequir; "The proxy requires authentication. Stat"...
0x18006c634  mov     r8d, 3ABh; unsigned int
0x18006c63a  mov     ecx, r15d; unsigned __int8
0x18006c63d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c642  lea     r9, [rbp+57h+pdwAuthTarget]; pdwAuthTarget
0x18006c646  lea     r8, [rbp+57h+dwFirstScheme]; lpdwFirstScheme
0x18006c64a  lea     rdx, [rbp+57h+dwSupportedSchemes]; lpdwSupportedSchemes
0x18006c64e  mov     rcx, [rsi+10h]; hRequest
0x18006c652  call    cs:__imp_WinHttpQueryAuthSchemes
0x18006c658  test    eax, eax
0x18006c65a  jz      loc_18006C75A
0x18006c660  mov     r8d, 3B4h
0x18006c666  jmp     short loc_18006C6A9
0x18006c668  mov     dword ptr [rsp+0D0h+lpdwBufferLength], 191h
0x18006c670  lea     r9, aTheServerRequi; "The server requires authentication. Sta"...
0x18006c677  mov     r8d, 39Ah; unsigned int
0x18006c67d  mov     ecx, r15d; unsigned __int8
0x18006c680  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c685  lea     r9, [rbp+57h+pdwAuthTarget]; pdwAuthTarget
0x18006c689  lea     r8, [rbp+57h+dwFirstScheme]; lpdwFirstScheme
0x18006c68d  lea     rdx, [rbp+57h+dwSupportedSchemes]; lpdwSupportedSchemes
0x18006c691  mov     rcx, [rsi+10h]; hRequest
0x18006c695  call    cs:__imp_WinHttpQueryAuthSchemes
0x18006c69b  test    eax, eax
0x18006c69d  jz      loc_18006C75A
0x18006c6a3  mov     r8d, 3A3h; unsigned int
0x18006c6a9  mov     eax, dword ptr [rbp+57h+pdwAuthTarget]
0x18006c6ac  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18006c6b0  mov     eax, [rbp+57h+dwFirstScheme]
0x18006c6b3  mov     dword ptr [rsp+0D0h+lpdwIndex], eax
0x18006c6b7  mov     eax, [rbp+57h+dwSupportedSchemes]
0x18006c6ba  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax
0x18006c6be  lea     r9, aSupportedschem; "SupportedSchemes %d, FirstScheme %d, Ta"...
0x18006c6c5  mov     rdx, r13; char *
0x18006c6c8  mov     ecx, r15d; unsigned __int8
0x18006c6cb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c6d0  jmp     loc_18006C75A
0x18006c6d5  mov     eax, [rbp+57h+dwBufferLength]
0x18006c6d8  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax
0x18006c6dc  lea     r9, aWinhttpqueryda_0; "WinHttpQueryDataAvailable bytes availab"...
0x18006c6e3  mov     r8d, 3D8h; unsigned int
0x18006c6e9  mov     rdx, r13; char *
0x18006c6ec  mov     ecx, edi; unsigned __int8
0x18006c6ee  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c6f3  movsxd  rax, dword ptr [rsi+30h]
0x18006c6f7  mov     r8d, [rbp+57h+dwBufferLength]; dwNumberOfBytesToRead
0x18006c6fb  lea     ecx, [rax+r8]
0x18006c6ff  cmp     ecx, ebx
0x18006c701  jnb     loc_18006C9A4
0x18006c707  mov     rdx, rax
0x18006c70a  add     rdx, [rsi+28h]; lpBuffer
0x18006c70e  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18006c712  mov     rcx, [rsi+10h]; hRequest
0x18006c716  call    cs:__imp_WinHttpReadData
0x18006c71c  test    eax, eax
0x18006c71e  jz      loc_18006C95B
0x18006c724  mov     eax, [rbp+57h+dwNumberOfBytesRead]
0x18006c727  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax
0x18006c72b  lea     r9, aWinhttpreaddat_0; "WinHttpReadData bytes read %d."
0x18006c732  mov     r8d, 3EFh; unsigned int
0x18006c738  mov     rdx, r13; char *
0x18006c73b  mov     ecx, edi; unsigned __int8
0x18006c73d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c742  mov     eax, [rbp+57h+dwNumberOfBytesRead]
0x18006c745  add     [rsi+30h], eax
0x18006c748  movsxd  rcx, dword ptr [rsi+30h]
0x18006c74c  mov     rax, [rsi+28h]
0x18006c750  mov     [rcx+rax], r12b
0x18006c754  cmp     [rbp+57h+dwNumberOfBytesRead], r12d
0x18006c758  jz      short loc_18006C7C1
0x18006c75a  mov     [rbp+57h+dwBufferLength], r12d
0x18006c75e  mov     [rbp+57h+dwNumberOfBytesRead], r12d
0x18006c762  lea     rdx, [rbp+57h+dwBufferLength]; lpdwNumberOfBytesAvailable
0x18006c766  mov     rcx, [rsi+10h]; hRequest
0x18006c76a  call    cs:__imp_WinHttpQueryDataAvailable
0x18006c770  test    eax, eax
0x18006c772  jnz     loc_18006C6D5
0x18006c778  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18006c77d  mov     r14d, eax
0x18006c780  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax
0x18006c784  lea     r9, aWinhttpqueryda_1; "WinHttpQueryDataAvailable failed 0x%x"
0x18006c78b  mov     r8d, 3D4h; unsigned int
0x18006c791  mov     rdx, r13; char *
0x18006c794  mov     ecx, r15d; unsigned __int8
0x18006c797  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c79c  mov     r8d, 3D5h
0x18006c7a2  mov     rdx, r13
0x18006c7a5  lea     rcx, [rbp+57h+pdwAuthTarget]
0x18006c7a9  call    ?FormatFileAndLine@WlidsvcUtil@@SA?AV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEBDI@Z; WlidsvcUtil::FormatFileAndLine(char const *,uint)
0x18006c7ae  nop
0x18006c7af  mov     rdx, rax
0x18006c7b2  lea     rcx, [rbp+57h+var_88]
0x18006c7b6  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x18006c7bb  nop
0x18006c7bc  jmp     loc_18006CA32
0x18006c7c1  mov     rcx, [rsi+38h]
0x18006c7c5  mov     rax, [rcx]
0x18006c7c8  mov     rax, [rax+40h]
0x18006c7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7d1  mov     ebx, eax
0x18006c7d3  test    cs:Microsoft_Windows_LiveIdEnableBits, 1
0x18006c7da  jz      short loc_18006C7F7
0x18006c7dc  mov     rcx, [rsi+38h]
0x18006c7e0  mov     rdx, [rcx]
0x18006c7e3  mov     rax, [rdx+38h]
0x18006c7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7ec  mov     r9d, eax
0x18006c7ef  mov     r8d, ebx
0x18006c7f2  call    McTemplateU0qq_EventWriteTransfer
0x18006c7f7  mov     ebx, [rsi+60h]
0x18006c7fa  call    cs:__imp_GetTickCount64
0x18006c800  sub     eax, ebx
0x18006c802  mov     [rsi+48h], eax
0x18006c805  mov     eax, [rsi+30h]
0x18006c808  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax; int
0x18006c80c  lea     r9, aReadTotalDChar; "Read total %d characters."
0x18006c813  mov     r8d, 3FEh; unsigned int
0x18006c819  mov     rdx, r13; char *
0x18006c81c  mov     ecx, edi; unsigned __int8
0x18006c81e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c823  mov     rax, [rsi+28h]
0x18006c827  test    rax, rax
0x18006c82a  jz      loc_18006C8F4
0x18006c830  cmp     [rax], r12b
0x18006c833  jz      loc_18006C8F4
0x18006c839  mov     [rbp+57h+arg_10], edi
0x18006c83c  mov     rcx, [rsi+38h]
0x18006c840  mov     edx, 80048820h; int
0x18006c845  mov     rcx, [rcx+18h]; this
0x18006c849  call    ?SetRequestStatus@CSingleIdentity@@QEAAXJ@Z; CSingleIdentity::SetRequestStatus(long)
0x18006c84e  mov     rcx, [rsi+38h]
0x18006c852  mov     rax, [rcx]
0x18006c855  lea     r9, [rbp+57h+arg_10]
0x18006c859  mov     r8d, [rsi+30h]
0x18006c85d  mov     rdx, [rsi+28h]
0x18006c861  mov     rax, [rax+28h]
0x18006c865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c86a  mov     r14d, eax
0x18006c86d  test    eax, eax
0x18006c86f  jns     short loc_18006C8DF
0x18006c871  mov     dword ptr [rsp+0D0h+lpdwBufferLength], eax; int
0x18006c875  lea     r9, aUnableToParseR; "Unable to parse response (0x%x)."
0x18006c87c  mov     r8d, 414h; unsigned int
0x18006c882  mov     rdx, r13; char *
0x18006c885  mov     ecx, r15d; unsigned __int8
0x18006c888  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006c88d  cmp     r14d, 80048103h
0x18006c894  jnz     short loc_18006C8BA
0x18006c896  mov     rdx, [rsi+10h]; void *
0x18006c89a  mov     rcx, rsi; this
0x18006c89d  call    ?LogResponseHeaders@CTransport@@AEAAJPEAX@Z; CTransport::LogResponseHeaders(void *)
0x18006c8a2  mov     rcx, [rbp+5Fh]; this
0x18006c8a6  test    eax, eax
0x18006c8a8  jns     short loc_18006C8BA
0x18006c8aa  mov     r9d, eax; char *
0x18006c8ad  mov     r8, r13; unsigned int
0x18006c8b0  mov     edx, 418h; void *
0x18006c8b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c8ba  mov     r8d, 41Bh
0x18006c8c0  mov     rdx, r13
  ... truncated ...
```
