# DecryptBlob(uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18008e878`
- end: `0x18008ea34`
- name: `?DecryptBlob@@YAJPEBEKPEAPEAEPEAK@Z`
- size: `444`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180087840`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x18008e878`
- `0x18008f5d0`
- `0x1800c97c2`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18008e9ca`
- `KERNEL32!LocalFree` at `0x18008e9f9`
- `KERNEL32!LocalFree` at `0x18008e9ca`
- `KERNEL32!LocalFree` at `0x18008e9f9`
- `ole32!CoTaskMemAlloc` at `0x18008e980`
- `ole32!CoTaskMemAlloc` at `0x18008e980`
- `CRYPT32!CryptUnprotectData` at `0x18008e954`
- `CRYPT32!CryptUnprotectData` at `0x18008e954`

## pseudocode

```c

```
