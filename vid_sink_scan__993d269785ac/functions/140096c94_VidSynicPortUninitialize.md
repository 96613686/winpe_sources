# VidSynicPortUninitialize

- ea: `0x140096c94`
- end: `0x140096d1f`
- name: `VidSynicPortUninitialize`
- size: `139`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400825cc`
- `0x140096308`

## callees

- `0x140096c94`

## import_xrefs

- `ntoskrnl!KeRemoveQueueDpc` at `0x140096cc9`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140096cc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096cff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096cff`
- `winhvr!WinHvSetSyntheticInterruptHandler` at `0x140096cad`
- `winhvr!WinHvSetSyntheticInterruptHandler` at `0x140096cad`
- `winhvr!WinHvFreePartitionSintIndex` at `0x140096cde`
- `winhvr!WinHvFreePartitionSintIndex` at `0x140096cde`

## pseudocode

```c

```
