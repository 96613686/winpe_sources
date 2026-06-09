# NtDCompositionDuplicateHandleToProcess

- ea: `0x14021b530`
- end: `0x14021b802`
- name: `NtDCompositionDuplicateHandleToProcess`
- size: `722`
- prototype: `__int64 __fastcall(ULONG BugCheckCode)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140032170`
- `0x140104574`
- `0x14021b530`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14021b59a`
- `ntoskrnl!KeBugCheckEx` at `0x14021b59a`
- `ntoskrnl!ZwOpenProcess` at `0x14021b658`
- `ntoskrnl!ZwOpenProcess` at `0x14021b658`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14021b690`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14021b690`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021b7ab`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021b7be`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021b7ab`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021b7be`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14021b6a2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14021b6a2`
- `ntoskrnl!ObCloseHandle` at `0x14021b797`
- `ntoskrnl!ObCloseHandle` at `0x14021b7d1`
- `ntoskrnl!ObCloseHandle` at `0x14021b797`
- `ntoskrnl!ObCloseHandle` at `0x14021b7d1`
- `ntoskrnl!PsGetVersion` at `0x14021b57b`
- `ntoskrnl!PsGetVersion` at `0x14021b57b`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021b6e8`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021b727`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021b6e8`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021b727`
- `ntoskrnl!ObDuplicateObject` at `0x14021b76a`
- `ntoskrnl!ObDuplicateObject` at `0x14021b76a`
- `ntoskrnl!ObfDereferenceObject` at `0x14021b7e2`
- `ntoskrnl!ObfDereferenceObject` at `0x14021b7e2`

## pseudocode

```c

```
