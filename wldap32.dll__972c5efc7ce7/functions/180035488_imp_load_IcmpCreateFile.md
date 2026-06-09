# __imp_load_IcmpCreateFile

- ea: `0x180035488`
- end: `0x180035494`
- name: `__imp_load_IcmpCreateFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1800353e5`

## import_xrefs

- `IPHLPAPI!IcmpCreateFile` at `0x180035488`

## pseudocode

```c
__int64 load_IcmpCreateFile()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x180035488  lea     rax, __imp_IcmpCreateFile
0x18003548f  jmp     __tailMerge_iphlpapi_dll
```
