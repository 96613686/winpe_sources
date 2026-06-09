# HNIntRefreshSecurity(ulong *)

- ea: `0x18015a4dc`
- end: `0x18015a6de`
- name: `?HNIntRefreshSecurity@@YAKPEAK@Z`
- size: `514`
- prototype: `unsigned int __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800f01a4`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800868b8`
- `0x180106340`
- `0x180107330`
- `0x18015986c`
- `0x18015a4dc`
- `0x18015ee88`
- `0x18019c518`
- `0x18019c79c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015a681`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015a681`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015a579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015a579`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a595`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015a595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015a57f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015a57f`
- `ntdll!WinSqmIncrementDWORD` at `0x18015a56c`
- `ntdll!WinSqmIncrementDWORD` at `0x18015a56c`

## pseudocode

```c

```
