# __imp_load_RegUserConfigQuery

- ea: `0x180007291`
- end: `0x18000729d`
- name: `__imp_load_RegUserConfigQuery`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegUserConfigQuery` at `0x180007291`

## pseudocode

```c
__int64 load_RegUserConfigQuery()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x180007291  lea     rax, __imp_RegUserConfigQuery
0x180007298  jmp     __tailMerge_regapi_dll
```
