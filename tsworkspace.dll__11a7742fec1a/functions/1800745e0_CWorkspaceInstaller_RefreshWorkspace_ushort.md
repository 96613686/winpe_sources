# CWorkspaceInstaller::RefreshWorkspace(ushort *)

- ea: `0x1800745e0`
- end: `0x18007492c`
- name: `?RefreshWorkspace@CWorkspaceInstaller@@UEAAJPEAG@Z`
- size: `844`
- prototype: `int(CWorkspaceInstaller *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800034b8`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x1800745e0`
- `0x180074e28`
- `0x180074ee0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180074902`
- `msvcrt!??3@YAXPEAX@Z` at `0x180074902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007472b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007472b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074768`
- `USER32!TranslateMessage` at `0x180074838`
- `USER32!TranslateMessage` at `0x180074838`
- `USER32!PostQuitMessage` at `0x180074855`
- `USER32!PostQuitMessage` at `0x180074855`
- `USER32!GetMessageW` at `0x180074808`
- `USER32!GetMessageW` at `0x180074808`
- `USER32!DispatchMessageW` at `0x180074843`
- `USER32!DispatchMessageW` at `0x180074843`
- `USER32!SetTimer` at `0x1800746fe`
- `USER32!SetTimer` at `0x1800746fe`
- `USER32!KillTimer` at `0x180074912`
- `USER32!KillTimer` at `0x180074912`

## string_xrefs

- `0x1800747cc`: `CWorkspaceUpdateTask::UpdateWorkspaces failed`
- `0x180074897`: `WORKSPACE_UPDATE_ALL_COMPLETE returned a failure`

## pseudocode

```c

```
