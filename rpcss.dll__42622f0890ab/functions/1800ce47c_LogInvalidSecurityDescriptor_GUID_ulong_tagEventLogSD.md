# LogInvalidSecurityDescriptor(_GUID *,ulong,tagEventLogSD)

- ea: `0x1800ce47c`
- end: `0x1800ce802`
- name: `?LogInvalidSecurityDescriptor@@YAXPEAU_GUID@@KW4tagEventLogSD@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800456f8`
- `0x180073bd4`

## callees

- `0x18000b310`
- `0x180034540`
- `0x18004105c`
- `0x1800410d4`
- `0x180054b7c`
- `0x180075e48`
- `0x180075e7c`
- `0x180081210`
- `0x180085140`
- `0x1800a2468`
- `0x1800a2f6c`
- `0x1800abca4`
- `0x1800b27e0`
- `0x1800ce47c`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800ce75d`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800ce75d`
- `ntdll!EtwEventRegister` at `0x1800ce723`
- `ntdll!EtwEventRegister` at `0x1800ce723`
- `ntdll!EtwEventUnregister` at `0x1800ce76a`
- `ntdll!EtwEventUnregister` at `0x1800ce76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce792`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800ce5a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800ce5dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800ce5a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800ce5dd`

## string_xrefs

- `0x1800ce6f5`: `onecore\com\combase\catalog\services.cxx`
- `0x1800ce7b0`: `onecore\com\combase\catalog\services.cxx`
- `0x1800ce6e9`: `LogInvalidSecurityDescriptor`
- `0x1800ce7a4`: `LogInvalidSecurityDescriptor`
- `0x1800ce6fc`: `CLSID:%ws Type:%d`

## pseudocode

```c

```
