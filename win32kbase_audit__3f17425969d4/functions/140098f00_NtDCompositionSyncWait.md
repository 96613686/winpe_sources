# NtDCompositionSyncWait

- ea: `0x140098f00`
- end: `0x1400990a6`
- name: `NtDCompositionSyncWait`
- size: `422`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14006ed10`
- `0x14008a2b8`
- `0x14008a8f0`
- `0x140098f00`
- `0x1400990ac`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140098fb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140098fb6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009901f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140099098`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009901f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140099098`
- `ntoskrnl!ZwCreateEvent` at `0x140098f56`
- `ntoskrnl!ZwCreateEvent` at `0x140098f56`
- `ntoskrnl!ExEventObjectType` at `0x140098f6c`
- `ntoskrnl!ExEventObjectType` at `0x140098fd3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009904b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009904b`
- `ntoskrnl!ObCloseHandle` at `0x140099079`
- `ntoskrnl!ObCloseHandle` at `0x140099079`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140098f9c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140098f9c`
- `ntoskrnl!ObfDereferenceObject` at `0x140099061`
- `ntoskrnl!ObfDereferenceObject` at `0x140099061`

## pseudocode

```c

```
