# CVersionManagerServer::_DownloadVersionList(int *)

- ea: `0x1800f79b0`
- end: `0x1800f7f1f`
- name: `?_DownloadVersionList@CVersionManagerServer@@AEAAJPEAH@Z`
- size: `1391`
- prototype: `__int64 __fastcall(CVersionManagerServer *__hidden this, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f9ba0`

## callees

- `0x18001054c`
- `0x1800a00f8`
- `0x1800f61e0`
- `0x1800f6fac`
- `0x1800f7734`
- `0x1800f79b0`
- `0x1800f8000`
- `0x1800f80ec`
- `0x1800f9220`
- `0x1800f9860`
- `0x18010e4f0`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7ea9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7ea9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f7a08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f7d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f7a08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f7d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7db2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f7dd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f7e61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f7dd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f7e61`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f7ecb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800f7ecb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800f7bcd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800f7bcd`
- `api-ms-win-http-time-l1-1-0!InternetTimeFromSystemTimeW` at `0x1800f7bfa`
- `api-ms-win-http-time-l1-1-0!InternetTimeFromSystemTimeW` at `0x1800f7bfa`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800f7da6`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800f7da6`
- `WININET!HttpOpenRequestW` at `0x1800f7b18`
- `WININET!HttpOpenRequestW` at `0x1800f7b18`
- `WININET!InternetSetOptionW` at `0x1800f7b5e`
- `WININET!InternetSetOptionW` at `0x1800f7b5e`
- `WININET!InternetConnectW` at `0x1800f7aac`
- `WININET!InternetConnectW` at `0x1800f7aac`
- `WININET!InternetOpenW` at `0x1800f7a52`
- `WININET!InternetOpenW` at `0x1800f7a52`
- `WININET!HttpSendRequestW` at `0x1800f7c7c`
- `WININET!HttpSendRequestW` at `0x1800f7c7c`
- `WININET!HttpAddRequestHeadersW` at `0x1800f7b7e`
- `WININET!HttpAddRequestHeadersW` at `0x1800f7c48`
- `WININET!HttpAddRequestHeadersW` at `0x1800f7b7e`
- `WININET!HttpAddRequestHeadersW` at `0x1800f7c48`
- `WININET!HttpQueryInfoW` at `0x1800f7ca9`
- `WININET!HttpQueryInfoW` at `0x1800f7ca9`
- `WININET!InternetCloseHandle` at `0x1800f7ed9`
- `WININET!InternetCloseHandle` at `0x1800f7ee4`
- `WININET!InternetCloseHandle` at `0x1800f7eed`
- `WININET!InternetCloseHandle` at `0x1800f7ed9`
- `WININET!InternetCloseHandle` at `0x1800f7ee4`
- `WININET!InternetCloseHandle` at `0x1800f7eed`

## string_xrefs

- `0x1800f7adf`: `text/xml`

## pseudocode

