# LogRegisterTimeout(HSTRING__ *,ulong,CToken *)

- ea: `0x180080470`
- end: `0x18008064e`
- name: `?LogRegisterTimeout@@YAXPEAUHSTRING__@@KPEAVCToken@@@Z`
- size: `478`
- prototype: `void __fastcall(HSTRING string, unsigned int, struct CToken *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c680`

## callees

- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18007a604`
- `0x180080470`
- `0x1800855d8`
- `0x1800857e0`
- `0x1800858f0`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800805b1`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800805b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800805f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800805f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800804d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800804d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800804bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800804bd`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800805c3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800805c3`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18008055a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18008055a`

## string_xrefs

- `0x18008052b`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x180080613`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x180080535`: `ClassIdentifier:%ws`

## pseudocode

```c

```
