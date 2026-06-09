# RaidAdapterRequestComplete

- ea: `0x140052e00`
- end: `0x1400531c6`
- name: `RaidAdapterRequestComplete`
- size: `966`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008a40`
- `0x140008eb0`
- `0x1400382b0`
- `0x140058bd0`
- `0x140093410`
- `0x140096410`
- `0x1400c96b0`

## callees

- `0x14002cd70`
- `0x14004a0a8`
- `0x140052e00`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140052f80`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005317e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140052f80`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005317e`
- `ntoskrnl!EtwWriteEx` at `0x140053165`
- `ntoskrnl!EtwWriteEx` at `0x140053165`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140052f29`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140052f29`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005319a`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005319a`
- `ntoskrnl!KeBugCheckEx` at `0x140052e79`
- `ntoskrnl!KeBugCheckEx` at `0x140052e79`

## pseudocode

```c

```
