# __imp_load_RegCreateKeyExW

- ea: `0x1800022f8`
- end: `0x180002304`
- name: `__imp_load_RegCreateKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000221f`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800022f8`

## pseudocode

```c
__int64 load_RegCreateKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022f8  lea     rax, __imp_RegCreateKeyExW
0x1800022ff  jmp     __tailMerge_advapi32_dll
```
