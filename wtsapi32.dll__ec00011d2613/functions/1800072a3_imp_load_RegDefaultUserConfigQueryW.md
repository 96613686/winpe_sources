# __imp_load_RegDefaultUserConfigQueryW

- ea: `0x1800072a3`
- end: `0x1800072af`
- name: `__imp_load_RegDefaultUserConfigQueryW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180007200`

## import_xrefs

- `REGAPI!RegDefaultUserConfigQueryW` at `0x1800072a3`

## pseudocode

```c
__int64 load_RegDefaultUserConfigQueryW()
{
  return _tailMerge_regapi_dll();
}

```

## disassembly

```asm
0x1800072a3  lea     rax, __imp_RegDefaultUserConfigQueryW
0x1800072aa  jmp     __tailMerge_regapi_dll
```
