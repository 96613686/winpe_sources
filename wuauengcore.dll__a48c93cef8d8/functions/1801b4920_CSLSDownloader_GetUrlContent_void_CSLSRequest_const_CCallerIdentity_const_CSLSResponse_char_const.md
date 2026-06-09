# CSLSDownloader::GetUrlContent(void *,CSLSRequest const &,CCallerIdentity const *,CSLSResponse &,char const *)

- ea: `0x1801b4920`
- end: `0x1801b5559`
- name: `?GetUrlContent@CSLSDownloader@@QEAAJPEAXAEBVCSLSRequest@@PEBVCCallerIdentity@@AEAVCSLSResponse@@PEBD@Z`
- size: `3129`
- prototype: `__int64 __fastcall(CSLSDownloader *__hidden this, void *, const struct CSLSRequest *, const struct CCallerIdentity *, struct CSLSResponse *, const char *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801b17b8`

## callees

- `0x18000c824`
- `0x18000df20`
- `0x180014964`
- `0x180038d00`
- `0x18005f4c4`
- `0x18005f808`
- `0x18007b7c0`
- `0x18010f31c`
- `0x18011098c`
- `0x180113ae8`
- `0x180113b9c`
- `0x180124c64`
- `0x180127a58`
- `0x18012b618`
- `0x18012d9d4`
- `0x18012dd74`
- `0x1801320ac`
- `0x1801b2ee8`
- `0x1801b4230`
- `0x1801b4854`
- `0x1801b4920`
- `0x1801b5560`
- `0x1801da650`
- `0x1801da7cc`
- `0x1801dc190`
- `0x1801e62f0`
- `0x1801e64d0`
- `0x1801e6764`
- `0x180238960`
- `0x180238984`
- `0x180240c50`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801b5223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801b5262`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801b5223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801b5262`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801b4cda`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801b4cda`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b4aa8`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b54a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b5500`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b4aa8`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b54a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b5500`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b4a55`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b4a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b52f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b5424`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b4a55`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b4a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b52f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801b5424`

## string_xrefs

