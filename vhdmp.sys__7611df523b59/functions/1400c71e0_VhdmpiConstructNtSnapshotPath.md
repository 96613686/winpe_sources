# VhdmpiConstructNtSnapshotPath

- ea: `0x1400c71e0`
- end: `0x1400c75ee`
- name: `VhdmpiConstructNtSnapshotPath`
- size: `1038`
- prototype: `__int64 __fastcall(__int64, const GUID *, __int16, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140040218`
- `0x1400a4430`
- `0x1400c5560`
- `0x1400c5c40`
- `0x1400c62c0`

## callees

- `0x140019310`
- `0x140023560`
- `0x140035e94`
- `0x14009e8a8`
- `0x1400c71e0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400c75bd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400c75d1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400c75bd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400c75d1`
- `ntoskrnl!RtlStringFromGUID` at `0x1400c7266`
- `ntoskrnl!RtlStringFromGUID` at `0x1400c7266`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400c7411`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400c74ac`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400c7411`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400c74ac`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c7460`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c751d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c7460`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400c751d`
- `ntoskrnl!ExAllocatePool2` at `0x1400c73b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400c73b2`

## string_xrefs

- `0x1400c72b5`: `VhdmpiConstructNtSnapshotPath`
- `0x1400c7322`: `VhdmpiConstructNtSnapshotPath`

## pseudocode

```c

```
