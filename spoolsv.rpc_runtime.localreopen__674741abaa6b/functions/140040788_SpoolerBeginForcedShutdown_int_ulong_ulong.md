# SpoolerBeginForcedShutdown(int,ulong,ulong)

- ea: `0x140040788`
- end: `0x1400408ac`
- name: `?SpoolerBeginForcedShutdown@@YAKHKK@Z`
- size: `292`
- prototype: `unsigned int(int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14003fa90`
- `0x14004d74c`

## callees

- `0x14001748c`
- `0x140017538`
- `0x14001755c`
- `0x140040694`
- `0x140040788`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140040894`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140040894`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004079f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004079f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400407ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400407ed`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140040851`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140040851`

## string_xrefs

- `0x140040835`: `No handle to call SetServiceStatus.`
- `0x140040874`: `SetServiceStatus failed. Error 0x%x.`

## pseudocode

```c
__int64 __fastcall SpoolerBeginForcedShutdown(int a1, unsigned int a2, DWORD a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  DWORD CurrentProcessId; // esi
  unsigned __int64 v9; // rdx
  unsigned __int8 v10; // cl
  __int64 v11; // rcx
  SpoolerServiceTelemetry *v12; // rcx
  DWORD LastError; // eax
  unsigned int v14; // ebx

  EnterCriticalSection(&ThreadCriticalSection);
  v6 = 1;
  if ( SpoolerState - 3 > 1 )
  {
    if ( a1 == 1 )
    {
      v6 = 3;
      ServiceStatus.dwCurrentState = 3;
      v7 = 3;
    }
    else
    {
      *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
      v7 = 4;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    }
    SpoolerState = v7;
    CurrentProcessId = GetCurrentProcessId();
    if ( SpoolerServiceTelemetry::IsEnabled(v10, v9) )
    {
      wil::details::static_lazy<SpoolerServiceTelemetry>::get(
        v11,
        _lambda_e6560249766775654ace24314ce18d53_::_lambda_invoker_cdecl_);
      SpoolerServiceTelemetry::ForcedShutdown_(v12, CurrentProcessId, v6, a2);
    }
    ServiceStatus.dwWin32ExitCode = a2;
    ServiceStatus.dwServiceSpecificExitCode = a3;
  }
  if ( SpoolerStatusHandle )
  {
    if ( !SetServiceStatus((SERVICE_STATUS_HANDLE)SpoolerStatusHandle, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( LastError )
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "SpoolerBeginForcedShutdown",
          L"SetServiceStatus failed. Error 0x%x.",
          LastError);
    }
  }
  else
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("SpoolerBeginForcedShutdown", L"No handle to call SetServiceStatus.");
  }
  v14 = SpoolerState;
  LeaveCriticalSection(&ThreadCriticalSection);
  return v14;
}

```

## disassembly

```asm
0x140040788  push    rbx
0x14004078a  push    rbp
0x14004078b  push    rsi
0x14004078c  push    rdi
0x14004078d  sub     rsp, 28h
0x140040791  mov     esi, ecx
0x140040793  mov     ebp, r8d
0x140040796  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004079d  mov     edi, edx
0x14004079f  call    cs:__imp_EnterCriticalSection
0x1400407a6  nop     dword ptr [rax+rax+00h]
0x1400407ab  mov     eax, cs:?SpoolerState@@3KA; ulong SpoolerState
0x1400407b1  mov     ebx, 1
0x1400407b6  add     eax, 0FFFFFFFDh
0x1400407b9  cmp     eax, ebx
0x1400407bb  jbe     short loc_140040829
0x1400407bd  cmp     esi, ebx
0x1400407bf  jnz     short loc_1400407D0
0x1400407c1  mov     ebx, 3
0x1400407c6  mov     cs:ServiceStatus.dwCurrentState, ebx
0x1400407cc  mov     eax, ebx
0x1400407ce  jmp     short loc_1400407E7
0x1400407d0  mov     qword ptr cs:ServiceStatus.dwCurrentState, rbx
0x1400407d7  mov     eax, 4
0x1400407dc  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x1400407e7  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x1400407ed  call    cs:__imp_GetCurrentProcessId
0x1400407f4  nop     dword ptr [rax+rax+00h]
0x1400407f9  mov     esi, eax
0x1400407fb  call    ?IsEnabled@SpoolerServiceTelemetry@@SA_NE_K@Z; SpoolerServiceTelemetry::IsEnabled(uchar,unsigned __int64)
0x140040800  test    al, al
0x140040802  jz      short loc_14004081D
0x140040804  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_e6560249766775654ace24314ce18d53_@@CA@XZ; _lambda_e6560249766775654ace24314ce18d53_::_lambda_invoker_cdecl_(void)
0x14004080b  call    ?get@?$static_lazy@VSpoolerServiceTelemetry@@@details@wil@@QEAAPEAVSpoolerServiceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<SpoolerServiceTelemetry>::get(void (*)(void))
0x140040810  mov     r9d, edi; unsigned int
0x140040813  mov     r8d, ebx; unsigned int
0x140040816  mov     edx, esi; unsigned int
0x140040818  call    ?ForcedShutdown_@SpoolerServiceTelemetry@@QEAAXKKK@Z; SpoolerServiceTelemetry::ForcedShutdown_(ulong,ulong,ulong)
0x14004081d  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x140040823  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebp
0x140040829  mov     rcx, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x140040830  test    rcx, rcx
0x140040833  jnz     short loc_14004084A
0x140040835  lea     rdx, aNoHandleToCall; "No handle to call SetServiceStatus."
0x14004083c  lea     rcx, aSpoolerbeginfo; "SpoolerBeginForcedShutdown"
0x140040843  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140040848  jmp     short loc_140040887
0x14004084a  lea     rdx, ServiceStatus; lpServiceStatus
0x140040851  call    cs:__imp_SetServiceStatus
0x140040858  nop     dword ptr [rax+rax+00h]
0x14004085d  test    eax, eax
0x14004085f  jnz     short loc_140040887
0x140040861  call    cs:__imp_GetLastError
0x140040868  nop     dword ptr [rax+rax+00h]
0x14004086d  test    eax, eax
0x14004086f  jz      short loc_140040887
0x140040871  mov     r8d, eax
0x140040874  lea     rdx, aSetservicestat; "SetServiceStatus failed. Error 0x%x."
0x14004087b  lea     rcx, aSpoolerbeginfo; "SpoolerBeginForcedShutdown"
0x140040882  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140040887  mov     ebx, cs:?SpoolerState@@3KA; ulong SpoolerState
0x14004088d  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140040894  call    cs:__imp_LeaveCriticalSection
0x14004089b  nop     dword ptr [rax+rax+00h]
0x1400408a0  mov     eax, ebx
0x1400408a2  add     rsp, 28h
0x1400408a6  pop     rdi
0x1400408a7  pop     rsi
0x1400408a8  pop     rbp
0x1400408a9  pop     rbx
0x1400408aa  retn
```
