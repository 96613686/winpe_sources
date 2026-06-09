# LogServiceStartError(HSTRING__ *,ulong,CToken *,ushort const *,ushort const *,ulong)

- ea: `0x18010698c`
- end: `0x180106c05`
- name: `?LogServiceStartError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG2K@Z`
- size: `633`
- prototype: `void __usercall(HSTRING string@<rcx>, unsigned int@<edx>, struct CToken *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073580`

## callees

- `0x18001037c`
- `0x18001c624`
- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18007a604`
- `0x1800855d8`
- `0x1800857e0`
- `0x1800b7ac0`
- `0x18010698c`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180106b58`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180106b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106b97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180106a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180106a45`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180106b6a`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180106b6a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180106afe`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180106afe`

## string_xrefs

- `0x180106ab6`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x180106bba`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x180106aab`: `LogServiceStartError`
- `0x180106bae`: `LogServiceStartError`
- `0x180106ad5`: `ClassIdentifier:%ws Servicename:%ws Args:%ws Error:%!WINERROR!`

## pseudocode

```c

```
