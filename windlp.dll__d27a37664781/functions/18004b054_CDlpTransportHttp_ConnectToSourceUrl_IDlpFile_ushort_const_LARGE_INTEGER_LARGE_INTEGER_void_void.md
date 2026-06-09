# CDlpTransportHttp::ConnectToSourceUrl(IDlpFile *,ushort const *,_LARGE_INTEGER *,_LARGE_INTEGER *,void * *,void * *)

- ea: `0x18004b054`
- end: `0x18004c070`
- name: `?ConnectToSourceUrl@CDlpTransportHttp@@AEAAJPEAVIDlpFile@@PEBGPEAT_LARGE_INTEGER@@2PEAPEAX3@Z`
- size: `4124`
- prototype: `__int64 __fastcall(CDlpTransportHttp *__hidden this, struct IDlpFile *, const unsigned __int16 *, union _LARGE_INTEGER *, union _LARGE_INTEGER *, void **, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006aecc`
- `0x1800787fc`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001fd60`
- `0x180028640`
- `0x180049628`
- `0x18004b054`
- `0x18007ec9a`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b38f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b3de`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b38f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004b3de`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b63e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b64d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b65e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b63e`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b64d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b65e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004b468`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004b468`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b67b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bfa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b67b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bfa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bfb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b689`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bfb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b53e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004baed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bdc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004beb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b53e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b9b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004baed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bdc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004beb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf0c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b5eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b5fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b60d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b61c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b62f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b5eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b5fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b60d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b61c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004b62f`
- `WINHTTP!WinHttpOpenRequest` at `0x18004bad7`
- `WINHTTP!WinHttpOpenRequest` at `0x18004bad7`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004bdbf`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004bdbf`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004be38`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004be38`
- `WINHTTP!WinHttpSetOption` at `0x18004b8a3`
- `WINHTTP!WinHttpSetOption` at `0x18004b9a8`
- `WINHTTP!WinHttpSetOption` at `0x18004b8a3`
- `WINHTTP!WinHttpSetOption` at `0x18004b9a8`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b4a7`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b521`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b5cd`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b5dc`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b4a7`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b521`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b5cd`
- `WINHTTP!WinHttpCloseHandle` at `0x18004b5dc`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18004b6f9`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18004b6f9`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18004b868`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18004b868`
- `WINHTTP!WinHttpSendRequest` at `0x18004bea6`
- `WINHTTP!WinHttpSendRequest` at `0x18004bea6`
- `WINHTTP!WinHttpConnect` at `0x18004ba35`
- `WINHTTP!WinHttpConnect` at `0x18004ba35`
- `WINHTTP!WinHttpOpen` at `0x18004b505`
- `WINHTTP!WinHttpOpen` at `0x18004b505`
- `WINHTTP!WinHttpCrackUrl` at `0x18004b2d7`
- `WINHTTP!WinHttpCrackUrl` at `0x18004b2d7`
- `WINHTTP!WinHttpReceiveResponse` at `0x18004bf02`
- `WINHTTP!WinHttpReceiveResponse` at `0x18004bf02`

## string_xrefs

- `0x18004b776`: `ConnectToSourceUrl: IE specifies auto-config URL.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDlpTransportHttp::ConnectToSourceUrl(
        CDlpTransportHttp *this,
        struct IDlpFile *a2,
        const unsigned __int16 *a3,
        union _LARGE_INTEGER *a4,
        union _LARGE_INTEGER *a5,
        void **a6,
        void **a7)
{
  WCHAR *v7; // rdi
  WCHAR *v8; // r14
  WCHAR *lpszProxy; // r12
  LPWSTR v10; // rbx
  LPWSTR lpszProxyBypass; // r13
  void *v12; // r15
  void *v13; // rsi
  signed int LastError; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r10
  __int64 v19; // rcx
  const wchar_t *v20; // rax
  BSTR v21; // rax
  BSTR v22; // rax
  CDlpTransportHttp *v23; // rax
  const WCHAR *v24; // rcx
  bool v25; // zf
  __int64 v26; // rcx
  void *v27; // rcx
  HINTERNET v28; // rbx
  void *v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  unsigned __int16 *v33; // rbx
  HANDLE v34; // rax
  int v36; // ecx
  LPWSTR lpszAutoConfigUrl; // rdx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  DWORD v41; // eax
  __int64 v42; // rcx
  DWORD v43; // eax
  __int64 v44; // rcx
  void *v45; // rax
  void *v46; // rax
  LONGLONG QuadPart; // r8
  __int64 v48; // rbx
  LONGLONG v49; // rcx
  unsigned int v50; // edx
  unsigned int v51; // edx
  __int64 v52; // rcx
  unsigned int v53; // edx
  unsigned int v54; // edx
  __int64 v55; // rcx
  CDlpTransportHttp *v56; // rbx
  __int64 v57; // rcx
  __int64 v58; // rcx
  void *v59; // rbx
  HANDLE ProcessHeap; // rax
  int StringCch; // eax
  __int64 v62; // rcx
  int Internal; // eax
  PCNZWCH lpString2; // [rsp+28h] [rbp-E0h]
  int cchCount2[2]; // [rsp+30h] [rbp-D8h]
  LPWSTR v66; // [rsp+48h] [rbp-C0h]
  __int64 v67; // [rsp+50h] [rbp-B8h] BYREF
  void *v68; // [rsp+58h] [rbp-B0h]
  LPCWSTR pwszUrl; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 *pAutoProxyOptions; // [rsp+68h] [rbp-A0h] BYREF
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions_8; // [rsp+70h] [rbp-98h] BYREF
  HGLOBAL hMem; // [rsp+90h] [rbp-78h]
  HGLOBAL v73; // [rsp+98h] [rbp-70h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+A0h] [rbp-68h] BYREF
  BSTR v75; // [rsp+B8h] [rbp-50h]
  BSTR v76; // [rsp+C0h] [rbp-48h]
  void *v77; // [rsp+C8h] [rbp-40h]
  void *v78; // [rsp+D0h] [rbp-38h]
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+D8h] [rbp-30h] BYREF
  LPWSTR v80; // [rsp+F8h] [rbp-10h]
  LPWSTR v81; // [rsp+100h] [rbp-8h]
  void *v82; // [rsp+108h] [rbp+0h]
  __int64 v83; // [rsp+110h] [rbp+8h]
  __int64 v84; // [rsp+118h] [rbp+10h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+128h] [rbp+20h] BYREF
  int v88; // [rsp+1F0h] [rbp+E8h]
  int v89; // [rsp+1F0h] [rbp+E8h]
  _QWORD *v90; // [rsp+1F0h] [rbp+E8h]

  pAutoProxyOptions = 0;
  pwszUrl = 0;
  v7 = 0;
  v75 = 0;
  v8 = 0;
  v76 = 0;
  v83 = 0;
  v84 = -1;
  v73 = 0;
  lpszProxy = 0;
  v80 = 0;
  hMem = 0;
  v10 = 0;
  v66 = 0;
  lpszProxyBypass = 0;
  v81 = 0;
  v12 = 0;
  v77 = 0;
  v13 = 0;
  v78 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  memset(&pAutoProxyOptions_8, 0, sizeof(pAutoProxyOptions_8));
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( !a2 )
  {
    LastError = -2147024809;
    v88 = -2147024809;
    v15 = *((_QWORD *)this + 12);
    if ( !v15 )
      goto LABEL_68;
    cchCount2[0] = -2147024809;
    LODWORD(lpString2) = 445;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    LastError = -2147024809;
    v88 = -2147024809;
    v15 = *((_QWORD *)this + 12);
    if ( !v15 )
      goto LABEL_68;
    cchCount2[0] = -2147024809;
    LODWORD(lpString2) = 446;
    goto LABEL_4;
  }
  if ( a4 )
  {
    if ( !a5 )
    {
LABEL_12:
      LastError = -2147024809;
      v88 = -2147024809;
      v15 = *((_QWORD *)this + 12);
      if ( !v15 )
        goto LABEL_68;
      cchCount2[0] = -2147024809;
      LODWORD(lpString2) = 448;
      goto LABEL_4;
    }
  }
  else if ( a5 )
  {
    goto LABEL_12;
  }
  if ( !a6 )
  {
    LastError = -2147024809;
    v88 = -2147024809;
    v15 = *((_QWORD *)this + 12);
    if ( !v15 )
      goto LABEL_68;
    cchCount2[0] = -2147024809;
    LODWORD(lpString2) = 449;
    goto LABEL_4;
  }
  if ( !a7 )
  {
    LastError = -2147024809;
    v88 = -2147024809;
    v15 = *((_QWORD *)this + 12);
    if ( !v15 )
      goto LABEL_68;
    cchCount2[0] = -2147024809;
    LODWORD(lpString2) = 450;
    goto LABEL_4;
  }
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  LastError = (*(__int64 (__fastcall **)(struct IDlpFile *, LPCWSTR *))(*(_QWORD *)a2 + 48LL))(a2, &pwszUrl);
  v88 = LastError;
  if ( LastError < 0 )
  {
    v15 = *((_QWORD *)this + 12);
    if ( !v15 )
      goto LABEL_68;
    cchCount2[0] = LastError;
    LODWORD(lpString2) = 459;
    goto LABEL_4;
  }
  if ( WinHttpCrackUrl(pwszUrl, 0, 0, &UrlComponents) )
  {
    v89 = UrlComponents.nScheme == INTERNET_SCHEME_GOPHER;
    v19 = *((_QWORD *)this + 12);
    if ( v19 )
    {
      v20 = L"TRUE";
      if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER )
        v20 = L"FALSE";
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v19,
        2,
        L"ConnectToSourceUrl: Port: [%d], Secure -> [%s]",
        UrlComponents.nPort,
        v20);
    }
    v21 = SysAllocStringLen((const OLECHAR *)UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
    v7 = v21;
    if ( !v21 )
    {
      v75 = 0;
      LastError = -2147024882;
      v88 = -2147024882;
      v15 = *((_QWORD *)this + 12);
      if ( !v15 )
        goto LABEL_68;
      cchCount2[0] = -2147024882;
      LODWORD(lpString2) = 473;
      goto LABEL_4;
    }
    v75 = v21;
    v22 = SysAllocStringLen((const OLECHAR *)UrlComponents.lpszUrlPath, UrlComponents.dwUrlPathLength);
    v8 = v22;
    if ( !v22 )
    {
      v76 = 0;
      LastError = -2147024882;
      v88 = -2147024882;
      v15 = *((_QWORD *)this + 12);
      if ( !v15 )
        goto LABEL_68;
      cchCount2[0] = -2147024882;
      LODWORD(lpString2) = 476;
      goto LABEL_4;
    }
    v76 = v22;
    v23 = this;
    if ( !*((_QWORD *)this + 68) )
      goto LABEL_54;
    v24 = (const WCHAR *)*((_QWORD *)this + 70);
    if ( v24 )
    {
      v25 = CompareStringW(0x409u, 1u, v7, -1, v24, -1) == 2;
      v26 = *((_QWORD *)this + 12);
      if ( v25 )
      {
        if ( v26 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v26, 1, L"ConnectToSourceUrl: Using existing WinHttp connection...");
        v23 = this;
      }
      else
      {
        if ( v26 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v26, 1, L"ConnectToSourceUrl: Refreshing WinHttp connection...");
        v23 = this;
        v27 = (void *)*((_QWORD *)this + 68);
        if ( v27 )
        {
          WinHttpCloseHandle(v27);
          v23 = this;
          *((_QWORD *)this + 68) = 0;
        }
      }
    }
    if ( !*((_QWORD *)v23 + 68) )
    {
LABEL_54:
      v28 = WinHttpOpen(L"Windows Dlp Manager", 1u, 0, 0, 0);
      v23 = this;
      v29 = (void *)*((_QWORD *)this + 68);
      if ( v29 )
      {
        WinHttpCloseHandle(v29);
        v23 = this;
      }
      if ( !v28 )
      {
        *((_QWORD *)v23 + 68) = 0;
        LastError = GetLastError();
        v88 = LastError;
        if ( LastError )
        {
          if ( LastError <= 0 )
            goto LABEL_62;
          LastError = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          LastError = -2147467259;
        }
        v88 = LastError;
LABEL_62:
        if ( *((_QWORD *)this + 12) )
        {
          cchCount2[0] = LastError;
          LODWORD(lpString2) = 506;
          v30 = *((_QWORD *)this + 12);
LABEL_64:
          v31 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v30,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpTransportHttp::ConnectToSourceUrl",
                  lpString2,
                  *(_QWORD *)cchCount2);
          v32 = (unsigned int)v31;
          if ( v31 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v31);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v32);
          LastError = v88;
          goto LABEL_67;
        }
        goto LABEL_67;
      }
      *((_QWORD *)v23 + 68) = v28;
      *((_DWORD *)v23 + 142) = 0;
      v10 = 0;
    }
    if ( *((_DWORD *)v23 + 142) )
      goto LABEL_139;
    memset(&pProxyInfo, 0, sizeof(pProxyInfo));
    memset(&pAutoProxyOptions_8, 0, sizeof(pAutoProxyOptions_8));
    memset(&pProxyConfig, 0, sizeof(pProxyConfig));
    if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
    {
      v36 = 0;
      lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      v73 = pProxyConfig.lpszAutoConfigUrl;
      lpszProxy = pProxyConfig.lpszProxy;
      v80 = pProxyConfig.lpszProxy;
      hMem = pProxyConfig.lpszProxyBypass;
      if ( pProxyConfig.fAutoDetect )
      {
        v38 = *((_QWORD *)this + 12);
        if ( v38 )
        {
          CDlpLogT<CEmptyType>::DlpLogFormat(v38, 2, L"ConnectToSourceUrl: IE specifies auto-detect.");
          lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
        }
        *(_QWORD *)&pAutoProxyOptions_8.dwFlags = 0x300000001LL;
        pAutoProxyOptions_8.fAutoLogonIfChallenged = 1;
        v36 = 1;
      }
      if ( lpszAutoConfigUrl )
      {
        v39 = *((_QWORD *)this + 12);
        if ( v39 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v39, 2, L"ConnectToSourceUrl: IE specifies auto-config URL.");
        pAutoProxyOptions_8.dwFlags |= 2u;
        pAutoProxyOptions_8.lpszAutoConfigUrl = (LPCWSTR)v73;
        pAutoProxyOptions_8.fAutoLogonIfChallenged = 1;
        v36 = 1;
LABEL_109:
        v23 = this;
        if ( !*((_DWORD *)this + 142) )
        {
          if ( v36 )
          {
            v42 = *((_QWORD *)this + 12);
            if ( v42 )
            {
              CDlpLogT<CEmptyType>::DlpLogFormat(v42, 2, L"ConnectToSourceUrl: Trying auto-detect...");
              v23 = this;
            }
            v25 = !WinHttpGetProxyForUrl(*((HINTERNET *)v23 + 69), pwszUrl, &pAutoProxyOptions_8, &pProxyInfo);
            v23 = this;
            if ( v25 )
            {
              if ( *((_QWORD *)this + 12) )
              {
                v43 = GetLastError();
                CDlpLogT<CEmptyType>::DlpLogFormat(
                  *((_QWORD *)this + 12),
                  3,
                  L"ConnectToSourceUrl: Unable to retrieve proxy info for URL -> [0x%x].",
                  v43);
                v23 = this;
              }
            }
            else
            {
              v10 = pProxyInfo.lpszProxy;
              v66 = pProxyInfo.lpszProxy;
              lpszProxyBypass = pProxyInfo.lpszProxyBypass;
              v81 = pProxyInfo.lpszProxyBypass;
              if ( !WinHttpSetOption(*((HINTERNET *)this + 68), 0x26u, &pProxyInfo, 0x18u) )
              {
                LastError = GetLastError();
                v88 = LastError;
                if ( LastError )
                {
                  if ( LastError <= 0 )
                  {
LABEL_120:
                    v18 = *((_QWORD *)this + 12);
                    if ( !v18 )
                      goto LABEL_68;
                    cchCount2[0] = LastError;
                    LODWORD(lpString2) = 602;
                    goto LABEL_32;
                  }
                  LastError = (unsigned __int16)LastError | 0x80070000;
                }
                else
                {
                  LastError = -2147467259;
                }
                v88 = LastError;
                goto LABEL_120;
              }
              v23 = this;
              *((_DWORD *)this + 142) = 1;
            }
          }
          if ( !*((_DWORD *)v23 + 142) && lpszProxy )
          {
            v44 = *((_QWORD *)v23 + 12);
            if ( v44 )
            {
              CDlpLogT<CEmptyType>::DlpLogFormat(v44, 2, L"ConnectToSourceUrl: Using IE proxy settings...");
              v23 = this;
            }
            pProxyInfo.dwAccessType = 3;
            pProxyInfo.lpszProxy = lpszProxy;
            pProxyInfo.lpszProxyBypass = (LPWSTR)hMem;
            if ( !WinHttpSetOption(*((HINTERNET *)v23 + 68), 0x26u, &pProxyInfo, 0x18u) )
            {
              LastError = GetLastError();
              v88 = LastError;
              if ( LastError )
              {
                if ( LastError <= 0 )
                {
LABEL_135:
                  v18 = *((_QWORD *)this + 12);
                  if ( !v18 )
                    goto LABEL_68;
                  cchCount2[0] = LastError;
                  LODWORD(lpString2) = 628;
                  goto LABEL_32;
                }
                LastError = (unsigned __int16)LastError | 0x80070000;
              }
              else
              {
                LastError = -2147467259;
              }
              v88 = LastError;
              goto LABEL_135;
            }
            v23 = this;
            *((_DWORD *)this + 142) = 1;
          }
        }
        *((_DWORD *)v23 + 142) = 1;
LABEL_139:
        v45 = WinHttpConnect(*((HINTERNET *)v23 + 68), v7, UrlComponents.nPort, 0);
        v82 = v45;
        if ( !v45 )
        {
          v12 = 0;
          v77 = 0;
          LastError = GetLastError();
          v88 = LastError;
          if ( LastError )
          {
            if ( LastError <= 0 )
            {
LABEL_145:
              v18 = *((_QWORD *)this + 12);
              if ( !v18 )
                goto LABEL_68;
              cchCount2[0] = LastError;
              LODWORD(lpString2) = 646;
              goto LABEL_32;
            }
            LastError = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            LastError = -2147467259;
          }
          v88 = LastError;
          goto LABEL_145;
        }
        v12 = v45;
        v77 = v45;
        v46 = WinHttpOpenRequest(v45, a3, v8, 0, 0, 0, v89 << 23);
        v68 = v46;
        if ( !v46 )
        {
          v13 = 0;
          v78 = 0;
          LastError = GetLastError();
          v88 = LastError;
          if ( LastError )
          {
            if ( LastError <= 0 )
            {
LABEL_153:
              v18 = *((_QWORD *)this + 12);
              if ( !v18 )
                goto LABEL_68;
              cchCount2[0] = LastError;
              LODWORD(lpString2) = 657;
              goto LABEL_32;
            }
            LastError = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            LastError = -2147467259;
          }
          v88 = LastError;
          goto LABEL_153;
        }
        v13 = v46;
        v78 = v46;
        if ( !a4 )
        {
          v56 = this;
          goto LABEL_204;
        }
        QuadPart = a4->QuadPart;
        if ( !a5 )
        {
          LastError = STRAPI_Format(&pAutoProxyOptions, L"Range: bytes=%I64u-", QuadPart);
          v88 = LastError;
          if ( LastError < 0 )
          {
            v15 = *((_QWORD *)this + 12);
            if ( v15 )
            {
              cchCount2[0] = LastError;
              LODWORD(lpString2) = 675;
              goto LABEL_4;
            }
            goto LABEL_67;
          }
LABEL_191:
          v56 = this;
          v57 = *((_QWORD *)this + 12);
          if ( v57 )
            CDlpLogT<CEmptyType>::DlpLogFormat(v57, 2, L"ConnectToSourceUrl: Requesting -> [%s]", pAutoProxyOptions);
          if ( !WinHttpAddRequestHeaders(v13, pAutoProxyOptions, 0xFFFFFFFF, 0xA0000000) )
          {
            LastError = GetLastError();
            v88 = LastError;
            if ( LastError )
            {
              if ( LastError <= 0 )
              {
LABEL_199:
                if ( !*((_QWORD *)this + 12) )
                  goto LABEL_67;
                cchCount2[0] = LastError;
                LODWORD(lpString2) = 683;
LABEL_201:
                v30 = *((_QWORD *)v56 + 12);
                goto LABEL_64;
              }
              LastError = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              LastError = -2147467259;
            }
            v88 = LastError;
            goto LABEL_199;
          }
          v46 = v13;
LABEL_204:
          if ( !WinHttpSetTimeouts(v46, 120000, 120000, 120000, 120000) )
          {
            LastError = GetLastError();
            v88 = LastError;
            if ( LastError )
            {
              if ( LastError <= 0 )
              {
LABEL_210:
                if ( !*((_QWORD *)v56 + 12) )
                  goto LABEL_67;
                cchCount2[0] = LastError;
                LODWORD(lpString2) = 692;
                goto LABEL_201;
              }
              LastError = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              LastError = -2147467259;
            }
            v88 = LastError;
            goto LABEL_210;
          }
          if ( !WinHttpSendRequest(v13, 0, 0, 0, 0, 0, 0) )
          {
            LastError = GetLastError();
            v88 = LastError;
            if ( LastError )
            {
              if ( LastError <= 0 )
              {
LABEL_218:
                if ( !*((_QWORD *)v56 + 12) )
                  goto LABEL_67;
                cchCount2[0] = LastError;
                LODWORD(lpString2) = 702;
                goto LABEL_201;
              }
              LastError = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              LastError = -2147467259;
            }
            v88 = LastError;
            goto LABEL_218;
          }
          if ( WinHttpReceiveResponse(v13, 0) )
          {
            LastError = CDlpTransportHttp::CheckHttpRequestStatus(v56, v13);
            v88 = LastError;
            if ( LastError >= 0 )
            {
              v90 = (_QWORD *)((char *)v56 + 560);
              v58 = *((_QWORD *)v56 + 70);
              if ( v58 )
              {
                v59 = (void *)(v58 - 4);
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v59);
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                *v90 = 0;
                v56 = this;
              }
              LODWORD(v67) = 0;
              StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v7, &v67);
              v62 = (unsigned int)StringCch;
              v88 = StringCch;
              if ( StringCch < 0
                || (Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v7),
                    v62 = (unsigned int)Internal,
                    v88 = Internal,
                    Internal < 0) )
              {
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v62);
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v62);
              LastError = v88;
              if ( v88 >= 0 )
              {
                v12 = 0;
                *a6 = v82;
                v13 = 0;
                *a7 = v68;
              }
              else
              {
                v30 = *((_QWORD *)v56 + 12);
                if ( v30 )
                {
                  cchCount2[0] = v88;
                  LODWORD(lpString2) = 716;
                  goto LABEL_64;
                }
              }
            }
            else
            {
              v30 = *((_QWORD *)v56 + 12);
              if ( v30 )
              {
                cchCount2[0] = LastError;
                LODWORD(lpString2) = 711;
                goto LABEL_64;
              }
            }
            goto LABEL_67;
          }
          LastError = GetLastError();
          v88 = LastError;
          if ( LastError )
          {
            if ( LastError <= 0 )
            {
LABEL_226:
              if ( !*((_QWORD *)v56 + 12) )
                goto LABEL_67;
              cchCount2[0] = LastError;
              LODWORD(lpString2) = 707;
              goto LABEL_201;
            }
            LastError = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            LastError = -2147467259;
          }
          v88 = LastError;
          goto LABEL_226;
        }
        v48 = 0;
        if ( QuadPart < 0 || (v49 = a5->QuadPart, a5->QuadPart < 0) )
        {
          v88 = -2147024809;
          v52 = 2147942487LL;
        }
        else
        {
          v67 = v49 + QuadPart;
          if ( v49 + QuadPart < (unsigned __int64)QuadPart )
          {
            v67 = 0;
            v88 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v50 = 0;
            v88 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v50);
          v51 = v88;
          if ( v88 >= 0 )
          {
            if ( v67 >= 0 )
            {
              v48 = v67;
              goto LABEL_169;
            }
            v52 = 2147942934LL;
            v88 = -2147024362;
          }
          else
          {
            v52 = (unsigned int)v88;
          }
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v52);
LABEL_169:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v51);
        LastError = v88;
        if ( v88 < 0 )
        {
          v30 = *((_QWORD *)this + 12);
          if ( v30 )
          {
            cchCount2[0] = v88;
            LODWORD(lpString2) = 663;
            goto LABEL_64;
          }
LABEL_67:
          v10 = v66;
          goto LABEL_68;
        }
        if ( !a5->QuadPart )
          goto LABEL_185;
        v67 = v48 - 1;
        if ( v48 )
        {
          v53 = 0;
          v88 = 0;
        }
        else
        {
          v67 = 0;
          v88 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v53);
        v54 = v88;
        if ( v88 >= 0 )
        {
          if ( v67 >= 0 )
          {
            v48 = v67;
            goto LABEL_182;
          }
          v88 = -2147024362;
          v55 = 2147942934LL;
        }
        else
        {
          v55 = (unsigned int)v88;
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v55);
LABEL_182:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v54);
        LastError = v88;
        if ( v88 < 0 )
        {
          v30 = *((_QWORD *)this + 12);
          if ( v30 )
          {
            cchCount2[0] = v88;
            LODWORD(lpString2) = 666;
            goto LABEL_64;
          }
          goto LABEL_67;
        }
