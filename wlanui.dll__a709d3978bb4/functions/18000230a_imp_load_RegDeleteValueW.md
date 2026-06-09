# __imp_load_RegDeleteValueW

- ea: `0x18000230a`
- end: `0x180002316`
- name: `__imp_load_RegDeleteValueW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000221f`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18000230a`

## pseudocode

```c
__int64 load_RegDeleteValueW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000230a  lea     rax, __imp_RegDeleteValueW
0x180002311  jmp     __tailMerge_advapi32_dll
```