- `0x1801b4a2f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801b4b30`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1801b4a28`: `SLSResponseCabOverridePath`
- `0x1801b4ae3`: `strFilePath.Assign`
- `0x1801b4ffc`: `Complete the request URL %ws with [%08X] and http status code[%d] and send SLS events.`
- `0x1801b5232`: `text/xml;`
- `0x1801b5206`: `text/xml`
- `0x1801b5310`: `X-Microsoft-SLSClientCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CSLSDownloader::GetUrlContent(
        CSLSDownloader *this,
        void *a2,
        GUID *a3,
        const struct CCallerIdentity *a4,
        struct CSLSResponse *a5,
        char *a6)
{
  struct CSLSResponse *v7; // rsi
  WCHAR *v8; // r15
  wchar_t *v9; // r12
  wchar_t *v10; // rdi
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // bl
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // r8
  int LocalFilePath; // r13d
  wchar_t *v19; // r14
  int v20; // eax
  wchar_t *v21; // rsi
  unsigned __int64 v22; // r13
  wchar_t *v23; // rbx
  __int64 v24; // rcx
  wchar_t *v25; // rax
  wchar_t *v26; // rax
  TraceLoggingCorrelationVector *v27; // rax
  TraceLoggingCorrelationVector *v28; // rbx
  const char *v29; // r9
  int v30; // eax
  char *v31; // rax
  char *v32; // r14
  bool v33; // zf
  bool v34; // sf
  CSLSDownloader *v35; // rcx
  unsigned __int64 v36; // r8
  char *v37; // r13
  const wchar_t *v38; // r8
  const OLECHAR *v39; // r8
  __int64 v40; // rdx
  int StringHeaderValueWorker; // eax
  int v42; // eax
  int v43; // esi
  int v44; // eax
  int v45; // eax
  unsigned int v46; // esi
  unsigned __int64 v47; // rsi
  unsigned int SLSExpireSecsInADay; // eax
  int v49; // esi
  int v50; // ecx
  wchar_t *v51; // rbx
  void *v52; // rcx
  __int64 v54; // [rsp+38h] [rbp-C8h]
  int v55; // [rsp+40h] [rbp-C0h]
  __int64 v56; // [rsp+40h] [rbp-C0h]
  __int64 v57; // [rsp+48h] [rbp-B8h]
  char v58; // [rsp+60h] [rbp-A0h]
  char v59; // [rsp+61h] [rbp-9Fh]
  bool v60; // [rsp+62h] [rbp-9Eh]
  bool v61; // [rsp+63h] [rbp-9Dh] BYREF
  int v62; // [rsp+64h] [rbp-9Ch]
  int NetworkLevel; // [rsp+68h] [rbp-98h]
  unsigned int v64; // [rsp+6Ch] [rbp-94h]
  int v65; // [rsp+70h] [rbp-90h]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v68; // [rsp+88h] [rbp-78h]
  GUID *rguid; // [rsp+90h] [rbp-70h]
  struct CSLSResponse *v70; // [rsp+98h] [rbp-68h]
  char *v71; // [rsp+A0h] [rbp-60h]
  void *lpMem; // [rsp+A8h] [rbp-58h] BYREF
  char *Str; // [rsp+B0h] [rbp-50h]
  wchar_t *v74; // [rsp+B8h] [rbp-48h] BYREF
  PCNZWCH lpString1; // [rsp+C0h] [rbp-40h] BYREF
  int v76; // [rsp+C8h] [rbp-38h]
  struct _GUID v77; // [rsp+D0h] [rbp-30h] BYREF
  void *v78; // [rsp+E0h] [rbp-20h]
  wchar_t *v79; // [rsp+E8h] [rbp-18h]
  wchar_t *String; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *v81; // [rsp+F8h] [rbp-8h]
  wchar_t *v82; // [rsp+100h] [rbp+0h]
  __int64 v83; // [rsp+108h] [rbp+8h]
  struct _FILETIME v84; // [rsp+110h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v86[30]; // [rsp+120h] [rbp+20h] BYREF
  CHAR MultiByteStr[144]; // [rsp+210h] [rbp+110h] BYREF
  WCHAR WideCharStr[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t v89[2088]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1548h] [rbp+1448h]

  rguid = a3;
  v78 = a2;
  v7 = a5;
  v70 = a5;
  Str = a6;
  memset(v86, 0, sizeof(v86));
  CDownloadSession::CDownloadSession((CDownloadSession *)v86, a4);
  v59 = 0;
  NetworkLevel = 0;
  LODWORD(v67) = 0;
  v65 = 2;
  v8 = 0;
  lpString1 = 0;
  v9 = 0;
  String = 0;
  v64 = 0;
  v83 = 0;
  v84 = 0;
  SystemTimeAsFileTime = 0;
  bstrString = 0;
  v74 = 0;
  v10 = 0;
  v79 = 0;
  v61 = 0;
  v76 = AreTestKeysAllowed(1);
  v13 = 0;
  v58 = 0;
  if ( v76 )
  {
    memset(WideCharStr, 0, 522);
    if ( (int)RegQueryStringValue(
                v12,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                L"SLSResponseCabOverridePath",
                WideCharStr,
                261) >= 0
      && WideCharStr[0] )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      GetSystemTimeAsFileTime(&v84);
      v15 = v84.dwLowDateTime + ((unsigned __int64)v84.dwHighDateTime << 32) + 864000000000LL;
      v84.dwLowDateTime += 711573504;
      v84.dwHighDateTime = HIDWORD(v15);
      v59 = 0;
      v65 = 2;
      NetworkLevel = 1;
      v64 = 200;
      SysFreeString(0);
      bstrString = 0;
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( WideCharStr[v17] );
      LocalFilePath = CSusBSTR::Append((CSusBSTR *)&bstrString, WideCharStr, v17);
      if ( LocalFilePath >= 0 )
      {
        v19 = bstrString;
LABEL_118:
        *((_BYTE *)v7 + 31) = v59;
        *((_DWORD *)v7 + 8) = v65;
        v50 = NetworkLevel;
        *((_BYTE *)v7 + 28) = NetworkLevel != 0;
        if ( v50 )
          *((_BYTE *)v7 + 29) = 0;
        *(struct _FILETIME *)v7 = v84;
        *((struct _FILETIME *)v7 + 1) = SystemTimeAsFileTime;
        *((_DWORD *)v7 + 6) = v64;
        if ( v19 != *((wchar_t **)v7 + 2) )
        {
          SysFreeString(*((BSTR *)v7 + 2));
          *((_QWORD *)v7 + 2) = 0;
          if ( v19 )
          {
            do
              ++v16;
            while ( v19[v16] );
          }
          else
          {
            LODWORD(v16) = 0;
          }
          CSusBSTR::Append((struct CSLSResponse *)((char *)v7 + 16), v19, v16);
        }
        v51 = v10;
        v10 = 0;
        v52 = (void *)*((_QWORD *)v7 + 5);
        if ( v52 )
          SusFree(v52);
        *((_QWORD *)v7 + 5) = v51;
        goto LABEL_129;
      }
      WUTrace(0, 0, 4, 3, LocalFilePath, L"strFilePath.Assign");
      v19 = bstrString;
LABEL_117:
      if ( LocalFilePath < 0 )
        goto LABEL_129;
      goto LABEL_118;
    }
    v20 = RegQueryDwordValueWithDefaultAndRangeCheck(
            v14,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            L"SLSBlockNoneMatchHeader",
            0,
            0,
            -1);
    v13 = v20 != 0;
    if ( v20 )
      WUTrace(0, 0, 4, 4, 0, L"SLSBlockNoneMatchHeader override set.");
  }
  *(_QWORD *)&v77.Data1 = 0;
  v62 = 0;
  v21 = 0;
  v81 = 0;
  v22 = 0;
  if ( v13 )
  {
    v23 = 0;
  }
  else
  {
    v23 = 0;
    if ( (int)DuplicateString<wchar_t *,wchar_t *>(*((_QWORD *)v70 + 5), &v74) >= 0 )
    {
      v10 = v74;
      v79 = v74;
      if ( v74 )
      {
        v24 = 0x7FFFFFFF;
        v25 = v74;
        do
        {
          if ( !*v25 )
            break;
          ++v25;
          --v24;
        }
        while ( v24 );
        v11 = (0x7FFFFFFF - v24) & ((unsigned __int128)-(__int128)(unsigned __int64)v24 >> 64);
        if ( v24 )
        {
          v22 = v11 + 17;
          if ( v11 + 17 < v11 )
          {
            v22 = -1;
          }
          else
          {
            v26 = (wchar_t *)SafeSusAllocArray(v22, 2u);
            v21 = v26;
            v81 = v26;
            if ( v26 && (int)StringCchPrintfW(v26, v22, L"%s%s", L"If-None-Match: ", v10) >= 0 )
            {
              LODWORD(v86[28]) = 1;
              v58 = 1;
              v62 = v22;
            }
          }
        }
      }
    }
  }
  v82 = 0;
  if ( !Str || !*Str )
  {
    v68 = 0;
LABEL_37:
    v30 = v62;
    goto LABEL_38;
  }
  MultiByteStr[0] = 0;
  v27 = TraceLoggingCorrelationVector::Set(Str, v11);
  v28 = v27;
  if ( v27 )
  {
    TraceLoggingCorrelationVector::Increment(v27, MultiByteStr);
    operator delete(v28, (const struct std::nothrow_t *)0x90);
  }
  v23 = (wchar_t *)SafeSusAllocArray(0x8Au, 2u);
  v82 = v23;
  v68 = 137;
  if ( !v23 )
    goto LABEL_37;
  if ( !MultiByteToWideChar(0, 1u, MultiByteStr, -1, WideCharStr, 129) )
  {
    v68 = 137;
    if ( (int)wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x7F,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MultiByteUtil.cpp",
                v29) < 0 )
      goto LABEL_37;
  }
  v68 = 137;
  if ( (int)StringCchPrintfW(v23, 0x89u, L"%ws%ws", L"MS-CV: ", WideCharStr) < 0 )
    goto LABEL_37;
  WUTrace(0, 0, 4, 5, 0, L"MS-CV header: %ws", v23);
  v30 = v62 + 137;
  if ( v21 && *v21 )
    v30 = v62 + 139;
  v68 = 137;
