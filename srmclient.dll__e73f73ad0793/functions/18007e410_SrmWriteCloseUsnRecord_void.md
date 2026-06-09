# SrmWriteCloseUsnRecord(void *)

- ea: `0x18007e410`
- end: `0x18007e5a3`
- name: `?SrmWriteCloseUsnRecord@@YA_JPEAX@Z`
- size: `403`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180048030`
- `0x18005b2a8`
- `0x18008ae3c`

## callees

- `0x18006febc`
- `0x1800700b8`
- `0x180073f54`
- `0x18007e410`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007e4f9`
- `KERNEL32!GetLastError` at `0x18007e542`
- `KERNEL32!GetLastError` at `0x18007e4f9`
- `KERNEL32!GetLastError` at `0x18007e542`
- `KERNEL32!GetOverlappedResult` at `0x18007e538`
- `KERNEL32!GetOverlappedResult` at `0x18007e538`
- `KERNEL32!DeviceIoControl` at `0x18007e4ef`
- `KERNEL32!DeviceIoControl` at `0x18007e4ef`

## string_xrefs

- `0x18007e443`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007e45a`: `SRMPATHC`
- `0x18007e516`: `FSCTL_WRITE_USN_CLOSE_RECORD returned error %ld`
- `0x18007e44f`: `SrmWriteCloseUsnRecord`

## pseudocode

```c

```
