# __imp_load_RpcStringBindingComposeW

- ea: `0x18002354f`
- end: `0x18002355b`
- name: `__imp_load_RpcStringBindingComposeW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180023421`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18002354f`

## pseudocode

```c
__int64 load_RpcStringBindingComposeW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18002354f  lea     rax, __imp_RpcStringBindingComposeW
0x180023556  jmp     __tailMerge_rpcrt4_dll
```
