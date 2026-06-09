# __imp_load_UuidCreate

- ea: `0x18001c8f9`
- end: `0x18001c905`
- name: `__imp_load_UuidCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c856`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001c8f9`

## pseudocode

```c
__int64 load_UuidCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001c8f9  lea     rax, __imp_UuidCreate
0x18001c900  jmp     __tailMerge_rpcrt4_dll
```
