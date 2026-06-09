# __imp_load_mmTaskBlock

- ea: `0x18000ba2f`
- end: `0x18000ba3b`
- name: `__imp_load_mmTaskBlock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b9b0`

## import_xrefs

- `WINMMBASE!mmTaskBlock` at `0x18000ba2f`

## pseudocode

```c
__int64 load_mmTaskBlock()
{
  return _tailMerge_winmmbase_dll();
}

```

## disassembly

```asm
0x18000ba2f  lea     rax, __imp_mmTaskBlock
0x18000ba36  jmp     __tailMerge_winmmbase_dll
```
