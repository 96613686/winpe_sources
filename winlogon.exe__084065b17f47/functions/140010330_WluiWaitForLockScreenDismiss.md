# WluiWaitForLockScreenDismiss

- ea: `0x140010330`
- end: `0x14001050c`
- name: `WluiWaitForLockScreenDismiss`
- size: `476`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1400619c0`
- `0x140062e20`
- `0x1400858e0`

## callees

- `0x140010330`
- `0x140012360`
- `0x14009a9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400104b9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400104b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140010414`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140010358`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140010398`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400103cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140010398`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400103cd`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1400103ed`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1400104c6`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1400103ed`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1400104c6`
- `RPCRT4!NdrClientCall3` at `0x140010448`
- `RPCRT4!NdrClientCall3` at `0x140010448`
- `RPCRT4!I_RpcExceptionFilter` at `0x14009d4ae`
- `RPCRT4!I_RpcExceptionFilter` at `0x14009d4ae`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140010376`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x140010376`

## pseudocode

```c

```
