# __imp_load_RpcAsyncCompleteCall

- ea: `0x18001ebec`
- end: `0x18001ebf8`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001e919`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001ebec`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001ebec  lea     rax, __imp_RpcAsyncCompleteCall
0x18001ebf3  jmp     __tailMerge_rpcrt4_dll
```
