# PnpServiceStop

- ea: `0x18000ea20`
- end: `0x18000f105`
- name: `PnpServiceStop`
- size: `1765`
- prototype: `__int64 __fastcall(DWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cf30`
- `0x1800142b0`

## callees

- `0x18000a210`
- `0x18000a3a0`
- `0x18000de70`
- `0x18000ea20`
- `0x18000f6f0`
- `0x18000f970`
- `0x180010960`
- `0x1800109ac`
- `0x180011964`
- `0x1800119a4`
- `0x180011a58`
- `0x180011c8c`
- `0x1800126cc`
- `0x1800142c4`
- `0x180018970`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x18000ef08`
- `ntdll!RtlDeleteSecurityObject` at `0x18000ef08`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f00e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f00e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ebc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ebc9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ebd6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ebd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eb1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ef97`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ea6d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ea6d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000eb03`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ef7e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000eb03`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000ef7e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eaea`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eb78`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eca4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ed42`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ee49`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eeea`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ef68`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000effc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000f062`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000f0da`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eaea`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eb78`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eca4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ed42`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ee49`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000eeea`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ef68`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000effc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000f062`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000f0da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee7d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ee8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ee8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee6b`

## pseudocode

```c
__int64 __fastcall PnpServiceStop(DWORD a1)
{
  DWORD v2; // edi
  DWORD v3; // edx
  DWORD v4; // edx
  DWORD v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  DWORD LastError; // eax
  DWORD v9; // edx
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD v12; // edx
  DWORD v13; // ebx
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // rcx
  DWORD v17; // eax
  int v18; // edx
  DWORD v19; // eax
  DWORD v20; // ebx
  DWORD v21; // eax
  DWORD v22; // ebx
  DWORD v23; // eax
  DWORD v24; // ebx
  int v25; // r8d
  DWORD v26; // edx
  int v27; // ecx
  __int64 result; // rax
  struct _SERVICE_STATUS v29; // [rsp+30h] [rbp-D0h] BYREF
  struct _SERVICE_STATUS v30; // [rsp+50h] [rbp-B0h] BYREF
  struct _SERVICE_STATUS v31; // [rsp+70h] [rbp-90h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+90h] [rbp-70h] BYREF
  struct _SERVICE_STATUS v33; // [rsp+B0h] [rbp-50h] BYREF
  struct _SERVICE_STATUS v34; // [rsp+D0h] [rbp-30h] BYREF
  struct _SERVICE_STATUS v35; // [rsp+F0h] [rbp-10h] BYREF

  _m_prefetchw(&PnpServiceControlFlags);
  while ( (_InterlockedOr(&PnpServiceControlFlags, 1u) & 0xFFFFFFFE) != 0 )
  {
    Sleep(0x32u);
    _m_prefetchw(&PnpServiceControlFlags);
  }
  PnpServiceCurrentState = 3;
  v2 = 45000;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( PnPServiceStatusHandle )
  {
    v3 = 45000;
    ServiceStatus.dwServiceType = 48;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
    if ( PnpServiceStopWaitHint )
      v3 = PnpServiceStopWaitHint;
    *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
    ServiceStatus.dwWaitHint = v3;
    ServiceStatus.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &ServiceStatus);
  }
  if ( PnpServiceParamChangeWaitObject )
  {
    UnregisterWaitEx(PnpServiceParamChangeWaitObject, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    PnpServiceParamChangeWaitObject = 0;
  }
  if ( PnpServiceParamChangeEvent )
  {
    CloseHandle(PnpServiceParamChangeEvent);
    PnpServiceParamChangeEvent = 0;
  }
  PnpServiceCurrentState = 3;
  memset(&v33, 0, sizeof(v33));
  if ( PnPServiceStatusHandle )
  {
    v4 = 45000;
    v33.dwServiceType = 48;
    *(_QWORD *)&v33.dwCurrentState = 3;
    if ( PnpServiceStopWaitHint )
      v4 = PnpServiceStopWaitHint;
    v33.dwCheckPoint = 1;
    v33.dwWaitHint = v4;
    *(_QWORD *)&v33.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v33);
  }
  v5 = 2;
  if ( (PnpStartedSubsystems & 2) != 0 )
  {
    if ( PnpServicePreshutdown && !AreDriverUpdatesPending() )
    {
      pSetupBeginSynchronizedAccess(&Handles);
      ServerInstallQueuingEnabled = 0;
      ServerInstallProcessingEnabled = 0;
      ReleaseMutex(hMutex);
      SetEvent(PnpServiceShutdownPendingEvent);
      PnpServiceStopWaitHint = 90000;
      PnPServiceStatusUpdate(v6, 3u, 2u, 0);
      PnpServiceTerminateInstallOperations();
      PnpServiceStopWaitHint = 0;
      PnPServiceStatusUpdate(v7, 3u, 3u, 0);
      v5 = 4;
    }
    if ( PnpInstallShutdown() )
    {
      PnpStartedSubsystems &= ~2u;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, LastError);
    }
  }
  PnpServiceCurrentState = 3;
  memset(&v34, 0, sizeof(v34));
  if ( PnPServiceStatusHandle )
  {
    v9 = 45000;
    v34.dwServiceType = 48;
    *(_QWORD *)&v34.dwCurrentState = 3;
    if ( PnpServiceStopWaitHint )
      v9 = PnpServiceStopWaitHint;
    v34.dwCheckPoint = v5;
    v34.dwWaitHint = v9;
    *(_QWORD *)&v34.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v34);
  }
  v10 = v5 + 1;
  if ( (PnpStartedSubsystems & 1) != 0 )
  {
    if ( (unsigned int)PnpRpcShutdown() )
    {
      PnpStartedSubsystems &= ~1u;
    }
    else
    {
      v11 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, v11);
    }
  }
  PnpServiceCurrentState = 3;
  memset(&v35, 0, sizeof(v35));
  if ( PnPServiceStatusHandle )
  {
    v12 = 45000;
    v35.dwServiceType = 48;
    *(_QWORD *)&v35.dwCurrentState = 3;
    if ( PnpServiceStopWaitHint )
      v12 = PnpServiceStopWaitHint;
    v35.dwCheckPoint = v10;
    v35.dwWaitHint = v12;
    *(_QWORD *)&v35.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v35);
  }
  v13 = v10 + 1;
  if ( PnpServicePreshutdown && AreDriverUpdatesPending() )
  {
    if ( (byte_180023989 & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v14, (unsigned int)INSTALLING_PENDING_UPDATES, v15, 1, (__int64)&v31);
    PnpServiceStopWaitHint = GetPreshutdownTimeout();
    PnPServiceStatusUpdate(v16, 3u, v13++, 0);
    if ( PnpInstallPendingDriverUpdates() )
    {
      ClearDriverUpdatesPending();
    }
    else
    {
      v17 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, v17);
    }
    v18 = 0;
    PnpServiceStopWaitHint = 0;
  }
  else
  {
    v18 = PnpServiceStopWaitHint;
  }
  PnpServiceCurrentState = 3;
  memset(&v31, 0, sizeof(v31));
  if ( PnPServiceStatusHandle )
  {
    v31.dwServiceType = 48;
    v19 = 45000;
    *(_QWORD *)&v31.dwCurrentState = 3;
    if ( v18 )
      v19 = v18;
    v31.dwCheckPoint = v13;
    v31.dwWaitHint = v19;
    *(_QWORD *)&v31.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v31);
    v18 = PnpServiceStopWaitHint;
  }
  v20 = v13 + 1;
  if ( PnpIdleStopTimer )
  {
    SetThreadpoolTimer(PnpIdleStopTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(PnpIdleStopTimer, 1);
    CloseThreadpoolTimer(PnpIdleStopTimer);
    v18 = PnpServiceStopWaitHint;
    PnpIdleStopTimer = 0;
  }
  PnpServiceCurrentState = 3;
  memset(&v30, 0, sizeof(v30));
  if ( PnPServiceStatusHandle )
  {
    v30.dwServiceType = 48;
    v21 = 45000;
    *(_QWORD *)&v30.dwCurrentState = 3;
    if ( v18 )
      v21 = v18;
    v30.dwCheckPoint = v20;
    v30.dwWaitHint = v21;
    *(_QWORD *)&v30.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v30);
    v18 = PnpServiceStopWaitHint;
  }
  v22 = v20 + 1;
  if ( PlugPlaySecurityObject )
  {
    RtlDeleteSecurityObject(&PlugPlaySecurityObject);
    v18 = PnpServiceStopWaitHint;
    PlugPlaySecurityObject = 0;
  }
  PnpServiceCurrentState = 3;
  memset(&v29, 0, sizeof(v29));
  if ( PnPServiceStatusHandle )
  {
    v29.dwServiceType = 48;
    v23 = 45000;
    *(_QWORD *)&v29.dwCurrentState = 3;
    if ( v18 )
      v23 = v18;
    v29.dwCheckPoint = v22;
    v29.dwWaitHint = v23;
    *(_QWORD *)&v29.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v29);
  }
  v24 = v22 + 1;
  if ( PnpServiceStopWaitObject )
  {
    UnregisterWaitEx(PnpServiceStopWaitObject, 0);
    PnpServiceStopWaitObject = 0;
  }
  if ( PnpServiceStopEvent )
  {
    CloseHandle(PnpServiceStopEvent);
    PnpServiceStopEvent = 0;
  }
  CloseDrvInstAlertEvents();
  PnpServiceCurrentState = 3;
  memset(&v29, 0, sizeof(v29));
  if ( PnPServiceStatusHandle )
  {
    v26 = 45000;
    v29.dwServiceType = 48;
    *(_QWORD *)&v29.dwCurrentState = 3;
    if ( PnpServiceStopWaitHint )
      v26 = PnpServiceStopWaitHint;
    v29.dwCheckPoint = v24;
    v29.dwWaitHint = v26;
    *(_QWORD *)&v29.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v29);
  }
  if ( PnpOobeCompleteSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    PnpOobeCompleteSubscription = 0;
  }
  v27 = (int)PnPServiceStatusHandle;
  PnpServiceCurrentState = 3;
  if ( PnPServiceStatusHandle )
  {
    v30.dwServiceType = 48;
    v30.dwCheckPoint = v24 + 1;
    *(_QWORD *)&v30.dwCurrentState = 3;
    if ( PnpServiceStopWaitHint )
      v2 = PnpServiceStopWaitHint;
    *(_QWORD *)&v30.dwWin32ExitCode = 0;
    v30.dwWaitHint = v2;
    SetServiceStatus(PnPServiceStatusHandle, &v30);
  }
  PnpStartedSubsystems = 0;
  PnpSvchostGlobalData = 0;
  if ( (byte_180023989 & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v27, (unsigned int)DEVICEINSTALL_STOPPED, v25, 1, (__int64)&v31);
  McGenEventUnregister_EtwEventUnregister();
  PnpServiceCurrentState = 1;
  if ( PnPServiceStatusHandle )
  {
    v29.dwServiceType = 48;
    *(_QWORD *)&v29.dwCurrentState = 1;
    *(_QWORD *)&v29.dwCheckPoint = 0;
    v29.dwWin32ExitCode = a1;
    v29.dwServiceSpecificExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &v29);
  }
  result = 0;
  PnPServiceStatusHandle = 0;
  return result;
}

```

