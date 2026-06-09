# LogInvalidSecurityDescriptor(_GUID *,ulong,tagEventLogSD)

- ea: `0x1800d4728`
- end: `0x1800d4ad3`
- name: `?LogInvalidSecurityDescriptor@@YAXPEAU_GUID@@KW4tagEventLogSD@@@Z`
- size: `939`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003afb8`
- `0x1800782dc`

## callees

- `0x180011db0`
- `0x180034260`
- `0x18004ab7c`
- `0x18004ac08`
- `0x18005ad10`
- `0x18007a604`
- `0x18007a638`
- `0x1800855d8`
- `0x180089e5c`
- `0x1800a7a48`
- `0x1800a858c`
- `0x1800b0c7c`
- `0x1800b7ac0`
- `0x1800d4728`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800d4a1b`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800d4a1b`
- `ntdll!EtwEventRegister` at `0x1800d49db`
- `ntdll!EtwEventRegister` at `0x1800d49db`
- `ntdll!EtwEventUnregister` at `0x1800d4a2e`
- `ntdll!EtwEventUnregister` at `0x1800d4a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800d484c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800d488f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800d484c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800d488f`

## string_xrefs

- `0x1800d49ad`: `onecore\com\combase\catalog\services.cxx`
- `0x1800d4a80`: `onecore\com\combase\catalog\services.cxx`
- `0x1800d49b4`: `CLSID:%ws Type:%d`
- `0x1800d49a1`: `LogInvalidSecurityDescriptor`
- `0x1800d4a74`: `LogInvalidSecurityDescriptor`

## pseudocode

```c

```
