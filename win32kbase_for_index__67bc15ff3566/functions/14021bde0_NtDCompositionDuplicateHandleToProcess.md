# NtDCompositionDuplicateHandleToProcess

- ea: `0x14021bde0`
- end: `0x14021c0b2`
- name: `NtDCompositionDuplicateHandleToProcess`
- size: `722`
- prototype: `__int64 __fastcall(ULONG BugCheckCode)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14006a6d0`
- `0x14010b774`
- `0x14021bde0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14021be4a`
- `ntoskrnl!KeBugCheckEx` at `0x14021be4a`
- `ntoskrnl!ZwOpenProcess` at `0x14021bf08`
- `ntoskrnl!ZwOpenProcess` at `0x14021bf08`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14021bf40`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14021bf40`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021c05b`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021c06e`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021c05b`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14021c06e`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14021bf52`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14021bf52`
- `ntoskrnl!ObCloseHandle` at `0x14021c047`
- `ntoskrnl!ObCloseHandle` at `0x14021c081`
- `ntoskrnl!ObCloseHandle` at `0x14021c047`
- `ntoskrnl!ObCloseHandle` at `0x14021c081`
- `ntoskrnl!PsGetVersion` at `0x14021be2b`
- `ntoskrnl!PsGetVersion` at `0x14021be2b`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bf98`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bfd7`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bf98`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x14021bfd7`
- `ntoskrnl!ObDuplicateObject` at `0x14021c01a`
- `ntoskrnl!ObDuplicateObject` at `0x14021c01a`
- `ntoskrnl!ObfDereferenceObject` at `0x14021c092`
- `ntoskrnl!ObfDereferenceObject` at `0x14021c092`

## pseudocode

```c

```
