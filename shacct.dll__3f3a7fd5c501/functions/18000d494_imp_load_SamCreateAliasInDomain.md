# __imp_load_SamCreateAliasInDomain

- ea: `0x18000d494`
- end: `0x18000d4a0`
- name: `__imp_load_SamCreateAliasInDomain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamCreateAliasInDomain` at `0x18000d494`

## pseudocode

```c
__int64 load_SamCreateAliasInDomain()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d494  lea     rax, __imp_SamCreateAliasInDomain
0x18000d49b  jmp     __tailMerge_samlib_dll
```
