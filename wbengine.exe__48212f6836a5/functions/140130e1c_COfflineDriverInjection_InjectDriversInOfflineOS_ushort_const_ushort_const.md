# COfflineDriverInjection::InjectDriversInOfflineOS(ushort const *,ushort const *)

- ea: `0x140130e1c`
- end: `0x14013114c`
- name: `?InjectDriversInOfflineOS@COfflineDriverInjection@@SAJPEBG0@Z`
- size: `816`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x14007d630`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140092184`
- `0x140130840`
- `0x140130914`
- `0x1401309cc`
- `0x140130b34`
- `0x140130e1c`
- `0x140131154`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14013110e`
- `KERNEL32!FreeLibrary` at `0x14013110e`
- `KERNEL32!GetProcAddress` at `0x14013103e`
- `KERNEL32!GetProcAddress` at `0x14013103e`
- `KERNEL32!GetLastError` at `0x140130fb5`
- `KERNEL32!GetLastError` at `0x14013104c`
- `KERNEL32!GetLastError` at `0x140130fb5`
- `KERNEL32!GetLastError` at `0x14013104c`
- `ole32!CoTaskMemAlloc` at `0x140130f2d`
- `ole32!CoTaskMemAlloc` at `0x140130f2d`
- `ole32!CoTaskMemFree` at `0x1401310db`
- `ole32!CoTaskMemFree` at `0x1401310f5`
- `ole32!CoTaskMemFree` at `0x1401310db`
- `ole32!CoTaskMemFree` at `0x1401310f5`

## string_xrefs

- `0x140130fa1`: `drvstore.dll`

## pseudocode

```c

```
