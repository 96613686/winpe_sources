# __imp_load_IcmpCreateFile

- ea: `0x18000f290`
- end: `0x18000f29c`
- name: `__imp_load_IcmpCreateFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000f150`

## import_xrefs

- `IPHLPAPI!IcmpCreateFile` at `0x18000f290`

## pseudocode

```c
__int64 load_IcmpCreateFile()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x18000f290  lea     rax, __imp_IcmpCreateFile
0x18000f297  jmp     __tailMerge_iphlpapi_dll
```
