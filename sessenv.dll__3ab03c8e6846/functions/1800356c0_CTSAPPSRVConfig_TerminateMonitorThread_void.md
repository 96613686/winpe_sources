# CTSAPPSRVConfig::TerminateMonitorThread(void)

- ea: `0x1800356c0`
- end: `0x180035773`
- name: `?TerminateMonitorThread@CTSAPPSRVConfig@@AEAAJXZ`
- size: `179`
- prototype: `__int64 __fastcall(CTSAPPSRVConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180035138`

## callees

- `0x180003f30`
- `0x18003508c`
- `0x1800356c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035707`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800356e8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800356e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800356f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800356f6`

## string_xrefs

- `0x180035723`: `Monitor thread failed to stop, wait status 0x%x, error code 0x%x`
- `0x18003573d`: `CTSAPPSRVConfig::TerminateMonitorThread`

## pseudocode

```c

```
