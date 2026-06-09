# Windows::Internal::Security::CPropertiesSerializer::BufferToBytes(Windows::Storage::Streams::IBuffer *,uchar * *,ulong *)

- ea: `0x180046a94`
- end: `0x180046c6e`
- name: `?BufferToBytes@CPropertiesSerializer@Security@Internal@Windows@@SAJPEAUIBuffer@Streams@Storage@4@PEAPEAEPEAK@Z`
- size: `474`
- prototype: `__int64 __fastcall(struct Windows::Storage::Streams::IBuffer *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800466bc`
- `0x180046764`
- `0x180055574`

## callees

- `0x18000f8e8`
- `0x180046a94`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046bde`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046c54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046b03`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046b2c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046b2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046b6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046c46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046c46`

## string_xrefs

- `0x180046af9`: `Windows.Storage.Streams.DataReader`

## pseudocode

```c

```
