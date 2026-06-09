# __imp_load_RegOpenKeyA

- ea: `0x180003f09`
- end: `0x180003f15`
- name: `__imp_load_RegOpenKeyA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegOpenKeyA` at `0x180003f09`

## pseudocode

```c
__int64 load_RegOpenKeyA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003f09  lea     rax, __imp_RegOpenKeyA
0x180003f10  jmp     __tailMerge_advapi32_dll
```
