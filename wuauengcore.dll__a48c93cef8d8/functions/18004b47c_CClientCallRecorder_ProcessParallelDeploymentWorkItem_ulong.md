# CClientCallRecorder::ProcessParallelDeploymentWorkItem(ulong)

- ea: `0x18004b47c`
- end: `0x18004b8db`
- name: `?ProcessParallelDeploymentWorkItem@CClientCallRecorder@@QEAAJK@Z`
- size: `1119`
- prototype: `__int64 __fastcall(CClientCallRecorder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048f10`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x18001bdb8`
- `0x18001da00`
- `0x18004b2a4`
- `0x18004b47c`
- `0x18004b8e4`
- `0x180052458`
- `0x1800530f8`
- `0x1800c7580`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b8a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004b8a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b4ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b4ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004b4dd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004b4dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b5a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b731`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b76b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b87a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b5a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b731`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b76b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b87a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b7b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b799`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b7b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b896`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004b629`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004b629`

## string_xrefs

- `0x18004b7df`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004b802`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004b557`: `Going through loop during shutdown`
- `0x18004b51f`: `Failed to run deployments in parallel; Handling deployment call [ID = %d] in the worker thread`
- `0x18004b82a`: `Too many parallel calls being added (> %zd); aborting parallel call handling completely`
- `0x18004b852`: `WI thread for parallel deployments exiting...`

## pseudocode

```c

```
