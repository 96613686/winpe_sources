# __imp_load_DnsNameCompare_W

- ea: `0x180021083`
- end: `0x18002108f`
- name: `__imp_load_DnsNameCompare_W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021004`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180021083`

## pseudocode

```c
__int64 load_DnsNameCompare_W()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x180021083  lea     rax, __imp_DnsNameCompare_W
0x18002108a  jmp     __tailMerge_dnsapi_dll
```
