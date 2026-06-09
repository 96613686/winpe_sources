# LauncherServiceHost::GetBroker(_GUID const &,_GUID const &,void * *)

- ea: `0x180038f10`
- end: `0x1800390c3`
- name: `?GetBroker@LauncherServiceHost@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `435`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010c04`
- `0x180038f10`
- `0x18003c4f8`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038fc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038fef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038fc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038fef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038f92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039007`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039066`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038f92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039007`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039066`

## string_xrefs

- `0x180038fd7`: `onecoreuap\shell\windows.system.launcher\lib\launcherservicehost.cpp`
- `0x180039036`: `onecoreuap\shell\windows.system.launcher\lib\launcherservicehost.cpp`
- `0x180039094`: `onecoreuap\shell\windows.system.launcher\lib\launcherservicehost.cpp`

## pseudocode

```c

```
