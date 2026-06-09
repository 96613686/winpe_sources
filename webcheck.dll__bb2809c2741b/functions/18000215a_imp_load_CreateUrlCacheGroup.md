# __imp_load_CreateUrlCacheGroup

- ea: `0x18000215a`
- end: `0x180002166`
- name: `__imp_load_CreateUrlCacheGroup`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ff1`

## import_xrefs

- `WININET!CreateUrlCacheGroup` at `0x18000215a`

## pseudocode

```c
__int64 load_CreateUrlCacheGroup()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x18000215a  lea     rax, __imp_CreateUrlCacheGroup
0x180002161  jmp     __tailMerge_wininet_dll
```
