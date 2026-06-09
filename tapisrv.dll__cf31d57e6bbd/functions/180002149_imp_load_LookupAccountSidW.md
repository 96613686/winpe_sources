# __imp_load_LookupAccountSidW

- ea: `0x180002149`
- end: `0x180002155`
- name: `__imp_load_LookupAccountSidW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x180002149`

## pseudocode

```c
__int64 load_LookupAccountSidW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002149  lea     rax, __imp_LookupAccountSidW
0x180002150  jmp     __tailMerge_advapi32_dll
```
