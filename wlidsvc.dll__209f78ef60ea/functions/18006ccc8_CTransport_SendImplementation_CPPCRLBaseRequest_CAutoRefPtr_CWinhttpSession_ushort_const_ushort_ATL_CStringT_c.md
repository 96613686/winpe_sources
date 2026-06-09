# CTransport::SendImplementation(CPPCRLBaseRequest *,CAutoRefPtr<CWinhttpSession> &,ushort const *,ushort,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CONFIGDATA &,bool,long &)

- ea: `0x18006ccc8`
- end: `0x18006d7b9`
- name: `?SendImplementation@CTransport@@AEAAJPEAVCPPCRLBaseRequest@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@PEBGGAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@5@AEAUCONFIGDATA@@_NAEAJ@Z`
- size: `2801`
- prototype: `__int64 __usercall@<rax>(unsigned __int64@<rcx>, __int16, __int64, __int64, struct CONFIGDATA *, char, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ee3d0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180013448`
- `0x180013510`
- `0x18001426c`
- `0x1800143a4`
- `0x1800151c4`
- `0x180015430`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001f968`
- `0x180021c10`
- `0x180029d54`
- `0x18002dfcc`
- `0x180031800`
- `0x1800320a8`
- `0x180033218`
- `0x180036f60`
- `0x18003ad50`
- `0x180042174`
- `0x180043344`
- `0x1800453c0`
- `0x18004a3c8`
- `0x18004e018`
- `0x18005538c`
- `0x18006ccc8`
- `0x180076a0c`
- `0x180079554`
- `0x18007bd04`
- `0x180084d44`
- `0x1800888e8`
- `0x18008b65c`
- `0x1800977c0`
- `0x1800a3b60`
- `0x1800a4778`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d4e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d5b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d60c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d4e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d5b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d60c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d622`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006cf89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006cf89`
- `WINHTTP!WinHttpOpenRequest` at `0x18006d197`
- `WINHTTP!WinHttpOpenRequest` at `0x18006d197`
- `WINHTTP!WinHttpConnect` at `0x18006d048`
- `WINHTTP!WinHttpConnect` at `0x18006d048`
- `WINHTTP!WinHttpSetOption` at `0x18006d0f0`
- `WINHTTP!WinHttpSetOption` at `0x18006d2c2`
- `WINHTTP!WinHttpSetOption` at `0x18006d3c4`
- `WINHTTP!WinHttpSetOption` at `0x18006d43f`
- `WINHTTP!WinHttpSetOption` at `0x18006d4d7`
- `WINHTTP!WinHttpSetOption` at `0x18006d5a9`
- `WINHTTP!WinHttpSetOption` at `0x18006d602`
- `WINHTTP!WinHttpSetOption` at `0x18006d0f0`
- `WINHTTP!WinHttpSetOption` at `0x18006d2c2`
- `WINHTTP!WinHttpSetOption` at `0x18006d3c4`
- `WINHTTP!WinHttpSetOption` at `0x18006d43f`
- `WINHTTP!WinHttpSetOption` at `0x18006d4d7`
- `WINHTTP!WinHttpSetOption` at `0x18006d5a9`
- `WINHTTP!WinHttpSetOption` at `0x18006d602`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18006d1e3`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18006d1e3`

## string_xrefs

- `0x18006cda0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006cde6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006ce93`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006d025`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006d2f9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006d567`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006d5e1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006d642`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006d6a0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18006ce7e`: `Acquiring caller nt token failed 0x%x.`
- `0x18006cf98`: `Aquiring caller nt token failed 0x%x.`
- `0x18006ced4`: `WinHttpOpen failed 0x%x.`
- `0x18006cf53`: `WinHttpOpen failed 0x%x.`
- `0x18006cfde`: `WinHttpOpen failed 0x%x.`
- `0x18006d1b5`: `WinHttpOpenRequest failed 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CTransport::SendImplementation(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        __int16 a5,
        __int64 a6,
        void *a7,
        LPCCH *a8,
        char a9,
        int *a10)
{
  void *v14; // r8
  bool v15; // r9
  void *v16; // r8
  bool v17; // r9
  signed int Error; // eax
  unsigned int v19; // r8d
  const unsigned __int16 *v20; // r9
  unsigned int v21; // r8d
  const char *v22; // rax
  void *v23; // r14
  __int64 v24; // rcx
  int v25; // r8d
  int v26; // eax
  void *v27; // rax
  CTransport *v28; // rcx
  signed int LastError; // eax
  CHAR *v30; // r8
  int v31; // r9d
  HCRYPTKEY *v32; // rax
  int v33; // eax
  signed int v34; // eax
  signed int v35; // eax
  signed int v36; // eax
  int v37; // eax
  _BYTE *v38; // rax
  unsigned int v39; // r9d
  unsigned int v40; // ebx
  const unsigned __int16 *ReturnLength; // [rsp+20h] [rbp-E0h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  struct _LUID v46; // [rsp+50h] [rbp-B0h] BYREF
  void **v47; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TokenHandle[2]; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+70h] [rbp-90h]
  unsigned int TokenInformation; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  INTERNET_PORT v52; // [rsp+88h] [rbp-78h]
  LPVOID v53[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h]
  __int64 v55; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID lpBuffer; // [rsp+B0h] [rbp-50h] BYREF
  void *v57; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v58[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v59[16]; // [rsp+E0h] [rbp-20h] BYREF
  int Buffer; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v61[208]; // [rsp+F4h] [rbp-Ch] BYREF
  int v62; // [rsp+1C4h] [rbp+C4h]
  __int128 v63; // [rsp+1C8h] [rbp+C8h]

  v52 = a5;
  v53[0] = a7;
  v44 = 0;
  *a10 = 0;
  Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation::ScopedRequestTelemetryOperation(
    (Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation *)v59,
    L"ns");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpBuffer);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v55,
    L"https://");
  v58[0] = "CTransport::SendImplementation";
  v58[1] = &v44;
  v58[2] = 0;
  v58[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
    "CTransport::SendImplementation",
    (const char *)0x19A,
    0,
    ReturnLength);
  CTransport::CloseAllInternet((CTransport *)a1, 0);
  ATL::CSimpleStringT<unsigned short,0>::Append(&v55, a4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&v55, v53[0]);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
    0x1A3u,
    L"##TestHook: URL-%s",
    v55);
  v47 = &ATL::CAccessToken::`vftable';
  *(_OWORD *)TokenHandle = 0;
  v49 = 0;
  v45 = 0;
  if ( !ATL::CAccessToken::GetThreadToken((ATL::CAccessToken *)&v47, 8u, v14, v15) && GetLastError() == 1008 )
    CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v45, 0);
  if ( ATL::CAccessToken::GetThreadToken((ATL::CAccessToken *)&v47, 8u, v16, v17) )
  {
    v46 = 0;
    TokenInformation = 0;
    if ( !ATL::CAccessToken::GetLogonSessionId((ATL::CAccessToken *)&v47, &v46) )
    {
      Error = ATL::AtlHresultFromLastError();
      v19 = 469;
LABEL_9:
      v20 = L"Acquiring caller nt token failed 0x%x.";
LABEL_10:
      v44 = Error;
LABEL_11:
      *a10 = -2147188665;
LABEL_12:
      LODWORD(ReturnLengtha) = Error;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        v19,
        v20,
        ReturnLengtha);
      goto LABEL_101;
    }
    if ( v46.LowPart != 999 || v46.HighPart )
    {
      LODWORD(v51) = 0;
      if ( !GetTokenInformation(TokenHandle[0], TokenSessionId, &TokenInformation, 4u, (PDWORD)&v51) )
      {
        Error = ATL::AtlHresultFromLastError();
        v20 = L"Aquiring caller nt token failed 0x%x.";
        v19 = 491;
        goto LABEL_10;
      }
      Error = CWinhttpSessions::GetWinhttpSession(
                (LPCRITICAL_SECTION)((char *)g_pPPCRL + 1048),
                (struct CONFIGDATA *)a8,
                a3);
      v44 = Error;
      if ( Error < 0 )
      {
        v20 = L"WinHttpOpen failed 0x%x.";
        v19 = 499;
        goto LABEL_11;
      }
    }
    else
    {
      Error = CWinhttpSessions::GetWinhttpSystemSession((LPCRITICAL_SECTION)((char *)g_pPPCRL + 1048));
      v44 = Error;
      if ( Error < 0 )
      {
        v20 = L"WinHttpOpen failed 0x%x.";
        v19 = 480;
        goto LABEL_11;
      }
    }
  }
  else
  {
    if ( GetLastError() != 1008 )
    {
      Error = GetLastError();
      if ( Error > 0 )
        Error = (unsigned __int16)Error | 0x80070000;
      v19 = 444;
      goto LABEL_9;
    }
    Error = CWinhttpSessions::GetWinhttpSystemSession((LPCRITICAL_SECTION)((char *)g_pPPCRL + 1048));
    v44 = Error;
    if ( Error < 0 )
    {
      v20 = L"WinHttpOpen failed 0x%x.";
      v19 = 453;
      goto LABEL_11;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL) + 624LL) )
  {
    v21 = 506;
LABEL_27:
    v22 = "!m_pRequest->m_pIdentity->IsRequestCancelled()";
LABEL_28:
    v44 = -2147186622;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      "CTransport::SendImplementation",
      v21,
      -2147186622,
      v22);
    goto LABEL_101;
  }
  v23 = WinHttpConnect(*(HINTERNET *)(*(_QWORD *)a3 + 16LL), a4, v52, 0);
  *(_QWORD *)(a1 + 8) = v23;
  if ( !v23 )
  {
    Error = ATL::AtlHresultFromLastError();
    v44 = Error;
    *a10 = -2147188664;
    v20 = L"WinHttpConnect failed 0x%x.";
    v19 = 518;
    goto LABEL_12;
  }
  v24 = *(_QWORD *)(a1 + 56);
  if ( *(_BYTE *)(*(_QWORD *)(v24 + 24) + 624LL) )
  {
    v21 = 525;
    goto LABEL_27;
  }
  if ( (*(_QWORD *)(v24 + 56) & 0x100000000LL) != 0 )
  {
    memset_0(v61, 0, sizeof(v61));
    Buffer = 65538;
    v62 = 1;
    v63 = WWAN_PROFILE_SET_GUID_ESIM_PROVISIONING_OD;
    WinHttpSetOption(v23, 0x83u, &Buffer, 0xE8u);
    if ( (unsigned int)dword_1801C2080 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
      {
        if ( v25 )
          v26 = 0;
        else
          v26 = ATL::AtlHresultFromLastError();
        LODWORD(v51) = v26;
        v46 = (struct _LUID)50331648LL;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          (__int64)&dword_1801C2080,
          (unsigned __int8 *)byte_18019B1B3,
          0,
          0,
          (__int64)&v46,
          (__int64)&v51);
      }
    }
  }
  v27 = WinHttpOpenRequest(
          *(HINTERNET *)(a1 + 8),
          L"POST",
          *(LPCWSTR *)v53[0],
          L"HTTP/1.0",
          0,
          &ppwszAcceptTypes,
          0x800000u);
  *(_QWORD *)(a1 + 16) = v27;
  if ( !v27 )
  {
    Error = ATL::AtlHresultFromLastError();
    v44 = Error;
    *a10 = -2147188663;
    v20 = L"WinHttpOpenRequest failed 0x%x";
    v19 = 564;
    goto LABEL_12;
  }
  if ( a9 == 1
    && WinHttpSetStatusCallback(v27, CTransport::WinHttpStatusCallback, 0x10000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    Error = GetLastError();
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    v44 = Error;
    *a10 = -2147188663;
    v20 = L"WinHttpSetStatusCallback failed 0x%x";
    v19 = 579;
    goto LABEL_12;
  }
  DeviceIdHelpers::IsCallerAccountType(0x12u, (int *)(a1 + 88));
  if ( *((_DWORD *)a8 + 48) == 3 && *((_DWORD *)a8[22] - 4) )
  {
    *(_OWORD *)v53 = 0;
    v54 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
    LODWORD(v53[0]) = *((_DWORD *)a8 + 48);
    WlidsvcUtil::ConvertA2W(a8[22]);
    WlidsvcUtil::ConvertA2W(a8[23]);
    v53[1] = (LPVOID)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v51);
    v54 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v46);
    if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 16), 0x26u, v53, 0x18u) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v44 = LastError;
      *a10 = -2147188656;
      LODWORD(ReturnLengtha) = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x265u,
        L"Failed to set user proxy settings, hr=0x%x..",
        ReturnLengtha);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
      goto LABEL_101;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  }
  if ( a9 == 1 )
  {
    LODWORD(v51) = 1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v46,
      L"BypassCertRevocationCheck");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)v53,
      L"Software\\Microsoft\\IdentityCRL");
    TokenInformation = 0;
    Reg_QueryDWORD(-2147483646, v53, &v46, &TokenInformation);
    CTransport::dwDisableCertRevocationCheck = TokenInformation;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v53);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
    if ( !CTransport::dwDisableCertRevocationCheck && !WinHttpSetOption(*(HINTERNET *)(a1 + 16), 0x4Fu, &v51, 4u) )
    {
      Error = GetLastError();
      if ( Error > 0 )
        Error = (unsigned __int16)Error | 0x80070000;
      v44 = Error;
      *a10 = -2147188656;
      v20 = L"Failed to enable revocation checking for winhttp, hr=0x%x.";
      v19 = 630;
      goto LABEL_12;
    }
  }
  Error = CTransport::AddCustomHTTPHeaders(v28, *(void **)(a1 + 16));
  v44 = Error;
  if ( Error < 0 )
  {
    v20 = L"AddCustomHTTPHeaders failed 0x%x.";
    v19 = 640;
    goto LABEL_12;
  }
  v30 = (CHAR *)a8[25];
  v31 = *((_DWORD *)v30 - 4);
  if ( v31 > 0 )
  {
    if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 16), 0x1002u, v30, v31 + 1) )
    {
      Error = GetLastError();
      if ( Error > 0 )
        Error = (unsigned __int16)Error | 0x80070000;
      v44 = Error;
      *a10 = -2147188656;
      v20 = L"Unable to set WINHTTP_OPTION_PROXY_USERNAME - WinHttpSetOption failed (0x%x).";
      v19 = 659;
      goto LABEL_12;
    }
    if ( *((int *)a8[26] - 4) > 0 )
    {
      v32 = (HCRYPTKEY *)(**(__int64 (__fastcall ***)(CPassportClientLibrary *))g_pPPCRL)(g_pPPCRL);
      Error = InMemoryDecrypt<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,unsigned short const *,unsigned short>(*v32);
      v44 = Error;
      if ( Error < 0 )
      {
        v20 = L"Could not decrypt proxy password. HR=(0x%x).";
        v19 = 670;
        goto LABEL_12;
      }
    }
    if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 16), 0x1003u, lpBuffer, *((_DWORD *)lpBuffer - 4) + 1) )
    {
      Error = GetLastError();
      if ( Error > 0 )
        Error = (unsigned __int16)Error | 0x80070000;
      v44 = Error;
      *a10 = -2147188656;
      v20 = L"Unable to set INTERNET_OPTION_PROXY_PASSWORD - InternetSetOption failed (0x%x).";
      v19 = 684;
      goto LABEL_12;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL) + 624LL) )
  {
    v21 = 690;
    goto LABEL_27;
  }
  v53[1] = 0;
  v53[0] = &SmartPCCERT_CONTEXT::`vftable';
  v33 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a2 + 104LL))(a2, v53);
  v44 = v33;
  if ( v33 < 0 )
  {
    LODWORD(ReturnLengtha) = v33;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x2BAu,
      L"GetClientCert failed with 0x%x.",
      ReturnLengtha);
    *a10 = v44;
