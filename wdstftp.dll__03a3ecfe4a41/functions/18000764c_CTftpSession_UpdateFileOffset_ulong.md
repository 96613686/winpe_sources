# CTftpSession::UpdateFileOffset(ulong)

- ea: `0x18000764c`
- end: `0x180007701`
- name: `?UpdateFileOffset@CTftpSession@@AEAAKK@Z`
- size: `181`
- prototype: `__int64 __fastcall(CTftpSession *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000742c`
- `0x18000751c`

## callees

- `0x180006318`
- `0x18000764c`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000766b`
- `KERNEL32!EnterCriticalSection` at `0x18000766b`
- `KERNEL32!LeaveCriticalSection` at `0x1800076de`
- `KERNEL32!LeaveCriticalSection` at `0x1800076de`

## string_xrefs

- `0x1800076a1`: `CTftpSession::UpdateFileOffset: Acked Blocks=%u, Next Block=%u, Offset=%I64u`

## pseudocode

```c

```
