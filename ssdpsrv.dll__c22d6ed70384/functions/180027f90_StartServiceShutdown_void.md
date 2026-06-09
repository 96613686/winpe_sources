# StartServiceShutdown(void)

- ea: `0x180027f90`
- end: `0x180027fe2`
- name: `?StartServiceShutdown@@YAXXZ`
- size: `82`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180019af0`
- `0x180024ba0`

## callees

- `0x180027f90`
- `0x18002cf44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027fd7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027fd7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180027fc0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180027fc0`

## pseudocode

```c
void StartServiceShutdown(void)
{
  ServiceStatus.dwCurrentState = 3;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 20000;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  Shutdown();
  if ( g_hServiceStopEvent )
    SetEvent(g_hServiceStopEvent);
}

```

## disassembly

```asm
0x180027f90  sub     rsp, 28h
0x180027f94  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180027f9b  lea     rdx, ServiceStatus; lpServiceStatus
0x180027fa2  mov     cs:ServiceStatus.dwCurrentState, 3
0x180027fac  mov     cs:ServiceStatus.dwCheckPoint, 0
0x180027fb6  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x180027fc0  call    cs:__imp_SetServiceStatus
0x180027fc6  call    _Shutdown
0x180027fcb  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hEvent
0x180027fd2  test    rcx, rcx
0x180027fd5  jz      short loc_180027FDD
0x180027fd7  call    cs:__imp_SetEvent
0x180027fdd  add     rsp, 28h
0x180027fe1  retn
```
