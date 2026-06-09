# CVersionManagerServer::_DownloadVersionList(int *)

- ea: `0x1801022c0`
- end: `0x1801028e0`
- name: `?_DownloadVersionList@CVersionManagerServer@@AEAAJPEAH@Z`
- size: `1568`
- prototype: `__int64 __fastcall(CVersionManagerServer *__hidden this, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180104650`

## callees

- `0x1800162d4`
- `0x1800a6e68`
- `0x180100954`
- `0x1801017b0`
- `0x180101fec`
- `0x1801022c0`
- `0x1801029c4`
- `0x180102ab0`
- `0x180103c38`
- `0x1801042e8`
- `0x18011a1bc`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010234c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010284b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010234c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010284b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180102318`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801026c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180102318`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801026c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801023ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801024d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801025ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010262d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010273e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801023ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801024d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801025ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010262d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010273e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180102763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801027fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180102763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801027fd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180102873`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180102873`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18010251f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18010251f`
- `api-ms-win-http-time-l1-1-0!InternetTimeFromSystemTimeW` at `0x180102556`
- `api-ms-win-http-time-l1-1-0!InternetTimeFromSystemTimeW` at `0x180102556`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18010272c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18010272c`
- `WININET!HttpOpenRequestW` at `0x18010244c`
- `WININET!HttpOpenRequestW` at `0x18010244c`
- `WININET!InternetSetOptionW` at `0x18010249e`
- `WININET!InternetSetOptionW` at `0x18010249e`
- `WININET!InternetConnectW` at `0x1801023d4`
- `WININET!InternetConnectW` at `0x1801023d4`
- `WININET!InternetOpenW` at `0x18010236e`
- `WININET!InternetOpenW` at `0x18010236e`
- `WININET!HttpSendRequestW` at `0x1801025ea`
- `WININET!HttpSendRequestW` at `0x1801025ea`
- `WININET!HttpAddRequestHeadersW` at `0x1801024c4`
- `WININET!HttpAddRequestHeadersW` at `0x1801025aa`
- `WININET!HttpAddRequestHeadersW` at `0x1801024c4`
- `WININET!HttpAddRequestHeadersW` at `0x1801025aa`
- `WININET!HttpQueryInfoW` at `0x18010261d`
- `WININET!HttpQueryInfoW` at `0x18010261d`
- `WININET!InternetCloseHandle` at `0x180102887`
- `WININET!InternetCloseHandle` at `0x180102898`
- `WININET!InternetCloseHandle` at `0x1801028a7`
- `WININET!InternetCloseHandle` at `0x180102887`
- `WININET!InternetCloseHandle` at `0x180102898`
- `WININET!InternetCloseHandle` at `0x1801028a7`

## string_xrefs

