# Windows::Internal::Security::Authentication::TokenBroker::GetByteArrayFromBuffer(Windows::Storage::Streams::IBuffer *,uint *,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::LocalAllocDeleter> &)

- ea: `0x1800467f0`
- end: `0x180046a8e`
- name: `?GetByteArrayFromBuffer@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIBuffer@Streams@Storage@5@PEAIAEAV?$unique_ptr@PEAXULocalAllocDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z`
- size: `670`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180066608`
- `0x180106228`
- `0x18010c9e8`

## callees

- `0x18000bd40`
- `0x18000f8e8`
- `0x18001a510`
- `0x1800467f0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046a65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046840`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046869`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180046869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800468ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800468ce`

## string_xrefs

- `0x180046974`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800469f6`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180046a77`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180046839`: `Windows.Storage.Streams.DataReader`

## pseudocode

```c

```
