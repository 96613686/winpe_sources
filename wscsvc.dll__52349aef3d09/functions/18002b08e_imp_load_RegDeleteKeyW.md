# __imp_load_RegDeleteKeyW

- ea: `0x18002b08e`
- end: `0x18002b09a`
- name: `__imp_load_RegDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002b00f`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x18002b08e`

## pseudocode

```c
__int64 load_RegDeleteKeyW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18002b08e  lea     rax, __imp_RegDeleteKeyW
0x18002b095  jmp     __tailMerge_advapi32_dll
```
