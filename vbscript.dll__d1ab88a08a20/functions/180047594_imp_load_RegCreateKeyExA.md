# __imp_load_RegCreateKeyExA

- ea: `0x180047594`
- end: `0x1800475a0`
- name: `__imp_load_RegCreateKeyExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800474df`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x180047594`

## pseudocode

```c
__int64 load_RegCreateKeyExA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180047594  lea     rax, __imp_RegCreateKeyExA
0x18004759b  jmp     __tailMerge_advapi32_dll
```
