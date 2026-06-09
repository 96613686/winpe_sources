# CAckReceiver::ProcessCompletion(long,int,_OVERLAPPED *)

- ea: `0x180001c30`
- end: `0x180001ea2`
- name: `?ProcessCompletion@CAckReceiver@@UEAAJJHPEAU_OVERLAPPED@@@Z`
- size: `626`
- prototype: `__int64 __fastcall(CAckReceiver *__hidden this, int, int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800018c0`
- `0x180001c30`
- `0x180001ea4`
- `0x18000245c`
- `0x18001cf70`
- `0x18001e674`
- `0x180043c8c`
- `0x180049b60`
- `0x18004d6c8`
- `0x18004d754`
- `0x1800653ba`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001cd1`
- `KERNEL32!GetLastError` at `0x180001cd1`
- `KERNEL32!GetOverlappedResult` at `0x180001ccb`
- `KERNEL32!GetOverlappedResult` at `0x180001ccb`
- `KERNEL32!EnterCriticalSection` at `0x180001c90`
- `KERNEL32!EnterCriticalSection` at `0x180001c90`
- `KERNEL32!LeaveCriticalSection` at `0x180001e6d`
- `KERNEL32!LeaveCriticalSection` at `0x180001e6d`

## pseudocode

```c

```