```c
__int64 __fastcall CVersionManagerServer::_DownloadVersionList(WCHAR *this, int *a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // r13
  int FullBlockListNotThreadSafe; // ebx
  void *v7; // rax
  void *v8; // r14
  signed int LastError; // eax
  void *v10; // rax
  signed int v11; // eax
  void *v12; // rax
  void *v13; // r15
  signed int v14; // eax
  signed int v15; // eax
  __int64 v16; // r8
  bool v17; // sf
  signed int v18; // eax
  char v19; // r14
  unsigned int v20; // edx
  int v21; // r9d
  bool v22; // sf
  int v23; // r8d
  bool v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  FILETIME FileTime; // [rsp+48h] [rbp-B8h] BYREF
  CBlockListManager *v27; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  int Buffer; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwBufferLength; // [rsp+64h] [rbp-9Ch] BYREF
  void *v31; // [rsp+68h] [rbp-98h]
  struct _FILETIME v32; // [rsp+70h] [rbp-90h] BYREF
  HINTERNET hInternet; // [rsp+78h] [rbp-88h]
  LPCWSTR lpszAcceptTypes[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szTime[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h]
  _BYTE v38[30]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szHeaders[264]; // [rsp+E0h] [rbp-20h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)(this + 964);
  *a2 = 0;
  FileTime = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 964));
  FullBlockListNotThreadSafe = CVersionManagerServer::_GetFileTime(
                                 (_DWORD)this,
                                 SettingStore::IEVALUE_urlmon_ExtVerLastUpdateLowDateTime[0],
                                 SettingStore::IEVALUE_urlmon_ExtVerLastUpdateHighDateTime[0],
                                 (unsigned int)&FileTime,
                                 1);
  LeaveCriticalSection(v5);
  if ( FullBlockListNotThreadSafe >= 0 )
  {
    v7 = InternetOpenW(0, 0, 0, 0, 0);
    v31 = v7;
    v8 = v7;
    if ( !v7 )
    {
      LastError = GetLastError();
      FullBlockListNotThreadSafe = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)FullBlockListNotThreadSafe;
    }
    v10 = InternetConnectW(v7, this + 275, 0x1BBu, 0, 0, 3u, 0, 0);
    hInternet = v10;
    if ( !v10 )
    {
      v11 = GetLastError();
      FullBlockListNotThreadSafe = v11;
      if ( v11 > 0 )
        FullBlockListNotThreadSafe = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_60;
    }
    lpszAcceptTypes[0] = L"text/xml";
    lpszAcceptTypes[1] = 0;
    v12 = HttpOpenRequestW(v10, L"GET", this + 535, 0, 0, lpszAcceptTypes, 0x4C00200u, 0);
    v13 = v12;
    if ( !v12 )
    {
      v14 = GetLastError();
      FullBlockListNotThreadSafe = v14;
      if ( v14 > 0 )
        FullBlockListNotThreadSafe = (unsigned __int16)v14 | 0x80070000;
      goto LABEL_59;
    }
    Buffer = 1;
    if ( !InternetSetOptionW(v12, 0x41u, &Buffer, 4u)
      || !HttpAddRequestHeadersW(v13, L"Accept-Encoding: gzip", 0x15u, 0x40000000u) )
    {
      v15 = GetLastError();
      FullBlockListNotThreadSafe = v15;
      if ( v15 > 0 )
        FullBlockListNotThreadSafe = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_58;
    }
    if ( FileTime.dwLowDateTime || FileTime.dwHighDateTime )
    {
      SystemTime = 0;
      if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
        goto LABEL_25;
      memset(v38, 0, sizeof(v38));
      *(_OWORD *)szTime = 0;
      v37 = 0;
      if ( !InternetTimeFromSystemTimeW(&SystemTime, 0, szTime, 0x3Eu) )
        goto LABEL_25;
      FullBlockListNotThreadSafe = StringCchPrintfW(szHeaders, 0x104u, L"If-Modified-Since: %s", szTime);
      if ( FullBlockListNotThreadSafe < 0 )
      {
LABEL_58:
        InternetCloseHandle(v13);
LABEL_59:
        InternetCloseHandle(hInternet);
LABEL_60:
        InternetCloseHandle(v8);
        return (unsigned int)FullBlockListNotThreadSafe;
      }
      v16 = -1;
      do
        ++v16;
      while ( szHeaders[v16] );
      if ( !HttpAddRequestHeadersW(v13, szHeaders, v16, 0x40000000u) )
      {
LABEL_25:
        FullBlockListNotThreadSafe = GetLastError();
        v17 = FullBlockListNotThreadSafe < 0;
        if ( FullBlockListNotThreadSafe > 0 )
        {
          FullBlockListNotThreadSafe = (unsigned __int16)FullBlockListNotThreadSafe | 0x80070000;
          v17 = FullBlockListNotThreadSafe < 0;
        }
        if ( v17 )
          goto LABEL_58;
      }
    }
    if ( !HttpSendRequestW(v13, 0, 0, 0, 0)
      || (v25 = 0, dwBufferLength = 4, !HttpQueryInfoW(v13, 0x20000013u, &v25, &dwBufferLength, 0)) )
    {
      v18 = GetLastError();
      FullBlockListNotThreadSafe = v18;
      if ( v18 > 0 )
        FullBlockListNotThreadSafe = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_58;
    }
    v19 = 0;
    v27 = 0;
    if ( v25 == 200 )
    {
      FullBlockListNotThreadSafe = CVersionManagerServer::_DownloadBlockListToTempFile(
                                     (CVersionManagerServer *)this,
                                     v13,
                                     szHeaders);
      if ( FullBlockListNotThreadSafe < 0 )
        goto LABEL_53;
      v19 = 1;
      FullBlockListNotThreadSafe = CVersionManagerServer::_CreateBlockListManager(
                                     (CVersionManagerServer *)this,
                                     &v27,
                                     szHeaders,
                                     v21);
      if ( FullBlockListNotThreadSafe < 0 )
        goto LABEL_53;
      FullBlockListNotThreadSafe = CVersionManagerServer::_ForceLoadFullBlockListNotThreadSafe(
                                     (CVersionManagerServer *)this,
                                     v27,
                                     szHeaders,
                                     0,
                                     0);
      if ( FullBlockListNotThreadSafe < 0 )
        goto LABEL_53;
    }
    v24 = 0;
    EnterCriticalSection(v5);
    *(_QWORD *)&SystemTime.wYear = this + 1016;
    FullBlockListNotThreadSafe = MutexUtils::CAutoMutex::Lock((MutexUtils::CAutoMutex *)&SystemTime, &v24);
    if ( FullBlockListNotThreadSafe < 0 )
    {
LABEL_52:
      MutexUtils::CAutoMutex::~CAutoMutex((MutexUtils::CAutoMutex *)&SystemTime);
      LeaveCriticalSection(v5);
      if ( FullBlockListNotThreadSafe >= 0 )
      {
LABEL_57:
        v8 = v31;
        goto LABEL_58;
      }
LABEL_53:
      if ( v27 )
        CBlockListManager::`scalar deleting destructor'(v27, v20);
      if ( v19 )
        DeleteFileW(szHeaders);
      goto LABEL_57;
    }
    if ( v24 )
    {
      FullBlockListNotThreadSafe = -2147024768;
      goto LABEL_52;
    }
    if ( v25 == 200 && v27 && v19 )
    {
      if ( MoveFileExW(szHeaders, this + 15, 9u) )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        FullBlockListNotThreadSafe = CVersionManagerServer::_SetFileTimeWithFailureFallback(
                                       (_DWORD)this,
                                       SettingStore::IEVALUE_urlmon_ExtVerLastUpdateLowDateTime[0],
                                       SettingStore::IEVALUE_urlmon_ExtVerLastUpdateHighDateTime[0],
                                       (unsigned int)&SystemTimeAsFileTime,
                                       (__int64)&FileTime,
                                       0);
        if ( FullBlockListNotThreadSafe < 0 )
          goto LABEL_52;
        FullBlockListNotThreadSafe = CVersionManagerServer::_SwitchBlockListNotThreadSafe(
                                       (CVersionManagerServer *)this,
                                       &v27,
                                       v23);
        if ( FullBlockListNotThreadSafe < 0 )
          goto LABEL_52;
        *a2 = 1;
      }
      else
      {
        FullBlockListNotThreadSafe = GetLastError();
        v22 = FullBlockListNotThreadSafe < 0;
        if ( FullBlockListNotThreadSafe <= 0 )
        {
LABEL_48:
          if ( !v22 )
          {
            SystemTimeAsFileTime = 0;
            FullBlockListNotThreadSafe = CVersionManagerServer::_GetFileTime(
                                           (_DWORD)this,
                                           SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateLowDateTime[0],
                                           SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateHighDateTime[0],
                                           (unsigned int)&SystemTimeAsFileTime,
                                           0);
            if ( FullBlockListNotThreadSafe >= 0 )
            {
              v32 = 0;
              GetSystemTimeAsFileTime(&v32);
              FullBlockListNotThreadSafe = CVersionManagerServer::_SetFileTimeWithFailureFallback(
                                             (_DWORD)this,
                                             SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateLowDateTime[0],
                                             SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateHighDateTime[0],
                                             (unsigned int)&v32,
                                             (__int64)&SystemTimeAsFileTime,
                                             0);
            }
          }
          goto LABEL_52;
        }
        FullBlockListNotThreadSafe = (unsigned __int16)FullBlockListNotThreadSafe | 0x80070000;
      }
    }
    v22 = FullBlockListNotThreadSafe < 0;
    goto LABEL_48;
  }
  return (unsigned int)FullBlockListNotThreadSafe;
}

