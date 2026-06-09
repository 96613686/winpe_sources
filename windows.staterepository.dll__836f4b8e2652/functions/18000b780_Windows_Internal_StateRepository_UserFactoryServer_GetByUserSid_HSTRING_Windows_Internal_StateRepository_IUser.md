# Windows::Internal::StateRepository::UserFactoryServer::GetByUserSid(HSTRING__ *,Windows::Internal::StateRepository::IUser * *)

- ea: `0x18000b780`
- end: `0x18000bb63`
- name: `?GetByUserSid@UserFactoryServer@StateRepository@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIUser@234@@Z`
- size: `995`
- prototype: `int(Windows::Internal::StateRepository::UserFactoryServer *__hidden this, HSTRING, struct Windows::Internal::StateRepository::IUser **)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006fec`
- `0x18000b380`
- `0x18000b3a0`
- `0x18000b71c`
- `0x18000b780`
- `0x18000c73c`
- `0x18000cc30`
- `0x18000d0a4`
- `0x18000d170`
- `0x18000e694`
- `0x18000e8dc`
- `0x180016030`
- `0x180017098`
- `0x1800171c0`
- `0x180017a58`
- `0x180018574`
- `0x180018628`
- `0x18001a9e0`
- `0x18003518c`
- `0x18018f650`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b8a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b973`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b8a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b973`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b846`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b880`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b8b4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b8b4`

## string_xrefs

- `0x18000b7e4`: `UserStatics::GetByUserSid`
- `0x18000b9e7`: `UserStatics::GetByUserSid`
- `0x18000b8c5`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`
- `0x18000b91f`: `onecore\base\appmodel\StateRepository\WinRT\common\inc\WinRT-DAL.hpp`

## pseudocode

```c

```
