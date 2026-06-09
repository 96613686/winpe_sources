# LogDebuggerStartError(HSTRING__ *,ulong,CToken *,ushort const *)

- ea: `0x1800fdcd8`
- end: `0x1800fdef1`
- name: `?LogDebuggerStartError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG@Z`
- size: `537`
- prototype: `void __fastcall(HSTRING string, unsigned int, struct CToken *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800fb694`

## callees

- `0x18000bbe8`
- `0x180034540`
- `0x18004105c`
- `0x1800410d4`
- `0x180075e48`
- `0x180081210`
- `0x180081398`
- `0x1800b27e0`
- `0x1800ccbd4`
- `0x1800fdcd8`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800fde5b`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800fde5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fdd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fde8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fdd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fde8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fdd89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fdd89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800fdd7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800fdd7a`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800fde67`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800fde67`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800fde17`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800fde17`

## string_xrefs

- `0x1800fdddf`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1800fdeab`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1800fddf6`: `ClassIdentifier:%ws CommandLine:%ws Error:%!WINERROR!`

## pseudocode

```c

```
