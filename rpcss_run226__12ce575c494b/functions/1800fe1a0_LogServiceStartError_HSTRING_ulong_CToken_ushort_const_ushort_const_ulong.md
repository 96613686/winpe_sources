# LogServiceStartError(HSTRING__ *,ulong,CToken *,ushort const *,ushort const *,ulong)

- ea: `0x1800fe1a0`
- end: `0x1800fe3f4`
- name: `?LogServiceStartError@@YAXPEAUHSTRING__@@KPEAVCToken@@PEBG2K@Z`
- size: `596`
- prototype: `void __usercall(HSTRING string@<rcx>, unsigned int@<edx>, struct CToken *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ed30`

## callees

- `0x18000bbe8`
- `0x180018344`
- `0x180034540`
- `0x18004105c`
- `0x1800410d4`
- `0x180075e48`
- `0x180081210`
- `0x180081398`
- `0x1800b27e0`
- `0x1800fe1a0`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800fe35a`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800fe35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe38d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe38d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fe268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fe268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800fe259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800fe259`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800fe366`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800fe366`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800fe306`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800fe306`

## string_xrefs

- `0x1800fe2be`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1800fe3aa`: `onecore\com\combase\rpcss\olescm\events.cxx`
- `0x1800fe2b3`: `LogServiceStartError`
- `0x1800fe39e`: `LogServiceStartError`
- `0x1800fe2dd`: `ClassIdentifier:%ws Servicename:%ws Args:%ws Error:%!WINERROR!`

## pseudocode

```c

```
