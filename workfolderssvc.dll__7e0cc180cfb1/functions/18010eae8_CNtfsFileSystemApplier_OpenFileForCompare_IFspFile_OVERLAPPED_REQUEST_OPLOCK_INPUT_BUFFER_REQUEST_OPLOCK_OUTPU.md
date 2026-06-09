# CNtfsFileSystemApplier::OpenFileForCompare(IFspFile *,_OVERLAPPED *,_REQUEST_OPLOCK_INPUT_BUFFER *,_REQUEST_OPLOCK_OUTPUT_BUFFER *,void * *)

- ea: `0x18010eae8`
- end: `0x18010f059`
- name: `?OpenFileForCompare@CNtfsFileSystemApplier@@AEAAJPEAUIFspFile@@PEAU_OVERLAPPED@@PEAU_REQUEST_OPLOCK_INPUT_BUFFER@@PEAU_REQUEST_OPLOCK_OUTPUT_BUFFER@@PEAPEAX@Z`
- size: `1393`
- prototype: `int(CNtfsFileSystemApplier *__hidden this, struct IFspFile *, struct _OVERLAPPED *, struct _REQUEST_OPLOCK_INPUT_BUFFER *, struct _REQUEST_OPLOCK_OUTPUT_BUFFER *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010ca50`

## callees

- `0x180007b9c`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x180058d88`
- `0x18008c1d4`
- `0x18008c218`
- `0x1800bb748`
- `0x18010eae8`
- `0x180110784`
- `0x180111f4c`
- `0x18013e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18010ee93`
- `KERNEL32!DeviceIoControl` at `0x18010ee93`
- `KERNEL32!CancelIo` at `0x18010efe5`
- `KERNEL32!CancelIo` at `0x18010efe5`
- `KERNEL32!WaitForSingleObject` at `0x18010f000`
- `KERNEL32!WaitForSingleObject` at `0x18010f000`
- `KERNEL32!GetLastError` at `0x18010eeae`
- `KERNEL32!GetLastError` at `0x18010eeae`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18010ee47`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18010ee47`
- `ntdll!NtClose` at `0x18010efba`
- `ntdll!NtClose` at `0x18010efee`
- `ntdll!NtClose` at `0x18010efba`
- `ntdll!NtClose` at `0x18010efee`

## string_xrefs

- `0x18010eb73`: `CNtfsFileSystemApplier::OpenFileForCompare`

## pseudocode

```c

```
