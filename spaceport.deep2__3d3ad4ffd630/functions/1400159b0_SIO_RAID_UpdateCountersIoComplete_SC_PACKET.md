# SIO_RAID::UpdateCountersIoComplete(SC_PACKET *)

- ea: `0x1400159b0`
- end: `0x140015ab9`
- name: `?UpdateCountersIoComplete@SIO_RAID@@QEAAXPEAVSC_PACKET@@@Z`
- size: `265`
- prototype: `void __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140015850`
- `0x1400158d0`

## callees

- `0x1400159b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140015a30`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140015a30`
- `HAL!KeQueryPerformanceCounter` at `0x1400159df`
- `HAL!KeQueryPerformanceCounter` at `0x140015a60`
- `HAL!KeQueryPerformanceCounter` at `0x1400159df`
- `HAL!KeQueryPerformanceCounter` at `0x140015a60`

## pseudocode

```c

```
