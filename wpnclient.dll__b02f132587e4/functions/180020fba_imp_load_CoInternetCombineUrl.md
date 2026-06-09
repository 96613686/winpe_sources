# __imp_load_CoInternetCombineUrl

- ea: `0x180020fba`
- end: `0x180020fc6`
- name: `__imp_load_CoInternetCombineUrl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020f3b`

## import_xrefs

- `urlmon!CoInternetCombineUrl` at `0x180020fba`

## pseudocode

```c
__int64 load_CoInternetCombineUrl()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x180020fba  lea     rax, __imp_CoInternetCombineUrl
0x180020fc1  jmp     __tailMerge_urlmon_dll
```