LABEL_185:
        LastError = STRAPI_Format(&pAutoProxyOptions, L"Range: bytes=%I64u-%I64u", a4->QuadPart, v48);
        v88 = LastError;
        if ( LastError < 0 )
        {
          v30 = *((_QWORD *)this + 12);
          if ( v30 )
          {
            cchCount2[0] = LastError;
            LODWORD(lpString2) = 670;
            goto LABEL_64;
          }
          goto LABEL_67;
        }
        goto LABEL_191;
      }
      if ( v36 || lpszProxy )
        goto LABEL_109;
      v40 = *((_QWORD *)this + 12);
      if ( v40 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v40, 2, L"ConnectToSourceUrl: No IE proxy settings.");
    }
    else if ( *((_QWORD *)this + 12) )
    {
      v41 = GetLastError();
      CDlpLogT<CEmptyType>::DlpLogFormat(
        *((_QWORD *)this + 12),
        3,
        L"ConnectToSourceUrl: Unable to retrieve IE proxy settings -> [0x%x].",
        v41);
    }
    v36 = 1;
    pAutoProxyOptions_8.fAutoLogonIfChallenged = 1;
    *(_QWORD *)&pAutoProxyOptions_8.dwFlags = 0x300000001LL;
    goto LABEL_109;
  }
  LastError = GetLastError();
  v88 = LastError;
  if ( !LastError )
  {
    LastError = -2147467259;
LABEL_29:
    v88 = LastError;
    goto LABEL_30;
  }
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_29;
  }
