# __imp_load_MesEncodeIncrementalHandleCreate

- ea: `0x18001382c`
- end: `0x180013838`
- name: `__imp_load_MesEncodeIncrementalHandleCreate`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013789`

## import_xrefs

- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x18001382c`

## pseudocode

```c
__int64 load_MesEncodeIncrementalHandleCreate()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001382c  lea     rax, __imp_MesEncodeIncrementalHandleCreate
0x180013833  jmp     __tailMerge_rpcrt4_dll
```
