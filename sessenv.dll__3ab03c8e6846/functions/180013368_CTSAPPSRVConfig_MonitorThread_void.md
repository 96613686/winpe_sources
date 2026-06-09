# CTSAPPSRVConfig::MonitorThread(void)

- ea: `0x180013368`
- end: `0x180013463`
- name: `?MonitorThread@CTSAPPSRVConfig@@AEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(CTSAPPSRVConfig *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180035680`

## callees

- `0x180003f30`
- `0x180013368`
- `0x18003537c`
- `0x180035600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001338a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001338a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001341c`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001341c`
- `USERENV!RegisterGPNotification` at `0x180013380`
- `USERENV!RegisterGPNotification` at `0x180013380`

## string_xrefs

- `0x1800133c1`: `CTSAPPSRVConfig::MonitorThread`
- `0x1800133cb`: `SetupWaitOnRegistry failed: 0x%x in %s`
- `0x180013447`: `Config Monitor Thread Terminating`

## pseudocode

```c

```
