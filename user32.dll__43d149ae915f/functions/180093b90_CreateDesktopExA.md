# CreateDesktopExA

- ea: `0x180093b90`
- end: `0x180093cc4`
- name: `CreateDesktopExA`
- size: `308`
- prototype: `HDESK __stdcall(LPCSTR lpszDesktop, LPCSTR lpszDevice, DEVMODEA *pDevmode, DWORD dwFlags, ACCESS_MASK dwDesiredAccess, LPSECURITY_ATTRIBUTES lpsa, ULONG ulHeapSize, PVOID pvoid)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180093b50`

## callees

- `0x180020e80`
- `0x18005b8cc`
- `0x180093b90`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180093bc7`
- `ntdll!RtlSetLastWin32Error` at `0x180093bc7`
- `ntdll!RtlInitAnsiString` at `0x180093bdb`
- `ntdll!RtlInitAnsiString` at `0x180093c0d`
- `ntdll!RtlInitAnsiString` at `0x180093bdb`
- `ntdll!RtlInitAnsiString` at `0x180093c0d`
- `ntdll!RtlFreeUnicodeString` at `0x180093c33`
- `ntdll!RtlFreeUnicodeString` at `0x180093c82`
- `ntdll!RtlFreeUnicodeString` at `0x180093c91`
- `ntdll!RtlFreeUnicodeString` at `0x180093c33`
- `ntdll!RtlFreeUnicodeString` at `0x180093c82`
- `ntdll!RtlFreeUnicodeString` at `0x180093c91`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180093bec`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180093c1e`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180093bec`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180093c1e`
- `ntdll!RtlFreeHeap` at `0x180093cae`
- `ntdll!RtlFreeHeap` at `0x180093cae`
- `GDI32!GdiConvertToDevmodeW` at `0x180093c49`
- `GDI32!GdiConvertToDevmodeW` at `0x180093c49`

## pseudocode

```c

```
