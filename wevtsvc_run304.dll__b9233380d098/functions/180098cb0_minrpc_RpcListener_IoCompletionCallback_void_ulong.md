# minrpc::RpcListener::IoCompletionCallback(void *,ulong)

- ea: `0x180098cb0`
- end: `0x180098df5`
- name: `?IoCompletionCallback@RpcListener@minrpc@@AEAAXPEAXK@Z`
- size: `325`
- prototype: `void __fastcall(minrpc::RpcListener *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800d30e0`

## callees

- `0x1800660ac`
- `0x18006d84c`
- `0x180098cb0`
- `0x180098dfc`
- `0x180098f8c`
- `0x18009973c`
- `0x1800d3044`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180098ce0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180098ce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d71`
- `WS2_32!__imp_setsockopt` at `0x180098d67`
- `WS2_32!__imp_setsockopt` at `0x180098d67`

## string_xrefs

- `0x180098d86`: `IoCompletionCallback[setsockopt]`
- `0x180098d31`: `IoCompletionCallback[AcceptEx]`

## pseudocode

```c

```
