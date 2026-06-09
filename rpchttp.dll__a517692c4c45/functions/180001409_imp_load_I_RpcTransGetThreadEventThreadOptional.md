# __imp_load_I_RpcTransGetThreadEventThreadOptional

- ea: `0x180001409`
- end: `0x180001415`
- name: `__imp_load_I_RpcTransGetThreadEventThreadOptional`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001354`

## import_xrefs

- `RPCRT4!I_RpcTransGetThreadEventThreadOptional` at `0x180001409`

## pseudocode

```c
__int64 load_I_RpcTransGetThreadEventThreadOptional()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180001409  lea     rax, __imp_I_RpcTransGetThreadEventThreadOptional
0x180001410  jmp     __tailMerge_rpcrt4_dll
```
