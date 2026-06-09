# __imp_load_GetUrlCacheConfigInfoW

- ea: `0x180002094`
- end: `0x1800020a0`
- name: `__imp_load_GetUrlCacheConfigInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001ff1`

## import_xrefs

- `WININET!GetUrlCacheConfigInfoW` at `0x180002094`

## pseudocode

```c
__int64 load_GetUrlCacheConfigInfoW()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180002094  lea     rax, __imp_GetUrlCacheConfigInfoW
0x18000209b  jmp     __tailMerge_wininet_dll
```
