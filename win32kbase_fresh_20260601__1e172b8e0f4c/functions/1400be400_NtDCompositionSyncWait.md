# NtDCompositionSyncWait

- ea: `0x1400be400`
- end: `0x1400be5a6`
- name: `NtDCompositionSyncWait`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140028c50`
- `0x14004fd08`
- `0x140050340`
- `0x1400be400`
- `0x1400be5ac`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400be4b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400be4b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400be51f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400be598`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400be51f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400be598`
- `ntoskrnl!ZwCreateEvent` at `0x1400be456`
- `ntoskrnl!ZwCreateEvent` at `0x1400be456`
- `ntoskrnl!ExEventObjectType` at `0x1400be46c`
- `ntoskrnl!ExEventObjectType` at `0x1400be4d3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400be54b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400be54b`
- `ntoskrnl!ObCloseHandle` at `0x1400be579`
- `ntoskrnl!ObCloseHandle` at `0x1400be579`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400be49c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400be49c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400be561`
- `ntoskrnl!ObfDereferenceObject` at `0x1400be561`

## pseudocode

```c

```
