# AllocateIStreamFromPbCb(unsigned __int64,uchar const *,IStream * *)

- ea: `0x18005619c`
- end: `0x1800562d1`
- name: `?AllocateIStreamFromPbCb@@YAJ_KPEBEPEAPEAUIStream@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(size_t Size, const unsigned __int8 *Src, LPSTREAM *ppstm)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018358`
- `0x18002170c`

## callees

- `0x18005619c`
- `0x180081a96`
- `0x180084259`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180056234`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180056234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005625c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005628c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056252`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005625c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005628c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800561d0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800561d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800562c6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800562c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800561e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800561e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180056248`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180056248`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180056277`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180056277`

## pseudocode

```c

```
