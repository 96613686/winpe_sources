# NtDCompositionSyncWait

- ea: `0x1400611c0`
- end: `0x140061366`
- name: `NtDCompositionSyncWait`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140031ed0`
- `0x140058ac8`
- `0x140059100`
- `0x1400611c0`
- `0x14006136c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140061276`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140061276`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400612df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061358`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400612df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140061358`
- `ntoskrnl!ZwCreateEvent` at `0x140061216`
- `ntoskrnl!ZwCreateEvent` at `0x140061216`
- `ntoskrnl!ExEventObjectType` at `0x14006122c`
- `ntoskrnl!ExEventObjectType` at `0x140061293`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006130b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006130b`
- `ntoskrnl!ObCloseHandle` at `0x140061339`
- `ntoskrnl!ObCloseHandle` at `0x140061339`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006125c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006125c`
- `ntoskrnl!ObfDereferenceObject` at `0x140061321`
- `ntoskrnl!ObfDereferenceObject` at `0x140061321`

## pseudocode

```c

```
