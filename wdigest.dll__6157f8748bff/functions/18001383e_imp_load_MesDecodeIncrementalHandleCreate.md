# __imp_load_MesDecodeIncrementalHandleCreate

- ea: `0x18001383e`
- end: `0x18001384a`
- name: `__imp_load_MesDecodeIncrementalHandleCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013789`

## import_xrefs

- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18001383e`

## pseudocode

```c
__int64 load_MesDecodeIncrementalHandleCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001383e  lea     rax, __imp_MesDecodeIncrementalHandleCreate
0x180013845  jmp     __tailMerge_rpcrt4_dll
```
