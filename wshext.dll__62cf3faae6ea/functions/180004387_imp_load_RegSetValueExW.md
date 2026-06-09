# __imp_load_RegSetValueExW

- ea: `0x180004387`
- end: `0x180004393`
- name: `__imp_load_RegSetValueExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180004387`

## pseudocode

```c
__int64 load_RegSetValueExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180004387  lea     rax, __imp_RegSetValueExW
0x18000438e  jmp     __tailMerge_advapi32_dll
```
