# UserManagerTokenAndShellHandler::Initialize(int *)

- ea: `0x180046b24`
- end: `0x180046dcd`
- name: `?Initialize@UserManagerTokenAndShellHandler@@QEAAKPEAH@Z`
- size: `681`
- prototype: `unsigned int __fastcall(UserManagerTokenAndShellHandler *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180072004`

## callees

- `0x180002ff0`
- `0x180012890`
- `0x180016c50`
- `0x18002799c`
- `0x180046b24`
- `0x1800624bc`
- `0x1800b6cdc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180046c25`
- `msvcrt!_wcsicmp` at `0x180046c45`
- `msvcrt!_wcsicmp` at `0x180046c8a`
- `msvcrt!_wcsicmp` at `0x180046c25`
- `msvcrt!_wcsicmp` at `0x180046c45`
- `msvcrt!_wcsicmp` at `0x180046c8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b84`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b97`
- `ntdll!RtlSetProcessIsCritical` at `0x180046cc5`
- `ntdll!RtlSetProcessIsCritical` at `0x180046cc5`
- `ntdll!RtlIsMultiSessionSku` at `0x180046ba7`
- `ntdll!RtlIsMultiSessionSku` at `0x180046ba7`

## string_xrefs

- `0x180046b45`: `Starting TokenAndShellHandler`
- `0x180046d80`: `Successfully read config`

## pseudocode

```c

```
