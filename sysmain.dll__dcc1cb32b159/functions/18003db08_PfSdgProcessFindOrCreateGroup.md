# PfSdgProcessFindOrCreateGroup

- ea: `0x18003db08`
- end: `0x18003dd06`
- name: `PfSdgProcessFindOrCreateGroup`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003d140`

## callees

- `0x18003db08`
- `0x18003dd0c`
- `0x18003ddc0`
- `0x18003de80`

## import_xrefs

- `ntdll!RtlRbInsertNodeEx` at `0x18003dc51`
- `ntdll!RtlRbInsertNodeEx` at `0x18003dc51`
- `ntdll!NtSetInformationProcess` at `0x18003db68`
- `ntdll!NtSetInformationProcess` at `0x18003db68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dbed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dbed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003db9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003db9f`

## pseudocode

```c

```