LABEL_78:
    SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v53);
    goto LABEL_101;
  }
  if ( v33 || !v53[1] )
  {
    if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 16), 0x2Fu, 0, 0) )
    {
      v35 = GetLastError();
      if ( v35 > 0 )
        v35 = (unsigned __int16)v35 | 0x80070000;
      if ( v35 != -2147024809 )
        goto LABEL_82;
      v36 = GetLastError();
      if ( v36 > 0 )
        v36 = (unsigned __int16)v36 | 0x80070000;
      LODWORD(ReturnLengtha) = v36;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
        0x2CCu,
        L"Ignoring E_INVALIDARG error when resetting INTERNET_OPTION_CLIENT_CERT_CONTEXT - InternetSetOption failed (0x%x).",
        ReturnLengtha);
    }
  }
  else if ( !WinHttpSetOption(*(HINTERNET *)(a1 + 16), 0x2Fu, v53[1], 0x28u) )
  {
LABEL_82:
    v34 = GetLastError();
    if ( v34 > 0 )
      v34 = (unsigned __int16)v34 | 0x80070000;
    v44 = v34;
    *a10 = -2147188656;
    LODWORD(ReturnLengtha) = v34;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x2D5u,
      L"Unable to set INTERNET_OPTION_CLIENT_CERT_CONTEXT - InternetSetOption failed (0x%x).",
      ReturnLengtha);
    goto LABEL_78;
  }
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v53);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0);
  *(_DWORD *)(a1 + 24) = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 32LL))(a2, &v57);
  v44 = v37;
  if ( v37 < 0 )
  {
    LODWORD(ReturnLengtha) = v37;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      0x2E0u,
      L"DecryptRequest failed with 0x%x.",
      ReturnLengtha);
    *a10 = -2147188222;
    goto LABEL_101;
  }
  *(_DWORD *)(a1 + 48) = 0;
  v38 = *(_BYTE **)(a1 + 40);
  if ( v38 )
    *v38 = 0;
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 24LL) + 624LL) )
  {
    v22 = "m_pRequest->m_pIdentity->IsRequestCancelled() == false";
    v21 = 746;
    goto LABEL_28;
  }
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)&Buffer);
  v44 = CWinhttpSessions::SendRequestAndReceiveResponse(
          (struct IServiceExecutionContext *)&Buffer,
          *(void **)(a1 + 16),
          &qword_18013DE20,
          v39,
          v57,
          *((_DWORD *)v57 - 4),
          *((_DWORD *)v57 - 4),
          a1);
  if ( v44 < 0 )
    *a10 = -2147188655;
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)&Buffer);
LABEL_101:
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v45);
  v47 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v47);
  v40 = v44;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpBuffer);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v57);
  Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation::~ScopedRequestTelemetryOperation((Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation *)v59);
  return v40;
}

