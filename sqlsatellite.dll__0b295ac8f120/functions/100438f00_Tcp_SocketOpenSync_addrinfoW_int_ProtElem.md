# Tcp::SocketOpenSync(addrinfoW *,int,ProtElem *)

- ea: `0x100438f00`
- end: `0x10043937f`
- name: `?SocketOpenSync@Tcp@@QEAAKPEAUaddrinfoW@@HPEAVProtElem@@@Z`
- size: `1151`
- prototype: `unsigned int __fastcall(Tcp *__hidden this, struct addrinfoW *, DWORD dwMilliseconds, struct ProtElem *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x100439390`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c0b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100435d20`
- `0x100436140`
- `0x100436280`
- `0x100436430`
- `0x1004368f0`
- `0x100438f00`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x10043904b`
- `KERNEL32!WaitForSingleObject` at `0x100439276`
- `KERNEL32!WaitForSingleObject` at `0x10043904b`
- `KERNEL32!WaitForSingleObject` at `0x100439276`
- `KERNEL32!CloseHandle` at `0x100439306`
- `KERNEL32!CloseHandle` at `0x100439306`
- `KERNEL32!GetLastError` at `0x10043907a`
- `KERNEL32!GetLastError` at `0x100439285`
- `KERNEL32!GetLastError` at `0x10043907a`
- `KERNEL32!GetLastError` at `0x100439285`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004392ef`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004392ef`
- `WS2_32!__imp_connect` at `0x100439147`
- `WS2_32!__imp_connect` at `0x100439147`
- `WS2_32!__imp_WSAGetLastError` at `0x100439152`
- `WS2_32!__imp_WSAGetLastError` at `0x100439152`

## string_xrefs

- `0x100438f37`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004390fa`: `TcpConnection::SyncOpen`
- `0x100439003`: `TcpConnection::WaitForCompletion`
- `0x100438f42`: `Tcp::SocketOpenSync`

## pseudocode

```c

```
