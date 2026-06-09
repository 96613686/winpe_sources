# StartServiceShutdown(void)

- ea: `0x180029d70`
- end: `0x180029dcf`
- name: `?StartServiceShutdown@@YAXXZ`
- size: `95`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001ad90`
- `0x1800266f0`

## callees

- `0x180029d70`
- `0x18002ef74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029dbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029dbd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180029da0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180029da0`

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
0x180029d70  sub     rsp, 28h
0x180029d74  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180029d7b  lea     rdx, ServiceStatus; lpServiceStatus
0x180029d82  mov     cs:ServiceStatus.dwCurrentState, 3
0x180029d8c  mov     cs:ServiceStatus.dwCheckPoint, 0
0x180029d96  mov     cs:ServiceStatus.dwWaitHint, 4E20h
0x180029da0  call    cs:__imp_SetServiceStatus
0x180029da7  nop     dword ptr [rax+rax+00h]
0x180029dac  call    _Shutdown
0x180029db1  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hEvent
0x180029db8  test    rcx, rcx
0x180029dbb  jz      short loc_180029DC9
0x180029dbd  call    cs:__imp_SetEvent
0x180029dc4  nop     dword ptr [rax+rax+00h]
0x180029dc9  add     rsp, 28h
0x180029dcd  retn
```
