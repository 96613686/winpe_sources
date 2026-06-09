# __imp_load_SamRemoveMemberFromAlias

- ea: `0x18000d4b8`
- end: `0x18000d4c4`
- name: `__imp_load_SamRemoveMemberFromAlias`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamRemoveMemberFromAlias` at `0x18000d4b8`

## pseudocode

```c
__int64 load_SamRemoveMemberFromAlias()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d4b8  lea     rax, __imp_SamRemoveMemberFromAlias
0x18000d4bf  jmp     __tailMerge_samlib_dll
```
