# SpoolerInitializeSpooler(ulong,ushort * *)

- ea: `0x1400490bc`
- end: `0x140049588`
- name: `?SpoolerInitializeSpooler@@YAKKPEAPEAG@Z`
- size: `1228`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140048140`

## callees

- `0x14000d5e4`
- `0x140014c34`
- `0x1400160a0`
- `0x1400178c4`
- `0x14002a830`
- `0x14002abc0`
- `0x14002f030`
- `0x14003ce38`
- `0x14003cf44`
- `0x140048e04`
- `0x140048eac`
- `0x1400490bc`
- `0x140049590`
- `0x14004f988`
- `0x1400518a4`

## import_xrefs

- `USER32!RegisterPowerSettingNotification` at `0x140049476`
- `USER32!RegisterPowerSettingNotification` at `0x140049476`
- `ntdll!TpAllocPool` at `0x140049334`
- `ntdll!TpAllocPool` at `0x140049334`
- `ntdll!RtlNtStatusToDosError` at `0x14004933c`
- `ntdll!RtlNtStatusToDosError` at `0x14004933c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140049162`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140049162`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004925f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004925f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400492b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400492b8`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400491c4`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400491c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400491af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400491af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004920c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400492ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004920c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400492ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049559`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004910f`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004911b`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x140049127`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004910f`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x14004911b`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x140049127`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140049509`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140049509`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400492e4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400492e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004927f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140049517`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004927f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140049517`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400492a1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400492a1`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1400491fa`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1400491fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004919b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004919b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400491a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400491a9`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x140049175`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x140049175`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140049394`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140049394`
- `GDI32!GdiDisableUMPDSandboxing` at `0x1400494a0`
- `GDI32!GdiDisableUMPDSandboxing` at `0x1400494a0`
- `SspiCli!LsaEnumerateLogonSessions` at `0x1400493cb`
- `SspiCli!LsaEnumerateLogonSessions` at `0x1400493cb`
- `SspiCli!LsaGetLogonSessionData` at `0x1400493fd`
- `SspiCli!LsaGetLogonSessionData` at `0x1400493fd`
- `SspiCli!LsaFreeReturnBuffer` at `0x140049432`
- `SspiCli!LsaFreeReturnBuffer` at `0x140049452`
- `SspiCli!LsaFreeReturnBuffer` at `0x140049432`
- `SspiCli!LsaFreeReturnBuffer` at `0x140049452`

## string_xrefs

