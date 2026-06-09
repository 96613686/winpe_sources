# __imp_load_RegSetValueExA

- ea: `0x180003dee`
- end: `0x180003dfa`
- name: `__imp_load_RegSetValueExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x180003dee`

## pseudocode

```c
__int64 load_RegSetValueExA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003dee  lea     rax, __imp_RegSetValueExA
0x180003df5  jmp     __tailMerge_advapi32_dll
```
