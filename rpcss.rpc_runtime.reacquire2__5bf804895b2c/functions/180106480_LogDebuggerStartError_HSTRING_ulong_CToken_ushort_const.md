# LogDebuggerStartError(HSTRING__ *,ulong,CToken *,ushort const *)

- ea: `0x180106480`
- end: `0x1801066c4`
- name: `?LogDebuggerStartError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG@Z`
- size: `580`
- prototype: `void __fastcall(HSTRING string, unsigned int, struct CToken *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180103c08`

## callees

- `0x18001037c`
- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18007a604`
- `0x1800855d8`
- `0x1800857e0`
- `0x1800b7ac0`
- `0x1800d2e14`
- `0x180106480`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18010661b`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18010661b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801064dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010665a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801064dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010665a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010653d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010653d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180106528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180106528`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18010662d`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18010662d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1801065d1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1801065d1`

## string_xrefs

- `0x180106599`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x18010667d`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1801065b0`: `ClassIdentifier:%ws CommandLine:%ws Error:%!WINERROR!`

## pseudocode

```c

```
