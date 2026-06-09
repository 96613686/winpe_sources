# LogServerStartError(long,HSTRING__ *,ulong,CToken *,ushort const *)

- ea: `0x180086af8`
- end: `0x180086d3f`
- name: `?LogServerStartError@@YAXJPEAUHSTRING__@@KPEAVCToken@@PEBG@Z`
- size: `583`
- prototype: `void(int, HSTRING, unsigned int, struct CToken *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180104e40`

## callees

- `0x18001037c`
- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18007a604`
- `0x1800855d8`
- `0x1800857e0`
- `0x180086af8`
- `0x1800a543c`
- `0x1800b7ac0`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180086c92`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180086c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086cd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086bb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180086bb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180086b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180086b9c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180086ca4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180086ca4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180086c42`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180086c42`

## string_xrefs

- `0x180086c21`: `ClassIdentifier:%ws CommandLine:%ws Error:%!HRESULT!`
- `0x180086c0a`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x180086cf4`: `onecore\com\combase\rpcss\olescm\events.cxx`

## pseudocode

```c

```
