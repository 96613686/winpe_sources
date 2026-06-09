# __imp_load_GetLengthSid

- ea: `0x18000217f`
- end: `0x18000218b`
- name: `__imp_load_GetLengthSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x18000217f`

## pseudocode

```c
__int64 load_GetLengthSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000217f  lea     rax, __imp_GetLengthSid
0x180002186  jmp     __tailMerge_advapi32_dll
```
