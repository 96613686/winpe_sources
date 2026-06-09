# Windows::Internal::Security::Authentication::TokenBroker::CSUAAccountManager::ReadAccountFromDataStore(HSTRING__ *,HSTRING__ *,ulong,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *,unsigned __int64)

- ea: `0x180028f20`
- end: `0x180029286`
- name: `?ReadAccountFromDataStore@CSUAAccountManager@TokenBroker@Authentication@Security@Internal@Windows@@UEAAJPEAUHSTRING__@@0K0PEAPEAUIWebAccount@Credentials@46@_K@Z`
- size: `870`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker::CSUAAccountManager *__hidden this, HSTRING, HSTRING, unsigned int, HSTRING, struct Windows::Security::Credentials::IWebAccount **, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800286a4`
- `0x180028f20`
- `0x180029478`
- `0x1800295d0`
- `0x18002a3e0`
- `0x18002a790`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002904f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002904f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029089`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029097`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800290a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800290b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029089`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029097`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800290a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800290b3`

## string_xrefs

- `0x18002910b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18002916b`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180029192`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x1800291c7`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180029259`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`

## pseudocode

```c

```
