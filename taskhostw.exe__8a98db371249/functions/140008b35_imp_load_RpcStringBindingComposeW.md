# __imp_load_RpcStringBindingComposeW

- ea: `0x140008b35`
- end: `0x140008b41`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008a07`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x140008b35`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x140008b35  lea     rax, __imp_RpcStringBindingComposeW
0x140008b3c  jmp     __tailMerge_rpcrt4_dll
```
