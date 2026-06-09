# WinHttpOpen

- ea: `0x1800604c0`
- end: `0x18006084d`
- name: `WinHttpOpen`
- size: `909`
- prototype: `HINTERNET __stdcall(LPCWSTR pszAgentW, DWORD dwAccessType, LPCWSTR pszProxyW, LPCWSTR pszProxyBypassW, DWORD dwFlags)`
- caller_count: `7`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x18005feac`
- `0x18007b4d4`
- `0x18009d5dc`
- `0x18009efe0`
- `0x1800a5860`
- `0x1800bc674`
- `0x1800bcc00`

## callees

- `0x1800065a0`
- `0x180013778`
- `0x1800241a0`
- `0x18003b230`
- `0x180041eb0`
- `0x1800600c0`
- `0x1800604c0`
- `0x180060854`
- `0x180062424`
- `0x18007dc8c`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf9a4`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800606b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800606b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060586`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060586`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800605a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800605eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060623`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800605a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800605eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800606c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800607f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800606c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800607f3`
- `ntdll!EtwEventActivityIdControl` at `0x1800605ce`
- `ntdll!EtwEventActivityIdControl` at `0x1800605ce`

## pseudocode

```c

```
