# __imp_load_RpcAsyncCompleteCall

- ea: `0x180025d94`
- end: `0x180025da0`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024d30`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180025d94`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180025d94  lea     rax, __imp_RpcAsyncCompleteCall
0x180025d9b  jmp     __tailMerge_rpcrt4_dll
```
