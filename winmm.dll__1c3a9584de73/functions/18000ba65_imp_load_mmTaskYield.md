# __imp_load_mmTaskYield

- ea: `0x18000ba65`
- end: `0x18000ba71`
- name: `__imp_load_mmTaskYield`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b9b0`

## import_xrefs

- `WINMMBASE!mmTaskYield` at `0x18000ba65`

## pseudocode

```c
__int64 load_mmTaskYield()
{
  return _tailMerge_winmmbase_dll();
}

```

## disassembly

```asm
0x18000ba65  lea     rax, __imp_mmTaskYield
0x18000ba6c  jmp     __tailMerge_winmmbase_dll
```
