# __imp_load_mmGetCurrentTask

- ea: `0x18000ba77`
- end: `0x18000ba83`
- name: `__imp_load_mmGetCurrentTask`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000b9b0`

## import_xrefs

- `WINMMBASE!mmGetCurrentTask` at `0x18000ba77`

## pseudocode

```c
__int64 load_mmGetCurrentTask()
{
  return _tailMerge_winmmbase_dll();
}

```

## disassembly

```asm
0x18000ba77  lea     rax, __imp_mmGetCurrentTask
0x18000ba7e  jmp     __tailMerge_winmmbase_dll
```
