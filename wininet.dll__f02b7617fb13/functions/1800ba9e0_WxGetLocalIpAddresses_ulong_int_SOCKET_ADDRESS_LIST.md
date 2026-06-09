# WxGetLocalIpAddresses(ulong,int,_SOCKET_ADDRESS_LIST * *)

- ea: `0x1800ba9e0`
- end: `0x1800bae04`
- name: `?WxGetLocalIpAddresses@@YAJKHPEAPEAU_SOCKET_ADDRESS_LIST@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(unsigned int, int, struct _SOCKET_ADDRESS_LIST **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800ba6c0`

## callees

- `0x180025980`
- `0x180027ec0`
- `0x1800ba9e0`
- `0x1800bbbc4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e41b0`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baae9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baae9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bac4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bac4c`
- `WS2_32!WSAIoctl` at `0x1800bab2f`
- `WS2_32!WSAIoctl` at `0x1800bab6b`
- `WS2_32!WSAIoctl` at `0x1800bab2f`
- `WS2_32!WSAIoctl` at `0x1800bab6b`
- `WS2_32!__imp_closesocket` at `0x1800babf5`
- `WS2_32!__imp_closesocket` at `0x1800babf5`
- `WS2_32!__imp_setsockopt` at `0x1800baab3`
- `WS2_32!__imp_setsockopt` at `0x1800baab3`
- `WS2_32!__imp_socket` at `0x1800baa85`
- `WS2_32!__imp_socket` at `0x1800baa85`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bac97`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bac97`
- `WS2_32!__imp_WSAStartup` at `0x1800baa53`
- `WS2_32!__imp_WSAStartup` at `0x1800baa53`
- `WS2_32!__imp_WSACleanup` at `0x1800babfb`
- `WS2_32!__imp_WSACleanup` at `0x1800babfb`

## pseudocode

```c

```
