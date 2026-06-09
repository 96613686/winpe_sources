# ServiceMain

- ea: `0x18000cf30`
- end: `0x18000d54a`
- name: `ServiceMain`
- size: `1562`
- prototype: `void()`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800020e0`
- `0x18000cf30`
- `0x18000d550`
- `0x18000d740`
- `0x18000d9e0`
- `0x18000de70`
- `0x18000ea20`
- `0x18000f970`
- `0x180010a20`
- `0x1800117d4`
- `0x180011964`
- `0x180011df0`
- `0x180011ef8`
- `0x180012698`
- `0x180012dac`
- `0x180013ed8`
- `0x180013f4c`
- `0x180018970`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d45b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d45b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d2ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d368`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d2ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d3`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000d022`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000d022`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d003`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d092`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d0d8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d14e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d277`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d003`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d092`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d0d8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d14e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000d277`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d160`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d160`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18000d1ab`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18000d1ab`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000d307`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18000d307`

## string_xrefs

- `0x18000d01b`: `DeviceInstall`
- `0x18000d3bf`: `DeviceInstall`

## pseudocode

```c
void ServiceMain()
{
  int v0; // r8d
  int v1; // ecx
  SERVICE_STATUS_HANDLE v2; // rax
  DWORD LastError; // eax
  __int64 v4; // rdx
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  bool v8; // zf
  int v9; // eax
  int v10; // ecx
  int v11; // r8d
  __int64 v12; // rcx
  HANDLE EventW; // rax
  __int64 v14; // rcx
  DWORD v15; // eax
  __int64 v16; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // ecx
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v21[16]; // [rsp+60h] [rbp-20h] BYREF

  PnpServicePreshutdown = 0;
  PnpServicePreshutdownRequired = 0;
  _InterlockedExchange(&PnpServiceControlFlags, 0);
  PnpServiceOutstandingInstalls = 0;
  PnpRpcIdle = 0;
  McGenEventRegister_EtwEventRegister();
  v1 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids);
  if ( (byte_180023989 & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v1, (unsigned int)DEVICEINSTALL_STARTING, v0, 1, (__int64)v21);
  PnpServiceCurrentState = 2;
  if ( PnPServiceStatusHandle )
  {
    ServiceStatus.dwServiceType = 48;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
    ServiceStatus.dwCheckPoint = 0;
    ServiceStatus.dwWaitHint = 45000;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &ServiceStatus);
  }
  v2 = RegisterServiceCtrlHandlerExW(L"DeviceInstall", PnpServiceControlHandlerEx, 0);
  PnPServiceStatusHandle = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 25;
LABEL_68:
      WPP_SF_d(v6[2], v7, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, LastError);
      goto LABEL_69;
    }
    goto LABEL_69;
  }
  PnpServiceCurrentState = 2;
  ServiceStatus.dwServiceType = 48;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwCheckPoint = 1;
  ServiceStatus.dwWaitHint = 45000;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  SetServiceStatus(v2, &ServiceStatus);
  InitPlugPlayGlobalFlags();
  PnpServiceCurrentState = 2;
  if ( PnPServiceStatusHandle )
  {
    ServiceStatus.dwServiceType = 48;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
    ServiceStatus.dwCheckPoint = 2;
    ServiceStatus.dwWaitHint = 45000;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &ServiceStatus);
  }
  if ( !CreatePlugPlaySecurityObject() )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 26;
      goto LABEL_68;
    }
