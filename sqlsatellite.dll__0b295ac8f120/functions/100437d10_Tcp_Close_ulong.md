# Tcp::Close(ulong)

- ea: `0x100437d10`
- end: `0x1004380bb`
- name: `?Close@Tcp@@MEAAKK@Z`
- size: `939`
- prototype: `unsigned int __fastcall(Tcp *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100437d10`
- `0x10045a1b0`
- `0x10045d370`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x100438051`
- `KERNEL32!InterlockedPushEntrySList` at `0x100438051`
- `KERNEL32!WaitForSingleObject` at `0x100437e48`
- `KERNEL32!WaitForSingleObject` at `0x100437f1d`
- `KERNEL32!WaitForSingleObject` at `0x100437e48`
- `KERNEL32!WaitForSingleObject` at `0x100437f1d`
- `KERNEL32!CloseHandle` at `0x100437fae`
- `KERNEL32!CloseHandle` at `0x100437fae`
- `KERNEL32!GetLastError` at `0x100437e67`
- `KERNEL32!GetLastError` at `0x100437f4d`
- `KERNEL32!GetLastError` at `0x100437fb8`
- `KERNEL32!GetLastError` at `0x100437e67`
- `KERNEL32!GetLastError` at `0x100437f4d`
- `KERNEL32!GetLastError` at `0x100437fb8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100438003`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100438003`
- `WS2_32!__imp_shutdown` at `0x100437da7`
- `WS2_32!__imp_shutdown` at `0x100437da7`
- `WS2_32!__imp_WSAGetLastError` at `0x100437db2`
- `WS2_32!__imp_WSAGetLastError` at `0x100437db2`

## string_xrefs

- `0x100437d35`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c

```
