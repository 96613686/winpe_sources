# __imp_load_Icmp6CreateFile

- ea: `0x1800354ac`
- end: `0x1800354b8`
- name: `__imp_load_Icmp6CreateFile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1800353e5`

## import_xrefs

- `IPHLPAPI!Icmp6CreateFile` at `0x1800354ac`

## pseudocode

```c
__int64 load_Icmp6CreateFile()
{
  return _tailMerge_iphlpapi_dll();
}

```

## disassembly

```asm
0x1800354ac  lea     rax, __imp_Icmp6CreateFile
0x1800354b3  jmp     __tailMerge_iphlpapi_dll
```
