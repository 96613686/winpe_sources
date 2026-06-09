# __imp_load_NetpwNameCompare

- ea: `0x18001f9fd`
- end: `0x18001fa09`
- name: `__imp_load_NetpwNameCompare`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f049`

## import_xrefs

- `netutils!NetpwNameCompare` at `0x18001f9fd`

## pseudocode

```c
__int64 load_NetpwNameCompare()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x18001f9fd  lea     rax, __imp_NetpwNameCompare
0x18001fa04  jmp     __tailMerge_netutils_dll
```
