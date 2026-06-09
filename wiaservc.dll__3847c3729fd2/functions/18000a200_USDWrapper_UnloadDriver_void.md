# USDWrapper::UnloadDriver(void)

- ea: `0x18000a200`
- end: `0x18000a530`
- name: `?UnloadDriver@USDWrapper@@UEAAJXZ`
- size: `816`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18004bfa8`

## callees

- `0x18000a200`
- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x180022d40`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a2fd`
- `KERNEL32!LeaveCriticalSection` at `0x18000a4b3`
- `KERNEL32!LeaveCriticalSection` at `0x18000a2fd`
- `KERNEL32!LeaveCriticalSection` at `0x18000a4b3`
- `KERNEL32!FreeLibrary` at `0x18000a390`
- `KERNEL32!FreeLibrary` at `0x18000a390`

## string_xrefs

- `0x18000a4d3`: `The WIA service is preparing to unload the driver for (%ws)`
- `0x18000a504`: `The WIA service is preparing to unload the driver for (%ws)`

## pseudocode

```c

```
