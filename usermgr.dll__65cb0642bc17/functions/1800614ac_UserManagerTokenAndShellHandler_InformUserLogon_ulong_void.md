# UserManagerTokenAndShellHandler::InformUserLogon(ulong,void *)

- ea: `0x1800614ac`
- end: `0x180061581`
- name: `?InformUserLogon@UserManagerTokenAndShellHandler@@QEAAJKPEAX@Z`
- size: `213`
- prototype: `int(UserManagerTokenAndShellHandler *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18004611c`
- `0x1800b7464`

## callees

- `0x1800356f8`
- `0x1800614ac`
- `0x1800624bc`
- `0x1800b7570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061554`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061554`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800614e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800614e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800614fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180061504`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800614fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180061504`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006152f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18006152f`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800614bf`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800614bf`

## pseudocode

```c

```
