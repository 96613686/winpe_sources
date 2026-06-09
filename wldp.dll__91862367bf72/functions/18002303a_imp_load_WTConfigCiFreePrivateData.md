# __imp_load_WTConfigCiFreePrivateData

- ea: `0x18002303a`
- end: `0x180023046`
- name: `__imp_load_WTConfigCiFreePrivateData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022ef5`

## import_xrefs

- `WINTRUST!WTConfigCiFreePrivateData` at `0x18002303a`

## pseudocode

```c
__int64 load_WTConfigCiFreePrivateData()
{
  return _tailMerge_wintrust_dll();
}

```

## disassembly

```asm
0x18002303a  lea     rax, __imp_WTConfigCiFreePrivateData
0x180023041  jmp     __tailMerge_wintrust_dll
```
