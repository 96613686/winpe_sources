# __imp_load_RpcAsyncCompleteCall

- ea: `0x180024444`
- end: `0x180024450`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800233e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180024444`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180024444  lea     rax, __imp_RpcAsyncCompleteCall
0x18002444b  jmp     __tailMerge_rpcrt4_dll
```