```

## disassembly

```asm
0x1800f79b0  mov     [rsp-8+arg_10], rbx
0x1800f79b5  push    rbp
0x1800f79b6  push    rsi
0x1800f79b7  push    rdi
0x1800f79b8  push    r12
0x1800f79ba  push    r13
0x1800f79bc  push    r14
0x1800f79be  push    r15
0x1800f79c0  lea     rbp, [rsp-200h]
0x1800f79c8  sub     rsp, 300h
0x1800f79cf  mov     rax, cs:__security_cookie
0x1800f79d6  xor     rax, rsp
0x1800f79d9  mov     [rbp+230h+var_40], rax
0x1800f79e0  xor     edi, edi
0x1800f79e2  mov     r12, rdx
0x1800f79e5  mov     rsi, rcx
0x1800f79e8  test    rdx, rdx
0x1800f79eb  jnz     short loc_1800F79F7
0x1800f79ed  mov     eax, 80070057h
0x1800f79f2  jmp     loc_1800F7EF5
0x1800f79f7  lea     r13, [rcx+788h]
0x1800f79fe  mov     [rdx], edi
0x1800f7a00  mov     rcx, r13; lpCriticalSection
0x1800f7a03  mov     qword ptr [rsp+330h+FileTime.dwLowDateTime], rdi
0x1800f7a08  call    cs:__imp_EnterCriticalSection
0x1800f7a0e  mov     r8, cs:?IEVALUE_urlmon_ExtVerLastUpdateHighDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateHighDateTime
0x1800f7a15  lea     r9, [rsp+330h+FileTime]
0x1800f7a1a  mov     rdx, cs:?IEVALUE_urlmon_ExtVerLastUpdateLowDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateLowDateTime
0x1800f7a21  mov     rcx, rsi
0x1800f7a24  mov     [rsp+330h+dwFlags], 1
0x1800f7a2c  call    ?_GetFileTime@CVersionManagerServer@@AEAAJU?$VALUEID@K@SettingStore@@0PEAU_FILETIME@@H@Z; CVersionManagerServer::_GetFileTime(SettingStore::VALUEID<ulong>,SettingStore::VALUEID<ulong>,_FILETIME *,int)
0x1800f7a31  mov     rcx, r13; lpCriticalSection
0x1800f7a34  mov     ebx, eax
0x1800f7a36  call    cs:__imp_LeaveCriticalSection
0x1800f7a3c  test    ebx, ebx
0x1800f7a3e  js      loc_1800F7EF3
0x1800f7a44  xor     r9d, r9d; lpszProxyBypass
0x1800f7a47  mov     [rsp+330h+dwFlags], edi; dwFlags
0x1800f7a4b  xor     r8d, r8d; lpszProxy
0x1800f7a4e  xor     edx, edx; dwAccessType
0x1800f7a50  xor     ecx, ecx; lpszAgent
0x1800f7a52  call    cs:__imp_InternetOpenW
0x1800f7a58  mov     [rsp+330h+var_2C8], rax
0x1800f7a5d  mov     r14, rax
0x1800f7a60  test    rax, rax
0x1800f7a63  jnz     short loc_1800F7A83
0x1800f7a65  call    cs:__imp_GetLastError
0x1800f7a6b  mov     ebx, eax
0x1800f7a6d  test    eax, eax
0x1800f7a6f  jle     loc_1800F7EF3
0x1800f7a75  movzx   ebx, ax
0x1800f7a78  or      ebx, 80070000h
0x1800f7a7e  jmp     loc_1800F7EF3
0x1800f7a83  mov     [rsp+330h+dwContext], rdi; dwContext
0x1800f7a88  lea     rdx, [rsi+226h]; lpszServerName
0x1800f7a8f  mov     [rsp+330h+var_300], edi; dwFlags
0x1800f7a93  mov     r8d, 1BBh; nServerPort
0x1800f7a99  mov     [rsp+330h+dwService], 3; dwService
0x1800f7aa1  xor     r9d, r9d; lpszUserName
0x1800f7aa4  mov     rcx, rax; hInternet
0x1800f7aa7  mov     qword ptr [rsp+330h+dwFlags], rdi; lpszPassword
0x1800f7aac  call    cs:__imp_InternetConnectW
0x1800f7ab2  mov     [rsp+330h+hInternet], rax
0x1800f7ab7  test    rax, rax
0x1800f7aba  jnz     short loc_1800F7ADA
0x1800f7abc  call    cs:__imp_GetLastError
0x1800f7ac2  mov     ebx, eax
0x1800f7ac4  test    eax, eax
0x1800f7ac6  jle     loc_1800F7EEA
0x1800f7acc  movzx   ebx, ax
0x1800f7acf  or      ebx, 80070000h
0x1800f7ad5  jmp     loc_1800F7EEA
0x1800f7ada  mov     [rsp+330h+dwContext], rdi; dwContext
0x1800f7adf  lea     rcx, aTextXml; "text/xml"
0x1800f7ae6  mov     [rbp+230h+lpszAcceptTypes], rcx
0x1800f7aea  lea     r8, [rsi+42Eh]; lpszObjectName
0x1800f7af1  lea     rcx, [rbp+230h+lpszAcceptTypes]
0x1800f7af5  mov     [rsp+330h+var_300], 4C00200h; dwFlags
0x1800f7afd  mov     qword ptr [rsp+330h+dwService], rcx; lplpszAcceptTypes
0x1800f7b02  lea     rdx, szVerb; "GET"
0x1800f7b09  mov     rcx, rax; hConnect
0x1800f7b0c  mov     [rbp+230h+var_2A8], rdi
0x1800f7b10  xor     r9d, r9d; lpszVersion
0x1800f7b13  mov     qword ptr [rsp+330h+dwFlags], rdi; lpszReferrer
0x1800f7b18  call    cs:__imp_HttpOpenRequestW
0x1800f7b1e  mov     r15, rax
0x1800f7b21  test    rax, rax
0x1800f7b24  jnz     short loc_1800F7B44
0x1800f7b26  call    cs:__imp_GetLastError
0x1800f7b2c  mov     ebx, eax
0x1800f7b2e  test    eax, eax
0x1800f7b30  jle     loc_1800F7EDF
0x1800f7b36  movzx   ebx, ax
0x1800f7b39  or      ebx, 80070000h
0x1800f7b3f  jmp     loc_1800F7EDF
0x1800f7b44  mov     r9d, 4; dwBufferLength
0x1800f7b4a  mov     [rsp+330h+Buffer], 1
0x1800f7b52  lea     r8, [rsp+330h+Buffer]; lpBuffer
0x1800f7b57  mov     rcx, r15; hInternet
0x1800f7b5a  lea     edx, [r9+3Dh]; dwOption
0x1800f7b5e  call    cs:__imp_InternetSetOptionW
0x1800f7b64  test    eax, eax
0x1800f7b66  jz      short loc_1800F7B88
0x1800f7b68  mov     r9d, 40000000h; dwModifiers
0x1800f7b6e  lea     rdx, aAcceptEncoding; "Accept-Encoding: gzip"
0x1800f7b75  mov     r8d, 15h; dwHeadersLength
0x1800f7b7b  mov     rcx, r15; hRequest
0x1800f7b7e  call    cs:__imp_HttpAddRequestHeadersW
0x1800f7b84  test    eax, eax
0x1800f7b86  jnz     short loc_1800F7BA6
0x1800f7b88  call    cs:__imp_GetLastError
0x1800f7b8e  mov     ebx, eax
0x1800f7b90  test    eax, eax
0x1800f7b92  jle     loc_1800F7ED6
0x1800f7b98  movzx   ebx, ax
0x1800f7b9b  or      ebx, 80070000h
0x1800f7ba1  jmp     loc_1800F7ED6
0x1800f7ba6  xor     ebx, ebx
0x1800f7ba8  mov     edi, 80070000h
0x1800f7bad  cmp     [rsp+330h+FileTime.dwLowDateTime], ebx
0x1800f7bb1  jnz     short loc_1800F7BBD
0x1800f7bb3  cmp     [rsp+330h+FileTime.dwHighDateTime], ebx
0x1800f7bb7  jz      loc_1800F7C6D
0x1800f7bbd  xorps   xmm0, xmm0
0x1800f7bc0  lea     rdx, [rbp+230h+SystemTime]; lpSystemTime
0x1800f7bc4  lea     rcx, [rsp+330h+FileTime]; lpFileTime
0x1800f7bc9  movups  xmmword ptr [rbp+230h+SystemTime.wYear], xmm0
0x1800f7bcd  call    cs:__imp_FileTimeToSystemTime
0x1800f7bd3  test    eax, eax
0x1800f7bd5  jz      short loc_1800F7C52
0x1800f7bd7  xorps   xmm0, xmm0
0x1800f7bda  lea     r8, [rbp+230h+szTime]; lpszTime
0x1800f7bde  movups  xmmword ptr [rbp+230h+var_270], xmm0
0x1800f7be2  mov     r9d, 3Eh ; '>'; cbTime
0x1800f7be8  lea     rcx, [rbp+230h+SystemTime]; pst
0x1800f7bec  xor     edx, edx; dwRFC
0x1800f7bee  movups  xmmword ptr [rbp+230h+var_270+0Eh], xmm0
0x1800f7bf2  movups  xmmword ptr [rbp+230h+szTime], xmm0
0x1800f7bf6  movups  [rbp+230h+var_280], xmm0
0x1800f7bfa  call    cs:__imp_InternetTimeFromSystemTimeW
0x1800f7c00  test    eax, eax
0x1800f7c02  jz      short loc_1800F7C52
0x1800f7c04  lea     r9, [rbp+230h+szTime]
0x1800f7c08  mov     edx, 104h; unsigned __int64
0x1800f7c0d  lea     r8, aIfModifiedSinc_0; "If-Modified-Since: %s"
0x1800f7c14  lea     rcx, [rbp+230h+szHeaders]; unsigned __int16 *
0x1800f7c18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f7c1d  mov     ebx, eax
0x1800f7c1f  test    eax, eax
0x1800f7c21  js      loc_1800F7ED6
0x1800f7c27  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f7c2b  lea     rax, [rbp+230h+szHeaders]
0x1800f7c2f  xor     ebx, ebx
0x1800f7c31  inc     r8; dwHeadersLength
0x1800f7c34  cmp     [rax+r8*2], bx
0x1800f7c39  jnz     short loc_1800F7C31
0x1800f7c3b  mov     r9d, 40000000h; dwModifiers
0x1800f7c41  lea     rdx, [rbp+230h+szHeaders]; lpszHeaders
0x1800f7c45  mov     rcx, r15; hRequest
0x1800f7c48  call    cs:__imp_HttpAddRequestHeadersW
0x1800f7c4e  test    eax, eax
0x1800f7c50  jnz     short loc_1800F7C6D
0x1800f7c52  call    cs:__imp_GetLastError
0x1800f7c58  mov     ebx, eax
0x1800f7c5a  test    eax, eax
0x1800f7c5c  jle     short loc_1800F7C65
0x1800f7c5e  movzx   ebx, bx
0x1800f7c61  or      ebx, edi
0x1800f7c63  test    ebx, ebx
0x1800f7c65  js      loc_1800F7ED6
0x1800f7c6b  xor     ebx, ebx
0x1800f7c6d  xor     r9d, r9d; lpOptional
0x1800f7c70  mov     [rsp+330h+dwFlags], ebx; dwOptionalLength
0x1800f7c74  xor     r8d, r8d; dwHeadersLength
0x1800f7c77  xor     edx, edx; lpszHeaders
0x1800f7c79  mov     rcx, r15; hRequest
0x1800f7c7c  call    cs:__imp_HttpSendRequestW
0x1800f7c82  test    eax, eax
0x1800f7c84  jz      short loc_1800F7CB3
0x1800f7c86  lea     r9, [rsp+330h+dwBufferLength]; lpdwBufferLength
0x1800f7c8b  mov     [rsp+330h+var_2EC], ebx
0x1800f7c8f  lea     r8, [rsp+330h+var_2EC]; lpBuffer
0x1800f7c94  mov     [rsp+330h+dwBufferLength], 4
0x1800f7c9c  mov     edx, 20000013h; dwInfoLevel
0x1800f7ca1  mov     qword ptr [rsp+330h+dwFlags], rbx; lpdwIndex
0x1800f7ca6  mov     rcx, r15; hRequest
0x1800f7ca9  call    cs:__imp_HttpQueryInfoW
0x1800f7caf  test    eax, eax
0x1800f7cb1  jnz     short loc_1800F7CCD
0x1800f7cb3  call    cs:__imp_GetLastError
0x1800f7cb9  mov     ebx, eax
0x1800f7cbb  test    eax, eax
0x1800f7cbd  jle     loc_1800F7ED6
0x1800f7cc3  movzx   ebx, ax
0x1800f7cc6  or      ebx, edi
0x1800f7cc8  jmp     loc_1800F7ED6
0x1800f7ccd  cmp     [rsp+330h+var_2EC], 0C8h
0x1800f7cd5  mov     r14b, bl
0x1800f7cd8  mov     [rsp+330h+var_2E0], rbx
0x1800f7cdd  jnz     short loc_1800F7D3C
0x1800f7cdf  lea     r8, [rbp+230h+szHeaders]; unsigned __int16 *
0x1800f7ce3  mov     rdx, r15; void *
0x1800f7ce6  mov     rcx, rsi; this
0x1800f7ce9  call    ?_DownloadBlockListToTempFile@CVersionManagerServer@@AEAAJPEAXPEAGK@Z; CVersionManagerServer::_DownloadBlockListToTempFile(void *,ushort *,ulong)
0x1800f7cee  mov     ebx, eax
0x1800f7cf0  test    eax, eax
0x1800f7cf2  js      loc_1800F7EB3
0x1800f7cf8  lea     r8, [rbp+230h+szHeaders]; unsigned __int16 *
0x1800f7cfc  mov     rcx, rsi; this
0x1800f7cff  lea     rdx, [rsp+330h+var_2E0]; struct CBlockListManager **
0x1800f7d04  mov     r14b, 1
0x1800f7d07  call    ?_CreateBlockListManager@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@PEBGH@Z; CVersionManagerServer::_CreateBlockListManager(CBlockListManager * *,ushort const *,int)
0x1800f7d0c  xor     ecx, ecx
0x1800f7d0e  mov     ebx, eax
0x1800f7d10  test    eax, eax
0x1800f7d12  js      loc_1800F7EB3
0x1800f7d18  mov     rdx, [rsp+330h+var_2E0]; struct CBlockListManager *
0x1800f7d1d  lea     r8, [rbp+230h+szHeaders]; unsigned __int16 *
0x1800f7d21  mov     [rsp+330h+dwFlags], ecx; int
0x1800f7d25  xor     r9d, r9d; int
0x1800f7d28  mov     rcx, rsi; this
0x1800f7d2b  call    ?_ForceLoadFullBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAVCBlockListManager@@PEBGHH@Z; CVersionManagerServer::_ForceLoadFullBlockListNotThreadSafe(CBlockListManager *,ushort const *,int,int)
0x1800f7d30  mov     ebx, eax
0x1800f7d32  test    eax, eax
0x1800f7d34  js      loc_1800F7EB3
0x1800f7d3a  xor     ebx, ebx
0x1800f7d3c  mov     rcx, r13; lpCriticalSection
0x1800f7d3f  mov     [rsp+330h+var_2F0], bl
0x1800f7d43  call    cs:__imp_EnterCriticalSection
0x1800f7d49  lea     rax, [rsi+7F0h]
0x1800f7d50  lea     rdx, [rsp+330h+var_2F0]; bool *
0x1800f7d55  mov     qword ptr [rbp+230h+SystemTime.wYear], rax
0x1800f7d59  lea     rcx, [rbp+230h+SystemTime]; this
0x1800f7d5d  call    ?Lock@CAutoMutex@MutexUtils@@QEAAJPEA_N@Z; MutexUtils::CAutoMutex::Lock(bool *)
0x1800f7d62  mov     ebx, eax
0x1800f7d64  xor     eax, eax
0x1800f7d66  test    ebx, ebx
0x1800f7d68  js      loc_1800F7E9D
0x1800f7d6e  cmp     [rsp+330h+var_2F0], al
0x1800f7d72  jnz     loc_1800F7E98
0x1800f7d78  cmp     [rsp+330h+var_2EC], 0C8h
0x1800f7d80  jnz     loc_1800F7E27
0x1800f7d86  cmp     [rsp+330h+var_2E0], rax
0x1800f7d8b  jz      loc_1800F7E27
0x1800f7d91  test    r14b, r14b
0x1800f7d94  jz      loc_1800F7E27
0x1800f7d9a  lea     rdx, [rsi+1Eh]; lpNewFileName
0x1800f7d9e  lea     r8d, [rax+9]; dwFlags
0x1800f7da2  lea     rcx, [rbp+230h+szHeaders]; lpExistingFileName
0x1800f7da6  call    cs:__imp_MoveFileExW
0x1800f7dac  xor     ebx, ebx
0x1800f7dae  test    eax, eax
0x1800f7db0  jnz     short loc_1800F7DC7
0x1800f7db2  call    cs:__imp_GetLastError
0x1800f7db8  mov     ebx, eax
0x1800f7dba  xor     eax, eax
0x1800f7dbc  test    ebx, ebx
0x1800f7dbe  jle     short loc_1800F7E29
0x1800f7dc0  movzx   ebx, bx
0x1800f7dc3  or      ebx, edi
0x1800f7dc5  jmp     short loc_1800F7E27
0x1800f7dc7  lea     rcx, [rsp+330h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f7dcc  mov     qword ptr [rsp+330h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800f7dd1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f7dd7  mov     r8, cs:?IEVALUE_urlmon_ExtVerLastUpdateHighDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateHighDateTime
0x1800f7dde  lea     rax, [rsp+330h+FileTime]
0x1800f7de3  mov     rdx, cs:?IEVALUE_urlmon_ExtVerLastUpdateLowDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateLowDateTime
0x1800f7dea  lea     r9, [rsp+330h+SystemTimeAsFileTime]
0x1800f7def  mov     [rsp+330h+dwService], ebx
0x1800f7df3  mov     rcx, rsi
0x1800f7df6  mov     qword ptr [rsp+330h+dwFlags], rax
0x1800f7dfb  call    ?_SetFileTimeWithFailureFallback@CVersionManagerServer@@AEAAJU?$VALUEID@K@SettingStore@@0PEAU_FILETIME@@1H@Z; CVersionManagerServer::_SetFileTimeWithFailureFallback(SettingStore::VALUEID<ulong>,SettingStore::VALUEID<ulong>,_FILETIME *,_FILETIME *,int)
0x1800f7e00  mov     ebx, eax
0x1800f7e02  test    eax, eax
0x1800f7e04  js      loc_1800F7E9D
0x1800f7e0a  lea     rdx, [rsp+330h+var_2E0]; struct CBlockListManager **
0x1800f7e0f  mov     rcx, rsi; this
0x1800f7e12  call    ?_SwitchBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@H@Z; CVersionManagerServer::_SwitchBlockListNotThreadSafe(CBlockListManager * *,int)
0x1800f7e17  mov     ebx, eax
0x1800f7e19  xor     eax, eax
0x1800f7e1b  test    ebx, ebx
0x1800f7e1d  js      short loc_1800F7E9D
0x1800f7e1f  mov     dword ptr [r12], 1
0x1800f7e27  test    ebx, ebx
0x1800f7e29  js      short loc_1800F7E9D
0x1800f7e2b  mov     r8, cs:?IEVALUE_urlmon_ExtVerLastCheckForUpdateHighDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateHighDateTime
0x1800f7e32  lea     r9, [rsp+330h+SystemTimeAsFileTime]
0x1800f7e37  mov     rdx, cs:?IEVALUE_urlmon_ExtVerLastCheckForUpdateLowDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateLowDateTime
0x1800f7e3e  mov     rcx, rsi
0x1800f7e41  mov     qword ptr [rsp+330h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800f7e46  mov     [rsp+330h+dwFlags], eax
0x1800f7e4a  call    ?_GetFileTime@CVersionManagerServer@@AEAAJU?$VALUEID@K@SettingStore@@0PEAU_FILETIME@@H@Z; CVersionManagerServer::_GetFileTime(SettingStore::VALUEID<ulong>,SettingStore::VALUEID<ulong>,_FILETIME *,int)
0x1800f7e4f  mov     ebx, eax
0x1800f7e51  xor     eax, eax
0x1800f7e53  test    ebx, ebx
0x1800f7e55  js      short loc_1800F7E9D
0x1800f7e57  lea     rcx, [rsp+330h+var_2C0]; lpSystemTimeAsFileTime
0x1800f7e5c  mov     qword ptr [rsp+330h+var_2C0.dwLowDateTime], rax
0x1800f7e61  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f7e67  mov     r8, cs:?IEVALUE_urlmon_ExtVerLastCheckForUpdateHighDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastCheckForUpdateHighDateTime
  ... truncated ...
```
