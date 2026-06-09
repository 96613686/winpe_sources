# __imp_load_UuidCreate

- ea: `0x180020ea4`
- end: `0x180020eb0`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020e25`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180020ea4`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180020ea4  lea     rax, __imp_UuidCreate
0x180020eab  jmp     __tailMerge_rpcrt4_dll
```
