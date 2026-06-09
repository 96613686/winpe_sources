# __imp_load_RegOpenKeyExA

- ea: `0x180003ddc`
- end: `0x180003de8`
- name: `__imp_load_RegOpenKeyExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180003ddc`

## pseudocode

```c
__int64 load_RegOpenKeyExA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003ddc  lea     rax, __imp_RegOpenKeyExA
0x180003de3  jmp     __tailMerge_advapi32_dll
```
