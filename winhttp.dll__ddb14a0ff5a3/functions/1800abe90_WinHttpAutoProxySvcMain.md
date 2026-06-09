# WinHttpAutoProxySvcMain

- ea: `0x1800abe90`
- end: `0x1800ac429`
- name: `WinHttpAutoProxySvcMain`
- size: `1433`
- prototype: `void()`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180041eb0`
- `0x18004eab4`
- `0x18005cfd8`
- `0x180070f1c`
- `0x1800865b4`
- `0x18008f814`
- `0x1800a1d10`
- `0x1800ab81c`
- `0x1800ab888`
- `0x1800abb3c`
- `0x1800abd90`
- `0x1800abe90`
- `0x1800c77ac`
- `0x1800cf008`
- `0x1800db6b0`
- `0x1800dbccc`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800abffb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ac034`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800abffb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800ac034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abf36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac3a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ac149`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ac189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ac1ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ac149`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ac189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ac1ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ac0ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ac0ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac1e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac1e6`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x1800abef2`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerSetFlags` at `0x1800abef2`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800ac322`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800ac322`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800ac218`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800ac2df`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800ac218`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800ac2df`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800abf24`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800abf24`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x1800abf7a`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x1800abf7a`

## string_xrefs

- `0x1800ac0dc`: `SYSTEM\CurrentControlSet\Services\WinHttpAutoProxySvc\Parameters`
- `0x1800ac2b4`: `EnableSessionStatusUpdates`

## pseudocode

```c
void WinHttpAutoProxySvcMain()
{
  SERVICE_STATUS_HANDLE v0; // rax
  DWORD LastError; // eax
  __int64 v2; // rdx
  unsigned int ServiceDirectory; // eax
  int v4; // eax
  int Directory; // eax
  int ProxyApi; // eax
  struct AUTOPROXY_RPC_SERVER **v7; // rcx
  int Instance; // eax
  unsigned int v9; // edi
  unsigned int v10; // eax
  HKEY v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // eax
  DWORD v14; // eax
  unsigned int (__fastcall *v15)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8)); // rax
  DWORD v16; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  DWORD Type; // [rsp+48h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-1Ch] BYREF
  int v23; // [rsp+58h] [rbp-18h] BYREF

  cbData = 4;
  v23 = 0;
  v22 = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 31, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids);
  WerSetFlags(2u);
  g_SvcStatus.dwServiceType = 32;
  *(_QWORD *)&g_SvcStatus.dwControlsAccepted = 0;
  *(_QWORD *)&g_SvcStatus.dwServiceSpecificExitCode = 0;
  g_SvcStatus.dwWaitHint = 0;
  v0 = RegisterServiceCtrlHandlerExW(L"WinHttpAutoProxySvc", SvcControl, 0);
  g_hSvcStatus = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
    {
      v2 = 32;
LABEL_51:
      WPP_SF_d(517, v2, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids, LastError, phkResult);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  g_fStateSeparationFallback = 0;
  phkResult = (PHKEY)&v23;
  ServiceDirectory = GetServiceDirectory(v0, 0, &g_wszServiceDirectoryPath, 261);
  if ( ServiceDirectory )
  {
    if ( (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_d(517, 33, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids, ServiceDirectory, &v23);
    v4 = 1;
    g_fStateSeparationFallback = 1;
  }
  else
  {
    v4 = g_fStateSeparationFallback;
  }
  if ( !v4 )
  {
    Directory = WxCreateDirectory(&g_wszServiceDirectoryPath);
    if ( Directory < 0 )
    {
      if ( (xmmword_180107A50 & 0x20) != 0 )
        WPP_SF_Sd(
          517,
          34,
          (unsigned int)WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids,
          (unsigned int)&g_wszServiceDirectoryPath,
          Directory);
      g_fStateSeparationFallback = 1;
    }
  }
  g_hSvcStopEvent = CreateEventA(0, 0, 0, 0);
  if ( !g_hSvcStopEvent )
  {
    LastError = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
    {
      v2 = 35;
      goto LABEL_51;
    }
LABEL_52:
    SvcCleanUp();
    if ( (xmmword_180107A60 & 0x20) == 0 )
      return;
    v12 = 46;
    goto LABEL_74;
  }
  g_hSvcTimerEvent = CreateEventA(0, 0, 0, 0);
  if ( !g_hSvcTimerEvent )
  {
    LastError = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
    {
      v2 = 36;
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  WinHttpInitializeEtw();
  SetProcessMitigations();
  ProxyApi = CRpcWatchDog::Start();
  if ( ProxyApi < 0 || (g_fWatchDogStarted = 1, ProxyApi = LoadProxyApi(1), ProxyApi < 0) )
  {
    WX_WIN32_FROM_HR((unsigned int)ProxyApi);
    goto LABEL_52;
  }
  g_fLoadedProxyApi = 1;
  Instance = AUTOPROXY_RPC_SERVER::CreateInstance(v7);
  if ( Instance < 0 )
  {
    WX_WIN32_FROM_HR((unsigned int)Instance);
    if ( (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_(517, 37, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids);
    goto LABEL_52;
  }
  v9 = 90000;
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\WinHttpAutoProxySvc\\Parameters",
          0,
          1u,
          &hKey);
  if ( v10 )
  {
    hKey = 0;
    if ( (xmmword_180107A50 & 0x20) == 0 )
      goto LABEL_45;
    WPP_SF_d(517, 38, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids, v10, phkResult);
  }
  if ( hKey )
  {
    if ( !RegQueryValueExW(hKey, L"EnableIdleShutdown", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data )
      g_fEnableIdleShutdown = 1;
    if ( !RegQueryValueExW(hKey, L"IdleTimeout", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data )
      g_dwIdleTimeout = *(_DWORD *)Data;
    if ( !RegQueryValueExW(hKey, L"IdleTimerInterval", 0, &Type, Data, &cbData) && Type == 4 && *(_DWORD *)Data )
      v9 = *(_DWORD *)Data;
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_45:
  g_SvcStatus.dwCurrentState = 2;
  g_SvcStatus.dwCheckPoint = 0;
  g_SvcStatus.dwWaitHint = 1000;
  if ( !SetServiceStatus(g_hSvcStatus, &g_SvcStatus) )
  {
    LastError = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
    {
      v2 = 39;
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  LastError = AUTOPROXY_RPC_SERVER::Open(g_pRpcSrv);
  g_SvcStatus.dwWaitHint = 0;
  if ( LastError )
  {
    g_SvcStatus.dwWin32ExitCode = 1066;
    g_SvcStatus.dwServiceSpecificExitCode = LastError;
    if ( (xmmword_180107A50 & 0x20) != 0 )
    {
      v2 = 40;
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  g_SvcStatus.dwCurrentState = 4;
  g_SvcStatus.dwControlsAccepted = 68;
  if ( !InternetReadRegistryDwordKey(
          v11,
          L"EnableSessionStatusUpdates",
          &v22,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp")
    && v22 )
  {
    g_SvcStatus.dwControlsAccepted |= 0x80u;
  }
  if ( !SetServiceStatus(g_hSvcStatus, &g_SvcStatus) )
  {
    v13 = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_d(517, 41, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids, v13, phkResult);
  }
  LODWORD(phkResult) = 0;
  g_hSvcTimerWait = (HANDLE)RegisterWaitForSingleObjectEx(g_hSvcTimerEvent, SvcTimer, 0, v9);
  if ( !g_hSvcTimerWait )
  {
    v14 = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_d(517, 42, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids, v14, phkResult);
LABEL_71:
    SvcStop(0, 0);
    goto LABEL_72;
  }
  if ( !g_pSvcHostGlobalData
    || (v15 = (unsigned int (__fastcall *)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8)))*((_QWORD *)g_pSvcHostGlobalData + 24)) == 0 )
  {
    if ( (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_(517, 43, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids);
    goto LABEL_71;
  }
  if ( v15(&g_hSvcStopWait, L"WinHttpAutoProxySvc", g_hSvcStopEvent, SvcStop) )
  {
    v16 = GetLastError();
    if ( (xmmword_180107A50 & 0x20) != 0 )
      WPP_SF_d(517, 44, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids, v16, 0);
    g_hSvcStopWait = 0;
    goto LABEL_71;
  }
LABEL_72:
  if ( (xmmword_180107A60 & 0x20) == 0 )
    return;
  v12 = 45;
LABEL_74:
  WPP_SF_(1029, v12, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids);
}

```

## disassembly

```asm
0x1800abe90  push    rbp
0x1800abe92  push    rbx
0x1800abe93  push    rsi
0x1800abe94  push    rdi
0x1800abe95  push    r12
0x1800abe97  push    r14
0x1800abe99  push    r15
0x1800abe9b  mov     rbp, rsp
0x1800abe9e  sub     rsp, 70h
0x1800abea2  mov     rax, cs:__security_cookie
0x1800abea9  xor     rax, rsp
0x1800abeac  mov     [rbp+var_10], rax
0x1800abeb0  xor     esi, esi
0x1800abeb2  mov     [rbp+cbData], 4
0x1800abeb9  mov     [rbp+var_18], esi
0x1800abebc  mov     [rbp+var_1C], esi
0x1800abebf  mov     [rbp+hKey], rsi
0x1800abec3  mov     dword ptr [rbp+Data], esi
0x1800abec6  mov     [rbp+Type], esi
0x1800abec9  lea     r14d, [rsi+20h]
0x1800abecd  test    byte ptr cs:xmmword_180107A60, r14b
0x1800abed4  lea     r15, WPP_c5b5079310a03897ce1667ae9e4aa974_Traceguids
0x1800abedb  jz      short loc_1800ABEED
0x1800abedd  lea     edx, [rsi+1Fh]
0x1800abee0  mov     ecx, 405h
0x1800abee5  mov     r8, r15
0x1800abee8  call    WPP_SF_
0x1800abeed  mov     ecx, 2; dwFlags
0x1800abef2  call    cs:__imp_WerSetFlags
0x1800abef8  xor     r8d, r8d; lpContext
0x1800abefb  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceType, r14d; _SERVICE_STATUS g_SvcStatus ...
0x1800abf02  lea     rdx, ?SvcControl@@YAKKKPEAX0@Z; lpHandlerProc
0x1800abf09  mov     qword ptr cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, rsi; _SERVICE_STATUS g_SvcStatus ...
0x1800abf10  lea     rcx, ServiceName; "WinHttpAutoProxySvc"
0x1800abf17  mov     qword ptr cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, rsi; _SERVICE_STATUS g_SvcStatus ...
0x1800abf1e  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, esi; _SERVICE_STATUS g_SvcStatus ...
0x1800abf24  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800abf2a  mov     cs:?g_hSvcStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hSvcStatus
0x1800abf31  test    rax, rax
0x1800abf34  jnz     short loc_1800ABF56
0x1800abf36  call    cs:__imp_GetLastError
0x1800abf3c  test    byte ptr cs:xmmword_180107A50, r14b
0x1800abf43  jz      loc_1800AC279
0x1800abf49  mov     edx, r14d
0x1800abf4c  mov     ecx, 205h
0x1800abf51  jmp     loc_1800AC26E
0x1800abf56  lea     rcx, [rbp+var_18]
0x1800abf5a  mov     cs:?g_fStateSeparationFallback@@3HA, esi; int g_fStateSeparationFallback
0x1800abf60  mov     [rsp+70h+phkResult], rcx
0x1800abf65  lea     rdi, ?g_wszServiceDirectoryPath@@3PAGA; ushort near * g_wszServiceDirectoryPath
0x1800abf6c  mov     rcx, rax
0x1800abf6f  mov     r9d, 105h
0x1800abf75  mov     r8, rdi
0x1800abf78  xor     edx, edx
0x1800abf7a  call    cs:__imp_GetServiceDirectory
0x1800abf80  mov     ebx, 205h
0x1800abf85  mov     r12d, 1
0x1800abf8b  test    eax, eax
0x1800abf8d  jz      short loc_1800ABFB5
0x1800abf8f  test    byte ptr cs:xmmword_180107A50, r14b
0x1800abf96  jz      short loc_1800ABFAA
0x1800abf98  lea     edx, [r12+20h]
0x1800abf9d  mov     ecx, ebx
0x1800abf9f  mov     r9d, eax
0x1800abfa2  mov     r8, r15
0x1800abfa5  call    WPP_SF_d
0x1800abfaa  mov     eax, r12d
0x1800abfad  mov     cs:?g_fStateSeparationFallback@@3HA, eax; int g_fStateSeparationFallback
0x1800abfb3  jmp     short loc_1800ABFBB
0x1800abfb5  mov     eax, cs:?g_fStateSeparationFallback@@3HA; int g_fStateSeparationFallback
0x1800abfbb  test    eax, eax
0x1800abfbd  jnz     short loc_1800ABFF1
0x1800abfbf  mov     rcx, rdi; unsigned __int16 *
0x1800abfc2  call    ?WxCreateDirectory@@YAJPEBG@Z; WxCreateDirectory(ushort const *)
0x1800abfc7  test    eax, eax
0x1800abfc9  jns     short loc_1800ABFF1
0x1800abfcb  test    byte ptr cs:xmmword_180107A50, r14b
0x1800abfd2  jz      short loc_1800ABFEA
0x1800abfd4  mov     edx, 22h ; '"'
0x1800abfd9  mov     dword ptr [rsp+70h+phkResult], eax
0x1800abfdd  mov     ecx, ebx
0x1800abfdf  mov     r9, rdi
0x1800abfe2  mov     r8, r15
0x1800abfe5  call    WPP_SF_Sd
0x1800abfea  mov     cs:?g_fStateSeparationFallback@@3HA, r12d; int g_fStateSeparationFallback
0x1800abff1  xor     r9d, r9d; lpName
0x1800abff4  xor     r8d, r8d; bInitialState
0x1800abff7  xor     edx, edx; bManualReset
0x1800abff9  xor     ecx, ecx; lpEventAttributes
0x1800abffb  call    cs:__imp_CreateEventA
0x1800ac001  mov     cs:?g_hSvcStopEvent@@3PEAXEA, rax; void * g_hSvcStopEvent
0x1800ac008  test    rax, rax
0x1800ac00b  jnz     short loc_1800AC02A
0x1800ac00d  call    cs:__imp_GetLastError
0x1800ac013  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac01a  jz      loc_1800AC279
0x1800ac020  mov     edx, 23h ; '#'
0x1800ac025  jmp     loc_1800AC26C
0x1800ac02a  xor     r9d, r9d; lpName
0x1800ac02d  xor     r8d, r8d; bInitialState
0x1800ac030  xor     edx, edx; bManualReset
0x1800ac032  xor     ecx, ecx; lpEventAttributes
0x1800ac034  call    cs:__imp_CreateEventA
0x1800ac03a  mov     cs:?g_hSvcTimerEvent@@3PEAXEA, rax; void * g_hSvcTimerEvent
0x1800ac041  test    rax, rax
0x1800ac044  jnz     short loc_1800AC063
0x1800ac046  call    cs:__imp_GetLastError
0x1800ac04c  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac053  jz      loc_1800AC279
0x1800ac059  mov     edx, 24h ; '$'
0x1800ac05e  jmp     loc_1800AC26C
0x1800ac063  call    ?WinHttpInitializeEtw@@YAXXZ; WinHttpInitializeEtw(void)
0x1800ac068  call    ?SetProcessMitigations@@YAXXZ; SetProcessMitigations(void)
0x1800ac06d  call    ?Start@CRpcWatchDog@@QEAAJW4_WatchDogReportType@@@Z; CRpcWatchDog::Start(_WatchDogReportType)
0x1800ac072  test    eax, eax
0x1800ac074  jns     short loc_1800AC082
0x1800ac076  mov     ecx, eax
0x1800ac078  call    WX_WIN32_FROM_HR
0x1800ac07d  jmp     loc_1800AC279
0x1800ac082  mov     ecx, r12d; int
0x1800ac085  mov     cs:?g_fWatchDogStarted@@3HA, r12d; int g_fWatchDogStarted
0x1800ac08c  call    ?LoadProxyApi@@YAJH@Z; LoadProxyApi(int)
0x1800ac091  test    eax, eax
0x1800ac093  js      short loc_1800AC076
0x1800ac095  mov     cs:?g_fLoadedProxyApi@@3HA, r12d; int g_fLoadedProxyApi
0x1800ac09c  call    ?CreateInstance@AUTOPROXY_RPC_SERVER@@SAJPEAPEAV1@@Z; AUTOPROXY_RPC_SERVER::CreateInstance(AUTOPROXY_RPC_SERVER * *)
0x1800ac0a1  test    eax, eax
0x1800ac0a3  jns     short loc_1800AC0CD
0x1800ac0a5  mov     ecx, eax
0x1800ac0a7  call    WX_WIN32_FROM_HR
0x1800ac0ac  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac0b3  jz      loc_1800AC279
0x1800ac0b9  mov     edx, 25h ; '%'
0x1800ac0be  mov     ecx, ebx
0x1800ac0c0  mov     r8, r15
0x1800ac0c3  call    WPP_SF_
0x1800ac0c8  jmp     loc_1800AC279
0x1800ac0cd  lea     rax, [rbp+hKey]
0x1800ac0d1  mov     r9d, r12d; samDesired
0x1800ac0d4  xor     r8d, r8d; ulOptions
0x1800ac0d7  mov     [rsp+70h+phkResult], rax; phkResult
0x1800ac0dc  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Wi"...
0x1800ac0e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ac0ea  mov     edi, 15F90h
0x1800ac0ef  call    cs:__imp_RegOpenKeyExW
0x1800ac0f5  test    eax, eax
0x1800ac0f7  jz      short loc_1800AC11C
0x1800ac0f9  mov     [rbp+hKey], rsi
0x1800ac0fd  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac104  jz      loc_1800AC1F0
0x1800ac10a  mov     edx, 26h ; '&'
0x1800ac10f  mov     ecx, ebx
0x1800ac111  mov     r9d, eax
0x1800ac114  mov     r8, r15
0x1800ac117  call    WPP_SF_d
0x1800ac11c  mov     rcx, [rbp+hKey]; hKey
0x1800ac120  test    rcx, rcx
0x1800ac123  jz      loc_1800AC1F0
0x1800ac129  lea     rax, [rbp+cbData]
0x1800ac12d  xor     r8d, r8d; lpReserved
0x1800ac130  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800ac135  lea     r9, [rbp+Type]; lpType
0x1800ac139  lea     rax, [rbp+Data]
0x1800ac13d  lea     rdx, aEnableidleshut; "EnableIdleShutdown"
0x1800ac144  mov     [rsp+70h+phkResult], rax; lpData
0x1800ac149  call    cs:__imp_RegQueryValueExW
0x1800ac14f  test    eax, eax
0x1800ac151  jnz     short loc_1800AC165
0x1800ac153  cmp     [rbp+Type], 4
0x1800ac157  jnz     short loc_1800AC165
0x1800ac159  cmp     dword ptr [rbp+Data], esi
0x1800ac15c  jz      short loc_1800AC165
0x1800ac15e  mov     cs:?g_fEnableIdleShutdown@@3HA, r12d; int g_fEnableIdleShutdown
0x1800ac165  mov     rcx, [rbp+hKey]; hKey
0x1800ac169  lea     rax, [rbp+cbData]
0x1800ac16d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800ac172  lea     r9, [rbp+Type]; lpType
0x1800ac176  lea     rax, [rbp+Data]
0x1800ac17a  xor     r8d, r8d; lpReserved
0x1800ac17d  lea     rdx, aIdletimeout; "IdleTimeout"
0x1800ac184  mov     [rsp+70h+phkResult], rax; lpData
0x1800ac189  call    cs:__imp_RegQueryValueExW
0x1800ac18f  test    eax, eax
0x1800ac191  jnz     short loc_1800AC1A6
0x1800ac193  cmp     [rbp+Type], 4
0x1800ac197  jnz     short loc_1800AC1A6
0x1800ac199  mov     eax, dword ptr [rbp+Data]
0x1800ac19c  test    eax, eax
0x1800ac19e  jz      short loc_1800AC1A6
0x1800ac1a0  mov     cs:?g_dwIdleTimeout@@3KA, eax; ulong g_dwIdleTimeout
0x1800ac1a6  mov     rcx, [rbp+hKey]; hKey
0x1800ac1aa  lea     rax, [rbp+cbData]
0x1800ac1ae  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800ac1b3  lea     r9, [rbp+Type]; lpType
0x1800ac1b7  lea     rax, [rbp+Data]
0x1800ac1bb  xor     r8d, r8d; lpReserved
0x1800ac1be  lea     rdx, aIdletimerinter; "IdleTimerInterval"
0x1800ac1c5  mov     [rsp+70h+phkResult], rax; lpData
0x1800ac1ca  call    cs:__imp_RegQueryValueExW
0x1800ac1d0  test    eax, eax
0x1800ac1d2  jnz     short loc_1800AC1E2
0x1800ac1d4  cmp     [rbp+Type], 4
0x1800ac1d8  jnz     short loc_1800AC1E2
0x1800ac1da  mov     eax, dword ptr [rbp+Data]
0x1800ac1dd  test    eax, eax
0x1800ac1df  cmovnz  edi, eax
0x1800ac1e2  mov     rcx, [rbp+hKey]; hKey
0x1800ac1e6  call    cs:__imp_RegCloseKey
0x1800ac1ec  mov     [rbp+hKey], rsi
0x1800ac1f0  mov     rcx, cs:?g_hSvcStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800ac1f7  lea     rdx, ?g_SvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800ac1fe  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_SvcStatus ...
0x1800ac208  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, esi; _SERVICE_STATUS g_SvcStatus ...
0x1800ac20e  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 3E8h; _SERVICE_STATUS g_SvcStatus ...
0x1800ac218  call    cs:__imp_SetServiceStatus
0x1800ac21e  test    eax, eax
0x1800ac220  jnz     short loc_1800AC238
0x1800ac222  call    cs:__imp_GetLastError
0x1800ac228  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac22f  jz      short loc_1800AC279
0x1800ac231  mov     edx, 27h ; '''
0x1800ac236  jmp     short loc_1800AC26C
0x1800ac238  mov     rcx, cs:?g_pRpcSrv@@3PEAVAUTOPROXY_RPC_SERVER@@EA; this
0x1800ac23f  call    ?Open@AUTOPROXY_RPC_SERVER@@QEAAJXZ; AUTOPROXY_RPC_SERVER::Open(void)
0x1800ac244  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, esi; _SERVICE_STATUS g_SvcStatus ...
0x1800ac24a  test    eax, eax
0x1800ac24c  jz      short loc_1800AC295
0x1800ac24e  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS g_SvcStatus ...
0x1800ac258  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, eax; _SERVICE_STATUS g_SvcStatus ...
0x1800ac25e  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac265  jz      short loc_1800AC279
0x1800ac267  mov     edx, 28h ; '('
0x1800ac26c  mov     ecx, ebx
0x1800ac26e  mov     r9d, eax
0x1800ac271  mov     r8, r15
0x1800ac274  call    WPP_SF_d
0x1800ac279  call    ?SvcCleanUp@@YAXXZ; SvcCleanUp(void)
0x1800ac27e  test    byte ptr cs:xmmword_180107A60, r14b
0x1800ac285  jz      loc_1800AC40E
0x1800ac28b  mov     edx, 2Eh ; '.'
0x1800ac290  jmp     loc_1800AC401
0x1800ac295  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800ac29c  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_SvcStatus ...
0x1800ac2a6  lea     r8, [rbp+var_1C]; unsigned int *
0x1800ac2aa  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 44h ; 'D'; _SERVICE_STATUS g_SvcStatus ...
0x1800ac2b4  lea     rdx, aEnablesessions; "EnableSessionStatusUpdates"
0x1800ac2bb  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x1800ac2c0  test    eax, eax
0x1800ac2c2  jnz     short loc_1800AC2D1
0x1800ac2c4  cmp     [rbp+var_1C], esi
0x1800ac2c7  jz      short loc_1800AC2D1
0x1800ac2c9  bts     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 7; _SERVICE_STATUS g_SvcStatus ...
0x1800ac2d1  mov     rcx, cs:?g_hSvcStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800ac2d8  lea     rdx, ?g_SvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800ac2df  call    cs:__imp_SetServiceStatus
0x1800ac2e5  test    eax, eax
0x1800ac2e7  jnz     short loc_1800AC30A
0x1800ac2e9  call    cs:__imp_GetLastError
0x1800ac2ef  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac2f6  jz      short loc_1800AC30A
0x1800ac2f8  mov     edx, 29h ; ')'
0x1800ac2fd  mov     ecx, ebx
0x1800ac2ff  mov     r9d, eax
0x1800ac302  mov     r8, r15
0x1800ac305  call    WPP_SF_d
0x1800ac30a  mov     rcx, cs:?g_hSvcTimerEvent@@3PEAXEA; void * g_hSvcTimerEvent
0x1800ac311  lea     rdx, ?SvcTimer@@YAXPEAXE@Z; SvcTimer(void *,uchar)
0x1800ac318  mov     r9d, edi
0x1800ac31b  mov     dword ptr [rsp+70h+phkResult], esi
0x1800ac31f  xor     r8d, r8d
0x1800ac322  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800ac328  mov     cs:?g_hSvcTimerWait@@3PEAXEA, rax; void * g_hSvcTimerWait
0x1800ac32f  test    rax, rax
0x1800ac332  jnz     short loc_1800AC35E
0x1800ac334  call    cs:__imp_GetLastError
0x1800ac33a  test    byte ptr cs:xmmword_180107A50, r14b
0x1800ac341  jz      loc_1800AC3EA
0x1800ac347  mov     edx, 2Ah ; '*'
0x1800ac34c  mov     ecx, ebx
0x1800ac34e  mov     r9d, eax
0x1800ac351  mov     r8, r15
0x1800ac354  call    WPP_SF_d
0x1800ac359  jmp     loc_1800AC3EA
0x1800ac35e  mov     rax, cs:?g_pSvcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvcHostGlobalData
0x1800ac365  test    rax, rax
0x1800ac368  jz      short loc_1800AC3D2
0x1800ac36a  mov     rax, [rax+0C0h]
0x1800ac371  test    rax, rax
0x1800ac374  jz      short loc_1800AC3D2
0x1800ac376  mov     r8, cs:?g_hSvcStopEvent@@3PEAXEA; void * g_hSvcStopEvent
0x1800ac37d  lea     r9, ?SvcStop@@YAXPEAXE@Z; SvcStop(void *,uchar)
0x1800ac384  mov     dword ptr [rsp+70h+lpcbData], 8
0x1800ac38c  lea     rdx, ServiceName; "WinHttpAutoProxySvc"
0x1800ac393  lea     rcx, ?g_hSvcStopWait@@3PEAXEA; void * g_hSvcStopWait
0x1800ac39a  mov     [rsp+70h+phkResult], rsi
0x1800ac39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac3a4  test    eax, eax
0x1800ac3a6  jz      short loc_1800AC3F3
0x1800ac3a8  call    cs:__imp_GetLastError
0x1800ac3ae  test    byte ptr cs:xmmword_180107A50, r14b
  ... truncated ...
```
