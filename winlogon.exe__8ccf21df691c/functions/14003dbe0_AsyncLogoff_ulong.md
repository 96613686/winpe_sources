# AsyncLogoff(ulong)

- ea: `0x14003dbe0`
- end: `0x14003dd08`
- name: `?AsyncLogoff@@YAKK@Z`
- size: `296`
- prototype: `unsigned int __fastcall(PVOID pv)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140003ea0`
- `0x1400045d0`
- `0x14002bcc0`
- `0x14002c380`
- `0x140063660`
- `0x1400656a0`
- `0x1400658d0`
- `0x14006c2e0`
- `0x140071140`
- `0x140082434`
- `0x14008a390`
- `0x14008e0f0`

## callees

- `0x1400057f4`
- `0x14003dbe0`
- `0x140041c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dcb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dcb4`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x14003dcaa`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x14003dcaa`
- `ntdll!TpSimpleTryPost` at `0x14003dc59`
- `ntdll!TpSimpleTryPost` at `0x14003dc59`
- `ntdll!RtlNtStatusToDosError` at `0x14003dc6b`
- `ntdll!RtlNtStatusToDosError` at `0x14003dc6b`

## pseudocode

```c

```
