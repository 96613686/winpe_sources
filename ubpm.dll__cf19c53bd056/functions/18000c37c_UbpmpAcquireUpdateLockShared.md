# UbpmpAcquireUpdateLockShared

- ea: `0x18000c37c`
- end: `0x18000c3ce`
- name: `UbpmpAcquireUpdateLockShared`
- size: `82`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a420`
- `0x18000b340`
- `0x18000e090`

## callees

- `0x18000c37c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x18000c3c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c393`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c39e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c393`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c39e`

## pseudocode

```c

```
