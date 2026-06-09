# DecryptBlob(uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800927e8`
- end: `0x1800929bd`
- name: `?DecryptBlob@@YAJPEBEKPEAPEAEPEAK@Z`
- size: `469`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18008b238`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x1800927e8`
- `0x1800935fc`
- `0x1800cf552`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180092946`
- `KERNEL32!LocalFree` at `0x18009297b`
- `KERNEL32!LocalFree` at `0x180092946`
- `KERNEL32!LocalFree` at `0x18009297b`
- `ole32!CoTaskMemAlloc` at `0x1800928f6`
- `ole32!CoTaskMemAlloc` at `0x1800928f6`
- `CRYPT32!CryptUnprotectData` at `0x1800928c4`
- `CRYPT32!CryptUnprotectData` at `0x1800928c4`

## pseudocode

```c

```