LABEL_69:
    if ( !v5 )
      return;
    goto LABEL_70;
  }
  PnpServiceCurrentState = 2;
  if ( PnPServiceStatusHandle )
  {
    ServiceStatus.dwServiceType = 48;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
    ServiceStatus.dwCheckPoint = 3;
    ServiceStatus.dwWaitHint = 45000;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &ServiceStatus);
  }
  PnpIdleStopTimer = CreateThreadpoolTimer(PnpIdleStopTimerCallback, 0, 0);
  if ( !PnpIdleStopTimer )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 27;
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  PnpStartedSubsystems = 0;
  v8 = !IsApiSetImplemented("ext-ms-win-driver-setup-l1-1-0");
  v9 = PnpServiceInstallOptions;
  if ( !v8 )
    v9 = PnpServiceInstallOptions | 0x31;
  PnpServiceInstallOptions = v9 | 0x100;
  if ( (v9 & 1) != 0 )
  {
    CreateDrvInstAlertEvents();
    if ( (unsigned int)PnpInstallDisabled() )
    {
      if ( (byte_180023989 & 2) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(v10, (unsigned int)DeviceInstallIsDisabled, v11, 1, (__int64)v21);
    }
    else
    {
      if ( !(unsigned int)PnpInstallStartup() )
      {
        LastError = GetLastError();
        v5 = LastError;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 28;
          goto LABEL_68;
        }
        goto LABEL_69;
      }
      PnpStartedSubsystems |= 2u;
    }
  }
  PnpServiceCurrentState = 2;
  if ( PnPServiceStatusHandle )
  {
    ServiceStatus.dwServiceType = 48;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
    ServiceStatus.dwCheckPoint = 4;
    ServiceStatus.dwWaitHint = 45000;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    SetServiceStatus(PnPServiceStatusHandle, &ServiceStatus);
  }
  if ( !PnpRpcStartup() )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 29;
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  PnpStartedSubsystems |= 1u;
  PnPServiceStatusUpdate(v12, 2, 5, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  PnpServiceParamChangeEvent = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 30;
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  PnpServiceParamChangeWaitObject = (HANDLE)RegisterWaitForSingleObjectEx(
                                              EventW,
                                              ParamChangeEventWaitCallback,
                                              0,
                                              0xFFFFFFFFLL,
                                              16);
  if ( !PnpServiceParamChangeWaitObject )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 31;
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  PnPServiceStatusUpdate(v14, 2, 6, 0);
  PnpServiceStopError = 0;
  PnpServiceStopEvent = CreateEventW(0, 0, 0, 0);
  if ( !PnpServiceStopEvent )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 32;
      goto LABEL_68;
    }
    goto LABEL_69;
  }
  v15 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(PnpSvchostGlobalData + 192))(
          &PnpServiceStopWaitObject,
          L"DeviceInstall",
          PnpServiceStopEvent,
          PnpServiceStopCallback,
          0,
          24);
  v5 = v15;
  if ( v15 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, v15);
