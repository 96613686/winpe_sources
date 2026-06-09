# __imp_load_RegOpenKeyExW

- ea: `0x180004375`
- end: `0x180004381`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180004375`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180004375  lea     rax, __imp_RegOpenKeyExW
0x18000437c  jmp     __tailMerge_advapi32_dll
```
