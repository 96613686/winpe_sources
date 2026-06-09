# Windows::Reboot::RebootSystem(Monitor<std::pair<bool,bool>> &,bool)

- ea: `0x180093410`
- end: `0x18009355d`
- name: `?RebootSystem@Reboot@Windows@@UEAAXAEAV?$Monitor@U?$pair@_N_N@std@@@@_N@Z`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x180010e80`
- `0x180039d4c`
- `0x180042e00`
- `0x180042e48`
- `0x1800932e0`
- `0x180093410`
- `0x180093864`
- `0x1800dff58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800934d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800934d6`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x180093450`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x180093450`

## string_xrefs

- `0x18009352e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x180093429`: `SeShutdownPrivilege`
- `0x1800934e2`: `SeShutdownPrivilege`

## pseudocode

```c

```
