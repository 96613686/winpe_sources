# SpoolerShutdown(void)

- ea: `0x14004d2d4`
- end: `0x14004d3d8`
- name: `?SpoolerShutdown@@YAXXZ`
- size: `260`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14004c400`
- `0x14004c580`
- `0x140054a80`
- `0x140055650`

## callees

- `0x140031720`
- `0x1400408b4`
- `0x14004d2d4`
- `0x14006c120`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14004d3cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004d3a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004d3a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d2eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d2eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004d33f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004d33f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d2f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d2f7`

## string_xrefs

- `0x14004d311`: `Spooler is already shutting down...`
- `0x14004d3ad`: `Spooler shutdown complete`

## pseudocode

```c
void SpoolerShutdown(void)
{
  struct _PROVIDOR *i; // rbx
  void (__fastcall *v1)(_QWORD); // rax

  CreateEventW(0, 1, 1, szSpoolerExitingEvent);
  if ( GetLastError() == 183 )
  {
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerShutdown", L"Spooler is already shutting down...");
  }
  else
  {
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerShutdown", L"Spooler shutting down...");
    SpoolerStatusUpdate(3);
    EnterCriticalSection(&RouterNotifySection);
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerShutdown", L"Shutting down providers...");
    for ( i = pLocalProvidor; i; i = *(struct _PROVIDOR **)i )
    {
      v1 = (void (__fastcall *)(_QWORD))*((_QWORD *)i + 59);
      if ( v1 )
        v1(0);
    }
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerShutdown", L"Shutting down router...");
    SplShutDownRouter();
    LeaveCriticalSection(&RouterNotifySection);
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SpoolerShutdown", L"Spooler shutdown complete");
    SetEvent(TerminateEvent);
  }
}

```

## disassembly

```asm
0x14004d2d4  push    rbx
0x14004d2d6  sub     rsp, 20h
0x14004d2da  mov     edx, 1; bManualReset
0x14004d2df  lea     r9, ?szSpoolerExitingEvent@@3PAGA; "Spooler_exiting"
0x14004d2e6  mov     r8d, edx; bInitialState
0x14004d2e9  xor     ecx, ecx; lpEventAttributes
0x14004d2eb  call    cs:__imp_CreateEventW
0x14004d2f2  nop     dword ptr [rax+rax+00h]
0x14004d2f7  call    cs:__imp_GetLastError
0x14004d2fe  nop     dword ptr [rax+rax+00h]
0x14004d303  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x14004d30a  cmp     eax, 0B7h
0x14004d30f  jnz     short loc_14004D322
0x14004d311  lea     rdx, aSpoolerIsAlrea; "Spooler is already shutting down..."
0x14004d318  add     rsp, 20h
0x14004d31c  pop     rbx
0x14004d31d  jmp     ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d322  lea     rdx, aSpoolerShuttin; "Spooler shutting down..."
0x14004d329  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d32e  mov     ecx, 3; unsigned int
0x14004d333  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004d338  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004d33f  call    cs:__imp_EnterCriticalSection
0x14004d346  nop     dword ptr [rax+rax+00h]
0x14004d34b  lea     rdx, aShuttingDownPr; "Shutting down providers..."
0x14004d352  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x14004d359  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d35e  mov     rbx, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x14004d365  jmp     short loc_14004D37D
0x14004d367  mov     rax, [rbx+1D8h]
0x14004d36e  test    rax, rax
0x14004d371  jz      short loc_14004D37A
0x14004d373  xor     ecx, ecx
0x14004d375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d37a  mov     rbx, [rbx]
0x14004d37d  test    rbx, rbx
0x14004d380  jnz     short loc_14004D367
0x14004d382  lea     rdx, aShuttingDownRo; "Shutting down router..."
0x14004d389  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x14004d390  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d395  call    SplShutDownRouter
0x14004d39a  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004d3a1  call    cs:__imp_LeaveCriticalSection
0x14004d3a8  nop     dword ptr [rax+rax+00h]
0x14004d3ad  lea     rdx, aSpoolerShutdow; "Spooler shutdown complete"
0x14004d3b4  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x14004d3bb  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004d3c0  mov     rcx, cs:?TerminateEvent@@3PEAXEA; void * TerminateEvent
0x14004d3c7  add     rsp, 20h
0x14004d3cb  pop     rbx
0x14004d3cc  jmp     cs:__imp_SetEvent
```
