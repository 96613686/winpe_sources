# SQLShutdownImpl(SQLEXITCODE)

- ea: `0x10040c8d0`
- end: `0x10040ca74`
- name: `?SQLShutdownImpl@@YAXW4SQLEXITCODE@@@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10041a4f0`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x10040c8d0`
- `0x10040cbe0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10040c949`
- `KERNEL32!EnterCriticalSection` at `0x10040c949`
- `KERNEL32!LeaveCriticalSection` at `0x10040c9ce`
- `KERNEL32!LeaveCriticalSection` at `0x10040c9ce`
- `KERNEL32!SetEvent` at `0x10040c965`
- `KERNEL32!SetEvent` at `0x10040c977`
- `KERNEL32!SetEvent` at `0x10040c965`
- `KERNEL32!SetEvent` at `0x10040c977`
- `ADVAPI32!SetServiceStatus` at `0x10040c9af`
- `ADVAPI32!SetServiceStatus` at `0x10040c9af`
- `sqlmin!?GetSQLExitError@@YAKXZ` at `0x10040c989`
- `sqlmin!?GetSQLExitError@@YAKXZ` at `0x10040c989`
- `sqlmin!?GetWin32ExitCode@@YAKXZ` at `0x10040c97d`
- `sqlmin!?GetWin32ExitCode@@YAKXZ` at `0x10040c97d`
- `sqlmin!?Shutdown@PerfmonManager@@QEAAXXZ` at `0x10040c9eb`
- `sqlmin!?Shutdown@PerfmonManager@@QEAAXXZ` at `0x10040c9eb`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x10040c90e`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c9da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040ca2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040ca2b`
- `sqldk!SystemThread_TlsOffset` at `0x10040ca12`
- `sqldk!SystemThread_TlsIndex` at `0x10040ca09`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040ca41`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10040ca41`
- `sqldk!?SilentBackoutHandler@@YAHHHHHPEAD@Z` at `0x10040c8ee`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10040c91d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10040c91d`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x10040ca6d`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040c917`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040c9d4`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040c917`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10040c9d4`
- `sbs!?SbsShutdown@@YAXXZ` at `0x10040ca58`
- `sbs!?SbsShutdown@@YAXXZ` at `0x10040ca58`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=2
void __fastcall SQLShutdownImpl(unsigned int a1)
{
  struct IErrorReportingManager *ErrorReportingManager; // rax
  __int64 v2; // rbx
  __int64 v3; // rcx
  _QWORD v4[2]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v5[3]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v6[16]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v7[24]; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v8[56]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v10; // [rsp+C8h] [rbp+10h] BYREF

  v5[2] = -2;
  try
  {
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v8, 0, 0, 0, SilentBackoutHandler, 0);
      CommonGlobalState::m_CollectingStatistics = 0;
      _flushall();
      ErrorReportingManager = GetErrorReportingManager();
      (*(void (__fastcall **)(struct IErrorReportingManager *))(*(_QWORD *)ErrorReportingManager + 240LL))(ErrorReportingManager);
      if ( *((_DWORD *)qword_10049F360 + 10544) )
      {
        EnterCriticalSection(&SCMCrtSec);
        SQLServiceStatus.dwCurrentState = 1;
        if ( hEvent )
          SetEvent(hEvent);
        if ( qword_1004D28C0 )
          SetEvent(qword_1004D28C0);
        SQLServiceStatus.dwWin32ExitCode = GetWin32ExitCode();
        SQLServiceStatus.dwServiceSpecificExitCode = GetSQLExitError();
        SQLServiceStatus.dwCheckPoint = 0;
        SQLServiceStatus.dwWaitHint = 0;
        SetServiceStatus(SQLServiceHandle, &SQLServiceStatus);
        if ( (*(_BYTE *)(qword_10049F340 + 83) & 4) == 0 )
          set_exit_status();
        LeaveCriticalSection(&SCMCrtSec);
      }
      _flushall();
      CommonGlobalState::m_PerfCountersEnabled = 0;
      PerfmonManager::Shutdown(qword_10049F360);
      ExcHandler::~ExcHandler((ExcHandler *)v8);
    }
    catch ( SQLError v7 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v6, (const struct SQLError *)v7);
        v4[0] = SOS_OS_LogUnlocalizedRoutine;
        v4[1] = L"Exception raised in SQLShutdown.\n";
        CallProtectorImpl::CallWithSEH<EmptyCallTraits,void,FunctionCallBinder_1<void,void (*)(wchar_t const *,...),wchar_t *>>(
          &v10,
          v4);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v6);
      }
      catch ( ShortStackException )
      {
      }
    }
    v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v3 = *(_QWORD *)(v2 + 256);
    if ( !v3 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v3 = *(_QWORD *)(v2 + 256);
    }
    if ( *(_DWORD *)(v3 + 556) )
      ExceptionPostCatchActions((struct Worker *)v3);
  }
  catch ( ... )
  {
    v5[0] = SOS_OS_LogUnlocalizedRoutine;
    v5[1] = L"Unknown Exception raised in SQLShutdown.\n";
    CallProtectorImpl::CallWithSEH<EmptyCallTraits,void,FunctionCallBinder_1<void,void (*)(wchar_t const *,...),wchar_t *>>(
      &v10,
      v5);
  }
  if ( *((_DWORD *)qword_10049F360 + 3645) )
    SbsShutdown();
  SOS_OS::KillProcess(a1);
}

```

