# __imp_load_RpcImpersonateClient

- ea: `0x18001e998`
- end: `0x18001e9a4`
- name: `__imp_load_RpcImpersonateClient`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001e919`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001e998`

## pseudocode

```c
__int64 load_RpcImpersonateClient()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001e998  lea     rax, __imp_RpcImpersonateClient
0x18001e99f  jmp     __tailMerge_rpcrt4_dll
```
