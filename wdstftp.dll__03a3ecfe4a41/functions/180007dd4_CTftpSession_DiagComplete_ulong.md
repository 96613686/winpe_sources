# CTftpSession::DiagComplete(ulong)

- ea: `0x180007dd4`
- end: `0x18000807c`
- name: `?DiagComplete@CTftpSession@@QEAAXK@Z`
- size: `680`
- prototype: `void __fastcall(CTftpSession *this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006318`

## callees

- `0x180007dd4`
- `0x180008490`
- `0x18003ce78`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007e09`
- `KERNEL32!EnterCriticalSection` at `0x180007e09`
- `KERNEL32!LeaveCriticalSection` at `0x180008048`
- `KERNEL32!LeaveCriticalSection` at `0x180008048`
- `WdsDiag!WdsDiagRecordEvent` at `0x180007f2d`
- `WdsDiag!WdsDiagRecordEvent` at `0x18000801d`
- `WdsDiag!WdsDiagRecordEvent` at `0x180007f2d`
- `WdsDiag!WdsDiagRecordEvent` at `0x18000801d`

## pseudocode

```c

```
