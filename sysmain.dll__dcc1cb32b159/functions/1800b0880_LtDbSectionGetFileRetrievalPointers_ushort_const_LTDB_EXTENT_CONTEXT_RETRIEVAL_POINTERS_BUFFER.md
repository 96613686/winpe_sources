# LtDbSectionGetFileRetrievalPointers(ushort const *,_LTDB_EXTENT_CONTEXT *,RETRIEVAL_POINTERS_BUFFER * *)

- ea: `0x1800b0880`
- end: `0x1800b0af5`
- name: `?LtDbSectionGetFileRetrievalPointers@@YAKPEBGPEAU_LTDB_EXTENT_CONTEXT@@PEAPEAURETRIEVAL_POINTERS_BUFFER@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _LTDB_EXTENT_CONTEXT *, struct RETRIEVAL_POINTERS_BUFFER **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800b06dc`
- `0x1800b0cb4`

## callees

- `0x180086614`
- `0x1800b0880`
- `0x1800b645a`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800b0943`
- `ntdll!NtCreateFile` at `0x1800b0943`
- `ntdll!NtQueryInformationFile` at `0x1800b0a6b`
- `ntdll!NtQueryInformationFile` at `0x1800b0a6b`
- `ntdll!RtlInitUnicodeString` at `0x1800b08d6`
- `ntdll!RtlInitUnicodeString` at `0x1800b08d6`
- `ntdll!RtlNtStatusToDosError` at `0x1800b094f`
- `ntdll!RtlNtStatusToDosError` at `0x1800b094f`
- `ntdll!NtClose` at `0x1800b0ad2`
- `ntdll!NtClose` at `0x1800b0ad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b09a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b09a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b0a0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b0a0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b09df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b09df`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800b0992`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800b0992`

## pseudocode

```c

```