- `0x180102413`: `text/xml`

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
0x1801022c0  mov     [rsp-8+arg_10], rbx
0x1801022c5  push    rbp
0x1801022c6  push    rsi
0x1801022c7  push    rdi
0x1801022c8  push    r12
0x1801022ca  push    r13
0x1801022cc  push    r14
0x1801022ce  push    r15
0x1801022d0  lea     rbp, [rsp-200h]
0x1801022d8  sub     rsp, 300h
0x1801022df  mov     rax, cs:__security_cookie
0x1801022e6  xor     rax, rsp
0x1801022e9  mov     [rbp+230h+var_40], rax
0x1801022f0  xor     edi, edi
0x1801022f2  mov     r12, rdx
0x1801022f5  mov     rsi, rcx
0x1801022f8  test    rdx, rdx
0x1801022fb  jnz     short loc_180102307
0x1801022fd  mov     eax, 80070057h
0x180102302  jmp     loc_1801028B5
0x180102307  lea     r13, [rcx+788h]
0x18010230e  mov     [rdx], edi
0x180102310  mov     rcx, r13; lpCriticalSection
0x180102313  mov     qword ptr [rsp+330h+FileTime.dwLowDateTime], rdi
0x180102318  call    cs:__imp_EnterCriticalSection
0x18010231f  nop     dword ptr [rax+rax+00h]
0x180102324  mov     r8, cs:?IEVALUE_urlmon_ExtVerLastUpdateHighDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateHighDateTime
0x18010232b  lea     r9, [rsp+330h+FileTime]
0x180102330  mov     rdx, cs:?IEVALUE_urlmon_ExtVerLastUpdateLowDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateLowDateTime
0x180102337  mov     rcx, rsi
0x18010233a  mov     [rsp+330h+dwFlags], 1
0x180102342  call    ?_GetFileTime@CVersionManagerServer@@AEAAJU?$VALUEID@K@SettingStore@@0PEAU_FILETIME@@H@Z; CVersionManagerServer::_GetFileTime(SettingStore::VALUEID<ulong>,SettingStore::VALUEID<ulong>,_FILETIME *,int)
0x180102347  mov     rcx, r13; lpCriticalSection
0x18010234a  mov     ebx, eax
0x18010234c  call    cs:__imp_LeaveCriticalSection
0x180102353  nop     dword ptr [rax+rax+00h]
0x180102358  test    ebx, ebx
0x18010235a  js      loc_1801028B3
0x180102360  xor     r9d, r9d; lpszProxyBypass
0x180102363  mov     [rsp+330h+dwFlags], edi; dwFlags
0x180102367  xor     r8d, r8d; lpszProxy
0x18010236a  xor     edx, edx; dwAccessType
0x18010236c  xor     ecx, ecx; lpszAgent
0x18010236e  call    cs:__imp_InternetOpenW
0x180102375  nop     dword ptr [rax+rax+00h]
0x18010237a  mov     [rsp+330h+var_2C8], rax
0x18010237f  mov     r14, rax
0x180102382  test    rax, rax
0x180102385  jnz     short loc_1801023AB
0x180102387  call    cs:__imp_GetLastError
0x18010238e  nop     dword ptr [rax+rax+00h]
0x180102393  mov     ebx, eax
0x180102395  test    eax, eax
0x180102397  jle     loc_1801028B3
0x18010239d  movzx   ebx, ax
0x1801023a0  or      ebx, 80070000h
0x1801023a6  jmp     loc_1801028B3
0x1801023ab  mov     [rsp+330h+dwContext], rdi; dwContext
0x1801023b0  lea     rdx, [rsi+226h]; lpszServerName
0x1801023b7  mov     [rsp+330h+var_300], edi; dwFlags
0x1801023bb  mov     r8d, 1BBh; nServerPort
0x1801023c1  mov     [rsp+330h+dwService], 3; dwService
0x1801023c9  xor     r9d, r9d; lpszUserName
0x1801023cc  mov     rcx, rax; hInternet
0x1801023cf  mov     qword ptr [rsp+330h+dwFlags], rdi; lpszPassword
0x1801023d4  call    cs:__imp_InternetConnectW
0x1801023db  nop     dword ptr [rax+rax+00h]
0x1801023e0  mov     [rsp+330h+hInternet], rax
0x1801023e5  test    rax, rax
0x1801023e8  jnz     short loc_18010240E
0x1801023ea  call    cs:__imp_GetLastError
0x1801023f1  nop     dword ptr [rax+rax+00h]
0x1801023f6  mov     ebx, eax
0x1801023f8  test    eax, eax
0x1801023fa  jle     loc_1801028A4
0x180102400  movzx   ebx, ax
0x180102403  or      ebx, 80070000h
0x180102409  jmp     loc_1801028A4
0x18010240e  mov     [rsp+330h+dwContext], rdi; dwContext
0x180102413  lea     rcx, aTextXml; "text/xml"
0x18010241a  mov     [rbp+230h+lpszAcceptTypes], rcx
0x18010241e  lea     r8, [rsi+42Eh]; lpszObjectName
0x180102425  lea     rcx, [rbp+230h+lpszAcceptTypes]
0x180102429  mov     [rsp+330h+var_300], 4C00200h; dwFlags
0x180102431  mov     qword ptr [rsp+330h+dwService], rcx; lplpszAcceptTypes
0x180102436  lea     rdx, szVerb; "GET"
0x18010243d  mov     rcx, rax; hConnect
0x180102440  mov     [rbp+230h+var_2A8], rdi
0x180102444  xor     r9d, r9d; lpszVersion
0x180102447  mov     qword ptr [rsp+330h+dwFlags], rdi; lpszReferrer
0x18010244c  call    cs:__imp_HttpOpenRequestW
0x180102453  nop     dword ptr [rax+rax+00h]
0x180102458  mov     r15, rax
0x18010245b  test    rax, rax
0x18010245e  jnz     short loc_180102484
0x180102460  call    cs:__imp_GetLastError
0x180102467  nop     dword ptr [rax+rax+00h]
0x18010246c  mov     ebx, eax
0x18010246e  test    eax, eax
0x180102470  jle     loc_180102893
0x180102476  movzx   ebx, ax
0x180102479  or      ebx, 80070000h
0x18010247f  jmp     loc_180102893
0x180102484  mov     r9d, 4; dwBufferLength
0x18010248a  mov     [rsp+330h+Buffer], 1
0x180102492  lea     r8, [rsp+330h+Buffer]; lpBuffer
0x180102497  mov     rcx, r15; hInternet
0x18010249a  lea     edx, [r9+3Dh]; dwOption
0x18010249e  call    cs:__imp_InternetSetOptionW
0x1801024a5  nop     dword ptr [rax+rax+00h]
0x1801024aa  test    eax, eax
0x1801024ac  jz      short loc_1801024D4
0x1801024ae  mov     r9d, 40000000h; dwModifiers
0x1801024b4  lea     rdx, aAcceptEncoding; "Accept-Encoding: gzip"
0x1801024bb  mov     r8d, 15h; dwHeadersLength
0x1801024c1  mov     rcx, r15; hRequest
0x1801024c4  call    cs:__imp_HttpAddRequestHeadersW
0x1801024cb  nop     dword ptr [rax+rax+00h]
0x1801024d0  test    eax, eax
0x1801024d2  jnz     short loc_1801024F8
0x1801024d4  call    cs:__imp_GetLastError
0x1801024db  nop     dword ptr [rax+rax+00h]
0x1801024e0  mov     ebx, eax
0x1801024e2  test    eax, eax
0x1801024e4  jle     loc_180102884
0x1801024ea  movzx   ebx, ax
0x1801024ed  or      ebx, 80070000h
0x1801024f3  jmp     loc_180102884
0x1801024f8  xor     ebx, ebx
0x1801024fa  mov     edi, 80070000h
0x1801024ff  cmp     [rsp+330h+FileTime.dwLowDateTime], ebx
0x180102503  jnz     short loc_18010250F
0x180102505  cmp     [rsp+330h+FileTime.dwHighDateTime], ebx
0x180102509  jz      loc_1801025DB
0x18010250f  xorps   xmm0, xmm0
0x180102512  lea     rdx, [rbp+230h+SystemTime]; lpSystemTime
0x180102516  lea     rcx, [rsp+330h+FileTime]; lpFileTime
0x18010251b  movups  xmmword ptr [rbp+230h+SystemTime.wYear], xmm0
0x18010251f  call    cs:__imp_FileTimeToSystemTime
0x180102526  nop     dword ptr [rax+rax+00h]
0x18010252b  test    eax, eax
0x18010252d  jz      loc_1801025BA
0x180102533  xorps   xmm0, xmm0
0x180102536  lea     r8, [rbp+230h+szTime]; lpszTime
0x18010253a  movups  xmmword ptr [rbp+230h+var_270], xmm0
0x18010253e  mov     r9d, 3Eh ; '>'; cbTime
0x180102544  lea     rcx, [rbp+230h+SystemTime]; pst
0x180102548  xor     edx, edx; dwRFC
0x18010254a  movups  xmmword ptr [rbp+230h+var_270+0Eh], xmm0
0x18010254e  movups  xmmword ptr [rbp+230h+szTime], xmm0
0x180102552  movups  [rbp+230h+var_280], xmm0
0x180102556  call    cs:__imp_InternetTimeFromSystemTimeW
0x18010255d  nop     dword ptr [rax+rax+00h]
0x180102562  test    eax, eax
0x180102564  jz      short loc_1801025BA
0x180102566  lea     r9, [rbp+230h+szTime]
0x18010256a  mov     edx, 104h; unsigned __int64
0x18010256f  lea     r8, aIfModifiedSinc_0; "If-Modified-Since: %s"
0x180102576  lea     rcx, [rbp+230h+szHeaders]; unsigned __int16 *
0x18010257a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010257f  mov     ebx, eax
0x180102581  test    eax, eax
0x180102583  js      loc_180102884
0x180102589  or      r8, 0FFFFFFFFFFFFFFFFh
0x18010258d  lea     rax, [rbp+230h+szHeaders]
0x180102591  xor     ebx, ebx
0x180102593  inc     r8; dwHeadersLength
0x180102596  cmp     [rax+r8*2], bx
0x18010259b  jnz     short loc_180102593
0x18010259d  mov     r9d, 40000000h; dwModifiers
0x1801025a3  lea     rdx, [rbp+230h+szHeaders]; lpszHeaders
0x1801025a7  mov     rcx, r15; hRequest
0x1801025aa  call    cs:__imp_HttpAddRequestHeadersW
0x1801025b1  nop     dword ptr [rax+rax+00h]
0x1801025b6  test    eax, eax
0x1801025b8  jnz     short loc_1801025DB
0x1801025ba  call    cs:__imp_GetLastError
0x1801025c1  nop     dword ptr [rax+rax+00h]
0x1801025c6  mov     ebx, eax
0x1801025c8  test    eax, eax
0x1801025ca  jle     short loc_1801025D3
0x1801025cc  movzx   ebx, bx
0x1801025cf  or      ebx, edi
0x1801025d1  test    ebx, ebx
0x1801025d3  js      loc_180102884
0x1801025d9  xor     ebx, ebx
0x1801025db  xor     r9d, r9d; lpOptional
0x1801025de  mov     [rsp+330h+dwFlags], ebx; dwOptionalLength
0x1801025e2  xor     r8d, r8d; dwHeadersLength
0x1801025e5  xor     edx, edx; lpszHeaders
0x1801025e7  mov     rcx, r15; hRequest
0x1801025ea  call    cs:__imp_HttpSendRequestW
0x1801025f1  nop     dword ptr [rax+rax+00h]
0x1801025f6  test    eax, eax
0x1801025f8  jz      short loc_18010262D
0x1801025fa  lea     r9, [rsp+330h+dwBufferLength]; lpdwBufferLength
0x1801025ff  mov     [rsp+330h+var_2EC], ebx
0x180102603  lea     r8, [rsp+330h+var_2EC]; lpBuffer
0x180102608  mov     [rsp+330h+dwBufferLength], 4
0x180102610  mov     edx, 20000013h; dwInfoLevel
0x180102615  mov     qword ptr [rsp+330h+dwFlags], rbx; lpdwIndex
0x18010261a  mov     rcx, r15; hRequest
0x18010261d  call    cs:__imp_HttpQueryInfoW
0x180102624  nop     dword ptr [rax+rax+00h]
0x180102629  test    eax, eax
0x18010262b  jnz     short loc_18010264D
0x18010262d  call    cs:__imp_GetLastError
0x180102634  nop     dword ptr [rax+rax+00h]
0x180102639  mov     ebx, eax
0x18010263b  test    eax, eax
0x18010263d  jle     loc_180102884
0x180102643  movzx   ebx, ax
0x180102646  or      ebx, edi
0x180102648  jmp     loc_180102884
0x18010264d  cmp     [rsp+330h+var_2EC], 0C8h
0x180102655  mov     r14b, bl
0x180102658  mov     [rsp+330h+var_2E0], rbx
0x18010265d  jnz     short loc_1801026BC
0x18010265f  lea     r8, [rbp+230h+szHeaders]; unsigned __int16 *
0x180102663  mov     rdx, r15; void *
0x180102666  mov     rcx, rsi; this
0x180102669  call    ?_DownloadBlockListToTempFile@CVersionManagerServer@@AEAAJPEAXPEAGK@Z; CVersionManagerServer::_DownloadBlockListToTempFile(void *,ushort *,ulong)
0x18010266e  mov     ebx, eax
0x180102670  test    eax, eax
0x180102672  js      loc_18010285B
0x180102678  lea     r8, [rbp+230h+szHeaders]; unsigned __int16 *
0x18010267c  mov     rcx, rsi; this
0x18010267f  lea     rdx, [rsp+330h+var_2E0]; struct CBlockListManager **
0x180102684  mov     r14b, 1
0x180102687  call    ?_CreateBlockListManager@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@PEBGH@Z; CVersionManagerServer::_CreateBlockListManager(CBlockListManager * *,ushort const *,int)
0x18010268c  xor     ecx, ecx
0x18010268e  mov     ebx, eax
0x180102690  test    eax, eax
0x180102692  js      loc_18010285B
0x180102698  mov     rdx, [rsp+330h+var_2E0]; struct CBlockListManager *
0x18010269d  lea     r8, [rbp+230h+szHeaders]; unsigned __int16 *
0x1801026a1  mov     [rsp+330h+dwFlags], ecx; int
0x1801026a5  xor     r9d, r9d; int
0x1801026a8  mov     rcx, rsi; this
0x1801026ab  call    ?_ForceLoadFullBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAVCBlockListManager@@PEBGHH@Z; CVersionManagerServer::_ForceLoadFullBlockListNotThreadSafe(CBlockListManager *,ushort const *,int,int)
0x1801026b0  mov     ebx, eax
0x1801026b2  test    eax, eax
0x1801026b4  js      loc_18010285B
0x1801026ba  xor     ebx, ebx
0x1801026bc  mov     rcx, r13; lpCriticalSection
0x1801026bf  mov     [rsp+330h+var_2F0], bl
0x1801026c3  call    cs:__imp_EnterCriticalSection
0x1801026ca  nop     dword ptr [rax+rax+00h]
0x1801026cf  lea     rax, [rsi+7F0h]
0x1801026d6  lea     rdx, [rsp+330h+var_2F0]; bool *
0x1801026db  mov     qword ptr [rbp+230h+SystemTime.wYear], rax
0x1801026df  lea     rcx, [rbp+230h+SystemTime]; this
0x1801026e3  call    ?Lock@CAutoMutex@MutexUtils@@QEAAJPEA_N@Z; MutexUtils::CAutoMutex::Lock(bool *)
0x1801026e8  mov     ebx, eax
0x1801026ea  xor     eax, eax
0x1801026ec  test    ebx, ebx
0x1801026ee  js      loc_18010283F
0x1801026f4  cmp     [rsp+330h+var_2F0], al
0x1801026f8  jnz     loc_18010283A
0x1801026fe  cmp     [rsp+330h+var_2EC], 0C8h
0x180102706  jnz     loc_1801027C3
0x18010270c  cmp     [rsp+330h+var_2E0], rax
0x180102711  jz      loc_1801027C3
0x180102717  test    r14b, r14b
0x18010271a  jz      loc_1801027C3
0x180102720  lea     rdx, [rsi+1Eh]; lpNewFileName
0x180102724  lea     r8d, [rax+9]; dwFlags
0x180102728  lea     rcx, [rbp+230h+szHeaders]; lpExistingFileName
0x18010272c  call    cs:__imp_MoveFileExW
0x180102733  nop     dword ptr [rax+rax+00h]
0x180102738  xor     ebx, ebx
0x18010273a  test    eax, eax
0x18010273c  jnz     short loc_180102759
0x18010273e  call    cs:__imp_GetLastError
0x180102745  nop     dword ptr [rax+rax+00h]
0x18010274a  mov     ebx, eax
0x18010274c  xor     eax, eax
0x18010274e  test    ebx, ebx
0x180102750  jle     short loc_1801027C5
0x180102752  movzx   ebx, bx
0x180102755  or      ebx, edi
0x180102757  jmp     short loc_1801027C3
0x180102759  lea     rcx, [rsp+330h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18010275e  mov     qword ptr [rsp+330h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180102763  call    cs:__imp_GetSystemTimeAsFileTime
0x18010276a  nop     dword ptr [rax+rax+00h]
0x18010276f  mov     r8, cs:?IEVALUE_urlmon_ExtVerLastUpdateHighDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateHighDateTime
0x180102776  lea     rax, [rsp+330h+FileTime]
0x18010277b  mov     rdx, cs:?IEVALUE_urlmon_ExtVerLastUpdateLowDateTime@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_ExtVerLastUpdateLowDateTime
0x180102782  lea     r9, [rsp+330h+SystemTimeAsFileTime]
0x180102787  mov     [rsp+330h+dwService], ebx
0x18010278b  mov     rcx, rsi
0x18010278e  mov     qword ptr [rsp+330h+dwFlags], rax
0x180102793  call    ?_SetFileTimeWithFailureFallback@CVersionManagerServer@@AEAAJU?$VALUEID@K@SettingStore@@0PEAU_FILETIME@@1H@Z; CVersionManagerServer::_SetFileTimeWithFailureFallback(SettingStore::VALUEID<ulong>,SettingStore::VALUEID<ulong>,_FILETIME *,_FILETIME *,int)
0x180102798  mov     ebx, eax
0x18010279a  test    eax, eax
0x18010279c  js      loc_18010283F
0x1801027a2  lea     rdx, [rsp+330h+var_2E0]; struct CBlockListManager **
0x1801027a7  mov     rcx, rsi; this
0x1801027aa  call    ?_SwitchBlockListNotThreadSafe@CVersionManagerServer@@AEAAJPEAPEAVCBlockListManager@@H@Z; CVersionManagerServer::_SwitchBlockListNotThreadSafe(CBlockListManager * *,int)
  ... truncated ...
```
