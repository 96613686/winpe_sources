# TcpConnection::CheckCompletedAsyncConnect(void)

- ea: `0x100436140`
- end: `0x100436277`
- name: `?CheckCompletedAsyncConnect@TcpConnection@@QEAAKXZ`
- size: `311`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100438970`
- `0x100438f00`

## callees

- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x100436140`

## import_xrefs

- `WS2_32!WSAGetOverlappedResult` at `0x1004361bd`
- `WS2_32!WSAGetOverlappedResult` at `0x1004361bd`
- `WS2_32!__imp_setsockopt` at `0x1004361dd`
- `WS2_32!__imp_setsockopt` at `0x1004361dd`
- `WS2_32!__imp_WSAGetLastError` at `0x1004361e8`
- `WS2_32!__imp_WSAGetLastError` at `0x1004361fc`
- `WS2_32!__imp_WSAGetLastError` at `0x1004361e8`
- `WS2_32!__imp_WSAGetLastError` at `0x1004361fc`

## string_xrefs

- `0x100436159`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100436164`: `TcpConnection::CheckCompletedAsyncConnect`

## pseudocode

```c

```
