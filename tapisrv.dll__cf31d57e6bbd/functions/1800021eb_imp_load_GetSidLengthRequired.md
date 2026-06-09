# __imp_load_GetSidLengthRequired

- ea: `0x1800021eb`
- end: `0x1800021f7`
- name: `__imp_load_GetSidLengthRequired`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetSidLengthRequired` at `0x1800021eb`

## pseudocode

```c
__int64 load_GetSidLengthRequired()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021eb  lea     rax, __imp_GetSidLengthRequired
0x1800021f2  jmp     __tailMerge_advapi32_dll
```
