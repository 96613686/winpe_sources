# SyncDeviceIoControl(void *,ulong,_OVERLAPPED *,void *,ulong,void *,ulong,ulong *)

- ea: `0x140087970`
- end: `0x140087a81`
- name: `?SyncDeviceIoControl@@YAHPEAXKPEAU_OVERLAPPED@@0K0KPEAK@Z`
- size: `273`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, DWORD dwIoControlCode@<edx>, struct _OVERLAPPED *@<r8>, void *@<r9>, DWORD nInBufferSize, void *, unsigned int, unsigned int *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140085910`
- `0x140085d84`
- `0x140085e14`
- `0x140086f5c`
- `0x1401b6c28`
- `0x1401b6ddc`
- `0x1401b7298`
- `0x1401b9c30`

## callees

- `0x140087970`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400879bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400879bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140087a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087a5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140087a5a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140087a13`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140087a13`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140087a49`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140087a49`

## pseudocode

```c

```
