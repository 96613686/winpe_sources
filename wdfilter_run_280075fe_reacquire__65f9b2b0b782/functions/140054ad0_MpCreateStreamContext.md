# MpCreateStreamContext

- ea: `0x140054ad0`
- end: `0x140055513`
- name: `MpCreateStreamContext`
- size: `2627`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, char, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1400408b0`
- `0x140047ad0`
- `0x140051af0`

## callees

- `0x140003c70`
- `0x140003d20`
- `0x1400051bc`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x14003c3b0`
- `0x140054ad0`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x140054f3b`
- `ntoskrnl!InitializeSListHead` at `0x140054f3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005515a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005515a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005514e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005514e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400550f5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400550f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400550e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400550e0`
- `FLTMGR!FltReleaseContext` at `0x1400551e8`
- `FLTMGR!FltReleaseContext` at `0x14005543d`
- `FLTMGR!FltReleaseContext` at `0x140055480`
- `FLTMGR!FltReleaseContext` at `0x14008caae`
- `FLTMGR!FltReleaseContext` at `0x1400551e8`
- `FLTMGR!FltReleaseContext` at `0x14005543d`
- `FLTMGR!FltReleaseContext` at `0x140055480`
- `FLTMGR!FltReleaseContext` at `0x14008caae`
- `FLTMGR!FltGetFileNameInformation` at `0x140054ebd`
- `FLTMGR!FltGetFileNameInformation` at `0x140054ebd`
- `FLTMGR!FltSetStreamContext` at `0x1400550ad`
- `FLTMGR!FltSetStreamContext` at `0x1400550ad`
- `FLTMGR!FltInitializePushLock` at `0x140054f92`
- `FLTMGR!FltInitializePushLock` at `0x140054fad`
- `FLTMGR!FltInitializePushLock` at `0x140054fc8`
- `FLTMGR!FltInitializePushLock` at `0x140054f92`
- `FLTMGR!FltInitializePushLock` at `0x140054fad`
- `FLTMGR!FltInitializePushLock` at `0x140054fc8`
- `FLTMGR!FltReferenceContext` at `0x140054e74`
- `FLTMGR!FltReferenceContext` at `0x140054e74`
- `FLTMGR!FltParseFileNameInformation` at `0x14005518d`
- `FLTMGR!FltParseFileNameInformation` at `0x14005518d`
- `FLTMGR!FltAllocateContext` at `0x140054d53`
- `FLTMGR!FltAllocateContext` at `0x140054d53`
- `FLTMGR!FltQueryInformationFile` at `0x140054be7`
- `FLTMGR!FltQueryInformationFile` at `0x140054c3a`
- `FLTMGR!FltQueryInformationFile` at `0x140054be7`
- `FLTMGR!FltQueryInformationFile` at `0x140054c3a`
- `FLTMGR!FltGetInstanceContext` at `0x140054b6d`
- `FLTMGR!FltGetInstanceContext` at `0x140054b6d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055467`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008ca95`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140055467`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008ca95`

## pseudocode

```c

```
