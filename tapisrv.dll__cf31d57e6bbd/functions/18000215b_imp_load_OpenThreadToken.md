# __imp_load_OpenThreadToken

- ea: `0x18000215b`
- end: `0x180002167`
- name: `__imp_load_OpenThreadToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18000215b`

## pseudocode

```c
__int64 load_OpenThreadToken()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000215b  lea     rax, __imp_OpenThreadToken
0x180002162  jmp     __tailMerge_advapi32_dll
```
