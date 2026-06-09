# __imp_load_SamDeleteAlias

- ea: `0x18000d4dc`
- end: `0x18000d4e8`
- name: `__imp_load_SamDeleteAlias`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamDeleteAlias` at `0x18000d4dc`

## pseudocode

```c
__int64 load_SamDeleteAlias()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d4dc  lea     rax, __imp_SamDeleteAlias
0x18000d4e3  jmp     __tailMerge_samlib_dll
```
