# CanDeletePath(ushort const *)

- ea: `0x180100b24`
- end: `0x180100df3`
- name: `?CanDeletePath@@YAJPEBG@Z`
- size: `719`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800eeeb4`
- `0x180116130`
- `0x180372a80`
- `0x18038ef78`

## callees

- `0x18004e06c`
- `0x180100b24`
- `0x180100dfc`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180100c77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180100cf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1806674b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180100c77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180100cf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1806674b3`
- `ntdll!NtQueryInformationFile` at `0x180100bc3`
- `ntdll!NtQueryInformationFile` at `0x180100ccc`
- `ntdll!NtQueryInformationFile` at `0x180100bc3`
- `ntdll!NtQueryInformationFile` at `0x180100ccc`
- `ntdll!NtSetInformationFile` at `0x180100c1a`
- `ntdll!NtSetInformationFile` at `0x180100c56`
- `ntdll!NtSetInformationFile` at `0x180100d3d`
- `ntdll!NtSetInformationFile` at `0x180100de2`
- `ntdll!NtSetInformationFile` at `0x180100c1a`
- `ntdll!NtSetInformationFile` at `0x180100c56`
- `ntdll!NtSetInformationFile` at `0x180100d3d`
- `ntdll!NtSetInformationFile` at `0x180100de2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180100b73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180100d8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1806674e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180667519`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180100b73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180100d8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1806674e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180667519`

## pseudocode

```c

```
