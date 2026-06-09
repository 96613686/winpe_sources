# __imp_load_WinHttpGetDefaultProxyConfiguration

- ea: `0x180001d59`
- end: `0x180001d65`
- name: `__imp_load_WinHttpGetDefaultProxyConfiguration`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001c02`

## import_xrefs

- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180001d59`

## pseudocode

```c
__int64 load_WinHttpGetDefaultProxyConfiguration()
{
  return _tailMerge_winhttp_dll();
}

```

## disassembly

```asm
0x180001d59  lea     rax, __imp_WinHttpGetDefaultProxyConfiguration
0x180001d60  jmp     __tailMerge_winhttp_dll
```
