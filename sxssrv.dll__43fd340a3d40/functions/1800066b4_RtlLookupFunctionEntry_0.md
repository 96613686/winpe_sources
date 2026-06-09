# RtlLookupFunctionEntry_0

- ea: `0x1800066b4`
- end: `0x1800066ba`
- name: `RtlLookupFunctionEntry_0`
- size: `6`
- prototype: `PRUNTIME_FUNCTION __stdcall(ULONG64 ControlPc, PULONG64 ImageBase, PUNWIND_HISTORY_TABLE HistoryTable)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006400`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x1800066b4`

## pseudocode

```c
// attributes: thunk
PRUNTIME_FUNCTION __stdcall RtlLookupFunctionEntry_0(
        ULONG64 ControlPc,
        PULONG64 ImageBase,
        PUNWIND_HISTORY_TABLE HistoryTable)
{
  return RtlLookupFunctionEntry(ControlPc, ImageBase, HistoryTable);
}

```

## disassembly

```asm
0x1800066b4  jmp     cs:__imp_RtlLookupFunctionEntry
```
