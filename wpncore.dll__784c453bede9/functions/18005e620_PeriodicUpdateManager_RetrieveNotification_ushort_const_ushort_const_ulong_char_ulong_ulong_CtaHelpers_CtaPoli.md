# PeriodicUpdateManager::RetrieveNotification(ushort const *,ushort const *,ulong,char *,ulong *,ulong *,CtaHelpers::CtaPolicy &,ushort * *,ushort * *,ushort * *)

- ea: `0x18005e620`
- end: `0x18005f22b`
- name: `?RetrieveNotification@PeriodicUpdateManager@@AEAAJPEBG0KPEADPEAK2AEAUCtaPolicy@CtaHelpers@@PEAPEAG44@Z`
- size: `3083`
- prototype: `int(PeriodicUpdateManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, char *, unsigned int *, unsigned int *, struct CtaHelpers::CtaPolicy *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005f240`

## callees

- `0x18002ee38`
- `0x18003a184`
- `0x18005de8c`
- `0x18005e620`
- `0x180060150`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e97c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e99a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e9b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e97c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e99a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005e9b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e98a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e9a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e9c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e98a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e9a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005e9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ea9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e8f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ea9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ec47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ed7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f175`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18005e7f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18005e7f1`
- `WINHTTP!WinHttpSetOption` at `0x18005ebe7`
- `WINHTTP!WinHttpSetOption` at `0x18005ebe7`
- `WINHTTP!WinHttpSetCredentials` at `0x18005ec08`
- `WINHTTP!WinHttpSetCredentials` at `0x18005ec08`
- `WINHTTP!WinHttpOpen` at `0x18005e8e4`
- `WINHTTP!WinHttpOpen` at `0x18005e8e4`
- `WINHTTP!WinHttpSendRequest` at `0x18005ec28`
- `WINHTTP!WinHttpSendRequest` at `0x18005ec28`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005ecc4`
- `WINHTTP!WinHttpReceiveResponse` at `0x18005ecc4`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005ecfe`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005ecfe`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18005ed31`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x18005ed31`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18005ef86`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18005ef86`
- `WINHTTP!WinHttpReadData` at `0x18005efc6`
- `WINHTTP!WinHttpReadData` at `0x18005efc6`
- `WINHTTP!WinHttpCloseHandle` at `0x18005e9d4`
- `WINHTTP!WinHttpCloseHandle` at `0x18005e9e2`
- `WINHTTP!WinHttpCloseHandle` at `0x18005e9f0`
- `WINHTTP!WinHttpCloseHandle` at `0x18005e9d4`
- `WINHTTP!WinHttpCloseHandle` at `0x18005e9e2`
- `WINHTTP!WinHttpCloseHandle` at `0x18005e9f0`
- `WINHTTP!WinHttpConnect` at `0x18005ea8f`
- `WINHTTP!WinHttpConnect` at `0x18005ea8f`
- `WINHTTP!WinHttpCrackUrl` at `0x18005e751`
- `WINHTTP!WinHttpCrackUrl` at `0x18005e751`
- `WINHTTP!WinHttpOpenRequest` at `0x18005eb46`
- `WINHTTP!WinHttpOpenRequest` at `0x18005eb46`

## string_xrefs

- `0x18005e777`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005e817`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005e890`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005e914`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005ea3a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005eab9`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005eb70`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005ec63`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005ed96`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005edfb`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005ee78`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005eed8`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005ef38`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005eff5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f045`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f097`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f0ed`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f191`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x18005f1e1`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
__int64 __fastcall PeriodicUpdateManager::RetrieveNotification(
        PeriodicUpdateManager *this,
        CtaHelpers *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        char *a5,
        unsigned int *a6,
        unsigned int *a7,
        struct CtaHelpers::CtaPolicy *a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10,
        unsigned __int16 **a11)
{
  void *v13; // rdi
  unsigned int v14; // r13d
  signed int LastError; // eax
  signed int v16; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  void *v19; // r14
  void *v20; // r15
  INTERNET_PORT nPort; // si
  signed int v22; // eax
  int v23; // eax
  struct CtaHelpers::CtaPolicy *v24; // r8
  signed int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  void *v28; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v30; // rsi
  HANDLE v31; // rax
  unsigned __int16 *v32; // rsi
  HANDLE v33; // rax
  int v35; // eax
  signed int v36; // eax
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  DWORD v39; // ecx
  PeriodicUpdateManager *v40; // rcx
  signed int v41; // eax
  char v42; // r14
  DWORD v43; // ebx
  unsigned int v44; // esi
  signed int v45; // eax
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r9
  signed int v49; // eax
  signed int v50; // eax
  int HttpHeader; // eax
  PeriodicUpdateManager *v52; // rcx
  int v53; // eax
  PeriodicUpdateManager *v54; // rcx
  int v55; // eax
  DWORD v56; // esi
  char *v57; // r14
  signed int v58; // eax
  unsigned __int16 *v59; // rax
  unsigned __int16 *v60; // rax
  unsigned __int16 *v61; // rax
  signed int v62; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-E0h]
  int dwFlagsb; // [rsp+20h] [rbp-E0h]
  int dwFlagsc; // [rsp+20h] [rbp-E0h]
  void *hSession; // [rsp+40h] [rbp-C0h]
  DWORD dwFirstScheme; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v69; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwSupportedSchemes; // [rsp+54h] [rbp-ACh] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v74; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v75; // [rsp+70h] [rbp-90h] BYREF
  int Buffer; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwBufferLength; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD pdwAuthTarget; // [rsp+80h] [rbp-80h] BYREF
  DWORD v79; // [rsp+84h] [rbp-7Ch]
  char *v80; // [rsp+88h] [rbp-78h]
  unsigned __int16 **v81; // [rsp+90h] [rbp-70h]
  unsigned __int16 **v82; // [rsp+98h] [rbp-68h]
  unsigned __int16 **v83; // [rsp+A0h] [rbp-60h]
  unsigned int *v84; // [rsp+A8h] [rbp-58h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+B0h] [rbp-50h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+120h] [rbp+20h] BYREF
  WCHAR pszAgentW[32]; // [rsp+240h] [rbp+140h] BYREF
  __int16 v88; // [rsp+280h] [rbp+180h] BYREF
  __int16 v89; // [rsp+380h] [rbp+280h] BYREF
  WCHAR pswzServerName[256]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  v80 = a5;
  v84 = a6;
  dwNumberOfBytesAvailable = 0;
  dwNumberOfBytesRead = 0;
  lpMem = 0;
  v74 = 0;
  v75 = 0;
  v79 = a4;
  v81 = a9;
  v82 = a10;
  v83 = a11;
  memset_0(&VersionInformation, 0, 0x11Cu);
  *a9 = 0;
  v13 = 0;
  *a10 = 0;
  *a11 = 0;
  v14 = 0;
  pswzServerName[0] = 0;
  v88 = 0;
  v89 = 0;
  *a7 = 200;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.lpszHostName = (LPSTR)pswzServerName;
  UrlComponents.dwUrlPathLength = 2048;
  UrlComponents.lpszUserName = (LPSTR)&v88;
  UrlComponents.dwHostNameLength = 256;
  UrlComponents.lpszPassword = (LPSTR)&v89;
  UrlComponents.dwUserNameLength = 128;
  UrlComponents.dwPasswordLength = 128;
  if ( !WinHttpCrackUrl(a3, 0, 0, &UrlComponents) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x538,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v16,
      dwFlags);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0 )
      goto LABEL_10;
    v18 = 49;
    goto LABEL_9;
  }
  nPort = UrlComponents.nPort;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    v22 = GetLastError();
    v16 = v22;
    if ( v22 > 0 )
      v16 = (unsigned __int16)v22 | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x540,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v16,
      dwFlags);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v18 = 50;
    goto LABEL_9;
  }
  dwFlagsa = VersionInformation.dwMinorVersion;
  v23 = StringCchPrintfW(pszAgentW, 0x20u, L"Microsoft-WNS/%u.%u", VersionInformation.dwMajorVersion);
  v16 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x549,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v23,
      dwFlagsa);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v18 = 51;
LABEL_9:
    WPP_SF_d(v17[2], v18, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, (unsigned int)v16);
LABEL_10:
    v19 = 0;
    v20 = 0;
    goto LABEL_34;
  }
  hSession = WinHttpOpen(pszAgentW, 4u, 0, 0, 0);
  if ( !hSession )
  {
    v25 = GetLastError();
    v16 = v25;
    if ( v25 > 0 )
      v16 = (unsigned __int16)v25 | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x551,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v16,
      dwFlagsb);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_32;
    v27 = 52;
    goto LABEL_31;
  }
  v35 = CtaHelpers::EvaluateCtaPolicy(a2, (const unsigned __int16 *)a8, v24);
  v16 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x554,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v35,
      dwFlagsb);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_32;
    v27 = 53;
LABEL_31:
    WPP_SF_d(v26[2], v27, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, (unsigned int)v16);
LABEL_32:
    v20 = 0;
    goto LABEL_33;
  }
  v19 = hSession;
  v20 = WinHttpConnect(hSession, pswzServerName, nPort, 0);
  if ( !v20 )
  {
    v36 = GetLastError();
    v16 = v36;
    if ( v36 > 0 )
      v16 = (unsigned __int16)v36 | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x55C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v16,
      dwFlagsb);
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_34;
    v38 = 54;
    goto LABEL_59;
  }
  v39 = 0x800000;
  if ( nPort != 443 )
    v39 = 0;
  v13 = WinHttpOpenRequest(v20, L"GET", (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, 0, v39);
  if ( !v13 )
  {
    v41 = GetLastError();
    v16 = v41;
    if ( v41 > 0 )
      v16 = (unsigned __int16)v41 | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x571,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v16,
      dwFlagsc);
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_34;
    v38 = 55;
LABEL_59:
    WPP_SF_d(v37[2], v38, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, (unsigned int)v16);
    goto LABEL_34;
  }
  v42 = 0;
  v43 = 0;
  v44 = 0;
  while ( !v42 )
  {
    Buffer = 1;
    if ( v43 && WinHttpSetOption(v13, 0x4Du, &Buffer, 4u) )
      WinHttpSetCredentials(v13, 1u, v43, 0, 0, 0);
    if ( WinHttpSendRequest(v13, 0, 0, 0, 0, 0, 0) )
    {
      if ( !WinHttpReceiveResponse(v13, 0) )
      {
        v50 = GetLastError();
        v16 = v50;
        if ( v50 > 0 )
          v16 = (unsigned __int16)v50 | 0x80070000;
        if ( v16 >= 0 )
          v16 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x588,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)(unsigned int)v16,
          dwFlagsc);
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_33;
        v47 = 57;
        goto LABEL_84;
      }
      v69 = 0;
      dwBufferLength = 4;
      if ( !WinHttpQueryHeaders(v13, 0x20000013u, 0, &v69, &dwBufferLength, 0) )
      {
        v49 = GetLastError();
        v16 = v49;
        if ( v49 > 0 )
          v16 = (unsigned __int16)v49 | 0x80070000;
        if ( v16 >= 0 )
          v16 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x594,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
          (const char *)(unsigned int)v16,
          dwFlagsc);
        v46 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_33;
        v47 = 58;
        goto LABEL_84;
      }
      if ( v69 != 407 )
        goto LABEL_98;
      dwSupportedSchemes = 0;
      dwFirstScheme = 0;
      pdwAuthTarget = 0;
      if ( WinHttpQueryAuthSchemes(v13, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget) )
      {
        if ( (dwSupportedSchemes & 0x10) != 0 )
        {
          v43 = 16;
        }
        else if ( (dwSupportedSchemes & 2) != 0 )
        {
          v43 = 2;
        }
        else if ( (dwSupportedSchemes & 4) != 0 )
        {
          v43 = 4;
        }
        else
        {
          v43 = dwSupportedSchemes & 8;
        }
      }
      if ( v44 == 407 )
LABEL_98:
        v42 = 1;
      v44 = v69;
    }
    else if ( GetLastError() != 12032 )
    {
      v45 = GetLastError();
      v16 = v45;
      if ( v45 > 0 )
        v16 = (unsigned __int16)v45 | 0x80070000;
      if ( v16 >= 0 )
        v16 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x584,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsc);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_33;
      v47 = 56;
      goto LABEL_84;
    }
  }
  *a7 = v44;
  if ( v44 - 200 > 0x63 )
  {
    v16 = -2143420117;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)0x803E012BLL,
      dwFlagsc);
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_33;
    v47 = 59;
    v48 = 2151547179LL;
LABEL_85:
    WPP_SF_d(v46[2], v47, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, v48);
    goto LABEL_33;
  }
  HttpHeader = PeriodicUpdateManager::RetrieveHttpHeader(v40, v13, L"X-WNS-Tag", (unsigned __int16 **)&lpMem);
  v16 = HttpHeader;
  if ( HttpHeader < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)HttpHeader,
      dwFlagsc);
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_33;
    v47 = 60;
LABEL_84:
    v48 = (unsigned int)v16;
    goto LABEL_85;
  }
  v53 = PeriodicUpdateManager::RetrieveHttpHeader(v52, v13, L"X-WNS-Group", &v74);
  v16 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5BB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v53,
      dwFlagsc);
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_33;
    v47 = 61;
    goto LABEL_84;
  }
  v55 = PeriodicUpdateManager::RetrieveHttpHeader(v54, v13, L"X-WNS-Expires", &v75);
  v16 = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5BE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)(unsigned int)v55,
      dwFlagsc);
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_33;
    v47 = 62;
    goto LABEL_84;
  }
  v56 = v79;
  v57 = v80;
  while ( 1 )
  {
    if ( !WinHttpQueryDataAvailable(v13, &dwNumberOfBytesAvailable) )
    {
      v62 = GetLastError();
      v16 = v62;
      if ( v62 > 0 )
        v16 = (unsigned __int16)v62 | 0x80070000;
      if ( v16 >= 0 )
        v16 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5DE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsc);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_33;
      v47 = 66;
      goto LABEL_84;
    }
    if ( !dwNumberOfBytesAvailable )
      break;
    if ( dwNumberOfBytesAvailable + v14 < dwNumberOfBytesAvailable )
    {
      v16 = -2147024362;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5CA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x80070216LL,
        dwFlagsc);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_33;
      v47 = 63;
      v48 = 2147942934LL;
      goto LABEL_85;
    }
    if ( dwNumberOfBytesAvailable + v14 > v56 )
    {
      v16 = -2143420139;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)0x803E0115LL,
        dwFlagsc);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_33;
      v47 = 64;
LABEL_144:
      v48 = 2151547157LL;
      goto LABEL_85;
    }
    if ( !WinHttpReadData(v13, &v57[v14], dwNumberOfBytesAvailable, &dwNumberOfBytesRead) )
    {
      v58 = GetLastError();
      v16 = v58;
      if ( v58 > 0 )
        v16 = (unsigned __int16)v58 | 0x80070000;
      if ( v16 >= 0 )
        v16 = -2147467259;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsc);
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v47 = 65;
        goto LABEL_84;
      }
      goto LABEL_33;
    }
    v14 += dwNumberOfBytesRead;
    v16 = 0;
  }
  if ( v14 )
  {
    v59 = (unsigned __int16 *)lpMem;
    lpMem = 0;
    *v81 = v59;
    v60 = v74;
    v74 = 0;
    *v82 = v60;
    v61 = v75;
    v75 = 0;
    *v83 = v61;
    goto LABEL_33;
  }
  v16 = -2143420139;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x5E4,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
    (const char *)0x803E0115LL,
    dwFlagsc);
  v46 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v47 = 67;
    goto LABEL_144;
  }
LABEL_33:
  v19 = hSession;
LABEL_34:
  v28 = lpMem;
  *v84 = v14;
  if ( v28 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v28);
  }
  v30 = v74;
  if ( v74 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v30);
  }
  v32 = v75;
  if ( v75 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v32);
  }
  if ( v13 )
    WinHttpCloseHandle(v13);
  if ( v20 )
    WinHttpCloseHandle(v20);
  if ( v19 )
    WinHttpCloseHandle(v19);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18005e620  mov     [rsp-8+arg_0], rbx
0x18005e625  push    rbp
0x18005e626  push    rsi
0x18005e627  push    rdi
0x18005e628  push    r12
0x18005e62a  push    r13
0x18005e62c  push    r14
0x18005e62e  push    r15
0x18005e630  lea     rbp, [rsp-590h]
0x18005e638  sub     rsp, 690h
0x18005e63f  mov     rax, cs:__security_cookie
0x18005e646  xor     rax, rsp
0x18005e649  mov     [rbp+5C0h+var_40], rax
0x18005e650  mov     rax, [rbp+5C0h+arg_20]
0x18005e657  lea     rcx, [rbp+5C0h+VersionInformation]; void *
0x18005e65b  mov     rdi, [rbp+5C0h+arg_40]
0x18005e662  mov     rbx, r8
0x18005e665  mov     rsi, [rbp+5C0h+arg_48]
0x18005e66c  mov     r14, rdx
0x18005e66f  mov     r13, [rbp+5C0h+arg_50]
0x18005e676  xor     edx, edx; Val
0x18005e678  mov     r12, [rbp+5C0h+arg_30]
0x18005e67f  mov     r8d, 11Ch; Size
0x18005e685  mov     r15, [rbp+5C0h+arg_38]
0x18005e68c  mov     [rbp+5C0h+var_638], rax
0x18005e690  mov     rax, [rbp+5C0h+arg_28]
0x18005e697  mov     [rbp+5C0h+var_618], rax
0x18005e69b  xor     eax, eax
0x18005e69d  mov     [rsp+6C0h+dwNumberOfBytesAvailable], eax
0x18005e6a1  mov     [rsp+6C0h+dwNumberOfBytesRead], eax
0x18005e6a5  mov     [rsp+6C0h+lpMem], rax
0x18005e6aa  mov     [rsp+6C0h+var_658], rax
0x18005e6af  mov     [rsp+6C0h+var_650], rax
0x18005e6b4  mov     [rbp+5C0h+var_63C], r9d
0x18005e6b8  mov     [rbp+5C0h+var_630], rdi
0x18005e6bc  mov     [rbp+5C0h+var_628], rsi
0x18005e6c0  mov     [rbp+5C0h+var_620], r13
0x18005e6c4  call    memset_0
0x18005e6c9  xor     ecx, ecx
0x18005e6cb  xor     edx, edx; Val
0x18005e6cd  mov     [rdi], rcx
0x18005e6d0  mov     edi, ecx
0x18005e6d2  mov     [rsi], rcx
0x18005e6d5  mov     [r13+0], rcx
0x18005e6d9  mov     r13d, ecx
0x18005e6dc  lea     esi, [rcx+68h]
0x18005e6df  mov     [rbp+5C0h+pswzServerName], cx
0x18005e6e6  mov     [rbp+5C0h+var_440], cx
0x18005e6ed  mov     r8d, esi; Size
0x18005e6f0  mov     [rbp+5C0h+var_340], cx
0x18005e6f7  lea     rcx, [rbp+5C0h+UrlComponents]; void *
0x18005e6fb  mov     dword ptr [r12], 0C8h
0x18005e703  call    memset_0
0x18005e708  lea     rax, [rbp+5C0h+pswzServerName]
0x18005e70f  mov     [rbp+5C0h+UrlComponents.dwStructSize], esi
0x18005e712  mov     [rbp+5C0h+UrlComponents.lpszHostName], rax
0x18005e716  lea     r9, [rbp+5C0h+UrlComponents]; lpUrlComponents
0x18005e71a  lea     rax, [rbp+5C0h+var_440]
0x18005e721  mov     [rbp+5C0h+UrlComponents.dwUrlPathLength], 800h
0x18005e728  mov     [rbp+5C0h+UrlComponents.lpszUserName], rax
0x18005e72c  mov     esi, 80h
0x18005e731  lea     rax, [rbp+5C0h+var_340]
0x18005e738  mov     [rbp+5C0h+UrlComponents.dwHostNameLength], 100h
0x18005e73f  xor     r8d, r8d; dwFlags
0x18005e742  mov     [rbp+5C0h+UrlComponents.lpszPassword], rax
0x18005e746  xor     edx, edx; dwUrlLength
0x18005e748  mov     [rbp+5C0h+UrlComponents.dwUserNameLength], esi
0x18005e74b  mov     rcx, rbx; pwszUrl
0x18005e74e  mov     [rbp+5C0h+UrlComponents.dwPasswordLength], esi
0x18005e751  call    cs:__imp_WinHttpCrackUrl
0x18005e757  test    eax, eax
0x18005e759  jnz     short loc_18005E7D1
0x18005e75b  call    cs:__imp_GetLastError
0x18005e761  mov     ebx, eax
0x18005e763  test    eax, eax
0x18005e765  jle     short loc_18005E770
0x18005e767  movzx   ebx, ax
0x18005e76a  or      ebx, 80070000h
0x18005e770  mov     rcx, [rbp+5C8h]; this
0x18005e777  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e77e  test    ebx, ebx
0x18005e780  mov     eax, 80004005h
0x18005e785  mov     edx, 538h; void *
0x18005e78a  cmovns  ebx, eax
0x18005e78d  mov     r9d, ebx; char *
0x18005e790  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e795  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e79c  lea     rax, WPP_GLOBAL_Control
0x18005e7a3  cmp     rcx, rax
0x18005e7a6  jz      short loc_18005E7C6
0x18005e7a8  test    [rcx+1Ch], sil
0x18005e7ac  jz      short loc_18005E7C6
0x18005e7ae  mov     edx, 31h ; '1'
0x18005e7b3  mov     rcx, [rcx+10h]
0x18005e7b7  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x18005e7be  mov     r9d, ebx
0x18005e7c1  call    WPP_SF_d
0x18005e7c6  mov     r14, rdi
0x18005e7c9  mov     r15, rdi
0x18005e7cc  jmp     loc_18005E96B
0x18005e7d1  movzx   esi, [rbp+5C0h+UrlComponents.nPort]
0x18005e7d5  lea     rcx, [rbp+5C0h+VersionInformation.dwMajorVersion]; void *
0x18005e7d9  xor     edx, edx; Val
0x18005e7db  mov     r8d, 118h; Size
0x18005e7e1  call    memset_0
0x18005e7e6  lea     rcx, [rbp+5C0h+VersionInformation]; lpVersionInformation
0x18005e7ea  mov     [rbp+5C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18005e7f1  call    cs:__imp_GetVersionExW
0x18005e7f7  test    eax, eax
0x18005e7f9  jnz     short loc_18005E860
0x18005e7fb  call    cs:__imp_GetLastError
0x18005e801  mov     ebx, eax
0x18005e803  test    eax, eax
0x18005e805  jle     short loc_18005E810
0x18005e807  movzx   ebx, ax
0x18005e80a  or      ebx, 80070000h
0x18005e810  mov     rcx, [rbp+5C8h]; this
0x18005e817  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e81e  test    ebx, ebx
0x18005e820  mov     eax, 80004005h
0x18005e825  mov     edx, 540h; void *
0x18005e82a  cmovns  ebx, eax
0x18005e82d  mov     r9d, ebx; char *
0x18005e830  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e835  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e83c  lea     rax, WPP_GLOBAL_Control
0x18005e843  cmp     rcx, rax
0x18005e846  jz      loc_18005E7C6
0x18005e84c  test    byte ptr [rcx+1Ch], 80h
0x18005e850  jz      loc_18005E7C6
0x18005e856  mov     edx, 32h ; '2'
0x18005e85b  jmp     loc_18005E7B3
0x18005e860  mov     eax, [rbp+5C0h+VersionInformation.dwMinorVersion]
0x18005e863  lea     r8, aMicrosoftWnsUU; "Microsoft-WNS/%u.%u"
0x18005e86a  mov     r9d, [rbp+5C0h+VersionInformation.dwMajorVersion]
0x18005e86e  lea     rcx, [rbp+5C0h+pszAgentW]; unsigned __int16 *
0x18005e875  mov     edx, 20h ; ' '; unsigned __int64
0x18005e87a  mov     [rsp+6C0h+dwFlags], eax; int
0x18005e87e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e883  mov     ebx, eax
0x18005e885  test    eax, eax
0x18005e887  jns     short loc_18005E8CF
0x18005e889  mov     rcx, [rbp+5C8h]; this
0x18005e890  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e897  mov     r9d, eax; char *
0x18005e89a  mov     edx, 549h; void *
0x18005e89f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e8ab  lea     rax, WPP_GLOBAL_Control
0x18005e8b2  cmp     rcx, rax
0x18005e8b5  jz      loc_18005E7C6
0x18005e8bb  test    byte ptr [rcx+1Ch], 80h
0x18005e8bf  jz      loc_18005E7C6
0x18005e8c5  mov     edx, 33h ; '3'
0x18005e8ca  jmp     loc_18005E7B3
0x18005e8cf  xor     r9d, r9d; pszProxyBypassW
0x18005e8d2  mov     [rsp+6C0h+dwFlags], edi; int
0x18005e8d6  xor     r8d, r8d; pszProxyW
0x18005e8d9  lea     rcx, [rbp+5C0h+pszAgentW]; pszAgentW
0x18005e8e0  lea     edx, [r9+4]; dwAccessType
0x18005e8e4  call    cs:__imp_WinHttpOpen
0x18005e8ea  mov     [rsp+6C0h+hSession], rax
0x18005e8ef  test    rax, rax
0x18005e8f2  jnz     loc_18005EA22
0x18005e8f8  call    cs:__imp_GetLastError
0x18005e8fe  mov     ebx, eax
0x18005e900  test    eax, eax
0x18005e902  jle     short loc_18005E90D
0x18005e904  movzx   ebx, ax
0x18005e907  or      ebx, 80070000h
0x18005e90d  mov     rcx, [rbp+5C8h]; this
0x18005e914  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005e91b  test    ebx, ebx
0x18005e91d  mov     eax, 80004005h
0x18005e922  mov     edx, 551h; void *
0x18005e927  cmovns  ebx, eax
0x18005e92a  mov     r9d, ebx; char *
0x18005e92d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e932  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e939  lea     rax, WPP_GLOBAL_Control
0x18005e940  cmp     rcx, rax
0x18005e943  jz      short loc_18005E963
0x18005e945  test    byte ptr [rcx+1Ch], 80h
0x18005e949  jz      short loc_18005E963
0x18005e94b  mov     edx, 34h ; '4'
0x18005e950  mov     rcx, [rcx+10h]
0x18005e954  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x18005e95b  mov     r9d, ebx
0x18005e95e  call    WPP_SF_d
0x18005e963  mov     r15, rdi
0x18005e966  mov     r14, [rsp+6C0h+hSession]
0x18005e96b  mov     rax, [rbp+5C0h+var_618]
0x18005e96f  mov     rsi, [rsp+6C0h+lpMem]
0x18005e974  mov     [rax], r13d
0x18005e977  test    rsi, rsi
0x18005e97a  jz      short loc_18005E990
0x18005e97c  call    cs:__imp_GetProcessHeap
0x18005e982  mov     r8, rsi; lpMem
0x18005e985  xor     edx, edx; dwFlags
0x18005e987  mov     rcx, rax; hHeap
0x18005e98a  call    cs:__imp_HeapFree
0x18005e990  mov     rsi, [rsp+6C0h+var_658]
0x18005e995  test    rsi, rsi
0x18005e998  jz      short loc_18005E9AE
0x18005e99a  call    cs:__imp_GetProcessHeap
0x18005e9a0  mov     r8, rsi; lpMem
0x18005e9a3  xor     edx, edx; dwFlags
0x18005e9a5  mov     rcx, rax; hHeap
0x18005e9a8  call    cs:__imp_HeapFree
0x18005e9ae  mov     rsi, [rsp+6C0h+var_650]
0x18005e9b3  test    rsi, rsi
0x18005e9b6  jz      short loc_18005E9CC
0x18005e9b8  call    cs:__imp_GetProcessHeap
0x18005e9be  mov     r8, rsi; lpMem
0x18005e9c1  xor     edx, edx; dwFlags
0x18005e9c3  mov     rcx, rax; hHeap
0x18005e9c6  call    cs:__imp_HeapFree
0x18005e9cc  test    rdi, rdi
0x18005e9cf  jz      short loc_18005E9DA
0x18005e9d1  mov     rcx, rdi; hInternet
0x18005e9d4  call    cs:__imp_WinHttpCloseHandle
0x18005e9da  test    r15, r15
0x18005e9dd  jz      short loc_18005E9E8
0x18005e9df  mov     rcx, r15; hInternet
0x18005e9e2  call    cs:__imp_WinHttpCloseHandle
0x18005e9e8  test    r14, r14
0x18005e9eb  jz      short loc_18005E9F6
0x18005e9ed  mov     rcx, r14; hInternet
0x18005e9f0  call    cs:__imp_WinHttpCloseHandle
0x18005e9f6  mov     eax, ebx
0x18005e9f8  mov     rcx, [rbp+5C0h+var_40]
0x18005e9ff  xor     rcx, rsp; StackCookie
0x18005ea02  call    __security_check_cookie
0x18005ea07  mov     rbx, [rsp+6C0h+arg_0]
0x18005ea0f  add     rsp, 690h
0x18005ea16  pop     r15
0x18005ea18  pop     r14
0x18005ea1a  pop     r13
0x18005ea1c  pop     r12
0x18005ea1e  pop     rdi
0x18005ea1f  pop     rsi
0x18005ea20  pop     rbp
0x18005ea21  retn
0x18005ea22  mov     rdx, r15; unsigned __int16 *
0x18005ea25  mov     rcx, r14; this
0x18005ea28  call    ?EvaluateCtaPolicy@CtaHelpers@@YAJPEBGAEAUCtaPolicy@1@@Z; CtaHelpers::EvaluateCtaPolicy(ushort const *,CtaHelpers::CtaPolicy &)
0x18005ea2d  mov     ebx, eax
0x18005ea2f  test    eax, eax
0x18005ea31  jns     short loc_18005EA79
0x18005ea33  mov     rcx, [rbp+5C8h]; this
0x18005ea3a  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005ea41  mov     r9d, eax; char *
0x18005ea44  mov     edx, 554h; void *
0x18005ea49  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ea4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ea55  lea     rax, WPP_GLOBAL_Control
0x18005ea5c  cmp     rcx, rax
0x18005ea5f  jz      loc_18005E963
0x18005ea65  test    byte ptr [rcx+1Ch], 80h
0x18005ea69  jz      loc_18005E963
0x18005ea6f  mov     edx, 35h ; '5'
0x18005ea74  jmp     loc_18005E950
0x18005ea79  mov     r14, [rsp+6C0h+hSession]
0x18005ea7e  lea     rdx, [rbp+5C0h+pswzServerName]; pswzServerName
0x18005ea85  mov     rcx, r14; hSession
0x18005ea88  xor     r9d, r9d; dwReserved
0x18005ea8b  movzx   r8d, si; nServerPort
0x18005ea8f  call    cs:__imp_WinHttpConnect
0x18005ea95  mov     r15, rax
0x18005ea98  test    rax, rax
0x18005ea9b  jnz     short loc_18005EB15
0x18005ea9d  call    cs:__imp_GetLastError
0x18005eaa3  mov     ebx, eax
0x18005eaa5  test    eax, eax
0x18005eaa7  jle     short loc_18005EAB2
0x18005eaa9  movzx   ebx, ax
0x18005eaac  or      ebx, 80070000h
0x18005eab2  mov     rcx, [rbp+5C8h]; this
0x18005eab9  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18005eac0  test    ebx, ebx
0x18005eac2  mov     eax, 80004005h
0x18005eac7  mov     edx, 55Ch; void *
0x18005eacc  cmovns  ebx, eax
0x18005eacf  mov     r9d, ebx; char *
0x18005ead2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005ead7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eade  lea     rax, WPP_GLOBAL_Control
0x18005eae5  cmp     rcx, rax
0x18005eae8  jz      loc_18005E96B
0x18005eaee  test    byte ptr [rcx+1Ch], 80h
0x18005eaf2  jz      loc_18005E96B
0x18005eaf8  mov     edx, 36h ; '6'
0x18005eafd  mov     rcx, [rcx+10h]
0x18005eb01  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x18005eb08  mov     r9d, ebx
0x18005eb0b  call    WPP_SF_d
0x18005eb10  jmp     loc_18005E96B
0x18005eb15  mov     r8, [rbp+5C0h+UrlComponents.lpszUrlPath]; pwszObjectName
0x18005eb19  xor     eax, eax
0x18005eb1b  mov     edx, 1BBh
  ... truncated ...
```
