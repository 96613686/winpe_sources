# __imp_load_RpcAsyncCompleteCall

- ea: `0x1800209cc`
- end: `0x1800209d8`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020740`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800209cc`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800209cc  lea     rax, __imp_RpcAsyncCompleteCall
0x1800209d3  jmp     __tailMerge_rpcrt4_dll
```
