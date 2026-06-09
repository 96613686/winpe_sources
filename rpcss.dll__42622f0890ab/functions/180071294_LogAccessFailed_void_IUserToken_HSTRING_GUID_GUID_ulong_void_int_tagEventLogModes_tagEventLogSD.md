# LogAccessFailed(void *,IUserToken *,HSTRING__ *,_GUID *,_GUID *,ulong,void *,int,tagEventLogModes,tagEventLogSD)

- ea: `0x180071294`
- end: `0x180071c57`
- name: `?LogAccessFailed@@YAXPEAXPEAUIUserToken@@PEAUHSTRING__@@PEAU_GUID@@3K0HW4tagEventLogModes@@W4tagEventLogSD@@@Z`
- size: `2499`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a4d0`
- `0x18005d8e0`
- `0x180096570`

## callees

- `0x1800249b4`
- `0x18002f058`
- `0x180034540`
- `0x18004105c`
- `0x1800410d4`
- `0x18004778c`
- `0x180054b7c`
- `0x18006cb10`
- `0x18006fa24`
- `0x180070784`
- `0x180071294`
- `0x180075d7c`
- `0x180075dac`
- `0x180075de0`
- `0x180075e14`
- `0x180075e48`
- `0x180075e7c`
- `0x180081210`
- `0x180085140`
- `0x18009f394`
- `0x1800a1b64`
- `0x1800a2468`
- `0x1800a2498`
- `0x1800abca4`
- `0x1800b27e0`
- `0x1800b3128`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180071b6b`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180071b6b`
- `ntdll!EtwEventRegister` at `0x180071b1f`
- `ntdll!EtwEventRegister` at `0x180071b1f`
- `ntdll!EtwEventUnregister` at `0x180071b77`
- `ntdll!EtwEventUnregister` at `0x180071b77`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1800714cc`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x1800714cc`
- `RPCRT4!RpcStringFreeW` at `0x180071bfd`
- `RPCRT4!RpcStringFreeW` at `0x180071bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071b9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071bea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071c15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071a1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071bea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007163a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180071753`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180071817`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007163a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180071753`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180071817`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180071a81`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180071a81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007194c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007194c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180071887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18007193b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180071aaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180071887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18007193b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180071aaf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18007155b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18007155b`

## string_xrefs

- `0x180071bbb`: `onecore\com\combase\catalog\services.cxx`
- `0x180071baf`: `LogAccessFailed`

## pseudocode

```c

```
