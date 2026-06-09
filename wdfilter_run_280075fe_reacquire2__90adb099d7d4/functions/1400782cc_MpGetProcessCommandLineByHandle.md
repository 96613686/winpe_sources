# MpGetProcessCommandLineByHandle

- ea: `0x1400782cc`
- end: `0x1400783eb`
- name: `MpGetProcessCommandLineByHandle`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400387f0`
- `0x14008bff8`

## callees

- `0x1400026c0`
- `0x1400118d0`
- `0x1400782cc`

## import_xrefs

- `ntoskrnl!ZwQueryInformationProcess` at `0x14007831d`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14007838d`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14007831d`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14007838d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400783aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400783aa`

## pseudocode

```c

```