LABEL_30:
  v18 = *((_QWORD *)this + 12);
  if ( !v18 )
    goto LABEL_68;
  cchCount2[0] = LastError;
  LODWORD(lpString2) = 463;
LABEL_32:
  v15 = v18;
LABEL_4:
  v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v15,
          4,
          L"%s(%d): Result = 0x%X",
          L"CDlpTransportHttp::ConnectToSourceUrl",
          lpString2,
          *(_QWORD *)cchCount2);
  v17 = (unsigned int)v16;
  if ( v16 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
  LastError = v88;
LABEL_68:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)LastError);
  if ( v13 )
    WinHttpCloseHandle(v13);
  if ( v12 )
    WinHttpCloseHandle(v12);
  if ( lpszProxyBypass )
    GlobalFree(lpszProxyBypass);
  if ( v10 )
    GlobalFree(v10);
  if ( hMem )
    GlobalFree(hMem);
  if ( lpszProxy )
    GlobalFree(lpszProxy);
  if ( v73 )
    GlobalFree(v73);
  if ( v8 )
    SysFreeString(v8);
  if ( v7 )
    SysFreeString(v7);
  if ( pwszUrl )
  {
    SysFreeString((BSTR)pwszUrl);
    pwszUrl = 0;
  }
  if ( pAutoProxyOptions )
  {
    v33 = pAutoProxyOptions - 2;
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v88;
}

