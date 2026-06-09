# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty::SetInlineBytesValue(uchar *,ulong)

- ea: `0x18011358c`
- end: `0x180113809`
- name: `?SetInlineBytesValue@JsonObjectProperty@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAEK@Z`
- size: `637`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker::JsonObjectProperty *__hidden this, BYTE *pbBinary, DWORD cbBinary)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010c9e8`
- `0x18010df64`
- `0x18010f314`

## callees

- `0x180006290`
- `0x18000bd40`
- `0x18001a510`
- `0x18002d940`
- `0x180048694`
- `0x18004fdbc`
- `0x1800506f8`
- `0x180063638`
- `0x18008e690`
- `0x18011358c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801136a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801136a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801135d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801135d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113766`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113766`
- `CRYPT32!CryptProtectData` at `0x180113696`
- `CRYPT32!CryptProtectData` at `0x180113696`
- `CRYPT32!CryptBinaryToStringW` at `0x1801136fe`
- `CRYPT32!CryptBinaryToStringW` at `0x1801137b2`
- `CRYPT32!CryptBinaryToStringW` at `0x1801136fe`
- `CRYPT32!CryptBinaryToStringW` at `0x1801137b2`

## string_xrefs

- `0x180113745`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`

## pseudocode

```c

```
