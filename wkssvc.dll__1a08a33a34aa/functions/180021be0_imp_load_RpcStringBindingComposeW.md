# __imp_load_RpcStringBindingComposeW

- ea: `0x180021be0`
- end: `0x180021bec`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020740`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180021be0`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180021be0  lea     rax, __imp_RpcStringBindingComposeW
0x180021be7  jmp     __tailMerge_rpcrt4_dll
```
