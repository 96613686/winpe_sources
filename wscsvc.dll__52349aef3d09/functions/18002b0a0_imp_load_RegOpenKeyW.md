# __imp_load_RegOpenKeyW

- ea: `0x18002b0a0`
- end: `0x18002b0ac`
- name: `__imp_load_RegOpenKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002b00f`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x18002b0a0`

## pseudocode

```c
__int64 load_RegOpenKeyW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18002b0a0  lea     rax, __imp_RegOpenKeyW
0x18002b0a7  jmp     __tailMerge_advapi32_dll
```
