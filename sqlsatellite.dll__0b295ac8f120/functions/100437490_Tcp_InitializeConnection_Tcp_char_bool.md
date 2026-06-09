# Tcp::InitializeConnection(Tcp *,char *,bool)

- ea: `0x100437490`
- end: `0x100437951`
- name: `?InitializeConnection@Tcp@@SAKPEAV1@PEAD_N@Z`
- size: `1217`
- prototype: `unsigned int __fastcall(struct Tcp *this, PVOID lpOutputBuffer, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004510d0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100437490`
- `0x100437960`
- `0x100437b30`
- `0x10045a2f0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004377f4`
- `KERNEL32!GetLastError` at `0x1004377f4`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x1004376b6`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x1004376b6`
- `WS2_32!WSAIoctl` at `0x100437626`
- `WS2_32!WSAIoctl` at `0x100437626`
- `WS2_32!__imp_getpeername` at `0x1004376f6`
- `WS2_32!__imp_getpeername` at `0x1004376f6`
- `WS2_32!__imp_getsockname` at `0x100437750`
- `WS2_32!__imp_getsockname` at `0x100437750`
- `WS2_32!__imp_ioctlsocket` at `0x1004378b7`
- `WS2_32!__imp_ioctlsocket` at `0x1004378b7`
- `WS2_32!__imp_setsockopt` at `0x100437565`
- `WS2_32!__imp_setsockopt` at `0x100437593`
- `WS2_32!__imp_setsockopt` at `0x1004375b6`
- `WS2_32!__imp_setsockopt` at `0x100437565`
- `WS2_32!__imp_setsockopt` at `0x100437593`
- `WS2_32!__imp_setsockopt` at `0x1004375b6`
- `WS2_32!__imp_WSAGetLastError` at `0x1004375c1`
- `WS2_32!__imp_WSAGetLastError` at `0x100437631`
- `WS2_32!__imp_WSAGetLastError` at `0x100437700`
- `WS2_32!__imp_WSAGetLastError` at `0x10043775a`
- `WS2_32!__imp_WSAGetLastError` at `0x1004378c2`
- `WS2_32!__imp_WSAGetLastError` at `0x1004375c1`
- `WS2_32!__imp_WSAGetLastError` at `0x100437631`
- `WS2_32!__imp_WSAGetLastError` at `0x100437700`
- `WS2_32!__imp_WSAGetLastError` at `0x10043775a`
- `WS2_32!__imp_WSAGetLastError` at `0x1004378c2`

## string_xrefs

- `0x1004374d1`: `sql\common\dk\sni\src\tcp.cpp`
- `0x10043779d`: `sql\common\dk\sni\src\transport.cpp`
- `0x100437809`: `ERR|SNISetFileCompletionNotificationModes for FILE_SKIP_SET_EVENT_ON_HANDLE failed: %d{WINERR}\n`

## pseudocode

```c

```
