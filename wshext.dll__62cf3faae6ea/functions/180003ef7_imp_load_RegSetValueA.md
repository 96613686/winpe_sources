# __imp_load_RegSetValueA

- ea: `0x180003ef7`
- end: `0x180003f03`
- name: `__imp_load_RegSetValueA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegSetValueA` at `0x180003ef7`

## pseudocode

```c
__int64 load_RegSetValueA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003ef7  lea     rax, __imp_RegSetValueA
0x180003efe  jmp     __tailMerge_advapi32_dll
```
