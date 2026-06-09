# __imp_load_UuidCreate

- ea: `0x18001ec10`
- end: `0x18001ec1c`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001e919`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001ec10`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001ec10  lea     rax, __imp_UuidCreate
0x18001ec17  jmp     __tailMerge_rpcrt4_dll
```
