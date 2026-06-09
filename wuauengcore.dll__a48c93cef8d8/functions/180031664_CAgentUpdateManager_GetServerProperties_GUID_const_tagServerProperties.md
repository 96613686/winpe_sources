# CAgentUpdateManager::GetServerProperties(_GUID const &,tagServerProperties *)

- ea: `0x180031664`
- end: `0x180031816`
- name: `?GetServerProperties@CAgentUpdateManager@@QEAAJAEBU_GUID@@PEAUtagServerProperties@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(CAgentUpdateManager *__hidden this, const struct _GUID *, struct tagServerProperties *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d00b0`

## callees

- `0x18000def4`
- `0x180031664`
- `0x18005c9a4`
- `0x1800608a8`
- `0x18006191c`
- `0x180110d24`
- `0x180113ae8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800316ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800316ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031734`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031734`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800317b3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800317b3`
- `OLEAUT32!__imp_SysAllocString` at `0x180031778`
- `OLEAUT32!__imp_SysAllocString` at `0x180031778`
- `OLEAUT32!__imp_SysFreeString` at `0x1800317eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800317eb`
- `OLEAUT32!__imp_SysStringLen` at `0x180031789`
- `OLEAUT32!__imp_SysStringLen` at `0x180031796`
- `OLEAUT32!__imp_SysStringLen` at `0x180031789`
- `OLEAUT32!__imp_SysStringLen` at `0x180031796`

## string_xrefs

- `0x18003168e`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x180031753`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x1800317d7`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`

## pseudocode

```c

```
