# SetProcessExtensionPointDisablePolicy

- ea: `0x14004ccac`
- end: `0x14004cd67`
- name: `SetProcessExtensionPointDisablePolicy`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14004c198`

## callees

- `0x14001748c`
- `0x140040654`
- `0x14004ccac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004cd29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004cd29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14004ccba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14004ccba`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x14004ccd9`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x14004ccd9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14004cd19`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14004cd4d`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14004cd19`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14004cd4d`

## string_xrefs

- `0x14004cd38`: `Failed to set DisableExtensionPoints policy! Error: %d`
- `0x14004cd3f`: `SetProcessExtensionPointDisablePolicy`

## pseudocode

```c

```
