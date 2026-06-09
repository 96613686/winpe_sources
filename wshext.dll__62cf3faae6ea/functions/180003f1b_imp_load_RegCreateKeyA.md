# __imp_load_RegCreateKeyA

- ea: `0x180003f1b`
- end: `0x180003f27`
- name: `__imp_load_RegCreateKeyA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180003d4b`

## import_xrefs

- `ADVAPI32!RegCreateKeyA` at `0x180003f1b`

## pseudocode

```c
__int64 load_RegCreateKeyA()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180003f1b  lea     rax, __imp_RegCreateKeyA
0x180003f22  jmp     __tailMerge_advapi32_dll
```
