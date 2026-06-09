# __imp_load_RpcMgmtSetComTimeout

- ea: `0x180021c04`
- end: `0x180021c10`
- name: `__imp_load_RpcMgmtSetComTimeout`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020740`

## import_xrefs

- `RPCRT4!RpcMgmtSetComTimeout` at `0x180021c04`

## pseudocode

```c
__int64 load_RpcMgmtSetComTimeout()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180021c04  lea     rax, __imp_RpcMgmtSetComTimeout
0x180021c0b  jmp     __tailMerge_rpcrt4_dll
```
