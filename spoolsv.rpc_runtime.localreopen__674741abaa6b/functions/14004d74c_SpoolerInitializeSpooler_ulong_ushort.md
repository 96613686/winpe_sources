# SpoolerInitializeSpooler(ulong,ushort * *)

- ea: `0x14004d74c`
- end: `0x14004dcd1`
- name: `?SpoolerInitializeSpooler@@YAKKPEAPEAG@Z`
- size: `1413`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14004c580`

## callees

- `0x14000e7f0`
- `0x140015f18`
- `0x14001748c`
- `0x140018d8c`
- `0x14002cd10`
- `0x14002d0a0`
- `0x140031720`
- `0x140040788`
- `0x1400408b4`
- `0x14004d458`
- `0x14004d50c`
- `0x14004d74c`
- `0x14004dcd8`
- `0x140054600`
- `0x1400567f8`

## import_xrefs

- `USER32!RegisterPowerSettingNotification` at `0x14004db9a`
- `USER32!RegisterPowerSettingNotification` at `0x14004db9a`
- `ntdll!TpAllocPool` at `0x14004da2a`
- `ntdll!TpAllocPool` at `0x14004da2a`
- `ntdll!RtlNtStatusToDosError` at `0x14004da38`
- `ntdll!RtlNtStatusToDosError` at `0x14004da38`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14004d804`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14004d804`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004d931`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004d931`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d99c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d99c`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14004d884`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14004d884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004d869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004d869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dbb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dbb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dc9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004d79f`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004d7b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004d7c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004d79f`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004d7b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004d7c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14004dc3f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14004dc3f`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004d9d4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004d9d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004d957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004dc53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004d957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004dc53`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14004d97f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14004d97f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14004d8c0`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14004d8c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d849`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004d849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d85d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004d85d`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x14004d81d`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x14004d81d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14004da96`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14004da96`
- `GDI32!GdiDisableUMPDSandboxing` at `0x14004dbd0`
- `GDI32!GdiDisableUMPDSandboxing` at `0x14004dbd0`
- `SspiCli!LsaEnumerateLogonSessions` at `0x14004dad3`
- `SspiCli!LsaEnumerateLogonSessions` at `0x14004dad3`
- `SspiCli!LsaGetLogonSessionData` at `0x14004db0f`
- `SspiCli!LsaGetLogonSessionData` at `0x14004db0f`
- `SspiCli!LsaFreeReturnBuffer` at `0x14004db4a`
- `SspiCli!LsaFreeReturnBuffer` at `0x14004db70`
- `SspiCli!LsaFreeReturnBuffer` at `0x14004db4a`
- `SspiCli!LsaFreeReturnBuffer` at `0x14004db70`

## string_xrefs

- `0x14004d8a0`: `Calling RegisterServiceCtrlHandler.`
- `0x14004d8e4`: `RegisterServiceCtrlHandler failed. Error %d`
- `0x14004d83b`: `CLSID`
- `0x14004d9e1`: `Getting ready to start the RPC server.`
- `0x14004daa9`: `Leaving No Printer Mode due to service restart`
- `0x14004dc0e`: `Getting ready to kick off the router`
- `0x14004dc5f`: `Initialization complete`

## pseudocode

```c
unsigned int __fastcall SpoolerInitializeSpooler(int a1, unsigned __int16 **a2, int a3)
{
  DWORD v3; // eax
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rbx
  unsigned int v6; // edx
  int v7; // ecx
  unsigned int result; // eax
  HANDLE v9; // rbx
  DWORD v10; // eax
  NThreadingLibrary::TWorkCrew *v11; // rax
  __int64 v12; // rbx
  NTSTATUS v13; // eax
  signed int v14; // eax
  __int64 v15; // rdx
  bool v16; // sf
  ULONG v17; // eax
  ULONG v18; // ebx
  PSECURITY_LOGON_SESSION_DATA v19; // rcx
  DWORD v20; // eax
  unsigned int started; // eax
  unsigned int v22; // ebx
  HANDLE v23; // rax
  int v24; // ecx
  int v25; // r8d
  DWORD v26; // eax
  ULONG LogonSessionCount; // [rsp+30h] [rbp-48h] BYREF
  PLUID LogonSessionList; // [rsp+38h] [rbp-40h] BYREF
  int HeapInformation; // [rsp+40h] [rbp-38h] BYREF
  DWORD ThreadId; // [rsp+44h] [rbp-34h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData[2]; // [rsp+50h] [rbp-28h] BYREF

  HeapInformation = 2;
  ThreadId = 0;
  hKey = 0;
  if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      a1,
      (unsigned int)DocPerf_PhaseOneInit_Start,
      a3,
      1,
      (__int64)ppLogonSessionData);
  gdwTlsBindingHandle = TlsAlloc();
  gdwTlsSetJobIndex = TlsAlloc();
  v3 = TlsAlloc();
  gdwTlsSetPortIndex = v3;
  if ( gdwTlsBindingHandle == -1
    || gdwTlsSetJobIndex == -1
    || v3 == -1
    || !InitializeCriticalSectionAndSpinCount(&ThreadCriticalSection, 0x80000000) )
  {
    return 3;
  }
  SpoolerStatusInit();
  RegDisablePredefinedCacheEx();
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, &hKey) )
    RegCloseKey(hKey);
  ProcessHeap = GetProcessHeap();
  HeapSetInformation(ProcessHeap, HeapCompatibilityInformation, &HeapInformation, 4u);
  if ( !g_bWindowsProtectedPrintSpoolerWorkerEnabled )
  {
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerInitializeSpooler", L"Calling RegisterServiceCtrlHandler.");
    SpoolerStatusHandle = RegisterServiceCtrlHandlerExW(L"SPOOLER", SpoolerCtrlHandler, 0);
    if ( !SpoolerStatusHandle )
    {
      LastError = GetLastError();
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerInitializeSpooler",
        L"RegisterServiceCtrlHandler failed. Error %d",
        LastError);
      v6 = LastError;
      v7 = 0;
      return SpoolerBeginForcedShutdown(v7, v6, 0);
    }
  }
  result = SpoolerStatusUpdate(1u);
  SpoolerState = result;
  if ( result == 1 )
  {
    WaitForDebugger();
    while ( 1 )
    {
      v9 = OpenEventW(2u, 0, szSpoolerExitingEvent);
      if ( !v9 )
        break;
      SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerInitializeSpooler", L"Waiting for previous spooler to exit.");
      CloseHandle(v9);
      result = SpoolerStatusUpdate(1u);
      SpoolerState = result;
      if ( result != 1 )
        return result;
      Sleep(0xBB8u);
    }
    hPhase2Init = CreateEventW(0, 1, 0, L"RouterPreInitEvent");
    if ( !hPhase2Init )
    {
      v10 = GetLastError();
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerInitializeSpooler",
        L"Phase2Init event creation failed. Error %d",
        v10);
      ExitProcess(0);
    }
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerInitializeSpooler", L"Getting ready to start the RPC server.");
    v11 = (NThreadingLibrary::TWorkCrew *)operator new(0xE8u);
    if ( v11 )
      v12 = NThreadingLibrary::TWorkCrew::TWorkCrew(v11);
    else
      v12 = 0;
    g_pWorkCrew = (NThreadingLibrary::TWorkCrew *)v12;
    if ( *(int *)(v12 + 196) >= 0 )
    {
      v13 = TpAllocPool(v12 + 224, 0);
      v14 = RtlNtStatusToDosError(v13);
      v16 = v14 < 0;
      if ( v14 > 0 )
        v16 = 1;
      if ( !v16 )
        NThreadingLibrary::TTpSetWorkEnv::SetCallBackEnv(v12 + 16, v15, *(_QWORD *)(v12 + 224));
    }
    CheckTestMode();
    if ( HasPrintServerRole() )
    {
      SpoolerServiceTelemetry::WriteDbgTraceInfo(
        "SpoolerInitializeSpooler",
        L"Leaving No Printer Mode due to print server role");
      g_bNoPrintersMode = 0;
    }
    else
    {
      if ( g_bNoPrintersMode )
      {
        if ( GetTickCount() < 0x1D4C0 )
        {
          LogonSessionCount = 0;
          LogonSessionList = 0;
          if ( !LsaEnumerateLogonSessions(&LogonSessionCount, &LogonSessionList) )
          {
            v17 = LogonSessionCount;
            if ( LogonSessionCount )
            {
              v18 = 0;
              if ( g_bNoPrintersMode )
              {
                while ( v18 < v17 )
                {
                  ppLogonSessionData[0] = 0;
                  if ( !LsaGetLogonSessionData(&LogonSessionList[v18], ppLogonSessionData) )
                  {
                    v19 = ppLogonSessionData[0];
                    if ( ((ppLogonSessionData[0]->LogonType - 2) & 0xFFFFFFF7) == 0 )
                    {
                      SpoolerServiceTelemetry::WriteDbgTraceInfo(
                        "SpoolerInitializeSpooler",
                        L"Leaving No Printer Mode because there are interactive users logged on");
                      v19 = ppLogonSessionData[0];
                      g_bNoPrintersMode = 0;
                    }
                    LsaFreeReturnBuffer(v19);
                  }
                  ++v18;
                  if ( !g_bNoPrintersMode )
                    break;
                  v17 = LogonSessionCount;
                }
              }
            }
          }
          if ( LogonSessionList )
          {
            LsaFreeReturnBuffer(LogonSessionList);
            LogonSessionList = 0;
          }
        }
        else
        {
          SpoolerServiceTelemetry::WriteDbgTraceInfo(
            "SpoolerInitializeSpooler",
            L"Leaving No Printer Mode due to service restart");
          g_bNoPrintersMode = 0;
        }
      }
      if ( !g_bSpoolerIsChildProcess )
      {
        g_hPowerSettingNotification = RegisterPowerSettingNotification(SpoolerStatusHandle, &GUID_LOW_POWER_EPOCH, 1u);
        if ( !g_hPowerSettingNotification )
        {
          v20 = GetLastError();
          SpoolerServiceTelemetry::WriteDbgTraceError(
            "SpoolerInitializeSpooler",
            L"RegisterPowerSettingNotification failed. Error %d",
            v20);
        }
      }
    }
    GdiDisableUMPDSandboxing();
    started = SpoolerStartRpcServer();
    v22 = started;
    if ( started )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SpoolerInitializeSpooler",
        L"RPC Initialization failed. Error 0x%x",
        started);
      v6 = v22;
