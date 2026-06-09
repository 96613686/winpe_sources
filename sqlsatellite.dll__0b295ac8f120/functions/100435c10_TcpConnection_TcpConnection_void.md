# TcpConnection::~TcpConnection(void)

- ea: `0x100435c10`
- end: `0x100435d14`
- name: `??1TcpConnection@@QEAA@XZ`
- size: `260`
- prototype: `void __fastcall(TcpConnection *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10048aacc`

## callees

- `0x10042b7f0`
- `0x10042c0b0`
- `0x100435c10`
- `0x100436280`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x100435c33`
- `KERNEL32!WaitForSingleObject` at `0x100435c33`
- `KERNEL32!CloseHandle` at `0x100435cca`
- `KERNEL32!CloseHandle` at `0x100435cca`
- `KERNEL32!GetLastError` at `0x100435c42`
- `KERNEL32!GetLastError` at `0x100435c42`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100435cb4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100435cb4`

## string_xrefs

- `0x100435c69`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100435c98`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100435cfd`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c

```
