# MpCopyFileChunkOnPreWrite

- ea: `0x14005f150`
- end: `0x14005f50a`
- name: `MpCopyFileChunkOnPreWrite`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140001900`

## callees

- `0x140003d20`
- `0x14000ae58`
- `0x140011890`
- `0x1400118d0`
- `0x14005e390`
- `0x14005f150`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14005f239`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14005f239`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14005f24e`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14005f24e`
- `FLTMGR!FltReleaseContext` at `0x14005f22b`
- `FLTMGR!FltReleaseContext` at `0x14005f4f9`
- `FLTMGR!FltReleaseContext` at `0x14005f22b`
- `FLTMGR!FltReleaseContext` at `0x14005f4f9`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005f26e`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005f36c`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005f26e`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005f36c`
- `FLTMGR!FltReferenceFileNameInformation` at `0x14005f33f`
- `FLTMGR!FltReferenceFileNameInformation` at `0x14005f33f`
- `FLTMGR!FltObjectDereference` at `0x14005f21a`
- `FLTMGR!FltObjectDereference` at `0x14005f21a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14005f31c`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14005f31c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f3aa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f4d4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f4e8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f3aa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f4d4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f4e8`

## pseudocode

```c

```
