# WdfTransientDevStateMgr::TryToRestartTransientStateDevices(int *,int)

- ea: `0x14008d2b8`
- end: `0x14008d580`
- name: `?TryToRestartTransientStateDevices@WdfTransientDevStateMgr@@AEAAKPEAHH@Z`
- size: `712`
- prototype: `unsigned int __fastcall(WdfTransientDevStateMgr *__hidden this, int *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14008cf38`
- `0x14008d22c`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140019014`
- `0x140032c78`
- `0x1400575b0`
- `0x14008d2b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008d50d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14008d3e2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14008d3e2`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14008d35b`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14008d35b`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x14008d385`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x14008d385`
- `DEVOBJ!DevObjDeleteDeviceInfo` at `0x14008d4ba`
- `DEVOBJ!DevObjDeleteDeviceInfo` at `0x14008d4ba`

## pseudocode

```c

```
