# CDefTaskLock::CreateInstance(IUnknown *,HWND__ *,uint,CDefTaskLock * *)

- ea: `0x18003b0fc`
- end: `0x18003b21c`
- name: `?CreateInstance@CDefTaskLock@@SAJPEAUIUnknown@@PEAUHWND__@@IPEAPEAV1@@Z`
- size: `288`
- prototype: `__int64 __fastcall(struct IUnknown *, HWND, unsigned int, struct CDefTaskLock **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180040f88`

## callees

- `0x18000268c`
- `0x18003b0fc`
- `0x180054e70`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003b15f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003b16f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003b15f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003b16f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b1cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b1cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b1bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b1bb`

## pseudocode

```c

```
