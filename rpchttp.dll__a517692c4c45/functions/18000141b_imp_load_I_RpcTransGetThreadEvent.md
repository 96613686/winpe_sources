# __imp_load_I_RpcTransGetThreadEvent

- ea: `0x18000141b`
- end: `0x180001427`
- name: `__imp_load_I_RpcTransGetThreadEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001354`

## import_xrefs

- `RPCRT4!I_RpcTransGetThreadEvent` at `0x18000141b`

## pseudocode

```c
__int64 load_I_RpcTransGetThreadEvent()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18000141b  lea     rax, __imp_I_RpcTransGetThreadEvent
0x180001422  jmp     __tailMerge_rpcrt4_dll
```
