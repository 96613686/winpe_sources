# LogServiceStopError(HSTRING__ *,ulong,CToken *,ushort const *)

- ea: `0x1800a5144`
- end: `0x1800a5338`
- name: `?LogServiceStopError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG@Z`
- size: `500`
- prototype: `void __fastcall(HSTRING string, unsigned int, struct CToken *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006c680`

## callees

- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18007a604`
- `0x1800855d8`
- `0x1800857e0`
- `0x1800a5144`
- `0x1800a6c48`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800a52a1`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800a52a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a52e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a52e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a51a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a51a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800a5192`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800a5192`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800a52b3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800a52b3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800a5249`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800a5249`

## string_xrefs

- `0x1800a5213`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1800a5303`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1800a5222`: `ClassIdentifier:%ws Servicename:%ws`
- `0x1800a5207`: `LogServiceStopError`
- `0x1800a52f7`: `LogServiceStopError`

## pseudocode

```c

```
