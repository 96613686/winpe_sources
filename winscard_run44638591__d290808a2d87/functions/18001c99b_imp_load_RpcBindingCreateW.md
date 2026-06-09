# __imp_load_RpcBindingCreateW

- ea: `0x18001c99b`
- end: `0x18001c9a7`
- name: `__imp_load_RpcBindingCreateW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c856`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18001c99b`

## pseudocode

```c
__int64 load_RpcBindingCreateW()
{
  return _tailMerge_rpcrt4_dll();
}

```

## disassembly

```asm
0x18001c99b  lea     rax, __imp_RpcBindingCreateW
0x18001c9a2  jmp     __tailMerge_rpcrt4_dll
```
