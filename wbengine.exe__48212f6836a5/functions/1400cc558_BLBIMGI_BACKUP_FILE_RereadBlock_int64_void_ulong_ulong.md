# BLBIMGI_BACKUP_FILE::RereadBlock(__int64,void * *,ulong *,ulong *)

- ea: `0x1400cc558`
- end: `0x1400cc7df`
- name: `?RereadBlock@BLBIMGI_BACKUP_FILE@@QEAA?AW4_BLBIMG_RESULT_CODE@@_JPEAPEAXPEAK2@Z`
- size: `647`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400b5e40`
- `0x1400b93e0`

## callees

- `0x140005070`
- `0x14000bb24`
- `0x14003c434`
- `0x1400c3d08`
- `0x1400cc558`
- `0x1400ce418`
- `0x140134cde`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1400cc71d`
- `KERNEL32!GetOverlappedResult` at `0x1400cc71d`
- `KERNEL32!LocalAlloc` at `0x1400cc6a1`
- `KERNEL32!LocalAlloc` at `0x1400cc6a1`
- `KERNEL32!LocalFree` at `0x1400cc7bf`
- `KERNEL32!LocalFree` at `0x1400cc7bf`
- `KERNEL32!CloseHandle` at `0x1400cc7b1`
- `KERNEL32!CloseHandle` at `0x1400cc7b1`
- `KERNEL32!CreateEventW` at `0x1400cc6d3`
- `KERNEL32!CreateEventW` at `0x1400cc6d3`
- `KERNEL32!GetLastError` at `0x1400cc6af`
- `KERNEL32!GetLastError` at `0x1400cc727`
- `KERNEL32!GetLastError` at `0x1400cc6af`
- `KERNEL32!GetLastError` at `0x1400cc727`
- `ntdll!RtlAreBitsClear` at `0x1400cc60f`
- `ntdll!RtlAreBitsClear` at `0x1400cc60f`

## pseudocode

```c

```
