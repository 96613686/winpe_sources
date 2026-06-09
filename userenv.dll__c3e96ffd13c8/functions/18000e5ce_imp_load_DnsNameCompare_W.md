# __imp_load_DnsNameCompare_W

- ea: `0x18000e5ce`
- end: `0x18000e5da`
- name: `__imp_load_DnsNameCompare_W`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e54f`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x18000e5ce`

## pseudocode

```c
__int64 load_DnsNameCompare_W()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x18000e5ce  lea     rax, __imp_DnsNameCompare_W
0x18000e5d5  jmp     __tailMerge_dnsapi_dll
```