LABEL_38:
  v31 = (char *)SafeSusAllocArray((unsigned int)(v30 + 1), 2u);
  v32 = v31;
  lpMem = v31;
  LOBYTE(v62) = v21 == 0;
  if ( v21 )
  {
    if ( (int)StringCchPrintfW((wchar_t *)v31, v22, L"%ws", v21) < 0 )
    {
      v31 = v32;
    }
    else
    {
      v31 = &v32[2 * v22];
      v71 = v31;
      v33 = v23 == 0;
      if ( !v23 )
        goto LABEL_45;
      v34 = (int)StringCchPrintfW((wchar_t *)v31, 2u, L"%ws", L"\r\n") < 0;
      v31 = v71;
      if ( !v34 )
        v31 = v71 + 4;
    }
  }
  v33 = v23 == 0;
LABEL_45:
  v60 = v33;
  LOBYTE(v71) = v33;
  if ( v23 )
    StringCchPrintfW((wchar_t *)v31, v68, L"%ws", v23);
  WUTrace(0, 0, 4, 5, 0, L"SLS request headers: %ws", v32);
  LocalFilePath = CSLSDownloader::GetLocalFilePath(v35, rguid, (struct CSusBSTR *)&bstrString, v78);
  if ( LocalFilePath < 0
    || (v89[0] = 0,
        LocalFilePath = CSLSRequest::GetUrl((CSLSRequest *)rguid, v89, v36, (unsigned __int64 *)&v77.Data1, &v61),
        LocalFilePath < 0) )
  {
    if ( !v60 )
      SusFree(v23);
    if ( !(_BYTE)v62 )
      SusFree(v21);
    if ( v32 )
      SusFree(v32);
    v19 = bstrString;
    goto LABEL_55;
  }
  v37 = Str;
  WUTrace(0, 0, 4, 4, 0, L"Making request with URL %ws and send SLS events, cV=%hs.", v89, Str);
  v38 = &OutputString;
  if ( v58 )
    v38 = v10;
  v77 = *rguid;
  sls::telemetry::DiscoveryEvent::SendRequestStartEvent(&v77, *(const wchar_t **)&rguid[2].Data1, v38, v37);
  v57 = (__int64)v32;
  LOBYTE(v55) = 1;
  v19 = bstrString;
  LocalFilePath = CDownloadSession::DoFileDownload(
                    (CDownloadSession *)v86,
                    v78,
                    (__int64)bstrString,
                    0,
                    (__int64)&v67,
                    v55,
                    v57,
                    2);
  if ( !v86[29] )
  {
    LocalFilePath = -2145120257;
    if ( !(_BYTE)v71 )
      SusFree(v23);
    if ( !(_BYTE)v62 )
      SusFree(v21);
    if ( lpMem )
      SusFree(lpMem);
    goto LABEL_129;
  }
  NetworkLevel = NetworkUtil::GetNetworkLevel();
  v64 = v86[24];
  LODWORD(v56) = v86[24];
  LODWORD(v54) = LocalFilePath;
  WUTrace(
    0,
    0,
    4,
    4,
    0,
    L"Complete the request URL %ws with [%08X] and http status code[%d] and send SLS events.",
    v89,
    v54,
    v56);
  v39 = &OutputString;
  v40 = *(_QWORD *)&rguid[2].Data1;
  v77 = *rguid;
  if ( LocalFilePath < 0 )
  {
    if ( v58 )
      v39 = v10;
    sls::telemetry::DiscoveryEvent::SendRequestFailedEvent(
      &v77,
      v40,
      v39,
      v64,
      LocalFilePath,
      Str,
      v86[29],
      NetworkLevel);
  }
  else
  {
    if ( v58 )
      v39 = v10;
    sls::telemetry::DiscoveryEvent::SendRequestSucceededEvent(&v77, v40, v39, v64, Str, v86[29], NetworkLevel);
  }
  if ( !(_BYTE)v71 )
    SusFree(v23);
  if ( !(_BYTE)v62 )
    SusFree(v21);
  if ( lpMem )
    SusFree(lpMem);
  if ( HIDWORD(v86[27]) )
  {
    WUTrace(0, 0, 4, 3, 0, L"*** Potential Failover Scenario ***");
    v59 = 1;
  }
  if ( LocalFilePath < 0 )
  {
    WUTrace(0, 0, 4, 1, LocalFilePath, L"GetDownloadedOnWeakSSLCert");
    NetworkLevel = v67;
LABEL_55:
    v16 = -1;
LABEL_116:
    v7 = v70;
    goto LABEL_117;
  }
  NetworkLevel = v67;
  if ( !(_DWORD)v67 )
  {
    v16 = -1;
    goto LABEL_103;
  }
  if ( v10 )
    SusFree(v10);
  StringHeaderValueWorker = CDownloadSession::GetStringHeaderValueWorker((CDownloadSession *)v86, 0x36u, 0, &v74);
  v10 = v74;
  v79 = v74;
  if ( StringHeaderValueWorker >= 0 )
  {
    WUTrace(0, 0, 4, 5, 0, L"New ETAG value %ws", v74);
    if ( v76 )
      LogETagValue(rguid);
  }
  else
  {
    WUTrace(0, 0, 4, 5, StringHeaderValueWorker, L"Failed to get the ETAG value; ignoring...");
  }
  if ( SLODWORD(v86[27]) < 0 )
    v42 = CDownloadSession::GetStringHeaderValueWorker((CDownloadSession *)v86, 1u, 0, (wchar_t **)&lpString1);
  else
    v42 = DuplicateString<wchar_t *,wchar_t *>(v86[26], &lpString1);
  LocalFilePath = v42;
  v8 = (WCHAR *)lpString1;
  if ( v42 >= 0 )
  {
    v16 = -1;
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"text/xml", -1) == 2
      || (unsigned int)WUStringStartsWithI(v8, L"text/xml;") )
    {
      v43 = 1;
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, v8, -1, L"application/octet-stream", -1) != 2
        && !(unsigned int)WUStringStartsWithI(v8, L"application/octet-stream;") )
      {
        LocalFilePath = -2145103867;
        WUTrace(0, 0, 4, 1, 0, L"Unsupported content type in response: %ws", v8);
        goto LABEL_129;
      }
      v43 = 2;
    }
    v65 = v43;
    WUTrace(0, 0, 4, 5, 0, L"Content Type for Response: %ws", v8);
    if ( v43 == 1 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
LABEL_115:
      v64 = v86[24];
      LocalFilePath = 0;
      goto LABEL_116;
    }
