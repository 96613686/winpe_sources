# __imp_load_SetKernelObjectSecurity

- ea: `0x18000227b`
- end: `0x180002287`
- name: `__imp_load_SetKernelObjectSecurity`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!SetKernelObjectSecurity` at `0x18000227b`

## pseudocode

```c
__int64 load_SetKernelObjectSecurity()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000227b  lea     rax, __imp_SetKernelObjectSecurity
0x180002282  jmp     __tailMerge_advapi32_dll
```
