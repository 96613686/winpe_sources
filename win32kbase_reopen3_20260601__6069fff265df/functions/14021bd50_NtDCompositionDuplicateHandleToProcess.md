# NtDCompositionDuplicateHandleToProcess

- ea: `0x14021bd50`
- end: `0x14021c022`
- name: `NtDCompositionDuplicateHandleToProcess`
- size: `722`
- prototype: `__int64 __fastcall(ULONG BugCheckCode)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140028ef0`
- `0x140108d04`
- `0x14021bd50`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14021bdba`
- `ntoskrnl!KeBugCheckEx` at `0x14021bdba`
- `ntoskrnl!ZwOpenProcess` at `0x14021be78`
- `ntoskrnl!ZwOpenProcess` at `0x14021be78`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14021beb0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14021beb0`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021bfcb`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021bfde`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021bfcb`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021bfde`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14021bec2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14021bec2`
- `ntoskrnl!ObCloseHandle` at `0x14021bfb7`
- `ntoskrnl!ObCloseHandle` at `0x14021bff1`
- `ntoskrnl!ObCloseHandle` at `0x14021bfb7`
- `ntoskrnl!ObCloseHandle` at `0x14021bff1`
- `ntoskrnl!PsGetVersion` at `0x14021bd9b`
- `ntoskrnl!PsGetVersion` at `0x14021bd9b`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bf08`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bf47`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bf08`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bf47`
- `ntoskrnl!ObDuplicateObject` at `0x14021bf8a`
- `ntoskrnl!ObDuplicateObject` at `0x14021bf8a`
- `ntoskrnl!ObfDereferenceObject` at `0x14021c002`
- `ntoskrnl!ObfDereferenceObject` at `0x14021c002`

## pseudocode

```c

```
