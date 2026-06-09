# RtlAppendUnicodeToString_0

- ea: `0x180006690`
- end: `0x180006696`
- name: `RtlAppendUnicodeToString_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006180`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180006690`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall RtlAppendUnicodeToString_0(PUNICODE_STRING Destination, PCWSTR Source)
{
  return RtlAppendUnicodeToString(Destination, Source);
}

```

## disassembly

```asm
0x180006690  jmp     cs:__imp_RtlAppendUnicodeToString
```
