# __imp_load_UuidCreate

- ea: `0x180001bf6`
- end: `0x180001c02`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001b77`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180001bf6`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180001bf6  lea     rax, __imp_UuidCreate
0x180001bfd  jmp     __tailMerge_rpcrt4_dll
```
