# MpGetRenameParentTargetSymLinkNameInformation

- ea: `0x1400484fc`
- end: `0x140048906`
- name: `MpGetRenameParentTargetSymLinkNameInformation`
- size: `1034`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, FLT_FILE_NAME_OPTIONS NameOptions, PFLT_FILE_NAME_INFORMATION *FileNameInformation, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x140046090`

## callees

- `0x140004da8`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x1400484fc`
- `0x140048908`
- `0x140048ac0`
- `0x140048c98`
- `0x140066180`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400486ec`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14004873f`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400486ec`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14004873f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400487dd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400487f0`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400487dd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400487f0`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400488a8`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400488a8`
- `ntoskrnl!KeBugCheck` at `0x1400488c3`
- `ntoskrnl!KeBugCheck` at `0x1400488c3`
- `ntoskrnl!ObfDereferenceObject` at `0x140048870`
- `ntoskrnl!ObfDereferenceObject` at `0x140048870`
- `FLTMGR!FltClose` at `0x140048857`
- `FLTMGR!FltClose` at `0x140048857`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14004881f`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14004881f`

## pseudocode

```c

```
