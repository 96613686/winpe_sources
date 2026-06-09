# JobStore::UpdateTaskEntry(JobMoniker const &,JobSecurity const &,Triggers::Trigulator const &,Actions::ActionCollection const &,DynamicTaskInfo const *)

- ea: `0x180031a40`
- end: `0x180031ce7`
- name: `?UpdateTaskEntry@JobStore@@QEBAJAEBVJobMoniker@@AEBVJobSecurity@@AEBVTrigulator@Triggers@@AEBVActionCollection@Actions@@PEBUDynamicTaskInfo@@@Z`
- size: `679`
- prototype: `__int64 __usercall@<rax>(JobStore *__hidden this@<rcx>, const struct JobMoniker *@<rdx>, const struct JobSecurity *@<r8>, const struct Triggers::Trigulator *@<r9>, const struct Actions::ActionCollection *, const struct DynamicTaskInfo *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180047ee0`
- `0x18004fc18`
- `0x18006fed4`

## callees

- `0x18002db74`
- `0x180031a40`
- `0x180031cf0`
- `0x1800324f0`
- `0x1800333f4`
- `0x1800444f0`
- `0x18004c8b0`
- `0x180056954`
- `0x180071b54`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180031b53`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180031b53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031b89`

## pseudocode

```c

```