```

## disassembly

```asm
0x18006ccc8  push    rbp
0x18006ccca  push    rbx
0x18006cccb  push    rsi
0x18006cccc  push    rdi
0x18006cccd  push    r12
0x18006cccf  push    r13
0x18006ccd1  push    r14
0x18006ccd3  push    r15
0x18006ccd5  lea     rbp, [rsp-0F8h]
0x18006ccdd  sub     rsp, 1F8h
0x18006cce4  mov     rax, cs:__security_cookie
0x18006cceb  xor     rax, rsp
0x18006ccee  mov     [rbp+130h+var_50], rax
0x18006ccf5  mov     r13, r9
0x18006ccf8  mov     r14, r8
0x18006ccfb  mov     r12, rdx
0x18006ccfe  mov     rdi, rcx
0x18006cd01  movzx   eax, [rbp+130h+arg_20]
0x18006cd08  mov     [rbp+130h+var_1A8], ax
0x18006cd0c  mov     r15, [rbp+130h+arg_28]
0x18006cd13  mov     rax, [rbp+130h+arg_30]
0x18006cd1a  mov     [rbp+130h+var_1A0], rax
0x18006cd1e  mov     rbx, [rbp+130h+arg_38]
0x18006cd25  mov     rsi, [rbp+130h+arg_48]
0x18006cd2c  mov     [rsp+230h+var_1F0], 0
0x18006cd34  mov     dword ptr [rsi], 0
0x18006cd3a  lea     rdx, aNs; "ns"
0x18006cd41  lea     rcx, [rbp+130h+var_150]; this
0x18006cd45  call    ??0ScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAA@PEBG@Z; Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation::ScopedRequestTelemetryOperation(ushort const *)
0x18006cd4a  nop
0x18006cd4b  lea     rcx, [rbp+130h+var_178]
0x18006cd4f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006cd54  nop
0x18006cd55  lea     rcx, [rbp+130h+lpBuffer]
0x18006cd59  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006cd5e  nop
0x18006cd5f  lea     rdx, aHttps; "https://"
0x18006cd66  lea     rcx, [rbp+130h+var_188]
0x18006cd6a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006cd6f  nop
0x18006cd70  lea     rcx, aCtransportSend_0; "CTransport::SendImplementation"
0x18006cd77  mov     [rbp+130h+var_170], rcx
0x18006cd7b  lea     rax, [rsp+230h+var_1F0]
0x18006cd80  mov     [rbp+130h+var_168], rax
0x18006cd84  mov     [rbp+130h+var_160], 0
0x18006cd8c  mov     [rbp+130h+var_158], 0
0x18006cd94  xor     r9d, r9d; unsigned int
0x18006cd97  mov     r8d, 19Ah; char *
0x18006cd9d  mov     rdx, rcx; char *
0x18006cda0  lea     rcx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006cda7  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18006cdac  nop
0x18006cdad  xor     edx, edx; bool
0x18006cdaf  mov     rcx, rdi; this
0x18006cdb2  call    ?CloseAllInternet@CTransport@@AEAAJ_N@Z; CTransport::CloseAllInternet(bool)
0x18006cdb7  mov     rdx, r13
0x18006cdba  lea     rcx, [rbp+130h+var_188]
0x18006cdbe  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18006cdc3  mov     rdx, [rbp+130h+var_1A0]
0x18006cdc7  lea     rcx, [rbp+130h+var_188]
0x18006cdcb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x18006cdd0  mov     rax, [rbp+130h+var_188]
0x18006cdd4  mov     [rsp+230h+ReturnLength], rax
0x18006cdd9  lea     r9, aTesthookUrlS; "##TestHook: URL-%s"
0x18006cde0  mov     r8d, 1A3h; unsigned int
0x18006cde6  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006cded  mov     ecx, 5; unsigned __int8
0x18006cdf2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006cdf7  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18006cdfe  mov     [rsp+230h+var_1D8], rax
0x18006ce03  xorps   xmm0, xmm0
0x18006ce06  movdqu  xmmword ptr [rsp+230h+TokenHandle], xmm0
0x18006ce0c  xor     eax, eax
0x18006ce0e  mov     [rsp+230h+var_1C0], rax
0x18006ce13  mov     [rsp+230h+var_1E8], rax
0x18006ce18  lea     edx, [rax+8]; unsigned int
0x18006ce1b  lea     rcx, [rsp+230h+var_1D8]; this
0x18006ce20  call    ?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z; ATL::CAccessToken::GetThreadToken(ulong,void *,bool)
0x18006ce25  test    al, al
0x18006ce27  jnz     short loc_18006CE42
0x18006ce29  call    cs:__imp_GetLastError
0x18006ce2f  cmp     eax, 3F0h
0x18006ce34  jnz     short loc_18006CE42
0x18006ce36  xor     edx, edx; struct ATL::CAccessToken *
0x18006ce38  lea     rcx, [rsp+230h+var_1E8]; this
0x18006ce3d  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18006ce42  mov     edx, 8; unsigned int
0x18006ce47  lea     rcx, [rsp+230h+var_1D8]; this
0x18006ce4c  call    ?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z; ATL::CAccessToken::GetThreadToken(ulong,void *,bool)
0x18006ce51  test    al, al
0x18006ce53  jnz     loc_18006CEE3
0x18006ce59  call    cs:__imp_GetLastError
0x18006ce5f  cmp     eax, 3F0h
0x18006ce64  jz      short loc_18006CEA9
0x18006ce66  call    cs:__imp_GetLastError
0x18006ce6c  test    eax, eax
0x18006ce6e  jle     short loc_18006CE78
0x18006ce70  movzx   eax, ax
0x18006ce73  or      eax, 80070000h
0x18006ce78  mov     r8d, 1BCh; unsigned int
0x18006ce7e  lea     r9, aAcquiringCalle; "Acquiring caller nt token failed 0x%x."
0x18006ce85  mov     [rsp+230h+var_1F0], eax
0x18006ce89  mov     dword ptr [rsi], 80048047h
0x18006ce8f  mov     dword ptr [rsp+230h+ReturnLength], eax
0x18006ce93  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006ce9a  mov     ecx, 2; unsigned __int8
0x18006ce9f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006cea4  jmp     loc_18006D73E
0x18006cea9  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18006ceb0  add     rcx, 418h; lpCriticalSection
0x18006ceb7  mov     r9, r14
0x18006ceba  mov     r8, rbx
0x18006cebd  mov     rdx, r15
0x18006cec0  call    ?GetWinhttpSystemSession@CWinhttpSessions@@QEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAUCONFIGDATA@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z; CWinhttpSessions::GetWinhttpSystemSession(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CONFIGDATA &,CAutoRefPtr<CWinhttpSession> &)
0x18006cec5  mov     [rsp+230h+var_1F0], eax
0x18006cec9  xor     r15d, r15d
0x18006cecc  test    eax, eax
0x18006cece  jns     loc_18006CFF0
0x18006ced4  lea     r9, aWinhttpopenFai; "WinHttpOpen failed 0x%x."
0x18006cedb  mov     r8d, 1C5h
0x18006cee1  jmp     short loc_18006CE89
0x18006cee3  mov     qword ptr [rsp+230h+var_1E0.LowPart], 0
0x18006ceec  mov     [rsp+230h+TokenInformation], 0
0x18006cef4  lea     rdx, [rsp+230h+var_1E0]; struct _LUID *
0x18006cef9  lea     rcx, [rsp+230h+var_1D8]; this
0x18006cefe  call    ?GetLogonSessionId@CAccessToken@ATL@@QEBA_NPEAU_LUID@@@Z; ATL::CAccessToken::GetLogonSessionId(_LUID *)
0x18006cf03  test    al, al
0x18006cf05  jnz     short loc_18006CF17
0x18006cf07  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18006cf0c  mov     r8d, 1D5h
0x18006cf12  jmp     loc_18006CE7E
0x18006cf17  cmp     [rsp+230h+var_1E0.LowPart], 3E7h
0x18006cf1f  jnz     short loc_18006CF65
0x18006cf21  cmp     [rsp+230h+var_1E0.HighPart], 0
0x18006cf26  jnz     short loc_18006CF65
0x18006cf28  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18006cf2f  add     rcx, 418h; lpCriticalSection
0x18006cf36  mov     r9, r14
0x18006cf39  mov     r8, rbx
0x18006cf3c  mov     rdx, r15
0x18006cf3f  call    ?GetWinhttpSystemSession@CWinhttpSessions@@QEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAUCONFIGDATA@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z; CWinhttpSessions::GetWinhttpSystemSession(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CONFIGDATA &,CAutoRefPtr<CWinhttpSession> &)
0x18006cf44  mov     [rsp+230h+var_1F0], eax
0x18006cf48  xor     r15d, r15d
0x18006cf4b  test    eax, eax
0x18006cf4d  jns     loc_18006CFF0
0x18006cf53  lea     r9, aWinhttpopenFai; "WinHttpOpen failed 0x%x."
0x18006cf5a  mov     r8d, 1E0h
0x18006cf60  jmp     loc_18006CE89
0x18006cf65  mov     dword ptr [rbp+130h+var_1B0], 0
0x18006cf6c  lea     rax, [rbp+130h+var_1B0]
0x18006cf70  mov     [rsp+230h+ReturnLength], rax; ReturnLength
0x18006cf75  mov     r9d, 4; TokenInformationLength
0x18006cf7b  lea     r8, [rsp+230h+TokenInformation]; TokenInformation
0x18006cf80  lea     edx, [r9+8]; TokenInformationClass
0x18006cf84  mov     rcx, [rsp+230h+TokenHandle]; TokenHandle
0x18006cf89  call    cs:__imp_GetTokenInformation
0x18006cf8f  test    eax, eax
0x18006cf91  jnz     short loc_18006CFAA
0x18006cf93  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18006cf98  lea     r9, aAquiringCaller; "Aquiring caller nt token failed 0x%x."
0x18006cf9f  mov     r8d, 1EBh
0x18006cfa5  jmp     loc_18006CE85
0x18006cfaa  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18006cfb1  add     rcx, 418h; lpCriticalSection
0x18006cfb8  mov     [rsp+230h+ppwszAcceptTypes], r14; __int64
0x18006cfbd  mov     [rsp+230h+ReturnLength], rbx; struct CONFIGDATA *
0x18006cfc2  mov     r9, r15
0x18006cfc5  lea     r8, [rsp+230h+var_1E0]
0x18006cfca  mov     edx, [rsp+230h+TokenInformation]
0x18006cfce  call    ?GetWinhttpSession@CWinhttpSessions@@QEAAJKAEAU_LUID@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAUCONFIGDATA@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z; CWinhttpSessions::GetWinhttpSession(ulong,_LUID &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CONFIGDATA &,CAutoRefPtr<CWinhttpSession> &)
0x18006cfd3  mov     [rsp+230h+var_1F0], eax
0x18006cfd7  xor     r15d, r15d
0x18006cfda  test    eax, eax
0x18006cfdc  jns     short loc_18006CFF0
0x18006cfde  lea     r9, aWinhttpopenFai; "WinHttpOpen failed 0x%x."
0x18006cfe5  mov     r8d, 1F3h
0x18006cfeb  jmp     loc_18006CE89
0x18006cff0  mov     rax, [rdi+38h]
0x18006cff4  mov     rcx, [rax+18h]
0x18006cff8  cmp     [rcx+270h], r15b
0x18006cfff  jz      short loc_18006D036
0x18006d001  mov     r8d, 1FAh; unsigned int
0x18006d007  lea     rax, aMPrequestMPide_0; "!m_pRequest->m_pIdentity->IsRequestCanc"...
0x18006d00e  mov     r9d, 80048842h; int
0x18006d014  mov     [rsp+230h+ReturnLength], rax; char *
0x18006d019  mov     [rsp+230h+var_1F0], r9d
0x18006d01e  lea     rdx, aCtransportSend_0; "CTransport::SendImplementation"
0x18006d025  lea     rcx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006d02c  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006d031  jmp     loc_18006D73E
0x18006d036  mov     rcx, [r14]
0x18006d039  xor     r9d, r9d; dwReserved
0x18006d03c  movzx   r8d, [rbp+130h+var_1A8]; nServerPort
0x18006d041  mov     rdx, r13; pswzServerName
0x18006d044  mov     rcx, [rcx+10h]; hSession
0x18006d048  call    cs:__imp_WinHttpConnect
0x18006d04e  mov     r14, rax
0x18006d051  mov     [rdi+8], rax
0x18006d055  test    rax, rax
0x18006d058  jnz     short loc_18006D07B
0x18006d05a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18006d05f  mov     [rsp+230h+var_1F0], eax
0x18006d063  mov     dword ptr [rsi], 80048048h
0x18006d069  lea     r9, aWinhttpconnect_0; "WinHttpConnect failed 0x%x."
0x18006d070  mov     r8d, 206h
0x18006d076  jmp     loc_18006CE8F
0x18006d07b  mov     rcx, [rdi+38h]
0x18006d07f  mov     rax, [rcx+18h]
0x18006d083  cmp     [rax+270h], r15b
0x18006d08a  jz      short loc_18006D097
0x18006d08c  mov     r8d, 20Dh
0x18006d092  jmp     loc_18006D007
0x18006d097  mov     rax, 100000000h
0x18006d0a1  mov     r13d, 1
0x18006d0a7  test    [rcx+38h], rax
0x18006d0ab  jz      loc_18006D165
0x18006d0b1  xor     edx, edx; Val
0x18006d0b3  mov     r8d, 0D0h; Size
0x18006d0b9  lea     rcx, [rbp+130h+var_13C]; void *
0x18006d0bd  call    memset_0
0x18006d0c2  mov     [rbp+130h+Buffer], 10002h
0x18006d0c9  mov     [rbp+130h+var_6C], r13d
0x18006d0d0  movups  xmm0, cs:WWAN_PROFILE_SET_GUID_ESIM_PROVISIONING_OD
0x18006d0d7  movdqu  [rbp+130h+var_68], xmm0
0x18006d0df  mov     r9d, 0E8h; dwBufferLength
0x18006d0e5  lea     r8, [rbp+130h+Buffer]; lpBuffer
0x18006d0e9  lea     edx, [r9-65h]; dwOption
0x18006d0ed  mov     rcx, r14; hInternet
0x18006d0f0  call    cs:__imp_WinHttpSetOption
0x18006d0f6  mov     r8d, eax
0x18006d0f9  mov     ecx, cs:dword_1801C2080
0x18006d0ff  cmp     ecx, 5
0x18006d102  jbe     short loc_18006D165
0x18006d104  mov     rdx, 400000000000h
0x18006d10e  lea     rcx, dword_1801C2080
0x18006d115  call    _tlgKeywordOn
0x18006d11a  test    al, al
0x18006d11c  jz      short loc_18006D165
0x18006d11e  test    r8d, r8d
0x18006d121  jz      short loc_18006D128
0x18006d123  mov     eax, r15d
0x18006d126  jmp     short loc_18006D12D
0x18006d128  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18006d12d  mov     dword ptr [rbp+130h+var_1B0], eax
0x18006d130  mov     qword ptr [rsp+230h+var_1E0.LowPart], 3000000h
0x18006d139  lea     rax, [rbp+130h+var_1B0]
0x18006d13d  mov     [rsp+230h+ppwszAcceptTypes], rax
0x18006d142  lea     rax, [rsp+230h+var_1E0]
0x18006d147  mov     [rsp+230h+ReturnLength], rax
0x18006d14c  xor     r9d, r9d
0x18006d14f  xor     r8d, r8d
0x18006d152  lea     rdx, byte_18019B1B3
0x18006d159  lea     rcx, dword_1801C2080
0x18006d160  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18006d165  mov     [rsp+230h+dwFlags], 800000h; dwFlags
0x18006d16d  lea     rax, ppwszAcceptTypes
0x18006d174  mov     [rsp+230h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18006d179  mov     [rsp+230h+ReturnLength], r15; pwszReferrer
0x18006d17e  lea     r9, pwszVersion; "HTTP/1.0"
0x18006d185  mov     rax, [rbp+130h+var_1A0]
0x18006d189  mov     r8, [rax]; pwszObjectName
0x18006d18c  lea     rdx, pwszVerb; "POST"
0x18006d193  mov     rcx, [rdi+8]; hConnect
0x18006d197  call    cs:__imp_WinHttpOpenRequest
0x18006d19d  mov     [rdi+10h], rax
0x18006d1a1  test    rax, rax
0x18006d1a4  jnz     short loc_18006D1C7
0x18006d1a6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18006d1ab  mov     [rsp+230h+var_1F0], eax
0x18006d1af  mov     dword ptr [rsi], 80048049h
0x18006d1b5  lea     r9, aWinhttpopenreq_0; "WinHttpOpenRequest failed 0x%x"
0x18006d1bc  mov     r8d, 234h
0x18006d1c2  jmp     loc_18006CE8F
0x18006d1c7  cmp     [rbp+130h+arg_40], r13b
0x18006d1ce  jnz     short loc_18006D21D
0x18006d1d0  xor     r9d, r9d; dwReserved
0x18006d1d3  mov     r8d, 10000h; dwNotificationFlags
0x18006d1d9  lea     rdx, ?WinHttpStatusCallback@CTransport@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18006d1e0  mov     rcx, rax; hInternet
0x18006d1e3  call    cs:__imp_WinHttpSetStatusCallback
0x18006d1e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006d1ed  jnz     short loc_18006D21D
0x18006d1ef  call    cs:__imp_GetLastError
0x18006d1f5  test    eax, eax
0x18006d1f7  jle     short loc_18006D201
0x18006d1f9  movzx   eax, ax
0x18006d1fc  or      eax, 80070000h
0x18006d201  mov     [rsp+230h+var_1F0], eax
0x18006d205  mov     dword ptr [rsi], 80048049h
0x18006d20b  lea     r9, aWinhttpsetstat_0; "WinHttpSetStatusCallback failed 0x%x"
0x18006d212  mov     r8d, 243h
0x18006d218  jmp     loc_18006CE8F
0x18006d21d  lea     rdx, [rdi+58h]; int *
0x18006d221  mov     ecx, 12h; unsigned int
0x18006d226  call    ?IsCallerAccountType@DeviceIdHelpers@@SAJJAEAH@Z; DeviceIdHelpers::IsCallerAccountType(long,int &)
0x18006d22b  cmp     dword ptr [rbx+0C0h], 3
0x18006d232  jnz     loc_18006D338
0x18006d238  mov     rax, [rbx+0B0h]
0x18006d23f  cmp     [rax-10h], r15d
0x18006d243  jz      loc_18006D338
  ... truncated ...
```
