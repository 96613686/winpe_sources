# Windows::Internal::Events::WatchdogEventCallMonitor::StartMonitor(Windows::Internal::Events::WatchdogEventCallMonitor::WatchdogToken &,unsigned __int64)

- ea: `0x18000f990`
- end: `0x18000fa48`
- name: `?StartMonitor@WatchdogEventCallMonitor@Events@Internal@Windows@@QEAAXAEAVWatchdogToken@1234@_K@Z`
- size: `184`
- prototype: `void __fastcall(Windows::Internal::Events::WatchdogEventCallMonitor *__hidden this, struct Windows::Internal::Events::WatchdogEventCallMonitor::WatchdogToken *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f4b4`
- `0x18005ff2c`

## callees

- `0x18000f990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fa41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f9cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f9cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f9b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f9b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f9a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f9a5`

## pseudocode

```c

```
