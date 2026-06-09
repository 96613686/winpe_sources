# BlbIsCdromWriteCapableFromModeSense

- ea: `0x1401162e0`
- end: `0x1401166b4`
- name: `BlbIsCdromWriteCapableFromModeSense`
- size: `980`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140115da0`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x1401162e0`
- `0x140117628`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401163f2`
- `KERNEL32!GetLastError` at `0x140116627`
- `KERNEL32!GetLastError` at `0x1401163f2`
- `KERNEL32!GetLastError` at `0x140116627`
- `KERNEL32!DeviceIoControl` at `0x1401163e8`
- `KERNEL32!DeviceIoControl` at `0x140116542`
- `KERNEL32!DeviceIoControl` at `0x1401163e8`
- `KERNEL32!DeviceIoControl` at `0x140116542`
- `ole32!CoTaskMemAlloc` at `0x14011648a`
- `ole32!CoTaskMemAlloc` at `0x14011648a`
- `ole32!CoTaskMemFree` at `0x140116481`
- `ole32!CoTaskMemFree` at `0x140116597`
- `ole32!CoTaskMemFree` at `0x140116481`
- `ole32!CoTaskMemFree` at `0x140116597`

## string_xrefs

- `0x140116367`: `pbIsWriteCapable`

## pseudocode

```c

```