## disassembly

```asm
0x18000ea20  push    rbp
0x18000ea22  push    rbx
0x18000ea23  push    rsi
0x18000ea24  push    rdi
0x18000ea25  push    r14
0x18000ea27  push    r15
0x18000ea29  lea     rbp, [rsp-28h]
0x18000ea2e  sub     rsp, 128h
0x18000ea35  mov     rax, cs:__security_cookie
0x18000ea3c  xor     rax, rsp
0x18000ea3f  mov     [rbp+50h+var_40], rax
0x18000ea43  mov     esi, ecx
0x18000ea45  prefetchw byte ptr cs:PnpServiceControlFlags
0x18000ea4c  mov     eax, cs:PnpServiceControlFlags
0x18000ea52  mov     edx, eax
0x18000ea54  or      edx, 1
0x18000ea57  lock cmpxchg cs:PnpServiceControlFlags, edx
0x18000ea5f  jnz     short loc_18000EA52
0x18000ea61  test    eax, 0FFFFFFFEh
0x18000ea66  jz      short loc_18000EA96
0x18000ea68  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000ea6d  call    cs:__imp_Sleep
0x18000ea73  prefetchw byte ptr cs:PnpServiceControlFlags
0x18000ea7a  mov     eax, cs:PnpServiceControlFlags
0x18000ea80  mov     ecx, eax
0x18000ea82  or      ecx, 1
0x18000ea85  lock cmpxchg cs:PnpServiceControlFlags, ecx
0x18000ea8d  jnz     short loc_18000EA80
0x18000ea8f  test    eax, 0FFFFFFFEh
0x18000ea94  jnz     short loc_18000EA68
0x18000ea96  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000ea9d  xorps   xmm0, xmm0
0x18000eaa0  xor     r14d, r14d
0x18000eaa3  mov     cs:PnpServiceCurrentState, 3
0x18000eaad  mov     edi, 0AFC8h
0x18000eab2  movups  xmmword ptr [rbp+50h+ServiceStatus.dwServiceType], xmm0
0x18000eab6  movups  xmmword ptr [rbp+50h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000eaba  test    rcx, rcx
0x18000eabd  jz      short loc_18000EAF0
0x18000eabf  mov     eax, cs:PnpServiceStopWaitHint
0x18000eac5  mov     edx, edi
0x18000eac7  test    eax, eax
0x18000eac9  mov     [rbp+50h+ServiceStatus.dwServiceType], 30h ; '0'
0x18000ead0  mov     qword ptr [rbp+50h+ServiceStatus.dwCurrentState], 3
0x18000ead8  cmovnz  edx, eax
0x18000eadb  mov     qword ptr [rbp+50h+ServiceStatus.dwServiceSpecificExitCode], r14
0x18000eadf  mov     [rbp+50h+ServiceStatus.dwWaitHint], edx
0x18000eae2  lea     rdx, [rbp+50h+ServiceStatus]; lpServiceStatus
0x18000eae6  mov     [rbp+50h+ServiceStatus.dwWin32ExitCode], r14d
0x18000eaea  call    cs:__imp_SetServiceStatus
0x18000eaf0  mov     rcx, cs:PnpServiceParamChangeWaitObject; WaitHandle
0x18000eaf7  test    rcx, rcx
0x18000eafa  jz      short loc_18000EB10
0x18000eafc  mov     rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000eb03  call    cs:__imp_UnregisterWaitEx
0x18000eb09  mov     cs:PnpServiceParamChangeWaitObject, r14
0x18000eb10  mov     rcx, cs:PnpServiceParamChangeEvent; hObject
0x18000eb17  test    rcx, rcx
0x18000eb1a  jz      short loc_18000EB29
0x18000eb1c  call    cs:__imp_CloseHandle
0x18000eb22  mov     cs:PnpServiceParamChangeEvent, r14
0x18000eb29  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000eb30  xorps   xmm0, xmm0
0x18000eb33  mov     cs:PnpServiceCurrentState, 3
0x18000eb3d  movups  xmmword ptr [rbp+50h+var_A0.dwServiceType], xmm0
0x18000eb41  movups  xmmword ptr [rbp+50h+var_A0.dwWin32ExitCode], xmm0
0x18000eb45  test    rcx, rcx
0x18000eb48  jz      short loc_18000EB7E
0x18000eb4a  mov     eax, cs:PnpServiceStopWaitHint
0x18000eb50  mov     edx, edi
0x18000eb52  test    eax, eax
0x18000eb54  mov     [rbp+50h+var_A0.dwServiceType], 30h ; '0'
0x18000eb5b  mov     qword ptr [rbp+50h+var_A0.dwCurrentState], 3
0x18000eb63  cmovnz  edx, eax
0x18000eb66  mov     [rbp+50h+var_A0.dwCheckPoint], 1
0x18000eb6d  mov     [rbp+50h+var_A0.dwWaitHint], edx
0x18000eb70  lea     rdx, [rbp+50h+var_A0]; lpServiceStatus
0x18000eb74  mov     qword ptr [rbp+50h+var_A0.dwWin32ExitCode], r14
0x18000eb78  call    cs:__imp_SetServiceStatus
0x18000eb7e  mov     ebx, 2
0x18000eb83  lea     r15, WPP_GLOBAL_Control
0x18000eb8a  test    byte ptr cs:PnpStartedSubsystems, bl
0x18000eb90  jz      loc_18000EC59
0x18000eb96  cmp     cs:PnpServicePreshutdown, r14d
0x18000eb9d  jz      short loc_18000EC17
0x18000eb9f  call    AreDriverUpdatesPending
0x18000eba4  test    eax, eax
0x18000eba6  jnz     short loc_18000EC17
0x18000eba8  lea     rcx, Handles; lpHandles
0x18000ebaf  call    pSetupBeginSynchronizedAccess
0x18000ebb4  mov     rcx, cs:hMutex; hMutex
0x18000ebbb  mov     cs:ServerInstallQueuingEnabled, r14d
0x18000ebc2  mov     cs:ServerInstallProcessingEnabled, r14d
0x18000ebc9  call    cs:__imp_ReleaseMutex
0x18000ebcf  mov     rcx, cs:PnpServiceShutdownPendingEvent; hEvent
0x18000ebd6  call    cs:__imp_SetEvent
0x18000ebdc  xor     r9d, r9d
0x18000ebdf  mov     cs:PnpServiceStopWaitHint, 15F90h
0x18000ebe9  mov     r8d, ebx
0x18000ebec  mov     edx, 3
0x18000ebf1  call    PnPServiceStatusUpdate
0x18000ebf6  call    PnpServiceTerminateInstallOperations
0x18000ebfb  mov     edx, 3
0x18000ec00  mov     cs:PnpServiceStopWaitHint, r14d
0x18000ec07  mov     r8d, edx
0x18000ec0a  xor     r9d, r9d
0x18000ec0d  call    PnPServiceStatusUpdate
0x18000ec12  mov     ebx, 4
0x18000ec17  call    PnpInstallShutdown
0x18000ec1c  test    eax, eax
0x18000ec1e  jz      short loc_18000EC29
0x18000ec20  and     cs:PnpStartedSubsystems, 0FFFFFFFDh
0x18000ec27  jmp     short loc_18000EC59
0x18000ec29  call    cs:__imp_GetLastError
0x18000ec2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec36  cmp     rcx, r15
0x18000ec39  jz      short loc_18000EC59
0x18000ec3b  test    byte ptr [rcx+1Ch], 2
0x18000ec3f  jz      short loc_18000EC59
0x18000ec41  mov     rcx, [rcx+10h]
0x18000ec45  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000ec4c  mov     edx, 12h
0x18000ec51  mov     r9d, eax
0x18000ec54  call    WPP_SF_d
0x18000ec59  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000ec60  xorps   xmm0, xmm0
0x18000ec63  mov     cs:PnpServiceCurrentState, 3
0x18000ec6d  movups  xmmword ptr [rbp+50h+var_80.dwServiceType], xmm0
0x18000ec71  movups  xmmword ptr [rbp+50h+var_80.dwWin32ExitCode], xmm0
0x18000ec75  test    rcx, rcx
0x18000ec78  jz      short loc_18000ECAA
0x18000ec7a  mov     eax, cs:PnpServiceStopWaitHint
0x18000ec80  mov     edx, edi
0x18000ec82  test    eax, eax
0x18000ec84  mov     [rbp+50h+var_80.dwServiceType], 30h ; '0'
0x18000ec8b  mov     qword ptr [rbp+50h+var_80.dwCurrentState], 3
0x18000ec93  cmovnz  edx, eax
0x18000ec96  mov     [rbp+50h+var_80.dwCheckPoint], ebx
0x18000ec99  mov     [rbp+50h+var_80.dwWaitHint], edx
0x18000ec9c  lea     rdx, [rbp+50h+var_80]; lpServiceStatus
0x18000eca0  mov     qword ptr [rbp+50h+var_80.dwWin32ExitCode], r14
0x18000eca4  call    cs:__imp_SetServiceStatus
0x18000ecaa  inc     ebx
0x18000ecac  test    byte ptr cs:PnpStartedSubsystems, 1
0x18000ecb3  jz      short loc_18000ECF7
0x18000ecb5  call    PnpRpcShutdown
0x18000ecba  test    eax, eax
0x18000ecbc  jz      short loc_18000ECC7
0x18000ecbe  and     cs:PnpStartedSubsystems, 0FFFFFFFEh
0x18000ecc5  jmp     short loc_18000ECF7
0x18000ecc7  call    cs:__imp_GetLastError
0x18000eccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecd4  cmp     rcx, r15
0x18000ecd7  jz      short loc_18000ECF7
0x18000ecd9  test    byte ptr [rcx+1Ch], 2
0x18000ecdd  jz      short loc_18000ECF7
0x18000ecdf  mov     rcx, [rcx+10h]
0x18000ece3  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000ecea  mov     edx, 13h
0x18000ecef  mov     r9d, eax
0x18000ecf2  call    WPP_SF_d
0x18000ecf7  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000ecfe  xorps   xmm0, xmm0
0x18000ed01  mov     cs:PnpServiceCurrentState, 3
0x18000ed0b  movups  xmmword ptr [rbp+50h+var_60.dwServiceType], xmm0
0x18000ed0f  movups  xmmword ptr [rbp+50h+var_60.dwWin32ExitCode], xmm0
0x18000ed13  test    rcx, rcx
0x18000ed16  jz      short loc_18000ED48
0x18000ed18  mov     eax, cs:PnpServiceStopWaitHint
0x18000ed1e  mov     edx, edi
0x18000ed20  test    eax, eax
0x18000ed22  mov     [rbp+50h+var_60.dwServiceType], 30h ; '0'
0x18000ed29  mov     qword ptr [rbp+50h+var_60.dwCurrentState], 3
0x18000ed31  cmovnz  edx, eax
0x18000ed34  mov     [rbp+50h+var_60.dwCheckPoint], ebx
0x18000ed37  mov     [rbp+50h+var_60.dwWaitHint], edx
0x18000ed3a  lea     rdx, [rbp+50h+var_60]; lpServiceStatus
0x18000ed3e  mov     qword ptr [rbp+50h+var_60.dwWin32ExitCode], r14
0x18000ed42  call    cs:__imp_SetServiceStatus
0x18000ed48  inc     ebx
0x18000ed4a  cmp     cs:PnpServicePreshutdown, r14d
0x18000ed51  jz      loc_18000EDF8
0x18000ed57  call    AreDriverUpdatesPending
0x18000ed5c  test    eax, eax
0x18000ed5e  jz      loc_18000EDF8
0x18000ed64  test    cs:byte_180023989, 2
0x18000ed6b  jz      short loc_18000ED89
0x18000ed6d  lea     rax, [rsp+150h+var_E0]
0x18000ed72  mov     r9d, 1
0x18000ed78  lea     rdx, INSTALLING_PENDING_UPDATES
0x18000ed7f  mov     [rsp+150h+var_130], rax
0x18000ed84  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ed89  call    GetPreshutdownTimeout
0x18000ed8e  xor     r9d, r9d
0x18000ed91  mov     cs:PnpServiceStopWaitHint, eax
0x18000ed97  mov     r8d, ebx
0x18000ed9a  mov     edx, 3
0x18000ed9f  call    PnPServiceStatusUpdate
0x18000eda4  mov     edx, 400h
0x18000eda9  xor     ecx, ecx
0x18000edab  inc     ebx
0x18000edad  call    PnpInstallPendingDriverUpdates
0x18000edb2  test    eax, eax
0x18000edb4  jz      short loc_18000EDBD
0x18000edb6  call    ClearDriverUpdatesPending
0x18000edbb  jmp     short loc_18000EDED
0x18000edbd  call    cs:__imp_GetLastError
0x18000edc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edca  cmp     rcx, r15
0x18000edcd  jz      short loc_18000EDED
0x18000edcf  test    byte ptr [rcx+1Ch], 2
0x18000edd3  jz      short loc_18000EDED
0x18000edd5  mov     rcx, [rcx+10h]
0x18000edd9  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000ede0  mov     edx, 14h
0x18000ede5  mov     r9d, eax
0x18000ede8  call    WPP_SF_d
0x18000eded  mov     edx, r14d
0x18000edf0  mov     cs:PnpServiceStopWaitHint, edx
0x18000edf6  jmp     short loc_18000EDFE
0x18000edf8  mov     edx, cs:PnpServiceStopWaitHint
0x18000edfe  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000ee05  xorps   xmm0, xmm0
0x18000ee08  mov     cs:PnpServiceCurrentState, 3
0x18000ee12  movups  xmmword ptr [rsp+150h+var_E0.dwServiceType], xmm0
0x18000ee17  movups  xmmword ptr [rsp+150h+var_E0.dwWin32ExitCode], xmm0
0x18000ee1c  test    rcx, rcx
0x18000ee1f  jz      short loc_18000EE55
0x18000ee21  test    edx, edx
0x18000ee23  mov     [rsp+150h+var_E0.dwServiceType], 30h ; '0'
0x18000ee2b  mov     eax, edi
0x18000ee2d  mov     qword ptr [rsp+150h+var_E0.dwCurrentState], 3
0x18000ee36  cmovnz  eax, edx
0x18000ee39  mov     [rbp+50h+var_E0.dwCheckPoint], ebx
0x18000ee3c  lea     rdx, [rsp+150h+var_E0]; lpServiceStatus
0x18000ee41  mov     [rbp+50h+var_E0.dwWaitHint], eax
0x18000ee44  mov     qword ptr [rsp+150h+var_E0.dwWin32ExitCode], r14
0x18000ee49  call    cs:__imp_SetServiceStatus
0x18000ee4f  mov     edx, cs:PnpServiceStopWaitHint
0x18000ee55  mov     rcx, cs:PnpIdleStopTimer; pti
0x18000ee5c  inc     ebx
0x18000ee5e  test    rcx, rcx
0x18000ee61  jz      short loc_18000EE9D
0x18000ee63  xor     r9d, r9d; msWindowLength
0x18000ee66  xor     r8d, r8d; msPeriod
0x18000ee69  xor     edx, edx; pftDueTime
0x18000ee6b  call    cs:__imp_SetThreadpoolTimer
0x18000ee71  mov     rcx, cs:PnpIdleStopTimer; pti
0x18000ee78  mov     edx, 1; fCancelPendingCallbacks
0x18000ee7d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ee83  mov     rcx, cs:PnpIdleStopTimer; pti
0x18000ee8a  call    cs:__imp_CloseThreadpoolTimer
0x18000ee90  mov     edx, cs:PnpServiceStopWaitHint
0x18000ee96  mov     cs:PnpIdleStopTimer, r14
0x18000ee9d  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000eea4  xorps   xmm0, xmm0
0x18000eea7  mov     cs:PnpServiceCurrentState, 3
0x18000eeb1  movups  xmmword ptr [rsp+150h+var_100.dwServiceType], xmm0
0x18000eeb6  movups  xmmword ptr [rsp+150h+var_100.dwWin32ExitCode], xmm0
0x18000eebb  test    rcx, rcx
0x18000eebe  jz      short loc_18000EEF6
0x18000eec0  test    edx, edx
0x18000eec2  mov     [rsp+150h+var_100.dwServiceType], 30h ; '0'
0x18000eeca  mov     eax, edi
0x18000eecc  mov     qword ptr [rsp+150h+var_100.dwCurrentState], 3
0x18000eed5  cmovnz  eax, edx
0x18000eed8  mov     [rsp+150h+var_100.dwCheckPoint], ebx
0x18000eedc  lea     rdx, [rsp+150h+var_100]; lpServiceStatus
0x18000eee1  mov     [rsp+150h+var_100.dwWaitHint], eax
0x18000eee5  mov     qword ptr [rsp+150h+var_100.dwWin32ExitCode], r14
0x18000eeea  call    cs:__imp_SetServiceStatus
0x18000eef0  mov     edx, cs:PnpServiceStopWaitHint
0x18000eef6  inc     ebx
0x18000eef8  cmp     cs:PlugPlaySecurityObject, r14
0x18000eeff  jz      short loc_18000EF1B
0x18000ef01  lea     rcx, PlugPlaySecurityObject; ObjectDescriptor
0x18000ef08  call    cs:__imp_RtlDeleteSecurityObject
0x18000ef0e  mov     edx, cs:PnpServiceStopWaitHint
0x18000ef14  mov     cs:PlugPlaySecurityObject, r14
0x18000ef1b  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000ef22  xorps   xmm0, xmm0
0x18000ef25  mov     cs:PnpServiceCurrentState, 3
0x18000ef2f  movups  xmmword ptr [rsp+150h+var_120.dwServiceType], xmm0
0x18000ef34  movups  xmmword ptr [rsp+150h+var_120.dwWin32ExitCode], xmm0
0x18000ef39  test    rcx, rcx
0x18000ef3c  jz      short loc_18000EF6E
0x18000ef3e  test    edx, edx
0x18000ef40  mov     [rsp+150h+var_120.dwServiceType], 30h ; '0'
0x18000ef48  mov     eax, edi
0x18000ef4a  mov     qword ptr [rsp+150h+var_120.dwCurrentState], 3
0x18000ef53  cmovnz  eax, edx
0x18000ef56  mov     [rsp+150h+var_120.dwCheckPoint], ebx
0x18000ef5a  lea     rdx, [rsp+150h+var_120]; lpServiceStatus
0x18000ef5f  mov     [rsp+150h+var_120.dwWaitHint], eax
0x18000ef63  mov     qword ptr [rsp+150h+var_120.dwWin32ExitCode], r14
0x18000ef68  call    cs:__imp_SetServiceStatus
0x18000ef6e  mov     rcx, cs:PnpServiceStopWaitObject; WaitHandle
0x18000ef75  inc     ebx
0x18000ef77  test    rcx, rcx
0x18000ef7a  jz      short loc_18000EF8B
  ... truncated ...
```
