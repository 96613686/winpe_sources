# JobStore::UpdateTaskEntry(JobMoniker const &,JobSecurity const &,Triggers::Trigulator const &,Actions::ActionCollection const &,DynamicTaskInfo const *)

- ea: `0x180017e70`
- end: `0x180018100`
- name: `?UpdateTaskEntry@JobStore@@QEBAJAEBVJobMoniker@@AEBVJobSecurity@@AEBVTrigulator@Triggers@@AEBVActionCollection@Actions@@PEBUDynamicTaskInfo@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(JobStore *this, const struct JobMoniker *, const struct JobSecurity *, const struct Triggers::Trigulator *, const struct Actions::ActionCollection *, BYTE *lpData)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180045df0`
- `0x18004d868`
- `0x18006c840`

## callees

- `0x180017b84`
- `0x180017e70`
- `0x180018110`
- `0x180018a20`
- `0x18002132c`
- `0x180042190`
- `0x18004a594`
- `0x180054084`
- `0x18006e43c`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180017f83`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180017f83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017fa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017f9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017fa9`

## pseudocode

```c

```
