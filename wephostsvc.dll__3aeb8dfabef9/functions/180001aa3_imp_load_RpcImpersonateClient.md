# __imp_load_RpcImpersonateClient

- ea: `0x180001aa3`
- end: `0x180001aaf`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001970`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180001aa3`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180001aa3  lea     rax, __imp_RpcImpersonateClient
0x180001aaa  jmp     __tailMerge_rpcrt4_dll
```
