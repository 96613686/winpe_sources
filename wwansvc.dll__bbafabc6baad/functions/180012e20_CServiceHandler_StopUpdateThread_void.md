# CServiceHandler::StopUpdateThread(void)

- ea: `0x180012e20`
- end: `0x180012eb9`
- name: `?StopUpdateThread@CServiceHandler@@AEAAJXZ`
- size: `153`
- prototype: `int(CServiceHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180012c38`

## callees

- `0x18000e99c`
- `0x180012e20`
- `0x1800135e0`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012e86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012e86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012e3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e90`

## string_xrefs

- `0x180012e67`: `onecoreuap\net\wwan\service\core\servicemain.cpp`
- `0x180012ea5`: `onecoreuap\net\wwan\service\core\servicemain.cpp`
- `0x180012e96`: `CServiceHandler::StopUpdateThread`

## pseudocode

```c

```
