# __imp_load_UuidCreate

- ea: `0x180008c72`
- end: `0x180008c7e`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008bf3`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180008c72`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180008c72  lea     rax, __imp_UuidCreate
0x180008c79  jmp     __tailMerge_rpcrt4_dll
```
