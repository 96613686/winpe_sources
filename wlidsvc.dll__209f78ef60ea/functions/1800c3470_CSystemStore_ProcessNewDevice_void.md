# CSystemStore::ProcessNewDevice(void)

- ea: `0x1800c3470`
- end: `0x1800c361f`
- name: `?ProcessNewDevice@CSystemStore@@SAJXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800ebad8`

## callees

- `0x180006ac0`
- `0x18000c050`
- `0x180023d24`
- `0x180039d60`
- `0x18003c814`
- `0x18005ae00`
- `0x1800c3470`
- `0x1800c37a4`
- `0x1800e6f98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c349d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c349d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34d0`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800c34c6`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800c34c6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c35fc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c35fc`

## string_xrefs

- `0x1800c3505`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`
- `0x1800c3545`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`
- `0x1800c357f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`

## pseudocode

```c

```
