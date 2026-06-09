# TcpConnection::CloseOutstandingSocket(void)

- ea: `0x100436280`
- end: `0x100436424`
- name: `?CloseOutstandingSocket@TcpConnection@@QEAAKXZ`
- size: `420`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100435c10`
- `0x100438970`
- `0x100438f00`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100436280`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x100436360`
- `WS2_32!__imp_closesocket` at `0x100436360`
- `WS2_32!__imp_shutdown` at `0x1004362f7`
- `WS2_32!__imp_shutdown` at `0x1004362f7`
- `WS2_32!__imp_WSAGetLastError` at `0x100436306`
- `WS2_32!__imp_WSAGetLastError` at `0x10043636f`
- `WS2_32!__imp_WSAGetLastError` at `0x100436306`
- `WS2_32!__imp_WSAGetLastError` at `0x10043636f`

## string_xrefs

- `0x10043629f`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c

```
