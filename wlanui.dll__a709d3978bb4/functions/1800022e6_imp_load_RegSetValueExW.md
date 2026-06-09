# __imp_load_RegSetValueExW

- ea: `0x1800022e6`
- end: `0x1800022f2`
- name: `__imp_load_RegSetValueExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000221f`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800022e6`

## pseudocode

```c
__int64 load_RegSetValueExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022e6  lea     rax, __imp_RegSetValueExW
0x1800022ed  jmp     __tailMerge_advapi32_dll
```
