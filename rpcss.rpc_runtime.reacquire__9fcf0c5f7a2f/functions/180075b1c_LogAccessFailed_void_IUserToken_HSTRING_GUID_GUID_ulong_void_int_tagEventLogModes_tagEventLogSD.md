# LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)

- ea: `0x180075b1c`
- end: `0x180076558`
- name: `?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z`
- size: `2620`
- prototype: ``
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800562a0`
- `0x180061fc0`
- `0x18009baa0`

## callees

- `0x180025088`
- `0x18002ec74`
- `0x180034260`
- `0x180039a7c`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18005ad10`
- `0x1800710a4`
- `0x180074190`
- `0x180074f88`
- `0x180075b1c`
- `0x18007a538`
- `0x18007a568`
- `0x18007a59c`
- `0x18007a5d0`
- `0x18007a604`
- `0x18007a638`
- `0x1800855d8`
- `0x180089e5c`
- `0x1800a45ac`
- `0x1800a6fec`
- `0x1800a7a48`
- `0x1800a7a7c`
- `0x1800b0c7c`
- `0x1800b7ac0`
- `0x1800b8428`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180076447`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180076447`
- `ntdll!EtwEventRegister` at `0x1800763f5`
- `ntdll!EtwEventRegister` at `0x1800763f5`
- `ntdll!EtwEventUnregister` at `0x180076459`
- `ntdll!EtwEventUnregister` at `0x180076459`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180075d54`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180075d54`
- `RPCRT4!RpcStringFreeW` at `0x1800764f1`
- `RPCRT4!RpcStringFreeW` at `0x1800764f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800762dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800764d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007650f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800762dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800764d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007650f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180075ece`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180075fed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800760b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180075ece`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180075fed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800760b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180076345`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180076345`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18007612d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800761ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180076379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18007612d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800761ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180076379`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180075de9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180075de9`

## string_xrefs

- `0x1800764a9`: `onecore\com\combase\catalog\services.cxx`
- `0x18007649d`: `LogAccessFailed`

## pseudocode

```c

```
