# HTTPRequest::RequestUrlHelper(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)

- ea: `0x1800c73a4`
- end: `0x1800c7893`
- name: `?RequestUrlHelper@HTTPRequest@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@1AEAK@Z`
- size: `1263`
- prototype: `__int64 __fastcall(int, int, int, int, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7308`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180013510`
- `0x180014490`
- `0x1800151c4`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x180029d54`
- `0x180079554`
- `0x180084d44`
- `0x1800a3b60`
- `0x1800a4778`
- `0x1800c73a4`
- `0x180116bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c74b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c75cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c761c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c774c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c74b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c75cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c761c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c774c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7804`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800c783b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800c783b`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800c7742`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800c77fa`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800c7742`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800c77fa`
- `WINHTTP!WinHttpOpenRequest` at `0x1800c75be`
- `WINHTTP!WinHttpOpenRequest` at `0x1800c75be`
- `WINHTTP!WinHttpConnect` at `0x1800c7556`
- `WINHTTP!WinHttpConnect` at `0x1800c7556`
- `WINHTTP!WinHttpSetOption` at `0x1800c7612`
- `WINHTTP!WinHttpSetOption` at `0x1800c7659`
- `WINHTTP!WinHttpSetOption` at `0x1800c7612`
- `WINHTTP!WinHttpSetOption` at `0x1800c7659`
- `WINHTTP!WinHttpCrackUrl` at `0x1800c74a4`
- `WINHTTP!WinHttpCrackUrl` at `0x1800c74a4`

## string_xrefs

- `0x1800c741b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c7457`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c74ea`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c76f4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c7770`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c744a`: `Opening Internet connection in WinInet.`
- `0x1800c76db`: `SUCCEEDED(hr = CWinhttpSessions::SendRequestAndReceiveResponse(&serviceExecutionContext, m_hRequest, nullptr, 0, nullptr, 0, 0, NULL))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HTTPRequest::RequestUrlHelper(HINTERNET *a1, _QWORD *a2, LPVOID *a3, LPVOID *a4, _DWORD *lpBuffer)
{
  DWORD v9; // ebx
  const WCHAR *v10; // rax
  signed int LastError; // eax
  signed int v12; // r9d
  unsigned int v13; // r8d
  const char *v14; // rax
  HINTERNET v15; // rax
  signed int v16; // eax
  HINTERNET v17; // rax
  signed int v18; // eax
  int v19; // r9d
  signed int v20; // eax
  signed int v21; // eax
  unsigned int v22; // r9d
  signed int v23; // eax
  signed int v24; // eax
  unsigned int v25; // ebx
  LPCWSTR pwszReferrer; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwBufferLength; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR pwszObjectName; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pswzServerName[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+60h] [rbp-A0h] BYREF
  const char *v33[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[224]; // [rsp+F0h] [rbp-10h] BYREF
  CHAR Buffer[8112]; // [rsp+1D0h] [rbp+D0h] BYREF

  v28 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v33,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    2782,
    (const char *)&v28,
    "HTTPRequest::RequestUrlHelper",
    L"wstrUrl: %ls",
    *a2);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(pswzServerName);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pwszObjectName);
  dwBufferLength = 0;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    0xAE5u,
    L"Opening Internet connection in WinInet.");
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  v9 = *(_DWORD *)(*a2 - 16LL);
  v10 = (const WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(a2);
  if ( !WinHttpCrackUrl(v10, v9, 0, &UrlComponents) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v28 = v12;
    if ( v12 < 0 )
    {
      v13 = 2797;
LABEL_6:
      v14 = "hr = HRESULT_FROM_WIN32(GetLastError())";
LABEL_7:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        "HTTPRequest::RequestUrlHelper",
        v13,
        v12,
        v14);
      goto LABEL_51;
    }
  }
  if ( UrlComponents.lpszHostName )
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      pswzServerName,
      UrlComponents.lpszHostName,
      UrlComponents.dwHostNameLength);
  if ( UrlComponents.lpszUrlPath )
    ATL::CSimpleStringT<unsigned short,0>::SetString(
      &pwszObjectName,
      UrlComponents.lpszUrlPath,
      UrlComponents.dwUrlPathLength);
  if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER )
  {
    v14 = "HRESULT_FROM_WIN32(ERROR_WINHTTP_SECURE_FAILURE)";
    v12 = -2147012721;
    v13 = 2811;
    goto LABEL_7;
  }
  v15 = WinHttpConnect(*a1, pswzServerName[0], UrlComponents.nPort, 0);
  a1[1] = v15;
  if ( !v15 )
  {
    v16 = GetLastError();
    v12 = v16;
    if ( v16 > 0 )
      v12 = (unsigned __int16)v16 | 0x80070000;
    v28 = v12;
    if ( v12 < 0 )
    {
      v13 = 2818;
      goto LABEL_6;
    }
  }
  v17 = WinHttpOpenRequest(a1[1], L"GET", pwszObjectName, 0, 0, &off_1801C20B8, 0x800000u);
  a1[2] = v17;
  if ( !v17 )
  {
    v18 = GetLastError();
    v12 = v18;
    if ( v18 > 0 )
      v12 = (unsigned __int16)v18 | 0x80070000;
    v28 = v12;
    if ( v12 < 0 )
    {
      v13 = 2831;
      goto LABEL_6;
    }
  }
  v19 = *((_DWORD *)*a3 - 4);
  if ( v19 > 0 )
  {
    if ( !WinHttpSetOption(a1[2], 0x1002u, *a3, v19 + 1) )
    {
      v20 = GetLastError();
      v12 = v20;
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
      v28 = v12;
      if ( v12 < 0 )
      {
        v13 = 2840;
        goto LABEL_6;
      }
    }
    if ( !WinHttpSetOption(a1[2], 0x1003u, *a4, *((_DWORD *)*a4 - 4) + 1) )
    {
      v21 = GetLastError();
      v12 = v21;
      if ( v21 > 0 )
        v12 = (unsigned __int16)v21 | 0x80070000;
      v28 = v12;
      if ( v12 < 0 )
      {
        v13 = 2843;
        goto LABEL_6;
      }
    }
  }
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v34);
  v28 = CWinhttpSessions::SendRequestAndReceiveResponse(
          (struct IServiceExecutionContext *)v34,
          a1[2],
          0,
          v22,
          0,
          0,
          0,
          0);
  if ( v28 < 0 )
  {
    v28 = -2147188655;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "HTTPRequest::RequestUrlHelper",
      0xB28u,
      -2147188655,
      "SUCCEEDED(hr = CWinhttpSessions::SendRequestAndReceiveResponse(&serviceExecutionContext, m_hRequest, nullptr, 0, n"
      "ullptr, 0, 0, NULL))");
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v34);
    goto LABEL_51;
  }
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v34);
  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(a1[2], 0x20000013u, 0, lpBuffer, &dwBufferLength, 0) )
  {
    v23 = GetLastError();
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    v28 = v23;
    LODWORD(pwszReferrer) = v23;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      0xB36u,
      L"WinHttpQueryHeaders failed 0x%x.",
      pwszReferrer);
    v12 = -2147188655;
    v28 = -2147188655;
    v14 = "hr = PPCRL_E_HTTPSENDREQUEST";
    v13 = 2871;
    goto LABEL_7;
  }
  if ( *lpBuffer != 200 && *lpBuffer != 304 )
  {
    v12 = -2147188133;
    v28 = -2147188133;
    v14 = "HTTP_STATUS_OK == dwStatus || HTTP_STATUS_NOT_MODIFIED == dwStatus";
    v13 = 2880;
    goto LABEL_7;
  }
  dwBufferLength = 8097;
  if ( !WinHttpQueryHeaders(a1[2], 0x14u, 0, Buffer, &dwBufferLength, 0) )
  {
    v24 = GetLastError();
    v12 = v24;
    if ( v24 > 0 )
      v12 = (unsigned __int16)v24 | 0x80070000;
    v28 = v12;
    if ( v12 < 0 )
    {
      v13 = 2889;
      goto LABEL_6;
    }
  }
  if ( !lstrcmpA(Buffer, "No data") )
    v28 = 1;
LABEL_51:
  v25 = v28;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pwszObjectName);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(pswzServerName);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
  return v25;
}

```

