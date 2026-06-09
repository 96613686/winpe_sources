# __imp_load_RegUserConfigSet

- ea: `0x18000727f`
- end: `0x18000728b`
- name: `__imp_load_RegUserConfigSet`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegUserConfigSet` at `0x18000727f`

## pseudocode

```c
__int64 load_RegUserConfigSet()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x18000727f  lea     rax, __imp_RegUserConfigSet
0x180007286  jmp     __tailMerge_regapi_dll
```
