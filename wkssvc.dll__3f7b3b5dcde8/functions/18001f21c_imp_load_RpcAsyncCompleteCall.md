# __imp_load_RpcAsyncCompleteCall

- ea: `0x18001f21c`
- end: `0x18001f228`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ef90`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f21c`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001f21c  lea     rax, __imp_RpcAsyncCompleteCall
0x18001f223  jmp     __tailMerge_rpcrt4_dll
```