## disassembly

```asm
0x1800c73a4  push    rbp
0x1800c73a6  push    rbx
0x1800c73a7  push    rsi
0x1800c73a8  push    rdi
0x1800c73a9  push    r12
0x1800c73ab  push    r14
0x1800c73ad  push    r15
0x1800c73af  lea     rbp, [rsp-2090h]
0x1800c73b7  mov     eax, 2190h
0x1800c73bc  call    _alloca_probe
0x1800c73c1  sub     rsp, rax
0x1800c73c4  mov     rax, cs:__security_cookie
0x1800c73cb  xor     rax, rsp
0x1800c73ce  mov     [rbp+20C0h+var_40], rax
0x1800c73d5  mov     r12, r9
0x1800c73d8  mov     r15, r8
0x1800c73db  mov     rdi, rdx
0x1800c73de  mov     rsi, rcx
0x1800c73e1  mov     r14, [rbp+20C0h+lpBuffer]
0x1800c73e8  mov     [rsp+21C0h+var_2180], 0
0x1800c73f0  mov     rax, [rdx]
0x1800c73f3  mov     qword ptr [rsp+21C0h+dwFlags], rax
0x1800c73f8  lea     rax, aWstrurlLs; "wstrUrl: %ls"
0x1800c73ff  mov     [rsp+21C0h+ppwszAcceptTypes], rax
0x1800c7404  lea     rax, aHttprequestReq; "HTTPRequest::RequestUrlHelper"
0x1800c740b  mov     [rsp+21C0h+pwszReferrer], rax
0x1800c7410  lea     r9, [rsp+21C0h+var_2180]
0x1800c7415  mov     r8d, 0ADEh
0x1800c741b  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c7422  lea     rcx, [rbp+20C0h+var_20F0]
0x1800c7426  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800c742b  nop
0x1800c742c  lea     rcx, [rsp+21C0h+pswzServerName]
0x1800c7431  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c7436  nop
0x1800c7437  lea     rcx, [rsp+21C0h+pwszObjectName]
0x1800c743c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c7441  nop
0x1800c7442  mov     [rsp+21C0h+dwBufferLength], 0
0x1800c744a  lea     r9, aOpeningInterne; "Opening Internet connection in WinInet."
0x1800c7451  mov     r8d, 0AE5h; unsigned int
0x1800c7457  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c745e  mov     ecx, 5; unsigned __int8
0x1800c7463  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c7468  mov     ebx, 68h ; 'h'
0x1800c746d  mov     r8d, ebx; Size
0x1800c7470  xor     edx, edx; Val
0x1800c7472  lea     rcx, [rsp+21C0h+UrlComponents]; void *
0x1800c7477  call    memset_0
0x1800c747c  mov     [rsp+21C0h+UrlComponents.dwStructSize], ebx
0x1800c7480  lea     eax, [rbx-67h]
0x1800c7483  mov     [rbp+20C0h+UrlComponents.dwHostNameLength], eax
0x1800c7486  mov     [rbp+20C0h+UrlComponents.dwUrlPathLength], eax
0x1800c7489  mov     rax, [rdi]
0x1800c748c  mov     ebx, [rax-10h]
0x1800c748f  mov     rcx, rdi
0x1800c7492  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800c7497  lea     r9, [rsp+21C0h+UrlComponents]; lpUrlComponents
0x1800c749c  xor     r8d, r8d; dwFlags
0x1800c749f  mov     edx, ebx; dwUrlLength
0x1800c74a1  mov     rcx, rax; pwszUrl
0x1800c74a4  call    cs:__imp_WinHttpCrackUrl
0x1800c74aa  mov     ebx, 80070000h
0x1800c74af  test    eax, eax
0x1800c74b1  jnz     short loc_1800C74FB
0x1800c74b3  call    cs:__imp_GetLastError
0x1800c74b9  mov     r9d, eax
0x1800c74bc  test    eax, eax
0x1800c74be  jle     short loc_1800C74C7
0x1800c74c0  movzx   r9d, ax
0x1800c74c4  or      r9d, ebx; int
0x1800c74c7  mov     [rsp+21C0h+var_2180], r9d
0x1800c74cc  test    r9d, r9d
0x1800c74cf  jns     short loc_1800C74FB
0x1800c74d1  mov     r8d, 0AEDh; unsigned int
0x1800c74d7  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c74de  mov     [rsp+21C0h+pwszReferrer], rax; char *
0x1800c74e3  lea     rdx, aHttprequestReq; "HTTPRequest::RequestUrlHelper"
0x1800c74ea  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c74f1  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c74f6  jmp     loc_1800C784D
0x1800c74fb  mov     rdx, [rsp+21C0h+UrlComponents.lpszHostName]
0x1800c7500  test    rdx, rdx
0x1800c7503  jz      short loc_1800C7513
0x1800c7505  mov     r8d, [rbp+20C0h+UrlComponents.dwHostNameLength]
0x1800c7509  lea     rcx, [rsp+21C0h+pswzServerName]
0x1800c750e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800c7513  mov     rdx, [rbp+20C0h+UrlComponents.lpszUrlPath]
0x1800c7517  test    rdx, rdx
0x1800c751a  jz      short loc_1800C752A
0x1800c751c  mov     r8d, [rbp+20C0h+UrlComponents.dwUrlPathLength]
0x1800c7520  lea     rcx, [rsp+21C0h+pwszObjectName]
0x1800c7525  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800c752a  cmp     [rsp+21C0h+UrlComponents.nScheme], 2
0x1800c752f  jz      short loc_1800C7546
0x1800c7531  lea     rax, aHresultFromWin_0; "HRESULT_FROM_WIN32(ERROR_WINHTTP_SECURE"...
0x1800c7538  mov     r9d, 80072F8Fh
0x1800c753e  mov     r8d, 0AFBh
0x1800c7544  jmp     short loc_1800C74DE
0x1800c7546  xor     r9d, r9d; dwReserved
0x1800c7549  movzx   r8d, [rbp+20C0h+UrlComponents.nPort]; nServerPort
0x1800c754e  mov     rdx, [rsp+21C0h+pswzServerName]; pswzServerName
0x1800c7553  mov     rcx, [rsi]; hSession
0x1800c7556  call    cs:__imp_WinHttpConnect
0x1800c755c  mov     [rsi+8], rax
0x1800c7560  test    rax, rax
0x1800c7563  jnz     short loc_1800C758E
0x1800c7565  call    cs:__imp_GetLastError
0x1800c756b  mov     r9d, eax
0x1800c756e  test    eax, eax
0x1800c7570  jle     short loc_1800C7579
0x1800c7572  movzx   r9d, ax
0x1800c7576  or      r9d, ebx
0x1800c7579  mov     [rsp+21C0h+var_2180], r9d
0x1800c757e  test    r9d, r9d
0x1800c7581  jns     short loc_1800C758E
0x1800c7583  mov     r8d, 0B02h
0x1800c7589  jmp     loc_1800C74D7
0x1800c758e  mov     [rsp+21C0h+dwFlags], 800000h; dwFlags
0x1800c7596  lea     rax, off_1801C20B8; "*/*"
0x1800c759d  mov     [rsp+21C0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1800c75a2  mov     [rsp+21C0h+pwszReferrer], 0; pwszReferrer
0x1800c75ab  xor     r9d, r9d; pwszVersion
0x1800c75ae  mov     r8, [rsp+21C0h+pwszObjectName]; pwszObjectName
0x1800c75b3  lea     rdx, aGet; "GET"
0x1800c75ba  mov     rcx, [rsi+8]; hConnect
0x1800c75be  call    cs:__imp_WinHttpOpenRequest
0x1800c75c4  mov     [rsi+10h], rax
0x1800c75c8  test    rax, rax
0x1800c75cb  jnz     short loc_1800C75F6
0x1800c75cd  call    cs:__imp_GetLastError
0x1800c75d3  mov     r9d, eax
0x1800c75d6  test    eax, eax
0x1800c75d8  jle     short loc_1800C75E1
0x1800c75da  movzx   r9d, ax
0x1800c75de  or      r9d, ebx
0x1800c75e1  mov     [rsp+21C0h+var_2180], r9d
0x1800c75e6  test    r9d, r9d
0x1800c75e9  jns     short loc_1800C75F6
0x1800c75eb  mov     r8d, 0B0Fh
0x1800c75f1  jmp     loc_1800C74D7
0x1800c75f6  mov     r8, [r15]; lpBuffer
0x1800c75f9  mov     r9d, [r8-10h]
0x1800c75fd  test    r9d, r9d
0x1800c7600  jle     loc_1800C768C
0x1800c7606  inc     r9d; dwBufferLength
0x1800c7609  mov     edx, 1002h; dwOption
0x1800c760e  mov     rcx, [rsi+10h]; hInternet
0x1800c7612  call    cs:__imp_WinHttpSetOption
0x1800c7618  test    eax, eax
0x1800c761a  jnz     short loc_1800C7645
0x1800c761c  call    cs:__imp_GetLastError
0x1800c7622  mov     r9d, eax
0x1800c7625  test    eax, eax
0x1800c7627  jle     short loc_1800C7630
0x1800c7629  movzx   r9d, ax
0x1800c762d  or      r9d, ebx
0x1800c7630  mov     [rsp+21C0h+var_2180], r9d
0x1800c7635  test    r9d, r9d
0x1800c7638  jns     short loc_1800C7645
0x1800c763a  mov     r8d, 0B18h
0x1800c7640  jmp     loc_1800C74D7
0x1800c7645  mov     r8, [r12]; lpBuffer
0x1800c7649  mov     r9d, [r8-10h]
0x1800c764d  inc     r9d; dwBufferLength
0x1800c7650  mov     edx, 1003h; dwOption
0x1800c7655  mov     rcx, [rsi+10h]; hInternet
0x1800c7659  call    cs:__imp_WinHttpSetOption
0x1800c765f  test    eax, eax
0x1800c7661  jnz     short loc_1800C768C
0x1800c7663  call    cs:__imp_GetLastError
0x1800c7669  mov     r9d, eax
0x1800c766c  test    eax, eax
0x1800c766e  jle     short loc_1800C7677
0x1800c7670  movzx   r9d, ax
0x1800c7674  or      r9d, ebx
0x1800c7677  mov     [rsp+21C0h+var_2180], r9d
0x1800c767c  test    r9d, r9d
0x1800c767f  jns     short loc_1800C768C
0x1800c7681  mov     r8d, 0B1Bh
0x1800c7687  jmp     loc_1800C74D7
0x1800c768c  lea     rcx, [rbp+20C0h+var_20D0]; this
0x1800c7690  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800c7695  nop
0x1800c7696  mov     [rsp+21C0h+var_2188], 0; unsigned __int64
0x1800c769f  mov     [rsp+21C0h+dwFlags], 0; unsigned int
0x1800c76a7  mov     dword ptr [rsp+21C0h+ppwszAcceptTypes], 0; unsigned int
0x1800c76af  mov     [rsp+21C0h+pwszReferrer], 0; void *
0x1800c76b8  xor     r8d, r8d; unsigned __int16 *
0x1800c76bb  mov     rdx, [rsi+10h]; void *
0x1800c76bf  lea     rcx, [rbp+20C0h+var_20D0]; struct IServiceExecutionContext *
0x1800c76c3  call    ?SendRequestAndReceiveResponse@CWinhttpSessions@@SAJPEAVIServiceExecutionContext@@PEAXPEBGK1KK_K@Z; CWinhttpSessions::SendRequestAndReceiveResponse(IServiceExecutionContext *,void *,ushort const *,ulong,void *,ulong,ulong,unsigned __int64)
0x1800c76c8  mov     [rsp+21C0h+var_2180], eax
0x1800c76cc  test    eax, eax
0x1800c76ce  jns     short loc_1800C770F
0x1800c76d0  mov     r9d, 80048051h; int
0x1800c76d6  mov     [rsp+21C0h+var_2180], r9d
0x1800c76db  lea     rax, aSucceededHrCwi; "SUCCEEDED(hr = CWinhttpSessions::SendRe"...
0x1800c76e2  mov     [rsp+21C0h+pwszReferrer], rax; char *
0x1800c76e7  mov     r8d, 0B28h; unsigned int
0x1800c76ed  lea     rdx, aHttprequestReq; "HTTPRequest::RequestUrlHelper"
0x1800c76f4  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c76fb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c7700  nop
0x1800c7701  lea     rcx, [rbp+20C0h+var_20D0]; this
0x1800c7705  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800c770a  jmp     loc_1800C784D
0x1800c770f  lea     rcx, [rbp+20C0h+var_20D0]; this
0x1800c7713  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800c7718  mov     [rsp+21C0h+dwBufferLength], 4
0x1800c7720  mov     [rsp+21C0h+ppwszAcceptTypes], 0; lpdwIndex
0x1800c7729  lea     rax, [rsp+21C0h+dwBufferLength]
0x1800c772e  mov     [rsp+21C0h+pwszReferrer], rax; lpdwBufferLength
0x1800c7733  mov     r9, r14; lpBuffer
0x1800c7736  xor     r8d, r8d; pwszName
0x1800c7739  mov     edx, 20000013h; dwInfoLevel
0x1800c773e  mov     rcx, [rsi+10h]; hRequest
0x1800c7742  call    cs:__imp_WinHttpQueryHeaders
0x1800c7748  test    eax, eax
0x1800c774a  jnz     short loc_1800C779E
0x1800c774c  call    cs:__imp_GetLastError
0x1800c7752  test    eax, eax
0x1800c7754  jle     short loc_1800C775B
0x1800c7756  movzx   eax, ax
0x1800c7759  or      eax, ebx
0x1800c775b  mov     [rsp+21C0h+var_2180], eax
0x1800c775f  mov     dword ptr [rsp+21C0h+pwszReferrer], eax
0x1800c7763  lea     r9, aWinhttpqueryhe_2; "WinHttpQueryHeaders failed 0x%x."
0x1800c776a  mov     r8d, 0B36h; unsigned int
0x1800c7770  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c7777  mov     ecx, 2; unsigned __int8
0x1800c777c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c7781  mov     r9d, 80048051h
0x1800c7787  mov     [rsp+21C0h+var_2180], r9d
0x1800c778c  lea     rax, aHrPpcrlEHttpse; "hr = PPCRL_E_HTTPSENDREQUEST"
0x1800c7793  mov     r8d, 0B37h
0x1800c7799  jmp     loc_1800C74DE
0x1800c779e  cmp     dword ptr [r14], 0C8h
0x1800c77a5  jz      short loc_1800C77CD
0x1800c77a7  cmp     dword ptr [r14], 130h
0x1800c77ae  jz      short loc_1800C77CD
0x1800c77b0  mov     r9d, 8004825Bh
0x1800c77b6  mov     [rsp+21C0h+var_2180], r9d
0x1800c77bb  lea     rax, aHttpStatusOkDw; "HTTP_STATUS_OK == dwStatus || HTTP_STAT"...
0x1800c77c2  mov     r8d, 0B40h
0x1800c77c8  jmp     loc_1800C74DE
0x1800c77cd  mov     [rsp+21C0h+dwBufferLength], 1FA1h
0x1800c77d5  mov     [rsp+21C0h+ppwszAcceptTypes], 0; lpdwIndex
0x1800c77de  lea     rax, [rsp+21C0h+dwBufferLength]
0x1800c77e3  mov     [rsp+21C0h+pwszReferrer], rax; lpdwBufferLength
0x1800c77e8  lea     r9, [rbp+20C0h+Buffer]; lpBuffer
0x1800c77ef  xor     r8d, r8d; pwszName
0x1800c77f2  lea     edx, [r8+14h]; dwInfoLevel
0x1800c77f6  mov     rcx, [rsi+10h]; hRequest
0x1800c77fa  call    cs:__imp_WinHttpQueryHeaders
0x1800c7800  test    eax, eax
0x1800c7802  jnz     short loc_1800C782D
0x1800c7804  call    cs:__imp_GetLastError
0x1800c780a  mov     r9d, eax
0x1800c780d  test    eax, eax
0x1800c780f  jle     short loc_1800C7818
0x1800c7811  movzx   r9d, ax
0x1800c7815  or      r9d, ebx
0x1800c7818  mov     [rsp+21C0h+var_2180], r9d
0x1800c781d  test    r9d, r9d
0x1800c7820  jns     short loc_1800C782D
0x1800c7822  mov     r8d, 0B49h
0x1800c7828  jmp     loc_1800C74D7
0x1800c782d  lea     rdx, aNoData; "No data"
0x1800c7834  lea     rcx, [rbp+20C0h+Buffer]; lpString1
0x1800c783b  call    cs:__imp_lstrcmpA
0x1800c7841  test    eax, eax
0x1800c7843  jnz     short loc_1800C784D
0x1800c7845  mov     [rsp+21C0h+var_2180], 1
0x1800c784d  mov     ebx, [rsp+21C0h+var_2180]
0x1800c7851  lea     rcx, [rsp+21C0h+pwszObjectName]
0x1800c7856  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c785b  nop
0x1800c785c  lea     rcx, [rsp+21C0h+pswzServerName]
0x1800c7861  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c7866  nop
0x1800c7867  lea     rcx, [rbp+20C0h+var_20F0]
0x1800c786b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800c7870  mov     eax, ebx
0x1800c7872  mov     rcx, [rbp+20C0h+var_40]
0x1800c7879  xor     rcx, rsp; StackCookie
0x1800c787c  call    __security_check_cookie
0x1800c7881  add     rsp, 2190h
0x1800c7888  pop     r15
0x1800c788a  pop     r14
0x1800c788c  pop     r12
0x1800c788e  pop     rdi
0x1800c788f  pop     rsi
0x1800c7890  pop     rbx
0x1800c7891  pop     rbp
0x1800c7892  retn
```
