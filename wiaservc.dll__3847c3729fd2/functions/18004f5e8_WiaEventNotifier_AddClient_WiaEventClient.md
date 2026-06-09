# WiaEventNotifier::AddClient(WiaEventClient *)

- ea: `0x18004f5e8`
- end: `0x18004f809`
- name: `?AddClient@WiaEventNotifier@@QEAAJPEAVWiaEventClient@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(WiaEventNotifier *__hidden this, struct WiaEventClient *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180051c60`

## callees

- `0x18000ac34`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x1800208f8`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18004f5e8`
- `0x1800500b4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004f62d`
- `KERNEL32!LeaveCriticalSection` at `0x18004f7f2`
- `KERNEL32!LeaveCriticalSection` at `0x18004f62d`
- `KERNEL32!LeaveCriticalSection` at `0x18004f7f2`

## string_xrefs

- `0x18004f708`: `Warning: Attempting to add client %p to WiaEventNotifier when it already exists in the list`
- `0x18004f749`: `Warning: Attempting to add client %p to WiaEventNotifier when it already exists in the list`

## pseudocode

```c

```
