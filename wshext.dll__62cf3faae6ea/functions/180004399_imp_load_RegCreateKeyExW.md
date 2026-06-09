# __imp_load_RegCreateKeyExW

- ea: `0x180004399`
- end: `0x1800043a5`
- name: `__imp_load_RegCreateKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180004399`

## pseudocode

```c
__int64 load_RegCreateKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180004399  lea     rax, __imp_RegCreateKeyExW
0x1800043a0  jmp     __tailMerge_advapi32_dll
```
