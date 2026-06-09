# EcbDiskAwaitCompletion

- ea: `0x18004f55c`
- end: `0x18004f696`
- name: `EcbDiskAwaitCompletion`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004f1e8`
- `0x18004f3f8`

## callees

- `0x180020ee8`
- `0x18004f55c`
- `0x18004f69c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f582`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004f582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f5c7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18004f5bd`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18004f5bd`

## string_xrefs

- `0x18004f630`: `%s:  FATAL ERROR:  Fewer bytes read (%u) than requested by ReadFile(%s,,%u,,) at addr 0x%08x%08x\n`
- `0x18004f5e6`: `FATAL ERROR:  Could not ReadFile(%s,0x%08x%08x,0x%x) completed with error %d\n`

## pseudocode

```c

```