LABEL_103:
    lpMem = 0;
    v44 = CDownloadSession::GetStringHeaderValueWorker(
            (CDownloadSession *)v86,
            0xFFFFu,
            L"X-Microsoft-SLSClientCache",
            &String);
    if ( v44 < 0 )
      WUTrace(0, 0, 4, 1, v44, L"GetStringHeaderValue");
    v9 = String;
    v45 = Safe_wtoi64(String, (__int64 *)&lpMem);
    if ( v45 < 0 )
      WUTrace(0, 0, 4, 1, v45, L"Safe_wtoi64");
    v46 = (unsigned int)lpMem;
    if ( (unsigned __int64)lpMem > 0xFFFFFFFF )
    {
      v46 = -1;
      WUTrace(0, 0, 4, 1, -2147024362, L"Int64ToDWord");
    }
    v47 = 60LL * v46;
    if ( v47 > 0xFFFFFFFF )
    {
      LODWORD(v47) = -1;
      WUTrace(0, 0, 4, 1, -2147024362, L"DWordMult");
    }
    SLSExpireSecsInADay = GetSLSExpireSecsInADay();
    v84 = (struct _FILETIME)CalculateWaitFileTime((unsigned int)v47, 0, SLSExpireSecsInADay);
    v49 = HIDWORD(v86[25]);
    if ( v86[25] < 0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      WUTrace(0, 0, 4, 1, v49, L"GetLastModified");
    }
    else
    {
      SystemTimeAsFileTime = *(struct _FILETIME *)((char *)&v86[24] + 4);
    }
    goto LABEL_115;
  }
