# VmPerfCreateInstance2

- ea: `0x140065e3c`
- end: `0x140065f99`
- name: `VmPerfCreateInstance2`
- size: `349`
- prototype: `__int64 __usercall@<rax>(HANDLE ProviderHandle@<rcx>, LPCGUID CounterSetGuid@<rdx>, wchar_t *Source@<r8>, ULONG Id, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140065dd8`

## callees

- `0x140065e3c`
- `0x14013400c`
- `0x14024db28`
- `0x14024dbb4`
- `0x14024dc5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140065e59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140065ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140065e59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140065ec2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140065e71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140065ed9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140065e71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140065ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f57`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x140065f43`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x140065f43`

## pseudocode

```c

```
