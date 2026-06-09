# GetCurrentTimeZoneId

- ea: `0x180026010`
- end: `0x18002624e`
- name: `GetCurrentTimeZoneId`
- size: `574`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dff4`
- `0x180010880`
- `0x180010f00`
- `0x18001c664`
- `0x180025d14`
- `0x180025f48`

## callees

- `0x180024910`
- `0x180025e4c`
- `0x180026010`
- `0x180026854`
- `0x180026884`
- `0x180026dfc`
- `0x180028f16`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026091`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026091`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026209`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026211`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002610c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002610c`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x180026062`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x180026062`

## pseudocode

```c

```
