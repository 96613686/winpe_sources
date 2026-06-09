# DbgPrintEx_0

- ea: `0x18000658c`
- end: `0x180006592`
- name: `DbgPrintEx_0`
- size: `6`
- prototype: `ULONG(ULONG ComponentId, ULONG Level, PCSTR Format, ...)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003e70`
- `0x180005f70`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18000658c`

## pseudocode

```c
// attributes: thunk
ULONG DbgPrintEx_0(ULONG ComponentId, ULONG Level, PCSTR Format, ...)
{
  return DbgPrintEx(ComponentId, Level, Format);
}

```

## disassembly

```asm
0x18000658c  jmp     cs:__imp_DbgPrintEx
```
