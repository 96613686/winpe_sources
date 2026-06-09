# __imp_load_DnsNameCompare_W

- ea: `0x18000f27e`
- end: `0x18000f28a`
- name: `__imp_load_DnsNameCompare_W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f1ff`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x18000f27e`

## pseudocode

```c
__int64 load_DnsNameCompare_W()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x18000f27e  lea     rax, __imp_DnsNameCompare_W
0x18000f285  jmp     __tailMerge_dnsapi_dll
```
