# SetPropA

- ea: `0x1800551c0`
- end: `0x18005532c`
- name: `SetPropA`
- size: `364`
- prototype: `BOOL __stdcall(HWND hWnd, LPCSTR lpString, HANDLE hData)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000d210`
- `0x1800104a0`
- `0x1800107b0`
- `0x1800551c0`
- `0x18006df24`

## import_xrefs

- `win32u!NtUserSetProp` at `0x18005528c`
- `win32u!NtUserSetProp` at `0x18005528c`
- `win32u!NtUserSetProp2` at `0x180055253`
- `win32u!NtUserSetProp2` at `0x180055253`
- `ntdll!RtlSetLastWin32Error` at `0x1800552fc`
- `ntdll!RtlSetLastWin32Error` at `0x1800552fc`
- `ntdll!RtlFreeUnicodeString` at `0x18005526b`
- `ntdll!RtlFreeUnicodeString` at `0x18005526b`
- `ntdll!RtlNtStatusToDosError` at `0x1800552f4`
- `ntdll!RtlNtStatusToDosError` at `0x1800552f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055307`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomA` at `0x1800552d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomA` at `0x1800552d9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800552a0`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800552a0`

## pseudocode

```c

```
