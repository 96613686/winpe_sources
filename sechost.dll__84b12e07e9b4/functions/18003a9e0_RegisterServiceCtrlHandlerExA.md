# RegisterServiceCtrlHandlerExA

- ea: `0x18003a9e0`
- end: `0x18003aa43`
- name: `RegisterServiceCtrlHandlerExA`
- size: `99`
- prototype: `SERVICE_STATUS_HANDLE __stdcall(LPCSTR lpServiceName, LPHANDLER_FUNCTION_EX lpHandlerProc, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180011290`
- `0x1800198d8`
- `0x18003a9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aa2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aa2f`

## pseudocode

```c

```
