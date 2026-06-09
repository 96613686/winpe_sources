# __imp_load_RpcStringBindingComposeW

- ea: `0x180025d4c`
- end: `0x180025d58`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024d30`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180025d4c`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180025d4c  lea     rax, __imp_RpcStringBindingComposeW
0x180025d53  jmp     __tailMerge_rpcrt4_dll
```