- `0x1400491da`: `Calling RegisterServiceCtrlHandler.`
- `0x140049212`: `RegisterServiceCtrlHandler failed. Error %d`
- `0x14004918d`: `CLSID`
- `0x1400492eb`: `Getting ready to start the RPC server.`
- `0x1400493a1`: `Leaving No Printer Mode due to service restart`
- `0x1400494d8`: `Getting ready to kick off the router`
- `0x14004951d`: `Initialization complete`

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
0x1400490bc  push    rbp
0x1400490be  push    rbx
0x1400490bf  push    rsi
0x1400490c0  push    rdi
0x1400490c1  push    r14
0x1400490c3  push    r15
0x1400490c5  mov     rbp, rsp
0x1400490c8  sub     rsp, 78h
0x1400490cc  mov     rax, cs:__security_cookie
0x1400490d3  xor     rax, rsp
0x1400490d6  mov     [rbp+var_18], rax
0x1400490da  xor     esi, esi
0x1400490dc  mov     [rbp+HeapInformation], 2
0x1400490e3  mov     [rbp+ThreadId], esi
0x1400490e6  mov     [rbp+hKey], rsi
0x1400490ea  lea     r14d, [rsi+1]
0x1400490ee  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x1400490f5  jz      short loc_14004910F
0x1400490f7  lea     rax, [rbp+ppLogonSessionData]
0x1400490fb  mov     r9d, r14d
0x1400490fe  lea     rdx, DocPerf_PhaseOneInit_Start
0x140049105  mov     [rsp+78h+phkResult], rax
0x14004910a  call    McGenEventWrite_EtwEventWriteTransfer
0x14004910f  call    cs:__imp_TlsAlloc
0x140049115  mov     cs:?gdwTlsBindingHandle@@3KA, eax; ulong gdwTlsBindingHandle
0x14004911b  call    cs:__imp_TlsAlloc
0x140049121  mov     cs:?gdwTlsSetJobIndex@@3KA, eax; ulong gdwTlsSetJobIndex
0x140049127  call    cs:__imp_TlsAlloc
0x14004912d  or      ecx, 0FFFFFFFFh
0x140049130  mov     cs:?gdwTlsSetPortIndex@@3KA, eax; ulong gdwTlsSetPortIndex
0x140049136  cmp     cs:?gdwTlsBindingHandle@@3KA, ecx; ulong gdwTlsBindingHandle
0x14004913c  jz      loc_14004956A
0x140049142  cmp     cs:?gdwTlsSetJobIndex@@3KA, ecx; ulong gdwTlsSetJobIndex
0x140049148  jz      loc_14004956A
0x14004914e  cmp     eax, ecx
0x140049150  jz      loc_14004956A
0x140049156  mov     edx, 80000000h; dwSpinCount
0x14004915b  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140049162  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140049168  test    eax, eax
0x14004916a  jz      loc_14004956A
0x140049170  call    ?SpoolerStatusInit@@YAXXZ; SpoolerStatusInit(void)
0x140049175  call    cs:__imp_RegDisablePredefinedCacheEx
0x14004917b  lea     rax, [rbp+hKey]
0x14004917f  mov     r9d, 20019h; samDesired
0x140049185  xor     r8d, r8d; ulOptions
0x140049188  mov     [rsp+78h+phkResult], rax; phkResult
0x14004918d  lea     rdx, aClsid; "CLSID"
0x140049194  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14004919b  call    cs:__imp_RegOpenKeyExW
0x1400491a1  test    eax, eax
0x1400491a3  jnz     short loc_1400491AF
0x1400491a5  mov     rcx, [rbp+hKey]; hKey
0x1400491a9  call    cs:__imp_RegCloseKey
0x1400491af  call    cs:__imp_GetProcessHeap
0x1400491b5  mov     r9d, 4; HeapInformationLength
0x1400491bb  lea     r8, [rbp+HeapInformation]; HeapInformation
0x1400491bf  mov     rcx, rax; HeapHandle
0x1400491c2  xor     edx, edx; HeapInformationClass
0x1400491c4  call    cs:__imp_HeapSetInformation
0x1400491ca  cmp     cs:?g_bWindowsProtectedPrintSpoolerWorkerEnabled@@3_NA, sil; bool g_bWindowsProtectedPrintSpoolerWorkerEnabled
0x1400491d1  lea     r15, aSpoolerinitial; "SpoolerInitializeSpooler"
0x1400491d8  jnz     short loc_140049237
0x1400491da  lea     rdx, aCallingRegiste; "Calling RegisterServiceCtrlHandler."
0x1400491e1  mov     rcx, r15; char *
0x1400491e4  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400491e9  xor     r8d, r8d; lpContext
0x1400491ec  lea     rdx, ?SpoolerCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1400491f3  lea     rcx, ServiceName; "SPOOLER"
0x1400491fa  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140049200  mov     cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * SpoolerStatusHandle
0x140049207  test    rax, rax
0x14004920a  jnz     short loc_140049237
0x14004920c  call    cs:__imp_GetLastError
0x140049212  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandler failed. Erro"...
0x140049219  mov     rcx, r15; char *
0x14004921c  mov     r8d, eax
0x14004921f  mov     ebx, eax
0x140049221  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140049226  xor     r8d, r8d; unsigned int
0x140049229  mov     edx, ebx; unsigned int
0x14004922b  xor     ecx, ecx; int
0x14004922d  call    ?SpoolerBeginForcedShutdown@@YAKHKK@Z; SpoolerBeginForcedShutdown(int,ulong,ulong)
0x140049232  jmp     loc_14004956F
0x140049237  mov     ecx, r14d; unsigned int
0x14004923a  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004923f  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x140049245  cmp     eax, r14d
0x140049248  jnz     loc_14004956F
0x14004924e  call    ?WaitForDebugger@@YAXXZ; WaitForDebugger(void)
0x140049253  xor     edx, edx; bInheritHandle
0x140049255  lea     r8, ?szSpoolerExitingEvent@@3PAGA; "Spooler_exiting"
0x14004925c  lea     ecx, [rdx+2]; dwDesiredAccess
0x14004925f  call    cs:__imp_OpenEventW
0x140049265  mov     rbx, rax
0x140049268  test    rax, rax
0x14004926b  jz      short loc_1400492A9
0x14004926d  lea     rdx, aWaitingForPrev; "Waiting for previous spooler to exit."
0x140049274  mov     rcx, r15; char *
0x140049277  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004927c  mov     rcx, rbx; hObject
0x14004927f  call    cs:__imp_CloseHandle
0x140049285  mov     ecx, r14d; unsigned int
0x140049288  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004928d  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x140049293  cmp     eax, r14d
0x140049296  jnz     loc_14004956F
0x14004929c  mov     ecx, 0BB8h; dwMilliseconds
0x1400492a1  call    cs:__imp_Sleep
0x1400492a7  jmp     short loc_140049253
0x1400492a9  lea     r9, Name; "RouterPreInitEvent"
0x1400492b0  xor     r8d, r8d; bInitialState
0x1400492b3  mov     edx, r14d; bManualReset
0x1400492b6  xor     ecx, ecx; lpEventAttributes
0x1400492b8  call    cs:__imp_CreateEventW
0x1400492be  mov     cs:?hPhase2Init@@3PEAXEA, rax; void * hPhase2Init
0x1400492c5  test    rax, rax
0x1400492c8  jnz     short loc_1400492EB
0x1400492ca  call    cs:__imp_GetLastError
0x1400492d0  lea     rdx, aPhase2initEven; "Phase2Init event creation failed. Error"...
0x1400492d7  mov     rcx, r15; char *
0x1400492da  mov     r8d, eax
0x1400492dd  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400492e2  xor     ecx, ecx; uExitCode
0x1400492e4  call    cs:__imp_ExitProcess
0x1400492eb  lea     rdx, aGettingReadyTo; "Getting ready to start the RPC server."
0x1400492f2  mov     rcx, r15; char *
0x1400492f5  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400492fa  mov     ecx, 0E8h; Size
0x1400492ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140049304  test    rax, rax
0x140049307  jz      short loc_140049316
0x140049309  mov     rcx, rax; this
0x14004930c  call    ??0TWorkCrew@NThreadingLibrary@@QEAA@XZ; NThreadingLibrary::TWorkCrew::TWorkCrew(void)
0x140049311  mov     rbx, rax
0x140049314  jmp     short loc_140049319
0x140049316  mov     rbx, rsi
0x140049319  mov     cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA, rbx; NThreadingLibrary::TWorkCrew * g_pWorkCrew
0x140049320  cmp     [rbx+0C4h], esi
0x140049326  jl      short loc_14004935E
0x140049328  lea     rdi, [rbx+0E0h]
0x14004932f  xor     edx, edx
0x140049331  mov     rcx, rdi
0x140049334  call    cs:__imp_TpAllocPool
0x14004933a  mov     ecx, eax; Status
0x14004933c  call    cs:__imp_RtlNtStatusToDosError
0x140049342  test    eax, eax
0x140049344  jle     short loc_140049350
0x140049346  movzx   eax, ax
0x140049349  or      eax, 80070000h
0x14004934e  test    eax, eax
0x140049350  js      short loc_14004935E
0x140049352  mov     r8, [rdi]
0x140049355  lea     rcx, [rbx+10h]
0x140049359  call    ?SetCallBackEnv@TTpSetWorkEnv@NThreadingLibrary@@QEAAJW4EWorkEnvironment@2@PEAX11@Z; NThreadingLibrary::TTpSetWorkEnv::SetCallBackEnv(NThreadingLibrary::EWorkEnvironment,void *,void *,void *)
0x14004935e  call    ?CheckTestMode@@YAXXZ; CheckTestMode(void)
0x140049363  call    ?HasPrintServerRole@@YA_NXZ; HasPrintServerRole(void)
0x140049368  test    al, al
0x14004936a  jz      short loc_140049387
0x14004936c  lea     rdx, aLeavingNoPrint_3; "Leaving No Printer Mode due to print se"...
0x140049373  mov     rcx, r15; char *
0x140049376  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004937b  mov     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x140049382  jmp     loc_1400494A0
0x140049387  cmp     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x14004938e  jz      loc_14004945C
0x140049394  call    cs:__imp_GetTickCount
0x14004939a  cmp     eax, 1D4C0h
0x14004939f  jb      short loc_1400493BC
0x1400493a1  lea     rdx, aLeavingNoPrint_1; "Leaving No Printer Mode due to service "...
0x1400493a8  mov     rcx, r15; char *
0x1400493ab  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400493b0  mov     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x1400493b7  jmp     loc_14004945C
0x1400493bc  lea     rdx, [rbp+LogonSessionList]; LogonSessionList
0x1400493c0  mov     [rbp+LogonSessionCount], esi
0x1400493c3  lea     rcx, [rbp+LogonSessionCount]; LogonSessionCount
0x1400493c7  mov     [rbp+LogonSessionList], rsi
0x1400493cb  call    cs:__imp_LsaEnumerateLogonSessions
0x1400493d1  test    eax, eax
0x1400493d3  jnz     short loc_140049449
0x1400493d5  mov     eax, [rbp+LogonSessionCount]
0x1400493d8  test    eax, eax
0x1400493da  jz      short loc_140049449
0x1400493dc  cmp     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x1400493e3  mov     ebx, esi
0x1400493e5  jz      short loc_140049449
0x1400493e7  cmp     ebx, eax
0x1400493e9  jnb     short loc_140049449
0x1400493eb  mov     rax, [rbp+LogonSessionList]
0x1400493ef  lea     rdx, [rbp+ppLogonSessionData]; ppLogonSessionData
0x1400493f3  mov     ecx, ebx
0x1400493f5  mov     [rbp+ppLogonSessionData], rsi
0x1400493f9  lea     rcx, [rax+rcx*8]; LogonId
0x1400493fd  call    cs:__imp_LsaGetLogonSessionData
0x140049403  test    eax, eax
0x140049405  jnz     short loc_140049438
0x140049407  mov     rcx, [rbp+ppLogonSessionData]
0x14004940b  mov     eax, [rcx+40h]
0x14004940e  sub     eax, 2
0x140049411  test    eax, 0FFFFFFF7h
0x140049416  jnz     short loc_140049432
0x140049418  lea     rdx, aLeavingNoPrint_2; "Leaving No Printer Mode because there a"...
0x14004941f  mov     rcx, r15; char *
0x140049422  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140049427  mov     rcx, [rbp+ppLogonSessionData]; Buffer
0x14004942b  mov     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x140049432  call    cs:__imp_LsaFreeReturnBuffer
0x140049438  add     ebx, r14d
0x14004943b  cmp     cs:?g_bNoPrintersMode@@3_NA, sil; bool g_bNoPrintersMode
0x140049442  jz      short loc_140049449
0x140049444  mov     eax, [rbp+LogonSessionCount]
0x140049447  jmp     short loc_1400493E7
0x140049449  mov     rcx, [rbp+LogonSessionList]; Buffer
0x14004944d  test    rcx, rcx
0x140049450  jz      short loc_14004945C
0x140049452  call    cs:__imp_LsaFreeReturnBuffer
0x140049458  mov     [rbp+LogonSessionList], rsi
0x14004945c  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, sil; bool g_bSpoolerIsChildProcess
0x140049463  jnz     short loc_1400494A0
0x140049465  mov     rcx, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hRecipient
0x14004946c  lea     rdx, GUID_LOW_POWER_EPOCH; PowerSettingGuid
0x140049473  mov     r8d, r14d; Flags
0x140049476  call    cs:__imp_RegisterPowerSettingNotification
0x14004947c  mov     cs:?g_hPowerSettingNotification@@3PEAXEA, rax; void * g_hPowerSettingNotification
0x140049483  test    rax, rax
0x140049486  jnz     short loc_1400494A0
0x140049488  call    cs:__imp_GetLastError
0x14004948e  lea     rdx, aRegisterpowers; "RegisterPowerSettingNotification failed"...
0x140049495  mov     rcx, r15; char *
0x140049498  mov     r8d, eax
0x14004949b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400494a0  call    cs:__imp_GdiDisableUMPDSandboxing
0x1400494a6  call    ?SpoolerStartRpcServer@@YAJXZ; SpoolerStartRpcServer(void)
0x1400494ab  mov     ebx, eax
0x1400494ad  test    eax, eax
0x1400494af  jz      short loc_1400494D0
0x1400494b1  mov     r8d, eax
0x1400494b4  lea     rdx, aRpcInitializat; "RPC Initialization failed. Error 0x%x"
0x1400494bb  mov     rcx, r15; char *
0x1400494be  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400494c3  mov     edx, ebx
0x1400494c5  xor     r8d, r8d
0x1400494c8  mov     ecx, r14d
0x1400494cb  jmp     loc_14004922D
0x1400494d0  mov     ecx, r14d; unsigned int
0x1400494d3  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x1400494d8  lea     rdx, aGettingReadyTo_0; "Getting ready to kick off the router"
0x1400494df  mov     rcx, r15; char *
0x1400494e2  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400494e7  mov     r9, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; lpParameter
0x1400494ee  lea     rax, [rbp+ThreadId]
0x1400494f2  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x1400494f7  lea     r8, ?PreInitializeRouter@@YAHPEAUSERVICE_STATUS_HANDLE__@@@Z; lpStartAddress
0x1400494fe  mov     edx, 10000h; dwStackSize
0x140049503  mov     dword ptr [rsp+78h+phkResult], esi; dwCreationFlags
0x140049507  xor     ecx, ecx; lpThreadAttributes
0x140049509  call    cs:__imp_CreateThread
0x14004950f  test    rax, rax
0x140049512  jz      short loc_140049559
0x140049514  mov     rcx, rax; hObject
0x140049517  call    cs:__imp_CloseHandle
0x14004951d  lea     rdx, aInitialization; "Initialization complete"
0x140049524  mov     rcx, r15; char *
0x140049527  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004952c  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x140049533  jz      short loc_14004954D
0x140049535  lea     rax, [rbp+ppLogonSessionData]
0x140049539  mov     r9d, r14d
0x14004953c  lea     rdx, DocPerf_PhaseOneInit_Stop
0x140049543  mov     [rsp+78h+phkResult], rax
0x140049548  call    McGenEventWrite_EtwEventWriteTransfer
0x14004954d  mov     ecx, 2; unsigned int
0x140049552  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x140049557  jmp     short loc_14004956F
0x140049559  call    cs:__imp_GetLastError
0x14004955f  test    eax, eax
0x140049561  jz      short loc_14004951D
0x140049563  mov     edx, eax
0x140049565  jmp     loc_1400494C5
0x14004956a  mov     eax, 3
0x14004956f  mov     rcx, [rbp+var_18]
0x140049573  xor     rcx, rsp; StackCookie
0x140049576  call    __security_check_cookie
0x14004957b  add     rsp, 78h
0x14004957f  pop     r15
0x140049581  pop     r14
0x140049583  pop     rdi
0x140049584  pop     rsi
0x140049585  pop     rbx
0x140049586  pop     rbp
0x140049587  retn
```
