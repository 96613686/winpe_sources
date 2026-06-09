# __imp_load_RpcImpersonateClient

- ea: `0x180020a26`
- end: `0x180020a32`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180020740`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180020a26`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x180020a26  lea     rax, __imp_RpcImpersonateClient
0x180020a2d  jmp     __tailMerge_rpcrt4_dll
```
