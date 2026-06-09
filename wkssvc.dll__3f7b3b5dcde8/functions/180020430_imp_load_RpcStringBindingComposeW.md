# __imp_load_RpcStringBindingComposeW

- ea: `0x180020430`
- end: `0x18002043c`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ef90`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180020430`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180020430  lea     rax, __imp_RpcStringBindingComposeW
0x180020437  jmp     __tailMerge_rpcrt4_dll
```
