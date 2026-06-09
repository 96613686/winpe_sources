# SetWindowServicesDestroyCallback

- ea: `0x1800159b0`
- end: `0x180015ac0`
- name: `SetWindowServicesDestroyCallback`
- size: `272`
- prototype: `__int64 __fastcall(HWND hWnd, LPCWSTR lpModuleName)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180017a5c`

## callees

- `0x1800159b0`
- `0x180016310`
- `0x180017ad0`
- `0x180017b0c`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180015a5d`
- `ntdll!RtlSetLastWin32Error` at `0x180015a5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800159cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800159cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800159f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800159f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a49`

## pseudocode

```c

```
