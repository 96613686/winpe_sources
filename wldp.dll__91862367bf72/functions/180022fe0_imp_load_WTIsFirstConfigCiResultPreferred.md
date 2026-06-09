# __imp_load_WTIsFirstConfigCiResultPreferred

- ea: `0x180022fe0`
- end: `0x180022fec`
- name: `__imp_load_WTIsFirstConfigCiResultPreferred`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022ef5`

## import_xrefs

- `WINTRUST!WTIsFirstConfigCiResultPreferred` at `0x180022fe0`

## pseudocode

```c
__int64 load_WTIsFirstConfigCiResultPreferred()
{
  return _tailMerge_wintrust_dll();
}

```

## disassembly

```asm
0x180022fe0  lea     rax, __imp_WTIsFirstConfigCiResultPreferred
0x180022fe7  jmp     __tailMerge_wintrust_dll
```
