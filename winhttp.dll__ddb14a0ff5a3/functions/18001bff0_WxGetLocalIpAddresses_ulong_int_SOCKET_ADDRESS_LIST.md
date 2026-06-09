# WxGetLocalIpAddresses(ulong,int,_SOCKET_ADDRESS_LIST * *)

- ea: `0x18001bff0`
- end: `0x18001c4fc`
- name: `?WxGetLocalIpAddresses@@YAJKHPEAPEAU_SOCKET_ADDRESS_LIST@@@Z`
- size: `1292`
- prototype: `__int64 __fastcall(unsigned int, int, struct _SOCKET_ADDRESS_LIST **)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x18001bcd0`
- `0x180092d54`
- `0x1800cab80`

## callees

- `0x1800081a0`
- `0x18001b480`
- `0x18001bff0`
- `0x18006c940`
- `0x18009b9b0`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf4c4`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c32c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c32c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c358`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c358`
- `WS2_32!WSAIoctl` at `0x18001c170`
- `WS2_32!WSAIoctl` at `0x18001c1b8`
- `WS2_32!WSAIoctl` at `0x18001c170`
- `WS2_32!WSAIoctl` at `0x18001c1b8`
- `WS2_32!__imp_closesocket` at `0x18001c232`
- `WS2_32!__imp_closesocket` at `0x18001c232`
- `WS2_32!__imp_setsockopt` at `0x18001c0ed`
- `WS2_32!__imp_setsockopt` at `0x18001c0ed`
- `WS2_32!__imp_socket` at `0x18001c0b7`
- `WS2_32!__imp_socket` at `0x18001c0b7`
- `WS2_32!__imp_WSAGetLastError` at `0x18001c38b`
- `WS2_32!__imp_WSAGetLastError` at `0x18001c38b`
- `WS2_32!__imp_WSAStartup` at `0x18001c086`
- `WS2_32!__imp_WSAStartup` at `0x18001c086`
- `WS2_32!__imp_WSACleanup` at `0x18001c238`
- `WS2_32!__imp_WSACleanup` at `0x18001c238`

## pseudocode

```c

```
