# __imp_load_GetAclInformation

- ea: `0x18000230b`
- end: `0x180002317`
- name: `__imp_load_GetAclInformation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetAclInformation` at `0x18000230b`

## pseudocode

```c
__int64 load_GetAclInformation()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000230b  lea     rax, __imp_GetAclInformation
0x180002312  jmp     __tailMerge_advapi32_dll
```
