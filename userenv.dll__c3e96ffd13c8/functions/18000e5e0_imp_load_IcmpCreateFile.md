# __imp_load_IcmpCreateFile

- ea: `0x18000e5e0`
- end: `0x18000e5ec`
- name: `__imp_load_IcmpCreateFile`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000e4a0`

## import_xrefs

- `IPHLPAPI!IcmpCreateFile` at `0x18000e5e0`

## pseudocode

```c
__int64 load_IcmpCreateFile()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18000e5e0  lea     rax, __imp_IcmpCreateFile
0x18000e5e7  jmp     __tailMerge_iphlpapi_dll
```