LABEL_129:
  if ( v10 )
    SusFree(v10);
  SysFreeString(v19);
  if ( v9 )
    SusFree(v9);
  if ( v8 )
    SusFree(v8);
  CDownloadSession::~CDownloadSession((CDownloadSession *)v86);
  return (unsigned int)LocalFilePath;
}

```

## disassembly

```asm
0x1801b4920  mov     [rsp-8+arg_0], rbx
0x1801b4925  push    rbp
0x1801b4926  push    rsi
0x1801b4927  push    rdi
0x1801b4928  push    r12
0x1801b492a  push    r13
0x1801b492c  push    r14
0x1801b492e  push    r15
0x1801b4930  lea     rbp, [rsp-1410h]
0x1801b4938  mov     eax, 1510h
0x1801b493d  call    _alloca_probe
0x1801b4942  sub     rsp, rax
0x1801b4945  mov     rax, cs:__security_cookie
0x1801b494c  xor     rax, rsp
0x1801b494f  mov     [rbp+1440h+var_40], rax
0x1801b4956  mov     rbx, r9
0x1801b4959  mov     [rbp+1440h+rguid], r8
0x1801b495d  mov     [rbp+1440h+var_1460], rdx
0x1801b4961  mov     rsi, [rbp+1440h+arg_20]
0x1801b4968  mov     [rbp+1440h+var_14A8], rsi
0x1801b496c  mov     rax, [rbp+1440h+arg_28]
0x1801b4973  mov     [rbp+1440h+Str], rax
0x1801b4977  xor     edx, edx; Val
0x1801b4979  mov     r8d, 0F0h; Size
0x1801b497f  lea     rcx, [rbp+1440h+var_1420]; void *
0x1801b4983  call    memset
0x1801b4988  mov     rdx, rbx; struct CCallerIdentity *
0x1801b498b  lea     rcx, [rbp+1440h+var_1420]; this
0x1801b498f  call    ??0CDownloadSession@@QEAA@PEBVCCallerIdentity@@@Z; CDownloadSession::CDownloadSession(CCallerIdentity const *)
0x1801b4994  nop
0x1801b4995  xor     r14d, r14d
0x1801b4998  mov     [rsp+1540h+var_14DF], r14b
0x1801b499d  mov     eax, r14d
0x1801b49a0  mov     [rsp+1540h+var_14D8], eax
0x1801b49a4  mov     dword ptr [rbp+1440h+var_14C0], eax
0x1801b49a7  mov     [rsp+1540h+var_14D0], 2
0x1801b49af  mov     r15d, r14d
0x1801b49b2  mov     [rbp+1440h+lpString1], r14
0x1801b49b6  mov     r12d, r14d
0x1801b49b9  mov     [rbp+1440h+String], r14
0x1801b49bd  mov     [rsp+1540h+var_14D4], r14d
0x1801b49c2  mov     [rbp+1440h+var_1438], r14
0x1801b49c6  mov     qword ptr [rbp+1440h+var_1430.dwLowDateTime], r14
0x1801b49ca  mov     qword ptr [rbp+1440h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1801b49ce  mov     [rsp+1540h+bstrString], r14
0x1801b49d3  mov     [rbp+1440h+var_1488], r14
0x1801b49d7  mov     edi, r14d
0x1801b49da  mov     [rbp+1440h+var_1458], r14
0x1801b49de  mov     [rsp+1540h+var_14DD], r14b
0x1801b49e3  mov     cl, 1; bool
0x1801b49e5  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801b49ea  mov     [rbp+1440h+var_1478], eax
0x1801b49ed  mov     bl, r14b
0x1801b49f0  mov     [rsp+1540h+var_14E0], r14b
0x1801b49f5  test    eax, eax
0x1801b49f7  jz      loc_1801B4B66
0x1801b49fd  mov     [rbp+1440h+WideCharStr], r14w
0x1801b4a05  xor     edx, edx; Val
0x1801b4a07  mov     r8d, 208h; Size
0x1801b4a0d  lea     rcx, [rbp+1440h+var_129E]; void *
0x1801b4a14  call    memset
0x1801b4a19  mov     dword ptr [rsp+1540h+lpWideCharStr], 105h
0x1801b4a21  lea     r9, [rbp+1440h+WideCharStr]
0x1801b4a28  lea     r8, ?c_szRegSLSResponseCabOverridePath@@3QB_WB; "SLSResponseCabOverridePath"
0x1801b4a2f  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b4a36  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x1801b4a3b  test    eax, eax
0x1801b4a3d  js      loc_1801B4B19
0x1801b4a43  cmp     [rbp+1440h+WideCharStr], r14w
0x1801b4a4b  jz      loc_1801B4B19
0x1801b4a51  lea     rcx, [rbp+1440h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801b4a55  call    cs:__imp_GetSystemTimeAsFileTime
0x1801b4a5b  lea     rcx, [rbp+1440h+var_1430]; lpSystemTimeAsFileTime
0x1801b4a5f  call    cs:__imp_GetSystemTimeAsFileTime
0x1801b4a65  mov     eax, [rbp+1440h+var_1430.dwHighDateTime]
0x1801b4a68  shl     rax, 20h
0x1801b4a6c  mov     ecx, [rbp+1440h+var_1430.dwLowDateTime]
0x1801b4a6f  mov     rdx, 0C92A69C000h
0x1801b4a79  add     rdx, rax
0x1801b4a7c  add     rdx, rcx
0x1801b4a7f  mov     [rbp+1440h+var_1430.dwLowDateTime], edx
0x1801b4a82  shr     rdx, 20h
0x1801b4a86  mov     [rbp+1440h+var_1430.dwHighDateTime], edx
0x1801b4a89  mov     [rsp+1540h+var_14DF], r14b
0x1801b4a8e  mov     [rsp+1540h+var_14D0], 2
0x1801b4a96  mov     [rsp+1540h+var_14D8], 1
0x1801b4a9e  mov     [rsp+1540h+var_14D4], 0C8h
0x1801b4aa6  xor     ecx, ecx; bstrString
0x1801b4aa8  call    cs:__imp_SysFreeString
0x1801b4aae  mov     [rsp+1540h+bstrString], r14
0x1801b4ab3  lea     rax, [rbp+1440h+WideCharStr]
0x1801b4aba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801b4abe  mov     r8, rbx
0x1801b4ac1  inc     r8; unsigned int
0x1801b4ac4  cmp     [rax+r8*2], r14w
0x1801b4ac9  jnz     short loc_1801B4AC1
0x1801b4acb  lea     rdx, [rbp+1440h+WideCharStr]; wchar_t *
0x1801b4ad2  lea     rcx, [rsp+1540h+bstrString]; this
0x1801b4ad7  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x1801b4adc  mov     r13d, eax
0x1801b4adf  test    eax, eax
0x1801b4ae1  jns     short loc_1801B4B0F
0x1801b4ae3  lea     rax, aStrfilepathAss; "strFilePath.Assign"
0x1801b4aea  mov     qword ptr [rsp+1540h+cchWideChar], rax
0x1801b4aef  mov     dword ptr [rsp+1540h+lpWideCharStr], r13d
0x1801b4af4  xor     edx, edx
0x1801b4af6  xor     ecx, ecx
0x1801b4af8  lea     r9d, [rdx+3]
0x1801b4afc  lea     r8d, [rdx+4]
0x1801b4b00  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b4b05  mov     r14, [rsp+1540h+bstrString]
0x1801b4b0a  jmp     loc_1801B545D
0x1801b4b0f  mov     r14, [rsp+1540h+bstrString]
0x1801b4b14  jmp     loc_1801B5466
0x1801b4b19  mov     [rsp+1540h+cchWideChar], 0FFFFFFFFh
0x1801b4b21  mov     dword ptr [rsp+1540h+lpWideCharStr], r14d
0x1801b4b26  xor     r9d, r9d
0x1801b4b29  lea     r8, ?c_szRegSLSBlockNoneMatchHeader@@3QB_WB; "SLSBlockNoneMatchHeader"
0x1801b4b30  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b4b37  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1801b4b3c  test    eax, eax
0x1801b4b3e  setnz   bl
0x1801b4b41  test    eax, eax
0x1801b4b43  jz      short loc_1801B4B66
0x1801b4b45  lea     rax, aSlsblocknonema; "SLSBlockNoneMatchHeader override set."
0x1801b4b4c  mov     qword ptr [rsp+1540h+cchWideChar], rax
0x1801b4b51  mov     [rsp+1540h+lpWideCharStr], r14
0x1801b4b56  xor     edx, edx
0x1801b4b58  xor     ecx, ecx
0x1801b4b5a  lea     r9d, [rdx+4]
0x1801b4b5e  mov     r8d, r9d
0x1801b4b61  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b4b66  mov     qword ptr [rbp+1440h+var_1470.Data1], r14
0x1801b4b6a  mov     [rsp+1540h+var_14DC], r14d
0x1801b4b6f  mov     rsi, r14
0x1801b4b72  mov     [rbp+1440h+var_1448], r14
0x1801b4b76  mov     r13, r14
0x1801b4b79  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801b4b7d  test    bl, bl
0x1801b4b7f  jnz     loc_1801B4C3F
0x1801b4b85  lea     rdx, [rbp+1440h+var_1488]
0x1801b4b89  mov     rcx, [rbp+1440h+var_14A8]
0x1801b4b8d  mov     rcx, [rcx+28h]
0x1801b4b91  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x1801b4b96  xor     ebx, ebx
0x1801b4b98  test    eax, eax
0x1801b4b9a  js      loc_1801B4C41
0x1801b4ba0  mov     rdi, [rbp+1440h+var_1488]
0x1801b4ba4  mov     [rbp+1440h+var_1458], rdi
0x1801b4ba8  test    rdi, rdi
0x1801b4bab  jz      loc_1801B4C41
0x1801b4bb1  mov     r8d, 7FFFFFFFh
0x1801b4bb7  mov     ecx, r8d
0x1801b4bba  mov     rax, rdi
0x1801b4bbd  cmp     [rax], bx
0x1801b4bc0  jz      short loc_1801B4BCC
0x1801b4bc2  add     rax, 2
0x1801b4bc6  sub     rcx, 1
0x1801b4bca  jnz     short loc_1801B4BBD
0x1801b4bcc  mov     rax, rcx
0x1801b4bcf  sub     r8, rcx
0x1801b4bd2  neg     rax
0x1801b4bd5  sbb     rdx, rdx
0x1801b4bd8  and     rdx, r8
0x1801b4bdb  test    rcx, rcx
0x1801b4bde  jz      short loc_1801B4C41
0x1801b4be0  lea     r13, [rdx+11h]
0x1801b4be4  cmp     r13, rdx
0x1801b4be7  jb      short loc_1801B4C3A
0x1801b4be9  mov     edx, 2; unsigned __int64
0x1801b4bee  mov     rcx, r13; unsigned __int64
0x1801b4bf1  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1801b4bf6  mov     rsi, rax
0x1801b4bf9  mov     [rbp+1440h+var_1448], rax
0x1801b4bfd  test    rax, rax
0x1801b4c00  jz      short loc_1801B4C41
0x1801b4c02  mov     [rsp+1540h+lpWideCharStr], rdi
0x1801b4c07  lea     r9, aIfNoneMatch; "If-None-Match: "
0x1801b4c0e  lea     r8, aSS_1; "%s%s"
0x1801b4c15  mov     rdx, r13; unsigned __int64
0x1801b4c18  mov     rcx, rax; Buffer
0x1801b4c1b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b4c20  test    eax, eax
0x1801b4c22  js      short loc_1801B4C41
0x1801b4c24  mov     [rbp+1440h+var_1340], 1
0x1801b4c2e  mov     [rsp+1540h+var_14E0], 1
0x1801b4c33  mov     [rsp+1540h+var_14DC], r13d
0x1801b4c38  jmp     short loc_1801B4C41
0x1801b4c3a  mov     r13, r14
0x1801b4c3d  jmp     short loc_1801B4C41
0x1801b4c3f  xor     ebx, ebx
0x1801b4c41  mov     [rbp+1440h+var_1440], rbx
0x1801b4c45  mov     rax, [rbp+1440h+Str]
0x1801b4c49  xor     ecx, ecx
0x1801b4c4b  test    rax, rax
0x1801b4c4e  jz      loc_1801B4D81
0x1801b4c54  cmp     [rax], cl
0x1801b4c56  jz      loc_1801B4D81
0x1801b4c5c  mov     [rbp+1440h+MultiByteStr], cl
0x1801b4c62  mov     rcx, rax; Str
0x1801b4c65  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x1801b4c6a  mov     rbx, rax
0x1801b4c6d  test    rax, rax
0x1801b4c70  jz      short loc_1801B4C8E
0x1801b4c72  lea     rdx, [rbp+1440h+MultiByteStr]; char *
0x1801b4c79  mov     rcx, rax; this
0x1801b4c7c  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1801b4c81  mov     edx, 90h; struct std::nothrow_t *
0x1801b4c86  mov     rcx, rbx; void *
0x1801b4c89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801b4c8e  mov     edx, 2; unsigned __int64
0x1801b4c93  mov     ecx, 8Ah; unsigned __int64
0x1801b4c98  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1801b4c9d  mov     rbx, rax
0x1801b4ca0  mov     [rbp+1440h+var_1440], rax
0x1801b4ca4  mov     [rbp+1440h+var_14B8], 89h
0x1801b4cac  test    rax, rax
0x1801b4caf  jz      loc_1801B4D85
0x1801b4cb5  mov     [rsp+1540h+cchWideChar], 81h; cchWideChar
0x1801b4cbd  lea     rax, [rbp+1440h+WideCharStr]
0x1801b4cc4  mov     [rsp+1540h+lpWideCharStr], rax; lpWideCharStr
0x1801b4cc9  mov     r9d, r14d; cbMultiByte
0x1801b4ccc  lea     r8, [rbp+1440h+MultiByteStr]; lpMultiByteStr
0x1801b4cd3  mov     edx, 1; dwFlags
0x1801b4cd8  xor     ecx, ecx; CodePage
0x1801b4cda  call    cs:__imp_MultiByteToWideChar
0x1801b4ce0  xor     r14d, r14d
0x1801b4ce3  test    eax, eax
0x1801b4ce5  jnz     short loc_1801B4D0C
0x1801b4ce7  mov     rcx, [rbp+1448h]; this
0x1801b4cee  lea     r8, aCW1SSrcClientL_41; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801b4cf5  lea     edx, [rax+7Fh]; void *
0x1801b4cf8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b4cfd  mov     edx, 89h
0x1801b4d02  mov     [rbp+1440h+var_14B8], rdx
0x1801b4d06  test    eax, eax
0x1801b4d08  js      short loc_1801B4D85
0x1801b4d0a  jmp     short loc_1801B4D11
0x1801b4d0c  mov     edx, 89h; unsigned __int64
0x1801b4d11  mov     [rbp+1440h+var_14B8], rdx
0x1801b4d15  lea     rax, [rbp+1440h+WideCharStr]
0x1801b4d1c  mov     [rsp+1540h+lpWideCharStr], rax
0x1801b4d21  lea     r9, aMsCv_0; "MS-CV: "
0x1801b4d28  lea     r8, aWsWs_1; "%ws%ws"
0x1801b4d2f  mov     rcx, rbx; Buffer
0x1801b4d32  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b4d37  test    eax, eax
0x1801b4d39  js      short loc_1801B4D85
0x1801b4d3b  mov     [rsp+1540h+var_1510], rbx
0x1801b4d40  lea     rax, aMsCvHeaderWs; "MS-CV header: %ws"
0x1801b4d47  mov     qword ptr [rsp+1540h+cchWideChar], rax
0x1801b4d4c  mov     [rsp+1540h+lpWideCharStr], r14
0x1801b4d51  xor     edx, edx
0x1801b4d53  xor     ecx, ecx
0x1801b4d55  lea     r9d, [rdx+5]
0x1801b4d59  lea     r8d, [rdx+4]
0x1801b4d5d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801b4d62  mov     eax, [rsp+1540h+var_14DC]
0x1801b4d66  mov     ecx, 89h
0x1801b4d6b  add     eax, ecx
0x1801b4d6d  test    rsi, rsi
0x1801b4d70  jz      short loc_1801B4D7B
0x1801b4d72  cmp     [rsi], r14w
0x1801b4d76  jz      short loc_1801B4D7B
0x1801b4d78  add     eax, 2
0x1801b4d7b  mov     [rbp+1440h+var_14B8], rcx
0x1801b4d7f  jmp     short loc_1801B4D89
0x1801b4d81  mov     [rbp+1440h+var_14B8], rcx
0x1801b4d85  mov     eax, [rsp+1540h+var_14DC]
0x1801b4d89  lea     ecx, [rax+1]; unsigned __int64
0x1801b4d8c  mov     edx, 2; unsigned __int64
0x1801b4d91  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1801b4d96  mov     r14, rax
0x1801b4d99  mov     [rbp+1440h+lpMem], rax
0x1801b4d9d  test    rsi, rsi
0x1801b4da0  setz    byte ptr [rsp+1540h+var_14DC]
0x1801b4da5  test    rsi, rsi
0x1801b4da8  jz      short loc_1801B4DFE
0x1801b4daa  mov     r9, rsi
0x1801b4dad  lea     r8, aWs_1; "%ws"
0x1801b4db4  mov     rdx, r13; unsigned __int64
0x1801b4db7  mov     rcx, rax; Buffer
0x1801b4dba  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b4dbf  test    eax, eax
0x1801b4dc1  js      short loc_1801B4DFB
0x1801b4dc3  lea     rax, [r14+r13*2]
0x1801b4dc7  mov     [rbp+1440h+var_14A0], rax
0x1801b4dcb  xor     r13d, r13d
0x1801b4dce  test    rbx, rbx
0x1801b4dd1  jz      short loc_1801B4E04
0x1801b4dd3  lea     r9, asc_1802AB98C; "\r\n"
0x1801b4dda  lea     r8, aWs_1; "%ws"
0x1801b4de1  lea     edx, [r13+2]; unsigned __int64
0x1801b4de5  mov     rcx, rax; Buffer
0x1801b4de8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b4ded  test    eax, eax
0x1801b4def  mov     rax, [rbp+1440h+var_14A0]
0x1801b4df3  js      short loc_1801B4E01
0x1801b4df5  add     rax, 4
0x1801b4df9  jmp     short loc_1801B4E01
  ... truncated ...
```
