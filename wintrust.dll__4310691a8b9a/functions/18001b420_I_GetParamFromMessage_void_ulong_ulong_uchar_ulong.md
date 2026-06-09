# I_GetParamFromMessage(void *,ulong,ulong,uchar * *,ulong *)

- ea: `0x18001b420`
- end: `0x18001b524`
- name: `?I_GetParamFromMessage@@YAJPEAXKKPEAPEAEPEAK@Z`
- size: `260`
- prototype: `__int64 __fastcall(HCRYPTMSG hCryptMsg, DWORD dwParamType, DWORD dwIndex, unsigned __int8 **, unsigned int *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fbec`
- `0x1800101a4`
- `0x180010350`
- `0x18001b27c`
- `0x180029250`
- `0x18002c448`
- `0x18002ce88`
- `0x18002dbcc`
- `0x18003813c`
- `0x180039dd8`
- `0x180039f50`
- `0x18003f904`

## callees

- `0x18001b420`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b4ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b467`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b467`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b4f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4db`
- `CRYPT32!CryptMsgGetParam` at `0x18001b44b`
- `CRYPT32!CryptMsgGetParam` at `0x18001b48e`
- `CRYPT32!CryptMsgGetParam` at `0x18001b44b`
- `CRYPT32!CryptMsgGetParam` at `0x18001b48e`

## pseudocode

```c

```
