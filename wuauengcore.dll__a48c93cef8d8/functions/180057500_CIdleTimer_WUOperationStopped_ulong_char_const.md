# CIdleTimer::WUOperationStopped(ulong &,char const *)

- ea: `0x180057500`
- end: `0x180057ac2`
- name: `?WUOperationStopped@CIdleTimer@@UEAAJAEAKPEBD@Z`
- size: `1474`
- prototype: `__int64 __fastcall(CIdleTimer *__hidden this, unsigned int *, const char *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x18000def4`
- `0x180036560`
- `0x18005657c`
- `0x180057500`
- `0x180057c5c`
- `0x180057f98`
- `0x1800589a4`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057727`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057727`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057a7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005769e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057795`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057a45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005769e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057795`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057a45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057a86`

## string_xrefs

- `0x1800575d1`: `C:\__w\1\s\src\Client\Engine\Agent\IdleTimer.cpp`
- `0x1800576f5`: `C:\__w\1\s\src\Client\Engine\Agent\IdleTimer.cpp`
- `0x180057776`: `C:\__w\1\s\src\Client\Engine\Agent\IdleTimer.cpp`
- `0x180057565`: `Attempted to stop WU operation (%d) when idle timer wasn't initialized`
- `0x180057599`: `WUOperationStopped called for invalid task number`
- `0x1800576b8`: `Attempt to find WU task record %d failed, hr = %lX`
- `0x180057746`: `WU operation (%d) stopped, but operation count was already at zero`
- `0x1800577ab`: `; will NOT start idle timer (task did not previously stop it`
- `0x180057894`: `Network operation count was already at zero`
- `0x180057910`: `System operation count was already at zero`
- `0x1800579b0`: `Priority operation count was already at zero`

## pseudocode

```c

```
