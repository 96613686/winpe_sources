# SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)

- ea: `0x1400977a4`
- end: `0x1400978b5`
- name: `?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z`
- size: `273`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD dwIoControlCode@<edx>, struct _OVERLAPPED *@<r8>, void *@<r9>, DWORD nInBufferSize, void *, unsigned int, unsigned int *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140096520`
- `0x140096994`
- `0x140096a24`
- `0x140096ef8`
- `0x1401a5d08`
- `0x1401a5ebc`
- `0x1401a6378`
- `0x1401a8d10`

## callees

- `0x1400977a4`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400977ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400977ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140097859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140097859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009788e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009788e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14009787d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x14009787d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140097847`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140097847`

## pseudocode

```c

```
