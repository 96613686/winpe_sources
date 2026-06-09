# initsignal(void)

- ea: `0x10040b7c0`
- end: `0x10040ba60`
- name: `?initsignal@@YAXXZ`
- size: `672`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10040b7c0`
- `0x1004403d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10040b80f`
- `KERNEL32!EnterCriticalSection` at `0x10040b80f`
- `KERNEL32!SetThreadPriority` at `0x10040b9e9`
- `KERNEL32!SetThreadPriority` at `0x10040b9e9`
- `KERNEL32!LeaveCriticalSection` at `0x10040b987`
- `KERNEL32!LeaveCriticalSection` at `0x10040b987`
- `KERNEL32!InitializeCriticalSection` at `0x10040b802`
- `KERNEL32!InitializeCriticalSection` at `0x10040b802`
- `KERNEL32!SetErrorMode` at `0x10040ba42`
- `KERNEL32!SetErrorMode` at `0x10040ba42`
- `KERNEL32!CreateEventA` at `0x10040b92b`
- `KERNEL32!CreateEventA` at `0x10040b92b`
- `KERNEL32!SetThreadAffinityMask` at `0x10040b9f7`
- `KERNEL32!SetThreadAffinityMask` at `0x10040b9f7`
- `KERNEL32!CloseHandle` at `0x10040ba00`
- `KERNEL32!CloseHandle` at `0x10040ba00`
- `KERNEL32!GetLastError` at `0x10040b84d`
- `KERNEL32!GetLastError` at `0x10040b8dc`
- `KERNEL32!GetLastError` at `0x10040b93d`
- `KERNEL32!GetLastError` at `0x10040b84d`
- `KERNEL32!GetLastError` at `0x10040b8dc`
- `KERNEL32!GetLastError` at `0x10040b93d`
- `ADVAPI32!SetServiceStatus` at `0x10040b8d2`
- `ADVAPI32!SetServiceStatus` at `0x10040b8d2`
- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x10040b823`
- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x10040b823`
- `ADVAPI32!SetServiceBits` at `0x10040b843`
- `ADVAPI32!SetServiceBits` at `0x10040b843`
- `sqlmin!?SetCompleteSignalRoutine@StartUp@@SAXP6AXXZ@Z` at `0x10040ba15`
- `sqlmin!?SetCompleteSignalRoutine@StartUp@@SAXP6AXXZ@Z` at `0x10040ba15`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b883`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b919`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b97a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b9db`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b883`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b919`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b97a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x10040b9db`
- `sqldk!?completesignal@@YAXXZ` at `0x10040ba0e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040b860`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040b8ef`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040b950`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040b860`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040b8ef`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10040b950`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10040b9ac`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10040b9ac`

## string_xrefs

- `0x10040b956`: `initsignal:CreateEvent`

## pseudocode

```c
void initsignal(void)
{
  SERVICE_STATUS_HANDLE v0; // rax
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  DWORD v3; // eax
  wchar_t *v4; // rax
  DWORD v5; // eax
  wchar_t *v6; // rax
  void *v7; // rbx
  UINT v8; // ecx
  unsigned int ThrdAddr[4]; // [rsp+30h] [rbp-1028h] BYREF
  _BYTE v10[4096]; // [rsp+40h] [rbp-1018h] BYREF

  if ( *((_DWORD *)qword_10049F360 + 10544) )
  {
    InitializeCriticalSection(&SCMCrtSec);
    EnterCriticalSection(&SCMCrtSec);
    v0 = RegisterServiceCtrlHandlerA("sqlserver", (LPHANDLER_FUNCTION)SQLServiceCtrlHandler);
    SQLServiceHandle = v0;
    if ( !v0 || !SetServiceBits(v0, 4u, 1, 0) )
    {
      LastError = GetLastError();
      OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v10, 0, 0);
      scierrlog(0x42F5u, OSErrString);
      SQLExit(244, 17141, 1066);
    }
    SQLServiceStatus.dwServiceType = 16;
    SQLServiceStatus.dwServiceSpecificExitCode = 0;
    SQLServiceStatus.dwCurrentState = 2;
    *(_QWORD *)&SQLServiceStatus.dwControlsAccepted = 7;
    SQLServiceStatus.dwCheckPoint = 1;
    SQLServiceStatus.dwWaitHint = 20000;
    if ( !SetServiceStatus(SQLServiceHandle, &SQLServiceStatus) )
    {
      v3 = GetLastError();
      v4 = GetOSErrString(v3, (struct ErrorStringHolder *)v10, 0, 0);
      scierrlog(0x42F7u, L"initsignal", v4);
      SQLExit(245, 17143, 1066);
    }
    hEvent = CreateEventA(0, 1, 0, 0);
    if ( !hEvent )
    {
      v5 = GetLastError();
      v6 = GetOSErrString(v5, (struct ErrorStringHolder *)v10, 0, 0);
      scierrlog(0x42F7u, L"initsignal:CreateEvent", v6);
      SQLExit(246, 17143, 1066);
    }
    LeaveCriticalSection(&SCMCrtSec);
    v7 = (void *)_beginthreadex(0, 0, incrementsignal, (void *)2, 0, ThrdAddr);
    if ( !v7 )
    {
      scierrlog(0x42E0u, L"incrementsignal");
      SQLExit(247, 17120, 1066);
    }
    SetThreadPriority(v7, 2);
    SetThreadAffinityMask(v7, 1u);
    CloseHandle(v7);
  }
  StartUp::SetCompleteSignalRoutine((void (*)(void))completesignal);
  v8 = ((~*(_BYTE *)(qword_10049F340 + 451) & 0x10 | 4u) >> 2) | 4;
  if ( (*(_BYTE *)(qword_10049F340 + 451) & 8) == 0 )
    v8 = (~*(_BYTE *)(qword_10049F340 + 451) & 0x10 | 4u) >> 2;
  SetErrorMode(v8);
}

```

