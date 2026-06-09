# RtlLookupFunctionEntry_0

- ea: `0x140001258`
- end: `0x14000125e`
- name: `RtlLookupFunctionEntry_0`
- size: `6`
- prototype: `PRUNTIME_FUNCTION __stdcall(DWORD64 ControlPc, PDWORD64 ImageBase, PUNWIND_HISTORY_TABLE HistoryTable)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001010`

## import_xrefs

- `ntdll!RtlLookupFunctionEntry` at `0x140001258`

## pseudocode

```c
// attributes: thunk
PRUNTIME_FUNCTION __stdcall RtlLookupFunctionEntry_0(
        DWORD64 ControlPc,
        PDWORD64 ImageBase,
        PUNWIND_HISTORY_TABLE HistoryTable)
{
  return RtlLookupFunctionEntry(ControlPc, ImageBase, HistoryTable);
}

```

## disassembly

```asm
0x140001258  jmp     cs:__imp_RtlLookupFunctionEntry
```
