# __imp_load_RpcStringBindingComposeW

- ea: `0x1800017b9`
- end: `0x1800017c5`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001354`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x1800017b9`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800017b9  lea     rax, __imp_RpcStringBindingComposeW
0x1800017c0  jmp     __tailMerge_rpcrt4_dll
```
