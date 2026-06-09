# __imp_load_RegCreateKeyExW

- ea: `0x18004787d`
- end: `0x180047889`
- name: `__imp_load_RegCreateKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800474df`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18004787d`

## pseudocode

```c
__int64 load_RegCreateKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18004787d  lea     rax, __imp_RegCreateKeyExW
0x180047884  jmp     __tailMerge_advapi32_dll
```