```

## disassembly

```asm
0x18004b054  mov     rax, rsp
0x18004b057  mov     [rax+20h], r9
0x18004b05b  mov     [rax+18h], r8
0x18004b05f  mov     [rax+10h], rdx
0x18004b063  mov     [rax+8], rcx
0x18004b067  push    rbp
0x18004b068  push    rbx
0x18004b069  push    rsi
0x18004b06a  push    rdi
0x18004b06b  push    r12
0x18004b06d  push    r13
0x18004b06f  push    r14
0x18004b071  push    r15
0x18004b073  lea     rbp, [rax-0D8h]
0x18004b07a  sub     rsp, 198h
0x18004b081  xor     eax, eax
0x18004b083  mov     qword ptr [rsp+1D0h+pAutoProxyOptions.dwFlags], rax
0x18004b088  mov     [rsp+1D0h+pwszUrl], rax
0x18004b08d  mov     edi, eax
0x18004b08f  mov     [rbp+0D0h+var_120], rax
0x18004b093  mov     r14d, eax
0x18004b096  mov     [rbp+0D0h+var_118], rax
0x18004b09a  mov     [rbp+0D0h+var_C8], rax
0x18004b09e  mov     [rbp+0D0h+var_C0], 0FFFFFFFFFFFFFFFFh
0x18004b0a6  mov     [rbp+0D0h+var_140], rax
0x18004b0aa  mov     r12d, eax
0x18004b0ad  mov     [rbp+0D0h+var_E0], rax
0x18004b0b1  mov     [rbp+0D0h+hMem], rax
0x18004b0b5  mov     ebx, eax
0x18004b0b7  mov     [rsp+1D0h+var_190], rax
0x18004b0bc  mov     r13d, eax
0x18004b0bf  mov     [rbp+0D0h+var_D8], rax
0x18004b0c3  mov     r15d, eax
0x18004b0c6  mov     [rbp+0D0h+var_110], rax
0x18004b0ca  mov     esi, eax
0x18004b0cc  mov     [rbp+0D0h+var_108], rax
0x18004b0d0  xor     edx, edx; Val
0x18004b0d2  lea     r8d, [rax+68h]; Size
0x18004b0d6  lea     rcx, [rbp+0D0h+UrlComponents]; void *
0x18004b0da  call    memset_0
0x18004b0df  xorps   xmm0, xmm0
0x18004b0e2  xor     eax, eax
0x18004b0e4  movups  xmmword ptr [rbp+0D0h+pProxyInfo.dwAccessType], xmm0
0x18004b0e8  mov     [rbp+0D0h+pProxyInfo.lpszProxyBypass], rax
0x18004b0ec  xorps   xmm1, xmm1
0x18004b0ef  movups  xmmword ptr [rsp+1D0h+pAutoProxyOptions.lpszAutoConfigUrl], xmm1
0x18004b0f4  movups  xmmword ptr [rsp+1D0h+pAutoProxyOptions.dwReserved], xmm1
0x18004b0f9  movups  xmmword ptr [rbp+0D0h+pProxyConfig.fAutoDetect], xmm0
0x18004b0fd  movups  xmmword ptr [rbp+0D0h+pProxyConfig.lpszProxy], xmm0
0x18004b101  mov     rcx, [rbp+0D0h+arg_8]
0x18004b108  xor     edx, edx
0x18004b10a  test    rcx, rcx
0x18004b10d  jnz     short loc_18004B172
0x18004b10f  mov     r8d, 80070057h
0x18004b115  mov     eax, r8d
0x18004b118  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b11e  mov     rcx, [rbp+0D0h+arg_0]
0x18004b125  mov     rcx, [rcx+60h]
0x18004b129  test    rcx, rcx
0x18004b12c  jz      loc_18004B5BD
0x18004b132  mov     [rsp+1D0h+cchCount2], r8d
0x18004b137  mov     dword ptr [rsp+1D0h+lpString2], 1BDh
0x18004b13f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004b146  lea     r9, aCdlptransporth_3; "CDlpTransportHttp::ConnectToSourceUrl"
0x18004b14d  mov     edx, 4
0x18004b152  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004b157  test    eax, eax
0x18004b159  mov     ecx, eax
0x18004b15b  jns     short loc_18004B162
0x18004b15d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004b162  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004b167  mov     eax, dword ptr [rbp+0D0h+arg_8]
0x18004b16d  jmp     loc_18004B5BD
0x18004b172  cmp     [rbp+0D0h+pwszVerb], rdx
0x18004b179  jnz     short loc_18004B1AD
0x18004b17b  mov     r8d, 80070057h
0x18004b181  mov     eax, r8d
0x18004b184  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b18a  mov     rcx, [rbp+0D0h+arg_0]
0x18004b191  mov     rcx, [rcx+60h]
0x18004b195  test    rcx, rcx
0x18004b198  jz      loc_18004B5BD
0x18004b19e  mov     [rsp+1D0h+cchCount2], r8d
0x18004b1a3  mov     dword ptr [rsp+1D0h+lpString2], 1BEh
0x18004b1ab  jmp     short loc_18004B13F
0x18004b1ad  cmp     [rbp+0D0h+arg_18], rax
0x18004b1b4  jz      short loc_18004B1F4
0x18004b1b6  cmp     [rbp+0D0h+arg_20], rax
0x18004b1bd  jnz     short loc_18004B1FD
0x18004b1bf  mov     r8d, 80070057h
0x18004b1c5  mov     eax, r8d
0x18004b1c8  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b1ce  mov     rcx, [rbp+0D0h+arg_0]
0x18004b1d5  mov     rcx, [rcx+60h]
0x18004b1d9  test    rcx, rcx
0x18004b1dc  jz      loc_18004B5BD
0x18004b1e2  mov     [rsp+1D0h+cchCount2], r8d
0x18004b1e7  mov     dword ptr [rsp+1D0h+lpString2], 1C0h
0x18004b1ef  jmp     loc_18004B13F
0x18004b1f4  cmp     [rbp+0D0h+arg_20], rax
0x18004b1fb  jnz     short loc_18004B1BF
0x18004b1fd  cmp     [rbp+0D0h+arg_28], rdx
0x18004b204  jnz     short loc_18004B23B
0x18004b206  mov     r8d, 80070057h
0x18004b20c  mov     eax, r8d
0x18004b20f  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b215  mov     rcx, [rbp+0D0h+arg_0]
0x18004b21c  mov     rcx, [rcx+60h]
0x18004b220  test    rcx, rcx
0x18004b223  jz      loc_18004B5BD
0x18004b229  mov     [rsp+1D0h+cchCount2], r8d
0x18004b22e  mov     dword ptr [rsp+1D0h+lpString2], 1C1h
0x18004b236  jmp     loc_18004B13F
0x18004b23b  cmp     [rbp+0D0h+arg_30], rdx
0x18004b242  jnz     short loc_18004B279
0x18004b244  mov     r8d, 80070057h
0x18004b24a  mov     eax, r8d
0x18004b24d  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b253  mov     rcx, [rbp+0D0h+arg_0]
0x18004b25a  mov     rcx, [rcx+60h]
0x18004b25e  test    rcx, rcx
0x18004b261  jz      loc_18004B5BD
0x18004b267  mov     [rsp+1D0h+cchCount2], r8d
0x18004b26c  mov     dword ptr [rsp+1D0h+lpString2], 1C2h
0x18004b274  jmp     loc_18004B13F
0x18004b279  mov     [rbp+0D0h+UrlComponents.dwStructSize], 68h ; 'h'
0x18004b280  or      eax, 0FFFFFFFFh
0x18004b283  mov     [rbp+0D0h+UrlComponents.dwHostNameLength], eax
0x18004b286  mov     [rbp+0D0h+UrlComponents.dwUrlPathLength], eax
0x18004b289  mov     rax, [rcx]
0x18004b28c  lea     rdx, [rsp+1D0h+pwszUrl]
0x18004b291  mov     rax, [rax+30h]
0x18004b295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b29a  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b2a0  test    eax, eax
0x18004b2a2  jns     short loc_18004B2C9
0x18004b2a4  mov     rcx, [rbp+0D0h+arg_0]
0x18004b2ab  mov     rcx, [rcx+60h]
0x18004b2af  test    rcx, rcx
0x18004b2b2  jz      loc_18004B5BD
0x18004b2b8  mov     [rsp+1D0h+cchCount2], eax
0x18004b2bc  mov     dword ptr [rsp+1D0h+lpString2], 1CBh
0x18004b2c4  jmp     loc_18004B13F
0x18004b2c9  lea     r9, [rbp+0D0h+UrlComponents]; lpUrlComponents
0x18004b2cd  xor     r8d, r8d; dwFlags
0x18004b2d0  xor     edx, edx; dwUrlLength
0x18004b2d2  mov     rcx, [rsp+1D0h+pwszUrl]; pwszUrl
0x18004b2d7  call    cs:__imp_WinHttpCrackUrl
0x18004b2dd  test    eax, eax
0x18004b2df  jnz     short loc_18004B33A
0x18004b2e1  call    cs:__imp_GetLastError
0x18004b2e7  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b2ed  test    eax, eax
0x18004b2ef  jnz     short loc_18004B2F8
0x18004b2f1  mov     eax, 80004005h
0x18004b2f6  jmp     short loc_18004B302
0x18004b2f8  jle     short loc_18004B308
0x18004b2fa  movzx   eax, ax
0x18004b2fd  or      eax, 80070000h
0x18004b302  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b308  mov     rcx, [rbp+0D0h+arg_0]
0x18004b30f  mov     r10, [rcx+60h]
0x18004b313  test    r10, r10
0x18004b316  jz      loc_18004B5BD
0x18004b31c  xor     ecx, ecx
0x18004b31e  test    eax, eax
0x18004b320  jns     loc_18004B162
0x18004b326  mov     [rsp+1D0h+cchCount2], eax
0x18004b32a  mov     dword ptr [rsp+1D0h+lpString2], 1CFh
0x18004b332  mov     rcx, r10
0x18004b335  jmp     loc_18004B13F
0x18004b33a  xor     edx, edx
0x18004b33c  cmp     [rbp+0D0h+UrlComponents.nScheme], 2
0x18004b340  setz    dl
0x18004b343  mov     dword ptr [rbp+0D0h+arg_8], edx
0x18004b349  mov     rax, [rbp+0D0h+arg_0]
0x18004b350  mov     rcx, [rax+60h]
0x18004b354  test    rcx, rcx
0x18004b357  jz      short loc_18004B388
0x18004b359  lea     r8, aFalse; "FALSE"
0x18004b360  lea     rax, aTrue_0; "TRUE"
0x18004b367  test    edx, edx
0x18004b369  cmovz   rax, r8
0x18004b36d  movzx   r9d, [rbp+0D0h+UrlComponents.nPort]
0x18004b372  mov     [rsp+1D0h+lpString2], rax
0x18004b377  lea     r8, aConnecttosourc_5; "ConnectToSourceUrl: Port: [%d], Secure "...
0x18004b37e  mov     edx, 2
0x18004b383  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004b388  mov     edx, [rbp+0D0h+UrlComponents.dwHostNameLength]; ui
0x18004b38b  mov     rcx, [rbp+0D0h+UrlComponents.lpszHostName]; strIn
0x18004b38f  call    cs:__imp_SysAllocStringLen
0x18004b395  mov     rdi, rax
0x18004b398  test    rax, rax
0x18004b39b  jnz     short loc_18004B3D3
0x18004b39d  mov     [rbp+0D0h+var_120], rax
0x18004b3a1  mov     edx, 8007000Eh
0x18004b3a6  mov     eax, edx
0x18004b3a8  mov     dword ptr [rbp+0D0h+arg_8], edx
0x18004b3ae  mov     rcx, [rbp+0D0h+arg_0]
0x18004b3b5  mov     rcx, [rcx+60h]
0x18004b3b9  test    rcx, rcx
0x18004b3bc  jz      loc_18004B5BD
0x18004b3c2  mov     [rsp+1D0h+cchCount2], edx
0x18004b3c6  mov     dword ptr [rsp+1D0h+lpString2], 1D9h
0x18004b3ce  jmp     loc_18004B13F
0x18004b3d3  mov     [rbp+0D0h+var_120], rdi
0x18004b3d7  mov     edx, [rbp+0D0h+UrlComponents.dwUrlPathLength]; ui
0x18004b3da  mov     rcx, [rbp+0D0h+UrlComponents.lpszUrlPath]; strIn
0x18004b3de  call    cs:__imp_SysAllocStringLen
0x18004b3e4  mov     r14, rax
0x18004b3e7  test    rax, rax
0x18004b3ea  jnz     short loc_18004B422
0x18004b3ec  mov     [rbp+0D0h+var_118], rax
0x18004b3f0  mov     edx, 8007000Eh
0x18004b3f5  mov     eax, edx
0x18004b3f7  mov     dword ptr [rbp+0D0h+arg_8], edx
0x18004b3fd  mov     rcx, [rbp+0D0h+arg_0]
0x18004b404  mov     rcx, [rcx+60h]
0x18004b408  test    rcx, rcx
0x18004b40b  jz      loc_18004B5BD
0x18004b411  mov     [rsp+1D0h+cchCount2], edx
0x18004b415  mov     dword ptr [rsp+1D0h+lpString2], 1DCh
0x18004b41d  jmp     loc_18004B13F
0x18004b422  mov     [rbp+0D0h+var_118], r14
0x18004b426  mov     rax, [rbp+0D0h+arg_0]
0x18004b42d  cmp     qword ptr [rax+220h], 0
0x18004b435  jz      loc_18004B4EC
0x18004b43b  mov     rcx, [rax+230h]
0x18004b442  test    rcx, rcx
0x18004b445  jz      loc_18004B4DE
0x18004b44b  mov     [rsp+1D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004b453  mov     [rsp+1D0h+lpString2], rcx; lpString2
0x18004b458  or      r9d, 0FFFFFFFFh; cchCount1
0x18004b45c  mov     r8, rdi; lpString1
0x18004b45f  lea     edx, [r9+2]; dwCmpFlags
0x18004b463  mov     ecx, 409h; Locale
0x18004b468  call    cs:__imp_CompareStringW
0x18004b46e  add     eax, 0FFFFFFFEh
0x18004b471  mov     rcx, [rbp+0D0h+arg_0]
0x18004b478  mov     rcx, [rcx+60h]
0x18004b47c  jz      short loc_18004B4C1
0x18004b47e  test    rcx, rcx
0x18004b481  jz      short loc_18004B494
0x18004b483  lea     r8, aConnecttosourc_0; "ConnectToSourceUrl: Refreshing WinHttp "...
0x18004b48a  mov     edx, 1
0x18004b48f  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004b494  mov     rax, [rbp+0D0h+arg_0]
0x18004b49b  mov     rcx, [rax+220h]; hInternet
0x18004b4a2  test    rcx, rcx
0x18004b4a5  jz      short loc_18004B4DE
0x18004b4a7  call    cs:__imp_WinHttpCloseHandle
0x18004b4ad  mov     rax, [rbp+0D0h+arg_0]
0x18004b4b4  mov     qword ptr [rax+220h], 0
0x18004b4bf  jmp     short loc_18004B4DE
0x18004b4c1  test    rcx, rcx
0x18004b4c4  jz      short loc_18004B4D7
0x18004b4c6  lea     r8, aConnecttosourc; "ConnectToSourceUrl: Using existing WinH"...
0x18004b4cd  mov     edx, 1
0x18004b4d2  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004b4d7  mov     rax, [rbp+0D0h+arg_0]
0x18004b4de  cmp     qword ptr [rax+220h], 0
0x18004b4e6  jnz     loc_18004B6C6
0x18004b4ec  mov     dword ptr [rsp+1D0h+lpString2], 0; dwFlags
0x18004b4f4  xor     r9d, r9d; pszProxyBypassW
0x18004b4f7  xor     r8d, r8d; pszProxyW
0x18004b4fa  lea     edx, [r9+1]; dwAccessType
0x18004b4fe  lea     rcx, pszAgentW; "Windows Dlp Manager"
0x18004b505  call    cs:__imp_WinHttpOpen
0x18004b50b  mov     rbx, rax
0x18004b50e  mov     rax, [rbp+0D0h+arg_0]
0x18004b515  mov     rcx, [rax+220h]; hInternet
0x18004b51c  test    rcx, rcx
0x18004b51f  jz      short loc_18004B52E
0x18004b521  call    cs:__imp_WinHttpCloseHandle
0x18004b527  mov     rax, [rbp+0D0h+arg_0]
0x18004b52e  test    rbx, rbx
0x18004b531  jnz     loc_18004B6B0
0x18004b537  mov     [rax+220h], rbx
0x18004b53e  call    cs:__imp_GetLastError
0x18004b544  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b54a  test    eax, eax
0x18004b54c  jnz     short loc_18004B555
0x18004b54e  mov     eax, 80004005h
0x18004b553  jmp     short loc_18004B55F
0x18004b555  jle     short loc_18004B565
0x18004b557  movzx   eax, ax
0x18004b55a  or      eax, 80070000h
0x18004b55f  mov     dword ptr [rbp+0D0h+arg_8], eax
0x18004b565  mov     rcx, [rbp+0D0h+arg_0]
0x18004b56c  mov     r10, [rcx+60h]
0x18004b570  test    r10, r10
0x18004b573  jz      short loc_18004B5B8
0x18004b575  xor     ecx, ecx
0x18004b577  test    eax, eax
0x18004b579  jns     short loc_18004B5AD
0x18004b57b  mov     [rsp+1D0h+cchCount2], eax
0x18004b57f  mov     dword ptr [rsp+1D0h+lpString2], 1FAh
0x18004b587  mov     rcx, r10
0x18004b58a  mov     edx, 4
0x18004b58f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
  ... truncated ...
```
