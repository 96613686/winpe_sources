# __imp_load_LookupPrivilegeValueW

- ea: `0x180002353`
- end: `0x18000235f`
- name: `__imp_load_LookupPrivilegeValueW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!LookupPrivilegeValueW` at `0x180002353`

## pseudocode

```c
__int64 load_LookupPrivilegeValueW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002353  lea     rax, __imp_LookupPrivilegeValueW
0x18000235a  jmp     __tailMerge_advapi32_dll
```
