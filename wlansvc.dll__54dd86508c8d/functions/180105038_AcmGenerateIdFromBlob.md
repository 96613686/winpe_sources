# AcmGenerateIdFromBlob

- ea: `0x180105038`
- end: `0x180105270`
- name: `AcmGenerateIdFromBlob`
- size: `568`
- prototype: `__int64 __fastcall(ULONG cbInput, PUCHAR pbInput, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180060c30`
- `0x180098e94`
- `0x180104d60`

## callees

- `0x180105038`
- `0x180107318`
- `0x1801b8998`
- `0x1801b89b8`
- `0x1801b89d8`
- `0x1801b8a10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180105220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010523b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180105220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010523b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801050f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180105151`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180105212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010522d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801050f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180105151`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180105212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010522d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180105104`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18010515f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180105104`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18010515f`
- `ntdll!RtlNtStatusToDosError` at `0x1801051a1`
- `ntdll!RtlNtStatusToDosError` at `0x1801051c2`
- `ntdll!RtlNtStatusToDosError` at `0x1801051e4`
- `ntdll!RtlNtStatusToDosError` at `0x1801051a1`
- `ntdll!RtlNtStatusToDosError` at `0x1801051c2`
- `ntdll!RtlNtStatusToDosError` at `0x1801051e4`
- `bcrypt!BCryptCreateHash` at `0x180105199`
- `bcrypt!BCryptCreateHash` at `0x180105199`
- `bcrypt!BCryptHashData` at `0x1801051ba`
- `bcrypt!BCryptHashData` at `0x1801051ba`
- `bcrypt!BCryptFinishHash` at `0x1801051dc`
- `bcrypt!BCryptFinishHash` at `0x1801051dc`

## pseudocode

```c

```
