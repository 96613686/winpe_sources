# __imp_load_mmTaskSignal

- ea: `0x18000ba53`
- end: `0x18000ba5f`
- name: `__imp_load_mmTaskSignal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b9b0`

## import_xrefs

- `WINMMBASE!mmTaskSignal` at `0x18000ba53`

## pseudocode

```c
__int64 load_mmTaskSignal()
{
  return _tailMerge_winmmbase_dll();
}

```

## disassembly

```asm
0x18000ba53  lea     rax, __imp_mmTaskSignal
0x18000ba5a  jmp     __tailMerge_winmmbase_dll
```
