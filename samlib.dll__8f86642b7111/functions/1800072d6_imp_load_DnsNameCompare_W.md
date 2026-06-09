# __imp_load_DnsNameCompare_W

- ea: `0x1800072d6`
- end: `0x1800072e2`
- name: `__imp_load_DnsNameCompare_W`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007257`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x1800072d6`

## pseudocode

```c
__int64 load_DnsNameCompare_W()
{
  return _tailMerge_dnsapi_dll();
}

```

## disassembly

```asm
0x1800072d6  lea     rax, __imp_DnsNameCompare_W
0x1800072dd  jmp     __tailMerge_dnsapi_dll
```
