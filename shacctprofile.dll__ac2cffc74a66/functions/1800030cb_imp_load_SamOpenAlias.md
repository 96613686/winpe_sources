# __imp_load_SamOpenAlias

- ea: `0x1800030cb`
- end: `0x1800030d7`
- name: `__imp_load_SamOpenAlias`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ff2`

## import_xrefs

- `SAMLIB!SamOpenAlias` at `0x1800030cb`

## pseudocode

```c
__int64 load_SamOpenAlias()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x1800030cb  lea     rax, __imp_SamOpenAlias
0x1800030d2  jmp     __tailMerge_samlib_dll
```
