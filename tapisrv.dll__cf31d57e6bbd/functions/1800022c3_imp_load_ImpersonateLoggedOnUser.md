# __imp_load_ImpersonateLoggedOnUser

- ea: `0x1800022c3`
- end: `0x1800022cf`
- name: `__imp_load_ImpersonateLoggedOnUser`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800022c3`

## pseudocode

```c
__int64 load_ImpersonateLoggedOnUser()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022c3  lea     rax, __imp_ImpersonateLoggedOnUser
0x1800022ca  jmp     __tailMerge_advapi32_dll
```