LABEL_70:
    if ( (byte_180023989 & 2) != 0 )
      McTemplateU0d_EtwEventWriteTransfer(v6, v4, v5);
    PnpServiceStop(v5);
    return;
  }
  PnPServiceStatusUpdate(v16, 4, 0, 0);
  if ( (byte_180023989 & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v17, (unsigned int)DEVICEINSTALL_START, v18, 1, (__int64)v21);
  v19 = (int)PnpServiceParamChangeEvent;
  if ( PnpServiceParamChangeEvent )
    SetEvent(PnpServiceParamChangeEvent);
  if ( (PnpGlobalFlags & 0xF) != 0 || (unsigned int)IsSysprepInVmMode() || (unsigned int)IsMiniNT() )
  {
    PnpIdleStopEnabled = 0;
    if ( (byte_180023989 & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v19, (unsigned int)IdleStopIsDisabled, v18, 1, (__int64)v21);
  }
  else
  {
    PnpIdleStopEnabled = 1;
  }
  EnterCriticalSection(&PnpIdleStopLock);
  EvaluateIdleStopPolicy();
  LeaveCriticalSection(&PnpIdleStopLock);
}

```

## disassembly

```asm
0x18000cf30  mov     [rsp-8+arg_8], rsi
0x18000cf35  mov     [rsp-8+arg_10], rdi
0x18000cf3a  push    rbp
0x18000cf3b  mov     rbp, rsp
0x18000cf3e  sub     rsp, 80h
0x18000cf45  mov     rax, cs:__security_cookie
0x18000cf4c  xor     rax, rsp
0x18000cf4f  mov     [rbp+var_10], rax
0x18000cf53  xor     edi, edi
0x18000cf55  mov     eax, edi
0x18000cf57  mov     cs:PnpServicePreshutdown, edi
0x18000cf5d  mov     cs:PnpServicePreshutdownRequired, edi
0x18000cf63  xchg    eax, cs:PnpServiceControlFlags
0x18000cf69  mov     cs:PnpServiceOutstandingInstalls, edi
0x18000cf6f  mov     cs:PnpRpcIdle, edi
0x18000cf75  call    McGenEventRegister_EtwEventRegister
0x18000cf7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf81  lea     rsi, WPP_GLOBAL_Control
0x18000cf88  cmp     rcx, rsi
0x18000cf8b  jz      short loc_18000CFA8
0x18000cf8d  test    byte ptr [rcx+1Ch], 8
0x18000cf91  jz      short loc_18000CFA8
0x18000cf93  mov     rcx, [rcx+10h]
0x18000cf97  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000cf9e  mov     edx, 18h
0x18000cfa3  call    WPP_SF_
0x18000cfa8  test    cs:byte_180023989, 2
0x18000cfaf  jz      short loc_18000CFCC
0x18000cfb1  lea     rax, [rbp+var_20]
0x18000cfb5  mov     r9d, 1
0x18000cfbb  lea     rdx, DEVICEINSTALL_STARTING
0x18000cfc2  mov     [rsp+80h+var_60], rax
0x18000cfc7  call    McGenEventWrite_EtwEventWriteTransfer
0x18000cfcc  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000cfd3  mov     cs:PnpServiceCurrentState, 2
0x18000cfdd  test    rcx, rcx
0x18000cfe0  jz      short loc_18000D009
0x18000cfe2  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18000cfe6  mov     [rbp+ServiceStatus.dwServiceType], 30h ; '0'
0x18000cfed  mov     qword ptr [rbp+ServiceStatus.dwCurrentState], 2
0x18000cff5  mov     [rbp+ServiceStatus.dwCheckPoint], edi
0x18000cff8  mov     [rbp+ServiceStatus.dwWaitHint], 0AFC8h
0x18000cfff  mov     qword ptr [rbp+ServiceStatus.dwWin32ExitCode], rdi
0x18000d003  call    cs:__imp_SetServiceStatus
0x18000d009  xor     r8d, r8d; lpContext
0x18000d00c  mov     [rsp+80h+arg_0], rbx
0x18000d014  lea     rdx, PnpServiceControlHandlerEx; lpHandlerProc
0x18000d01b  lea     rcx, ServiceName; "DeviceInstall"
0x18000d022  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000d028  mov     cs:PnPServiceStatusHandle, rax
0x18000d02f  test    rax, rax
0x18000d032  jnz     short loc_18000D060
0x18000d034  call    cs:__imp_GetLastError
0x18000d03a  mov     ebx, eax
0x18000d03c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d043  cmp     rcx, rsi
0x18000d046  jz      loc_18000D505
0x18000d04c  test    byte ptr [rcx+1Ch], 1
0x18000d050  jz      loc_18000D505
0x18000d056  mov     edx, 19h
0x18000d05b  jmp     loc_18000D4F2
0x18000d060  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18000d064  mov     cs:PnpServiceCurrentState, 2
0x18000d06e  mov     rcx, rax; hServiceStatus
0x18000d071  mov     [rbp+ServiceStatus.dwServiceType], 30h ; '0'
0x18000d078  mov     qword ptr [rbp+ServiceStatus.dwCurrentState], 2
0x18000d080  mov     [rbp+ServiceStatus.dwCheckPoint], 1
0x18000d087  mov     [rbp+ServiceStatus.dwWaitHint], 0AFC8h
0x18000d08e  mov     qword ptr [rbp+ServiceStatus.dwWin32ExitCode], rdi
0x18000d092  call    cs:__imp_SetServiceStatus
0x18000d098  call    InitPlugPlayGlobalFlags
0x18000d09d  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000d0a4  mov     cs:PnpServiceCurrentState, 2
0x18000d0ae  test    rcx, rcx
0x18000d0b1  jz      short loc_18000D0DE
0x18000d0b3  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18000d0b7  mov     [rbp+ServiceStatus.dwServiceType], 30h ; '0'
0x18000d0be  mov     qword ptr [rbp+ServiceStatus.dwCurrentState], 2
0x18000d0c6  mov     [rbp+ServiceStatus.dwCheckPoint], 2
0x18000d0cd  mov     [rbp+ServiceStatus.dwWaitHint], 0AFC8h
0x18000d0d4  mov     qword ptr [rbp+ServiceStatus.dwWin32ExitCode], rdi
0x18000d0d8  call    cs:__imp_SetServiceStatus
0x18000d0de  call    CreatePlugPlaySecurityObject
0x18000d0e3  test    eax, eax
0x18000d0e5  jnz     short loc_18000D113
0x18000d0e7  call    cs:__imp_GetLastError
0x18000d0ed  mov     ebx, eax
0x18000d0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0f6  cmp     rcx, rsi
0x18000d0f9  jz      loc_18000D505
0x18000d0ff  test    byte ptr [rcx+1Ch], 1
0x18000d103  jz      loc_18000D505
0x18000d109  mov     edx, 1Ah
0x18000d10e  jmp     loc_18000D4F2
0x18000d113  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000d11a  mov     cs:PnpServiceCurrentState, 2
0x18000d124  test    rcx, rcx
0x18000d127  jz      short loc_18000D154
0x18000d129  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18000d12d  mov     [rbp+ServiceStatus.dwServiceType], 30h ; '0'
0x18000d134  mov     qword ptr [rbp+ServiceStatus.dwCurrentState], 2
0x18000d13c  mov     [rbp+ServiceStatus.dwCheckPoint], 3
0x18000d143  mov     [rbp+ServiceStatus.dwWaitHint], 0AFC8h
0x18000d14a  mov     qword ptr [rbp+ServiceStatus.dwWin32ExitCode], rdi
0x18000d14e  call    cs:__imp_SetServiceStatus
0x18000d154  xor     r8d, r8d; pcbe
0x18000d157  lea     rcx, PnpIdleStopTimerCallback; pfnti
0x18000d15e  xor     edx, edx; pv
0x18000d160  call    cs:__imp_CreateThreadpoolTimer
0x18000d166  mov     cs:PnpIdleStopTimer, rax
0x18000d16d  test    rax, rax
0x18000d170  jnz     short loc_18000D19E
0x18000d172  call    cs:__imp_GetLastError
0x18000d178  mov     ebx, eax
0x18000d17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d181  cmp     rcx, rsi
0x18000d184  jz      loc_18000D505
0x18000d18a  test    byte ptr [rcx+1Ch], 1
0x18000d18e  jz      loc_18000D505
0x18000d194  mov     edx, 1Bh
0x18000d199  jmp     loc_18000D4F2
0x18000d19e  lea     rcx, Contract; "ext-ms-win-driver-setup-l1-1-0"
0x18000d1a5  mov     cs:PnpStartedSubsystems, edi
0x18000d1ab  call    cs:__imp_IsApiSetImplemented
0x18000d1b1  test    eax, eax
0x18000d1b3  mov     eax, cs:PnpServiceInstallOptions
0x18000d1b9  jz      short loc_18000D1BE
0x18000d1bb  or      eax, 31h
0x18000d1be  bts     eax, 8
0x18000d1c2  mov     cs:PnpServiceInstallOptions, eax
0x18000d1c8  test    al, 1
0x18000d1ca  jz      short loc_18000D23C
0x18000d1cc  call    CreateDrvInstAlertEvents
0x18000d1d1  call    PnpInstallDisabled
0x18000d1d6  test    eax, eax
0x18000d1d8  jnz     short loc_18000D218
0x18000d1da  call    PnpInstallStartup
0x18000d1df  test    eax, eax
0x18000d1e1  jz      short loc_18000D1EC
0x18000d1e3  or      cs:PnpStartedSubsystems, 2
0x18000d1ea  jmp     short loc_18000D23C
0x18000d1ec  call    cs:__imp_GetLastError
0x18000d1f2  mov     ebx, eax
0x18000d1f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1fb  cmp     rcx, rsi
0x18000d1fe  jz      loc_18000D505
0x18000d204  test    byte ptr [rcx+1Ch], 1
0x18000d208  jz      loc_18000D505
0x18000d20e  mov     edx, 1Ch
0x18000d213  jmp     loc_18000D4F2
0x18000d218  test    cs:byte_180023989, 2
0x18000d21f  jz      short loc_18000D23C
0x18000d221  lea     rax, [rbp+var_20]
0x18000d225  mov     r9d, 1
0x18000d22b  lea     rdx, DeviceInstallIsDisabled
0x18000d232  mov     [rsp+80h+var_60], rax
0x18000d237  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d23c  mov     rcx, cs:PnPServiceStatusHandle; hServiceStatus
0x18000d243  mov     cs:PnpServiceCurrentState, 2
0x18000d24d  test    rcx, rcx
0x18000d250  jz      short loc_18000D27D
0x18000d252  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x18000d256  mov     [rbp+ServiceStatus.dwServiceType], 30h ; '0'
0x18000d25d  mov     qword ptr [rbp+ServiceStatus.dwCurrentState], 2
0x18000d265  mov     [rbp+ServiceStatus.dwCheckPoint], 4
0x18000d26c  mov     [rbp+ServiceStatus.dwWaitHint], 0AFC8h
0x18000d273  mov     qword ptr [rbp+ServiceStatus.dwWin32ExitCode], rdi
0x18000d277  call    cs:__imp_SetServiceStatus
0x18000d27d  call    PnpRpcStartup
0x18000d282  test    eax, eax
0x18000d284  jz      loc_18000D4D3
0x18000d28a  or      cs:PnpStartedSubsystems, 1
0x18000d291  xor     r9d, r9d
0x18000d294  mov     edx, 2
0x18000d299  mov     r8d, 5
0x18000d29f  call    PnPServiceStatusUpdate
0x18000d2a4  xor     r9d, r9d; lpName
0x18000d2a7  xor     r8d, r8d; bInitialState
0x18000d2aa  xor     edx, edx; bManualReset
0x18000d2ac  xor     ecx, ecx; lpEventAttributes
0x18000d2ae  call    cs:__imp_CreateEventW
0x18000d2b4  mov     cs:PnpServiceParamChangeEvent, rax
0x18000d2bb  test    rax, rax
0x18000d2be  jnz     short loc_18000D2EC
0x18000d2c0  call    cs:__imp_GetLastError
0x18000d2c6  mov     ebx, eax
0x18000d2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2cf  cmp     rcx, rsi
0x18000d2d2  jz      loc_18000D505
0x18000d2d8  test    byte ptr [rcx+1Ch], 1
0x18000d2dc  jz      loc_18000D505
0x18000d2e2  mov     edx, 1Eh
0x18000d2e7  jmp     loc_18000D4F2
0x18000d2ec  mov     r9d, 0FFFFFFFFh
0x18000d2f2  mov     dword ptr [rsp+80h+var_60], 10h
0x18000d2fa  xor     r8d, r8d
0x18000d2fd  lea     rdx, ParamChangeEventWaitCallback
0x18000d304  mov     rcx, rax
0x18000d307  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18000d30d  mov     cs:PnpServiceParamChangeWaitObject, rax
0x18000d314  test    rax, rax
0x18000d317  jnz     short loc_18000D345
0x18000d319  call    cs:__imp_GetLastError
0x18000d31f  mov     ebx, eax
0x18000d321  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d328  cmp     rcx, rsi
0x18000d32b  jz      loc_18000D505
0x18000d331  test    byte ptr [rcx+1Ch], 1
0x18000d335  jz      loc_18000D505
0x18000d33b  mov     edx, 1Fh
0x18000d340  jmp     loc_18000D4F2
0x18000d345  xor     r9d, r9d
0x18000d348  mov     edx, 2
0x18000d34d  mov     r8d, 6
0x18000d353  call    PnPServiceStatusUpdate
0x18000d358  xor     r9d, r9d; lpName
0x18000d35b  mov     cs:PnpServiceStopError, edi
0x18000d361  xor     r8d, r8d; bInitialState
0x18000d364  xor     edx, edx; bManualReset
0x18000d366  xor     ecx, ecx; lpEventAttributes
0x18000d368  call    cs:__imp_CreateEventW
0x18000d36e  mov     cs:PnpServiceStopEvent, rax
0x18000d375  mov     r8, rax
0x18000d378  test    rax, rax
0x18000d37b  jnz     short loc_18000D3A9
0x18000d37d  call    cs:__imp_GetLastError
0x18000d383  mov     ebx, eax
0x18000d385  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d38c  cmp     rcx, rsi
0x18000d38f  jz      loc_18000D505
0x18000d395  test    byte ptr [rcx+1Ch], 1
0x18000d399  jz      loc_18000D505
0x18000d39f  mov     edx, 20h ; ' '
0x18000d3a4  jmp     loc_18000D4F2
0x18000d3a9  mov     rax, cs:PnpSvchostGlobalData
0x18000d3b0  lea     r9, PnpServiceStopCallback
0x18000d3b7  mov     [rsp+80h+var_58], 18h
0x18000d3bf  lea     rdx, ServiceName; "DeviceInstall"
0x18000d3c6  lea     rcx, PnpServiceStopWaitObject
0x18000d3cd  mov     [rsp+80h+var_60], rdi
0x18000d3d2  mov     rax, [rax+0C0h]
0x18000d3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3de  mov     ebx, eax
0x18000d3e0  test    eax, eax
0x18000d3e2  jz      short loc_18000D41B
0x18000d3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3eb  cmp     rcx, rsi
0x18000d3ee  jz      loc_18000D509
0x18000d3f4  test    byte ptr [rcx+1Ch], 1
0x18000d3f8  jz      loc_18000D509
0x18000d3fe  mov     rcx, [rcx+10h]
0x18000d402  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18000d409  mov     edx, 21h ; '!'
0x18000d40e  mov     r9d, eax
0x18000d411  call    WPP_SF_d
0x18000d416  jmp     loc_18000D509
0x18000d41b  xor     r9d, r9d
0x18000d41e  xor     r8d, r8d
0x18000d421  mov     edx, 4
0x18000d426  call    PnPServiceStatusUpdate
0x18000d42b  test    cs:byte_180023989, 2
0x18000d432  jz      short loc_18000D44F
0x18000d434  lea     rax, [rbp+var_20]
0x18000d438  mov     r9d, 1
0x18000d43e  lea     rdx, DEVICEINSTALL_START
0x18000d445  mov     [rsp+80h+var_60], rax
0x18000d44a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d44f  mov     rcx, cs:PnpServiceParamChangeEvent; hEvent
0x18000d456  test    rcx, rcx
0x18000d459  jz      short loc_18000D461
0x18000d45b  call    cs:__imp_SetEvent
0x18000d461  test    byte ptr cs:PnpGlobalFlags, 0Fh
0x18000d468  jnz     short loc_18000D488
0x18000d46a  call    IsSysprepInVmMode
0x18000d46f  test    eax, eax
0x18000d471  jnz     short loc_18000D488
0x18000d473  call    IsMiniNT
0x18000d478  test    eax, eax
0x18000d47a  jnz     short loc_18000D488
0x18000d47c  mov     cs:PnpIdleStopEnabled, 1
0x18000d486  jmp     short loc_18000D4B2
0x18000d488  test    cs:byte_180023989, 2
0x18000d48f  mov     cs:PnpIdleStopEnabled, edi
0x18000d495  jz      short loc_18000D4B2
0x18000d497  lea     rax, [rbp+var_20]
0x18000d49b  mov     r9d, 1
0x18000d4a1  lea     rdx, IdleStopIsDisabled
0x18000d4a8  mov     [rsp+80h+var_60], rax
0x18000d4ad  call    McGenEventWrite_EtwEventWriteTransfer
0x18000d4b2  lea     rcx, PnpIdleStopLock; lpCriticalSection
0x18000d4b9  call    cs:__imp_EnterCriticalSection
0x18000d4bf  call    EvaluateIdleStopPolicy
0x18000d4c4  lea     rcx, PnpIdleStopLock; lpCriticalSection
0x18000d4cb  call    cs:__imp_LeaveCriticalSection
0x18000d4d1  jmp     short loc_18000D521
0x18000d4d3  call    cs:__imp_GetLastError
0x18000d4d9  mov     ebx, eax
0x18000d4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4e2  cmp     rcx, rsi
0x18000d4e5  jz      short loc_18000D505
  ... truncated ...
```
