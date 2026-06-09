# __imp_load_GetComputerObjectNameW

- ea: `0x1800026ef`
- end: `0x1800026fb`
- name: `__imp_load_GetComputerObjectNameW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180002670`

## import_xrefs

- `Secur32!GetComputerObjectNameW` at `0x1800026ef`

## pseudocode

```c
__int64 load_GetComputerObjectNameW()
{
  return _tailMerge_secur32_dll();
}

```

## disassembly

```asm
0x1800026ef  lea     rax, __imp_GetComputerObjectNameW
0x1800026f6  jmp     __tailMerge_secur32_dll
```
