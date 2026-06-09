# __imp_load_GetKernelObjectSecurity

- ea: `0x18000228d`
- end: `0x180002299`
- name: `__imp_load_GetKernelObjectSecurity`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetKernelObjectSecurity` at `0x18000228d`

## pseudocode

```c
__int64 load_GetKernelObjectSecurity()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000228d  lea     rax, __imp_GetKernelObjectSecurity
0x180002294  jmp     __tailMerge_advapi32_dll
```
