# ADAPTER_RENDER::GetUmdFileVersion(_LARGE_INTEGER *)

- ea: `0x1403634e0`
- end: `0x1403638e4`
- name: `?GetUmdFileVersion@ADAPTER_RENDER@@QEAAJPEAT_LARGE_INTEGER@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(ADAPTER_RENDER *__hidden this, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14035feb0`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001b9c0`
- `0x1403634e0`
- `0x14036399c`
- `0x140363af0`

## import_xrefs

- `ntoskrnl!wcsnlen` at `0x1403635fb`
- `ntoskrnl!wcsnlen` at `0x14036374a`
- `ntoskrnl!wcsnlen` at `0x1403635fb`
- `ntoskrnl!wcsnlen` at `0x14036374a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1403636ec`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1403636ff`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363825`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363838`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363863`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1403636ec`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1403636ff`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363825`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363838`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140363863`
- `watchdog!WdLogSingleEntry2` at `0x140363895`
- `watchdog!WdLogSingleEntry2` at `0x140363895`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14036372e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14036372e`
- `watchdog!WdLogSingleEntry0` at `0x140363518`
- `watchdog!WdLogSingleEntry0` at `0x140363617`
- `watchdog!WdLogSingleEntry0` at `0x140363766`
- `watchdog!WdLogSingleEntry0` at `0x140363518`
- `watchdog!WdLogSingleEntry0` at `0x140363617`
- `watchdog!WdLogSingleEntry0` at `0x140363766`
- `watchdog!WdLogSingleEntry1` at `0x1403636a3`
- `watchdog!WdLogSingleEntry1` at `0x1403637ff`
- `watchdog!WdLogSingleEntry1` at `0x1403636a3`
- `watchdog!WdLogSingleEntry1` at `0x1403637ff`

## string_xrefs

- `0x14036381a`: `\Systemroot\System32\`
- `0x1403638a6`: `Failed to open the user mode driver DLL on adapter %I64d (ntStatus = %I64d).`

## pseudocode

```c

```
