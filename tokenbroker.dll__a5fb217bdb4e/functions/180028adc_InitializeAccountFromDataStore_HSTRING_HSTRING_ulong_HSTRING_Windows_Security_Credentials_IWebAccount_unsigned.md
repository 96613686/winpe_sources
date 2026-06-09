# InitializeAccountFromDataStore(HSTRING__ *,HSTRING__ *,ulong,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *,unsigned __int64)

- ea: `0x180028adc`
- end: `0x180028e3d`
- name: `?InitializeAccountFromDataStore@@YAJPEAUHSTRING__@@0K0PEAPEAUIWebAccount@Credentials@Security@Windows@@_K@Z`
- size: `865`
- prototype: `__int64 __fastcall(HSTRING, HSTRING, unsigned int, HSTRING, struct Windows::Security::Credentials::IWebAccount **, unsigned __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073260`
- `0x180074e0c`
- `0x1800e31c0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800286a4`
- `0x180028adc`
- `0x180029478`
- `0x1800295d0`
- `0x18002a3e0`
- `0x18002a790`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028c06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028c06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c6a`

## string_xrefs

- `0x180028cc2`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180028d22`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180028d49`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180028d7e`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`
- `0x180028e10`: `onecore\ds\security\tokenbroker\pluginmgr\lib\plugreg.cpp`

## pseudocode

```c

```
