# __imp_load_RpcStringBindingComposeA

- ea: `0x1800021ef`
- end: `0x1800021fb`
- name: `__imp_load_RpcStringBindingComposeA`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020e0`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeA` at `0x1800021ef`

## pseudocode

```c
__int64 load_RpcStringBindingComposeA()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x1800021ef  lea     rax, __imp_RpcStringBindingComposeA
0x1800021f6  jmp     __tailMerge_rpcrt4_dll
```
