# __imp_load_RegInstallW

- ea: `0x180002adf`
- end: `0x180002aeb`
- name: `__imp_load_RegInstallW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002a60`

## import_xrefs

- `ADVPACK!RegInstallW` at `0x180002adf`

## pseudocode

```c
__int64 load_RegInstallW()
{
  return _tailMerge_advpack_dll();
}

```

## disassembly

```asm
0x180002adf  lea     rax, __imp_RegInstallW
0x180002ae6  jmp     __tailMerge_advpack_dll
```
