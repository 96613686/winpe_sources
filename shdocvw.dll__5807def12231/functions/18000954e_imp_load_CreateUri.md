# __imp_load_CreateUri

- ea: `0x18000954e`
- end: `0x18000955a`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800094cf`

## import_xrefs

- `urlmon!CreateUri` at `0x18000954e`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x18000954e  lea     rax, __imp_CreateUri
0x180009555  jmp     __tailMerge_urlmon_dll
```