LABEL_50:
      v7 = 1;
      return SpoolerBeginForcedShutdown(v7, v6, 0);
    }
    SpoolerStatusUpdate(1u);
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerInitializeSpooler", L"Getting ready to kick off the router");
    v23 = CreateThread(0, 0x10000u, PreInitializeRouter, SpoolerStatusHandle, 0, &ThreadId);
    if ( v23 )
    {
      CloseHandle(v23);
    }
    else
    {
      v26 = GetLastError();
      if ( v26 )
      {
        v6 = v26;
        goto LABEL_50;
      }
    }
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerInitializeSpooler", L"Initialization complete");
    if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v24,
        (unsigned int)DocPerf_PhaseOneInit_Stop,
        v25,
        1,
        (__int64)ppLogonSessionData);
    return SpoolerStatusUpdate(2u);
  }
  return result;
}

```

## disassembly

```asm
0x14004d74c  push    rbp
0x14004d74e  push    rbx
0x14004d74f  push    rsi
0x14004d750  push    rdi
0x14004d751  push    r14
0x14004d753  push    r15
0x14004d755  mov     rbp, rsp
0x14004d758  sub     rsp, 78h
0x14004d75c  mov     rax, cs:__security_cookie
0x14004d763  xor     rax, rsp
0x14004d766  mov     [rbp+var_18], rax
0x14004d76a  xor     esi, esi
0x14004d76c  mov     [rbp+HeapInformation], 2
0x14004d773  mov     [rbp+ThreadId], esi
0x14004d776  mov     [rbp+hKey], rsi
0x14004d77a  lea     r14d, [rsi+1]
0x14004d77e  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x14004d785  jz      short loc_14004D79F
0x14004d787  lea     rax, [rbp+ppLogonSessionData]
0x14004d78b  mov     r9d, r14d
0x14004d78e  lea     rdx, DocPerf_PhaseOneInit_Start
0x14004d795  mov     [rsp+78h+phkResult], rax
0x14004d79a  call    McGenEventWrite_EtwEventWriteTransfer
0x14004d79f  call    cs:__imp_TlsAlloc
0x14004d7a6  nop     dword ptr [rax+rax+00h]
0x14004d7ab  mov     cs:?gdwTlsBindingHandle@@3KA, eax; ulong gdwTlsBindingHandle
0x14004d7b1  call    cs:__imp_TlsAlloc
0x14004d7b8  nop     dword ptr [rax+rax+00h]
0x14004d7bd  mov     cs:?gdwTlsSetJobIndex@@3KA, eax; ulong gdwTlsSetJobIndex
0x14004d7c3  call    cs:__imp_TlsAlloc
0x14004d7ca  nop     dword ptr [rax+rax+00h]
0x14004d7cf  or      ecx, 0FFFFFFFFh
0x14004d7d2  mov     cs:?gdwTlsSetPortIndex@@3KA, eax; ulong gdwTlsSetPortIndex
0x14004d7d8  cmp     cs:?gdwTlsBindingHandle@@3KA, ecx; ulong gdwTlsBindingHandle
0x14004d7de  jz      loc_14004DCB2
0x14004d7e4  cmp     cs:?gdwTlsSetJobIndex@@3KA, ecx; ulong gdwTlsSetJobIndex
0x14004d7ea  jz      loc_14004DCB2
0x14004d7f0  cmp     eax, ecx
0x14004d7f2  jz      loc_14004DCB2
0x14004d7f8  mov     edx, 80000000h; dwSpinCount
0x14004d7fd  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004d804  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14004d80b  nop     dword ptr [rax+rax+00h]
0x14004d810  test    eax, eax
0x14004d812  jz      loc_14004DCB2
0x14004d818  call    ?SpoolerStatusInit@@YAXXZ; SpoolerStatusInit(void)
0x14004d81d  call    cs:__imp_RegDisablePredefinedCacheEx
0x14004d824  nop     dword ptr [rax+rax+00h]
0x14004d829  lea     rax, [rbp+hKey]
0x14004d82d  mov     r9d, 20019h; samDesired
0x14004d833  xor     r8d, r8d; ulOptions
0x14004d836  mov     [rsp+78h+phkResult], rax; phkResult
0x14004d83b  lea     rdx, aClsid; "CLSID"
0x14004d842  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14004d849  call    cs:__imp_RegOpenKeyExW
0x14004d850  nop     dword ptr [rax+rax+00h]
0x14004d855  test    eax, eax
0x14004d857  jnz     short loc_14004D869
0x14004d859  mov     rcx, [rbp+hKey]; hKey
0x14004d85d  call    cs:__imp_RegCloseKey
0x14004d864  nop     dword ptr [rax+rax+00h]
0x14004d869  call    cs:__imp_GetProcessHeap
0x14004d870  nop     dword ptr [rax+rax+00h]
0x14004d875  mov     r9d, 4; HeapInformationLength
0x14004d87b  lea     r8, [rbp+HeapInformation]; HeapInformation
0x14004d87f  mov     rcx, rax; HeapHandle
0x14004d882  xor     edx, edx; HeapInformationClass
0x14004d884  call    cs:__imp_HeapSetInformation
0x14004d88b  nop     dword ptr [rax+rax+00h]
0x14004d890  cmp     cs:?g_bWindowsProtectedPrintSpoolerWorkerEnabled@@3_NA, sil; bool g_bWindowsProtectedPrintSpoolerWorkerEnabled
0x14004d897  lea     r15, aSpoolerinitial; "SpoolerInitializeSpooler"
0x14004d89e  jnz     short loc_14004D909
0x14004d8a0  lea     rdx, aCallingRegiste; "Calling RegisterServiceCtrlHandler."
0x14004d8a7  mov     rcx, r15; char *
0x14004d8aa  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d8af  xor     r8d, r8d; lpContext
0x14004d8b2  lea     rdx, ?SpoolerCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x14004d8b9  lea     rcx, ServiceName; "SPOOLER"
0x14004d8c0  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x14004d8c7  nop     dword ptr [rax+rax+00h]
0x14004d8cc  mov     cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * SpoolerStatusHandle
0x14004d8d3  test    rax, rax
0x14004d8d6  jnz     short loc_14004D909
0x14004d8d8  call    cs:__imp_GetLastError
0x14004d8df  nop     dword ptr [rax+rax+00h]
0x14004d8e4  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandler failed. Erro"...
0x14004d8eb  mov     rcx, r15; char *
0x14004d8ee  mov     r8d, eax
0x14004d8f1  mov     ebx, eax
0x14004d8f3  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004d8f8  xor     r8d, r8d; unsigned int
0x14004d8fb  mov     edx, ebx; unsigned int
0x14004d8fd  xor     ecx, ecx; int
0x14004d8ff  call    ?SpoolerBeginForcedShutdown@@YAKHKK@Z; SpoolerBeginForcedShutdown(int,ulong,ulong)
0x14004d904  jmp     loc_14004DCB7
0x14004d909  mov     ecx, r14d; unsigned int
0x14004d90c  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004d911  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x14004d917  cmp     eax, r14d
0x14004d91a  jnz     loc_14004DCB7
0x14004d920  call    ?WaitForDebugger@@YAXXZ; WaitForDebugger(void)
0x14004d925  xor     edx, edx; bInheritHandle
0x14004d927  lea     r8, ?szSpoolerExitingEvent@@3PAGA; "Spooler_exiting"
0x14004d92e  lea     ecx, [rdx+2]; dwDesiredAccess
0x14004d931  call    cs:__imp_OpenEventW
0x14004d938  nop     dword ptr [rax+rax+00h]
0x14004d93d  mov     rbx, rax
0x14004d940  test    rax, rax
0x14004d943  jz      short loc_14004D98D
0x14004d945  lea     rdx, aWaitingForPrev; "Waiting for previous spooler to exit."
0x14004d94c  mov     rcx, r15; char *
0x14004d94f  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d954  mov     rcx, rbx; hObject
0x14004d957  call    cs:__imp_CloseHandle
0x14004d95e  nop     dword ptr [rax+rax+00h]
0x14004d963  mov     ecx, r14d; unsigned int
0x14004d966  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004d96b  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x14004d971  cmp     eax, r14d
0x14004d974  jnz     loc_14004DCB7
0x14004d97a  mov     ecx, 0BB8h; dwMilliseconds
0x14004d97f  call    cs:__imp_Sleep
0x14004d986  nop     dword ptr [rax+rax+00h]
0x14004d98b  jmp     short loc_14004D925
0x14004d98d  lea     r9, Name; "RouterPreInitEvent"
0x14004d994  xor     r8d, r8d; bInitialState
0x14004d997  mov     edx, r14d; bManualReset
0x14004d99a  xor     ecx, ecx; lpEventAttributes
0x14004d99c  call    cs:__imp_CreateEventW
0x14004d9a3  nop     dword ptr [rax+rax+00h]
0x14004d9a8  mov     cs:?hPhase2Init@@3PEAXEA, rax; void * hPhase2Init
0x14004d9af  test    rax, rax
0x14004d9b2  jnz     short loc_14004D9E1
0x14004d9b4  call    cs:__imp_GetLastError
0x14004d9bb  nop     dword ptr [rax+rax+00h]
0x14004d9c0  lea     rdx, aPhase2initEven; "Phase2Init event creation failed. Error"...
0x14004d9c7  mov     rcx, r15; char *
0x14004d9ca  mov     r8d, eax
0x14004d9cd  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004d9d2  xor     ecx, ecx; uExitCode
0x14004d9d4  call    cs:__imp_ExitProcess
0x14004d9e1  lea     rdx, aGettingReadyTo; "Getting ready to start the RPC server."
0x14004d9e8  mov     rcx, r15; char *
0x14004d9eb  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d9f0  mov     ecx, 0E8h; Size
0x14004d9f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004d9fa  test    rax, rax
0x14004d9fd  jz      short loc_14004DA0C
0x14004d9ff  mov     rcx, rax; this
0x14004da02  call    ??0TWorkCrew@NThreadingLibrary@@QEAA@XZ; NThreadingLibrary::TWorkCrew::TWorkCrew(void)
0x14004da07  mov     rbx, rax
0x14004da0a  jmp     short loc_14004DA0F
0x14004da0c  mov     rbx, rsi
0x14004da0f  mov     cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA, rbx; NThreadingLibrary::TWorkCrew * g_pWorkCrew
0x14004da16  cmp     [rbx+0C4h], esi
0x14004da1c  jl      short loc_14004DA60
0x14004da1e  lea     rdi, [rbx+0E0h]
0x14004da25  xor     edx, edx
0x14004da27  mov     rcx, rdi
0x14004da2a  call    cs:__imp_TpAllocPool
0x14004da31  nop     dword ptr [rax+rax+00h]
0x14004da36  mov     ecx, eax; Status
0x14004da38  call    cs:__imp_RtlNtStatusToDosError
0x14004da3f  nop     dword ptr [rax+rax+00h]
0x14004da44  test    eax, eax
0x14004da46  jle     short loc_14004DA52
0x14004da48  movzx   eax, ax
0x14004da4b  or      eax, 80070000h
0x14004da50  test    eax, eax
0x14004da52  js      short loc_14004DA60
0x14004da54  mov     r8, [rdi]
0x14004da57  lea     rcx, [rbx+10h]
0x14004da5b  call    ?SetCallBackEnv@TTpSetWorkEnv@NThreadingLibrary@@QEAAJW4EWorkEnvironment@2@PEAX11@Z; NThreadingLibrary::TTpSetWorkEnv::SetCallBackEnv(NThreadingLibrary::EWorkEnvironment,void *,void *,void *)
0x14004da60  call    ?CheckTestMode@@YAXXZ; CheckTestMode(void)
0x14004da65  call    ?HasPrintServerRole@@YA_NXZ; HasPrintServerRole(void)
0x14004da6a  test    al, al
0x14004da6c  jz      short loc_14004DA89
0x14004da6e  lea     rdx, aLeavingNoPrint_3; "Leaving No Printer Mode due to print se"...
0x14004da75  mov     rcx, r15; char *
0x14004da78  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004da7d  mov     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004da84  jmp     loc_14004DBD0
0x14004da89  cmp     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004da90  jz      loc_14004DB80
0x14004da96  call    cs:__imp_GetTickCount
0x14004da9d  nop     dword ptr [rax+rax+00h]
0x14004daa2  cmp     eax, 1D4C0h
0x14004daa7  jb      short loc_14004DAC4
0x14004daa9  lea     rdx, aLeavingNoPrint_1; "Leaving No Printer Mode due to service "...
0x14004dab0  mov     rcx, r15; char *
0x14004dab3  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004dab8  mov     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004dabf  jmp     loc_14004DB80
0x14004dac4  lea     rdx, [rbp+LogonSessionList]; LogonSessionList
0x14004dac8  mov     [rbp+LogonSessionCount], esi
0x14004dacb  lea     rcx, [rbp+LogonSessionCount]; LogonSessionCount
0x14004dacf  mov     [rbp+LogonSessionList], rsi
0x14004dad3  call    cs:__imp_LsaEnumerateLogonSessions
0x14004dada  nop     dword ptr [rax+rax+00h]
0x14004dadf  test    eax, eax
0x14004dae1  jnz     loc_14004DB67
0x14004dae7  mov     eax, [rbp+LogonSessionCount]
0x14004daea  test    eax, eax
0x14004daec  jz      short loc_14004DB67
0x14004daee  cmp     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004daf5  mov     ebx, esi
0x14004daf7  jz      short loc_14004DB67
0x14004daf9  cmp     ebx, eax
0x14004dafb  jnb     short loc_14004DB67
0x14004dafd  mov     rax, [rbp+LogonSessionList]
0x14004db01  lea     rdx, [rbp+ppLogonSessionData]; ppLogonSessionData
0x14004db05  mov     ecx, ebx
0x14004db07  mov     [rbp+ppLogonSessionData], rsi
0x14004db0b  lea     rcx, [rax+rcx*8]; LogonId
0x14004db0f  call    cs:__imp_LsaGetLogonSessionData
0x14004db16  nop     dword ptr [rax+rax+00h]
0x14004db1b  test    eax, eax
0x14004db1d  jnz     short loc_14004DB56
0x14004db1f  mov     rcx, [rbp+ppLogonSessionData]
0x14004db23  mov     eax, [rcx+40h]
0x14004db26  sub     eax, 2
0x14004db29  test    eax, 0FFFFFFF7h
0x14004db2e  jnz     short loc_14004DB4A
0x14004db30  lea     rdx, aLeavingNoPrint_2; "Leaving No Printer Mode because there a"...
0x14004db37  mov     rcx, r15; char *
0x14004db3a  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004db3f  mov     rcx, [rbp+ppLogonSessionData]; Buffer
0x14004db43  mov     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004db4a  call    cs:__imp_LsaFreeReturnBuffer
0x14004db51  nop     dword ptr [rax+rax+00h]
0x14004db56  add     ebx, r14d
0x14004db59  cmp     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004db60  jz      short loc_14004DB67
0x14004db62  mov     eax, [rbp+LogonSessionCount]
0x14004db65  jmp     short loc_14004DAF9
0x14004db67  mov     rcx, [rbp+LogonSessionList]; Buffer
0x14004db6b  test    rcx, rcx
0x14004db6e  jz      short loc_14004DB80
0x14004db70  call    cs:__imp_LsaFreeReturnBuffer
0x14004db77  nop     dword ptr [rax+rax+00h]
0x14004db7c  mov     [rbp+LogonSessionList], rsi
0x14004db80  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, sil; bool g_bSpoolerIsChildProcess
0x14004db87  jnz     short loc_14004DBD0
0x14004db89  mov     rcx, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hRecipient
0x14004db90  lea     rdx, GUID_LOW_POWER_EPOCH; PowerSettingGuid
0x14004db97  mov     r8d, r14d; Flags
0x14004db9a  call    cs:__imp_RegisterPowerSettingNotification
0x14004dba1  nop     dword ptr [rax+rax+00h]
0x14004dba6  mov     cs:?g_hPowerSettingNotification@@3PEAXEA, rax; void * g_hPowerSettingNotification
0x14004dbad  test    rax, rax
0x14004dbb0  jnz     short loc_14004DBD0
0x14004dbb2  call    cs:__imp_GetLastError
0x14004dbb9  nop     dword ptr [rax+rax+00h]
0x14004dbbe  lea     rdx, aRegisterpowers; "RegisterPowerSettingNotification failed"...
0x14004dbc5  mov     rcx, r15; char *
0x14004dbc8  mov     r8d, eax
0x14004dbcb  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004dbd0  call    cs:__imp_GdiDisableUMPDSandboxing
0x14004dbd7  nop     dword ptr [rax+rax+00h]
0x14004dbdc  call    ?SpoolerStartRpcServer@@YAJXZ; SpoolerStartRpcServer(void)
0x14004dbe1  mov     ebx, eax
0x14004dbe3  test    eax, eax
0x14004dbe5  jz      short loc_14004DC06
0x14004dbe7  mov     r8d, eax
0x14004dbea  lea     rdx, aRpcInitializat; "RPC Initialization failed. Error 0x%x"
0x14004dbf1  mov     rcx, r15; char *
0x14004dbf4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004dbf9  mov     edx, ebx
0x14004dbfb  xor     r8d, r8d
0x14004dbfe  mov     ecx, r14d
0x14004dc01  jmp     loc_14004D8FF
0x14004dc06  mov     ecx, r14d; unsigned int
0x14004dc09  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004dc0e  lea     rdx, aGettingReadyTo_0; "Getting ready to kick off the router"
0x14004dc15  mov     rcx, r15; char *
0x14004dc18  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004dc1d  mov     r9, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; lpParameter
0x14004dc24  lea     rax, [rbp+ThreadId]
0x14004dc28  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x14004dc2d  lea     r8, ?PreInitializeRouter@@YAHPEAUSERVICE_STATUS_HANDLE__@@@Z; lpStartAddress
0x14004dc34  mov     edx, 10000h; dwStackSize
0x14004dc39  mov     dword ptr [rsp+78h+phkResult], esi; dwCreationFlags
0x14004dc3d  xor     ecx, ecx; lpThreadAttributes
0x14004dc3f  call    cs:__imp_CreateThread
0x14004dc46  nop     dword ptr [rax+rax+00h]
0x14004dc4b  test    rax, rax
0x14004dc4e  jz      short loc_14004DC9B
0x14004dc50  mov     rcx, rax; hObject
0x14004dc53  call    cs:__imp_CloseHandle
0x14004dc5a  nop     dword ptr [rax+rax+00h]
0x14004dc5f  lea     rdx, aInitialization; "Initialization complete"
0x14004dc66  mov     rcx, r15; char *
0x14004dc69  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004dc6e  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x14004dc75  jz      short loc_14004DC8F
0x14004dc77  lea     rax, [rbp+ppLogonSessionData]
0x14004dc7b  mov     r9d, r14d
0x14004dc7e  lea     rdx, DocPerf_PhaseOneInit_Stop
0x14004dc85  mov     [rsp+78h+phkResult], rax
0x14004dc8a  call    McGenEventWrite_EtwEventWriteTransfer
  ... truncated ...
```
