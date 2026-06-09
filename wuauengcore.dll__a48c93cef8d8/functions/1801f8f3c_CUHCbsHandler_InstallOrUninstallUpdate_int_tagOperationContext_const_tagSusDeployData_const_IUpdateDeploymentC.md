# CUHCbsHandler::InstallOrUninstallUpdate(int,tagOperationContext const &,tagSusDeployData const &,IUpdateDeploymentCallback *)

- ea: `0x1801f8f3c`
- end: `0x1801f9b95`
- name: `?InstallOrUninstallUpdate@CUHCbsHandler@@AEAAJHAEBUtagOperationContext@@AEBUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@@Z`
- size: `3161`
- prototype: `__int64 __fastcall(CUHCbsHandler *__hidden this, int, const struct tagOperationContext *, const struct tagSusDeployData *, struct IUpdateDeploymentCallback *)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801f9ba0`

## callees

- `0x18003a2c0`
- `0x18011098c`
- `0x180113ae8`
- `0x180114950`
- `0x180114c0c`
- `0x180116648`
- `0x18012b618`
- `0x18012bed4`
- `0x1801f8f3c`
- `0x1801fd568`
- `0x1801fd898`
- `0x1801fd90c`
- `0x1801fd948`
- `0x1801fddf4`
- `0x1801fdf60`
- `0x1801fe084`
- `0x1801fe7e0`
- `0x1801fe824`
- `0x1801fe954`
- `0x1801fe9cc`
- `0x1801ff8c0`
- `0x1801fff60`
- `0x180238960`
- `0x180239110`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801f9238`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801f9238`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801f9807`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801f9807`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801f982e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801f982e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f926a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f926a`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1801f97c9`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1801f9849`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1801f97c9`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1801f9849`

## string_xrefs

- `0x1801f8fe2`: `Install`
- `0x1801f8fe9`: `Uninstall`
- `0x1801f916b`: `install`
- `0x1801f9a32`: `install`
- `0x1801f9162`: `uninstall`
- `0x1801f9a2b`: `uninstall`
- `0x1801f9180`: `Starting %ws of CBS update %ws`
- `0x1801f9a6b`: `Completed %ws of CBS update with type=%d, requiresReboot=%d, installerError=%d, hr=0x%x`
- `0x1801f9627`: `Installing %ws with source=%ws, workingdir=%ws`
- `0x1801f96c9`: `Uninstalling package %ws`

## pseudocode

```c

```
