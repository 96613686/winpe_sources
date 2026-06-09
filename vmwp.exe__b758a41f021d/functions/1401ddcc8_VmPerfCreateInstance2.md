# VmPerfCreateInstance2

- ea: `0x1401ddcc8`
- end: `0x1401dde79`
- name: `VmPerfCreateInstance2`
- size: `433`
- prototype: `__int64 __usercall@<rax>(HANDLE ProviderHandle@<rcx>, LPCGUID CounterSetGuid@<rdx>, wchar_t *Source@<r8>, ULONG Id, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400e3ae0`
- `0x140273540`

## callees

- `0x1400ea318`
- `0x14011f6cc`
- `0x1401ddc3c`
- `0x1401ddcc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401ddce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401ddd4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401ddce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401ddd4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401ddcfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401ddd65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401ddcfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401ddd65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401dde37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401dde37`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1401dde23`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1401dde23`

## pseudocode

```c

```
