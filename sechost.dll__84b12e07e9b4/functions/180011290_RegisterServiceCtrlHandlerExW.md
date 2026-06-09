# RegisterServiceCtrlHandlerExW

- ea: `0x180011290`
- end: `0x180011339`
- name: `RegisterServiceCtrlHandlerExW`
- size: `169`
- prototype: `SERVICE_STATUS_HANDLE __stdcall(LPCWSTR lpServiceName, LPHANDLER_FUNCTION_EX lpHandlerProc, LPVOID lpContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18003a9e0`

## callees

- `0x180011290`
- `0x180011340`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800112fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800112fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001131f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001131f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800112c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800112c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011306`

## pseudocode

```c

```
