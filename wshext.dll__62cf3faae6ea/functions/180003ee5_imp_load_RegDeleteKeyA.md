# __imp_load_RegDeleteKeyA

- ea: `0x180003ee5`
- end: `0x180003ef1`
- name: `__imp_load_RegDeleteKeyA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegDeleteKeyA` at `0x180003ee5`

## pseudocode

```c
__int64 load_RegDeleteKeyA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003ee5  lea     rax, __imp_RegDeleteKeyA
0x180003eec  jmp     __tailMerge_advapi32_dll
```
