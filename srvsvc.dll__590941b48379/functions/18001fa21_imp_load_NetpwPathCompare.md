# __imp_load_NetpwPathCompare

- ea: `0x18001fa21`
- end: `0x18001fa2d`
- name: `__imp_load_NetpwPathCompare`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f049`

## import_xrefs

- `netutils!NetpwPathCompare` at `0x18001fa21`

## pseudocode

```c
__int64 load_NetpwPathCompare()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x18001fa21  lea     rax, __imp_NetpwPathCompare
0x18001fa28  jmp     __tailMerge_netutils_dll
```
