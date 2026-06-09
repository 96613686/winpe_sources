# MpApplyVolumeExclusions

- ea: `0x140071f88`
- end: `0x140072389`
- name: `MpApplyVolumeExclusions`
- size: `1025`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140071cb4`

## callees

- `0x1400049dc`
- `0x140007030`
- `0x140009bf0`
- `0x14000b3bc`
- `0x1400118d0`
- `0x140040388`
- `0x140071f88`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140072138`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007229d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140072138`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007229d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072354`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140072354`
- `ntoskrnl!ExReleaseResourceLite` at `0x140072348`
- `ntoskrnl!ExReleaseResourceLite` at `0x140072348`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400720f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140072259`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400720f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140072259`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140072013`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140072013`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071ffe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071ffe`

## string_xrefs

- `0x140072182`: `[Mini-filter] volume %wZ is one of the configured included volumes`
- `0x1400722e7`: `[Mini-filter] volume %wZ excluded from scanning due to path exclusion`

## pseudocode

```c

```