## disassembly

```asm
0x10040c8d0  mov     [rsp+arg_0], ecx
0x10040c8d4  push    rbx
0x10040c8d5  sub     rsp, 0B0h
0x10040c8dc  mov     [rsp+0B8h+var_68], 0FFFFFFFFFFFFFFFEh
0x10040c8e5  xor     edx, edx; unsigned __int16
0x10040c8e7  xor     ebx, ebx
0x10040c8e9  mov     [rsp+0B8h+var_90], rbx; struct Worker *
0x10040c8ee  mov     rax, cs:__imp_?SilentBackoutHandler@@YAHHHHHPEAD@Z; SilentBackoutHandler(int,int,int,int,char *)
0x10040c8f5  mov     [rsp+0B8h+var_98], rax; int (*)(int, int, int, int, char *)
0x10040c8fa  xor     r9d, r9d; unsigned __int8
0x10040c8fd  xor     r8d, r8d; unsigned __int8
0x10040c900  lea     rcx, [rsp+0B8h+var_38]; this
0x10040c908  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10040c90d  nop
0x10040c90e  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x10040c915  mov     [rax], bl
0x10040c917  call    cs:__imp__flushall
0x10040c91d  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x10040c923  mov     rdx, [rax]
0x10040c926  mov     rcx, rax
0x10040c929  call    qword ptr [rdx+0F0h]
0x10040c92f  mov     rax, cs:qword_10049F360
0x10040c936  cmp     [rax+0A4C0h], ebx
0x10040c93c  jz      loc_10040C9D4
0x10040c942  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c949  call    cs:__imp_EnterCriticalSection
0x10040c94f  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS SQLServiceStatus ...
0x10040c959  mov     rcx, cs:hEvent; hEvent
0x10040c960  test    rcx, rcx
0x10040c963  jz      short loc_10040C96B
0x10040c965  call    cs:__imp_SetEvent
0x10040c96b  mov     rcx, cs:qword_1004D28C0; hEvent
0x10040c972  test    rcx, rcx
0x10040c975  jz      short loc_10040C97D
0x10040c977  call    cs:__imp_SetEvent
0x10040c97d  call    cs:__imp_?GetWin32ExitCode@@YAKXZ; GetWin32ExitCode(void)
0x10040c983  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS SQLServiceStatus ...
0x10040c989  call    cs:__imp_?GetSQLExitError@@YAKXZ; GetSQLExitError(void)
0x10040c98f  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, eax; _SERVICE_STATUS SQLServiceStatus ...
0x10040c995  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, ebx; _SERVICE_STATUS SQLServiceStatus ...
0x10040c99b  mov     cs:?SQLServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, ebx; _SERVICE_STATUS SQLServiceStatus ...
0x10040c9a1  lea     rdx, ?SQLServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x10040c9a8  mov     rcx, cs:?SQLServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x10040c9af  call    cs:__imp_SetServiceStatus
0x10040c9b5  mov     rax, cs:qword_10049F340
0x10040c9bc  test    byte ptr [rax+53h], 4
0x10040c9c0  jnz     short loc_10040C9C7
0x10040c9c2  call    ?set_exit_status@@YAXXZ; set_exit_status(void)
0x10040c9c7  lea     rcx, ?SCMCrtSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040c9ce  call    cs:__imp_LeaveCriticalSection
0x10040c9d4  call    cs:__imp__flushall
0x10040c9da  mov     rax, cs:__imp_?m_PerfCountersEnabled@CommonGlobalState@@2_NA; bool CommonGlobalState::m_PerfCountersEnabled
0x10040c9e1  mov     byte ptr [rax], 0
0x10040c9e4  mov     rcx, cs:qword_10049F360
0x10040c9eb  call    cs:__imp_?Shutdown@PerfmonManager@@QEAAXXZ; PerfmonManager::Shutdown(void)
0x10040c9f1  nop
0x10040c9f2  lea     rcx, [rsp+0B8h+var_38]; this
0x10040c9fa  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10040c9ff  nop
0x10040ca00  mov     rdx, gs:58h
0x10040ca09  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040ca10  mov     ecx, [rax]
0x10040ca12  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040ca19  mov     ebx, [rax]
0x10040ca1b  add     rbx, [rdx+rcx*8]
0x10040ca1f  mov     rcx, [rbx+100h]
0x10040ca26  test    rcx, rcx
0x10040ca29  jnz     short loc_10040CA38
0x10040ca2b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040ca31  mov     rcx, [rbx+100h]
0x10040ca38  cmp     dword ptr [rcx+22Ch], 0
0x10040ca3f  jz      short loc_10040CA48
0x10040ca41  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10040ca47  nop
0x10040ca48  mov     rax, cs:qword_10049F360
0x10040ca4f  cmp     dword ptr [rax+38F4h], 0
0x10040ca56  jz      short loc_10040CA5E
0x10040ca58  call    cs:__imp_?SbsShutdown@@YAXXZ; SbsShutdown(void)
0x10040ca5e  mov     ecx, [rsp+0B8h+arg_0]
0x10040ca65  add     rsp, 0B0h
0x10040ca6c  pop     rbx
0x10040ca6d  jmp     cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
```
