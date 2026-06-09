# LogServiceStopError(HSTRING__ *,ulong,CToken *,ushort const *)

- ea: `0x18009fd60`
- end: `0x18009ff2f`
- name: `?LogServiceStopError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG@Z`
- size: `463`
- prototype: `void __fastcall(HSTRING string, unsigned int, struct CToken *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180067898`

## callees

- `0x180034540`
- `0x18004105c`
- `0x1800410d4`
- `0x180075e48`
- `0x180081210`
- `0x180081398`
- `0x18009fd60`
- `0x1800a16f4`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18009feab`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18009feab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009fdbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009fdbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18009fdae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18009fdae`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18009feb7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18009feb7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18009fe59`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18009fe59`

## string_xrefs

- `0x18009fe23`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x18009fefb`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x18009fe17`: `LogServiceStopError`
- `0x18009feef`: `LogServiceStopError`
- `0x18009fe32`: `ClassIdentifier:%ws Servicename:%ws`

## pseudocode

```c

```
