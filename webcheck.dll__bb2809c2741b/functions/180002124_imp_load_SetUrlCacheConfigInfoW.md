# __imp_load_SetUrlCacheConfigInfoW

- ea: `0x180002124`
- end: `0x180002130`
- name: `__imp_load_SetUrlCacheConfigInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001ff1`

## import_xrefs

- `WININET!SetUrlCacheConfigInfoW` at `0x180002124`

## pseudocode

```c
__int64 load_SetUrlCacheConfigInfoW()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180002124  lea     rax, __imp_SetUrlCacheConfigInfoW
0x18000212b  jmp     __tailMerge_wininet_dll
```
