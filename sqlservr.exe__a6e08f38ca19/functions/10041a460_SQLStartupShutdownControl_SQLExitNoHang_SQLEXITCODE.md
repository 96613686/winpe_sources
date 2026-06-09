# SQLStartupShutdownControl::SQLExitNoHang(SQLEXITCODE)

- ea: `0x10041a460`
- end: `0x10041a4dd`
- name: `?SQLExitNoHang@SQLStartupShutdownControl@@EEAAXW4SQLEXITCODE@@@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x10041a460`

## import_xrefs

- `sqlmin!?ClearReadyForConnectionsEvents@StartUp@@SAXXZ` at `0x10041a468`
- `sqlmin!?ClearReadyForConnectionsEvents@StartUp@@SAXXZ` at `0x10041a468`
- `sqlmin!?ClearRecEvents@StartUp@@SAXXZ` at `0x10041a46e`
- `sqlmin!?ClearRecEvents@StartUp@@SAXXZ` at `0x10041a46e`
- `sqllang!?FlushAllExtendedEventSessions@@YAXXZ` at `0x10041a485`
- `sqllang!?FlushAllExtendedEventSessions@@YAXXZ` at `0x10041a485`
- `sqllang!?OnShutdown@CServerHeartbeat@@SAXH@Z` at `0x10041a49b`
- `sqllang!?OnShutdown@CServerHeartbeat@@SAXH@Z` at `0x10041a49b`
- `sqllang!?StopSrvRun@@YA_NK@Z` at `0x10041a4b9`
- `sqllang!?StopSrvRun@@YA_NK@Z` at `0x10041a4b9`
- `sqllang!?Shutdown@CEventNotificationSubsystemSink@@SAXG@Z` at `0x10041a48d`
- `sqllang!?Shutdown@CEventNotificationSubsystemSink@@SAXG@Z` at `0x10041a48d`
- `sqllang!?ShutdownSqlTrace@CTraceManagementTask@@SAX_N@Z` at `0x10041a479`
- `sqllang!?ShutdownSqlTrace@CTraceManagementTask@@SAX_N@Z` at `0x10041a479`
- `sqllang!?FlushAllSessions@AuditXESessionManager@SecAuditPkg@@SAXXZ` at `0x10041a47f`
- `sqllang!?FlushAllSessions@AuditXESessionManager@SecAuditPkg@@SAXXZ` at `0x10041a47f`
- `sqldk!?SQLShutdown@@YAXW4SQLEXITCODE@@@Z` at `0x10041a4ca`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10041a493`
- `api-ms-win-crt-stdio-l1-1-0!_flushall` at `0x10041a493`
- `sbs!?SbsShutdown@@YAXXZ` at `0x10041a4b1`
- `sbs!?SbsShutdown@@YAXXZ` at `0x10041a4b1`

## pseudocode

```c
char __fastcall SQLStartupShutdownControl::SQLExitNoHang(__int64 a1, unsigned int a2)
{
  char result; // al

  StartUp::ClearReadyForConnectionsEvents();
  StartUp::ClearRecEvents();
  CTraceManagementTask::ShutdownSqlTrace(a2 != 0);
  SecAuditPkg::AuditXESessionManager::FlushAllSessions();
  FlushAllExtendedEventSessions();
  CEventNotificationSubsystemSink::Shutdown(0);
  _flushall();
  CServerHeartbeat::OnShutdown(0);
  if ( *((_DWORD *)qword_10049F360 + 3645) )
    SbsShutdown();
  result = StopSrvRun(a2);
  if ( !result )
    return SQLShutdown(a2);
  return result;
}

```

## disassembly

```asm
0x10041a460  push    rbx
0x10041a462  sub     rsp, 20h
0x10041a466  mov     ebx, edx
0x10041a468  call    cs:__imp_?ClearReadyForConnectionsEvents@StartUp@@SAXXZ; StartUp::ClearReadyForConnectionsEvents(void)
0x10041a46e  call    cs:__imp_?ClearRecEvents@StartUp@@SAXXZ; StartUp::ClearRecEvents(void)
0x10041a474  test    ebx, ebx
0x10041a476  setnz   cl
0x10041a479  call    cs:__imp_?ShutdownSqlTrace@CTraceManagementTask@@SAX_N@Z; CTraceManagementTask::ShutdownSqlTrace(bool)
0x10041a47f  call    cs:__imp_?FlushAllSessions@AuditXESessionManager@SecAuditPkg@@SAXXZ; SecAuditPkg::AuditXESessionManager::FlushAllSessions(void)
0x10041a485  call    cs:__imp_?FlushAllExtendedEventSessions@@YAXXZ; FlushAllExtendedEventSessions(void)
0x10041a48b  xor     ecx, ecx
0x10041a48d  call    cs:__imp_?Shutdown@CEventNotificationSubsystemSink@@SAXG@Z; CEventNotificationSubsystemSink::Shutdown(ushort)
0x10041a493  call    cs:__imp__flushall
0x10041a499  xor     ecx, ecx
0x10041a49b  call    cs:__imp_?OnShutdown@CServerHeartbeat@@SAXH@Z; CServerHeartbeat::OnShutdown(int)
0x10041a4a1  mov     rax, cs:qword_10049F360
0x10041a4a8  cmp     dword ptr [rax+38F4h], 0
0x10041a4af  jz      short loc_10041A4B7
0x10041a4b1  call    cs:__imp_?SbsShutdown@@YAXXZ; SbsShutdown(void)
0x10041a4b7  mov     ecx, ebx
0x10041a4b9  call    cs:__imp_?StopSrvRun@@YA_NK@Z; StopSrvRun(ulong)
0x10041a4bf  test    al, al
0x10041a4c1  jnz     short loc_10041A4D7
0x10041a4c3  mov     ecx, ebx
0x10041a4c5  add     rsp, 20h
0x10041a4c9  pop     rbx
0x10041a4ca  jmp     cs:__imp_?SQLShutdown@@YAXW4SQLEXITCODE@@@Z; SQLShutdown(SQLEXITCODE)
0x10041a4d7  add     rsp, 20h
0x10041a4db  pop     rbx
0x10041a4dc  retn
```