## disassembly

```asm
0x10040b7c0  mov     eax, 1058h
0x10040b7c5  call    _alloca_probe
0x10040b7ca  sub     rsp, rax
0x10040b7cd  mov     rax, cs:__security_cookie
0x10040b7d4  xor     rax, rsp
0x10040b7d7  mov     [rsp+1058h+var_18], rax
0x10040b7df  mov     rax, cs:qword_10049F360
0x10040b7e6  cmp     dword ptr [rax+0A4C0h], 0
0x10040b7ed  jz      loc_10040BA0E
0x10040b7f3  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040b7fa  mov     [rsp+1058h+var_8], rbx
0x10040b802  call    cs:__imp_InitializeCriticalSection
0x10040b808  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040b80f  call    cs:__imp_EnterCriticalSection
0x10040b815  lea     rdx, ?SQLServiceCtrlHandler@@YAXK@Z; lpHandlerProc
0x10040b81c  lea     rcx, ServiceName; "sqlserver"
0x10040b823  call    cs:__imp_RegisterServiceCtrlHandlerA
0x10040b829  mov     cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * SQLServiceHandle
0x10040b830  test    rax, rax
0x10040b833  jz      short loc_10040B84D
0x10040b835  xor     r9d, r9d; bUpdateImmediately
0x10040b838  mov     rcx, rax; hServiceStatus
0x10040b83b  lea     edx, [r9+4]; dwServiceBits
0x10040b83f  lea     r8d, [r9+1]; bSetBitsOn
0x10040b843  call    cs:__imp_SetServiceBits
0x10040b849  test    eax, eax
0x10040b84b  jnz     short loc_10040B889
0x10040b84d  call    cs:__imp_GetLastError
0x10040b853  xor     r9d, r9d
0x10040b856  lea     rdx, [rsp+1058h+var_1018]
0x10040b85b  mov     ecx, eax
0x10040b85d  xor     r8d, r8d
0x10040b860  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040b866  mov     rdx, rax
0x10040b869  mov     ecx, 42F5h; unsigned int
0x10040b86e  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040b873  mov     edx, 42F5h
0x10040b878  mov     ecx, 0F4h
0x10040b87d  mov     r8d, 42Ah
0x10040b883  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040b889  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040b890  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040b897  xor     ebx, ebx
0x10040b899  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS SQLServiceStatus ...
0x10040b8a3  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, ebx; _SERVICE_STATUS SQLServiceStatus ...
0x10040b8a9  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS SQLServiceStatus ...
0x10040b8b3  mov     qword ptr cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 7; _SERVICE_STATUS SQLServiceStatus ...
0x10040b8be  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS SQLServiceStatus ...
0x10040b8c8  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 4E20h; _SERVICE_STATUS SQLServiceStatus ...
0x10040b8d2  call    cs:__imp_SetServiceStatus
0x10040b8d8  test    eax, eax
0x10040b8da  jnz     short loc_10040B91F
0x10040b8dc  call    cs:__imp_GetLastError
0x10040b8e2  xor     r9d, r9d
0x10040b8e5  lea     rdx, [rsp+1058h+var_1018]
0x10040b8ea  mov     ecx, eax
0x10040b8ec  xor     r8d, r8d
0x10040b8ef  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040b8f5  lea     rdx, aInitsignal; "initsignal"
0x10040b8fc  mov     ecx, 42F7h; unsigned int
0x10040b901  mov     r8, rax
0x10040b904  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040b909  mov     edx, 42F7h
0x10040b90e  mov     ecx, 0F5h
0x10040b913  mov     r8d, 42Ah
0x10040b919  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040b91f  xor     r9d, r9d; lpName
0x10040b922  xor     r8d, r8d; bInitialState
0x10040b925  xor     ecx, ecx; lpEventAttributes
0x10040b927  lea     edx, [r9+1]; bManualReset
0x10040b92b  call    cs:__imp_CreateEventA
0x10040b931  mov     cs:hEvent, rax
0x10040b938  test    rax, rax
0x10040b93b  jnz     short loc_10040B980
0x10040b93d  call    cs:__imp_GetLastError
0x10040b943  xor     r9d, r9d
0x10040b946  lea     rdx, [rsp+1058h+var_1018]
0x10040b94b  mov     ecx, eax
0x10040b94d  xor     r8d, r8d
0x10040b950  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x10040b956  lea     rdx, aInitsignalCrea; "initsignal:CreateEvent"
0x10040b95d  mov     ecx, 42F7h; unsigned int
0x10040b962  mov     r8, rax
0x10040b965  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040b96a  mov     edx, 42F7h
0x10040b96f  mov     ecx, 0F6h
0x10040b974  mov     r8d, 42Ah
0x10040b97a  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040b980  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040b987  call    cs:__imp_LeaveCriticalSection
0x10040b98d  lea     rax, [rsp+1058h+var_1028]
0x10040b992  mov     r9d, 2; ArgList
0x10040b998  mov     [rsp+1058h+ThrdAddr], rax; ThrdAddr
0x10040b99d  lea     r8, ?incrementsignal@@YAIPEAX@Z; StartAddress
0x10040b9a4  xor     edx, edx; StackSize
0x10040b9a6  mov     [rsp+1058h+InitFlag], ebx; InitFlag
0x10040b9aa  xor     ecx, ecx; Security
0x10040b9ac  call    cs:__imp__beginthreadex
0x10040b9b2  mov     rbx, rax
0x10040b9b5  test    rax, rax
0x10040b9b8  jnz     short loc_10040B9E1
0x10040b9ba  lea     rdx, aIncrementsigna; "incrementsignal"
0x10040b9c1  mov     ecx, 42E0h; unsigned int
0x10040b9c6  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10040b9cb  mov     edx, 42E0h
0x10040b9d0  mov     ecx, 0F7h
0x10040b9d5  mov     r8d, 42Ah
0x10040b9db  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x10040b9e1  mov     edx, 2; nPriority
0x10040b9e6  mov     rcx, rbx; hThread
0x10040b9e9  call    cs:__imp_SetThreadPriority
0x10040b9ef  mov     edx, 1; dwThreadAffinityMask
0x10040b9f4  mov     rcx, rbx; hThread
0x10040b9f7  call    cs:__imp_SetThreadAffinityMask
0x10040b9fd  mov     rcx, rbx; hObject
0x10040ba00  call    cs:__imp_CloseHandle
0x10040ba06  mov     rbx, [rsp+1058h+var_8]
0x10040ba0e  mov     rcx, cs:__imp_?completesignal@@YAXXZ; completesignal(void)
0x10040ba15  call    cs:__imp_?SetCompleteSignalRoutine@StartUp@@SAXP6AXXZ@Z; StartUp::SetCompleteSignalRoutine(void (*)(void))
0x10040ba1b  mov     rax, cs:qword_10049F340
0x10040ba22  movzx   edx, byte ptr [rax+1C3h]
0x10040ba29  movzx   eax, dl
0x10040ba2c  not     al
0x10040ba2e  and     eax, 10h
0x10040ba31  or      eax, 4
0x10040ba34  shr     eax, 2
0x10040ba37  mov     ecx, eax
0x10040ba39  or      ecx, 4
0x10040ba3c  and     dl, 8
0x10040ba3f  cmovz   ecx, eax; uMode
0x10040ba42  call    cs:__imp_SetErrorMode
0x10040ba48  mov     rcx, [rsp+1058h+var_18]
0x10040ba50  xor     rcx, rsp; StackCookie
0x10040ba53  call    __security_check_cookie
0x10040ba58  add     rsp, 1058h
0x10040ba5f  retn
```
