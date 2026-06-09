# SpoolerShutdown(void)

- ea: `0x140048cac`
- end: `0x140048d93`
- name: `?SpoolerShutdown@@YAXXZ`
- size: `231`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140047fc0`
- `0x140048140`
- `0x14004fdd0`
- `0x140050880`

## callees

- `0x14002f030`
- `0x14003cf44`
- `0x140048cac`
- `0x140065c40`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140048d8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140048d67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140048d67`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140048cc3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140048cc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140048d0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140048d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048cc9`

## string_xrefs

- `0x140048cdd`: `Spooler is already shutting down...`
- `0x140048d6d`: `Spooler shutdown complete`

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
0x140048cac  push    rbx
0x140048cae  sub     rsp, 20h
0x140048cb2  mov     edx, 1; bManualReset
0x140048cb7  lea     r9, ?szSpoolerExitingEvent@@3PAGA; "Spooler_exiting"
0x140048cbe  mov     r8d, edx; bInitialState
0x140048cc1  xor     ecx, ecx; lpEventAttributes
0x140048cc3  call    cs:__imp_CreateEventW
0x140048cc9  call    cs:__imp_GetLastError
0x140048ccf  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x140048cd6  cmp     eax, 0B7h
0x140048cdb  jnz     short loc_140048CEE
0x140048cdd  lea     rdx, aSpoolerIsAlrea; "Spooler is already shutting down..."
0x140048ce4  add     rsp, 20h
0x140048ce8  pop     rbx
0x140048ce9  jmp     ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048cee  lea     rdx, aSpoolerShuttin; "Spooler shutting down..."
0x140048cf5  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048cfa  mov     ecx, 3; unsigned int
0x140048cff  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x140048d04  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140048d0b  call    cs:__imp_EnterCriticalSection
0x140048d11  lea     rdx, aShuttingDownPr; "Shutting down providers..."
0x140048d18  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x140048d1f  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048d24  mov     rbx, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x140048d2b  jmp     short loc_140048D43
0x140048d2d  mov     rax, [rbx+1D8h]
0x140048d34  test    rax, rax
0x140048d37  jz      short loc_140048D40
0x140048d39  xor     ecx, ecx
0x140048d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048d40  mov     rbx, [rbx]
0x140048d43  test    rbx, rbx
0x140048d46  jnz     short loc_140048D2D
0x140048d48  lea     rdx, aShuttingDownRo; "Shutting down router..."
0x140048d4f  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x140048d56  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048d5b  call    SplShutDownRouter
0x140048d60  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140048d67  call    cs:__imp_LeaveCriticalSection
0x140048d6d  lea     rdx, aSpoolerShutdow; "Spooler shutdown complete"
0x140048d74  lea     rcx, aSpoolershutdow; "SpoolerShutdown"
0x140048d7b  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048d80  mov     rcx, cs:?TerminateEvent@@3PEAXEA; void * TerminateEvent
0x140048d87  add     rsp, 20h
0x140048d8b  pop     rbx
0x140048d8c  jmp     cs:__imp_SetEvent
```
