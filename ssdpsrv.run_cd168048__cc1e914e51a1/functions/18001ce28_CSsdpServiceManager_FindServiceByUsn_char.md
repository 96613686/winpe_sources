# CSsdpServiceManager::FindServiceByUsn(char *)

- ea: `0x18001ce28`
- end: `0x18001cef1`
- name: `?FindServiceByUsn@CSsdpServiceManager@@QEAAPEAVCSsdpService@@PEAD@Z`
- size: `201`
- prototype: `struct CSsdpService *__fastcall(LPCRITICAL_SECTION lpCriticalSection, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180018590`

## callees

- `0x18001ce28`
- `0x18002fe28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ce8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce3d`

## pseudocode

```c

```
