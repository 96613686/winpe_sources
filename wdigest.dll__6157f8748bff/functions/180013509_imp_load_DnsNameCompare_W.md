# __imp_load_DnsNameCompare_W

- ea: `0x180013509`
- end: `0x180013515`
- name: `__imp_load_DnsNameCompare_W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001348a`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180013509`

## pseudocode

```c
__int64 load_DnsNameCompare_W()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180013509  lea     rax, __imp_DnsNameCompare_W
0x180013510  jmp     __tailMerge_dnsapi_dll
```
