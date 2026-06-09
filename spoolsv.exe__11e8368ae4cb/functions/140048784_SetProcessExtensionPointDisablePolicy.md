# SetProcessExtensionPointDisablePolicy

- ea: `0x140048784`
- end: `0x140048820`
- name: `SetProcessExtensionPointDisablePolicy`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140047d7c`

## callees

- `0x1400160a0`
- `0x14003cd0c`
- `0x140048784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400487ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400487ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140048792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140048792`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1400487ab`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1400487ab`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1400487e5`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14004880d`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1400487e5`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14004880d`

## string_xrefs

- `0x1400487f8`: `Failed to set DisableExtensionPoints policy! Error: %d`
- `0x1400487ff`: `SetProcessExtensionPointDisablePolicy`

## pseudocode

```c

```
