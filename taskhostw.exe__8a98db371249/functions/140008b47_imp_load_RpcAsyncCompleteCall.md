# __imp_load_RpcAsyncCompleteCall

- ea: `0x140008b47`
- end: `0x140008b53`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008a07`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x140008b47`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x140008b47  lea     rax, __imp_RpcAsyncCompleteCall
0x140008b4e  jmp     __tailMerge_rpcrt4_dll
```
