# Tcp::CheckAndAdjustSendBufferSizeBasedOnISB(void)

- ea: `0x10043a0f0`
- end: `0x10043a649`
- name: `?CheckAndAdjustSendBufferSizeBasedOnISB@Tcp@@IEAAKXZ`
- size: `1369`
- prototype: `unsigned int __fastcall(Tcp *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x100453090`
- `0x1004536e0`
- `0x1004539e0`
- `0x100458510`
- `0x1004591d0`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10043a0f0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10043a1f7`
- `KERNEL32!WaitForSingleObject` at `0x10043a1f7`
- `KERNEL32!SetEvent` at `0x10043a484`
- `KERNEL32!SetEvent` at `0x10043a484`
- `KERNEL32!ResetEvent` at `0x10043a353`
- `KERNEL32!ResetEvent` at `0x10043a353`
- `KERNEL32!GetLastError` at `0x10043a249`
- `KERNEL32!GetLastError` at `0x10043a35d`
- `KERNEL32!GetLastError` at `0x10043a249`
- `KERNEL32!GetLastError` at `0x10043a35d`
- `WS2_32!WSAIoctl` at `0x10043a42c`
- `WS2_32!WSAIoctl` at `0x10043a51e`
- `WS2_32!WSAIoctl` at `0x10043a42c`
- `WS2_32!WSAIoctl` at `0x10043a51e`
- `WS2_32!WSAGetOverlappedResult` at `0x10043a2dd`
- `WS2_32!WSAGetOverlappedResult` at `0x10043a2dd`
- `WS2_32!__imp_setsockopt` at `0x10043a57b`
- `WS2_32!__imp_setsockopt` at `0x10043a57b`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a2e7`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a43b`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a529`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a586`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a2e7`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a43b`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a529`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a586`

## string_xrefs

- `0x10043a10e`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c

```
