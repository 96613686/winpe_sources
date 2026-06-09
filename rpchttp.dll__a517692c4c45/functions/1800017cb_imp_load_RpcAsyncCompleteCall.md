# __imp_load_RpcAsyncCompleteCall

- ea: `0x1800017cb`
- end: `0x1800017d7`
- name: `__imp_load_RpcAsyncCompleteCall`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001354`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800017cb`

## pseudocode

```c
__int64 load_RpcAsyncCompleteCall()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800017cb  lea     rax, __imp_RpcAsyncCompleteCall
0x1800017d2  jmp     __tailMerge_rpcrt4_dll
```
