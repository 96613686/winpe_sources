# NdisQueryPhysicalMediumDevice(ushort const *,_NDIS_PHYSICAL_MEDIUM *)

- ea: `0x180058d60`
- end: `0x180058f77`
- name: `?NdisQueryPhysicalMediumDevice@@YAJPEBGPEAW4_NDIS_PHYSICAL_MEDIUM@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum _NDIS_PHYSICAL_MEDIUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180058a08`

## callees

- `0x180058d60`
- `0x180058f80`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058f4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058e82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058eef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058e82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058eef`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180058ed0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180058ed0`
- `ntdll!NtOpenFile` at `0x180058e5c`
- `ntdll!NtOpenFile` at `0x180058e5c`

## pseudocode

```c

```
