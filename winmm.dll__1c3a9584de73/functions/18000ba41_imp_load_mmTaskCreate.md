# __imp_load_mmTaskCreate

- ea: `0x18000ba41`
- end: `0x18000ba4d`
- name: `__imp_load_mmTaskCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b9b0`

## import_xrefs

- `WINMMBASE!mmTaskCreate` at `0x18000ba41`

## pseudocode

```c
__int64 load_mmTaskCreate()
{
  return _tailMerge_winmmbase_dll();
}

```

## disassembly

```asm
0x18000ba41  lea     rax, __imp_mmTaskCreate
0x18000ba48  jmp     __tailMerge_winmmbase_dll
```
