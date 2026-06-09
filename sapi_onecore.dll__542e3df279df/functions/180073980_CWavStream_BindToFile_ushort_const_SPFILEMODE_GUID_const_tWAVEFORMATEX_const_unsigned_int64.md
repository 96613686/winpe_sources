# CWavStream::BindToFile(ushort const *,SPFILEMODE,_GUID const *,tWAVEFORMATEX const *,unsigned __int64)

- ea: `0x180073980`
- end: `0x180073f12`
- name: `?BindToFile@CWavStream@@UEAAJPEBGW4SPFILEMODE@@PEBU_GUID@@PEBUtWAVEFORMATEX@@_K@Z`
- size: `1426`
- prototype: `__int64 __fastcall(CWavStream *__hidden this, const unsigned __int16 *, enum SPFILEMODE, const struct _GUID *, const struct tWAVEFORMATEX *, unsigned __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x18000bec4`
- `0x18000e518`
- `0x180013ec0`
- `0x180016870`
- `0x18001ae00`
- `0x180021970`
- `0x18002d404`
- `0x180073980`
- `0x180073f18`
- `0x1800741c8`
- `0x18007642c`
- `0x180079e30`
- `0x18007d31c`
- `0x18007d7a5`
- `0x1800a3c38`
- `0x1800fc48c`
- `0x18027b320`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073ae8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180073ae8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800739ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800739ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073edd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073edd`
- `OLEAUT32!__imp_SysFreeString` at `0x180073cb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180073cb7`
- `urlmon!URLOpenBlockingStreamW` at `0x180073d8b`
- `urlmon!URLOpenBlockingStreamW` at `0x180073d8b`
- `urlmon!CoInternetParseUrl` at `0x180073be0`
- `urlmon!CoInternetParseUrl` at `0x180073c5f`
- `urlmon!CoInternetParseUrl` at `0x180073be0`
- `urlmon!CoInternetParseUrl` at `0x180073c5f`

## string_xrefs

- `0x180073d9e`: `URLOpenBlockingStreamW failed, hr=0x%X`
- `0x180073e44`: `Cannot write to file %S, hr=0x%X`

## pseudocode

```c

```
