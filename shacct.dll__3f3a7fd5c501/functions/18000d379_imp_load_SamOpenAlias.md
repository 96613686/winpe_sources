# __imp_load_SamOpenAlias

- ea: `0x18000d379`
- end: `0x18000d385`
- name: `__imp_load_SamOpenAlias`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamOpenAlias` at `0x18000d379`

## pseudocode

```c
__int64 load_SamOpenAlias()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d379  lea     rax, __imp_SamOpenAlias
0x18000d380  jmp     __tailMerge_samlib_dll
```
