# WinHelpW

- ea: `0x1800673d0`
- end: `0x1800676a3`
- name: `WinHelpW`
- size: `723`
- prototype: `BOOL __stdcall(HWND hWndMain, LPCWSTR lpszHelp, UINT uCommand, ULONG_PTR dwData)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068724`

## callees

- `0x180043b70`
- `0x1800673d0`
- `0x180073c08`
- `0x18007f9e0`

## import_xrefs

- `ntdll!strcpy_s` at `0x180067530`
- `ntdll!strcpy_s` at `0x180067530`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180067459`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800675be`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180067459`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800675be`
- `ntdll!RtlFreeHeap` at `0x18006747e`
- `ntdll!RtlFreeHeap` at `0x180067636`
- `ntdll!RtlFreeHeap` at `0x18006764d`
- `ntdll!RtlFreeHeap` at `0x18006766b`
- `ntdll!RtlFreeHeap` at `0x180067682`
- `ntdll!RtlFreeHeap` at `0x18006747e`
- `ntdll!RtlFreeHeap` at `0x180067636`
- `ntdll!RtlFreeHeap` at `0x18006764d`
- `ntdll!RtlFreeHeap` at `0x18006766b`
- `ntdll!RtlFreeHeap` at `0x180067682`
- `ntdll!RtlAllocateHeap` at `0x180067435`
- `ntdll!RtlAllocateHeap` at `0x180067500`
- `ntdll!RtlAllocateHeap` at `0x180067586`
- `ntdll!RtlAllocateHeap` at `0x180067435`
- `ntdll!RtlAllocateHeap` at `0x180067500`
- `ntdll!RtlAllocateHeap` at `0x180067586`

## pseudocode

```c

```
