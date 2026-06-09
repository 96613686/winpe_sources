# SpoolerBeginForcedShutdown(int,ulong,ulong)

- ea: `0x14003ce38`
- end: `0x14003cf3d`
- name: `?SpoolerBeginForcedShutdown@@YAKHKK@Z`
- size: `261`
- prototype: `unsigned int(int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14003c240`
- `0x1400490bc`

## callees

- `0x1400160a0`
- `0x140016148`
- `0x14001616c`
- `0x14003cd4c`
- `0x14003ce38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cf2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003cf2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003ce4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003ce4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ceff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ceff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003ce97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003ce97`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003cef5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14003cef5`

## string_xrefs

- `0x14003ced9`: `No handle to call SetServiceStatus.`
- `0x14003cf0c`: `SetServiceStatus failed. Error 0x%x.`

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
0x14003ce38  push    rbx
0x14003ce3a  push    rbp
0x14003ce3b  push    rsi
0x14003ce3c  push    rdi
0x14003ce3d  sub     rsp, 28h
0x14003ce41  mov     esi, ecx
0x14003ce43  mov     ebp, r8d
0x14003ce46  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003ce4d  mov     edi, edx
0x14003ce4f  call    cs:__imp_EnterCriticalSection
0x14003ce55  mov     eax, cs:?SpoolerState@@3KA; ulong SpoolerState
0x14003ce5b  mov     ebx, 1
0x14003ce60  add     eax, 0FFFFFFFDh
0x14003ce63  cmp     eax, ebx
0x14003ce65  jbe     short loc_14003CECD
0x14003ce67  cmp     esi, ebx
0x14003ce69  jnz     short loc_14003CE7A
0x14003ce6b  mov     ebx, 3
0x14003ce70  mov     cs:ServiceStatus.dwCurrentState, ebx
0x14003ce76  mov     eax, ebx
0x14003ce78  jmp     short loc_14003CE91
0x14003ce7a  mov     qword ptr cs:ServiceStatus.dwCurrentState, rbx
0x14003ce81  mov     eax, 4
0x14003ce86  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x14003ce91  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x14003ce97  call    cs:__imp_GetCurrentProcessId
0x14003ce9d  mov     esi, eax
0x14003ce9f  call    ?IsEnabled@SpoolerServiceTelemetry@@SA_NE_K@Z; SpoolerServiceTelemetry::IsEnabled(uchar,unsigned __int64)
0x14003cea4  test    al, al
0x14003cea6  jz      short loc_14003CEC1
0x14003cea8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_e6560249766775654ace24314ce18d53_@@CA@XZ; _lambda_e6560249766775654ace24314ce18d53_::_lambda_invoker_cdecl_(void)
0x14003ceaf  call    ?get@?$static_lazy@VSpoolerServiceTelemetry@@@details@wil@@QEAAPEAVSpoolerServiceTelemetry@@P6AXXZ@Z; wil::details::static_lazy<SpoolerServiceTelemetry>::get(void (*)(void))
0x14003ceb4  mov     r9d, edi; unsigned int
0x14003ceb7  mov     r8d, ebx; unsigned int
0x14003ceba  mov     edx, esi; unsigned int
0x14003cebc  call    ?ForcedShutdown_@SpoolerServiceTelemetry@@QEAAXKKK@Z; SpoolerServiceTelemetry::ForcedShutdown_(ulong,ulong,ulong)
0x14003cec1  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x14003cec7  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebp
0x14003cecd  mov     rcx, cs:?SpoolerStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14003ced4  test    rcx, rcx
0x14003ced7  jnz     short loc_14003CEEE
0x14003ced9  lea     rdx, aNoHandleToCall; "No handle to call SetServiceStatus."
0x14003cee0  lea     rcx, aSpoolerbeginfo; "SpoolerBeginForcedShutdown"
0x14003cee7  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003ceec  jmp     short loc_14003CF1F
0x14003ceee  lea     rdx, ServiceStatus; lpServiceStatus
0x14003cef5  call    cs:__imp_SetServiceStatus
0x14003cefb  test    eax, eax
0x14003cefd  jnz     short loc_14003CF1F
0x14003ceff  call    cs:__imp_GetLastError
0x14003cf05  test    eax, eax
0x14003cf07  jz      short loc_14003CF1F
0x14003cf09  mov     r8d, eax
0x14003cf0c  lea     rdx, aSetservicestat; "SetServiceStatus failed. Error 0x%x."
0x14003cf13  lea     rcx, aSpoolerbeginfo; "SpoolerBeginForcedShutdown"
0x14003cf1a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003cf1f  mov     ebx, cs:?SpoolerState@@3KA; ulong SpoolerState
0x14003cf25  lea     rcx, ?ThreadCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003cf2c  call    cs:__imp_LeaveCriticalSection
0x14003cf32  mov     eax, ebx
0x14003cf34  add     rsp, 28h
0x14003cf38  pop     rdi
0x14003cf39  pop     rsi
0x14003cf3a  pop     rbp
0x14003cf3b  pop     rbx
0x14003cf3c  retn
```
