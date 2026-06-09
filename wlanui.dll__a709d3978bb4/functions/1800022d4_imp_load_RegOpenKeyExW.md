# __imp_load_RegOpenKeyExW

- ea: `0x1800022d4`
- end: `0x1800022e0`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000221f`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800022d4`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022d4  lea     rax, __imp_RegOpenKeyExW
0x1800022db  jmp     __tailMerge_advapi32_dll
```
