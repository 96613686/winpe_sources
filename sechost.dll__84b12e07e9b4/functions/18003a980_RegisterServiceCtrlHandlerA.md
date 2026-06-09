# RegisterServiceCtrlHandlerA

- ea: `0x18003a980`
- end: `0x18003a9da`
- name: `RegisterServiceCtrlHandlerA`
- size: `90`
- prototype: `SERVICE_STATUS_HANDLE __stdcall(LPCSTR lpServiceName, LPHANDLER_FUNCTION lpHandlerProc)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800198d8`
- `0x18001998c`
- `0x18003a980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a9cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a9cb`

## pseudocode

```c

```
