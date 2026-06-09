# UbpmpReleaseUpdateLockShared

- ea: `0x18000b2f4`
- end: `0x18000b335`
- name: `UbpmpReleaseUpdateLockShared`
- size: `65`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a420`
- `0x18000b340`

## callees

- `0x18000b2f4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000b32a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b303`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b303`

## pseudocode

```c

```
