# __imp_load_RegCreateKeyExA

- ea: `0x180003e00`
- end: `0x180003e0c`
- name: `__imp_load_RegCreateKeyExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x180003e00`

## pseudocode

```c
__int64 load_RegCreateKeyExA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003e00  lea     rax, __imp_RegCreateKeyExA
0x180003e07  jmp     __tailMerge_advapi32_dll
```
