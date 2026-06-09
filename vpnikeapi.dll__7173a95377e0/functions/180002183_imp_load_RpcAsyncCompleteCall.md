# __imp_load_RpcAsyncCompleteCall

- ea: `0x180002183`
- end: `0x18000218f`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180002183`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180002183  lea     rax, __imp_RpcAsyncCompleteCall
0x18000218a  jmp     __tailMerge_rpcrt4_dll
```
