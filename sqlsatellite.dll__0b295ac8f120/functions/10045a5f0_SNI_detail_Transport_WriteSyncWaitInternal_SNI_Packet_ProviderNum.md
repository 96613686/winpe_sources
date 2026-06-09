# SNI::detail::Transport::WriteSyncWaitInternal(SNI_Packet *,ProviderNum)

- ea: `0x10045a5f0`
- end: `0x10045a87a`
- name: `?WriteSyncWaitInternal@Transport@detail@SNI@@IEAAKPEAVSNI_Packet@@W4ProviderNum@@@Z`
- size: `650`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x10043c140`
- `0x100453cc0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bb70`
- `0x10042c270`
- `0x10042c430`
- `0x10042c590`
- `0x1004349f0`
- `0x10045a5f0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10045a720`
- `KERNEL32!GetOverlappedResult` at `0x10045a720`
- `KERNEL32!WaitForSingleObject` at `0x10045a67e`
- `KERNEL32!WaitForSingleObject` at `0x10045a67e`
- `KERNEL32!GetLastError` at `0x10045a6a3`
- `KERNEL32!GetLastError` at `0x10045a72e`
- `KERNEL32!GetLastError` at `0x10045a6a3`
- `KERNEL32!GetLastError` at `0x10045a72e`

## string_xrefs

- `0x10045a61d`: `sql\common\dk\sni\src\transport.cpp`
- `0x10045a744`: `ERR|SNISend Packet Error during GetOverlappedResult, Bytes Try To Write:%d{DWORD}\n`
- `0x10045a628`: `SNI::detail::Transport::WriteSyncWaitInternal`
- `0x10045a6b9`: `ERR|SNISend Packet Error during WaitForSingleObject, Bytes Try To Write:%d{DWORD}\n`

## pseudocode

```c

```
