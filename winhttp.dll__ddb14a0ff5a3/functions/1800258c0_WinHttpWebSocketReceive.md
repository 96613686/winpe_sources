# WinHttpWebSocketReceive

- ea: `0x1800258c0`
- end: `0x180025d8a`
- name: `WinHttpWebSocketReceive`
- size: `1226`
- prototype: `DWORD __stdcall(HINTERNET hWebSocket, PVOID pvBuffer, DWORD dwBufferLength, DWORD *pdwBytesRead, WINHTTP_WEB_SOCKET_BUFFER_TYPE *peBufferType)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting`

## callees

- `0x180013680`
- `0x1800241a0`
- `0x1800258c0`
- `0x1800268a0`
- `0x180027514`
- `0x18003b230`
- `0x18003bc60`
- `0x18007f33c`
- `0x180084fdc`
- `0x18009bac4`
- `0x1800a1d10`
- `0x1800b0e18`
- `0x1800c69cc`
- `0x1800da848`
- `0x1800db6b0`
- `0x1800db758`
- `0x1800dd2e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025a27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025a27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025a5b`
- `ntdll!EtwEventActivityIdControl` at `0x180025abf`
- `ntdll!EtwEventActivityIdControl` at `0x180025abf`

## pseudocode

```c

```
